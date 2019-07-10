---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-02"

keywords: Exchange, finalize, questionnaire, Special Network Services, billing, fees, VRF, BGP, ticket, ASN, VPN, metering, data, center, datacenter

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Questionari su IBM Cloud Direct Link Exchange
{: #ibm-cloud-direct-link-exchange-questionnaire}

Grazie per aver aperto una richiesta per {{site.data.keyword.cloud}} Direct Link Exchange. Per finalizzare la tua richiesta, ci piacerebbe raccogliere alcune informazioni aggiuntive da te. Puoi parlare con un ingegnere in qualsiasi momento durante il processo del questionario. Dopo che lo avrai completato, il questionario verrà esaminato dal nostro team Cloud Design Engineering e fatto arrivare a Special Network Services per l'implementazione.

## Riconosci e accetti quanto segue?
{: #exchange-do-you-agree}

1. Ogni connessione Direct Link richiede un ordine univoco. Se richiedi più connessioni, apri ordini Direct Link separati per ognuna di esse.

2. Gli addebiti per il tuo servizio Direct Link Exchange coprono il costo della terminazione del servizio nell'infrastruttura IBM Cloud. 

 * I servizi dell'infrastruttura vengono fatturati in anticipo e iniziano con l'accettazione del tuo ordine; tuttavia a causa della natura di IBM Cloud Direct Link, la fatturazione del servizio Direct Link inizia all'avvio di una sessione BGP (Border Gateway Protocol) con IBM Cloud o 30 giorni dopo che la chiave del servizio viene fornita al client. 

 * La fatturazione si arresta dopo che:
   * Un cliente richiede che un circuito venga eliminato, **e** 
   * Che il provider Exchange o del servizio di rete abbia annullato il provisioning del circuito.
  * Per ulteriori informazioni, consulta la **Section 5 - Charges** in Cloud Services Agreement al seguente link: [https://www.ibm.com/support/customer/zz/en/selectcountrylang.html](https://www.ibm.com/support/customer/zz/en/selectcountrylang.html). Ad esempio, i clienti negli Stai Uniti visualizzerebbero [questo documento di contratto di Cloud Services](https://www.ibm.com/support/customer/csol/contractexplorer/cloud/csa/us-en).
  * In alternativa, la fatturazione può arrestarsi se un cliente riceve una notifica che il proprio servizio Direct Link sarà disattivato e non funzionerà più.

3. Ordinando il servizio Direct Link, sarai responsabile di tutte le tariffe associate al raggiungimento del PoP (Point of Presence) dalla tua rete remota e di tutte le connessioni trasversali necessarie nella struttura del PoP per raggiungere il tuo provider di scambio. Tu (o il tuo provider) sarai inoltre responsabile dell'acquisto del circuito virtuale per IBM Cloud. Se il tuo provider richiede che un router o un altro dispositivo sia posizionato fisicamente nel PoP, sarai responsabile anche dei costi associati al posizionamento di tale apparecchiatura. Conferma che il tuo provider di rete o PoP possa raggiungere Direct Link Exchange e pagare i costi associati.

4. IBM Cloud non posizionerà alcuna apparecchiatura del cliente nei nostri PoP di rete. Dovrai collaborare con il tuo provider per determinare se devi collocare o meno le apparecchiature nella stessa struttura in cui si trova il PoP di IBM Cloud.

5. Il servizio Direct Link Exchange viene fornito in un modo in cui il tuo link e il router IBM Cloud possono essere terminati poiché sono entrambi singoli punti di errore (SPOF). Se desideri ottenere la ridondanza tramite il servizio Direct Link Exchange, dovrai terminare i link in due PoP di rete IBM Cloud separati o ordinare due connessioni in un'ubicazione Direct Link Exchange con un router secondario.

6. La rete dei servizi IBM Cloud non sarà accessibile direttamente dalle tue reti remote. Se queste modifiche saranno apportate in futuro, ti verrà inviata una notifica.

7. IBM Cloud non consentirà ai clienti il backhaul del traffico dei loro siti remoti tramite il backbone di IBM Cloud. Il prodotto Direct Link Exchange è destinato alle tue reti remote in modo che possano comunicare privatamente con l'infrastruttura IBM Cloud.

8. Dopo che hai confermato che il tuo circuito ha raggiunto il PoP di Direct Link Exchange, dovrai effettuare un ordine con il tuo provider cloud exchange e fornire tutte le informazioni rilevanti al provider e a IBM Cloud. Per i provider Equinix, il tempo di distribuzione tipico può essere di ore. Il tempo di distribuzione tipico per l'offerta IBM Cloud Direct Link Exchange richiede 5-10 giorni per il completamento. 

9. IBM Cloud Direct Link Exchange richiede l'utilizzo di un'istanza VRF (Virtual Routing and Forwarding) nel lato della rete di IBM Cloud.  Questo consente al cliente di definire i propri indirizzi IP remoti per l'utilizzo nella propria rete remota; tuttavia, devi essere consapevole che se sei in grado di utilizzare la rete 10.x.x.x, non puoi ancora sovrapporre gli host in IBM Cloud né con la rete di servizi IBM Cloud (10.0.0.0/14, 10.198.0.0/15 e 10.200.0.0/14). La transizione del tuo account a una VRF richiede una breve interruzione della rete privata in quanto ciascuna VLAN viene migrata nella nuova configurazione.  Il team Special Network Services lavorerà con te per definire una finestra per questa attività. Il team Special Network Services è normalmente disponibile dal lunedì al venerdì, dalle 8 alle 17 CST (Ora solare fuso centrale USA). Qualsiasi attività di attivazione non rientrante in questa finestra dovrà essere richiesta mediante un ticket e approvata in anticipo, se gli ingegneri sono disponibili. 

10. VRF non è compatibile con i servizi IBM Cloud SSL, PPTP e IPSEC VPN.  Un'alternativa è di utilizzare lo stesso Direct Link per la gestione dei tuoi server o di eseguire la tua soluzione VPN (come Vyatta) che può essere configurata con diversi tipi di VPN. Dopo aver eseguito la migrazione a una VRF, la VPN SSL normalmente funziona quando viene effettuata una connessione VPN alla stessa ubicazione DC del calcolo a cui si sta accedendo, ma non concede l'accesso globalmente.

11. IBM Cloud Direct Link Exchange richiede BGP per poter implementare le rotte in una rete remota del cliente.Quando il tuo servizio Direct Link è stato distribuito, IBM Cloud annuncerà tutte le sottoreti private assegnate al tuo account.IBM Cloud non implementerà i filtri personalizzati, l'anteposizione del percorso AS e le preferenze di locale personalizzate agli avvisi al peer BGP remoto del cliente.IBM Cloud non implementerà i filtri sugli avvisi ricevuti da IBM Cloud.I clienti dovranno gestire correttamente gli avvisi a/da IBM Cloud dal router edge del cliente.

## Altre domande
{: #exchange-other-questions}

* **Riconosci e accetti i prezzi della _TUA UBICAZIONE_ per la connessione IBM Cloud Direct Link Exchange?**

* **IBM Cloud ti assegnerà un ASN privato per scopi di configurazione di BGP per annunciare le tue reti remote alla tue rete privata di IBM Cloud. È accettabile o preferiresti utilizzare il tuo ASN pubblico?**

* **Hai bisogno che BGP MultiPath con ECMP sia configurato per l'impostazione di una connessione ridondante a IBM Cloud?**  

    _Se sì, includi l'ID del ticket dell'altra connessione. Numero ticket ____________  (nota che ECMP può essere fornito solo su due sessioni nello stesso XCR IBM Cloud.  Se desideri ECMP, sappi che entrambi i Direct Link devono trovarsi sullo stesso router.)_

* **Hai bisogno dell'accesso all'instradamento globale o locale?**

    _I clienti che selezionano l'instradamento locale saranno in grado di passare solo il traffico tra i data center gestiti dal PoP in cui è stato ordinato Direct Link. I clienti che desiderano passare il traffico al di fuori del PoP in cui è stato ordinato il Direct Link dovranno aggiungere l'opzione dell'instradamento globale._

* **Accetti la tariffa per l'instradamento globale inclusa la tariffa mensile della _TUA UBICAZIONE_ e i costi aggiuntivi indicati di seguito?**

    _L'instradamento locale include l'accesso a tutti i data center collegati direttamente al PoP e fornisce traffico in entrata/uscita illimitato. L'instradamento globale espande l'accesso per includere tutti i data center di IBM Cloud globalmente. La larghezza di banda viene misurata quando il servizio può misurare il traffico. Quando la larghezza di banda viene misurata, ti verrà addebitata mensilmente in base al prezzo di mercato, come mostrato nella seguente tabella._


### Prezzo dell'instradamento globale
{: #exchange-global-routing-pricing}

| Instradamento globale in entrata | Instradamento globale in uscita |
|---|---|
| Gratuito | Circuito a 1, 2 o 5Gbps - 10TB gratuiti di larghezza di banda |
| Gratuito | Circuito a 10Gbps - 50TB gratuiti di larghezza di banda |


| Costi aggiuntivi della larghezza di banda |
|---|
| Market 1: $0.05 per GB |
| Market 2: $0.10 per GB |
| Market 3: $0.15 per GB |
