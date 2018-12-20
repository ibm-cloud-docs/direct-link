---

copyright:
  years: 2017, 2018
lastupdated: "2018-11-13"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}
{: faq: data-hd-content-type=‘faq’}

# FAQ

Questa sezione contiene le risposte ad alcune domande frequenti su IBM Cloud Direct Link. 

## Come funziona IBM Cloud Direct Link?
{: faq}

Per ogni cliente Direct Link, il team di IBM Cloud assegna una piccola sottorete privata per creare una rete point-to-point tra il XCR (cross-connect router) {{site.data.keyword.BluSoftlayer_notm}} cross-connect router (XCR) e il CER (customer's edge router). Quindi, {{site.data.keyword.BluSoftlayer_notm}} e il cliente configurano BGP per poter scambiare le rotte tra gli ambienti. Infine, {{site.data.keyword.BluSoftlayer_notm}} inserisce il cliente in un VRF per consentire l'implementazione di rotte non univoche allo spazio di indirizzo privato della rete remota del cliente.

## IBM Cloud misura la banda dei prodotti Direct Link?
{: faq}

Sì. L'utilizzo della larghezza di banda attraverso il servizio Direct Link tra i clienti e IBM Cloud è gratuito e non misurato, IBM Cloud misura la larghezza di banda in uscita dai servizi IBM Cloud a internet pubblico.

## Quando inizia la fatturazione con Direct Link?
{: faq}

Gli addebiti per Direct Link Connect coprono il costo della terminazione del servizio nell'infrastruttura IBM Cloud. 

I servizi dell'infrastruttura vengono fatturati in anticipo e iniziano con l'accettazione dell'ordine del nostro cliente; tuttavia, a causa della natura di IBM Cloud Direct Link, la fatturazione del servizio Direct Link inizia quando viene stabilita una sessione BGP (Border Gateway Protocol) con IBM Cloud o 30 giorni dopo che la chiave del servizio viene fornita al client. 

La fatturazione si arresta dopo che (1) un cliente richiede che un circuito venga eliminato E (2) che il provider Connect o del servizio di rete abbia annullato il provisioning del circuito.

## Quali costi addizionali avrò da altre parti con Direct Link?
{: faq}

Potresti avere costi addizionali dal tuo provider di scambio o di servizio di rete. Fai riferimento ai tuoi provider per informazioni sulle loro tariffe.

## Posso archiviare la ridondanza con IBM Cloud Direct Link?
{: faq}

Il Direct Link non fornisce un servizio intrinsecamente ridondante. Direct Link può fornire connessioni diverse, che consentono ai clienti di creare la ridondanza tramite BGP. Puoi archiviare la diversità con Direct Link collegando più di un provider IBM Cloud Direct Link Dedicated o Exchange per {{site.data.keyword.BluSoftlayer_notm}}. In alternativa, con Exchange e Connect puoi utilizzare diverse NNI con i provider di IBM Cloud Direct Link.

## Qual è la differenza tra l'instradamento "locale" predefinito e il componente aggiuntivo di instradamento globale per Direct Link?
{: faq}

Con l'offerta Direct Link standard, puoi inviare il traffico tra i data center nella tua regione selezionata. Se hai bisogno di accedere ad altri data center al di fuori della regione specificata, devi ordinare il componente aggiuntivo di instradamento globale. Questo modello si basa su ACL (access control list) messi in atto nel momento in cui viene ordinata la tua connessione Direct Link. 

## Come vengono fatturate le eccedenze della larghezza di banda in uscita dal componente aggiuntivo di instradamento globale in Direct Link?
{: faq}

Le eccedenze vengono fatturate mensilmente quando viene superata la quota assegnata di larghezza di banda, ma solo per la larghezza di banda in uscita. La larghezza di banda in entrata è gratuita e non misurata. La larghezza di banda in uscita viene fatturata in base alla frequenza maggiore tra le due regioni attraversate dai tuoi dati. Ad esempio, se il tuo Direct Link è configurato in DAL03 e il tuo traffico dati passa tramite il Messico, ti sarà addebitata la frequenza di banda del Messico.

## Perché esiste un pacchetto del componente aggiuntivo di instradamento globale per Direct Link?
{: faq}

Abbiamo aggiunto il componente di instradamento globale per evitare che i nostri clienti riscontrino costi di dati non previsti durante la trasmissione al di fuori della loro regione del data center. Mantiene i costi più bassi per la maggior parte dei nostri clienti e fornisce la possibilità, ai clienti con una presenza globale, di raggiungere tutte le regioni nel mondo in modo più facile. Di solito, tuttavia, un cliente richiede solo un pacchetto di banda locale.

## Se sono collegato a un Direct Link Dedicated, Direct Link Connect o Direct Link Exchange in una regione come Dallas, ho accesso ad altre regioni negli Stati Uniti tramite Direct Link?
{: faq}

Sì, sei in grado di accedere alle aree al di fuori della tua regione se scegli il componente aggiuntivo di instradamento globale. Se questa opzione non viene selezionata, il tuo traffico Direct Link sarà limitato alla regione dell'ubicazione PoP che hai selezionato. Per i dettagli, fai riferimento al [documento dei prezzi](pricing.html).

## Posso collegarmi a qualsiasi regione disponibile da un'ubicazione Direct Link selezionata?
{: faq}

Sì, se hai ordinato Direct Link con il componente aggiuntivo di instradamento globale.

## Posso limitare le regioni che il mio Direct Link può raggiungere?
{: faq}

No. IBM Cloud offre due opzioni: (1) solo una regione singola o (2) tutte le regioni, con il componente aggiuntivo di instradamento globale.

## Che succede se ho usato il processo di ordine automatizzato Direct Link per Equinix Cloud Exchange e mi è stata assegnata una sottorete che si sovrappone alla mia rete interna?
{: faq}

A partire da marzo 2018, la procedura consigliata è di annullare l'ordine automatizzato ed inviare un nuovo ticket per compilare il questionario di Direct Link. Devi indicare se preferisci un'altra sottorete nell'intervallo 10.254.x.x o 172.32.x.x.

## Qual è la differenza tra Direct Link Exchange e Direct Link Connect?
{: faq}

Questi due servizi sono simili, relativamente a basso costo, tolleranti alla latenza e punti di ingresso rapidi ai vantaggi di IBM Cloud Direct Link. In sintesi, Exchange utilizza provider di data center e Connect utilizza vettori Telco. Ecco alcuni ulteriori dettagli:

**Direct Link Exchange** è consigliato ai clienti che preferiscono utilizzare uno scambio all'interno di un data center. Con un servizio Exchange, i clienti possono abilitare la connettività a più cloud per la loro co-ubicazione velocemente, perché i circuiti sottostanti vengono già forniti (questi altri provider cloud devono già avere un'interconnessione fisica presente nella struttura).

