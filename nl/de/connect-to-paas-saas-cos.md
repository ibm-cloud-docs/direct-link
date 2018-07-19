---

copyright:
  years: 2018
lastupdated: "2018-04-24"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Zusammen: IBM Cloud Direct Link und IBM Cloud Object Storage

In diesem Dokument wird die Vorgehensweise zum Konfigurieren von IBM Cloud Direct Link für den Zugriff auf IBM Cloud Object Storage und andere IBM Cloud-Services beschrieben. Es stehen mehrere Methoden für die Überbrückung von dem privaten IBM Cloud IaaS-Netz, in dem IBM Cloud Direct Link enthalten ist, zu dem “öffentlichen” Netz bereit, das IBM Cloud PaaS- und -SaaS-Funktionen unterstützt, ohne das IaaS-Backbone zu verlassen.

Die aktuelle Richtlinie sieht nicht vor, dass private IBM Cloud-Serviceendpunkte über IBM Cloud Direct Link zugänglich sind. Die in diesem Dokument beschriebenen Verfahren basieren auf dem indirekten Zugriff über Systeme, die von IBM Cloud gehostet werden. Obwohl private Serviceendpunkte nicht über Direct Link erreichbar sind, ist dies für die privaten Server und Geräte eines Kunden nicht ausgeschlossen.

## Was ist IBM Cloud Object Storage (COS)?

IBM Cloud Object Storage ist eine webbasierte Plattform zum Speichern unstrukturierter Daten. Diese Plattform bietet Zuverlässigkeit, Sicherheit, Verfügbarkeit und Disaster-Recovery ohne Replikation. 

Mit IBM Cloud Object Storage gespeicherte Daten werden verschlüsselt und auf mehrere geografische Standorte verteilt. Die Daten sind über eine Implementierung der S3-API zugänglich. Dieser Service nutzt Technologien für die verteilte Speicherung, die vom IBM Cloud Object Storage-Service bereitgestellt werden.

IBM COS ist in zwei Konfigurationen verfügbar: **Überregional** und **Regional**. Der überregionale Service (Cross Region) bietet größere Dauerhaftigkeit und Verfügbarkeit als die Verwendung einer einzigen Region, jedoch auf Kosten einer etwas höheren Latenz. Dieser Service ist derzeit in den USA und in der EU verfügbar. Der regionale Service bietet die umgekehrte Funktionalität, d. h. Objekte werden auf mehrere Verfügbarkeitszonen innerhalb einer Region verteilt. Wenn eine Region oder Verfügbarkeitszone nicht zugänglich ist, kann der Objektspeicher ohne Unterbrechung weiter genutzt werden. Alle fehlenden Änderungen werden angewendet, sobald das nicht zugängliche Rechenzentrum wieder online ist.

## Was ist IBM Cloud Direct Link?

IBM Cloud Direct Link ist eine Produktsuite, mit der Kunden private Verbindungen zwischen ihren fernen Netzumgebungen und ihren IBM Cloud-Bereitstellungen herstellen können. 

## Cloud Object Storage (COS) über IBM Cloud Direct Link verwenden

Die IBM Cloud Direct Link-Produktfamilie für Konnektivitätslösungen ist ein IaaS-Angebot, das private WAN-Konnektivität zu Ihren IaaS-Services ermöglichen soll. Die meisten IBM Cloud PaaS- und -SaaS-Lösungen bauen auf Ihr IaaS auf. Daher können Sie diese Verbindungstypen über die IBM Cloud aufrufen.

Die drei folgenden Methoden können Verbindungen zu IBM Cloud PaaS und SaaS über IBM Cloud Direct Link unterstützen. Derzeit wird die Methode 3 empfohlen, die am gründlichsten getestet wurde.

## Drei Methoden für PaaS- und SaaS-Verbindungen über Direct Link


### Methode 1: Verwendung einer virtuellen Routereinheit (Virtual Router Appliance, VRA; auch als Vyatta bezeichnet) als “Hop in den öffentlichen Bereich”
 
![vyatta-flow.png](images/vyatta-flow.png)



**Grundvoraussetzung: Verwendung von IBM COS mit einem "öffentlichen Hop" als Verbindung zu den Speicherendpunkten**
*Bei diesem "öffentlichen Hop" wird das IBM Cloud IaaS-Backbone nicht verlassen.*

