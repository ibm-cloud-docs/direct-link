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

# Passo dopo passo: ordina un IBM Cloud Direct Link Exchange

Questa pagina ti spiega come ordinare il servizio IBM Cloud Direct Link Exchange. Se l'ordine di IBM Cloud Direct Link è per Equinix Cloud Exchange, il provisioning del servizio è completamente automatizzato, il che significa che puoi inserire un ordine per una connessione IBM Cloud Direct Link (Equinix) senza aprire un ticket di supporto IBM.

**(Nota: le funzionalità di automazione attualmente sono limitata a Equinix Cloud Exchange. Nelle seguenti release, l'automazione sarà abilitata per altri provider.)**

## Prerequisiti

Per utilizzare la funzionalità di automazione, le tue VLAN private devono essere associate a un VRF nella rete privata IBM Cloud. Se questo requisito non viene soddisfatto, verrà generato un ticket di supporto IBM quando inserisci l'ordine tramite il portale del cliente. 

 * [Come ordinare Cloud Exchange](#how-to-order-cloud-exchange)
 * [Come ordinare Cloud Exchange per Equinix](#how-to-order-cloud-exchange-for-equinix)

## Come ordinare Cloud Exchange

Per eseguire il provisioning di una connessione IBM Cloud Direct Link Exchange, completa la seguente procedura: 

**Passo 1:**

Accedi al tuo account cliente in [Customer Portal ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/).

**Passo 2:**

Nella scheda **Network**, seleziona **Direct Link -> Exchange**, per aprire una pagina che mostra le connessioni IBM Cloud Direct Link esistenti, se presenti.

![Passo 2](/images/Equinix-Step2.png)

**Passo 3:**

Dopo aver fatto clic sul pulsante **Order Direct Link Exchange** all'inizio della pagina, vedrai il modulo d'ordine dove puoi immettere i parametri di configurazione per la connessione IBM Cloud Direct Link Exchange.

![Passo 3](/images/Equinix-Step3.png)

**Passo 4:**

Nel modulo d'ordine, immetti i seguenti parametri per configurare Direct Link: 
  * Immetti il nome della connessione IBM Cloud Direct Link. 
  * Dall'elenco, seleziona l'ubicazione PoP in cui desideri stabilire la connessione IBM Cloud Direct Link. 
  * Dall'elenco, seleziona il nome del provider Cloud Exchange che preferisci. 
  * Seleziona la velocità di collegamento richiesta per la connessione. 
  * Seleziona l'opzione di instradamento richiesta per la connessione. 
  * Immetti un numero ASN dall'intervallo fornito nella casella delle informazioni per gli scambi BGP. 

**Passo 5:**

Come selezioni o immetti questi valori, puoi vedere un addebito mensile approssimativo sul pannello nel lato sinistro.

![Passo 4-5](/images/Equinix-Step4-5.png)

**Passo 6.**

Dopo aver fornito i valori di input, la schermata della IU successiva mostra il prezzo mensile attuale basato sulle opzioni che hai selezionato. 

**Passo 7:**

Devi **ACCETTARE** i termini e le condizioni prima di poter inserire l'ordine di IBM Cloud Direct Link. Leggi i termini e le condizioni attentamente, perché contengono le informazioni tecniche importanti che devi comprendere prima di procedere. **(Nota: se non vengono accettati i termini e le condizioni, sarà generato un ticket di supporto IBM all'inserimento dell'ordine.)** Le seguenti figure mostrano le schermate che puoi visualizzare, in base alla tua selezione in questo passo.

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

## Come ordinare Cloud Exchange per Equinix 

**Passo 1:**

Segui i passi da 1 a 7 dai precedenti passi per l'ordine di Cloud Exchange

**Passo 2:**

Dopo aver inserito l'ordine, viene avviato il provisioning di IBM Cloud Direct.

![Passo 8](/images/Equinix-Step8.png)

**Passo 3:**

Puoi vedere lo stato della tua connessione dopo aver inserito l'ordine. Se la configurazione viene completata correttamente dal lato IBM, visualizzerai lo stato di **Provisioned**. Se la configurazione non viene terminata, visualizzerai lo stato di **In-Progress**. Se la configurazione ha esito negativo, visualizzerai lo stato di **Create Failed**. Se la configurazione è stata completata correttamente e la connessione BGP è attiva, visualizzerai lo stato di **UP**.

![Passo 9 in corso](/images/Equinix-Step9-InProgress.png)

La seguente figura mostra i diversi stati della connessione dopo l'inserimento dell'ordine: 

![Passo 9 attivo](/images/Equinix-Step9-UP.png)

**Passo 4:**

Se la connessione è nello stato **Provisioned**, espandila facendo clic su **>** davanti al **Name** della connessione. Quindi prendi nota delle informazioni **Customer IP Address** e **Service Key**. Saranno necessarie per configurare il router edge del cliente e la chiave di autorizzazione per la configurazione (Equinix) lato provider cloud, rispettivamente.

![Passo 10](/images/Equinix-Step10-Provisioned.png)

**Passo 5:**

Per le connessioni nello stato **Provisioned**, dopo aver espanso la connessione facendo clic su **>** davanti alla connessione, visualizzerai un messaggio di errore se vi è una mancata corrispondenza con la velocità del link di peer. Una volta che la velocità è la stessa sul lato IBM e Equinix, questa notifica di errore non viene più visualizzata.

![Passo 11](/images/Equinix-Step11-PortMismatch.png)

**Passo 6:**

Per le connessioni nello stato **Create Failed**, viene generato un ticket di supporto IBM e vengono comunicati ulteriori dettagli tramite di esso. Quando espandi la connessione, puoi vedere i dettagli del ticket di supporto.

![Passo 12](/images/Equinix-Step12-CreateFailed.png)

**Passo 7:**

Per le connessioni nello stato **Provisioned**, **UP** o **DOWN**, puoi **Eliminare** la connessione facendo clic sulla colonna **ACTIONS** accanto ad essa.

![Passo 13](/images/Equinix-Step13-Delete.png)

**Passo 8:**

Per le connessioni nello stato **Create Failed**, puoi **Annullare** la connessione facendo clic sulla colonna **ACTIONS** accanto ad essa.

