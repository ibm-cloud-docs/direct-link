---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-02-19"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:note: .note}
{:download: .download}

# Come ordinare IBM Cloud Direct Link Dedicato
{: #how-to-order-ibm-cloud-direct-link-dedicated}

1. Verifica le funzionalità del tuo provider di rete per raggiungere la connessione trasversale e il PoP appropriati nell'ambiente {{site.data.keyword.BluSoftlayer_notm}}.
2. Apri una richiesta {{site.data.keyword.cloud}} Direct Link Dedicato e compila le informazioni richieste. (Può essere richiesta assistenza dagli ingegneri delle vendite di IBM.)
3. {{site.data.keyword.BluSoftlayer_notm}} fornisce la LOA (Letter of Authorization) per la connessione.
4. Conferma che il circuito ha raggiunto il PoP ed è stato completato dal vettore.
5. Ordina la connessione trasversale utilizzando le informazioni {{site.data.keyword.BluSoftlayer_notm}} CFA (Customer Facility Assignment) nella LOA, normalmente servono tra i 2 e i 10 giorni lavorativi per il completamento. (Questo intervallo di tempo dipende dalla struttura del fornitore e dal tipo di priorità dell'ordine come viene inserito dal cliente.) Questo processo include la configurazione della patch nella porta di terminazione di {{site.data.keyword.BluSoftlayer_notm}}.
6. Fornisci a {{site.data.keyword.BluSoftlayer_notm}} l'avviso di completamento della connessione trasversale dalla struttura del fornitore nel ticket del portale {{site.data.keyword.BluSoftlayer_notm}}.
7. {{site.data.keyword.BluSoftlayer_notm}} verificherà l'efficacia dell'avviso di completamento e ordinerà alla patch di venire effettuata dalla LOA/CFA al XCR (cross-connect router) e altre cose.
8. La tua assegnazione dell'IP nell'infrastruttura di rete {{site.data.keyword.BluSoftlayer_notm}} sarà completata in 3 giorni lavorativi dopo il completamento della connessione trasversale.

## Ubicazioni

La tabella fornisce i dettagli sui data center di IBM Cloud in cui è disponibile Direct Link Dedicated:

|**Codice ubicazione IBM** | **Operatore MMR (Meet Me Room)**| **Codice sito operatore** | **Indirizzo operatore** |
|-----------------|-----------------|--------------------|--------------------|
| **APAC** | | | |
| CHE01 | Tata | PH-01 | 226, Red Hills Road,Kallikuppam, Ambattur |
| HKG01 | Mega-I (via PACNET) | Mega-I (iAdvantage Hong Kong) |29F, 399 Chai Wan Road |
| MEL01 | Digital Realty | MEL11 | 72 Radnor Drive, Deer Park |
| MEL02 | NextDC | M2 | 820 Lorimer Street, Port Melbourne |
| PER01 | Metronode | F1Z | 60 Randell St, Shenton Park, Western Australia |
| SEO01 | C&C | Seoul01 | 46, Pangyo-ro 255beon-gil, Bundang-gu, Seongnam-si, Gyeonggi-do |
| SEO02 | KINX | KINX Bundang IDC | 3F Hostway IDC ,343-1 Yatap-dong , Gyeonggi-do |
| SNG01 | Digital Realty | SIN10 | 29A International Business Park, S180 |
| SNG02 | Equinix | SG1 | 20 Ayer Rajan Crescent Industrial Park |
| SYD01 | Global Switch | SYD01 | 400 Harris Street aka 273 Pyrmont St Ultimo  |
| SYD02 | Equinix | SY3 | 47 Bourke Rd |
| SYD03 | NextDC | 4 Eden Park Drive, Macquarie Park |
| SYD04 | Digital Realty | SYD10 | 1-11 Templar Rd, Erskine Park |
| SYD05 | Equinix | 200 Bourke Rd |
| TOK01 | Equinix | TY2 |
| TOK02 | At Tokyo | CC2 | 
| TOK03 | Equinix | 
| TOK04 | SoftBank |
| TOK05 | NTT |
| **EMEA** |  |  |
| AMS02 | Equinix | AM1 / AM2 | Larrderhoogtweg 57 |
| AMS03 | KPN | Amsterdam 3 | Rondebeltweg 62 |
| FRA01 | InterXion | FRA01 | Hanauer Landstrasse 302 |
| FRA02 | Zenium | FRA1 | Leonhard - Heisswolf Str 4., Frankfurt am Main |
| FRA03 | Equinix| FRA6 | Larchenstrasse 110, Frankfurt Griesheim |
| FRA04 | E-Shelter | Frankfurt 1 | Eschborner Landstrasse 100, Building H | 
| FRA05 | InterXion | FRA05 | Weismüllerstraße 40 |
| LON01 | Equinix (fTelecity) | LD8 | 6/7 Harbour Exchange  E14 9GE |
| LON02 | Digital Realty | LHR13 | Fountain Court, Cox Lane |
| LON03 | Equinix | LD5 | 8 Buckingham Ave |
| LON04 | ARK | A103 | A57 Cody Technology Park Old, Victor Way, Farnborough |
| LON06 | Zenium | LON1 | 12 Liverpool Rd, Trading Estate |
| MIL01 | Data IV | Via Monzoro 101-105 , 20010 Cornaredo (MI) |
| MIL02 | Infracom Italia | Infracom 21 Via Caldera Way | Infracom Italia Spa, Building D, Caldera Business Park, Via Caldera, 21|
| OSL01 | EVRY | DigiPlex - Fetsund | 9,, Heiaveien, 1900 Fetsund |
| OSL02 | Verizon | Verizon Oslo | Hans Møller Gassmanssvei 9 |
| PAR01 | Global Switch | PAR01 | Société par Actions Simplifiée Unipersonnelle, 7-9 rue Petit |
| PAR02 | Equinix | PA2 | 114 Rue Ambroise Croizat, St Denis |
| STO01 | InterXion | STO01 | Esbogatan 11 |
|  |  |  |
| **PoP / codice data center IBM** | **Operatore MMR (Meet Me Room)** | **Codice sito operatore** |
| **Americhe** |  |  |
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
| MEX01 | Alestra | Alestra Queretaro Datacenter | Lateral Carretera Estatal 431,Parque Tecnologico Inovacion Lote 79, El Marqués |
| MIA01 | Terremark / Verizon | NAP | 50 NE 9th Street |
| MON01 | COLO-D | COLO-D1 | 2525 Rue Canadien |
| MON02 | Cologix | MTL3 | 1155 University Street |
| NYC01 | Digital Realty | JFK10 | 111 8th Ave |
| NYC02* | Equinix | NY4 | 755 Secaucus Rd, Secaucus, NJ |
| NYC03* | Equinix | NY5 | 800 Secaucus Rd, Secaucus, NJ |
| SAO01 | Ascenty | SP1 | Rua Presbitero Plinio Alves de Souza, 757 J. Ermida II,Jundiai |
| SAO02 | Equinix | SP2 | Alameda Araguaia, 3641 - Alphaville, Barueri |
| SEA02 | The Westin Building | WBX | 2001 6th Avenue |
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

## Prezzi

Per informazioni sui prezzi, fai riferimento al [documento dei prezzi](/docs/infrastructure/direct-link/pricing.html).

Se hai bisogno dell'indirizzo esatto di TOK01 o TOK02, contatta il tuo team di gestione o di vendita dell'offerta Direct Link.
{:note}
