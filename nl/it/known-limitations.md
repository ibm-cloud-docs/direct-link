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

## Limitazioni note
Per prima cosa, questa sezione copre le limitazioni che si applicano a tutte e tre le offerte IBM Cloud Direct Link e quindi fornisce i dettagli di alcune limitazioni di ogni offerta individualmente.

### Limitazioni IBM Cloud Direct Link generali
 * Ogni connessione IBM Cloud Direct Link richiede un ordine univoco. Se richiedi più connessioni, apri un ordine Direct Link per ognuna di esse. 
 * La rete dei servizi {{site.data.keyword.BluSoftlayer_notm}} non è accessibile direttamente dalle tue reti remote.
 * {{site.data.keyword.BluSoftlayer_notm}} non consentirà agli utenti il backhaul del traffico dei loro siti remoti tramite il backbone {{site.data.keyword.BluSoftlayer_notm}}. Il prodotto IBM Cloud Direct Link è pensato per consentire alle tue reti remote di comunicare privatamente con la tua infrastruttura {{site.data.keyword.BluSoftlayer_notm}}.
 * IBM Cloud Direct Link ti richiede di utilizzare un'istanza VRF (Virtual Routing and Forwarding).
 * VRF non è completamente compatibile con i servizi VPN {{site.data.keyword.BluSoftlayer_notm}} SSL, PPTP e IPSec.
 * VRF non è compatibile con lo spanning VLAN account-to-account {{site.data.keyword.BluSoftlayer_notm}}.
 * IBM Cloud Direct Link richiede BGP per poter stabilire le rotte a una rete remota del cliente.
 * Le modifiche all'infrastruttura IBM Cloud Direct Link devono essere effettuate tra le 8 e le 17, fuso orario degli Stati Uniti centrali.
 
### Limitazioni di IBM Cloud Direct Link Exchange e Direct Link Connect
 * I clienti sono responsabili per ogni costo associato con il raggiungimento del POP da una rete remota e per tutti i cosi che si verificano con il provider Cloud Exchange.
 * {{site.data.keyword.BluSoftlayer_notm}} non condividerà le apparecchiature del cliente nei nostri POP di rete. I clienti devono utilizzare il proprio provider per determinare se necessitano di condividere un'apparecchiatura nella struttura in cui è presente il PoP di rete {{site.data.keyword.BluSoftlayer_notm}}.
 * La disponibilità di Direct Link Cloud Exchange varia tra le ubicazioni. I clienti possono contattare il proprio gestore dell'account IBM Cloud per confermare la disponibilità corrente o futura.
 
### Limitazioni di IBM Cloud Direct Link Dedicato
 * I costi {{site.data.keyword.BluSoftlayer_notm}} di IBM Cloud Direct Link dedicato coprono il costo della terminazione della porta nell'infrastruttura {{site.data.keyword.BluSoftlayer_notm}}. I clienti sono responsabili per ogni costo associato con il raggiungimento del PoP da una rete remota e per ogni connessione trasversale necessaria nella struttura PoP.  {{site.data.keyword.BluSoftlayer_notm}} non ordinerà una connessione trasversale al posto di un cliente.
 * {{site.data.keyword.BluSoftlayer_notm}} non condividerà le apparecchiature del cliente nei nostri PoP di rete. I clienti devono utilizzare il proprio provider per determinare se necessitano di condividere un'apparecchiatura nella struttura in cui è presente il PoP di rete {{site.data.keyword.BluSoftlayer_notm}}.

### Limitazioni di Host di IBM Cloud Direct Link dedicato
 * Host di IBM Cloud Direct Link dedicato richiede un contratto specifico tra {{site.data.keyword.BluSoftlayer_notm}} e il cliente. Questo contratto evidenzia i termini e le condizioni del prodotto, il prezzo dell'ambiente di ubicazione e l'obbligo di spesa per i servizi. È obbligatorio un contratto di 6, 9 o 12 mesi.
 * La connettività al provider è limitata ai provider nella rete del data center selezionato.
