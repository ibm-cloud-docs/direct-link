---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-25"

keywords: order, provider, capabilities, Dedicated, cross-connect, locations, PoP, datacenter, data, center, pricing, Letter of Authorization, LOA, 

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

# Vorgehensweise zur Bestellung von IBM Cloud Direct Link Dedicated
{: #how-to-order-ibm-cloud-direct-link-dedicated}

1. Überprüfen Sie die Möglichkeiten Ihres Netzproviders, den entsprechenden Bereitstellungspunkt zu erreichen und die Querverbindung in die {{site.data.keyword.BluSoftlayer_notm}}-Umgebung einzurichten.
2. Öffnen Sie eine Anforderung für {{site.data.keyword.cloud}} Direct Link Dedicated und füllen Sie die angeforderten Informationen aus. (Unterstützung von IBM Sales Engineers kann angefordert werden.)
3. {{site.data.keyword.BluSoftlayer_notm}} stellt das Bevollmächtigungsschreiben (LOA, Letter of Authorization) für die Verbindung bereit.
4. Stellen Sie sicher, dass die Verbindung den Bereitstellungspunkt erreicht hat und vom Netzbetreiber eingerichtet wurde.
5. Bestellen Sie die Querverbindung anhand der CFA-Informationen (CFA, Customer Facility Assignment) von {{site.data.keyword.BluSoftlayer_notm}} aus dem Berechtigungsschreiben. Dieser Vorgang ist in der Regel nach 2 bis 10 Werktagen abgeschlossen. (Dieser Zeitrahmen hängt vom entsprechenden Facility-Anbieter und der Art der vom Kunden angegebenen Auftragspriorität ab.) Dieser Prozess umfasst die Einrichtung des Patches für den Abschlussport von {{site.data.keyword.BluSoftlayer_notm}}.
6. Stellen Sie für {{site.data.keyword.BluSoftlayer_notm}} den Fertigstellungshinweis für die Querverbindung vom Facility-Provider im Ticket des {{site.data.keyword.BluSoftlayer_notm}}-Portals bereit.
7. {{site.data.keyword.BluSoftlayer_notm}} überprüft den Fertigstellungshinweis auf dessen Wirksamkeit und bestellt den Patch vom LOA/CFA zum Router für Querverbindungen (XCR) und zu anderen Geräten.
8. Die IP-Zuordnung für die Netzinfrastruktur von {{site.data.keyword.BluSoftlayer_notm}} erfolgt innerhalb von drei Werktagen nach erfolgreicher Einrichtung der Querverbindung.

## Standorte
{: #dedicated-locations}

In der nachfolgenden Tabelle sind Details zu den IBM Cloud-Rechenzentren aufgeführt, in denen Direct Link Dedicated verfügbar ist:

|**IBM Standortcode** | **Kontakt für Raumtechnik**| **Site-Code für Operator** | **Operatoradresse** |
|-----------------|-----------------|--------------------|--------------------|
| **Asien und Pazifik** | | | |
| Chennai 1 | Tata | PH-01 | 226, Red Hills Road,Kallikuppam, Ambattur |
| Hong Kong 1 | Mega-I (über PACNET) | Mega-I (iAdvantage Hong Kong) |29F, 399 Chai Wan Road |
| Melbourne 1 | Digital Realty | MEL11 | 72 Radnor Drive, Deer Park |
| Melbourne 2 | NextDC | M2 | 820 Lorimer Street, Port Melbourne |
| Osaka 1 | Equinix | OS1 |  |
| Perth 1 | Metronode | F1Z | 60 Randell St, Shenton Park, Western Australia |
| Seoul 1 | C&C | Seoul01 | 46, Pangyo-ro 255beon-gil, Bundang-gu, Seongnam-si, Gyeonggi-do |
| Seoul 2 | KINX | KINX Bundang IDC | 3F Hostway IDC ,343-1 Yatap-dong , Gyeonggi-do |
| Singapore 1 | Digital Realty | SIN10 | 29A International Business Park, S180 |
| Singapore 2 | Equinix | SG1 | 20 Ayer Rajan Crescent Industrial Park |
| Sydney 1 | Global Switch | SYD01 | 400 Harris Street aka 273 Pyrmont St Ultimo  |
| Sydney 2 | Equinix | SY3 | 47 Bourke Rd |
| Sydney 3 | NextDC | S1 | 4 Eden Park Drive, Macquarie Park |
| Sydney 4 | Digital Realty | SYD10 | 1-11 Templar Rd, Erskine Park |
| Sydney 5 | Equinix | SY4 | 200 Bourke Rd |
| Tokyo 1 | Equinix | TY2 | |
| Tokyo 2 | At Tokyo | CC2 |  |
| Tokyo 3 | Equinix | TY4 | |
| Tokyo 4 | SoftBank | | |
| Tokyo 5 | NTT | | |
| **EMEA** |  |  |
| Amsterdam 2 | Equinix | AM1 / AM2 | Larrderhoogtweg 57 |
| Amsterdam 3 | KPN | Amsterdam 3 | Rondebeltweg 62 |
| Frankfurt 1 | InterXion | FRA01 | Hanauer Landstrasse 302 |
| Frankfurt 2 | Zenium | FRA1 | Leonhard - Heisswolf Str 4., Frankfurt am Main |
| Frankfurt 3 | Equinix| FRA6 | Larchenstrasse 110, Frankfurt Griesheim |
| Frankfurt 4 | E-Shelter | Frankfurt 1 | Eschborner Landstrasse 100, Building H | 
| Frankfurt 5 | InterXion | FRA05 | Weismüllerstraße 40 |
| London 1 | Equinix (fTelecity) | LD8 | 6/7 Harbour Exchange  E14 9GE |
| London 2 | Digital Realty | LHR13 | Fountain Court, Cox Lane |
| London 3 | Equinix | LD5 | 8 Buckingham Ave |
| London 4 | ARK | A103 | A57 Cody Technology Park Old, Victor Way, Farnborough |
| London 6 | Zenium | LON1 | 12 Liverpool Rd, Trading Estate |
| Milan 1 | Data IV | | Via Monzoro 101-105 , 20010 Cornaredo (MI) |
| Milan 2 | Infracom Italia | Infracom 21 Via Caldera Way | Infracom Italia Spa, Building D, Caldera Business Park, Via Caldera, 21|
| Oslo 1 | EVRY | DigiPlex - Fetsund | 9,, Heiaveien, 1900 Fetsund |
| Oslo 2 | Verizon | Verizon Oslo | Hans Møller Gassmanssvei 9 |
| Paris 1 | Global Switch | PAR01 | Société par Actions Simplifiée Unipersonnelle, 7-9 rue Petit |
| Paris 2 | Equinix | PA2 | 114 Rue Ambroise Croizat, St Denis |
| Stockholm 1 | InterXion | STO01 | Esbogatan 11 |
|  |  |  |
| **IBM PoP / Code für Rechenzentrum** | **Kontakt für Raumtechnik** | **Site-Code für Operator** |
| **Nord- und Südamerika** |  |  |
| Atlanta 1*| Digital Realty | ATL13 | 56 Marietta Street |
| Chicago 1 | Equinix | CH4 | 350 E. Cermak |
| Dallas 3 | Equinix | DA1 | 1950 N. Stemmons Freeway |
| Dallas 4 | Digital Realty | DFW14 | 2323 Bryan St |
| Dallas 9 | Digital Realty | DFW35 | 900 Quality Way |
| Dallas 10 | QTS | IRV | 6431 Longhorn Drive |
| Dallas 12 |Digital Realty | DFW18 | 907 Security Row |
| Dallas 13 | Cyrus One | Carrollton - Frankford | 1649 W. Frankford Rd |
| Denver 1* | Coresite | DE1 | 910 15th Street | 
| Houston 2* | IBM | HOU02 | 855 Greens Parkway | 
| Los Angeles 1* | Coresite | LA1 | 624 S. Grand Ave. AKA 1 Wilshire Blvd |
| Mexico 1 | Alestra | Alestra Queretaro Datacenter | Lateral Carretera Estatal 431, Parque Tecnologico Inovacion Lote 79, El Marqués |
| Miami 1 | Terremark / Verizon | NAP | 50 NE 9th Street |
| Montreal 1 | COLO-D | COLO-D1 | 2525 Rue Canadien |
| Montreal 2 | Cologix | MTL3 | 1155 University Street |
| New York City 1 | Digital Realty | JFK10 | 111 8th Ave |
| New York City 2* | Equinix | NY4 | 755 Secaucus Rd, Secaucus, NJ |
| New York City 3* | Equinix | NY5 | 800 Secaucus Rd, Secaucus, NJ |
| Sao Paulo 1 | Ascenty | SP1 | Rua Presbitero Plinio Alves de Souza, 757 J. Ermida II, Jundiai |
| Sao Paulo 2 | Equinix | SP2 | Alameda Araguaia, 3641 - Alphaville, Barueri |
| Seattle 2 | The Westin Building | WBX | 2001 6th Avenue |
| San Jose 2 | Equinix | SV1 | 11 Great Oaks Blvd |
| San Jose 3 | Digital Realty | SJC31 | 1100 Space Park Drive |
| San Jose 4 | Infomart | SJC1 | 2001 Fortune Drive |
| Toronto 1 | Digital Realty | YYZ11 | 371 Gough Rd |
| Toronto 2 | Cologix | TOR1 | 151 Front Street |
| Washington DC 2 | Equinix | DC2 | 21715 Filigree Ct |
| Washington DC 4 | Digital Realty | IAD38 | 44060 Digital Loudoun Plaza (Bldg K) |
| Washington DC 5 | Coresite | DC2 | 12098 Sunrise Valley Dr |
| Washington DC 6 | Raging Wire | VA2 | 44610 Guilford Drive |
| Washington DC 7 | Sabey | Sabey Intergate.Ashburn | 21741 Red Rum Dr|

## Preise
{: #dedicated-pricing}

Informationen zu Preisen finden Sie im [Preisdokument](/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-direct-link-dedicated).

Wenn Sie die genaue Adresse für TOK01 oder TOK02 benötigen, wenden Sie sich bitte an Ihr Direct Link-Team für Angebotsmanagement oder Vertrieb.
{:note}
