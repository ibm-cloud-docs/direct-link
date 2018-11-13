---

copyright:
  years: 2017, 2018
lastupdated: "2018-07-25"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Panoramica di VRF (Virtual Routing and Forwarding) su IBM Cloud

Per definizione, VRF (virtual routing and forwarding) è una tecnologia inclusa nei router di rete IP (Internet Protocol). Viene fornito come un servizio di backbone intrinseco.

## Opzioni di connettività per IBM Cloud

**Le risorse cloud diffuse** sono risorse in più di un'ubicazione o anche in più di una sottorete o VLAN. Queste risorse richiedono una funzione di instradamento per comunicare tra loro, anche all'interno di un contesto di rete privata. Questo documento descrive un'opzione di comunicazione tenancy "isolamento multiplo", spesso denominata come _VRF cliente_. È implementata come una VPN di livello 3 MPLS (RFC 4364) nell backbone IBM Cloud globale.

In generale, la piattaforma IBM Cloud offre due opzioni per l'instradamento attraverso la nostra rete privata, fornendo connettività tra i pod e i datacenter: 

1. **Tenancy condivisa:** una rete logica comune, condivisa da tutti i tenant che utilizzano questo modello, con separazione fornita da ACL (Access Control List) automatizzati e abilitati con lo spanning della VLAN. (Questa opzione non viene descritta in questo documento.)

2. **Isolamento multiplo:** una rete logica dedicata per tenant, che non consente l'interazione con altre reti logiche dei tenant.  

Questo documento utilizza il termine **VRF cliente** per descrivere la connettività di rete _isolamento multiplo_ .

## Panoramica sul VRF cliente

VRF (Virtual routing and forwarding) consente a più istanze di una tabella di instradamento di stare in un router e di funzionare contemporaneamente. Con VRF (virtual routing and forwarding), la rete VRF di ogni cliente viene suddivisa all'interno della sua tabella di instradamento. Questa suddivisione consente sovrapposizioni dell'indirizzo IP e non crea alcuna interazione o interferenza con altri VRF cliente. IBM Cloud utilizza una grande maggioranza della rete `10.0.0.0/8`, che può sovrapporsi alle reti remote di molti clienti. 

Utilizzando VRF (Virtual Routing and Forwarding), ai clienti è consentito utilizzare gli indirizzi IP remoti che normalmente non sarebbero autorizzati a sovrapporsi nella tabella Globale. IBM riserva ancora i seguenti RFC 1918, indirizzi locali di collegamento e indirizzi multicast, che non sono instradabili da questo servizio VRF:

* `10.0.0.0/14` 
* `10.200.0.0/14` 
* `10.198.0.0/15` 
* `169.254.0.0/16` 
* `224.0.0.0/4` 
* `166.9.0.0/16`(che utilizza il servizio endpoint privato)
* Qualsiasi intervallo IP assegnato alle tue VLAN sulla piattaforma IBM.

IBM sta procedendo con una distribuzione cloud di nuova generazione per abilitare i VPC (Virtual Private Cloud) nelle nostre zone di disponibilità (AZ). Questa nuova funzionalità VPC consente ai clienti di utilizzare BYoIP (Bring Your own IP) nelle zone di disponibilità abilitate VPC, che si trovano a Dallas, Washington DC, Londra, Francoforte, Tokyo e Sydney. 

Ogni tenant sulla backbone che utilizza VRF (Virtual Routing and Forwarding) può avere uno (e solo uno) _VRF cliente_ per Direct Link, che fornisce la connettività tra tutti i server del tenant, indipendentemente dalla posizione. Tuttavia, un cliente potrebbe avere più di un account Direct Link che forniscono un solo router trasversale.  

* I server di un tenant in qualsiasi VLAN, pod, datacenter in tutto il mondo possono raggiungere tutti gli altri server del tenant in tutto il mondo. 

* Ogni VRF cliente del tenant è collegato alla rete di servizi condivisi comune, per fornire la raggiungibilità privata per tali server per utilizzare il DNS, la memoria condivisa, il monitoraggio, l'applicazione di patch e così via.

