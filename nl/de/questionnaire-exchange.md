---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-02"

keywords: Exchange, finalize, questionnaire, Special Network Services, billing, fees, VRF, BGP, ticket, ASN, VPN, metering, data, center, datacenter

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Fragebogen für IBM Cloud Direct Link Exchange
{: #ibm-cloud-direct-link-exchange-questionnaire}

Vielen Dank für die {{site.data.keyword.cloud}} Direct Link Exchange-Anforderung, die Sie geöffnet haben! Für die Bearbeitung Ihrer Anforderung benötigen wir weitere Informationen von Ihnen. Beim Ausfüllen des Fragebogens können Sie jederzeit direkt mit einem Entwickler in Kontakt treten. Der von Ihnen ausgefüllte Fragebogen wird von unserem Entwicklungsteam für Cloud Design überprüft und zur Implementierung an Special Network Services weitergeleitet.

## Stimmen Sie den folgenden Hinweisen zu?
{: #exchange-do-you-agree}

1. Für jede Direct Link-Verbindung ist eine dedizierte Bestellung erforderlich. Wenn Sie mehrere Verbindungen benötigen, öffnen Sie für jede Verbindung eine separate Direct Link-Bestellung.

2. Die Gebühren für Ihren Direct Link Exchange-Service beinhalten die Kosten für die Beendigung des Service in der IBM Cloud-Infrastruktur. 

 * Infrastrukturservices werden im voraus abgerechnet, beginnend mit der Annahme Ihrer Bestellung. Aufgrund der Produktgestaltung von IBM Cloud Direct Link beginnt die Abrechnung für den Direct Link-Service ab der Einrichtung einer BGP-Sitzung (BGP = Border Gateway Protocol) mit IBM Cloud oder 30 Tage nach der Bereitstellung des Serviceschlüssels für den Kunden. 

 * Wann endet die Abrechnung?
   * Nachdem ein Kunde das Löschen einer Verbindung angefordert **und** 
   * der Exchange-Provider oder Netzserviceprovider die Bereitstellung der Verbindung zurückgenommen hat.
  * Weitere Informationen finden Sie in **Abschnitt 5 - Gebühren** in der Cloud-Services-Vereinbarung unter dem folgenden Link: [https://www.ibm.com/support/customer/zz/en/selectcountrylang.html](https://www.ibm.com/support/customer/zz/en/selectcountrylang.html). Für Kunden in den Vereinigten Staaten wird beispielsweise [dieses Vertragsdokument für Cloud-Services](https://www.ibm.com/support/customer/csol/contractexplorer/cloud/csa/us-en) angezeigt.
  * Alternativ kann die Rechnungsstellung für einen Kunden beendet werden, nachdem der Kunde davon in Kenntnis gesetzt wurde, dass der bestehende Direct Link-Service abgeschaltet wird und danach nicht mehr betriebsbereit ist.

3. Nach der Bestellung des Direct Link-Service ist der Kunde für alle Gebühren verantwortlich, die für das Erreichen des Bereitstellungspunkts über das ferne Netz des Kunden anfallen, sowie für alle erforderlichen Querverbindungen zum Erreichen des Exchange-Providers. Sie (oder Ihr Provider) sind außerdem verantwortlich für den Erwerb der virtuellen Verbindung zu IBM Cloud. Wenn Ihr Provider die physische Präsenz eines Routers oder eines anderen Geräts am Bereitstellungspunkt erfordert, sind Sie außerdem für die Kosten der Zusammenstellung dieser Ausrüstung verantwortlich. Bestätigen Sie bitte, dass Ihr Netzprovider oder der Provider des Bereitstellungspunkts die Direct Link Exchange-Verbindung erreichen und die zugehörigen Kosten berechnen kann.

4. IBM Cloud stellt keine Kundengeräte an seinen Netzbereitstellungspunkten zusammen. Ermitteln Sie in Zusammenarbeit mit Ihrem Provider, ob Sie Geräte in derselben Einrichtung zusammenstellen müssen, in der sich der IBM Cloud-Bereitstellungspunkt befindet.

5. Der Direct Link Exchange-Service wird so bereitgestellt, dass sowohl Ihr Link als auch der IBM Cloud-Router, die als Endpunkte für den Service dienen können, jeweils ein Single Point of Failure (SPOF) ist. Wenn Sie die Redundanz über den Direct Link Exchange-Service bereitstellen möchten, müssen Links an zwei separaten IBM Cloud-Netzbereitstellungspunkten enden, oder Sie müssen zwei Verbindungen zu einem Direct Link Exchange-Standort mit einem sekundären Router bestellen.

6. Das IBM Cloud-Servicenetz ist über Ihre fernen Netze nicht direkt zugänglich. Über künftige Änderungen werden Sie zu gegebener Zeit benachrichtigt.

7. IBM Cloud ermöglicht den Kunden keine Rückübertragung des Datenverkehrs zwischen ihren fernen Standorten über das IBM Cloud-Backbone. Das Produkt 'Direct Link Exchange' soll Ihren fernen Netzen die private Kommunikation mit Ihrer IBM Cloud-Infrastruktur ermöglichen.

8. Nachdem Sie überprüft haben, dass Ihrer Verbindung den Direct Link Exchange-Bereitstellungspunkt erreichen kann, müssen Sie bei Ihrem Cloud Exchange-Provider eine Bestellung einreichen und dabei alle relevanten Informationen für den Cloud Exchange-Provider und für IBM Cloud bereitstellen. Die Bereitstellung durch Equinix-Provider kann mehrere Stunden dauern. Die typische Bereitstellungszeit für das Angebot 'IBM Cloud Direct Link Exchange' beträgt 5 bis 10 Tage. 

9. Für IBM Cloud Direct Link Exchange ist die Verwendung einer VRF-Instanz (VRF = Virtual Routing and Forwarding) auf der IBM Cloud Network-Seite erforderlich.  Dies ermöglicht dem Kunden das Definieren von eigenen fernen IP-Adressen für die Verwendung im eigenen fernen Netz. Beachten Sie jedoch, dass auch bei Verwendung des 10.x.x.x-Netzes keine Überschneidungen mit den Hosts in IBM Cloud oder mit dem IBM Cloud-Servicenetz (10.0.0.0/14, 10.198.0.0/15 und 10.200.0.0/14) auftreten dürfen. Für den Übergang von Ihrem Konto auf eine VRF ist eine kurze Betriebsunterbrechung des privaten Netzes erforderlich, während jedes VLAN auf die neue Konfiguration migriert wird.  Das Special Network Services-Team legt in Absprache mit Ihnen ein geeignetes Zeitfenster für diesen Vorgang fest. Das Special Network Services-Team steht normalerweise von Montag bis Freitag von 8:00 bis 17:00 CST (Central Standard Time, USA) zur Verfügung. Aktivierungsaktivitäten außerhalb dieses Zeitfensters müssen anhand eines Tickets angefordert und vorab genehmigt werden, falls Entwickler verfügbar sind. 

10. VRF ist nicht kompatibel mit SSL-, PPTP- und IPSEC-VPN-Services von IBM Cloud. Eine Alternative ist die Verwendung eines direkten Links zum Verwalten Ihrer Server oder die Ausführung einer eigenen VPN-Lösung (z. B. Vyatta), die mit unterschiedlichen VPN-Typen konfiguriert werden kann. Nach der Migration auf eine VRF-Instanz kann SSL VPN in der Regel verwendet werden, wenn eine VPN-Verbindung zu dem Rechenzentrumsstandort hergestellt wird, an dem eine Compute-VM ausgeführt wird. Der globale Zugriff ist hierbei jedoch nicht zulässig.

11. IBM Cloud Direct Link Exchange erfordert BGP zum Implementieren der Routen zum fernen Netz des Kunden.Nach dem Implementieren Ihres Direct Link-Service macht IBM Cloud alle privaten Teilnetze zugänglich, die Ihrem Konto zugeordnet sind.IBM Cloud implementiert keine angepassten Filter als Pfadpräfix und als lokale Vorgaben für Mitteilungen an den fernen BGP-Peer des Kunden. IBM Cloud implementiert keine Filter für die von IBM Cloud empfangenen Mitteilungen. Die Kunden müssen die Mitteilungen für/von IBM Cloud über den Edge-Router des Kunden ordnungsgemäß verwalten. 

## Weitere Fragen
{: #exchange-other-questions}

* **Stimmen Sie der Preisgestaltung an _IHREM STANDORT_ für die IBM Cloud Direct Link Exchange-Verbindung zu?**

* **IBM Cloud weist Ihnen ein privates ASN zu, um BGP für das Zugänglichmachen Ihrer fernen Netze in Ihrem privaten IBM Cloud-Netz zu konfigurieren. Sind Sie damit einverstanden, oder möchten Sie lieber Ihr eigenes öffentliches ASN verwenden?**

* **Soll BGP MultiPath mit ECMP für das Einrichten einer redundanten Verbindung zu IBM Cloud konfiguriert werden?**  

    _Wenn dies zutrifft, geben Sie die Ticket-ID für die andere Verbindung an. Ticketnummer ____________  (beachten Sie, dass ECMP nur in zwei Sitzungen auf demselben IBM Cloud-XCR-Router bereitgestellt werden kann.  Wenn Sie ECMP benötigen, ist zu beachten, dass beide Direct Link-Verbindungen zum selben Router führen müssen.)

* **Benötigen Sie Local Routing- oder Global Routing-Zugriff?**

    _Kunden, die sich für Local Routing entscheiden, können nur Datenverkehr zwischen den Rechenzentren übertragen, die über den Bereitstellungspunkt angebunden werden, für den Direct Link bestellt wurde. Wenn Datenverkehr außerhalb des Bereitstellungspunkts weitergeleitet werden soll, für den Direct Link bestellt wurde, müssen die betreffenden Kunden die Option für Global Routing hinzufügen._

* **Sind Sie mit der Gebühr für Global Routing sowie mit der monatlichen Gebühr für _IHREN STANDORT_ und mit den unten beschriebenen Überschreitungsgebühren einverstanden?**

    _Local Routing schließt den Zugriff auf alle Rechenzentren ein, die direkt mit dem Bereitstellungspunkt verbunden sind, sowie unbegrenzten eingehenden und ausgehenden Datenverkehr. Global Routing erweitert den Zugriff auf alle IBM Cloud-Rechenzentren weltweit. Die Bandbreite wird gemessen, wenn der Service die Bandbreitenmessung für den Datenverkehr unterstützt. Wenn die Bandbreitenmessung angewendet wird, erfolgt die Abrechnung monatlich gemäß dem für Sie geltenden Marktpreis, wie in der folgenden Tabelle angegeben._


### Preise für Global Routing
{: #exchange-global-routing-pricing}

| Global Routing (eingehend) | Global Routing (ausgehend) |
|---|---|
| Kostenlos | Verbindung mit 1, 2 oder 5 Gb/s; 10 TB Bandbreite kostenlos |
| Kostenlos | Verbindung mit 10 Gb/s; 50 TB Bandbreite kostenlos |


| Gebühren bei Überschreitung der Bandbreite |
|---|
| Markt 1: 0,05 USD pro GB |
| Markt 2: 0,10 USD pro GB |
| Markt 3: 0,15 USD pro GB |
