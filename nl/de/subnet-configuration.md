---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-30"

keywords: direct link, configure, connectivity, BGP, VRF, configuration, RFC1918, ASN, BYOIP, NAT, VLAN Spanning, 10.0.0.0/8, ECMP, redundancy, IP assignments, VMWare, Vyatta, IP limitations

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:note: .note}
{:download: .download}

# IBM Cloud Direct Link konfigurieren
{: #configure-ibm-cloud-direct-link}

Nachdem die {{site.data.keyword.cloud}} Direct Link-Konnektivität hergestellt wurde, können Sie den Schritten in diesem Dokument folgen, um Ihr Teilnetz für die Interaktion mit {{site.data.keyword.cloud_notm}} zu konfigurieren.

Im Allgemeinen müssen Sie, um Ihre {{site.data.keyword.cloud_notm}} Direct Link-Verbindung zu aktivieren, einige Schritte zur grundlegenden Netzkonfiguration durchführen. Anschließend muss ein Border Gateway Protocol (BGP) eingerichtet werden. Während des Einrichtungsprozesses wird ein IBM Servicetechniker Sie dabei unterstützen, Ihr Netz für die Verwendung der obligatorischen VRF-Funktion (VRF, Virtual Routing Function) zu unterstützen.

## Grundlegende Netzkonfiguration
{: #basic-network-configuration}

1. Definieren Sie Ihr fernes Netz mithilfe des in RFC1918 festgelegten privaten Standardadressraums. 
 * Bei neuen Umgebungen wird empfohlen, **NICHT** den Adressraum 10.0.0.0/8 zu verwenden. 
 * Bei vorhandenen Umgebungen, die 10.0.0.0/8 verwenden, sollten Sie eine genauere Beurteilung durchführen, um sicherzustellen, dass es keine Konflikte mit dem {{site.data.keyword.cloud_notm}}-Servicenetz oder den Netzen gibt, die Ihrem Konto bereits zugewiesen sind.

2. Unsere Mitarbeiter bei {{site.data.keyword.cloud_notm}} weisen entweder /31 oder /30 für jede Verbindung zu und konfigurieren eine Schnittstellen-IP-Adresse für die XCR-Infrastruktur von {{site.data.keyword.cloud_notm}}.  

3. Konfigurieren Sie die Schnittstelle auf dem Edge-Router des Kunden (CER, Customer Edge Router) und verwenden Sie dabei die von uns bereitgestellte IP-Adresse: Nutzen Sie die XCR-IP von {{site.data.keyword.cloud_notm}} ganz einfach als nächste Station für den an {{site.data.keyword.cloud_notm}} gerichteten Datenverkehr. 

4. Bei zurückfließendem Datenverkehr verwendet {{site.data.keyword.cloud_notm}} die zugewiesene CER-IP als nächste Station für den gesamten Datenverkehr, der für das ferne Netz bestimmt ist, wie über BGP angegeben.

## BGP konfigurieren
{: #configuring-bgp}

Zum Austausch von Routeninformationen mit Ihrer Umgebung muss für {{site.data.keyword.cloud_notm}} BGP konfiguriert sein.  

1. **ASN**: {{site.data.keyword.cloud_notm}} weist ein privates ASN für die einzelnen Kunden zu. Alternativ können Sie Ihr eigenes öffentliches ASN verwenden. Ihre bevorzugte Methode müssen Sie zum Zeitpunkt Ihrer Bestellung angeben. Das Ihnen zugewiesene private ASN wird Ihnen im Rahmen des Implementierungsprozesses bereitgestellt.

2. **VRF**: Bei der Verwendung von VRF macht {{site.data.keyword.cloud_notm}} die Ihrem Kundenkonto zugewiesenen privaten Teilnetze zugänglich. Sie müssen die fernen Netze zugänglich machen, die über das private {{site.data.keyword.cloud_notm}}-Netz erreichbar sein sollen. Es liegt in Ihrer Verantwortung als Kunde, die Werbung rund um das IBM Cloud-Netz zu verwalten. (Weitere Informationen zu VRF finden Sie im nächsten Abschnitt.)

Die folgenden Netze werden herausgefiltert und können nicht akzeptiert werden: 0.0.0.0, 10.0.0.0/14, 10.198.0.0/15, 10.200.0.0/14, 169.254.0.0/16, 224.0.0.0/4.
{:note}

3. **ECMP**: Für Kunden, die eine Redundanz an einem unterstützten Standort schaffen möchten, unterstützt {{site.data.keyword.cloud_notm}} die Implementierung von Equal Cost Multipath (ECMP), um Lastausgleich und Redundanz über beide Verbindungen hinweg bereitzustellen. Diese ECMP-Konfiguration sollte zum Zeitpunkt der Bestellung angefordert werden.

## BGP-Spezifikationen für IBM Cloud Direct Link
{: #bgp-specifications-for-ibm-cloud-direct-link}

Die BGP-Spezifikationen lauten wie folgt:

Wie im vorherigen Abschnitt angegeben, ist BGP für die Verwaltung Ihrer Routenwahl über Direct Link obligatorisch. Ein Konto, über das Direct Link bestellt wird, wird in die VRF-Umgebung migriert.

**Einschränkungen für VLANs und VRF:**
 * Kontoübergreifendes VLAN-Spanning ist in der VRF-Umgebung nicht zulässig 
 * Der IPSEC-VPN-Service ist eingeschränkt 
 
VRF verhindert nicht den SSL- oder PPTP-VPN-Zugriff, aber das Verhalten ändert sich. Ohne VRF reicht eine einzige VPN-Verbindung aus, um alle Server in Ihrem Konto anzuzeigen. Mit VRF können Sie nur auf Ressourcen in dem Markt zugreifen, der Ihrem VPN zugeordnet ist. Beispiel: Wenn Sie die Verbindung zum DAL-VPN herstellen, sind nur Verbindungen zu DAL-Servern möglich.
{: note}

Die IBM Cloud-ASN-Nummer für öffentliche und private Services ist **13884**. 
 * Die Standard-ASN-Nummer für Bestellungen ist **64999**. Diese Standardeinstellung kann auf Kundenanfrage geändert werden. 
 * Optional kann eine 4 Byte umfassende, private ASN-Nummer von 4201000000 bis 4201064511 unterstützt werden.
 * Wenn Sie Direct Link Connect mit einem Layer-3-Service wie IP VPN verwenden, wird BGP von IBM Cloud mit dem ASN des Direct Link Connect-Providers eingerichtet.

**Empfehlungen, Standardwerte und Einschränkungen:**

 * Die Tunnelung (GRE) wird unterstützt und empfohlen, wenn IP-Überschneidungen ein Problem darstellen.
 * Die Standardeinstellungen für den BGP-Zeitgeber sind `Keepalive:30` und `Holdtime:60.`
 * Die Authentifizierung ist nicht standardmäßig aktiviert.
 * BGP BFD ist nicht standardmäßig aktiviert.
 * Der maximale Präfixgrenzwert für den Empfang (vom Kunden oder vom Provider) ist 200 pro VRF.
 
## Strikte Einschränkungen für IP-Zuordnungen
{: #strict-limitations-on-ip-assignments}

 * Bei Verwendung des 10.x.x.x-Netzes dürfen weiterhin keine Überschneidungen mit Ihren Hosts in IBM Cloud und mit dem IBM Cloud-Servicenetz auftreten, das `10.0.0.0/14`, `10.198.0.0/15` und `10.200.0.0/14` umfasst.  

 * Die folgenden Bereiche sind im US-System nicht zulässig und werden von IBM Servern abgelehnt: `169.254.0.0/16`, `224.0.0.0/4`.

## Redundanz und Diversität
{: #redundancy-and-diversity}

{{site.data.keyword.cloud_notm}} Direct Link bietet Diversität. Die Kunden sind für die Bereitstellung von Redundanz über ihre BGP-Schemas verantwortlich.

Wenn Sie ECMP zwecks Redundanz auswählen, müssen beide BGP-Sitzungen auf demselben Router für Querverbindungen (XCR) vorhanden sein. Sie geben also die Diversität des Routers auf und sind bei Fehlern des Routers einem Risiko ausgesetzt. Sie gewinnen Layer-3-Redundanz, verlieren jedoch Router-Diversität.

## Weitere Informationen zur Verwendung von VRF
{: #more-about-using-vrf}

Alle Konten, die eine {{site.data.keyword.cloud_notm}} Direct Link-Lösung nutzen, müssen auf eine VRF-Instanz migrieren. Durch die Verwendung von VRF machen Kunden die verfügbaren Routen in den eigens definierten Netzen zugänglich. Beachten Sie, dass es im Rahmen dieser Konfiguration nicht möglich ist, selbstdefinierte IP-Adressen für das {{site.data.keyword.cloud_notm}}-Netz zu verwenden.

Die Migration auf eine VRF-Instanz wird während der Installation durchgeführt. Dazu wird ein kurzes Ausfallfenster (bis zu 30 Minuten bei großen Konten mit mehreren VLANs/Standorten) benötigt. Während dieses Zeitfensters gehen während der Verschiebung in die VRF-Instanz die Verbindungen zwischen den Back-End-VLANs verloren. Die VRF-Migration wird mit dem Entwickler geplant, der für die Implementierung verantwortlich ist.

Beachten Sie, dass bei der Verwendung von VRF die Option für das VLAN-Spanning nicht verwendet werden kann, einschließlich aller VLAN-Spanning-Funktionen zwischen Konten, da alle VLANs miteinander kommunizieren können, es sei denn, für die Verwaltung des Datenverkehrs wird eine Gateway-Appliance eingeführt. Mit VRF können zudem VPN-Services von {{site.data.keyword.cloud_notm}} nur eingeschränkt genutzt werden, da die Funktion nicht mit den SSL-, PPTP- und IPSec VPN-Services von {{site.data.keyword.cloud_notm}} kompatibel ist.   

Eine Alternative ist die Verwendung des IBM Cloud Direct Link-Angebots selbst zur Verwaltung Ihrer Server oder die Ausführung einer eigenen VPN-Lösung (z. B. Vyatta), die mit unterschiedlichen VPN-Typen konfiguriert werden kann. Nach der Migration auf eine VRF-Instanz kann SSL VPN für gewöhnlich verwendet werden, wenn eine VPN-Verbindung zu dem Rechenzentrumsstandort hergestellt wird, an dem eine Compute-VM ausgeführt wird. Ein globaler Zugriff ist hierbei allerdings nicht zulässig.

## BYOIP und NAT mit Direct Link verwenden
{: #using-byoip-and-nat-with-direct-link}

IBM Cloud Direct Link umfasst nicht BYOIP für das private Netz. Datenverkehr mit einer Ziel-IP-Adresse, die nicht durch {{site.data.keyword.cloud_notm}} zugewiesen wurde, wird daher gelöscht. Kunden können jedoch den Datenverkehr zwischen dem fernen Netz und ihrem {{site.data.keyword.cloud_notm}}-Netz mithilfe von GRE, IPSec (Internet Protocol Security) oder VXLAN einkapseln.  

Am häufigsten wird die BYOIP-Umgebung im Rahmen eines Netzgateways (Vyatta) oder einer VMWare-NSX-Bereitstellung implementiert. Mit dieser Konfiguration können Kunden {{site.data.keyword.cloud_notm}}-seitig und für die Rückleitung über den Tunnel zurück zum fernen Netz einen beliebigen IP-Bereich verwenden. Beachten Sie, dass diese Konfiguration unabhängig von {{site.data.keyword.cloud_notm}} vom Kunden verwaltet und unterstützt werden muss. Außerdem kann es im Rahmen dieser Konfiguration zu einer Unterbrechung der Verbindung zum {{site.data.keyword.cloud_notm}}-Servicenetz kommen, wenn der Kunde einen 10.x.x.x-Block zuweist, der von {{site.data.keyword.cloud_notm}} für Services verwendet wird. 

Diese Lösung erfordert auch, dass jedem Host, der Konnektivität zum {{site.data.keyword.cloud_notm}}-Servicenetz und zum fernen Netz benötigt, 2 IP-Adressen zugewiesen sind: Eine muss über den IBM 10.x.x.x-Block und eine über den Block des fernen Netzes zugewiesen sein. Statische Routen müssen auf dem Host eingerichtet werden, um sicherzustellen, dass der Datenverkehr entsprechend weitergeleitet wird. Sie können einen IP-Bereich nicht direkt für die {{site.data.keyword.cloud_notm}}-Hosts (BYOIP) zuweisen und diesen inhärent im {{site.data.keyword.cloud_notm}} weiterleiten. Die einzige Möglichkeit, dies zu implementieren, wurde bereits an anderer Stelle erläutert, wird jedoch nicht von {{site.data.keyword.cloud_notm}} unterstützt.

Alternativ weisen Kunden häufig einen fernen Netzblock für die Verwendung in einer NAT-Tabelle zu, die auf ihrem fernen Edge-Router konfiguriert ist. Mit dieser Konfiguration können Kunden die an beiden Netzen erforderlichen Änderungen beschränken, während Datenverkehr weiterhin in einen Netzadressraum verschoben wird, der mit beiden Netzen kompatibel ist.
