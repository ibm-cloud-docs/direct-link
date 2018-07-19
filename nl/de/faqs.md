---

copyright:
  years: 2017, 2018
lastupdated: "2018-05-11"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Häufig gestellte Fragen

Dieser Abschnitt enthält Antworten auf einige häufig gestellte Fragen zu IBM Cloud Direct Link. 

## Wie funktioniert IBM Cloud Direct Link?
Für jeden Direct Link-Kunden weist das IBM Cloud-Team ein kleines privates Teilnetz zu, um ein Punkt-zu-Punkt-Netz zwischen dem Router für Querverbindungen (XCR-Router) von {{site.data.keyword.BluSoftlayer_notm}} und dem Edge-Router (CER-Router) des Kunden herzustellen. Anschließend konfigurieren {{site.data.keyword.BluSoftlayer_notm}} und der Kunde BGP so, dass Routen zwischen den Umgebungen ausgetauscht werden können. Abschließend migriert {{site.data.keyword.BluSoftlayer_notm}} den Kunden in eine VRF-Instanz, um die Implementierung nicht eindeutiger Routen zum privaten Adressraum des fernen Kundennetzes zu ermöglichen.

## Misst IBM Cloud die Bandbreite für Direct Link-Produkte?
Ja. Die Bandbreitennutzung im Direct Link-Service zwischen Kunden und IBM Cloud ist kostenlos und unbegrenzt. IBM Cloud misst die abgehende Bandbreite von den IBM Cloud-Services in das öffentliche Internet.

## Wann beginnt die Abrechnung für Direct Link?
Die Gebühren für Direct Link Connect beinhalten die Kosten für die Beendigung des Service in der IBM Cloud-Infrastruktur. 

Infrastrukturservices werden im Voraus abgerechnet, beginnend mit der Annahme Ihrer Kundenbestellung. Aufgrund der Produktgestaltung von IBM Cloud Direct Link beginnt die Abrechnung für den Direct Link-Service ab der Einrichtung einer BGP-Sitzung (BGP = Border Gateway Protocol) mit IBM Cloud oder 30 Tage nach der Bereitstellung des Serviceschlüssels für den Kunden. 

Die Abrechnung endet, (1) wenn ein Kunde das Löschen einer Verbindung anfordert UND (2) der Connect-Provider oder Netzserviceprovider die Bereitstellung der Verbindung zurückgenommen hat.

## Welche zusätzlichen Gebühren können für mich von anderen Parteien im Zusammenhang mit Direct Link anfallen?
Es können zusätzliche Gebühren von Ihrem Austauschprovider oder Netzserviceprovider anfallen. Weitere Informationen zu diesen Gebühren erhalten Sie von Ihrem/Ihren Provider/n.

## Wie erreiche ich Redundanz mit IBM Cloud Direct Link?
Direct Link ist kein Service mit inhärenter Redundanz. Direct Link kann verschiedene Verbindungen herstellen, die es den Kunden ermöglichen mithilfe von BGP Redundanz bereitzustellen. Sie können mit Direct Link Diversität erreichen, indem Sie mehr als eine Verbindung zu einem IBM Cloud Direct Link Dedicated-Provider oder Exchange-Provider für {{site.data.keyword.BluSoftlayer_notm}} herstellen. Alternativ können Sie mit Exchange und Connect verschiedene NNIs über IBM Cloud Direct Link-Provider nutzen.

## Was ist der Unterschied zwischen dem standardmäßig verwendeten 'Local Routing' und dem Add-on 'Global Routing'?
Mit unserem Standardangebot für Direct Link können Daten zwischen den Rechenzentren in Ihrer ausgewählten Region ausgetauscht werden. Wenn Sie auf andere Rechenzentren außerhalb der angegebenen Region zugreifen müssen, müssen Sie das Add-on 'Global Routing' bestellen. Dieses Modell basiert auf Zugriffssteuerungslisten (ACLs, Access Control Lists), die zum Zeitpunkt der Bestellung Ihrer Direct Link-Verbindung eingerichtet werden. 

