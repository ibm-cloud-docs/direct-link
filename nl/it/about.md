---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-29"

keywords: hybrid, solutions, features, benefits, port speed, cross-connect, use cases, latency, routing, options, colocation

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Informazioni su IBM Cloud Direct Link
{: #about-ibm-cloud-direct-link}

Questa sezione permette di consultare gli ulteriori dettagli sulle funzioni chiave e i vantaggi di ognuna delle quattro soluzioni di {{site.data.keyword.cloud}}
Direct Link.
  * [**IBM Cloud Direct Link Exchange**](#direct-link-exchange-solution)
  * [**IBM Cloud Direct Link Connect**](#direct-link-connect-solution)
  * [**IBM Cloud Direct Link Dedicated**](#direct-link-dedicated-solution)
  * [**IBM Cloud Direct Link Dedicated Hosting**](#direct-link-dedicated-hosting-solution)

## La soluzione IBM Cloud Direct Link Exchange
{: #direct-link-exchange-solution}

La soluzione IBM Cloud Direct Link Exchange consente agli utenti di utilizzare un provider Cloud Exchange per fornire la connettività alle ubicazioni {{site.data.keyword.cloud_notm}}. Questa offerta normalmente fornisce la connettività a un costo ridotto, perché la connettività fisica da {{site.data.keyword.cloud_notm}} al provider Cloud Exchange è già in atto, condivisa tra altri clienti. 

**Casi di utilizzo comuni:** _Migliore per i carichi di lavoro ibridi e tra provider, per i trasferimenti di dati frequenti o grandi con un'elevata larghezza di banda in uscita, per i carichi di lavoro privati e per la gestione dell'ambiente.  Questa opzione normalmente viene selezionata quando l'ubicazione PoP desiderata già dispone del provider IBM Cloud Direct Link Exchange desiderato._

![Figura 1](/images/Direct-Link-Exchange.png)

 * **Ubicazione di terminazione:** PoP (point of presence) {{site.data.keyword.cloud_notm}}.

 * **Tempo di distribuzione tipico:** per i provider Equinix il tempo di distribuzione tipico sarà in ore. Per altri provider, 5-10 giorni dopo che il circuito raggiunge Exchange. Il tempo di distribuzione può essere compreso tra 30 e 60 giorni complessivi, a seconda dell'ubicazione e dei requisiti quando si ordina un circuito da un NSP o un vettore. 

 * **Dettagli connessione trasversale:** le connessioni trasversali fisiche per l'interconnessione Cloud Exchange sicura vengono conservate tra {{site.data.keyword.cloud_notm}} e il provider Cloud Exchange. I clienti richiedono un "Circuito virtuale" dal provider Cloud Exchange, che stabilisce la connettività logica a {{site.data.keyword.cloud_notm}}, una volta che sono interconnessi al provider Cloud Exchange. 

 * **Opzioni di velocità della porta:** seleziona 50Mbps, 100Mbps, 200Mbps, 500Mbps, 1Gbps, 2Gbps o 5Gbps.

 * **Latenza approssimativa:** la latenza approssimativa è circa 1.5ms nell'area locale (data center con lo stesso prefisso di tre lettere, ad esempio DAL, AMS, MEL). Consulta http://lg.softlayer.com/ per le misurazioni della latenza dell'ubicazione PoP-to-PoP (P2P) dal vivo.

 * **Servizi di ubicazione IBM:** Nessuno.

 * **Ridondanza:** {{site.data.keyword.cloud_notm}} fornisce connessioni a due (2) XCR (cross-connect router) diversi come parte del prodotto. Per stabilire la connettività ridondante, i clienti devono configurare BGP su ogni connessione Direct Link come preferiscono. Gli esempi includono opzioni come le seguenti: _prefer Lowest MED_, _prefer highest local-preference_ o _prefer shorter AS paths_.

 * **Opzioni di instradamento Locale/Globale:** l'opzione di instradamento locale è l'opzione di instradamento predefinita. Fornisce l'accesso ai datacenter nello stesso mercato del PoP di Direct Link (indicato, ad esempio, come DAL, AMS o MEL). L'opzione di instradamento globale è necessaria come un componente aggiuntivo per il collegamento delle tue risorse IBM ad altre risorse IBM Cloud in datacenter al di fuori del mercato locale. Fornisce un modo per condividere i carichi di lavoro tra le risorse IBM Cloud (ad esempio Dallas con Ashburn o Dallas con Francoforte). 
 
## La soluzione IBM Cloud Direct Link Connect
{: #direct-link-connect-solution}

**Casi di utilizzo comuni** _La soluzione IBM Cloud Direct Link Connect consente agli utenti di utilizzare un provider del servizio di rete (Network Service Provider - NSP) per fornire la connettività alle ubicazioni {{site.data.keyword.cloud_notm}}. Questa offerta normalmente fornisce la connettività a un costo ridotto, perché la connettività fisica da {{site.data.keyword.cloud_notm}} all'NSP è già in atto, condivisa tra altri clienti._

![Figura 2](/images/Direct-Link-Connect.png)

* **Ubicazione di terminazione:** PoP (point of presence) {{site.data.keyword.cloud_notm}}.

* **Tempo di distribuzione tipico:** da 5 a 10 giorni dopo che il circuito raggiunge Exchange. Il tempo di distribuzione può essere compreso tra 30 e 60 giorni complessivi, a seconda dell'ubicazione e dei requisiti quando si ordina un circuito da un NSP o un vettore. 

* **Dettagli connessione trasversale:** le connessioni trasversali fisiche per l'interconnessione Direct Link Connect sicura vengono conservate tra {{site.data.keyword.cloud_notm}} e il provider Connect. I clienti richiedono un "Circuito virtuale" dal provider Cloud Connect, che stabilisce la connettività logica a {{site.data.keyword.cloud_notm}}, una volta che sono interconnessi al provider Cloud Connect.

* **Opzioni di velocità della porta:** seleziona 50Mbps, 100Mbps, 200Mbps, 500Mbps, 1Gbps, 2Gbps o 5Gbps.

* **Latenza approssimativa:** la latenza approssimativa è circa 1.5ms nell'area locale (data center con lo stesso prefisso di tre lettere, ad esempio DAL, AMS, MEL). Consulta http://lg.softlayer.com/ per le misurazioni della latenza dell'ubicazione PoP-to-PoP (P2P) dal vivo.

* **Servizi di ubicazione IBM:** Nessuno.

* **Ridondanza:** {{site.data.keyword.cloud_notm}} fornisce connessioni a due (2) XCR (cross-connect router) diversi come parte del prodotto. Per stabilire la connettività ridondante, i clienti devono configurare BGP su ogni connessione Direct Link come preferiscono. Gli esempi includono opzioni come le seguenti: _prefer Lowest MED_, _prefer highest local-preference_ o _prefer shorter AS paths_.

* **Opzioni di instradamento Locale/Globale:** l'opzione di instradamento locale è l'opzione di instradamento predefinita. Fornisce l'accesso ai datacenter nello stesso mercato del PoP di Direct Link (indicato, ad esempio, come DAL, AMS o MEL). L'opzione di instradamento globale è necessaria come un componente aggiuntivo per il collegamento delle tue risorse IBM ad altre risorse IBM Cloud in datacenter al di fuori del mercato locale. Viene utilizzata per condividere i carichi di lavoro tra le risorse IBM Cloud (ad esempio Dallas con Ashburn o Dallas con Francoforte).

## La soluzione IBM Cloud Direct Link Dedicated
{: #direct-link-dedicated-solution}

La soluzione IBM Cloud Direct Link Dedicated consente agli utenti di terminare una connessione trasversale fiber a singolo tenant nella propria rete privata {{site.data.keyword.cloud_notm}}. Questa offerta può essere utilizzata dai clienti con strutture di co-ubicazione vicine ai datacenter e ai POP di IBM Cloud, come pure dai provider del servizio di rete che forniscono i circuiti ai datacenter in loco dei clienti e ad altri datacenter.

 **Casi di utilizzo comuni:** _Migliore per l'utilizzo dei carichi di lavoro ibridi e tra provider, per i trasferimenti di dati frequenti o grandi, per i carichi di lavoro privati e per la gestione dell'ambiente. Questa opzione normalmente viene selezionata: (1) quando il PoP desiderato non dispone dell'Exchange o dell'NSP desiderato, (2) per i carichi di lavoro ad elevate prestazioni che richiedono una elevata velocità oppure (3) per i requisiti di conformità che non possono essere soddisfatti dal modello di implementazione IBM Cloud Direct Link Exchange o Connect._
 
 **Caso di utilizzo 1: Funzione cliente in IBM Cloud.**

![Figura 3](/images/Direct-link-Dedicated.png)

**Caso di utilizzo 2: Co-ubicazione cliente in IBM Cloud.**

![Figura 3B](/images/dedicated-model-colo.png)

 * **Ubicazione di terminazione:** PoP (point of presence) o Data Center (DC) {{site.data.keyword.cloud_notm}}. 

 * **Tempo di distribuzione tipico:** da 10 a 15 giorni lavorativi dopo che il nuovo circuito raggiunge il POP. Il tempo di distribuzione può essere di 30-60 giorni complessivi, a seconda dell'ubicazione e dei requisiti quando si ordina un circuito da un NSP o un vettore.

 * **Dettagli connessione trasversale:** {{site.data.keyword.cloud_notm}} fornisce una LOA (Letter of Authorization) che un cliente utilizza per ordinare l'ethernet fiber (solo fiber a modalità singola, ottiche 1Gig-LX o 10Gig-LR) eseguita da un cage del cliente o da un cage del provider al punto di terminazione CFA {{site.data.keyword.cloud_notm}}, che sarà vincolato all'infrastruttura XCR (cross-connect router). Il supporto deve essere di una lunghezza d'onda di 1310nm.

 * **Opzioni di velocità della porta:** seleziona 1Gbps, 2Gbps, 5Gbps o 10Gbps.

 * **Latenza approssimativa:** la latenza approssimativa è circa 1.5ms nell'area locale (data center con lo stesso prefisso di tre lettere, ad esempio DAL, AMS, MEL).  Consulta http://lg.softlayer.com/ per le misurazioni della latenza dell'ubicazione PoP-to-PoP (P2P) dal vivo.

 * **Servizi di ubicazione IBM:** Nessuno.

 * **Ridondanza:** {{site.data.keyword.cloud_notm}} fornisce connessioni a due (2) XCR (cross-connect router) diversi come parte del prodotto. Per stabilire la connettività ridondante, i clienti devono configurare BGP su ogni connessione Direct Link come preferiscono. Gli esempi includono opzioni come le seguenti: _prefer Lowest MED_, _prefer highest local-preference_ o _prefer shorter AS paths_.

 * **Opzioni di instradamento Locale/Globale:** l'opzione di instradamento locale è l'opzione di instradamento predefinita. Fornisce l'accesso ai datacenter nello stesso mercato del PoP di Direct Link (indicato, ad esempio, come DAL, AMS o MEL). L'opzione di instradamento globale è necessaria come un componente aggiuntivo per il collegamento delle tue risorse IBM ad altre risorse IBM Cloud in datacenter al di fuori del mercato locale. Fornisce un modo per condividere i carichi di lavoro tra le risorse IBM Cloud (ad esempio Dallas con Ashburn o Dallas con Francoforte). 

## La soluzione IBM Cloud Direct Link Dedicated Hosting
{: #direct-link-dedicated-hosting-solution}

La soluzione IBM Cloud Direct Link Dedicated Hosting fornisce una connettività simile a IBM Cloud Direct Link Dedicated, ma il punto di connessione è vicino a un data center {{site.data.keyword.cloud_notm}}, ciò migliora la latenza per i casi di utilizzo a prestazioni elevate. IBM Cloud offre molti servizi personalizzabili e di condivisione con questa soluzione, con una determinazione dei prezzi semplice.

**Casi di utilizzo comuni:** _Migliore per l'utilizzo di tecnologie di calcolo non standard, per i requisiti di archiviazione dedicati o per l'utilizzo di investimenti IT esistenti._

![Figura 4](/images/Direct-Link-Dedicated-Hosting.png)

* **Ubicazione di terminazione:** {{site.data.keyword.cloud_notm}} Data Center (DC).

 * **Tempo di distribuzione tipico:** 30-60 giorni dopo che tutti i requisiti vengono finalizzati e che vengono firmati i contratti.

 * **Dettagli connessione trasversale:** {{site.data.keyword.cloud_notm}} fornisce connessioni fiber 1G o 10G dall'infrastruttura XCR (cross-connect router) {{site.data.keyword.cloud_notm}} all'ambiente di condivisone del cliente come parte della distribuzione.  Se i servizi di condivisione non sono richiesti (se gli ambienti esistenti sono già collegati), {{site.data.keyword.cloud_notm}} fornisce una LOA (Letter of Authorization) che un cliente utilizza per ordinare l'ethernet fiber (solo fibre a modalità singola, ottiche 1Gig-LX o 10Gig-LR) eseguita da un cage del cliente al punto di terminazione CFA {{site.data.keyword.cloud_notm}}, che sarà vincolato all'infrastruttura XCR (cross-connect router). Il supporto deve essere di una lunghezza d'onda di 1310nm.

 * **Opzioni di velocità della porta:** seleziona 1Gbps, 2Gbps, 5Gbps o 10Gbps.

 * **Latenza approssimativa:** la latenza approssimativa è circa 0.5ms nel data center locale.

 * **Servizi di ubicazione IBM:** Sì.

 * **Ridondanza:** {{site.data.keyword.cloud_notm}} fornisce connessioni a due (2) XCR (cross-connect router) diversi come parte del prodotto. Per stabilire la connettività ridondante, i clienti devono configurare BGP su ogni connessione Direct Link come preferiscono. Gli esempi includono opzioni come le seguenti: _prefer Lowest MED_, _prefer highest local-preference_ o _prefer shorter AS paths_.

 * **Opzioni di instradamento Locale/Globale:** l'opzione di instradamento locale è l'opzione di instradamento predefinita. Fornisce l'accesso ai datacenter nello stesso mercato del PoP di Direct Link (indicato, ad esempio, come DAL, AMS o MEL). L'opzione di instradamento globale è necessaria come un componente aggiuntivo per il collegamento delle tue risorse IBM ad altre risorse IBM Cloud in datacenter al di fuori del mercato locale. Viene utilizzata per condividere i carichi di lavoro tra le risorse IBM Cloud (ad esempio Dallas con Ashburn o Dallas con Francoforte).
