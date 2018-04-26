---

copyright:
 years: 2017, 2018
lastupdated: "2018-04-05"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# FAQ

Questa sezione contiene le risposte ad alcune domande frequenti su IBM Cloud Direct Link. 

## Come funziona IBM Cloud Direct Link?
Per ogni cliente Direct Link, il team di IBM Cloud assegna una piccola sottorete privata per creare una rete point-to-point tra il XCR (cross-connect router) {{site.data.keyword.BluSoftlayer_notm}} cross-connect router (XCR) e il CER (customer's edge router). Quindi, {{site.data.keyword.BluSoftlayer_notm}} e il cliente configurano BGP per poter scambiare le rotte tra gli ambienti. Infine, {{site.data.keyword.BluSoftlayer_notm}} inserisce il cliente in un VRF per consentire l'implementazione di rotte non univoche allo spazio di indirizzo privato della rete remota del cliente.

## IBM Cloud misura la banda dei prodotti Direct Link?
Sì. IBM Cloud misura tutta la banda in uscita dei prodotti Direct Link. La banda in entrata è gratuita e non misurata.

## Quali costi addizionali avrò da altre parti con Direct Link?
Potresti avere costi addizionali dal tuo provider di scambio o di servizio di rete. Fai riferimento ai tuoi provider per informazioni sulle loro tariffe.

## Posso archiviare la ridondanza con IBM Cloud Direct Link?
Puoi archiviare la ridondanza con Direct Link collegando più di un provider IBM Cloud Direct Link Dedicato o Exchange {{site.data.keyword.BluSoftlayer_notm}}. In alternativa, puoi utilizzare uno dei provider IBM Cloud Direct Link che aggiunge la ridondanza al tuo servizio. 

## Qual'è la differenza tra la rotta "locale" predefinita e il componente aggiuntivo di instradamento globale?
Con l'offerta Direct Link standard, puoi inviare il traffico tra i data center nella tua regione selezionata. Se hai bisogno di accedere ad altri data center al di fuori della regione specificata, devi ordinare il componente aggiuntivo di instradamento globale. Questo modello si basa su ACL (access control list) messi in atto nel momento in cui viene ordinata la tua connessione Direct Link. 

## Come i costi aggiuntivi della banda in uscita vengono fatturati dal componente aggiuntivo di instradamento globale?
I costi aggiuntivi vengono fatturati mensilmente quando viene superata la quota assegnata di banda, ma solo per la banda in uscita. La banda in entrata è gratuita e non misurata. La banda in uscita viene fatturata in base alla frequenza maggiore tra le due regioni tra cui vengono trasmessi i tuoi dati.  Ad esempio, se il tuo Direct Link è configurato in DAL03 e il tuo traffico dati passa tramite il Messico, ti sarà addebitata la frequenza di banda del Messico.

## Perché esiste un pacchetto del componente aggiuntivo di instradamento globale?
Abbiamo aggiunto il componente di instradamento globale per evitare che i nostri clienti riscontrino costi di dati non previsti durante la trasmissione al di fuori della loro regione del data center. Mantiene i costi più bassi per la maggior parte dei nostri clienti e fornisce la possibilità, ai clienti con una presenza globale, di raggiungere tutte le regioni nel mondo in modo più facile. Di solito, tuttavia, un cliente richiede solo un pacchetto di banda locale.

## Cosa sono le opzioni di instradamento locale e globale?
Le opzioni di instradamento locale e globale vengono selezionate per ogni cliente quando ordina il servizio Direct Link. Se i clienti necessitano di instradare il traffico al di fuori del POP nell'area in cui hanno ordinato Direct Link, devono aggiungere l'opzione di instradamento globale; altrimenti il loro traffico viene limitato ai servizi forniti dal POP locale.

Ogni mese, a tutti i clienti che utilizzano 1G di circuiti vengono assegnati 10TB di traffico in uscita gratuito; ai clienti che utilizzano 10G di circuiti vengono assegnati 50TB. I costi aggiuntivi si basano sulla seguente tabella, con il tasso di mercato più elevato prevalente. Se selezioni l'instradamento globale, non ti viene addebitato tutto il traffico in uscita locale, soltanto il traffico originato o terminato al di fuori del POP locale.

|Mercato dati 1|Mercato dati 2|Mercato dati 3|
|---|---|---|
|<ul><li>DAL</li><li>WDC</li><li>SEA</li><li>SJC</li><li>NYC*</li><li>CHI*</li><li>DEN*</li><li>MIA*</li><li>ATL*</li><li>LAX*</li><li>TOR</li><li>MON</li><li>AMS</li><li>FRA</li></ul>|<ul><li>TOK</li><li>HKG</li><li>PAR</li><li>MIL</li><li>STK*</li><li>OSL</li></ul>|<ul><li>MEX</li><li>SAO</li><li>SYD</li><li>MEL</li><li>PER*</li><li>CHE</li><li>SEO</li></ul>|
**Tabella 1: livelli di utilizzo**<br/>
L'offerta Direct Link nei mercanti contrassegnati con un asterisco (*) DEVE ordinare l'instradamento globale.

## Se sono collegato a un Direct Link NSP o un Direct Link Cloud Exchange in una regione come Dallas, ho accesso ad altre regioni negli Stati Uniti tramite Direct Link?
Sì, sei in grado di accedere alle aree al di fuori della tua regione se scegli il componente aggiuntivo di instradamento globale. se questa opzione non viene selezionata, il tuo traffico Direct Link sarà limitato alla regione del POP che hai selezionato.

## Posso collegarmi a qualsiasi regione disponibile da un'ubicazione Direct Link selezionata?
Sì, se hai ordinato Direct Link con il componente aggiuntivo di instradamento globale.

## Posso limitare le regioni che il mio Direct Link può raggiungere?
No. IBM Cloud offre due opzioni: (1) solo una regione singola o (2) tutte le regioni, con il componente aggiuntivo di instradamento globale.

## Se ho usato il processo di ordine automatizzato di Equinix Cloud Exchange e mi è stata assegnata un sottorete che si sovrappone alla mia rete interna? 

A partire da marzo 2018, la procedura consigliata è di annullare l'ordine automatizzato ed inviare un nuovo ticket per compilare il questionario di Direct Link. Devi indicare se preferisci un'altra sottorete nell'intervallo 10.254.x.x o 172.32.x.x.

## Qual è la differenza tra Direct Link Exchange e Direct Link Connect?

Questi due servizi sono simili, relativamente a basso costo, tolleranti alla latenza e punti di ingresso rapidi ai vantaggi di IBM Cloud Direct Link. In sintesi, Exchange utilizza provider di data center e Connect utilizza vettori Telco. Ecco alcuni ulteriori dettagli: 

**Direct Link Exchange** è per i clienti che preferiscono utilizzare uno scambio all'interno di un data center. Con un servizio Exchange, i clienti possono abilitare la connettività a più cloud per la loro ubicazione velocemente, perché i circuiti sottostanti vengono già forniti (questi altri provider cloud devono già avere un'interconnessione fisica presente nella struttura).

Direct Link Exchange può consentire un ambiente di utilizzo condiviso, con più cloud tramite una sola porta di scambio cloud, creato da una connessione NNI al livello 2 tra IBM Cloud e il provider di servizi Cloud Exchange. Le velocità della porta sono disponibili fino a 1Gb. 

**Direct Link Connect** è per i clienti che preferiscono utilizzare la propria rete esistente tra loro propria distribuzione in loco e IBM Cloud. Con un servizio Direct Link Connect, i clienti possono utilizzare reti Telco nuove e esistenti (come MPLS) per abilitare IBM Cloud rapidamente, utilizzando circuiti sottostanti preforniti. 

Con Direct Link Connect, sia IBM che il partner si collegheranno al cliente al livello 2 e 3 tramite Layer-2 10G Network-to-Network Interfaces (NNIs) duali, gestite dai partner IBM nelle strutture in tutto il mondo. Le velocità della porta sono disponibili fino a 5Gb. 

