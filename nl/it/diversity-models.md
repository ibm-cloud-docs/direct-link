---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-19"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Modelli per la diversità e la ridondanza in Direct Link
{: #models-for-diversity-and-redundancy-in-direct-link}

Questo documento fornisce una serie di schemi correlati ai problemi di ridondanza e diversità, che possono aiutarti a trovare un modello per la creazione della distribuzione di {{site.data.keyword.cloud}} Direct Link più efficace per soddisfare le tue esigenze. Gli schemi sono organizzati in livelli incrementali di complessità e anche in base all'offerta di Direct Link illustrata da ognuno di essi. Direct Link non è un servizio intrinsecamente ridondante nell'XCR (cross-connect router), i clienti hanno la responsabilità di creare la ridondanza tramite i loro schemi BGP (Border Gateway Protocol). 

## Sezione 1: Configurazioni relativamente semplici per archiviare la diversità

Le configurazioni illustrate in questo gruppo si basano sul fatto che tutti gli asset sono ubicati nello stesso PoP e nello stesso mercato globale.

**Figura 1: Direct Link Exchange con diversità, nello stesso PoP (non-AZ)**

![Exchange con diversità nello stesso PoP](/images/exchange-diversity-same-pop.png)

**Figura 2: Direct Link Connect con diversità nello stesso PoP (non-AZ)**

![Connect con diversità nello stesso PoP](/images/connect-diversity-same-pop.png)

**Figura 3: Direct Link Dedicated con diversità nello stesso PoP (non-AZ)**

![Dedicated con diversità nello stesso PoP](/images/dedicated-diversity-same-pop.png)

## Sezione 2: Diversità che include le opzioni Instradamento globale e AZ

Le configurazioni mostrate in questo gruppo offrono le opzioni per la connessione tra le zone di disponibilità locali e i mercati.

### Parte A: Diversità in una zona di disponibilità locale (AZ)

**Figura 4: Direct Link Exchange con diversità in una AZ locale (WDC, DAL, FRA, LON)**

![Exchange con diversità nella AZ locale](/images/exchange-diversity-local-az.png)

**Figura 5: Direct Link Connect con diversità in una AZ locale (WDC, DAL, FRA, LON)**

![Connect con diversità nella AZ locale](/images/connect-diversity-local-az.png)

**Figura 6: Direct Link Dedicated con diversità in una AZ locale (WDC, DAL, FRA, LON)**

![Dedicated con diversità nella AZ locale](/images/dedicated-diversity-local-az.png)

### Parte B: Diversità in mercati locali differenti, con l'instradamento globale

**Figura 7: Direct Link Connect con diversità e instradamento globale**

![Connect con diversità e instradamento globale](/images/connect-diversity-global.png)

**Figura 8: Direct Link Exchange con diversità e instradamento globale**

![Exchange con diversità e instradamento globale](/images/exchange-diversity-global.png)

**Figura 9: Direct Link Dedicated con diversità e instradamento globale**

![Dedicated con diversità e instradamento globale](/images/dedicated-diversity-global.png)

## Ulteriori informazioni su ECMP

ECMP è una funzione di BGP. Alcuni clienti hanno chiesto informazioni sull'utilizzo di ECMP come un modo per archiviare la ridondanza. Tuttavia, il solo ECMP non è sufficiente. Questa sezione spiega il motivo.

**D: ECMP è il modo di effettuare le connessioni ridondanti? Quali alternative esistono?**

ECMP non è progettato per la creazione di connessioni ridondanti ma per il bilanciamento del carico su due link. Con ECMP su IBM Cloud, entrambe le connessioni devono terminare con lo stesso XCR (cross-connect router) IBM Cloud, il che lo rende un singolo punto di errore. (In altre parole, ECMP può essere fornito solo come due sessioni nello stesso XCR IBM Cloud.)

**Figura 10: provisioning di ECMP**

![Modello dedicato ECMP](/images/ecmp-without-diversity.png)

### Come archiviare la diversità e la ridondanza

Se stai cercando l'elevata disponibilità (HA) o la ridondanza completa: configura due link in XCR differenti nello stesso data center (ad esempio DAL03). Quindi esegui il failover come necessario utilizzando le configurazioni BGP.

**Figura 11: ECMP con XCR duali**

![Modello XCR duale ECMP](/images/ecmp-with-diversity.png)