* Der Kunde wählt mit Unterstützung durch IBM COS-Support- und -Onboarding-Teams einen öffentlichen Endpunkt aus und erhält einen API-Schlüssel.
* Auf dem eigenen lokalen Router fügt der Kunde Routen zu bestimmten Teilnetzen hinzu, um den reibungslosen Datenfluss über IBM Cloud Direct Link sicherzustellen.
* In der eigenen VRA erstellt der Kunde eine Route, um das öffentliche Netz zu durchqueren und den öffentlichen Endpunkt für IBM COS-Services zu erreichen.
* Der Kunde muss ein HA-Paar mit VRA-Hardware (@x) bereitstellen.
* Jedes VRA-Member erhält eine inklusive Bandbreite von 20 TB im Monat als Ausgleich für die Kosten der Public Cloud-Messung und -Abrechnung.
* Verwenden Sie den Bandbreitenzusammenschluss für Ihre gehosteten Server, um vorausbezahlte Bandbreite zu kumulieren.


### Methode 2: Cloud-Server-Durchgriff (privat zu privat)

![reverse=proxy](images/reverse-proxy.png)

**Grundvoraussetzung: Trust Cloud-Server mit COS-Berechtigungsnachweisen**

 * Der Kunde stellt mindestens einen Server (VSI oder Bare Metal) in IBM Cloud bereit.
 * Jeder Server hostet eine webbasierte oder auf Scripts basierende Anwendung (Java, Python, PHP etc.), die nur über die eigene private Schnittstelle für Verbindungen und Anforderungen empfangsbereit ist.
 * Die Server-App verwendet eine eigene API oder imitiert S3 ganz oder teilweise.
 * Private IBM Cloud-Serverschnittstellen sind recht sicher. Trennen Sie den Zugriff im privaten Netz mithilfe von VLANs, Sicherheitsgruppen, Betriebssystemfirewall oder VRA.
 * Maßnahmen zur Überprüfung des Anrufers und zur Begrenzung der API-Reichweite sind empfehlenswert.
 * Clients im lokalen Netz des Kunden verwenden die privaten IP-Adressen des Durchgriffsservers als Ziele für Anforderungen.
 * Client-Routing und DNS-Änderungen sind erforderlich.
 * Die auf dem Server gehostete Anwendung verarbeitet jede Anforderung, indem ein authentifizierter API-Aufruf an einen privaten COS-Endpunkt abgesetzt und die Antwort an den Anrufer zurückgegeben wird.

### Methode 3: Reverse Proxy (privat zu privat)

Diese Methode wird aktuell empfohlen.

**Grundvoraussetzung: Lokale Client-Aufrufer mit COS-Berechtigungsnachweisen werden anerkannt**

 

 * Als angepasste Variante der Methode 2 werden keine Web-Apps auf Cloud-Servern gehostet, sondern HTTPS-Server (z. B. NGINX), die für den Reverse Proxy konfiguriert sind.
 * Jeder Server ist mit einem selbst ausgegebenen Zertifikat über HTTPS empfangsbereit und leitet Anforderungen direkt an private COS-Endpunkte weiter, die in dem unten beschriebenen Dokument angegeben sind:
 
 ![COS Endpoints](https://console.bluemix.net/docs/services/cloud-object-storage/basics/endpoints.html)
 
### Beispiel für die Vorgehensweise zum Verbessern der Zuverlässigkeit und der Leistung Ihrer Cloud (nicht COS-spezisch):`serverfault.com`

 * Zur Optimierung der Skalierung und Ausfallsicherheit können mehrere Proxy-Server bereitgestellt werden. 
 * Durch Umlauf-DNS auf der Clientseite können einfache Funktionen für Ausweichbetrieb und Lastausgleich bereitgestellt werden.
 * Proxy-Server können hinter einer VRA platziert werden, um Sicherheit und zentrale Protokollierung bereitzustellen.
 
 ## IBM Cloud-Funktionalität verwalten und bereitstellen 
 
Dieser Abschnitt enthält Quick Links zur Dokumentation für manche IBM Cloud PaaS- und -SaaS-Angebote die über IBM Cloud Direct Link verbunden werden können.

## Vorgehensweise zur Bereitstellung von Bare-Metal-Servern

Ausführliche Anweisungen zur Vorgehensweise beim Bereitstellen von Bare-Metal-Servern finden Sie in [diesem Dokument](https://console.bluemix.net/docs/bare-metal/about.html#getting-started-with-bare-metal-servers).

## Vorgehensweise zum Bereitstellen einer Virtual Router Appliance (VRA)

Ausführliche Anweisungen zur Vorgehensweise beim Bereitstellen einer VRA finden Sie in [diesem Dokument](https://console.bluemix.net/docs/infrastructure/virtual-router-appliance/getting-started.html#getting-started).

## Vorgehensweise zum Bereitstellen von IBM Cloud Object Storage (COS)

 * Ausführliche Anweisungen zur Vorgehensweise beim Bereitstellen von COS finden Sie in [diesem Dokument](https://console.bluemix.net/catalog/services/cloud-object-storage).
 
 * Verwenden Sie einen der (zuvor aufgelisteten) privaten Endpunkte als Schnittstelle zu Ihrem Bucket oder Objekt in Ihrem bereitgestellten COS-Konto.
