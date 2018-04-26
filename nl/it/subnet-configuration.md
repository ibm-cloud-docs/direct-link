---

copyright:
  years: 2017
lastupdated: "2017-12-04"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Configura IBM Cloud Direct Link

Dopo aver stabilito la connettività al tuo IBM Cloud Direct Link, puoi seguire la procedura fornita in questa documentazione per configurare la tua sottorete per interagire con IBM Cloud.

In generale, per far funzionare la tua connessione IBM Cloud Direct Link, dovrai effettuare alcuni passi di configurazione della rete di base e configurare il BGP (Border Gateway Protocol). Durante il processo di configurazione, un ingegnere IBM lavorerà con te per abilitare la tua rete ad utilizzare la funzionalità VRF (Virtual Routing Function), che è obbligatoria.

## Configurazione della rete di base

1. Definisci la tua rete remota utilizzando lo spazio di indirizzo privato RFC1918 standard. 
 * Per i nuovi ambienti, è consigliato di **non** utilizzare lo spazio 10.0.0.0/8. 
 * Per gli ambienti esistenti che utilizzano 10.0.0.0/8, ti consigliamo di ottenere una valutazione più dettagliata, per assicurarti che non sia presente un conflitto con la rete dei servizi {{site.data.keyword.BluSoftlayer_notm}} o con le reti già assegnate al tuo account.

2. Il nostro personale {{site.data.keyword.BluSoftlayer_notm}} assegna /31 o /30 ad ogni connessione e configura un indirizzo IP dell'interfaccia nell'infrastruttura XCR (cross-connect router) {{site.data.keyword.BluSoftlayer_notm}}.  

3. Configura l'interfaccia nel tuo CER (customer edge router), utilizzando l'indirizzo IP che abbiamo fornito: utilizza solo l'IP XCR {{site.data.keyword.BluSoftlayer_notm}} come hop successivo per tutto il traffico destinato a {{site.data.keyword.BluSoftlayer_notm}}. 

4. Per il traffico di ritorno, {{site.data.keyword.BluSoftlayer_notm}} utilizza l'IP CER assegnato come hop successivo per tutto il traffico destinato alla rete remota, come annunciato tramite BGP.

## Configurazione di BGP

Per scambiare le informazioni della rotta con il tuo ambiente, {{site.data.keyword.BluSoftlayer_notm}} richiede la configurazione di BGP.  

1. **ASN**: {{site.data.keyword.BluSoftlayer_notm}} assegna un ASN privato per ogni utilizzo del cliente. In alternativa, puoi utilizzare il tuo proprio ASN pubblico. La tua preferenza viene richiesta al momento in cui inserisci l'ordine. L'ASN privato assegnato ti viene fornito durante il processo di implementazione.

2. **VRF**: l'utilizzo di VRF, {{site.data.keyword.BluSoftlayer_notm}} annuncia le sottoreti private specificate assegnate al tuo account del cliente.  Devi annunciare le reti remote che desideri siano raggiungibili dalla rete privata {{site.data.keyword.BluSoftlayer_notm}}. Le seguenti reti vengono filtrate e non possono essere accettate: 0.0.0.0, 10.0.0.0/14, 10.198.0.0/15, 10.200.0.0/14, 169.254.0.0/16, 224.0.0.0/4. È tua responsabilità come cliente di gestire gli avvisi della rete IBM Cloud. (Ulteriori dettagli su VRF sono inclusi nella prossima sezione.)

3. **ECMP**: per i clienti che scelgono di creare la ridondanza nell'ubicazione supportata, {{site.data.keyword.BluSoftlayer_notm}} supporta l'implementazione di ECMP (equal-cost multipath) per fornire il bilanciamento del carico e la ridondanza tra i due link. Questa configurazione ECMP deve essere richiesta al momento dell'ordine.

## Ridondanza e diversità

IBM Cloud Direct Link fornisce la diversità e i clienti sono responsabili per l'implementazione della ridondanza tramite i propri schemi BGP.

Se selezioni ECMP per la ridondanza, entrambe le sessioni BGP devono essere sullo stesso XCR, pertanto rinuncia alla diversità del router e vengono esposte a rischi se il router dovesse avere un malfunzionamento. Ottieni la ridondanza di livello 3 ma perdi quella di livello 2.

## Ulteriori informazioni sull'utilizzo di VRF

Tutti gli account che utilizzano una soluzione Direct Link devono essere migrati a una VRF. Utilizzando la VRF, i clienti annunciano le rotte disponibili alle proprie reti remote auto-definite. Nota che questa configurazione non ti consente di utilizzare l'indirizzo IP auto-definito nella rete {{site.data.keyword.BluSoftlayer_notm}}.

La migrazione a una VRF viene effettuata durante il processo di configurazione. Richiede una breve finestra di inattività (fino a 30 minuti per account grandi con più VLAN/ubicazioni), durante la quale le VLAN della rete di backend perderanno la connettività reciproca mentre vengono spostate nella VRF. La migrazione VRF viene pianificata con l'ingegnere di implementazione.

Nota che la VRF elimina l'opzione "Spanning VLAN" per il tuo account, inclusa ogni funzionalità di spanning VLAN account-to-account, perché tutte le VLAN sono in grado di comunicare a meno che non viene introdotta un'applicazione gateway per gestire il traffico. La VRF inoltre limita la possibilità di utilizzare i servizi VPN {{site.data.keyword.BluSoftlayer_notm}}, perché non è compatibile con i servizi VPN {{site.data.keyword.BluSoftlayer_notm}} SSL, PPTP e IPSec VPN.   

