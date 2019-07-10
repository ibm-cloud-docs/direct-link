---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: order, provider, capabilities, Exchange, cross-connect, locations, PoP, datacenter, data, center, pricing

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Come ordinare IBM Cloud Direct Link Exchange
{: # how-to-order-ibm-cloud-direct-link-exchange}

1. Verifica le funzionalità del tuo provider di rete per raggiungere la connessione trasversale e il PoP appropriati nel provider Exchange associato.
2. Utilizza [Customer Portal ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/) per aprire una richiesta {{site.data.keyword.cloud}} Direct Link Exchange e compilare le informazioni richieste. (Può essere richiesta assistenza dagli ingegneri delle vendite di IBM.) Se utilizzi il provider Equinix, puoi utilizzare l'[ordine automatizzato](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix).
3. Contatta il tuo provider Exchange e negozia la connettività del tuo scambio.
4. Ordina la connettività tra il tuo provider di rete e il provider Exchange.
5. Ordina un "circuito virtuale" tramite il provider Exchange e fai riferimento all'ID del ticket della richiesta {{site.data.keyword.BluSoftlayer_notm}} Direct Link come il tuo "ID richiesta" o "ID autorizzazione"
6. L'assegnazione dell'IP nell'infrastruttura di rete {{site.data.keyword.BluSoftlayer_notm}} sarà completata in 3 giorni lavorativi dopo il completamento della richiesta del circuito virtuale.
 
## Ubicazioni
{: #exchange-locations}
 
 La tabella mostra i data center di IBM Cloud che offrono la connettività Direct Link Exchange:
 
| Provider Exchange	| Codice data center IBM |
|-------------|-----------------------|
| AT Tokyo | Tokyo 2 |
| Ascenty | Sao Paulo 1* |
| Cologix | Montreal 2, Toronto 2 |
| Cyrus One | Dallas 13 |
| DE-CIX | Frankfurt 3 |
| Equinix | Hong Kong 1,Singapore 2, Sydney 2, Tokyo 1, Amsterdam 2, Paris 2, Chicago 1, Dallas 3, New York City 2, New York City 3, Sao Paulo 2, San Jose 2, Toronto 2, Washington DC 2, London 1, Frankfurt 3 |							
| InterXion | Frankfurt 1, Stockholm 1 |
| KINX	| Seoul 2 |
| NextDC | Melbourne 2, Sydney 3 |
| SK C&C | Seoul 1 |

* Coming Soon

## Prezzi
{: #exchange-pricing}

Per informazioni sui prezzi, fai riferimento al [documento dei prezzi](/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-direct-link-exchange).
