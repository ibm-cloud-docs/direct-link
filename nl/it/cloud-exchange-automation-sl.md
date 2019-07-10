---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-06-12"

keywords: provisioning, Exchange, order, support, ticket, diverse, virtual circuit, parameters, Terms and Conditions, legacy, customer, portal

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:note: .note}
{:download: .download}

# Provisioning di IBM Cloud Direct Link Exchange tramite il portale del cliente legacy
{: #provisioning-ibm-cloud-direct-link-exchange-legacy}

Questa pagina ti spiega come ordinare il servizio {{site.data.keyword.cloud}} Direct Link Exchange dal portale del cliente legacy {{site.data.keyword.cloud_notm}}.
{: shortdesc}

Se l'ordine di {{site.data.keyword.cloud_notm}} Direct Link è per Equinix Cloud Exchange, il provisioning del servizio è completamente automatizzato, il che significa che puoi [inserire un ordine per una connessione IBM Cloud Direct Link (Equinix) senza aprire un ticket di supporto IBM](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix-legacy) come descritto in un documento correlato. 

Le funzionalità di automazione attualmente sono limitata a Equinix Cloud Exchange. Nelle seguenti release, l'automazione sarà abilitata per altri provider.
{:note}

## Prerequisiti
{: #cloud-exchange-prerequisites-legacy}

Per utilizzare la funzionalità di automazione, le tue VLAN private devono essere associate a un VRF nella rete privata {{site.data.keyword.cloud_notm}}. Se questo requisito non viene soddisfatto, verrà generato un ticket di supporto IBM quando inserisci l'ordine tramite il portale del cliente.

 * [Come ordinare Cloud Exchange](#how-to-order-cloud-exchange-no-equinix-legacy)
 * [Come ordinare Cloud Exchange per Equinix](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix-legacy)

## Come ordinare Cloud Exchange
{: #how-to-order-cloud-exchange-no-equinix-legacy}

Per eseguire il provisioning di una connessione IBM Cloud Direct Link Exchange, completa la seguente procedura:

**Passo 1:**

Accedi al tuo account cliente in [Customer Portal ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/).

**Passo 2:**

Nella scheda **Network**, seleziona **Direct Link -> Exchange**, per aprire una pagina che mostra le connessioni IBM Cloud Direct Link esistenti, se presenti.

![Passo 2](/images/Equinix-Step2.png)

**Passo 3:**

Dopo aver fatto clic sul pulsante **Order Direct Link Exchange** all'inizio della pagina, vedrai il modulo d'ordine dove puoi immettere i parametri di configurazione per la connessione IBM Cloud Direct Link Exchange.

![Passo 3](/images/Equinix-Step3.png)

**Passo 3A:**

Facoltativamente, se sono accessibili porte diverse e non hai precedentemente eseguito il provisioning del primo circuito virtuale, vedrai una schermata simile alla seguente, che mostra due porte, da cui puoi selezionare il tuo secondo circuito virtuale.

![immagine-porta-2](/images/exchange-2-ports-image.png)

**Passo 4:**

Nel modulo d'ordine, immetti i seguenti parametri per configurare Direct Link:
  * Immetti il nome della connessione IBM Cloud Direct Link.
  * Dall'elenco, seleziona l'ubicazione PoP in cui desideri stabilire la connessione IBM Cloud Direct Link.
  * Dall'elenco, seleziona il nome del provider Cloud Exchange che preferisci.
  * Seleziona la velocità di collegamento richiesta per la connessione.
  * Seleziona l'opzione di instradamento richiesta per la connessione.
  * Immetti un numero ASN dall'intervallo fornito nella casella delle informazioni per gli scambi BGP.

**Passo 5:**

Mentre selezioni o immetti questi valori, puoi vedere un addebito mensile approssimativo sul pannello nel lato sinistro.

![Passo 4-5](/images/Equinix-Step4-5.png)

**Passo 6.**

Dopo aver fornito i valori di input, la schermata della IU successiva mostra il prezzo mensile attuale basato sulle opzioni che hai selezionato.

**Passo 7:**

Devi **ACCETTARE** i termini e le condizioni prima di poter inserire l'ordine di IBM Cloud Direct Link. Leggi i termini e le condizioni attentamente, perché contengono le informazioni tecniche importanti che devi comprendere prima di procedere. 

Se non vengono accettati i termini e le condizioni, verrà generato un ticket di supporto IBM all'inserimento dell'ordine.
{:note}

Le seguenti figure mostrano le schermate che puoi visualizzare, in base alla tua selezione in questo passo.

La seguente figura mostra la schermata dei termini e delle condizioni:

![Passo 7](images/Equinix-Step7.png)

La seguente figura mostra la schermata che puoi vedere se non sei d'accordo con i termini e le condizioni quando inserisci l'ordine. La schermata mostra il numero del ticket generato:

![Passo 7 accettazione](/images/Equinix-Step7-NoAgree.png)

La seguente figura mostra un esempio del ticket che sta venendo aperto:

![Passo 7 ticket](/images/Equinix-Step7-NoAgree-Ticket.png)

**Passo 8:**

Dopo aver accettato i termini e le condizioni, quando inserisci l'ordine, viene generato un ticket di supporto dopo aver inserito l'ordine per continuare con il provisioning del servizio. Il numero del ticket verrà visualizzato nella IU dopo aver inserito l'ordine. 

![Passo NE1](/images/Non-Equinix-Step1.png)

**Passo 9:**

Facendo clic sul numero del ticket nel messaggio, puoi vedere i dettagli del ticket.

![Passo NE2](/images/Non-Equinix-Step2.png)
