---

copyright:
  years: 2018
lastupdated: "2018-06-11"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Fragebogen für IBM Cloud Direct Link Connect

Danke für Ihre Anforderung von IBM Cloud Direct Link Connect. Für die Bearbeitung Ihrer Anforderung benötigen wir weitere Informationen von Ihnen. Beim Ausfüllen des Fragebogens können Sie jederzeit direkt mit einem Entwickler in Kontakt treten. Der von Ihnen ausgefüllte Fragebogen wird von unserem Entwicklungsteam für Cloud Design überprüft und zur Implementierung an die Abteilung für Network Engineering weitergeleitet.

## Stimmen Sie den folgenden Hinweisen zu?

1. Für jede Direct Link-Verbindung ist eine dedizierte Bestellung erforderlich. Wenn Sie mehrere Verbindungen benötigen, öffnen Sie für jede Verbindung eine separate Direct Link-Bestellung.

2. Die Gebühren für Ihren Direct Link Connect-Service beinhalten die Kosten für die Beendigung des Service in der IBM Cloud-Infrastruktur. 

 * Infrastrukturservices werden im voraus abgerechnet, beginnend mit der Annahme Ihrer Bestellung. Aufgrund der Produktgestaltung von IBM Cloud Direct Link beginnt die Abrechnung für den Direct Link-Service ab der Einrichtung einer BGP-Sitzung (BGP = Border Gateway Protocol) mit IBM Cloud oder 30 Tage nach der Bereitstellung des Serviceschlüssels für den Kunden. 

 * Wann endet die Abrechnung?
   * Nachdem ein Kunde das Löschen einer Verbindung angefordert **und** 
   * der Connect-Provider oder Netzserviceprovider die Bereitstellung der Verbindung zurückgenommen hat.
  * Weitere Informationen finden Sie in **Abschnitt 5 - Gebühren** in der Cloud Services-Vereinbarung über den folgenden Link: [ibm.biz/service-agreement](ibm.biz/service-agreement).
  * Alternativ kann die Rechnungsstellung für einen Kunden beendet werden, nachdem der Kunde davon in Kenntnis gesetzt wurde, dass der bestehende Direct Link-Service abgeschaltet wird und danach nicht mehr betriebsbereit ist.

3. Nach der Bestellung des Direct Link-Service ist der Kunde für alle Gebühren verantwortlich, die für das Erreichen des Bereitstellungspunkts über das ferne Netz des Kunden anfallen, sowie für alle erforderlichen Querverbindungen zum Erreichen des Exchange-Providers. Sie (oder Ihr Provider) sind außerdem verantwortlich für den Erwerb der virtuellen Verbindung zu IBM Cloud. Wenn Ihr Provider die physische Präsenz eines Routers oder eines anderen Geräts am Bereitstellungspunkt erfordert, sind Sie außerdem für die Kosten der Zusammenstellung dieser Ausrüstung verantwortlich. Bestätigen Sie bitte, dass Ihr Netzprovider oder der Provider des Bereitstellungspunkts die Direct Link Connect-Verbindung erreichen und die zugehörigen Kosten berechnen kann.

4. IBM Cloud stellt keine Kundengeräte an seinen Netzbereitstellungspunkten zusammen. Ermitteln Sie in Zusammenarbeit mit Ihrem Provider, ob Sie Geräte in derselben Einrichtung zusammenstellen müssen, in der sich der IBM Cloud-Bereitstellungspunkt befindet.

5. Der Direct Link Exchange-Service wird so bereitgestellt, dass sowohl Ihr Link als auch der IBM Cloud-Router, die als Endpunkte für den Service dienen können, jeweils ein Single Point of Failure (SPOF) sind. Wenn Sie Redundanz über den Direct Link Connect-Service bereitstellen möchten, müssen die Links an zwei IBM Cloud-Netzbereitstellungspunkten enden, oder Sie müssen zwei Verbindungen zu einem Direct Link Connect-Standort mit einem sekundären Router bestellen.

6. Das IBM Cloud-Servicenetz ist über Ihre fernen Netze nicht direkt zugänglich. Über künftige Änderungen werden Sie zu gegebener Zeit benachrichtigt.

7. IBM Cloud ermöglicht den Kunden keine Rückübertragung des Datenverkehrs zwischen ihren fernen Standorten über das IBM Cloud-Backbone. Das Produkt 'Direct Link Connect' soll Ihren fernen Netzen die private Kommunikation mit Ihrer IBM Cloud-Infrastruktur ermöglichen.

8. Nachdem Sie überprüft haben, dass Ihre Verbindung den Direct Link Connect-Bereitstellungspunkt erreichen kann, müssen Sie bei Ihrem Connect-Provider eine Bestellung einreichen und dabei alle relevanten Informationen für den Cloud Exchange-Provider und für IBM Cloud bereitstellen. Die Bereitstellung durch Equinix-Provider kann mehrere Stunden dauern. Die typische Bereitstellungszeit für das Angebot 'IBM Cloud Direct Link Connect' beträgt 5 bis 10 Tage. 