## Wie werden Überschreitungen bei der ausgehenden Bandbreite für das Add-on 'Global Routing' in Rechnung gestellt?
Überschreitungen werden monatlich in Rechnung gestellt, wenn Ihr Kontingent an Bandbreite überschritten wird. Dies gilt jedoch nur für die Bandbreite bei ausgehenden Verbindungen. Die eingehende Bandbreite ist kostenlos und unbegrenzt. Die ausgehende Bandbreite wird basierend auf der Rate in Rechnung gestellt, die in den beiden entsprechenden Regionen, durch die der Datenverkehr läuft, höher ist.  Wenn beispielsweise Direct Link in DAL03 konfiguriert ist und der Datenverkehr durch Mexiko läuft, wird Ihnen die Bandbreitenrate für Mexiko berechnet.

## Warum gibt es das Add-on-Paket 'Global Routing'?
Das Add-on 'Global Routing' wurde hinzugefügt, um zu verhindern, dass für Kunden unerwartete Kosten in Bezug auf ihre Daten entstehen, wenn der Datenverkehr außerhalb der Rechenzentren der entsprechenden Region läuft. Es hält die Kosten für die Mehrheit unserer Kunden gering und es bietet Kunden mit einer globalen Präsenz die Möglichkeit, alle Regionen weltweit einfach zu erreichen. Normalerweise benötigt ein Kunde jedoch nur ein Paket für lokale Bandbreite.

## Was sind die Optionen 'Local Routing' und 'Global Routing'?
Die Optionen 'Local Routing' und 'Global Routing' werden von jedem Kunden beim Bestellen des Direct Link-Service ausgewählt. Wenn Kunden ihren Datenverkehr außerhalb des Bereitstellungspunkts in dem Bereich verlagern möchten, in dem sie Direct Link bestellen, müssen sie die Option 'Global Routing' hinzufügen; andernfalls wird der Datenverkehr auf die Services beschränkt, die über den lokalen Bereitstellungspunkt verfügbar sind.

Die ersten 10 TB ausgehenden Datenverkehrs sind bei Direct Link-Verbindungen mit 1 Gb/s ohne gesonderte Berechnung enthalten; bei Verbindungen mit 10 Gb/s sind die ersten 50 TB ausgehenden Datenverkehrs ohne gesonderte Berechnung enthalten. Überschreitungen basieren auf der nachfolgenden Tabelle, wobei der höhere Marktpreis gilt. Wenn Sie 'Global Routing' auswählen, ist der gesamte eingehende Datenverkehr kostenlos. Es wird nur der Datenverkehr berechnet, der außerhalb des lokalen Bereitstellungspunkts fließt.

|Daten Markt 1|Daten Markt 2|Daten Markt 3|
|---|---|---|
|<ul><li>DAL</li><li>WDC</li><li>SEA</li><li>SJC</li><li>NYC*</li><li>CHI*</li><li>DEN*</li><li>MIA*</li><li>ATL*</li><li>LAX*</li><li>TOR</li><li>MON</li><li>AMS</li><li>FRA</li></ul>|<ul><li>TOK</li><li>HKG</li><li>PAR</li><li>MIL</li><li>STK*</li><li>OSL</li><li>SNG</li></ul>|<ul><li>MEX</li><li>SAO</li><li>SYD</li><li>MEL</li><li>PER*</li><li>CHE</li><li>SEO</li></ul>|
**Tabelle 1: Nutzungsstufen**<br/>
Direct Link-Angebote in den mit einem Stern (*) gekennzeichneten Märkten MÜSSEN 'Global Routing' bestellen.

## Wenn ich die Angebote 'Direct Link Dedicated', 'Direct Link Connect' oder 'Direct Link Exchange' in einer Region wie Dallas verwende, habe ich dann Zugriff auf andere Regionen in den USA über Direct Link?
Ja. Wenn Sie das Add-on 'Global Routing' auswählen, haben Sie Zugriff auf Bereiche außerhalb Ihrer Region. Wenn diese Option nicht ausgewählt ist, wird der Direct Link-Datenverkehr auf die Region für den von Ihnen gewählten Bereitstellungspunkt begrenzt. Details finden Sie im [Preisdokument](pricing.html).

## Kann ich eine Verbindung zu jeder verfügbaren Region von einem angegebenen Direct Link-Standort herstellen?
Ja, solange Sie Direct Link mit dem Add-on 'Global Routing' bestellen.

