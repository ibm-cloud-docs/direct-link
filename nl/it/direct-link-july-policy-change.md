---
copyright:
  years: 2018, 2019
lastupdated: "2019-04-02"

keywords: Intercloud, Frankfurt, PoPs, Connect, Exchange, Chennai, Equinix, Megaport, Kinx, diversity, Bluefringe, CenturyLink, BT, Sao Paulo, Tokyo, Japan, PCCW, Colt, blog, service provider, partner, Telia, Internexion, Packet Fabric, Global Routing, expanded, market

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:important: .important}

# Annuncio: la modifica della politica di instradamento globale inizia il 1° luglio

Effettivo a partire dal 1° luglio 2019 -  Modifica della politica di instradamento globale di IBM Direct Link
{: important}

Per migliorare l'esperienza del cliente e fornire un maggior valore, stiamo migliorando il servizio di instradamento globale di IBM Direct Link. I miglioramenti chiave includono:

* **Mercati locali ampliati:** stiamo implementando l'allineamento dei nostri siti a cui possono connettersi i clienti all'interno dei loro mercati locali. Stiamo allineando ogni sito PoP nella rete IBM Cloud per consentire ai clienti che si connettono a IBM Cloud nei loro siti PoP di connettersi alle risorse in uno o più dei loro data center che si trovano in tutto il mondo. 

* **Nuovo modello dei prezzi:** per allineare meglio i prezzi alle velocità di connessione selezionate, stiamo modificando il modello dei prezzi del nostro servizio di instradamento globale di IBM Direct Link.

* **Traffico Direct Link illimitato:** stiamo eliminando i costi aggiuntivi del traffico di rete per i clienti che hanno il loro instradamento locale o globale per il traffico di rete privata Direct Link tra i PoP e i data center di IBM Cloud globalmente. 

## Panoramica dell'instradamento globale di IBM Cloud Direct Link
{: #ibm-cloud-direct-link-global-routing-overview}

Tutte le offerte correnti di Direct Link includono l'instradamento locale senza costi aggiuntivi. Questo servizio include l'accesso ai data center nel mercato locale in cui si trova la connessione Direct Link. Fornisce traffico in entrata e in uscita illimitato tra le connessioni private Direct Link alle risorse IBM Cloud all'interno dell'account del cliente. Con l'opzione di instradamento locale, il traffico Direct Link è limitato ai servizi forniti da questo mercato locale. 

Per instradare il traffico al di fuori del mercato locale a cui è connesso Direct Link (PoP o data center), devi aggiungere l'opzione di instradamento globale che amplia l'accesso per includere tutti i data center IBM Cloud globalmente. 

L'instradamento globale si applica ai singoli servizi Direct Link. L'instradamento globale non si applica tramite aggregazione. Deve essere specificato in ogni servizio Direct Link che desidera connettersi al di fuori di un determinato mercato. 

## Mercati locali IBM Direct Link ampliati
{: #announce-expanded-ibm-direct-link-local-markets}

Stiamo ampliando i mercati locali Direct Link per fornire maggiori opzioni di instradamento locale ai nostri clienti globalmente. Di seguito vengono elencate le nuove assegnazioni di mercato locale: 

* Ora il mercato locale di Dallas includerà i PoP di Denver, Houston e Chicago.
* Ora il mercato locale di Washington DC includerà i PoP di New York, Atlanta e Miami.
* Ora il mercato locale di San Jose includerà il PoP di Los Angeles.
* Ora il mercato locale di Oslo includerà il PoP di Stoccolma.
* Ora il mercato locale di Sydney includerà il PoP di Perth.
* Il mercato locale di Hong Kong includerà il PoP di Taipei una volta avviato.
* Il mercato locale di Tokyo includerà il PoP di Osaka una volta avviato.
* Il mercato locale di Chennai includerà il PoP di Mumbai una volta avviato. 

Queste modifiche vengono descritte nelle tabelle disponibili al seguente indirizzo: https://cloud.ibm.com/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#expanded-ibm-direct-link-local-markets

## Modello dei prezzi dell'instradamento globale di IBM Cloud Direct Link
{: #announce-ibm-cloud-direct-link-global-routing-pricing-model}

Con tutte le offerte di IBM Cloud Direct Link, l'instradamento di rete all'interno di un mercato locale è standard. A partire dal 1° luglio 2019, i prezzi per l'opzione di instradamento globale vengono allineati alla velocità di connessione della connessione Direct Link. Questo allineamento fornisce un valore migliore ai clienti in tutte le velocità di connessione disponibili per le offerte Direct Link.

I prezzi si trovano all'indirizzo https://cloud.ibm.com/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-global-routing-add-on

## Costi aggiuntivi del transito di rete dell'instradamento globale di IBM Cloud Direct Link
{: #announce-ibm-cloud-direct-link-global-routing-network-transit-overage-charges}

Insieme a questo annuncio, stiamo ritirando i limiti del transito di rete e i costi aggiuntivi per i clienti con l'opzione di instradamento globale. I prezzi precedenti includevano le franchigie del transito di rete e i costi aggiuntivi per il traffico in uscita al di fuori del mercato locale del cliente. I nuovi prezzi eliminano questi costi del traffico di rete. A partire da questo annuncio, al traffico in entrata e in uscita nelle connessioni Direct Link non verranno addebitati costi aggiuntivi. 

## Data di validità
{: #announce-effective-date}

Queste modifiche entreranno in vigore a partire da lunedì 1° luglio 2019 e verranno applicate a tutti i nuovi ordini nel ciclo di fatturazione successivo dopo questo data. 

È importante tenere presente che con questa automazione aggiornata, tutti i circuiti Direct Link che richiedono l'instradamento globale devono essere aggiornati in modo appropriato prima di questa data. Gli upgrade o i downgrade di un servizio Direct Link produrranno l'automazione che si verifica se è presente l'instradamento globale. Se l'instradamento globale non è presente, il traffico nei circuiti Direct Link verrà limitato ai mercati locali. 

Consigliamo vivamente ai clienti di controllare il loro instradamento di IBM Cloud nei servizi Direct Link e di aprire ticket per correggere l'instradamento nei servizi Direct Link esistenti.
