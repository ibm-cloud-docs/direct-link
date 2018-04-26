---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-11"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Ordine di IBM Cloud Direct Link

Quando ti prepari ad ordinare il tipo di IBM Cloud Direct Link che meglio soddisfa i tuoi bisogni, puoi utilizzare i seguenti link (o semplicemente scorrere tramite questo documento) per visualizzare una panoramica generale del processo. Quando sei pronto a inserire il tuo ordine, puoi trovare le istruzioni dettagliate che ti guidano nel processo di ordine, nelle nostre serie di documenti "Dettagliati".

* [Come ordinare IBM Cloud Direct Link Exchange](how-to-order.html#how-to-order-ibm-cloud-direct-link-exchange)
* [Come ordinare IBM Cloud Direct Link Connect](how-to-order.html#how-to-order-ibm-cloud-direct-link-connect)
* [Come ordinare IBM Cloud Direct Link Dedicato](how-to-order.html#how-to-order-ibm-cloud-direct-link-dedicated)
* [Come ordinare Host di IBM Cloud Direct Link dedicato](how-to-order.html#how-to-order-ibm-cloud-direct-link-dedicated-hosting)

## Come ordinare IBM Cloud Direct Link Exchange 

 * Verifica le funzionalità del tuo provider di rete per raggiungere la connessione trasversale e il PoP appropriati nel provider Cloud Exchange associato.
 * Utilizza [Customer Portal ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/) per aprire una richiesta IBM Cloud Direct Link Exchange e compilare le informazioni richieste. (Può essere richiesta assistenza dagli ingegneri delle vendite di IBM.) Se utilizzi il provider Equinix, il processo di ordine e provisioning è [completamente automatizzato](cloud-exchange-automation.html).
 * Contatta il tuo provider Exchange e negozia la connettività del tuo scambio. 
 * Ordina la connettività tra il tuo provider di rete e il provider Exchange. 
 * Ordina un "circuito virtuale" tramite il provider Exchange e fai riferimento all'ID del ticket della richiesta {{site.data.keyword.BluSoftlayer_notm}} IBM Cloud Direct Link come il tuo "ID richiesta" o "ID autorizzazione"
 * L'assegnazione dell'IP nell'infrastruttura di rete {{site.data.keyword.BluSoftlayer_notm}} sarà completata in 3 giorni lavorativi dopo il completamento della richiesta del circuito virtuale.

## Come ordinare IBM Cloud Direct Link Connect 

 * Verifica le funzionalità del tuo provider di rete per raggiungere la connessione trasversale e il PoP appropriati nel provider Connect associato. 
 * Utilizza [Customer Portal ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/) per aprire una richiesta IBM Cloud Direct Link Connect e compilare le informazioni richieste. (Può essere richiesta assistenza dagli ingegneri delle vendite di IBM.) 
 * Contatta il tuo provider Connect e negozia la connettività del tuo scambio. 
 * Ordina la connettività tra il tuo provider di rete e il provider Connect. 
 * Ordina un "circuito virtuale" tramite il provider Connect e fai riferimento all'ID del ticket della richiesta {{site.data.keyword.BluSoftlayer_notm}} IBM Cloud Direct Link come il tuo "ID richiesta" o "ID autorizzazione"
 * L'assegnazione dell'IP nell'infrastruttura di rete {{site.data.keyword.BluSoftlayer_notm}} sarà completata in 3 giorni lavorativi dopo il completamento della richiesta del circuito virtuale.

## Come ordinare IBM Cloud Direct Link Dedicato 

 * Verifica le funzionalità del tuo provider di rete per raggiungere la connessione trasversale e il PoP appropriati nell'ambiente {{site.data.keyword.BluSoftlayer_notm}}.
 * Apri una richiesta IBM Cloud Direct Link Dedicato e compila le informazioni richieste. (Può essere richiesta assistenza dagli ingegneri delle vendite di IBM.)
 * {{site.data.keyword.BluSoftlayer_notm}} fornisce la LOA (Letter of Authorization) per la connessione.
 * Conferma che il circuito ha raggiunto il PoP ed è stato completato dal vettore.
 * Ordina la connessione trasversale utilizzando le informazioni {{site.data.keyword.BluSoftlayer_notm}} CFA (Customer Facility Assignment) nella LOA, normalmente servono tra i 2 e i 10 giorni lavorativi per il completamento. (Questo intervallo di tempo dipende dalla struttura del fornitore e dal tipo di priorità dell'ordine come viene inserito dal cliente.) Questo processo include la configurazione della patch nella porta di terminazione di {{site.data.keyword.BluSoftlayer_notm}}.
 * Fornisci a {{site.data.keyword.BluSoftlayer_notm}} l'avviso di completamento della connessione trasversale dalla struttura del fornitore nel ticket del portale {{site.data.keyword.BluSoftlayer_notm}}.
 * {{site.data.keyword.BluSoftlayer_notm}} verificherà l'efficacia dell'avviso di completamento e ordinerà alla patch di venire effettuata dalla LOA/CFA al XCR (cross-connect router) e altre cose.
 * La tua assegnazione dell'IP nell'infrastruttura di rete {{site.data.keyword.BluSoftlayer_notm}} sarà completata in 3 giorni lavorativi dopo il completamento della connessione trasversale.

## Come ordinare Host di IBM Cloud Direct Link dedicato 

 * Identifica i tuoi requisiti di connettività e ubicazione e collabora con il team delle vendite di IBM per finalizzare ed eseguire un'aggiunta tecnica e un contratto.
 * {{site.data.keyword.BluSoftlayer_notm}} esegue un ordine di creazione con il provider di ubicazione per i servizi e l'ambiente richiesti. La distribuzione viene normalmente completata entro 30 giorni da quando viene inserito l'ordine di creazione.
 * Quando la build del tuo cage di ubicazione viene completata, il processo di interconnessione tra il tuo cage di ubicazione e l'ingranaggio XCR dell'ambiente POD {{site.data.keyword.BluSoftlayer_notm}} seguirà il processo IBM Cloud Direct Link Dedicato, a partire dal passo 3.