Direct Link Exchange può consentire un ambiente di utilizzo condiviso, con più cloud tramite una sola porta di scambio cloud, creato da una connessione NNI (network-to-network) al livello 2 tra IBM Cloud e il provider di servizi Cloud Exchange. Le velocità della porta sono disponibili fino a 1Gb.

**Direct Link Connect** è per i clienti che preferiscono utilizzare la propria rete esistente tra loro propria distribuzione in loco e IBM Cloud. Con un servizio Direct Link Connect, i clienti possono utilizzare reti Telco nuove e esistenti (come MPLS) per abilitare IBM Cloud rapidamente, utilizzando circuiti sottostanti preforniti.

Con Direct Link Connect, i clienti possono collegarsi a IBM Cloud tramite il provider Connect, su una connessione NNI (Network to Network), dai partner IBM nelle strutture in tutto il mondo. Le velocità della porta sono disponibili fino a 5Gb.

## Come confrontare i provider Direct Link Connect e Direct Link Exchange?
{: faq}

I provider Connect sono Telco che hanno una copertura di rete oltre il datacenter. I provider Exchange sono limitati ai loro datacenter. Entrambi possono abilitare l'esperienza multi cloud per i clienti. I provider Exchange di solito richiedono la condivisione del percorso nei loro datacenter, mentre i provider Connect possono raggiungere il sito e i datacenter di un cliente in loco.

## IBM può supportare IPv6 su Direct Link?
{: faq}

Non per la sessione BGP. Dobbiamo assegnare il nostro /30 da IPv4 e abbiamo bisogno della stessa cosa in cambio dal cliente.

## IBM può eseguire IPV6 sulla rete privata?
{: faq}

No. IPv6 è solo pubblico.

## Ci sono dei requisiti speciali Direct Link per Verizon SCI? Prefisso / ASN / VLAN BGP / e così via?
{: faq}

Verizon SCI è uno dei diversi servizi basati su MPLS, Layer-3 (IP VPN). Richiede che IBM stabilisca BGP con Verizon invece che direttamente con il cliente. Verizon quindi stabilisce BGP con il cliente e annuncia le rotte di conseguenza. Molti altri fornitori di servizi basati su Layer-3 partecipano al programma Direct Link Connect. I clienti devono essere consapevoli di ciò che stanno ordinando e di come il loro account si comporterà quando si collegano a IBM Cloud.

## Direct Link supporta un qualsiasi tipo di QoS?
{: faq}

