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

Grazie per aver aperto una richiesta per IBM Cloud Direct Link Dedicated. Per finalizzare la tua richiesta, ci piacerebbe raccogliere alcune informazioni aggiuntive da te. Puoi parlare con un ingegnere in qualsiasi momento durante il processo del questionario. Una volta completato il questionario, verrà esaminato dal nostro team Cloud Design Engineering e inoltrato a Network Engineering per l'implementazione.

## Riconosci e accetti quanto segue?

1. Ogni connessione Direct Link richiede un ordine univoco. Se richiedi più connessioni, apri ordini Direct Link separati per ognuna di esse.

2. Gli addebiti per il tuo servizio Direct Link Connect coprono il costo della terminazione del servizio nell'infrastruttura IBM Cloud. 

 * I servizi dell'infrastruttura vengono fatturati in anticipo e iniziano con l'accettazione del tuo ordine; tuttavia a causa della natura di IBM Cloud Direct Link, la fatturazione del servizio Direct Link inizia all'avvio di una sessione BGP (Border Gateway Protocol) con IBM Cloud o 30 giorni dopo che la chiave del servizio viene fornita al client. 

 * La fatturazione si arresta dopo che:
   * Un cliente richiede che un circuito venga eliminato, **e** 
   * Che il provider Exchange o del servizio di rete abbia annullato il provisioning del circuito.
  * Per ulteriori informazioni, consulta la **Section 5 - Charges** in Cloud Services Agreement al seguente link: [ibm.biz/service-agreement](ibm.biz/service-agreement)

3. Ordinando il servizio Direct Link, sarai responsabile di tutte le tariffe associate al raggiungimento del PoP (Point of Presence) dalla tua rete remota e di tutte le connessioni trasversali necessarie nella struttura del PoP. Se il tuo provider richiede che un router o un altro dispositivo sia posizionato fisicamente nel PoP, sarai responsabile anche dei costi associati al posizionamento di tale apparecchiatura.

4. IBM Cloud non ordinerà una connessione trasversale al posto di un cliente.

5. IBM Cloud non co-posizionerà alcuna apparecchiatura del cliente nei nostri PoP di rete. Accettiamo solo ‘connessioni trasversali’ che sono un ethernet fiber (solo fibre a modalità singola, ottiche 1Gig-LX o 10Gig-LR 1310nm) eseguita dal tuo cage o provider. Non accettiamo T1s, DS3s, ISDN, POTs line, ecc. Dovrai collaborare con il tuo provider per determinare se devi collocare o meno le apparecchiature nella stessa struttura in cui si trova il PoP della rete di IBM Cloud. 

6. Il servizio Direct Link viene fornito in un modo in cui quando ti colleghi e il router di IBM Cloud viene terminato sono entrambi singoli punti di errore (SPOF). Se desideri ottenere la ridondanza tramite il servizio Direct Link, dovrai ordinare due connessioni in un'ubicazione Direct Link con un router secondario o terminare i link in due PoP di IBM Cloud separati.

7. La rete dei servizi IBM Cloud non sarà accessibile direttamente dalle tue reti remote. Se questa funzionalità viene modificata in futuro, ti verrà inviata una notifica. 

8. IBM Cloud non consentirà ai clienti il backhaul del traffico dei loro siti remoti tramite il backbone di IBM Cloud. Il prodotto Direct Link è destinato alle tue reti remote in modo che possano comunicare privatamente con l'infrastruttura IBM Cloud. 

9. Dopo aver confermato che il tuo circuito ha raggiunto il PoP ed è stato completato dal vettore, avrai bisogno di ordinare la connessione trasversale al XCR (cross connect router) di IBM Cloud che di solito impiega tra 2 e 10 giorni lavorativi per il completamento. Questa include la patch alla porta di terminazione SoftLayer.  Una volta completata, ti verrà richiesto di fornire a IBM Cloud l'avviso di completamento della connessione trasversale dalla struttura del fornitore. L'assegnazione dell'IP nell'infrastruttura di rete sarà completata in 3 giorni lavorativi dopo il completamento della connessione trasversale.

