---

copyright:
  years: 2017, 2018
lastupdated: "2018-08-09"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Informazioni su IBM Cloud Direct Link

Questa sezione permette di consultare gli ulteriori dettagli sulle funzioni chiave e i vantaggi di ognuna delle quattro soluzioni di Direct Link.
  * [**IBM Cloud Direct Link Exchange**](#the-ibm-cloud-direct-link-exchange-solution)
  * [**IBM Cloud Direct Link Connect**](#the-ibm-cloud-direct-link-connect-solution)
  * [**IBM Cloud Direct Link Dedicato**](#the-ibm-cloud-direct-link-dedicated-solution)
  * [**IBM Cloud Direct Link Dedicated Hosting**](#the-ibm-cloud-direct-link-dedicated-hosting-solution)

## La soluzione IBM Cloud Direct Link Exchange

La soluzione IBM Cloud Direct Link Exchange consente agli utenti di utilizzare un provider Cloud Exchange per fornire la connettività alle ubicazioni {{site.data.keyword.BluSoftlayer_notm}}. Questa offerta normalmente fornisce la connettività a un costo ridotto, perché la connettività fisica da {{site.data.keyword.BluSoftlayer_notm}} al provider Cloud Exchange è già in atto, condivisa tra altri clienti.

**Casi di utilizzo comuni:** _Migliore per i carichi di lavoro ibridi e tra provider, per i trasferimenti di dati frequenti o grandi con un'elevata larghezza di banda in uscita, per i carichi di lavoro privati e per la gestione dell'ambiente.  Questa opzione normalmente viene selezionata quando l'ubicazione PoP desiderata già dispone del provider IBM Cloud Direct Link Exchange desiderato._

![Figura 1](/images/Direct-Link-Exchange.png)

 * **Ubicazione di terminazione:** PoP (point of presence) {{site.data.keyword.BluSoftlayer_notm}}.

 * **Tempo di distribuzione tipico:** per i provider Equinix il tempo di distribuzione tipico sarà in ore. Per altri provider, 5-10 giorni dopo che il circuito raggiunge Exchange. Il tempo di distribuzione può essere di 30-60 giorni complessivi, a seconda dell'ubicazione e dei requisiti quando si ordina un circuito da un NSP o un vettore.

 * **Dettagli connessione trasversale:** le connessioni trasversali fisiche per l'interconnessione Cloud Exchange sicura vengono conservate tra {{site.data.keyword.BluSoftlayer_notm}} e il provider Cloud Exchange. I clienti richiedono un "Circuito virtuale" dal provider Cloud Exchange, che stabilisce la connettività logica a {{site.data.keyword.BluSoftlayer_notm}}, una volta che sono interconnessi al provider Cloud Exchange.

 * **Opzioni di velocità della porta:** seleziona 50Mbps, 100Mbps, 200Mbps, 500Mbps o 1Gbps.

 * **Latenza approssimativa:** la latenza approssimativa è circa 1.5ms nell'area locale (data center con lo stesso prefisso di tre lettere, ad esempio DAL, AMS, MEL). Consulta http://lg.softlayer.com/ per le misurazioni della latenza dell'ubicazione PoP-to-PoP (P2P) dal vivo.

 * **Servizi di ubicazione:** Nessuno.

 * **Ridondanza:** per stabilire la ridondanza per IBM Cloud Direct Link Exchange, è necessaria la connettività in 2+ ubicazioni o la selezione di un'ubicazione con un XCR secondario disponibile che può essere utilizzata dal provider Cloud Exchange.

 * **Opzioni di instradamento Locale/Globale:** l'opzione di instradamento locale è l'opzione di instradamento predefinita. Fornisce l'accesso ai datacenter nello stesso Market as the Direct Link PoP (indicato, ad esempio, come DAL, AMS o MEL). L'opzione di instradamento globale è necessaria come un componente aggiuntivo per il collegamento delle tue risorse IBM Cloud sul mercato ad altre risorse IBM Cloud in datacenter al di fuori del mercato locale. Viene utilizzata per condividere i carichi di lavoro tra le risorse IBM Cloud (ad esempio Dallas con Ashburn o Dallas con Frankfurt).
 
## La soluzione IBM Cloud Direct Link Connect

**Casi di utilizzo comuni** simili alla soluzione Direct Link Exchange. Offre più opzioni di velocità. La soluzione Direct Link Cloud Connect fornisce un punto di ingresso a basso costo per i clienti della rete IBM Cloud.

![Figura 2](/images/Direct-Link-Connect.png)

* **Ubicazione di terminazione:** PoP (point of presence) {{site.data.keyword.BluSoftlayer_notm}}.

* **Tempo di distribuzione tipico:** 5-10 giorni dopo che il circuito raggiunge Exchange. Il tempo di distribuzione può essere di 30-60 giorni complessivi, a seconda dell'ubicazione e dei requisiti quando si ordina un circuito da un NSP o un vettore.

* **Dettagli connessione trasversale:** le connessioni trasversali fisiche per l'interconnessione Direct Link Connect sicura vengono conservate tra {{site.data.keyword.BluSoftlayer_notm}} e il provider Connect. I clienti richiedono un "Circuito virtuale" dal provider Cloud Connect, che stabilisce la connettività logica a {{site.data.keyword.BluSoftlayer_notm}}, una volta che sono interconnessi al provider Cloud Connect.

* **Opzioni di velocità della porta:** seleziona 50Mbps, 100Mbps, 200Mbps, 500Mbps, 1Gbps, 2Gbps o 5Gbps.

* **Latenza approssimativa:** la latenza approssimativa è circa 1.5ms nell'area locale (data center con lo stesso prefisso di tre lettere, ad esempio DAL, AMS, MEL). Consulta http://lg.softlayer.com/ per le misurazioni della latenza dell'ubicazione PoP-to-PoP (P2P) dal vivo.

* **Servizi di ubicazione:** Nessuno.

* **Ridondanza:** per stabilire la ridondanza per IBM Cloud Direct Link Connect, è necessaria la connettività in 2+ ubicazioni o la selezione di un'ubicazione con un XCR secondario disponibile che può essere utilizzata dal provider IBM Cloud Connect.

* **Opzioni di instradamento Locale/Globale:** l'opzione di instradamento locale è l'opzione di instradamento predefinita. Fornisce l'accesso ai datacenter nello stesso Market as the Direct Link PoP (indicato, ad esempio, come DAL, AMS o MEL). L'opzione di instradamento globale è necessaria come un componente aggiuntivo per il collegamento delle tue risorse IBM Cloud sul mercato ad altre risorse IBM Cloud in datacenter al di fuori del mercato locale. Viene utilizzata per condividere i carichi di lavoro tra le risorse IBM Cloud (ad esempio Dallas con Ashburn o Dallas con Frankfurt).

## La soluzione IBM Cloud Direct Link Dedicato

La soluzione IBM Cloud Direct Link Dedicato consente agli utenti di terminare una connessione trasversale fiber, a modalità singola e dedicata nella propria rete privata {{site.data.keyword.BluSoftlayer_notm}}.

 **Casi di utilizzo comuni:** _Migliore per l'utilizzo dei carichi di lavoro ibridi e tra provider, per i trasferimenti di dati frequenti o grandi, per i carichi di lavoro privati e per la gestione dell'ambiente.  Questa opzione normalmente viene selezionata: (1) quando il PoP desiderato non dispone del provider IBM Cloud Direct Link Exchange desiderato, (2) per i carichi di lavoro ad elevate prestazioni che richiedono una elevata velocità, (3) per i requisiti di conformità che non possono venire soddisfatti dal modello di implementazione IBM Cloud Direct Link Exchange._

![Figura 3](/images/Direct-link-Dedicated.png)

 * **Ubicazione di terminazione:** PoP (point of presence) {{site.data.keyword.BluSoftlayer_notm}}.

 * **Tempo di distribuzione tipico:** 10-15 giorni lavorativi dopo che il nuovo circuito raggiunge il POP. Il tempo di distribuzione può essere di 30-60 giorni complessivi, a seconda dell'ubicazione e dei requisiti quando si ordina un circuito da un NSP o un vettore.

 * **Dettagli connessione trasversale:** {{site.data.keyword.BluSoftlayer_notm}} fornisce una LOA (Letter of Authorization) che un cliente utilizza per ordinare l'ethernet fiber (solo fibre a modalità singola, ottiche 1Gig-LX o 10Gig-LR) eseguita da un cage o un provider del cliente al punto di terminazione CFA {{site.data.keyword.BluSoftlayer_notm}}, che sarà vincolato all'infrastruttura XCR (cross-connect router). Il supporto deve essere di una lunghezza d'onda di 1310nm.

 * **Opzioni di velocità della porta:** seleziona 1Gbps, 2Gbps, 5Gbps o 10Gbps.

 * **Latenza approssimativa:** la latenza approssimativa è circa 1.5ms nell'area locale (data center con lo stesso prefisso di tre lettere, ad esempio DAL, AMS, MEL).  Consulta http://lg.softlayer.com/ per le misurazioni della latenza dell'ubicazione PoP-to-PoP (P2P) dal vivo.

 * **Servizi di ubicazione:** Nessuno.

 * **Ridondanza:** per stabilire la ridondanza è richiesta la connettività IBM Cloud Direct Link in 2+ ubicazioni o la selezione di un'ubicazione con un XCR secondario disponibile e una seconda richiesta di connessione IBM Cloud Direct Link.

 * **Opzioni di instradamento Locale/Globale:** l'opzione di instradamento locale è l'opzione di instradamento predefinita. Fornisce l'accesso ai datacenter nello stesso Market as the Direct Link PoP (indicato, ad esempio, come DAL, AMS o MEL). L'opzione di instradamento globale è necessaria come un componente aggiuntivo per il collegamento delle tue risorse IBM Cloud sul mercato ad altre risorse IBM Cloud in datacenter al di fuori del mercato locale. Viene utilizzata per condividere i carichi di lavoro tra le risorse IBM Cloud (ad esempio Dallas con Ashburn o Dallas con Frankfurt).

## La soluzione IBM Cloud Direct Link Dedicated Hosting

La soluzione IBM Cloud Direct Link Dedicated Hosting fornisce una connettività simile a IBM Cloud Direct Link Dedicato, ma il punto di connessione è vicino a un data center {{site.data.keyword.BluSoftlayer_notm}}, che migliora la latenza per i casi di utilizzo a prestazioni elevate. IBM Cloud offre molti servizi personalizzabili e di condivisione con questa soluzione, con una determinazione dei prezzi semplice.

**Casi di utilizzo comuni:** _Migliore per l'utilizzo di tecnologie di calcolo non standard, per i requisiti di archiviazione dedicati o per l'utilizzo di investimenti IT esistenti._

![Figura 4](/images/Direct-Link-Dedicated-Hosting.png)

* **Ubicazione di terminazione:** {{site.data.keyword.BluSoftlayer_notm}} Data Center (DC).

 * **Tempo di distribuzione tipico:** 30-60 giorni dopo che tutti i requisiti vengono finalizzati e che vengono firmati i contratti.

 * **Dettagli connessione trasversale:** {{site.data.keyword.BluSoftlayer_notm}} fornisce connessioni fiber 1G o 10G dall'infrastruttura XCR (cross-connect router) {{site.data.keyword.BluSoftlayer_notm}} all'ambiente di condivisone del cliente come parte della distribuzione.  Se i servizi di condivisione non sono richiesti (se gli ambienti esistenti sono già collegati), {{site.data.keyword.BluSoftlayer_notm}} fornisce una LOA (Letter of Authorization) che un cliente utilizza per ordinare l'ethernet fiber (solo fibre a modalità singola, ottiche 1Gig-LX o 10Gig-LR) eseguita da un cage del cliente al punto di terminazione CFA {{site.data.keyword.BluSoftlayer_notm}}, che sarà vincolato all'infrastruttura XCR (cross-connect router). Il supporto deve essere di una lunghezza d'onda di 1310nm.

 * **Opzioni di velocità della porta:** seleziona 1Gbps, 2Gbps, 5Gbps o 10Gbps.

 * **Latenza approssimativa:** la latenza approssimativa è circa 0.5ms nel data center locale.

 * **Servizi di ubicazione:** Sì.

 * **Ridondanza:** {{site.data.keyword.BluSoftlayer_notm}} fornisce connessioni a due XCR (cross-connect router) come parte del prodotto. Per stabilire la connettività ridondante i clienti devono configurare BGP su ogni connessione Direct Link se ritengono adeguato archiviare la ridondanza. Gli esempi includono opzioni come le seguenti: _prefer Lowest MED_, _prefer highest local-preference_ o _prefer shorter AS paths_.

 * **Opzioni di instradamento Locale/Globale:** l'opzione di instradamento locale è l'opzione di instradamento predefinita. Fornisce l'accesso ai datacenter nello stesso Market as the Direct Link PoP (indicato, ad esempio, come DAL, AMS o MEL). L'opzione di instradamento globale è necessaria come un componente aggiuntivo per il collegamento delle tue risorse IBM Cloud sul mercato ad altre risorse IBM Cloud in datacenter al di fuori del mercato locale. Viene utilizzata per condividere i carichi di lavoro tra le risorse IBM Cloud (ad esempio Dallas con Ashburn o Dallas con Frankfurt).