* Il VRF cliente è un servizio di connettività che fornisce l'isolamento tra i tenant. Tutti i controlli aggiuntivi necessari all'interno di una tenancy devono essere forniti separatamente, utilizzando un gateway, i gruppi di sicurezza o i controlli basati sull'host.

## Vantaggi del passaggio a un VRF cliente

**I vantaggi principali di un VRF cliente includono:**

* Tecnologia di separazione comprovata e ampiamente accettata per l'_isolamento multiplo_. Molti clienti trovano l'approccio della VPN di livello 3 migliore (rispetto agli ACL) ai propri revisori e responsabili di conformità.   

* I clienti possono estendere o migrare la portata della loro rete in modo significativo, grazie all'aggiunta di nuovi siti o applicazioni in tutta la rete IBM. 

* Le tabelle di instradamento specifiche del tenant restringono l'apertura per la sovrapposizione dell'indirizzo IP, senza il rischio di sovrapposizione con altre sottoreti dei tenant o altre parti della rete che non sono applicabili. 

**Sono disponibili alcuni compromessi con il VRF cliente, rispetto al vecchio modello ACL:**  

* La conversione a un VRF cliente richiede una finestra di manutenzione, che causa una breve interruzione dei flussi del traffico di backbone.

* L'accesso remoto tramite i servizi VPN gestiti (SSL, IPSec) è limitato al datacenter locale; tuttavia, il backbone ACL condiviso consente l'accesso globale da qualsiasi punto di ingresso.

* Lo spanning della VLAN all'interno della tenancy dell'_isolamento multiplo_ di un cliente non è disponibile.

## Cosa succede durante il processo di conversione dell'account

Molti clienti stanno attualmente utilizzando un modello di tenancy condiviso sulla rete IBM Cloud. Durante la conversione, la tenancy viene convertita per utilizzare un VRF cliente, più comunemente con una nuova sottoscrizione Direct Link o come altrimenti richiesto o necessario.  

Il processo di conversione comporta un'interruzione della rete, mentre le VLAN e le loro sottoreti vengono scollegate dal backbone ACL e collegate al VRF cliente. Questo processo causa una piccola perdita di pacchetti per il traffico in entrata e in uscita dalle VLAN. I pacchetti all'interno della VLAN continuano a fluire. Nei casi in cui è coinvolto un gateway di rete, come ad esempio un FortiGate Security Appliance o Virtual Router Appliance, non si verifica alcuna interruzione tra le VLAN collegate a tale gateway. I server non vedono l'interruzione di rete e la maggior parte dei carichi di lavoro vengono ripristinati automaticamente quando il flusso di traffico riprende. La durata totale dell'interruzione dipende dalla portata della topologia del tenant, cioè il numero di sottoreti, VLAN e pod inclusi nella tenancy.

![Il processo di conversione](/images/vrf-on-ibm-cloud.png)

Durante la migrazione, le VLAN del cliente vengono scollegate dalla backbone e ricollegate al VRF cliente.  La durata dell'interruzione varia, a seconda della quantità di VLAN, POD e datacenter coinvolti. Il traffico tra le VLAN viene interrotto, ma i server restano collegati alla rete. L'applicazione potrebbe essere influenzata o meno a seconda della sensibilità per la perdita di pacchetti.

## Come puoi iniziare la conversione

I nostri clienti possono aprire un ticket di supporto tramite il loro account [IBM Cloud Console ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")]( https://control.bluemix.net/support/unifiedConsole/tickets/add), richiedendo la migrazione in un VRF. Il ticket deve dichiarare: “Private Network Question” e includere il seguente testo: 

"We are requesting that account _fill in your account number_ is moved to its own VRF. We understand the risks and approve the change.  Please reply back with the scheduled window(s) of time where this change will be made so we can prepare for the migration." 

La migrazione viene completata dal team IBM Cloud Network Engineering. Non sono necessarie altre informazioni dal cliente, tranne una pianificazione concordata. Normalmente, la perdita di pacchetti può durare 15-30 minuti, a seconda della complessità dell'account. (Potrebbe essere più lunga se un cliente dispone di connessioni Direct Link legacy). Il processo è altamente automatizzato. Comporta interazione minima con il team IBM e dovrebbe essere chiara a un cliente.
