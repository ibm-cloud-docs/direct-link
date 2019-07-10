---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-30"

keywords: direct link, configure, connectivity, BGP, VRF, configuration, RFC1918, ASN, BYOIP, NAT, VLAN Spanning, 10.0.0.0/8, ECMP, redundancy, IP assignments, VMWare, Vyatta, IP limitations

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

# Configura IBM Cloud Direct Link
{: #configure-ibm-cloud-direct-link}

Dopo aver stabilito la connettività al tuo {{site.data.keyword.cloud}} Direct Link, puoi seguire la procedura fornita in questa documentazione per configurare la tua sottorete per interagire con {{site.data.keyword.cloud_notm}}.

In generale, per far funzionare la tua connessione {{site.data.keyword.cloud_notm}} Direct Link, dovrai effettuare alcuni passi di configurazione della rete di base e poi dovrai configurare il BGP (Border Gateway Protocol). Durante il processo di configurazione, un ingegnere IBM lavorerà con te per abilitare la tua rete ad utilizzare la funzionalità VRF (Virtual Routing Function), che è obbligatoria.

## Configurazione della rete di base
{: #basic-network-configuration}

1. Definisci la tua rete remota utilizzando lo spazio di indirizzo privato RFC1918 standard. 
 * Per i nuovi ambienti, ti consigliamo di **NON** utilizzare lo spazio 10.0.0.0/8. 
 * Per gli ambienti esistenti che utilizzano 10.0.0.0/8, ti consigliamo di ottenere una valutazione più dettagliata, per assicurarti che non sia presente un conflitto con la rete dei servizi {{site.data.keyword.cloud_notm}} o con le reti già assegnate al tuo account.

2. Il nostro personale {{site.data.keyword.cloud_notm}} assegna /31 o /30 ad ogni connessione e configura un indirizzo IP dell'interfaccia nell'infrastruttura XCR (cross-connect router) {{site.data.keyword.cloud_notm}}.  

3. Configura l'interfaccia nel tuo CER (customer edge router), utilizzando l'indirizzo IP che abbiamo fornito: utilizza solo l'IP XCR {{site.data.keyword.cloud_notm}} come hop successivo per tutto il traffico destinato a {{site.data.keyword.cloud_notm}}. 

4. Per il traffico di ritorno, {{site.data.keyword.cloud_notm}} utilizza l'IP CER assegnato come hop successivo per tutto il traffico destinato alla rete remota, come annunciato tramite BGP.

## Configurazione di BGP
{: #configuring-bgp}

Per scambiare le informazioni della rotta con il tuo ambiente, {{site.data.keyword.cloud_notm}} richiede la configurazione di BGP.  

1. **ASN**: {{site.data.keyword.cloud_notm}} assegna un ASN privato per ogni utilizzo del cliente. In alternativa, puoi utilizzare il tuo proprio ASN pubblico. La tua preferenza viene richiesta al momento in cui inserisci l'ordine. L'ASN privato assegnato ti viene fornito durante il processo di implementazione.

2. **VRF**: l'utilizzo di VRF, {{site.data.keyword.cloud_notm}} annuncia le sottoreti private specificate assegnate al tuo account del cliente. Devi annunciare le reti remote che desideri siano raggiungibili dalla rete privata {{site.data.keyword.cloud_notm}}. È tua responsabilità come cliente di gestire gli avvisi della rete IBM Cloud. (Ulteriori dettagli su VRF sono inclusi nella prossima sezione.)

Le seguenti reti vengono filtrate e non possono essere accettate: 0.0.0.0, 10.0.0.0/14, 10.198.0.0/15, 10.200.0.0/14, 169.254.0.0/16, 224.0.0.0/4.
{:note}

3. **ECMP**: per i clienti che scelgono di creare la ridondanza nell'ubicazione supportata, {{site.data.keyword.cloud_notm}} supporta l'implementazione di ECMP (equal-cost multipath) per fornire il bilanciamento del carico e la ridondanza tra i due link. Questa configurazione ECMP deve essere richiesta al momento dell'ordine.

## Specifiche per IBM Cloud Direct Link
{: #bgp-specifications-for-ibm-cloud-direct-link}

Le specifiche BGP sono le seguenti:

Come indicato nella sezione precedente, BGP è obbligatorio per la gestione del tuo instradamento tramite Direct Link. Un account che ordina Direct Link verrà migrato nell'ambiente VRF.

**Avvertimenti per le VLAN e VRF:**
 * Lo spanning della VLAN tra gli account non è consentito nell'ambiente VRF. 
 * Il servizio IPSEC VPN è limitato. 
 
VRF non impedisce l'accesso SSL o PPTP VPN, ma il suo comportamento cambia. Senza VRF, una connessione VPN è sufficiente per visualizzare tutti i server sul tuo account. Con VRF, puoi accedere solo alle risorse nel mercato associato alla VPN. Per cui se ti colleghi alla VPN DAL, puoi collegarti solo al server DAL.
{: note}

L'ASN di IBM Cloud è **13884**, per i servizi pubblico e privato. 
 * L'ASN predefinito per un cliente quando ordina è **64999**, ma il valore predefinito può essere modificato dalla richiesta del cliente. 
 * Facoltativamente, può essere supportato un ASN privato a 4-byte compreso tra 4201000000 e 4201064511.
 * Se stai utilizzando Direct Link Connect con un servizio layer-3, come ad esempio IP VPN, IBM Cloud stabilirà BGP con l'ASN del provider Direct Link Connect

**Consigli, valori predefiniti e limiti:**

 * Il tunneling (ossia, GRE) è supportato e consigliato se la sovrapposizione IP diventa un problema.
 * I valori predefiniti del timer BGP sono `Keepalive:30`, `Holdtime:60.`
 * L'autenticazione non è abilitata per impostazione predefinita.
 * BGP BFD non è abilitato per impostazione predefinita.
 * Il limite massimo di prefisso ricevuto (dal cliente o provider) è 200 per VRF.
 
## Limitazioni rigorose sulle assegnazioni IP
{: #strict-limitations-on-ip-assignments}

 * Se utilizzi la rete 10.x.x.x, non puoi ancora creare una sovrapposizione con i tuoi host in IBM Cloud né con la rete dei servizi IBM Cloud, che occupa `10.0.0.0/14`, `10.198.0.0/15` e `10.200.0.0/14`.  

 * I seguenti intervalli non sono consentiti nel sistema federale e verranno rifiutati dai server IBM: `169.254.0.0/16`, `224.0.0.0/4`.

## Ridondanza e diversità
{: #redundancy-and-diversity}

{{site.data.keyword.cloud_notm}} Direct Link fornisce la diversità e i clienti sono responsabili per l'implementazione della ridondanza tramite i propri schemi BGP. 

Se selezioni ECMP per la ridondanza, entrambe le sessioni BGP devono trovarsi sullo stesso XCR; rinunci pertanto alla diversità del router e vengono esposte a rischi se il router dovesse avere un malfunzionamento. Ottieni la ridondanza di livello 3 ma perdi la diversità del router. 

## Ulteriori informazioni sull'utilizzo di VRF
{: #more-about-using-vrf}

Tutti gli account che utilizzano una soluzione {{site.data.keyword.cloud_notm}} Direct Link devono essere migrati a una VRF. Utilizzando la VRF, i clienti annunciano le rotte disponibili alle proprie reti remote auto-definite. Nota che questa configurazione non ti consente di utilizzare l'indirizzo IP auto-definito nella rete {{site.data.keyword.cloud_notm}}.

La migrazione a una VRF viene effettuata durante il processo di configurazione. Richiede una breve finestra di inattività (fino a 30 minuti per account grandi con più VLAN/ubicazioni), durante la quale le VLAN della rete di backend perderanno la connettività reciproca mentre vengono spostate nella VRF. La migrazione VRF viene pianificata con l'ingegnere di implementazione.

Nota che la VRF elimina l'opzione "VLAN Spanning" per il tuo account, inclusa ogni funzionalità di spanning VLAN account-to-account, perché tutte le VLAN sono in grado di comunicare a meno che non viene introdotta un'applicazione gateway per gestire il traffico. La VRF inoltre limita la possibilità di utilizzare i servizi VPN {{site.data.keyword.cloud_notm}}, perché non è compatibile con i servizi VPN {{site.data.keyword.cloud_notm}} SSL, PPTP e IPSec VPN.   

Un'alternativa è di utilizzare la stessa offerta IBM Cloud Direct Link per gestire i tuoi server o di eseguire la tua propria soluzione VPN (come Vyatta) che può essere configurata con diversi tipi di VPN. Dopo aver eseguito la migrazione a una VRF, la VPN SSL normalmente funziona quando viene effettuata una connessione VPN alla stessa ubicazione del data center in cui la VM di calcolo è in esecuzione, ma non concede l'accesso globalmente.

## Utilizzo di BYOIP e NAT con Direct Link
{: #using-byoip-and-nat-with-direct-link}

IBM Cloud Direct Link non offre BYOIP nella rete privata. Pertanto, il traffico con un indirizzo IP di destinazione che non è stato assegnato da {{site.data.keyword.cloud_notm}} sarà eliminato. Tuttavia, i clienti possono incapsulare il traffico tra la rete remota e la propria rete {{site.data.keyword.cloud_notm}} utilizzando GRE, IPSec o VXLAN.  

Più comunemente, l'ambiente BYOIP viene implementato nello scopo di un gateway di rete (Vyatta) o una distribuzione VMWare NSX. Questa configurazione consente ai clienti di utilizzare ogni spazio IP opportuno nel lato {{site.data.keyword.cloud_notm}} e di ritornare tramite il tunnel nella rete remota. Nota che questa configurazione deve essere gestita e supportata dal cliente, indipendentemente da {{site.data.keyword.cloud_notm}}. Inoltre, questa configurazione può interrompere la connettività alla rete dei servizi {{site.data.keyword.cloud_notm}} se il cliente assegna un blocco 10.x.x.x che {{site.data.keyword.cloud_notm}} ha in uso per i servizi. 

Questa soluzione richiede inoltre che ogni host che necessita della connettività alla rete dei servizi {{site.data.keyword.cloud_notm}} e alla rete remota deve avere 2 IP assegnati: uno deve essere assegnato dal blocco IBM 10.x.x.x e uno dal blocco della rete remota. Le rotte statiche devono essere configurate nell'host, per garantire che il traffico venga instradato correttamente. Non potrai assegnare lo spazio IP direttamente per gli host {{site.data.keyword.cloud_notm}} (BYOIP) ed averlo instradabile alla rete {{site.data.keyword.cloud_notm}} intrinsecamente. L'unico modo per implementare questa funzionalità è come illustrato precedentemente, ma non è supportata da {{site.data.keyword.cloud_notm}}.

In alternativa, i clienti spesso assegnano un blocco della rete privata per utilizzarlo in una tabella NAT configurata nel proprio router edge remoto. Questa configurazione consente agli utenti di limitare le modifiche richieste ad entrambe le reti, mentre ancora viene trasmesso il traffico a uno spazio di indirizzo di rete compatibile con entrambe le reti.