## Kann ich die Regionen einzuschränken, die ich über Direct Link erreichen kann?
Nein IBM Cloud bietet zwei Optionen: (1) nur eine einzige Region oder (2) alle Regionen, mit dem Add-on 'Global Routing'.

## Was ist, wenn ich den automatisierten Bestellablauf für Equinix Cloud Exchange angewendet habe und mir ein Teilnetz zugewiesen wurde, das sich mit meinem internen Netz überschneidet?

Ab März 2018 ist das empfohlene bewährte Verfahren, Ihre automatisierte Bestellung abzubrechen und ein neues Ticket einzureichen, um den Direct Link-Fragebogen ausfüllen zu können. Darin sollten Sie angeben, ob Sie ein anderes Teilnetz im Bereich 10.254.x.x oder im Bereich 172.32.x.x bevorzugen.

## Was ist der Unterschied zwischen Direct Link Exchange und Direct Link Connect?

Diese zwei Services sind sich ähnlich, beide relativ kostengünstig, Latenz-tolerant und bieten schnelle Einstiegspunkte für die Vorteile von IBM Cloud Direct Link. Der wesentliche Unterschied ist, dass Exchange Rechenzentrenprovider nutzt, Connect hingegen Telco-Netzbetreiber. Hier einige zusätzliche Details:

**Direct Link Exchange** wird für Kunden empfohlen, die es vorziehen, einen Datenaustausch innerhalb eines Rechenzentrums zu nutzen. Bei einem Exchange-Service können Kunden schnell die Konnektivität mehrerer Clouds zu Ihrer Colocation aktivieren, da die zugrundeliegenden Verbindungen bereits bereitgestellt sind (diese anderen Cloud-Provider müssen bereits über physische Verbindungen innerhalb der Facility verfügen).

Direct Link Exchange kann eine gemeinsam genutzte Umgebung mit mehreren Clouds über einen einzigen Cloud Exchange-Port ermöglichen, der mittels einer NNI-Verbindung in Layer 2 zwischen IBM Cloud und Cloud Exchange Service Provider erstellt wird. Es sind Portgeschwindigkeiten bis zu 1 Gb verfügbar.

**Direct Link Connect** ist für Kunden gedacht, die es bevorzugen, ihr vorhandenes Netz zwischen ihrer lokalen Bereitstellung und IBM Cloud zu nutzen. Mit einem Direct Link Connect-Service können Kunden neue wie auch vorhandene Telco-Netze (wie z. B. MPLS) nutzen, mit denen IBM Cloud schnell aktiviert werden kann, indem sie im Voraus bereitgestellte zugrundeliegende Verbindungen nutzen.

Mit Direct Link Connect können Kunden Verbindungen zu IBM Cloud über den Connect-Provider durch eine NNI-Verbindung herstellen, die von IBM Partnern in Einrichtungen weltweit betrieben werden. Es sind Portgeschwindigkeiten bis zu 5 Gb verfügbar.

## Kann IPv6 über Direct Link unterstützt werden?

Nicht für die BGP-Sitzung. Wir müssen unser Präfix /30 aus IPv4 zuweisen, das auch vom Kunden zurückgegeben werden muss.

## Kann IPV6 im privaten Netz verwendet werden?

Nein. IPv6 ist ein öffentliches Protokoll.

## Gelten für Verizon SCI spezielle Anforderungen wie Präfix / ASN / VLAN BGP / usw.?

Verizon SCI ist einer von mehreren MPLS-basierten Layer-3-Services (IP VPN). Dieser Service erfordert, dass BGP von IBM mit Verizon eingerichtet wird anstatt direkt mit dem Kunden. Anschließend richtet Verizon mit dem Kunden BGP ein und macht entsprechende Routen zugänglich. Mehrere andere Provider für Layer-3-basierte Services nehmen am Direct Link Connect-Programm teil. Die Kunden sollten darauf achten, was sie bestellen und wie sich die Verbindung zu IBM Cloud auf Ihr Konto auswirkt.

## Bietet Direct Link Unterstützung für Servicequalitätstypen?