Un'alternativa è di utilizzare la stessa offerta IBM Cloud Direct Link per gestire i tuoi server o di eseguire la tua propria soluzione VPN (come Vyatta) che può essere configurata con diversi tipi di VPN. Dopo aver eseguito la migrazione a una VRF, la VPN SSL normalmente funziona quando viene effettuata una connessione VPN alla stessa ubicazione del data center in cui la VM di calcolo è in esecuzione, ma non concede l'accesso globalmente.

## Utilizzo di BYOIP e NAT con Direct Link
IBM Cloud Direct Link non offre BYOIP nella rete privata, ad eccezione di circostanze speciali descritte nella sezione [Indirizzamento privato personalizzato](#custom-private-addressing). Pertanto, il traffico con un indirizzo IP di destinazione che non è stato assegnato da {{site.data.keyword.BluSoftlayer_notm}} sarà eliminato. Tuttavia, i clienti possono incapsulare il traffico tra la rete remota e la propria rete {{site.data.keyword.BluSoftlayer_notm}} utilizzando GRE, IPSec o VXLAN.  

Più comunemente, l'ambiente BYOIP viene implementato nello scopo di un gateway di rete (Vyatta) o una distribuzione VMWare NSX. Questa configurazione consente ai clienti di utilizzare ogni spazio IP opportuno nel lato {{site.data.keyword.BluSoftlayer_notm}} e di ritornare tramite il tunnel nella rete remota. Nota che questa configurazione deve essere gestita e supportata dal cliente, indipendentemente da {{site.data.keyword.BluSoftlayer_notm}}. Inoltre, questa configurazione può interrompere la connettività alla rete dei servizi {{site.data.keyword.BluSoftlayer_notm}} se il cliente assegna un blocco 10.x.x.x che {{site.data.keyword.BluSoftlayer_notm}} ha in uso per i servizi. 

Questa soluzione richiede inoltre che ogni host che necessita della connettività alla rete dei servizi {{site.data.keyword.BluSoftlayer_notm}} e alla rete remota deve avere 2 IP assegnati: uno deve essere assegnato dal blocco IBM 10.x.x.x e uno dal blocco della rete remota. Le rotte statiche devono essere configurate nell'host, per garantire che il traffico venga instradato correttamente. Non potrai assegnare lo spazio IP direttamente per gli host {{site.data.keyword.BluSoftlayer_notm}} (BYOIP) ed averlo instradabile alla rete {{site.data.keyword.BluSoftlayer_notm}} intrinsecamente. L'unico modo per implementare questa funzionalità è come illustrato precedentemente, ma non è supportata da {{site.data.keyword.BluSoftlayer_notm}}.

In alternativa, i clienti spesso assegnano un blocco della rete privata per utilizzarlo in una tabella NAT configurata nel proprio router edge remoto. Questa configurazione consente agli utenti di limitare le modifiche richieste ad entrambe le reti, mentre ancora viene trasmesso il traffico a uno spazio di indirizzo di rete compatibile con entrambe le reti.

## Informazioni sull'indirizzamento privato personalizzato

A volte, durante l'on-boarding di IBM Cloud Direct Link, un cliente non riesce a risolvere i conflitti di indirizzamento dell'IP tra le reti privata e in loco {{site.data.keyword.BluSoftlayer_notm}} utilizzando i metodi precedentemente descritti. Se si verifica questa situazione, un rappresentante delle vendite o di progettazione {{site.data.keyword.BluSoftlayer_notm}} può consigliarti di utilizzare l'_Indirizzamento privato personalizzato_ (CPA). Nessun costo aggiuntivo viene associato con CPA; tuttavia, questa funzione ha requisiti e limitazioni univoci che devono essere compresi approfonditamente prima di accettarne l'utilizzo. Questi dettagli vengono descritti nella documentazione che ti sarà fornita dal rappresentante IBM Cloud che consiglia CPA. 

Il _requisito chiave_ è che l'indirizzamento privato personalizzato può essere attivato solo per un account nuovo e vuoto {{site.data.keyword.BluSoftlayer_notm}} e per una nuova connessione Direct Link. Non è possibile convertire o migrare risorse esistenti a CPA.

L'indirizzamento privato personalizzato ti consente di ospitare i server {{site.data.keyword.BluSoftlayer_notm}} in un intervallo IPv4 privato e valido di tua scelta (10.x.x.x, 192.168.x.x o 172.16.x.x). CPA fornisce un sottoinsieme di servizi IBM Cloud comuni in un intervallo di indirizzi internamente instradato, 161.26.x.x, che lascia gli indirizzi IP privati gratuiti per l'utilizzo del cliente. Mentre CPA ti abilita a definire fino a 5 intervalli IP privati (a cui viene fatto riferimento come _Reti CPA_), ogni Direct Link si collega a solo una rete CPA. Se esistono ulteriori reti CPA nell'account, non saranno accessibili tramite Direct Link.

L'indirizzamento privato personalizzato utilizza VRF e BGP. L'ingegnere di implementazione ti assisterà con i dettagli correlati a CPA.
