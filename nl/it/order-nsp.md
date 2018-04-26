---

copyright:
  years: 2017
lastupdated: "2017-12-04"

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