Non siamo in grado di supportare le garanzie QoS. QoS richiede l'associazione MPLS tra ognuno dei nostri fornitori di servizi e IBM Cloud. I provider dei servizi cloud generalmente non possono supportare QoS in questo momento, perché deve essere raggiunto tramite end-to-end e coinvolgere tutti i dispositivi nel mezzo. Non esiste una soluzione temporanea disponibile mediante "tunneling" o un qualsiasi altro metodo.

## Direct Link supporta i frame Jumbo?
{: faq}

I frame Jumbo (fino a 9214 byte) sono supportati su Dedicated e Dedicated Hosting. 
Il supporto per Connect e Exchange è teoricamente possibile, ma richiede che il tuo provider di servizi funzioni con IBM e che garantisca che la connessione end-to-end supporti i frame Jumbo, inclusa la NNI (Network-to Network-Interface) sottostante.
Per impostazione predefinita, Exchange e Connect sono impostati con il supporto MTU a 1500 byte.

## Con Direct Link Connect come fa un cliente a garantire la diversità del router attraverso lo stesso vettore (esempio: Verizon in DAL03)?
{: faq}

Abbiamo diverse XCR che creano link NNI diversi al vettore. È compito del vettore mantenere la diversità da quel punto.

## Per Direct Link Connect un cliente deve ordinare 2 link per la ridondanza oppure la ridondanza di Direct Link Connect è intrinsecamente ridondante?
{: faq}

Ordina 2 link per la diversità. Non offriamo la ridondanza tra gli switch o i router. I clienti creano la ridondanza con le loro configurazioni BGP su ogni Direct Link.

## Quanto è facile eseguire l'upgrade della larghezza di banda della mia connessione Direct Link, ad esempio da 1GB a 5GB?
{: faq}

Normalmente, installiamo le velocità di 1G e inferiore sulle ottiche 1G. Per le velocità da 2G a 10G, installiamo le ottiche 10G. Pertanto, l'aggiornamento da 1G a 5G richiederebbe l'assegnazione o l'inserimento di nuove ottiche. Si tratta di un evento che interessa il servizio. Se prevedi una tale crescita, è possibile richiedere l'installazione di fibre ottiche 10G all'inizio della tua distribuzione di Direct Link o di ordinare inizialmente 2G in modo che siano implementate le ottiche 10G.

## ECMP è la soluzione per le connessioni Direct Link ridondanti? Quali alternative esistono?
{: faq}

Nota che ECMP non è pensato per la creazione di connessioni ridondanti ma per il bilanciamento del carico su due link. Con ECMP, entrambe le connessioni devono terminare con lo stesso XCR (cross-connect router) IBM Cloud, il che lo rende un singolo punto di errore. (In altre parole, ECMP può essere fornito solo come due sessioni nello stesso XCR IBM Cloud.) 

ECMP è una funzione di BGP. Se stai cercando la ridondanza, ottieni due connessioni Direct Link, una in ogni XCR. Se vuoi utilizzare ECMP e disponi della ridondanza, avrai bisogno di due connessioni Direct Link in ogni XCR, in modo che tu possa avere 2 sessioni ECMP simultaneamente.

In alternativa, alcuni dei nostri clienti hanno impostato due link in XCR differenti nello stesso data center, ad esempio WDC02, e viene quindi eseguito il failover come necessario utilizzando le configurazioni BGP. Questa configurazione è meno ridondante (meno sicura) rispetto alle connessioni Direct Link in due data center separati, come ad esempio WDC02 e WDC05.

## Esiste uno SLA nelle connessioni XCR Direct Link fino alla connessione BCR dell'account?
{: faq}

Non c'è nessun SLA su Direct Link al momento. I clienti possono raggiungere il 99,999% in modo efficace con 2 o più Direct Link correttamente configurati per il failover utilizzando BGP, ma IBM non può controllarlo o fornire uno SLA su di esso.

## Dove posso trovare supporto per la configurazione di un Direct Link?
{: faq}

Per la connessione a Direct Link, vedi [Configura {{site.data.keyword.cloud_notm}} Direct Link](../../docs/infrastructure/direct-link/subnet-configuration.html#configure-ibm-cloud-direct-link). Se hai bisogno di più aiuto, puoi richiedere il supporto ingegneristico nel ticket che era stato aperto per il nuovo servizio. Anche se si tratta di un servizio API con Equinix, l'apertura di un ticket abiliterà l'ingegnere a verificarlo. In alternativa, puoi contattare il tuo rappresentante delle vendite IBM.

## Su Direct Link Exchange, IBM imposta una password BGP?
{: faq}

Non impostiamo alcuna password BGP per Direct Link Exchange per impostazione predefinita. È disponibile un'opzione per specificare BGP ASN e assegniamo indirizzi IP BGP. È inoltre possibile configurare una password BGP per finalità di autenticazione; basta informare gli ingegneri della cosa.
