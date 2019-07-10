---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: overview, connectivity, private network, site-to-site, Exchange, Connect, Dedicated, Hosting, OSI, Layer-3, partners, NNI, latency, backbone

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Panoramica delle offerte Direct Link
{: #overview-of-direct-link-offerings}

L'offerta {{site.data.keyword.cloud}} Direct Link fornisce la connettività da un'origine esterna a una rete privata IBM del cliente. Direct Link può essere visto come un'alternativa a una soluzione VPN site-to-site, progettato per i clienti che hanno bisogno di una connettività con velocità effettiva più elevata e consistente tra una rete remota e i propri ambienti IBM Cloud. Sono disponibili quattro tipi di connessioni:
 
 * **IBM Cloud Direct Link Exchange** consente ai clienti di utilizzare un provider Exchange per fornire la connettività al proprio IBM Cloud. Un provider Exchange è un provider di co-ubicazione o di data center già connesso alla rete {{site.data.keyword.cloud_notm}}, che utilizza link ad elevata capacità a più tenant (noto anche come _network-to-network interface_ o NNI). I clienti normalmente possono acquistare un circuito virtuale presso questo provider, portando la connettività a un costo ridotto, perché la connettività fisica da {{site.data.keyword.cloud_notm}} al provider Exchange è già in atto, condivisa tra altri clienti.
 
 * **IBM Cloud Direct Link Connect** consente ai clienti di utilizzare una connessione tramite i nostri partner vettore che gestiscono e operano su una rete basata sulla struttura. Un provider Connect è un NSP (provider del servizio di rete - network service provider) già connesso alla rete {{site.data.keyword.cloud_notm}}, che utilizza link ad elevata capacità a più tenant (noto anche come _network-to-network interface_ o NNI). I clienti normalmente possono acquistare un circuito virtuale presso questo provider, portando la connettività a un costo ridotto, perché la connettività fisica da {{site.data.keyword.cloud_notm}} al provider Connect è già in atto, condivisa tra altri clienti. 
 
 * **IBM Cloud Direct Link Dedicated** consente ai clienti di terminare una connessione trasversale fiber a singolo tenant nella rete {{site.data.keyword.cloud_notm}}. Questa offerta può essere utilizzata dai clienti con strutture di co-ubicazione in loco vicine ai data center e ai POP di IBM Cloud, come pure dai provider del servizio di rete che forniscono i circuiti ai data center in loco dei clienti e ad altri data center. 
 
 * **IBM Cloud Direct Link Dedicated Hosting** fornisce una connettività simile a {{site.data.keyword.cloud_notm}} Direct Link Dedicated, ma il punto di connessione è vicino a un data center {{site.data.keyword.cloud_notm}}, ciò migliora la latenza per i casi di utilizzo a prestazioni elevate. {{site.data.keyword.cloud_notm}} offre molti servizi di co-ubicazione personalizzabili con questa soluzione. 
  
Il servizio {{site.data.keyword.cloud_notm}} Direct Link è un servizio di livello 3 OSI instradato. Offre una connessione diretta al backbone della rete privata {{site.data.keyword.cloud_notm}}, con bassa latenza e con velocità fino a 10Gbps.
Per una flessibilità incrementata nella creazione di questa connettività di livello 3, {{site.data.keyword.cloud_notm}} Direct Link consente ai clienti di utilizzare:
 * IP duale per gli host remoti
 * NAT
 * Tunneling per BYOIP
 
 Per le descrizioni dettagliate di ogni offerta, consulta [Informazioni su IBM Cloud Direct Link](/docs/infrastructure/direct-link?topic=direct-link-about-ibm-cloud-direct-link).
