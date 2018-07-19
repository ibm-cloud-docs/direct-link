---

copyright:
  years: 2018
lastupdated: "2018-04-24"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Insieme: IBM Cloud Direct Link e IBM Cloud Object Storage

Questo documento descrive come configurare IBM Cloud Direct Link in modo da avere accesso a IBM Cloud Object Storage e ad altri servizi IBM Cloud. Esistono molti metodi per il collegamento dalla rete IBM Cloud IaaS, su cui si trova IBM Cloud Direct Link, alla rete “pubblica” che supporta le funzionalità IBM Cloud PaaS e SaaS, senza realmente lasciare il backbone IaaS.

Con la politica corrente, gli endpoint del servizio privato IBM Cloud non sono accessibili tramite IBM Cloud Direct Link. Le tecniche descritte in questo documento si basano sull'accesso indiretto tramite i sistemi ospitati da IBM Cloud. Mentre gli endpoint del servizio privato non sono accessibili tramite Direct Link, le applicazioni e i server privati del cliente possono diventare raggiungibili.

## Che cos'è IBM Cloud Object Storage (COS)?

IBM Cloud Object Storage è una piattaforma su scala web che archivia i dati non strutturati. Fornisce affidabilità, sicurezza, disponibilità e ripristino di emergenza senza replica. 

Le informazioni archiviate con IBM Cloud Object Storage vengono crittografate e distribuite in più ubicazioni geografiche. Sono accessibili tramite un'implementazione dell'API S3. Questo servizio utilizza le tecnologie di archiviazione distribuita fornite dal servizio IBM Cloud Object Storage.

IBM COS è disponibile in due configurazioni: **Cross Region** e **Regional**. Il servizio Cross Region fornisce una disponibilità e una durata maggiori rispetto all'utilizzo di una sola regione, ma al costo di una leggermente maggiore latenza, questo servizio è disponibile oggi negli Stati Uniti e in Europa. Il servizio Regional fornisce il contrario: distribuisce gli oggetti in più zone di disponibilità all'interno di una sola regione. Se una zona di disponibilità o una regione non è disponibile, l'archiviazione oggetti continua a funzionare correttamente. Tutte le modifiche mancanti vengono applicate quando il data center non accessibile torna online.

## Che cos'è IBM Cloud Direct Link?

IBM Cloud Direct Link è una suite di prodotti che fornisce ai clienti la capacità di creare connessioni private tra i loro ambienti di rete remoti e le loro distribuzioni IBM Cloud. 

## Utilizzo di Cloud Object Storage (COS) su IBM Cloud Direct Link

La famiglia di soluzioni di connettività IBM Cloud Direct Link è un'offerta IaaS, pensata per consentire la connettività WAN privata ai nostri servizi IaaS. La maggior parte delle soluzioni IBM Cloud PaaS e SaaS sono create con il nostro IaaS. Pertanto, puoi avviare questi tipi di connessioni dall'interno di IBM Cloud.

Questi tre approcci possono aiutarti a collegarti a IBM Cloud PaaS e SaaS utilizzando IBM Cloud Direct Link. Al momento, il metodo #3 è l'approccio consigliato, perché è stato verificato più attentamente.

## I tre metodi per la connessione a PaaS e SaaS con Direct Link


### Metodo 1: utilizza un VRA (Virtual Router Appliance, a volte denominato Vyatta) per creare un “hop al pubblico”
 
![vyatta-flow.png](images/vyatta-flow.png)



**Premessa di base: collegati a IBM COS con un "hop pubblico" per collegare e archiviare gli endpoint**
*Questo "hop pubblico" non lascia mai il backbone IBM Cloud IaaS.*

