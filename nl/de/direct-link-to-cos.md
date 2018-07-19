---

copyright:
  years: 2017, 2018
lastupdated: "2018-05-22"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Verbindung zu IBM Cloud Object Storage über IBM Cloud Direct Link herstellen

In diesem Dokument wird die Vorgehensweise zum Konfigurieren von IBM Cloud Direct Link für den Zugriff auf IBM Cloud Object Storage (COS) beschrieben. Obwohl die hier beschriebenen Methoden mit COS entworfen und getestet wurden, können Sie möglicherweise auch auf bestimmte andere IBM Cloud-Services angewendet werden.

Gemäß der aktuell gültigen Richtlinie verweigert IBM Cloud Direct Link den Zugriff auf private IBM Cloud-Serviceendpunkte (dies gilt auch für die von IBM Cloud Object Storage (COS) verwendeten Endpunkte). Das in diesem Dokument beschriebene Verfahren basiert auf dem direkten Zugriff auf COS über Server, die im IBM Cloud-Konto eines Kunden gehostet werden. Nach dem Einrichten kann der Server jedes Kunden Datenverkehr in beiden Richtungen zwischen privaten IBM Cloud-Serviceendpunkten und den über Direct Link verbundenen zugehörigen fernen Netzen weiterleiten.

## Was ist IBM Cloud Object Storage (COS)?

IBM Cloud Object Storage (COS) ist eine webbasierte Plattform zum Speichern unstrukturierter Daten. Diese Plattform bietet Zuverlässigkeit, Sicherheit, Verfügbarkeit und Disaster-Recovery ohne manuelle Replikation.

In IBM Cloud Object Storage gespeicherte Daten werden verschlüsselt und auf mehrere geografische Standorte verteilt. Die Daten sind über eine Implementierung der S3-API zugänglich. Dieser Service nutzt Technologien für die verteilte Speicherung, die vom IBM Cloud Object Storage-Service bereitgestellt werden.

IBM COS ist in drei Konfigurationen verfügbar: **Überregional**, **Regional** und **Single Site** (einzelner Standort).

 * Der überregionale Service (Cross Region) bietet größere Dauerhaftigkeit und höhere Verfügbarkeit als die Verwendung einer einzigen Region, jedoch auf Kosten einer etwas höheren Latenz. Dieser Service ist aktuell in den USA und in der EU verfügbar.
 
 * Der regionale Service bietet die umgekehrte Funktionalität, d. h. Objekte werden auf mehrere Verfügbarkeitszonen innerhalb einer Region verteilt. Wenn eine Region oder Verfügbarkeitszone nicht zugänglich ist, kann der Objektspeicher reibungslos weiter genutzt werden. Alle fehlenden Änderungen werden angewendet, sobald das nicht zugängliche Rechenzentrum wieder online ist.
  
 * Der Service für einen einzelnen Standort bietet kosteneffizienten Zugriff auf Cloud Object Storage in einem ausgewählten Rechenzentrum.

### Private und öffentliche COS-Endpunkte
Endpunkte sind URLs, die von Anwendungen verwendet werden, um COS-Befehle abzusetzen und Daten mit COS auszutauschen. Jeder Endpunkt verwendet dieselbe Anwendungsprogrammierschnittstelle (Application Programming Interface, API) für die Interaktion mit COS.

In IBM Cloud bereitgestellte Server verwenden private API-Endpunkte für Services (einschließlich COS). Private Endpunkte ermöglichen den Kunden sehr schnelle Direktverbindungen zu Services ohne Zusatzkosten für die Bandbreite.

Öffentliche COS-Endpunkte bieten IBM Cloud-Kunden den Zugriff auf dieselben COS-Daten, die auch über IBM Cloud zugänglich sind, jedoch von jedem beliebigen Standort mit Internetadresse aus.

Bei öffentlichen COS-Endpunkten sind die beiden folgenden Einschränkungen zu beachten:
 * Für die Verwendung öffentlicher Endpunkte können nutzungsabhängige Kosten für die Bandbreite anfallen, die über die Nutzungsgebühr für den COS-Service hinaus gehen. 
 * Obwohl alle Daten bei der Übertragung verschlüsselt werden, können Kunden Bedenken bezüglich der Vertrauchlichkeit oder der Einhaltung von Vorschriften bei der Datenübertragung im Internet hegen.

## Was ist IBM Cloud Direct Link?
IBM Cloud Direct Link ist eine Produktsuite, mit der Kunden sichere private Verbindungen zwischen ihren fernen Netzumgebungen und ihren IBM Cloud-Bereitstellungen herstellen können. Die über Direct Link ausgetauschten Daten werden zu keinem Zeitpunkt im Internet zugänglich gemacht.