10. IBM Cloud Direct Link Dedicated richiede l'utilizzo di un'istanza VRF (Virtual Routing and Forwarding). Questo consente al cliente di definire i propri indirizzi IP remoti per l'utilizzo nella propria rete remota; tuttavia, devi essere consapevole che se utilizzi la rete 10.x.x.x non puoi ancora sovrapporre gli host in IBM Cloud né con la rete di servizi IBM Cloud (10.0.0.0/14, 10.198.0.0/15 e 10.200.0.0/14). La transizione del tuo account a una VRF richiede una breve interruzione della rete privata in quanto ciascuna VLAN viene migrata nella nuova configurazione. Il team Network Engineering lavorerà con te per definire una finestra per questa attività.

11. VRF non è compatibile con i servizi IBM Cloud (legacy SoftLayer) SSL, PPTP e IPSEC VPN. Un'alternativa è di utilizzare lo stesso Direct Link per la gestione dei tuoi server o di eseguire la tua soluzione VPN (come Vyatta) che può essere configurata con diversi tipi di VPN. Dopo aver eseguito la migrazione a una VRF, la VPN SSL normalmente funziona quando viene effettuata una connessione VPN alla stessa ubicazione DC del calcolo a cui si sta accedendo, ma non concede l'accesso globalmente.

12. IBM Cloud Direct Link Dedicated richiede BGP per poter implementare le rotte in una rete remota del cliente. Quando il tuo servizio Direct Link è stato distribuito, IBM Cloud annuncerà tutte le sottoreti private assegnate al tuo account. IBM Cloud non implementerà i filtri personalizzati, l'anteposizione del percorso AS e le preferenze di locale personalizzate agli avvisi al peer BGP remoto del cliente. IBM Cloud non implementerà i filtri sugli avvisi ricevuti da IBM Cloud.I clienti dovranno gestire correttamente gli avvisi a/da IBM Cloud dal router edge del cliente.

## Altre domande

* **In quale PoP vuoi terminare Direct Link?**

* **Quale velocità di collegamento ti serve (1, 2, 5 o 10Gbps)?**

* **Hai bisogno che BGP MultiPath con ECMP sia configurato per l'impostazione di una connessione ridondante a IBM Cloud?**  

    _Se sì, includi l'ID del ticket dell'altra connessione. Numero ticket ____________  (nota che ECMP può essere fornito solo su due sessioni nello stesso XCR IBM Cloud.  Se desideri ECMP, sappi che entrambi i Direct Link devono trovarsi sullo stesso router.)_

* **Hai bisogno dell'accesso all'instradamento globale o locale?**

    _I clienti che selezionano l'instradamento locale saranno in grado di passare solo il traffico tra i data center gestiti dal PoP in cui è stato ordinato Direct Link. I clienti che desiderano passare il traffico al di fuori del PoP in cui è stato ordinato il Direct Link dovranno aggiungere l'opzione dell'instradamento globale._

* **Accetti la tariffa per l'instradamento globale inclusa la tariffa mensile della _TUA UBICAZIONE_ e i costi aggiuntivi indicati di seguito?**

    _L'instradamento locale include l'accesso a tutti i data center collegati direttamente al PoP e fornisce traffico in entrata/uscita illimitato. L'instradamento globale espande l'accesso per includere tutti i data center di IBM Cloud globalmente. La larghezza di banda viene misurata quando il servizio può misurare il traffico. Quando la larghezza di banda viene misurata, ti verrà addebitata mensilmente in base al prezzo di mercato, come mostrato nella seguente tabella._


### Prezzo dell'instradamento globale

| Instradamento globale in entrata | Instradamento globale in uscita |
|---|---|
| Gratuito | Circuito a 1, 2 o 5Gbps - 10TB gratuiti di larghezza di banda |
| Gratuito | Circuito a 10Gbps - 50TB gratuiti di larghezza di banda |


| Costi aggiuntivi della larghezza di banda |
|---|
| Market 1: $0.05 per GB |
| Market 2: $0.10 per GB |
| Market 3: $0.15 per GB |
