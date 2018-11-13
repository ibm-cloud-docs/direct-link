---

copyright:
  years: 2017, 2018
lastupdated: "2018-07-23"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Vorgehensweise zur Bestellung von IBM Cloud Direct Link Dedicated

1. Überprüfen Sie die Möglichkeiten Ihres Netzproviders, den entsprechenden Bereitstellungspunkt zu erreichen und die Querverbindung in die {{site.data.keyword.BluSoftlayer_notm}}-Umgebung einzurichten.
2. Öffnen Sie eine IBM Cloud Direct Link Dedicated-Anforderung und füllen Sie die angeforderten Informationen aus. (Unterstützung von IBM Sales Engineers kann angefordert werden.)
3. {{site.data.keyword.BluSoftlayer_notm}} stellt das Bevollmächtigungsschreiben (LOA, Letter of Authorization) für die Verbindung bereit.
4. Stellen Sie sicher, dass die Verbindung den Bereitstellungspunkt erreicht hat und vom Netzbetreiber eingerichtet wurde.
5. Bestellen Sie die Querverbindung anhand der CFA-Informationen (CFA, Customer Facility Assignment) von {{site.data.keyword.BluSoftlayer_notm}} aus dem Berechtigungsschreiben. Dieser Vorgang ist in der Regel nach 2 bis 10 Werktagen abgeschlossen. (Dieser Zeitrahmen hängt vom entsprechenden Facility-Anbieter und der Art der vom Kunden angegebenen Auftragspriorität ab.) Dieser Prozess umfasst die Einrichtung des Patches für den Abschlussport von {{site.data.keyword.BluSoftlayer_notm}}.
6. Stellen Sie für {{site.data.keyword.BluSoftlayer_notm}} den Fertigstellungshinweis für die Querverbindung vom Facility-Provider im Ticket des {{site.data.keyword.BluSoftlayer_notm}}-Portals bereit.
7. {{site.data.keyword.BluSoftlayer_notm}} überprüft den Fertigstellungshinweis auf dessen Wirksamkeit und bestellt den Patch vom LOA/CFA zum Router für Querverbindungen (XCR) und zu anderen Geräten.
8. Die IP-Zuordnung für die Netzinfrastruktur von {{site.data.keyword.BluSoftlayer_notm}} erfolgt innerhalb von drei Werktagen nach erfolgreicher Einrichtung der Querverbindung.

## Standorte

In der nachfolgenden Tabelle sind Details zu den IBM Cloud-Rechenzentren aufgeführt, in denen Direct Link Dedicated verfügbar ist:

