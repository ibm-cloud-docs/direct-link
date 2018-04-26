---

copyright:
 years: 2017, 2018
lastupdated: "2018-04-05"

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
Ja. IBM Cloud misst die Bandbreite aller ausgehenden Verbindungen für Direct Link-Produkte. Die eingehende Bandbreite ist kostenlos und unbegrenzt.

## Welche zusätzlichen Gebühren können für mich von anderen Parteien im Zusammenhang mit Direct Link anfallen?
Es können zusätzliche Gebühren von Ihrem Austauschprovider oder Netzserviceprovider anfallen. Weitere Informationen zu diesen Gebühren erhalten Sie von Ihrem/Ihren Provider/n.

## Wie erreiche ich Redundanz mit IBM Cloud Direct Link?
Sie können mit Direct Link Redundanz erreichen, indem Sie Verbindungen zu mehr als einer {{site.data.keyword.BluSoftlayer_notm}} des IBM Cloud Direct Link Dedicated-Providers oder Exchange-Providers herstellen. Alternativ können Sie einen der IBM Cloud Direct Link-Provider nutzen, der Ihrem Service Redundanz hinzufügt.

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
|<ul><li>DAL</li><li>WDC</li><li>SEA</li><li>SJC</li><li>NYC*</li><li>CHI*</li><li>DEN*</li><li>MIA*</li><li>ATL*</li><li>LAX*</li><li>TOR</li><li>MON</li><li>AMS</li><li>FRA</li></ul>|<ul><li>TOK</li><li>HKG</li><li>PAR</li><li>MIL</li><li>STK*</li><li>OSL</li></ul>|<ul><li>MEX</li><li>SAO</li><li>SYD</li><li>MEL</li><li>PER*</li><li>CHE</li><li>SEO</li></ul>|
**Tabelle 1: Nutzungsstufen**<br/>
Direct Link-Angebote in den mit einem Stern (*) gekennzeichneten Märkten MÜSSEN 'Global Routing' bestellen.

## Wenn ich die Angebote 'Direct Link NSP' oder 'Direct Link Cloud Exchange' in einer Region wie Dallas verwende, habe ich dann Zugriff auf andere Regionen in den USA über Direct Link?
Ja, wenn Sie das Add-on 'Global Routing' auswählen, haben Sie Zugriff auf Bereiche außerhalb Ihrer Region. Wenn diese Option nicht ausgewählt ist, wird Ihr Direct Link-Datenverkehr auf die Region für den von Ihnen gewählten Bereitstellungspunkt begrenzt.

## Kann ich eine Verbindung zu jeder verfügbaren Region von einem angegebenen Direct Link-Standort herstellen?
Ja, solange Sie Direct Link mit dem Add-on 'Global Routing' bestellen.

## Kann ich die Regionen einzuschränken, die ich über Direct Link erreichen kann?
Nein IBM Cloud bietet zwei Optionen: (1) nur eine einzige Region oder (2) alle Regionen, mit dem Add-on 'Global Routing'.

## Was ist, wenn ich den automatisierten Bestellablauf für Equinix Cloud Exchange angewendet habe und mir ein Teilnetz zugewiesen wurde, das sich mit meinem internen Netz überschneidet?

Ab März 2018 ist das empfohlene bewährte Verfahren, Ihre automatisierte Bestellung abzubrechen und ein neues Ticket einzureichen, um den Direct Link-Fragebogen ausfüllen zu können. Darin sollten Sie angeben, ob Sie ein anderes Teilnetz im Bereich 10.254.x.x oder im Bereich 172.32.x.x bevorzugen.

## Was ist der Unterschied zwischen Direct Link Exchange und Direct Link Connect?

Diese zwei Services sind sich ähnlich, beide relativ kostengünstig, Latenz-tolerant und bieten schnelle Einstiegspunkte für die Vorteile von IBM Cloud Direct Link. Der wesentliche Unterschied ist, dass Exchange Rechenzentrenprovider nutzt, Connect hingegen Telco-Netzbetreiber. Hier einige zusätzliche Details:

**Direct Link Exchange** ist für Kunden gedacht, die es bevorzugen, einen Datenaustausch innerhalb eines Rechenzentrums zu nutzen. Bei einem Exchange-Service können Kunden schnell die Konnektivität mehrerer Clouds zu ihrer Colocation aktivieren, da die zugrundeliegenden Verbindungen bereits bereitgestellt sind (diese anderen Cloud-Provider müssen bereits über physische Verbindungen innerhalb der Facility verfügen).

Direct Link Exchange kann eine gemeinsam genutzte Umgebung mit mehreren Clouds über einen einzigen Cloud-Austauschport ermöglichen, der mittels einer NNI-Verbindung auf Layer 2 zwischen IBM Cloud und dem Cloud Exchange Service Provider erstellt wird. Es sind Portgeschwindigkeiten bis zu 1 Gb verfügbar.

**Direct Link Connect** ist für Kunden gedacht, die es bevorzugen, ihr vorhandenes Netz zwischen ihrer lokalen Bereitstellung und IBM Cloud zu nutzen. Mit einem Direct Link Connect-Service können Kunden neue wie auch vorhandene Telco-Netze (wie z. B. MPLS) nutzen, mit denen IBM Cloud schnell aktiviert werden kann, indem sie im Voraus bereitgestellte zugrundeliegende Verbindungen nutzen.

Mit Direct Link Connect stellen sowohl IBM als auch der Partner Verbindungen auf Layer 2 und 3 über duale Layer-2-Network-to-Network Interfaces (NNIs) mit 10 Gb her, die von IBM Partner in Facilitys weltweit betrieben werden. Es sind Portgeschwindigkeiten bis zu 5 Gb verfügbar.