Wir können keine Gewährleistung für die Servicequalität bieten. Die Servicequalität (Quality of Service, QoS) erfordert eine MPLS-Zuordnung zwischen jedem unserer Servicebereitsteller und IBM Cloud. Cloud-Service-Provider können zum gegenwärtigen Zeitpunkt keine QoS-Unterstützung bieten, da diese durchgängig von einem Ende bis zum anderen reichen und jedes dazwischen liegende Gerät einschließen muss. Es ist keine Ausweichlösung durch Tunnelung oder durch ein anderes Verfahren verfügbar.

## Bietet Direct Link Unterstützung für Jumbo-Frames?

Jumbo-Frames (bis 9214 Byte) werden von Dedicated und von Dedicated Hosting unterstützt.
Die Unterstützung durch Connect und Exchange ist theoretisch möglich, erfordert jedoch die Zusammenarbeit Ihres Service-Providers mit IBM, um sicherzustellen, dass die End-to-End-Verbindung (einschließlich der zugrundeliegenden NNI-Schnittstelle) Jumbo-Frames unterstützt.
Exchange und Connect werden standardmäßig mit 1500-Byte-MTU-Unterstützung eingerichtet. 

## Wie kann ein Kunde mit Direct Link Connect die Router-Diversität über denselben Netzbetreiber sicherstellen (z. B. Verizon in DAL03)?

Wir verfügen über verschiedene XCR-Router, die verschiedene NNI-Links zum Netzbetreiber erstellen. Ab diesem Punkt liegt die Verwaltung der Diversität in der Verantwortung des Netzbetreibers.

## Muss der Kunde für Direct Link Connect 2 Links für die Redundanz bestellen, oder verfügt Direct Link Connect über inhärente Redundanz?

Bestellen Sie 2 Links für die Diversität. Wir stellen keine Redundanz zwischen Switch- oder Routerinstanzen bereit. Die Kunden stellen Redundanz für jede Direct Link-Instanz durch ihre BGP-Konfigurationen bereit.

## Kann ich meine Verbindungsbandbreite ohne großen Aufwand zum Beispiel von 1 GB auf 5 GB erweitern?

Für Geschwindigkeiten bis 1 G installieren wir in der Regel 1-G-Glasfaserkabel. Für Geschwindigkeiten von 2 G bis 10 G installieren wir 10-G-Glasfaserkabel. Für das Upgrade von 1 G auf 5 G müssten daher neue Glasfaserkabel zugewiesen oder eingebaut werden. Das Upgrade wäre folglich ein servicerelevantes Ereignis. Wenn Sie eine Zunahme in dieser Größenordnung erwarten, können Sie bereits zu Beginn Ihrer Direct Link-Bereitstellung die Installation von 10-G-Glasfaserkabeln anfordern oder sofort die Geschwindigkeitsstufe 2 G bestellen, damit von Anfang an 10-G-Glasfaserkabel verwendet werden.

## Ist ECMP eine geeignete Methode für redundante Verbindungen? Welche Alternativen gib es?

Beachten Sie, dass ECMP nicht für redundante Verbindungen konzipiert wurde, sondern für den Lastausgleich über zwei Links. Bei Verwendung von ECMP müssen beide Verbindungen auf demselben IBM Cloud-Router für Querverbindungen (XCR-Router) enden, der dadurch zu einem  Single Point of Failure wird. (Mit anderen Worten: ECMP kann nur in zwei Sitzungen auf demselben IBM Cloud-XCR-Router bereitgestellt werden.) 

ECMP ist eine Funktion von BGP. Wenn Sie Redundanz bereitstellen möchten, fordern Sie zwei Direct Link-Verbindungen an, die jeweils zu einem der beiden XCR-Router führen. Wenn Sie ECMP und Redundanz gleichzeitig verwenden möchten., benötigen Sie zwei Direct Link-Verbindungen auf jedem XCR-Router, damit zwei ECMP-Sitzungen gleichzeitig ausgeführt werden können.

Wenn einige Ihrer Kunden zwei Links zu verschiedenen XCR-Routern im selben Rechenzentrum eingerichtet haben (z. B. WDC02) kann die Funktionsübernahme nach Bedarf durch BGP-Konfigurationen erfolgen. Diese Konfiguration bietet eine geringere Redundanz (und Sicherheit) als Direct Link-Verbindungen zu zwei separaten Rechenzentren wie WDC02 und WDC05.