|**IBM Standortcode** | **Kontakt für Raumtechnik**| **Site-Code für Operator** | **Operatoradresse** |
|-----------------|-----------------|--------------------|--------------------|
| **Asien und Pazifik** | | | |
| CHE01 | Tata | PH-01 | 226, Red Hills Road,Kallikuppam, Ambattur |
| HKG01 | Mega-I (über PACNET) | Mega-I (iAdvantage Hong Kong) |29F, 399 Chai Wan Road |
| MEL01 | Digital Realty | MEL11 | 72 Radnor Drive, Deer Park |
| MEL02 | NextDC | M2 | 820 Lorimer Street, Port Melbourne |
| PER01 | Metronode | F1Z | 60 Randell St, Shenton Park, Western Australia |
| SEO01 | C&C | Seoul01 | 46, Pangyo-ro 255beon-gil, Bundang-gu, Seongnam-si, Gyeonggi-do |
| SEO02 | KINX | KINX Bundang IDC | 3F Hostway IDC ,343-1 Yatap-dong , Gyeonggi-do |
| SNG01 | Digital Realty | SIN10 | 29A International Business Park, S180 |
| SNG02 | Equinix | SG1 | 20 Ayer Rajan Crescent Industrial Park |
| SYD01 | Global Switch | SYD01 | 400 Harris Street aka 273 Pyrmont St Ultimo  |
| SYD02 | Equinix | SY3 | 47 Bourke Rd |
| SYD04 | Digital Realty | SYD10 | 1-11 Templar Rd, Erskine Park |
| TOK01 | Equinix | TY2 | Shinagawa-ku |
| TOK02 | At Tokyo | CC2 | Koto-ku |
| **EMEA** |  |  |
| AMS02 | Equinix | AM1 / AM2 | Larrderhoogtweg 57 |
| AMS03 | KPN | Amsterdam 3 | Rondebeltweg 62 |
| FRA01 | InterXion | FRA01 | Hanauer Landstrasse 302 |
| FRA02 | Zenium | FRA1 | Leonhard - Heisswolf Str 4., Frankfurt am Main |
| FRA03 | Equinix| FRA6 | Larchenstrasse 110, Frankfurt Griesheim |
| FRA05 | InterXion | FRA05 | Weismüllerstraße 40 |
| LON01 | Telecity | LD1 | 6/7 Harbour Exchange  E14 9GE |
| LON02 | Digital Realty | LHR13 | Fountain Court, Cox Lane |
| LON03 | Equinix | LD5 | 8 Buckingham Ave |
| LON04 | ARK | A103 | A57 Cody Technology Park Old, Victor Way, Farnborough |
| LON06 | Zenium | LON1 | 12 Liverpool Rd, Trading Estate |
| MIL02 | Infracom Italia | Infracom 21 Via Caldera Way | Infracom Italia Spa, Building D, Caldera Business Park, Via Caldera, 21|
| OSL01 | EVRY | DigiPlex - Fetsund | 9,, Heiaveien, 1900 Fetsund |
| OSL02 | Verizon | Verizon Oslo | Hans Møller Gassmanssvei 9 |
| PAR01 | IBM | PAR01 | Société par Actions Simplifiée Unipersonnelle, 7-9 rue Petit |
| PAR02 | Equinix | PA2 | 114 Rue Ambroise Croizat, St Denis |
| STO01 | InterXion | STO01 | Esbogatan 11 |
|  |  |  |
| **IBM PoP / Code für Rechenzentrum** | **Kontakt für Raumtechnik** | **Site-Code für Operator** |
| **Nord- und Südamerika** |  |  |
| ATL01*| Digital Realty | ATL13 | 56 Marietta Street |
| CHI01 | Equinix | CH4 | 350 E. Cermak |
| DAL03 | Equinix | DA1 | 1950 N. Stemmons Freeway |
| DAL04 | Digital Realty | DFW14 | 2323 Bryan St |
| DAL09 | Digital Realty | DFW35 | 900 Quality Way |
| DAL10 | QTS | IRV | 6431 Longhorn Drive |
| DAL12 |Digital Realty | DFW18 | 907 Security Row |
| DAL13 | Cyrus One | Carrollton - Frankford | 1649 W. Frankford Rd |
| DEN01* | Coresite | DE1 | 910 15th Street | 
| HOU02* | IBM | HOU02 | 855 Greens Parkway | 
| LAX01* | Coresite | LA1 | 624 S. Grand Ave. AKA 1 Wilshire Blvd |
| MEX01 | Alestra | Alestra Queretaro Datacenter | Lateral Carretera Estatal 431, Parque Tecnologico Inovacion Lote 79, El Marqués |
| MIA01* | Terremark / Verizon | NAP | 50 NE 9th Street |
| MON01 | COLO-D | COLO-D1 | 2525 Rue Canadien |
| MON02 | Cologix | MTL3 | 1155 University Street |
| NYC01 | Digital Realty | JFK10 | 111 8th Ave |
| NYC02* | Equinix | NY4 | 755 Secaucus Rd, Secaucus, NJ |
| NYC03* | Equinix | NY5 | 800 Secaucus Rd, Secaucus, NJ |
| SAO01 | Ascenty | SP1 | Rua Presbitero Plinio Alves de Souza, 757 J. Ermida II, Jundiai |
| SAO02 | Equinix | SP2 | Alameda Araguaia, 3641 - Alphaville, Barueri |
| SEA02* | The Westin Building | WBX | 2001 6th Avenue |
| SJC02 | Equinix | SV1 | 11 Great Oaks Blvd |
| SJC03 | Digital Realty | SJC31 | 1100 Space Park Drive |
| SJC04 | Infomart | SJC1 | 2001 Fortune Drive |
| TOR01 | Digital Realty | YYZ11 | 371 Gough Rd |
| TOR02 | Cologix | TOR1 | 151 Front Street |
| WDC02 | Equinix | DC2 | 21715 Filigree Ct |
| WDC04 | Digital Realty | IAD38 | 44060 Digital Loudoun Plaza (Bldg K) |
| WDC05 | Coresite | DC2 | 12098 Sunrise Valley Dr |
| WDC06 | Raging Wire | VA2 | 44610 Guilford Drive |
| WDC07 | Sabey | Sabey Intergate.Ashburn | 21741 Red Rum Dr|

## Preise

Informationen zu Preisen finden Sie im [Preisdokument](pricing.html).

**Wenn Sie die genaue Adresse für TOK01 oder TOK02 benötigen, wenden Sie sich bitte an Ihr Direct Link-Angebotsmanagement oder -Vertriebsteam.**
