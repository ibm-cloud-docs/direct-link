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
{:download: .download}

# Panoramica sui prezzi competitivi
{: #competitive-pricing-overview}

Le aziende scelgono di utilizzare l'interconnessione cloud privata come ad esempio {{site.data.keyword.cloud}} Direct Link, AWS Direct Connect, Google Cloud Interconnect e Microsoft Azure ExpressRoute per diversi motivi, che includono prestazioni di rete superiori, requisiti di sicurezza e privacy e riduzione dei costi della larghezza di banda. Sebbene la tua azienda possa utilizzare un'architettura di rete di interconnessione cloud privata per sfruttare i vantaggi sulla sicurezza e sulle prestazioni, la riduzione associata dei costi di rete è una metrica che favorisce chiaramente IBM Cloud Direct Link in molti scenari di utilizzo. 

## Perché scegliere IBM Direct Link?
{: #why-choose-ibm-cloud-direct-link}

Le tariffe standard di IBM per Direct Link hanno un valore notevole per i clienti che utilizzano le risorse cloud in modo attivo. Questo viene confermato nel calcolo del TCO per un Direct Link rispetto alla sua concorrenza.

Una connessione di 10Gbps dedicata per Direct Link al momento costa $4.999 in Nord America. Questa offerta garantisce ingresso e uscita illimitati alle risorse IBM Cloud attraverso la connessione. Direct Link non ha un'opzione a consumo.

I seguenti confronti rappresentano il punto critico rispetto alla maggior parte della concorrenza. La tabella alla fine di questo articolo mostra un riepilogo dettagliato di questo confronto dei prezzi, per regione geografica.

## AWS
{: #aws}

AWS (come Google e Microsoft) presenta un'offerta a consumo che si presta a un ingresso poco costoso con però un prezzo che varia sensibilmente in uscita.
* Il prezzo di AWS 10Gbps è composto da ore di porta a un addebito ricorrente mensile (MRC) di $1.620 più un addebito di trasferimento di $,02/GB in uscita (in Nord America).
* Per un confronto con IBM Cloud Direct Link Dedicated, una connessione AWS Direct Connect 10Gbps al 5% di utilizzo (o 170TB) in uscita in un mese costerebbe a un cliente $5.020, rispetto a $4.999 per una connessione Direct Link 10Gbps. Tutti i dati in uscita oltre il 5% (o 170TB) in un mese favorirebbe il modello dei prezzi a tariffa forfettaria di Direct Link.
* Per un confronto più estremo, supponendo che un cliente AWS abbia un 50% di utilizzo (o 1.7PB) in uscita in un mese, avrebbe un costo di $35.620, rispetto al prezzo di $4.999 per una connessione 10Gbps Direct Link.

## Google
{: #google}

Google (come AWS e Microsoft) presenta un'offerta a consumo che si presta a un ingresso poco costoso con però un prezzo che varia sensibilmente in uscita.

* Il prezzo di Google 10Gbps è fissato su $1.750 MRC più un addebito di trasferimento di $,02/GB in uscita (in Nord America).
* Per un confronto con IBM Cloud Direct Link Dedicated, una porta Google Cloud (GCP) 10Gbps al 5% di utilizzo o (170TB) in uscita in un mese costerebbe a un cliente $5.172, rispetto a $4.999 per una connessione Direct Link 10Gbps. 
* Tutti i dati in uscita oltre il 5% (o 170TB) in un mese favorirebbe il modello dei prezzi a tariffa forfettaria di Direct Link.
* Per un confronto più estremo, supponendo che un cliente Google abbia un 50% di utilizzo (o 1.7 PB) in uscita in un mese, avrebbe un costo di $35.772, rispetto al prezzo di $4.999 per una connessione 10Gbps Direct Link.

## Microsoft
{: #microsoft}

Microsoft (come Google e AWS) presenta un'offerta a consumo che si presta a un ingresso poco costoso con però un prezzo che varia sensibilmente in uscita. Microsoft offre inoltre una tabella di prezzi illimitati. Entrambe le opzioni sono confrontate nelle seguenti sezioni.

### A consumo
{: #metered}

* Il prezzo di Microsoft Azure 10Gbps è composto da una tariffa per porta ($5.000 MRC) più un addebito di trasferimento di $,02/GB in uscita (in Nord America). Fin dall'inizio, TUTTI i dati trasferiti saranno più costosi rispetto a IBM Cloud Direct Link!!!
* Per un confronto con IBM Cloud Direct Link Dedicated, una porta Microsoft Azure Express Route 10Gbps al 5% di utilizzo (o 170TB) in uscita in un mese costerebbe a un cliente $8.400, rispetto a $4.999 per una connessione Direct Link 10Gbps. 
* Tutti i dati in uscita oltre un 1TB in un mese favorirebbe il modello dei prezzi forfettario di Direct Link.
* Per un confronto più estremo, supponendo che un cliente Microsoft Azure abbia un 50% di utilizzo (o 1.7 PB) in uscita in un mese, avrebbe un costo di $47.500, rispetto al prezzo di $4.999 per una connessione 10Gbps Direct Link.


### Illimitato 
{: #unmetered}

* Il prezzo di Microsoft Azure 10Gbps è composto da una tariffa per porta di $51.000 MRC per ingresso e uscita illimitati.

* Per un confronto con IBM Cloud Direct Link Dedicated, questo costo mensile ammonta a $51.000, rispetto ai $4.999 per una connessione 10Gbps Direct Link. 

## Tabella riepilogativa
{: #summary-table}

Scorri orizzontalmente quando necessario per visualizzare tutte le 5 colonne di confronto.

**Note:**
* **Le informazioni nella seguente tabella sono state ottenute dai siti web pubblici di queste aziende.**
* **Per il confronto dei prezzi viene utilizzata la dimensione di connessione di 10 Gbps.**
* **L'utilizzo è basato su 5 Gbps sostenuti o di 1.7 PB di trasferimento di dati al mese.**


| Regione | IBM illimitato | Azure illimitato | Azure a consumo | AWS a consumo (intraregionale) |
|-----|-----|-----|-----|-----|
| USA | $4.999 | $51.300 | $47.500 | $35.620 |
| TOR/MON/AMS | $5.149 | $51.300 | $47.500 | $35.620 |
| LON/OSL/STO/MEX | $5.349 | $51.300 | $47.500 | $35.620 |
| PAR/FRA/MIL | $5.499 | $51.300 | $47.500 | $35.620 |
| SEO | $5.499 | $51.300 | $90.000 | $73.020 |
| SNG/HKG | $5.699 | $82.000 | $90.000 | $73.020 |
| TOK | $5.999 |$82.000 | $90.000 | $73.020 |
| MEL/SYD | $5.999 |$82.000 | $90.000 | $73.020 |
| CHE | $5.999 |$82.000 | $90.000 | $78.120 |
| SAO | $5.999 |$82.000 | $242.350 | $188.620 |


