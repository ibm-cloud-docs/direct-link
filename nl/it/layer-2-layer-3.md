---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-30"

keywords: layer 2, layer 3, interconnect, partner, multi-cloud, other clouds, BGP, XCR

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Confronto delle connessioni di livello 2 e di livello 3 per Direct Link
{: #comparing-layer-2-layer-3}

{{site.data.keyword.cloud}} Direct Link accetta le interconnessioni di partner di livello 2 e di livello 3 OSI dai provider del servizio di rete (NSP). Alcuni NSP offrono servizi per entrambi questi livelli su reti differenti, tuttavia, alcuni provider possono aver scelto di **non** interconnettere tutte le loro reti in {{site.data.keyword.cloud_notm}}. 

Quando pianifichi la tua distribuzione di {{site.data.keyword.cloud_notm}} Direct Link, tieni in considerazione le caratteristiche associate alle connessioni di livello 2 e di livello 3, in questo modo puoi creare una distribuzione che si adatta meglio alle tue esigenze. 

## Considerazioni per le connessioni di livello 2
{: #layer-2-networks}

Per ogni circuito virtuale basato su VLAN--che creerai con un'interconnessione di partner di livello 2--devi configurare e stabilire una sessione BGP tra i tuoi router in loco e l'XCR di IBM Cloud. IBM Cloud ti fornirà un'assegnazione IPv4 `/31` per stabilire una sessione BGP con il tuo router.

* Le reti di livello 2 offrono opzioni per connessioni uno-a-uno semplici tra le aziende e {{site.data.keyword.cloud_notm}}. 
* I servizi di livello 2 si basano sulle VLAN invece che sugli indirizzi IP.  
* I servizi di livello 2 possono avere un costo più basso e una latenza più bassa e possono consumare un sovraccarico inferiore rispetto ai servizi di livello 3.  
* Le reti di livello 2 non impongono limitazioni alle funzioni di livello 3 che possono essere abilitate da un'azienda. 

## Considerazioni per le connessioni di livello 3
{: #layer-3-networks}

Per le connessioni di livello 3, per ciascun circuito virtuale, il tuo provider del servizio stabilisce una sessione BGP tra gli XCR di IBM Cloud e i router edge del provider. Non dovrai configurare BGP con IBM Cloud per il tuo router in loco in quanto il tuo provider del servizio gestirà la configurazione di BGP in IBM Cloud.

* Le reti VPN o AVPN IP di livello 3 consentono la connettività "tutte-con-tutte". 
* Le reti di livello 3 richiedono che l'NSP mantenga una sessione BGP tra l'azienda e {{site.data.keyword.cloud_notm}}. 
* Alcuni NSP possono limitare determinate funzionalità nelle loro reti quando utilizzano le connessioni di livello 3, ad esempio l'anteposizione ASN, il tunneling GRE e così via. Assicurati di controllare con il tuo provider le possibili limitazioni. 

## Tabella di interconnessione di partner
{: #partner-interconnection-table}

La tabella riportata di seguito riepiloga il tipo di connessione che viene fornito da ciascun partner {{site.data.keyword.cloud_notm}}. 

| Partner | Tipo di interconnessione |  
|-------|-------|
| AT&T NetBond® for Cloud | Livello 3 |
| AT&T Cloud Gateway (formerly known as RedFringe)| Livello 3 |
| Bell Canada | Livello 3 | 
| British Telecom | Livello 3 | 
| CenturyLink IP VPN | Livello 3 | 
| CenturyLink Dynamic Connections | Livello 2 | 
| Chief Telecomm | Livello 2 |
| Colt | Livello 2 | 
| Console Connect by PCCW | Livello 2 |
| Digital Realty Service Exchange | Livello 2 | 
| Epsilon | Livello 2 | 
| IBM BlueFringe | Livello 3 | 
| Intercloud | Livello 3 |
| Megaport | Livello 2 |
| MWS GNPP | Livello 3 |
| Neutrona | Livello 2 |
| NTT | Livello 3 |
| PacketFabric | Livello 2 |
| Softbank | Livello 3 |
| SES Networks | Livello 2 |
| Tata IZO™ Private Connect  | Livello 3 | 
| Telia | Livello 3 |
| Telstra | Livello 3 |
| Tokai | Livello 2 | 
| Verizon SCI| Livello 3 |
| Zayo Cloud Link | Livello 2 |