## Cloud Object Storage (COS) über IBM Cloud Direct Link verwenden
IBM Entwickler haben ein Verfahren entwickelt, mit dem ein IBM Cloud-Kunde, der COS und Direct Link erworben hat, Fernverbindungen zu privaten COS-Endpunkten herstellen kann. Dieser Verbindungstyp macht die Vorteile privater Serviceendpunkte auch für Kundensysteme außerhalb von IBM Cloud-Einrichtungen nutzbar.
 
Diese Lösung wird in den folgenden Abschnitten dargestellt und erläutert.

### Reverse Proxy

**Grundvoraussetzung: Ferne Clients leiten Anforderungen (einschließlich geschützter Berechtigungsnachweise) über einen privaten Server an COS weiter**

![reverse=proxy](images/reverse-proxy.png)

COS-Anforderungen über HTTPS (sicheres HTTP) werden von einem Client an einem fernen Standort eingeleitet. Sie werden über IBM Cloud Direct Link geschützt zu einem Cluster mit _Reverse-Proxy-Servern_ übertragen, der im IBM Cloud-Konto eines Kunden bereitgestellt wird. Von dort aus werden Anforderungen an einen privaten COS-Endpunkt weitergeleitet und verarbeitet. Die Ergebnisse werden anschließend an den fernen anrufenden Client zurückgegeben.

Jeder Beispielcode, der mit COS funktioniert, müsste auch über einen _Reverse-Proxy_-Server ausgeführt werden können. Als einzige Anpassung muss der Client anstelle der von IBM veröffentlichten URL für einen privaten COS-Endpunkt die IP-Adresse oder URL des Reverse-Proxy-Servers als Ziel verwenden.

#### NginX-Reverse-Proxy installieren
**NginX** ist ein technisch ausgereifter, kompakter und schneller Open-Source-Web-Server, der auf bestimmte Tasks spezialisiert ist (einschließlich der zuvor genannten Rolle als _Reverse-Proxy_).

