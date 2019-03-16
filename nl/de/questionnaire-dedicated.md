---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-19"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Fragebogen für IBM Cloud Direct Link Dedicated
{: #ibm-cloud-direct-link-dedicated-questionnaire}

Vielen Dank für die {{site.data.keyword.cloud}} Direct Link Dedicated-Anforderung, die Sie geöffnet haben! Für die Bearbeitung Ihrer Anforderung benötigen wir weitere Informationen von Ihnen. Beim Ausfüllen des Fragebogens können Sie jederzeit direkt mit einem Entwickler in Kontakt treten. Der von Ihnen ausgefüllte Fragebogen wird von unserem Entwicklungsteam für Cloud Design überprüft und zur Implementierung an Special Network Services weitergeleitet.

## Stimmen Sie den folgenden Hinweisen zu?

1. Für jede Direct Link-Verbindung ist eine dedizierte Bestellung erforderlich. Wenn Sie mehrere Verbindungen benötigen, öffnen Sie für jede Verbindung eine separate Direct Link-Bestellung.

2. Die Gebühren für Ihren Direct Link Connect-Service beinhalten die Kosten für die Beendigung des Service in der IBM Cloud-Infrastruktur. 

 * Infrastrukturservices werden im voraus abgerechnet, beginnend mit der Annahme Ihrer Bestellung. Aufgrund der Produktgestaltung von IBM Cloud Direct Link beginnt die Abrechnung für den Direct Link-Service ab der Einrichtung einer BGP-Sitzung (BGP = Border Gateway Protocol) mit IBM Cloud oder 30 Tage nach der Bereitstellung des Serviceschlüssels für den Kunden. 

 * Wann endet die Abrechnung?
   * Nachdem ein Kunde das Löschen einer Verbindung angefordert **und** 
   * der Exchange-Provider oder Netzserviceprovider die Bereitstellung der Verbindung zurückgenommen hat.
  * Weitere Informationen finden Sie in **Abschnitt 5 - Gebühren** in der Cloud-Services-Vereinbarung unter dem folgenden Link: [https://www.ibm.com/support/customer/zz/en/selectcountrylang.html](https://www.ibm.com/support/customer/zz/en/selectcountrylang.html). Für Kunden in den Vereinigten Staaten wird beispielsweise [dieses Vertragsdokument für Cloud-Services](https://www.ibm.com/support/customer/csol/contractexplorer/cloud/csa/us-en) angezeigt. 

3. Nach der Bestellung des Direct Link-Service sind Sie für alle Gebühren verantwortlich, die für das Erreichen des Bereitstellungspunkts über Ihr fernes Netz anfallen, sowie für alle erforderlichen Querverbindungen innerhalb der Einrichtung am Bereitstellungspunkt. Wenn Ihr Provider die physische Präsenz eines Routers oder eines anderen Geräts am Bereitstellungspunkt erfordert, sind Sie außerdem für die Kosten der Zusammenstellung dieser Ausrüstung verantwortlich.

4. IBM Cloud bestellt keine Querverbindungen im Namen das Kunden.

5. IBM Cloud stellt keine Kundengeräte an unseren Netzbereitstellungspunkten zusammen. Wir akzeptieren nur 'Querverbindungen' in Form von Ethernet-Glasfaserkabeln (nur Einzelmodus-Glasfaser mit 1Gig-LX- oder 10Gig-LR 1310nm), die von Ihrem Gehäuse oder Provider ausgehen. Wir akzeptieren keine T1s-, DS3s-, ISDN- und POTs-Leitungen usw. Ermitteln Sie in Zusammenarbeit mit Ihrem Provider, ob Sie Geräte in derselben Einrichtung zusammenstellen müssen, in der sich der IBM Cloud-Netzbereitstellungspunkt befindet.

6. Der Direct Link-Service wird so bereitgestellt, dass sowohl Ihr Link als auch der IBM Cloud-Router (beide können als Endpunkt für den Service dienen), ein Single Point of Failure (SPOF) ist. Wenn Sie Redundanz über den Direct Link-Service bereitstellen möchten, müssen Sie entweder zwei Verbindungen zu einem Direct Link-Standort mit einem sekundären Router bestellen, oder die Links müssen an zwei separaten IBM Cloud-Bereitstellungspunkten enden.

7. Das IBM Cloud-Servicenetz ist über Ihre fernen Netze nicht direkt zugänglich. Über künftige Änderungen werden Sie zu gegebener Zeit von uns benachrichtigt.

8. IBM Cloud ermöglicht den Kunden keine Rückübertragung des Datenverkehrs zwischen ihren fernen Standorten über das IBM Cloud-Backbone. Das Produkt 'Direct Link' soll Ihren fernen Netzen die private Kommunikation mit Ihrer IBM Cloud-Infrastruktur ermöglichen.

9. Nachdem Sie überprüft haben, dass Ihre Verbindung den Bereitstellungspunkt erreicht und vom Netzbetreiber fertiggestellt wurde, müssen Sie die Querverbindung zum IBM Cloud XCR-Router bestellen, die in der Regel innerhalb von 2 bis 10 Werktagen bearbeitet wird. Dies schließt die Einrichtung des Patches für den SoftLayer-Abschlussport ein. Nach der Beendigung des Vorgangs müssen Sie den Fertigstellungshinweis des Providers der Querverbindung an IBM Cloud weiterleiten. Die IP-Zuordnung für die IBM Cloud-Netzinfrastruktur erfolgt innerhalb von 3 Werktagen nach erfolgreicher Einrichtung der Querverbindung.

10. IBM Cloud Direct Link Dedicated erfordert die Verwendung einer VRF-Instanz (VRF = Virtual Routing and Forwarding).Diese Funktion ermöglicht Kunden das Definieren von eigenen fernen IP-Adressen für die Verwendung im eigenen fernen Netz. Beachten Sie jedoch, dass auch bei Verwendung des 10.x.x.x-Netzes keine Überschneidungen mit Ihren Hosts in IBM Cloud oder mit dem IBM Cloud-Servicenetz (10.0.0.0/14, 10.198.0.0/15 und 10.200.0.0/14) auftreten dürfen. Für den Übergang von Ihrem Konto auf eine VRF ist eine kurze Betriebsunterbrechung des privaten Netzes erforderlich, während jedes VLAN auf die neue Konfiguration migriert wird.Das Specail Network Services-Team legt in Absprache mit Ihnen ein geeignetes Zeitfenster für diesen Vorgang fest. Das Special Network Services-Team steht von Montag bis Freitag von 8:00 bis 17:00 CST (Central Standard Time, USA) zur Verfügung. Aktivierungsaktivitäten außerhalb dieses Zeitfensters müssen anhand eines Tickets angefordert und vorab genehmigt werden, wenn Entwickler verfügbar sind.

11. VRF ist nicht kompatibel mit den SSL-, PPTP- und IPSEC-VPN-Services von IBM Cloud (früher SoftLayer). Eine Alternative ist die Verwendung eines direkten Links zum Verwalten Ihrer Server oder die Ausführung einer eigenen VPN-Lösung (z. B. Vyatta), die mit unterschiedlichen VPN-Typen konfiguriert werden kann. Nach der Migration auf eine VRF-Instanz kann SSL VPN in der Regel verwendet werden, wenn eine VPN-Verbindung zu dem Rechenzentrumsstandort hergestellt wird, an dem eine Compute-VM ausgeführt wird. Der globale Zugriff ist hierbei jedoch nicht zulässig.

12. IBM Cloud Direct Link Dedicated erfordert BGP zum Implementieren der Routen zum fernen Netz eines Kunden. Nach dem Implementieren Ihres Direct Link-Service macht IBM Cloud alle privaten Teilnetze zugänglich, die Ihrem Konto zugeordnet sind.IBM Cloud implementiert keine angepassten Filter als Pfadpräfix und als angepasste lokale Vorgaben für Mitteilungen an den fernen BGP-Peer des Kunden. IBM Cloud implementiert keine Filter für die von IBM Cloud empfangenen Mitteilungen. Die Kunden müssen die Mitteilungen für/von IBM Cloud über den Edge-Router des Kunden ordnungsgemäß verwalten. 

## Weitere Fragen

* **An welchem Bereitstellungspunkt soll die Direct Link-Verbindung enden?**

* **Welche Verbindungsgeschwindigkeit benötigen Sie (1, 2, 5 oder 10 Gb/s)?**

* **Soll BGP MultiPath mit ECMP für das Einrichten einer redundanten Verbindung zu IBM Cloud konfiguriert werden?**  

    _Wenn dies zutrifft, geben Sie die Ticket-ID für die andere Verbindung an. Ticketnummer ____________  (beachten Sie, dass ECMP nur in zwei Sitzungen auf demselben IBM Cloud-XCR-Router bereitgestellt werden kann.  Wenn Sie ECMP benötigen, ist zu beachten, dass beide Direct Link-Verbindungen zum selben Router führen müssen.)

* **Benötigen Sie Local Routing- oder Global Routing-Zugriff?**

    _Kunden, die sich für Local Routing entscheiden, können nur Datenverkehr zwischen den Rechenzentren übertragen, die über den Bereitstellungspunkt angebunden sind, für den Direct Link bestellt wurde. Wenn Datenverkehr außerhalb des Bereitstellungspunkts weitergeleitet werden soll, für den Direct Link bestellt wurde, müssen die betreffenden Kunden die Option für Global Routing hinzufügen._

* **Sind Sie mit der Gebühr für Global Routing sowie mit der monatlichen Gebühr für _IHREN STANDORT_ und mit den unten beschriebenen Überschreitungsgebühren einverstanden?**

    _Local Routing schließt den Zugriff auf alle Rechenzentren ein, die direkt mit dem Bereitstellungspunkt verbunden sind, sowie unbegrenzten eingehenden und ausgehenden Datenverkehr. Global Routing erweitert den Zugriff auf alle IBM Cloud-Rechenzentren weltweit. Die Bandbreite wird gemessen, wenn der Service die Bandbreitenmessung für den Datenverkehr unterstützt. Wenn die Bandbreitenmessung angewendet wird, erfolgt die Abrechnung monatlich gemäß dem für Sie geltenden Marktpreis, wie in der folgenden Tabelle angegeben._


### Preise für Global Routing

| Global Routing (eingehend) | Global Routing (ausgehend) |
|---|---|
| Kostenlos | Verbindung mit 1, 2 oder 5 Gb/s; 10 TB Bandbreite kostenlos |
| Kostenlos | Verbindung mit 10 Gb/s; 50 TB Bandbreite kostenlos |


| Gebühren bei Überschreitung der Bandbreite |
|---|
| Markt 1: 0,05 USD pro GB |
| Markt 2: 0,10 USD pro GB |
| Markt 3: 0,15 USD pro GB |
