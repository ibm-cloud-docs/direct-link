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

# Come ordinare IBM Cloud Direct Link Dedicato

1. Verifica le funzionalità del tuo provider di rete per raggiungere la connessione trasversale e il PoP appropriati nell'ambiente {{site.data.keyword.BluSoftlayer_notm}}.
2. Apri una richiesta IBM Cloud Direct Link Dedicato e compila le informazioni richieste. (Può essere richiesta assistenza dagli ingegneri delle vendite di IBM.)
3. {{site.data.keyword.BluSoftlayer_notm}} fornisce la LOA (Letter of Authorization) per la connessione.
4. Conferma che il circuito ha raggiunto il PoP ed è stato completato dal vettore.
5. Ordina la connessione trasversale utilizzando le informazioni {{site.data.keyword.BluSoftlayer_notm}} CFA (Customer Facility Assignment) nella LOA, normalmente servono tra i 2 e i 10 giorni lavorativi per il completamento. (Questo intervallo di tempo dipende dalla struttura del fornitore e dal tipo di priorità dell'ordine come viene inserito dal cliente.) Questo processo include la configurazione della patch nella porta di terminazione di {{site.data.keyword.BluSoftlayer_notm}}.
6. Fornisci a {{site.data.keyword.BluSoftlayer_notm}} l'avviso di completamento della connessione trasversale dalla struttura del fornitore nel ticket del portale {{site.data.keyword.BluSoftlayer_notm}}.
7. {{site.data.keyword.BluSoftlayer_notm}} verificherà l'efficacia dell'avviso di completamento e ordinerà alla patch di venire effettuata dalla LOA/CFA al XCR (cross-connect router) e altre cose.
8. La tua assegnazione dell'IP nell'infrastruttura di rete {{site.data.keyword.BluSoftlayer_notm}} sarà completata in 3 giorni lavorativi dopo il completamento della connessione trasversale.

## Ubicazioni

La tabella fornisce i dettagli sui data center di IBM Cloud in cui è disponibile Direct Link Dedicated:

|**PoP o codice data center IBM** | **Operatore MMR (Meet Me Room)**| **Codice sito operatore** |
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
| **PoP / codice data center IBM** | **Operatore MMR (Meet Me Room)** | **Codice sito operatore** |
| **Americhe** |  |  |
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

## Prezzi

Per informazioni sui prezzi, fai riferimento al [documento dei prezzi](pricing.html).
