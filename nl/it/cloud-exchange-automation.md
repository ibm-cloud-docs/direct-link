---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: provisioning, Exchange, order, support, ticket, diverse, virtual circuit, parameters, Terms and Conditions

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

# Provisioning di IBM Cloud Direct Link Exchange
{: #provisioning-ibm-cloud-direct-link-exchange}

Questa pagina ti spiega come ordinare il servizio {{site.data.keyword.cloud}} Direct Link Exchange. Se l'ordine di {{site.data.keyword.cloud_notm}} Direct Link è per Equinix Cloud Exchange, il provisioning del servizio è completamente automatizzato, il che significa che puoi [inserire un ordine per una connessione IBM Cloud Direct Link (Equinix) senza aprire un ticket di supporto IBM](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix) come descritto in un documento correlato. 

Le funzionalità di automazione attualmente sono limitata a Equinix Cloud Exchange. Nelle seguenti release, l'automazione sarà abilitata per altri provider.
{:note}

## Prerequisiti
{: #cloud-exchange-prerequisites}

Per utilizzare la funzionalità di automazione, le tue VLAN private devono essere associate a un VRF nella rete privata {{site.data.keyword.cloud_notm}}. Se questo requisito non viene soddisfatto, verrà generato un ticket di supporto IBM quando inserisci l'ordine tramite il portale del cliente.

 * [Come ordinare Cloud Exchange](#how-to-order-cloud-exchange-no-equinix)
 * [Come ordinare Cloud Exchange per Equinix](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix)

## Come ordinare Cloud Exchange
{: #how-to-order-cloud-exchange-no-equinix}

Per eseguire il provisioning di una connessione IBM Cloud Direct Link Exchange, completa la seguente procedura:

**Passo 1:**

Accedi al tuo account cliente in [Customer Portal ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://cloud.ibm.com/).

**Passo 2:**

Nella scheda **Network**, seleziona **Direct Link -> Exchange**, per aprire una pagina che mostra le connessioni IBM Cloud Direct Link esistenti, se presenti.

![Passo 2](/images/pup_exchange_list.png)

**Passo 3:**

Dopo aver fatto clic sul pulsante **Order Direct Link Exchange** all'inizio della pagina, vedrai il modulo d'ordine dove puoi immettere i parametri di configurazione per la connessione IBM Cloud Direct Link Exchange.

![Passo 3](/images/pup_exchange_create_default.png)

**Passo 3A:**

Facoltativamente, se sono accessibili porte diverse e non hai precedentemente eseguito il provisioning del primo circuito virtuale, vedrai una schermata simile alla seguente, che mostra due porte, da cui puoi selezionare il tuo secondo circuito virtuale.

![immagine-porta-2](/images/pup_exchange_create_ports.png)

**Passo 4:**

Nel modulo d'ordine, immetti i seguenti parametri per configurare Direct Link:
  * Immetti il nome della connessione IBM Cloud Direct Link.
  * Dall'elenco, seleziona l'ubicazione in cui desideri stabilire la connessione IBM Cloud Direct Link. 
  * Dall'elenco, seleziona il nome del provider Cloud Exchange che preferisci.
  * Seleziona la velocità di collegamento richiesta per la connessione.
  * Seleziona l'opzione di instradamento richiesta per la connessione.
  * Immetti un numero ASN dall'intervallo fornito nella casella delle informazioni per gli scambi BGP.

**Passo 5:**

Mentre selezioni o immetti questi valori, puoi vedere un addebito mensile approssimativo sul pannello nel lato destro.

![Passo 4-5](/images/pup_exchange_create_prices.png)

**Passo 6.**

I campi del modulo vengono convalidati man mano che fornisci l'input.
Devi **ACCETTARE** i termini e le condizioni affinché il pulsante "Create" venga abilitato. 

**Passo 7:**

Dopo aver accettato i termini e le condizioni, quando inserisci l'ordine, viene generato un ticket di supporto dopo aver inserito l'ordine per continuare con il provisioning del servizio. Il numero del ticket verrà visualizzato nella IU dopo aver inserito l'ordine. 

![Passo NE1](/images/pup_exchange_ticket_notification.png)

**Passo 8:**

Facendo clic sul numero del ticket nel messaggio, puoi vedere i dettagli del ticket.

![Passo NE2](/images/pup_exchange_ticket_details.png)