* Il cliente sceglie un endpoint pubblico con l'assistenza dal supporto clienti IBM COS e dal team di onboarding e riceve una chiave API.
* Nei propri router in loco, il cliente aggiunge le rotte a sottoreti specifiche, in modo da assicurare buoni flussi del traffico utilizzando IBM Cloud Direct Link
* Nel proprio VRA, il cliente crea una rotta per attraversare la rete pubblica e raggiungere l'endpoint pubblico per i servizi IBM COS.
* Il cliente deve eseguire il provisioning di una coppia HA dell'hardware VRA (@x)
* Ogni membro del VRA riceve 20TB al mese di larghezza di banda inclusa, per compensare gli addebiti alla tua misurazione e fatturazione del cloud pubblico.
* Utilizza il pooling della larghezza di banda tra i tuoi server ospitati per accumulare larghezza di banda prepagata.


### Metodo 2: pass-through del server cloud (privato-a-privato)

![reverse=proxy](images/reverse-proxy.png)

**Premessa di base: server cloud attendibili con credenziali COS**

 * Il client esegue il provisioning di uno o più server, VSI o Bare Metal, in IBM Cloud
 * Ogni server ospita un'applicazione (Java, Python, PHP, ecc.) con script o basata sul web per essere in ascolto delle connessioni e delle richieste solo nella propria interfaccia privata
 * L'applicazione server utilizza la propria API o le proprie simulazioni (parti di) S3
 * Le interfacce private del server IBM Cloud sono piuttosto sicure. Separa l'accesso all'interno della rete privata utilizzando le VLAN, i gruppi di sicurezza, il firewall del SO o il VRA
 * Delle misure per convalidare il chiamante e limitare il raggiungimento dell'API sono sagge
 * I client nella rete in loco del cliente utilizzano gli indirizzi IP dei server pass-through cloud come destinazioni delle richieste
 * Richiede l'instradamento client e le modifiche DNS
 * L'applicazione ospitata sul server gestisce ogni richiesta emettendo una chiamata API autenticata a un endpoint COS privato, restituendo la risposta al chiamante

### Metodo 3: proxy inverso (privato-a-privato)

Questo metodo è al momento l'approccio consigliato.

**Premessa di base: chiamanti client in loco affidabili con credenziali COS**

 

 * Come un adattamento del metodo 2, invece di ospitare le applicazioni web sui server cloud, ospita i server HTTPS (ad esempio, NGINX) configurati per il proxy inverso.
 * Ogni server è in ascolto su HTTPS, con il certificato emesso in automatico e passa le richieste direttamente agli endpoint COS privati forniti nel documento a cui viene fatto riferimento qui di seguito:
 
 ![Endpoint COS](https://console.bluemix.net/docs/services/cloud-object-storage/basics/endpoints.html)
 
### Vedi un esempio di come migliorare le prestazioni e l'affidabilità del tuo cloud (non specifico per COS):`serverfault.com`

 * Per rafforzare la resilienza e il ridimensionamento, possono essere distribuiti più server proxy. 
 * Utilizza il DNS round robin nel lato del client per le funzionalità di bilanciamento del carico e di failover elementari.
 * I server proxy possono essere posizionati dietro il VRA per la protezione e per la registrazione centralizzata.
 
 ## Gestione e provisioning delle funzionalità IBM Cloud 
 
Questa sezione fornisce link rapidi alla documentazione per alcune offerte di IBM Cloud PaaS e SaaS che potresti collegare per utilizzare IBM Cloud Direct Link.

## Come eseguire il provisioning dei server bare metal

Per istruzioni dettagliate su come eseguire il provisioning del server bare metal, fai riferimento a [questo documento](https://console.bluemix.net/docs/bare-metal/about.html#getting-started-with-bare-metal-servers).

## Come eseguire il provisioning di un VRA (Virtual Router Appliance)

Per istruzioni dettagliate su come eseguire il provisioning di un VRA, fai riferimento a [questo documento](https://console.bluemix.net/docs/infrastructure/virtual-router-appliance/getting-started.html#getting-started).

## Come eseguire il provisioning di IBM Cloud Object Storage (COS)

 * Per istruzioni dettagliate su come eseguire il provisioning di COS, fai riferimento a [questo documento](https://console.bluemix.net/catalog/services/cloud-object-storage).
 
 * Utilizza uno degli endpoint privati (elencati precedentemente) per interagire con il tuo bucket o oggetto nel tuo account COS fornito.
