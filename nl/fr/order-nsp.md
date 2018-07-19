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

# Comment commander IBM Cloud Direct Link Dedicated ?

1. Vérifiez que votre fournisseur de réseau peut accéder au point de présence (PoP) approprié et établir une interconnexion avec l'environnement {{site.data.keyword.BluSoftlayer_notm}}.
2. Ouvrez une demande IBM Cloud Direct Link Dedicated et indiquez les informations demandées. (Vous pouvez faire appel à des ingénieurs commerciaux IBM pour vous aider).
3. {{site.data.keyword.BluSoftlayer_notm}} fournit une lettre d'autorisation (LOA) pour la connexion.
4. Confirmez que votre circuit a atteint le PoP et a été finalisé par l'opérateur.
5. Commandez une interconnexion à l'aide des informations d'affectation de site client (CFA (Customer Facility Assignment)) {{site.data.keyword.BluSoftlayer_notm}} figurant dans la lettre d'autorisation, ce qui prend en principe de 2 à 10 jours ouvrables pour aboutir. (Ce délai dépend du fournisseur du site et du type de priorité de la commande défini par le client). Ce processus comprend la configuration du correctif pour le port de terminaison {{site.data.keyword.BluSoftlayer_notm}}.
6. Fournissez à {{site.data.keyword.BluSoftlayer_notm}} l'avis d'achèvement de l'interconnexion du fournisseur du site figurant dans le ticket du portail {{site.data.keyword.BluSoftlayer_notm}}.
7. {{site.data.keyword.BluSoftlayer_notm}} vérifiera l'efficacité de l'avis d'achèvement et commandera le correctif à appliquer à partir des informations LOA/CFA au routeur d'interconnexion (XCR) et à d'autres équipements.
8. L'affectation de votre adresse IP sur l'infrastructure réseau {{site.data.keyword.BluSoftlayer_notm}} sera effective dans les trois jours ouvrables une fois l'interconnexion terminée.

## Emplacements

Le tableau fournit des détails sur les centres de données IBM Cloud dans lesquels Direct Link Dedicated est disponible :

|**Code de point de présence ou de centre de données IBM**| **Opérateur de salle d'interconnexion**| **Code de site opérateur** |
|-----------------|-----------------|--------------------|
| **APAC** | | |
| CHE01 | Tata | PH-01 |
| HKG01 | Mega-I (via PACNET) | Mega-I (iAdvantage Hong Kong) |
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
|**Code point de présence/centre de données IBM**| **Opérateur de salle d'interconnexion**| **Code de site opérateur** |
| **Amériques** |  |  |
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

## Tarification

Pour obtenir des informations de tarification, voir la [rubrique sur la tarification](pricing.html).
