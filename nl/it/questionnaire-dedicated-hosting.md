---

copyright:
  years: 2018
lastupdated: "2018-06-11"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Questionari su IBM Cloud Direct Link Dedicated

Grazie per aver aperto una richiesta per IBM Cloud Direct Link Dedicated Hosting.  Per finalizzare la tua richiesta, ci piacerebbe raccogliere alcune informazioni aggiuntive da te. Puoi parlare con un ingegnere in qualsiasi momento durante il processo del questionario. Una volta completato il questionario, verrà esaminato dal nostro team Cloud Design Engineering e inoltrato a Network Engineering per l'implementazione.

## Riconoscimenti

1. Le tariffe descritte in questo questionario coprono il costo della terminazione del servizio nell'infrastruttura della rete IBM Cloud. I costi di collocamento, inclusi i cabinet, le connessioni trasversali, ecc. includono tariffe non ricorrenti e mensili che sono descritte separatamente come parte di un contratto di posizionamento.

2. IBM Cloud Direct Link Dedicated Hosting fornisce connessioni trasversali in fibra 1Gbps o 10Gbps nella rete privata di IBM Cloud. Dovrai fornire un router o uno switch Layer 3 che può supportare gli uplink SMF (single mode fiber). Il tempo di distribuzione può variare in base al tuo provider del circuito, il tempo di distribuzione tipico per questo servizio è 30-60 giorni.

3. Direct Link Dedicated Hosting richiede l'utilizzo di un'istanza VRF (Virtual Routing and Forwarding).  Questo consente al cliente di definire i propri indirizzi IP remoti per l'utilizzo nella propria rete remota; tuttavia, devi essere consapevole che se utilizzi la rete 10.x.x.x non puoi ancora sovrapporre gli host in IBM Cloud né con la rete di servizi SIBM Cloud (10.0.0.0/14, 10.198.0.0/15 e 10.200.0.0/14). La transizione del tuo account a una VRF richiede una breve interruzione della rete privata in quanto ciascuna VLAN viene migrata nella nuova configurazione. Il team Network Engineering lavorerà con te per definire una finestra per questa attività.

4. VRF modifica il comportamento di IBM Cloud SSL, PPTP e IPsec VPN. Questo normalmente funziona quando la connessione VPN viene effettuata alla stessa ubicazione del data center delle risorse di calcolo a cui si sta eseguendo l'accesso, ma che non consentono l'accesso globalmente.  Come alternativa, puoi utilizzare lo stesso Direct Link per la gestione dei tuoi server o di eseguire la tua soluzione VPN (come Vyatta) che può essere configurata con diversi tipi di VPN. 

5. Direct Link Dedicated Hosting richiede BGP per poter implementare le rotte in una rete remota del cliente.  IBM Cloud non implementerà i filtri sugli avvisi effettuati da IBM Cloud. IBM Cloud annuncerà tutte le sottoreti private assegnate al tuo account. I clienti dovranno gestire correttamente gli annunci ricevuti da IBM Cloud.

6. IBM Cloud fornisce uplink duali, uno per ogni router di connessione trasversale di IBM Cloud, per consentire ai clienti di stabilire la connettività ridondante. Questa operazione viene eseguita sul router o sui router del cliente utilizzando le funzionalità ECMP o semplicemente pesando le connessioni.

7. La rete dei servizi IBM Cloud non sarà accessibile direttamente dal tuo Dedicated Hosting o dalle tue reti remote.

8. IBM Cloud non ti consentirà il backhaul del traffico dei tuoi siti remoti tramite il backbone di IBM Cloud. Il servizio Direct Link è progettato per le tue reti remote in modo che possano comunicare privatamente con l'infrastruttura IBM Cloud.

9. IBM Cloud offre Direct Link con l'instradamento locale o globale. Conferma di quale pacchetto di instradamento hai bisogno e che accetti i piani della larghezza di banda associati a tali pacchetti elencati al seguente link: ibm.biz/DirectLink-Docs.

10. Specifica la quantità di traffico che vuoi distribuire tramite il tuo Direct Link e a quale data center di IBM Cloud hai pianificato di eseguire il push di questo traffico.

11. Se non stai acquistando servizi di co-ubicazione tramite IBM Cloud, sarai responsabile dell'ordine e del pagamento delle connessioni trasversali tra il tuo ambiente e IBM Cloud. Una volta collegato, forniremo una LOA (Letter of Authorization) che descrive la nostra approvazione della tua connessione e dell'ubicazione a cui devi collegarti.

12. Conferma di accettare i seguenti prezzi per Direct Link:
 * 1Gbps: _UBICAZIONE BASATA SUL PREZZO_ 
* 2Gbps: _UBICAZIONE BASATA SUL PREZZO_
* 5Gbps: _UBICAZIONE BASATA SUL PREZZO_
* 10Gbps: _UBICAZIONE BASATA SUL PREZZO_
* Instradamento globale facoltativo
