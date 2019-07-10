---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: provisioning, order, Exchange, Equinix, automated, status, connection

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


# Provisioning di IBM Cloud Direct Link Exchange per Equinix
{: #provisioning-ibm-cloud-direct-link-exchange-for-equinix}

Se l'ordine di {{site.data.keyword.cloud}} Direct Link è per Equinix Cloud Exchange, il provisioning del servizio è completamente automatizzato, il che significa che puoi inserire un ordine per una connessione {{site.data.keyword.cloud_notm}} Direct Link (Equinix) senza aprire un ticket di supporto IBM. 

Le funzionalità di automazione attualmente sono limitata a Equinix Cloud Exchange. Nelle seguenti release, l'automazione sarà abilitata per altri provider.
{:note}

## Prerequisiti
{: #cloud-exchange-equinix-prerequisites}

Per utilizzare la funzionalità di ordine automatizzato, le tue VLAN private devono essere associate a un VRF nella rete privata {{site.data.keyword.cloud_notm}}. Se questo requisito non viene soddisfatto, verrà generato un ticket di supporto IBM quando inserisci l'ordine tramite il portale del cliente.

## Procedura per l'ordine e il provisioning
{: #cloud-exchange-steps-for-ordering-and-provisioning}

**Passo 1:**

Segui i passi da 1 a 7 dai [passi per l'ordine di Cloud Exchange](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange) regolari.

**Passo 2:**

Dopo aver inserito l'ordine, viene avviato il provisioning di IBM Cloud Direct.

Puoi vedere lo stato della tua connessione dopo aver inserito l'ordine. Se la configurazione viene completata correttamente dal lato IBM, visualizzerai lo stato di **Provisioned**. Se la configurazione non viene terminata, visualizzerai lo stato di **In-Progress**. Se la configurazione ha esito negativo, visualizzerai lo stato di **Create Failed**. Se la configurazione è stata completata correttamente e la connessione BGP è attiva, visualizzerai lo stato di **UP**.

![Passo 9 in corso](/images/pup_exchange_equinix_inProgress.png)

**Passo 3:**

Se la connessione è nello stato **Provisioned**, fai clic sul nome della connessione facendo clic sul link **<connection_name>**.  Dovrebbe portarti alla pagina dei dettagli. 

![Passo 10](/images/pup_exchange_equinix_provisioned.png)

La seguente figura mostra i diversi stati della connessione dopo l'inserimento dell'ordine:

![Passo 9 attivo](/images/pup_exchange_equinix_up.png)

**Passo 4:**

Prendi nota delle informazioni **Customer IP Address** e **Service Key**. Saranno necessarie per configurare il router edge del cliente e la chiave di autorizzazione per la configurazione (Equinix) lato provider cloud, rispettivamente.

![Passo 9 attivo](/images/pup_exchange_equinix_provisioned_details.png)

**Passo 5:**

Per le connessioni nello stato **Provisioned**, dopo aver fatto clic sul nome della connessione facendo clic su **<connection_name>**, visualizzerai un messaggio di errore se vi è una mancata corrispondenza con la velocità del link di peer. Una volta che la velocità è la stessa sul lato IBM e Equinix, questa notifica di errore non viene più visualizzata.

![Passo 11](/images/pup_exchange_equinix_provisioned_details_portSpeedMismatch.png)

**Passo 6:**

Per le connessioni nello stato **Create Failed**, viene generato un ticket di supporto IBM e vengono comunicati ulteriori dettagli tramite di esso. Quando espandi la connessione, puoi vedere i dettagli del ticket di supporto.

![Passo 12](/images/pup_exchange_equinix_list_createFailed.png)

**Passo 7:**

Per le connessioni nello stato **Provisioned**, **UP** o **DOWN**, puoi **Eliminare** la connessione facendo clic sull'overflow nella colonna **ACTIONS** accanto alla connessione.

![Passo 13](/images/pup_exchange_equinix_list_delete.png)

**Passo 8:**

Per le connessioni nello stato **Create Failed**, puoi **Annullare** la connessione facendo clic sulla colonna **ACTIONS** accanto ad essa.

![Passo 14](/images/pup_exchange_equinix_list_delete.png)
