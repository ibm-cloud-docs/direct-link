---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-24"

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

|**IBM PoP oder Code für Rechenzentrum** | **Kontakt für Raumtechnik**| **Site-Code für Operator** |
|-----------------|-----------------|--------------------|
| **Asien und Pazifik** | | |
| CHE01 | Tata | PH-01 |
| HKG01 | Mega-I (über PACNET) | Mega-I (iAdvantage Hong Kong) |
| MEL01 | Digital Realty | MEL11 |
| MEL02 | NextDC | M2 |
| PER01 | Metronode | F1Z |
| SEO01 | C&C | Seoul01 |
| SEO02 | KINX | KINX Bundang IDC |
| SNG01 | Digital Realty | SIN10 |
| SNG02 | Equinix | SG1 |
| SYD01 | Global Switch | SYD01 |
| SYD02 | Equinix | SY3 |
| SYD04 | Digital Realty | SYD10 |
| TOK01 | Equinix | TY2 |
| TOK02 | At Tokyo | CC2 |
| **EMEA** |  |  |
| AMS02 | Equinix | AM1 / AM2 |
| AMS03 | KPN | Amsterdam 3 |
| FRA01 | InterXion | FRA01 |
| FRA02 | Zenium | FRA1 |
| FRA03 | Equinix| FRA6 |
| FRA05 | InterXion | FRA05 |
| LON01 | Telecity | LD1 |
| LON02 | Digital Realty | LHR13 |
| LON03 | Equinix | LD5 |
| LON04 | ARK | A103 |
| LON06 | Zenium | LON1 |
| MIL02 | Infracom Italia | Infracom 21 Via Caldera Way |
| OSL01 | Ervy | DigiPlex - Fetsund |
| OSL02 | Verizon | Verizon Oslo |
| PAR01 | IBM | PAR01 |
| PAR02 | Equinix | PA2 |
| STO01 | InterXion | STO01 |
|  |  |  |
| **IBM PoP / Code für Rechenzentrum** | **Kontakt für Raumtechnik** | **Site-Code für Operator** |
| **Nord- und Südamerika** |  |  |
| ATL01*| Digital Realty | ATL13 |
| CHI01* | Equinix | CH4 |
| DAL03 | Equinix | DA1 |
| DAL04 | Digital Realty | DFW14 |
| DAL09 | Digital Realty | DFW35 |
| DAL10 | QTS | IRV |
| DAL12 |Digital Realty | DFW18 |
| DAL13 | Cyrus One | Carrollton - Frankford |
| DEN01* | Coresite | DE1 |
| HOU02* | IBM | HOU02 |
| LAX01* | Coresite | LA1 |
| MEX01 | Alestra | Alestra Queretaro Datacenter |
| MIA01* | Terremark / Verizon | NAP |
| MON01 | COLO-D | COLO-D1 |
| MON02 | Cologix | MTL3 |
| NYC01 | Digital Realty | JFK10 |
| NYC02 | Equinix | NY4 |
| NYC03 | Equinix | NY5 |
| SAO01 | Ascenty | SP1 |
| SAO02 | Equinix | SP2 |
| SEA02* | The Westin Building | WBX |
| SJC02 | Equinix | SV1 |
| SJC03 | Digital Realty | SJC31 |
| SJC04 | Infomart | SJC1 |
| TOR01 | Digital Realty | YYZ11 |
| TOR02 | Cologix | TOR1 |
| WDC02 | Equinix | DC2 |
| WDC04 | Digital Realty | IAD38 |
| WDC05 | Coresite | DC2 |
| WDC06 | Raging Wire | VA2 |
| WDC07 | Sabey | Sabey Intergate.Ashburn |

## Preise

Informationen zu Preisen finden Sie im [Preisdokument](pricing.html).