Die folgenden Anweisungen und Konfigurationsinformationen zum Einrichten eines NginX-Reverse-Proxy-Servers können an Ihre Umgebung angepasst und angewendet werden. Wenn Sie Hilfestellung oder zusätzliche Informationen benötigen, lesen Sie den Abschnitt zum Reverse Proxy in der [NginX-Dokumentation](https://docs.nginx.com/nginx/admin-guide/web-server/reverse-proxy/) oder suchen Sie in [stackoverflow](http://stackoverflow.com) nach Beispielen.

1. Stellen Sie Ihre virtuelle Serverinstanzen (VSI) oder Bare-Metal-Server mit dem minimalen Build von **RHEL**- oder **CentOS**-Linux bereit (empfohlen).
2. Aktivieren Sie für jede VSI die folgenden Sicherheitsgruppenregeln in der öffentlichen Schnittstelle: `allow_http`, `allow_https`, `allow_outbound`, `allow_ssh`.
3. Aktivieren Sie für jede VSI die Regeln `allow_all` und `allow_outbound` in der privaten Schnittstelle und wählen Sie **Speichern** aus.
4. Melden Sie sich mit **PuTTY** unter Windows oder mit Ihrem Desktop-Terminalprogramm über `ssh` bei Ihrem neuen Server als Rootbenutzer an.
5. Führen Sie ein Upgrade für Ihr Betriebssystem durch (`yum update`).
6. Installieren Sie das EPEL-Repository (`yum install epel-release`).
7. Installieren Sie NginX (`yum install nginx`).
8. Starten Sie NginX (`nginx`) und öffnen Sie die IP-Adresse Ihres Servers in einem Browser.
9. Die Standardposition von `nginx.conf` ist `/etc/nginx`. Erstellen Sie eine sichere Kopie.
10. Verschieben Sie die Beispielkonfigurationsdatei `nginx.conf` unten in das Verzeichnis `/etc/nginx`.
11. Erwerben Sie SSL-Zertifikate über das IBM Cloud-Portal oder führen Sie den Befehl `yum install easy-rsa` aus und suchen Sie in Ihren bevorzugten Online-Dokumenten nach Tipps zum Erstellen von selbst signierten Zertifikaten.
12. Fügen Sie Zertifikatsinformationen zur Konfigurationsdatei `nginx.conf` hinzu.
13. Testen Sie die geänderte NginX-Konfiguration mit dem Befehl `nginx -t`.
14. Wenn der Test erfolgreich verlaufen ist, starten Sie `nginx` mit dem Befehl `nginx -s quit; sleep 3; nginx` erneut.
15. Ihr Client sollte jetzt in der Lage sein, COS-Anforderungen an die IP-Adressen oder URLs des NginX-Servers (Proxy) zu schicken.

#### Hinweise:

* Die Lösung setzt voraus, dass Direct Link bestellt und ordnungsgemäß bereitgestellt wurde, obwohl der Test auch ohne diese Voraussetzung erfolgen kann.
* Mit `proxy_cache` kann optionaler Speicher oder Plattencache verwendet werden.
* Für umfangreiche Dateiübertragungen kann ein höherer Zeitlimitwert für `proxy_read_timeout` erforderlich sein.
* Verwenden Sie `keepalive` oder Pacemaker für Hochverfügbarkeit (automatische Funktionsübernahme).

#### Konfigurationsdatei: `nginx.conf`

Die Beispielkonfigurationsdatei wird im folgenden Abschnitt vorgestellt. Diese Datei kann kopiert und eingefügt werden.

```
user nginx;
worker_processes auto;
error_log /var/log/nginx/error.log;
pid /run/nginx.pid;

events {
    worker_connections 1024;
}

http {
    log_format  main  '$remote_addr - $remote_user [$time_local] "$request" '
                      '$status $body_bytes_sent "$http_referer" '
                      '"$http_user_agent" "$http_x_forwarded_for"';

    access_log  /var/log/nginx/access.log  main;

    sendfile            on;
    tcp_nopush          on;
    tcp_nodelay         on;
    keepalive_timeout   5;
    types_hash_max_size 2048;

    include             /etc/nginx/mime.types;
    default_type        application/octet-stream;
    ssl_session_cache shared:SSL:1m;
    ssl_session_timeout  10m;
    ssl_ciphers HIGH:!aNULL:!MD5;
    ssl_prefer_server_ciphers on;
    proxy_http_version 1.1;
    proxy_buffering off;
    proxy_intercept_errors on;

    # IBM COS Endpoints
    # https://console.bluemix.net/docs/infrastructure/cloud-object-storage-infrastructure/endpoints.html#select-regions-and-endpoints
    # US
    server {
        listen       443 ssl http2;
        server_name  us-cos.myibmcloud.com;
        ssl_certificate "/etc/pki/tls/certs/star.myibmcloud.com.pem";
        ssl_certificate_key "/etc/pki/tls/private/star.myibmcloud.com.key";
        location / {
            proxy_set_header Host $server_name;
            proxy_pass https://s3-api.us-geo.objectstorage.service.networklayer.com;
        }
    }

    # Dallas
    server {
        listen       443 ssl http2;
        server_name  dal-cos.myibmcloud.com;
        ssl_certificate "/etc/pki/tls/certs/star.myibmcloud.com.pem";
        ssl_certificate_key "/etc/pki/tls/private/star.myibmcloud.com.key";
        location / {
            proxy_set_header Host $server_name;
            proxy_pass https://s3-api.dal-us-geo.objectstorage.service.networklayer.com;
        }
    }
}
```

In [COS Endpoints](https://console.bluemix.net/docs/infrastructure/cloud-object-storage-infrastructure/endpoints.html#select-regions-and-endpoints) finden Sie eine Liste der privaten Endpunkte für die Verwendung in den oben angegebenen `proxy_pass`-Einträgen.

#### Tipps:

 * Zur Optimierung der Skalierung und Ausfallsicherheit können mehrere Proxy-Server bereitgestellt werden, die verschiedenen Endpunkten zugeordnet sind.
 * Durch Umlauf-DNS auf der Clientseite können einfache Funktionen für Ausweichbetrieb und Lastausgleich bereitgestellt werden.
 * Proxy-Server können hinter einer VRA (Virtual Router Appliance) platziert werden, um Sicherheit und zentrale Protokollierung bereitzustellen.

## IBM Cloud-Funktionalität verwalten und bereitstellen

Dieser Abschnitt enthält Quick Links zur Dokumentation für manche IBM Cloud PaaS- und -SaaS-Angebote die über IBM Cloud Direct Link verbunden werden können.

### Vorgehensweise zur Bereitstellung von Bare-Metal-Servern

Ausführliche Anweisungen zur Vorgehensweise beim Bereitstellen von Bare-Metal-Servern finden Sie in [Einführung in Bare Metal Servers](https://console.bluemix.net/docs/bare-metal/about.html#getting-started-with-bare-metal-servers).

### Vorgehensweise zum Bereitstellen einer Virtual Router Appliance (VRA)

Ausführliche Anweisungen zur Vorgehensweise beim Bereitstellen einer VRA finden Sie in
[IBM Virtual Router Appliance - Einführung](https://console.bluemix.net/docs/infrastructure/virtual-router-appliance/getting-started.html#getting-started).

### Vorgehensweise zum Bereitstellen von IBM Cloud Object Storage (COS)

 * Ausführliche Anweisungen zur Vorgehensweise beim Bereitstellen von COS finden Sie in [Cloud Object Storage Guide](https://console.bluemix.net/catalog/services/cloud-object-storage).

 * Verwenden Sie einen der (zuvor aufgelisteten) privaten Endpunkte zum Erstellen einer Schnittstelle zu Ihrem Bucket oder
zu einem beliebigen Objekt in Ihrem bereitgestellten COS-Konto.
