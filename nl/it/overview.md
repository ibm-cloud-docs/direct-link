---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-02-19"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Panoramica delle offerte Direct Link
{ #overview-of-direct-link-offerings}

L'offerta {{site.data.keyword.cloud}} Direct Link fornisce la connettività da un'origine esterna a una rete privata IBM del cliente. Direct Link può essere visto come un'alternativa a una soluzione VPN site-to-site, progettato per i clienti che hanno bisogno di una connettività con velocità effettiva più elevata e consistente tra una rete remota e i propri ambienti IBM Cloud. Sono disponibili quattro tipi di connessioni:
 
 * **IBM Cloud Direct Link Exchange** consente agli utenti di utilizzare un provider Exchange per fornire la connettività al proprio IBM Cloud. Un provider Exchange è un provider di rete o vettore già collegato alla rete IBM Cloud, che utilizza link ad elevata capacità a più tenant. I clienti normalmente possono acquistare un circuito virtuale a questo provider, fornendo a un costo ridotto, perché la connettività fisica da {{site.data.keyword.BluSoftlayer_notm}} al provider Exchange è già in atto, condivisa tra altri clienti.
 
 * **IBM Cloud Direct Link Connect** consente agli utenti di utilizzare un collegamento tramite i nostri partner che gestiscono e operano su una rete basata sulla struttura. Con IBM Cloud Direct Link Connect, IBM e il partner si collegano ai clienti al livello 2 e 3 tramite, Layer-2 10G NNIs duali.
 
 * **IBM Cloud Direct Link Dedicato** consente agli utenti di terminare una connessione trasversale fiber, a modalità singola e dedicata nella propria rete privata IBM Cloud.
 
 * **Direct Link Dedicated Hosting** fornisce una connettività simile a IBM Cloud Direct Link Dedicato, ma il punto di connessione è vicino a un data center {{site.data.keyword.BluSoftlayer_notm}}, che migliora la latenza per i casi di utilizzo a prestazioni elevate. IBM Cloud offre molti servizi personalizzabili e di condivisione con questa soluzione.
  
Il servizio IBM Cloud Direct Link è un servizio OSI Layer-3 instradato. Offre una connessione diretta al backbone della rete privata {{site.data.keyword.BluSoftlayer_notm}}, con bassa latenza e con velocità fino a 10Gbps.
Per una flessibilità incrementata nella creazione di questa connettività Layer-3, IBM Cloud Direct Link consente ai clienti di utilizzare:
 * IP duale per gli host remoti
 * NAT
 * Tunneling per BYOIP
 
 Per le descrizioni dettagliate di ogni offerta, consulta [Informazioni su IBM Cloud Direct Link](/docs/infrastructure/direct-link?topic=direct-link-about-ibm-cloud-direct-link).