9. Für IBM Cloud Direct Link Connect ist die Verwendung einer VRF-Instanz (VRF = Virtual Routing and Forwarding) auf der IBM Cloud Network-Seite erforderlich. Dies ermöglicht dem Kunden das Definieren von eigenen fernen IP-Adressen für die Verwendung im eigenen fernen Netz. Beachten Sie jedoch, dass auch bei Verwendung des 10.x.x.x-Netzes keine Überschneidungen mit den Hosts in IBM Cloud oder mit dem IBM Cloud-Servicenetz (10.0.0.0/14, 10.198.0.0/15 und 10.200.0.0/14) auftreten dürfen. Für den Übergang von Ihrem Konto auf eine VRF ist eine kurze Betriebsunterbrechung des privaten Netzes erforderlich, während jedes VLAN auf die neue Konfiguration migriert wird. Das Network Engineering-Team legt in Absprache mit Ihnen ein geeignetes Zeitfenster für diesen Vorgang fest.

10. VRF ist nicht kompatibel mit SSL-, PPTP- und IPSEC-VPN-Services von IBM Cloud. Eine Alternative ist die Verwendung eines direkten Links zum Verwalten Ihrer Server oder die Ausführung einer eigenen VPN-Lösung (z. B. Vyatta), die mit unterschiedlichen VPN-Typen konfiguriert werden kann. Nach der Migration auf eine VRF-Instanz kann SSL VPN in der Regel genutzt werden, wenn eine VPN-Verbindung zu dem Rechenzentrumsstandort hergestellt wird, an dem eine Compute-VM ausgeführt wird. Der globale Zugriff ist hierbei jedoch nicht zulässig.

11. IBM Cloud Direct Link Connect erfordert BGP zum Implementieren der Routen zum fernen Netz eines Kunden. Nach dem Implementieren Ihres Direct Link-Service macht IBM Cloud alle privaten Teilnetze zugänglich, die Ihrem Konto zugeordnet sind. IBM Cloud implementiert keine angepassten Filter als Pfadpräfix und als lokale Vorgaben für Mitteilungen an den fernen BGP-Peer des Kunden. IBM Cloud implementiert keine Filter für die von IBM Cloud empfangenen Mitteilungen. Die Kunden müssen die Mitteilungen für/von IBM Cloud über den Edge-Router des Kunden ordnungsgemäß verwalten. 

## Weitere Fragen

* **Stimmen Sie der Preisgestaltung an _IHREM STANDORT_ für die IBM Cloud Direct Link Connect-Verbindung zu?**

* **IBM Cloud weist Ihnen ein privates ASN zu, um BGP für das Zugänglichmachen Ihrer fernen Netze in Ihrem privaten IBM Cloud-Netz zu konfigurieren. Sind Sie damit einverstanden, oder möchten Sie lieber Ihr eigenes öffentliches ASN verwenden?**

* **Soll BGP MultiPath mit ECMP für das Einrichten einer redundanten Verbindung zu IBM Cloud konfiguriert werden?**  

    _Wenn dies zutrifft, geben Sie die Ticket-ID für die andere Verbindung an. Ticketnummer ____________  (beachten Sie, dass ECMP nur in zwei Sitzungen auf demselben IBM Cloud-XCR-Router bereitgestellt werden kann. Wenn Sie ECMP benötigen, ist zu beachten, dass beide Direct Link-Verbindungen zum selben Router führen müssen.) 

* **Benötigen Sie Local Routing- oder Global Routing-Zugriff?**

    _Kunden, die sich für Local Routing entscheiden, können nur Datenverkehr zwischen den Rechenzentren übertragen, die über den Bereitstellungspunkt angebunden sind, für den Direct Link bestellt wurde. Wenn Datenverkehr außerhalb des Bereitstellungspunkts weitergeleitet werden soll, für den Direct Link bestellt wurde, müssen die betreffenden Kunden die Option für Global Routing hinzufügen._

* **Sind Sie mit der Gebühr Global Routing sowie mit der monatlichen Gebühr für _IHREN STANDORT_ und mit den unten beschriebenen Überschreitungsgebühren einverstanden?**

    _Local Routing schließt den Zugriff auf alle Rechenzentren ein, die direkt mit dem Bereitstellungspunkt verbunden sind, sowie unbegrenzten eingehenden und ausgehenden Datenverkehr. Global Routing erweitert den Zugriff auf alle IBM Cloud-Rechenzentren weltweit. Die Bandbreite wird gemessen, wenn der Service die Bandbreitenmessung für den Datenverkehr unterstützt. Wenn die Bandbreitenmessung angewendet wird, erfolgt die Abrechnung monatlich gemäß dem für Sie geltenden Marktpreis, wie in der folgenden Tabelle angegeben._


### Preise für Global Routing

|Global Routing (eingehend) |Global Routing (ausgehend) |
|---|---|
|Kostenlos | Verbindung mit 1, 2 oder 5 Gb/s; 10 TB Bandbreite kostenlos |
|Kostenlos | Verbindung mit 10 Gb/s; 50 TB Bandbreite kostenlos |


|Gebühren bei Überschreitung der Bandbreite |
|---|
| Markt 1: 0,05 USD pro GB |
| Markt 2: 0,10 USD pro GB |
| Markt 3: 0,15 USD pro GB |
