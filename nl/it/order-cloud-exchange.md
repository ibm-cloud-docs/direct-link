---

copyright:
  years: 2017, 2018
lastupdated: "2018-06-25"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Come ordinare IBM Cloud Direct Link Exchange

1. Verifica le funzionalità del tuo provider di rete per raggiungere la connessione trasversale e il PoP appropriati nel provider Exchange associato.
2. Utilizza [Customer Portal ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/) per aprire una richiesta IBM Cloud Direct Link Exchange e compilare le informazioni richieste. (Può essere richiesta assistenza dagli ingegneri delle vendite di IBM.) Se utilizzi il provider Equinix, puoi utilizzare l'[ordine automatizzato](cloud-exchange-automation.html).
3. Contatta il tuo provider Exchange e negozia la connettività del tuo scambio.
4. Ordina la connettività tra il tuo provider di rete e il provider Exchange.
5. Ordina un "circuito virtuale" tramite il provider Exchange e fai riferimento all'ID del ticket della richiesta {{site.data.keyword.BluSoftlayer_notm}} Direct Link come il tuo "ID richiesta" o "ID autorizzazione"
6. L'assegnazione dell'IP nell'infrastruttura di rete {{site.data.keyword.BluSoftlayer_notm}} sarà completata in 3 giorni lavorativi dopo il completamento della richiesta del circuito virtuale.
 
## Ubicazioni
 
 La tabella mostra i data center di IBM Cloud che offrono la connettività Direct Link Exchange:
 
| Provider Exchange	| Codice data center IBM |
|-------------|-----------------------|
| AT Tokyo	| TOK02 |
| Ascenty | SAO01* |
| Cologix	| MON02, TOR02 |
| Equinix	| HKG01,SNG02, SYD02, TOK01, AMS02, PAR02, CHI01, DAL03, NYC02, NYC03, SAO02, SJC02, TOR02, WDC02, LON01, FRA03 |							
| InterXion	| FRA01, STO01 |
| KINX	| SEO02 |
| NextDC | 	MEL02* |
| SK C&C | 	SEO01 |

* Coming Soon

## Prezzi

Per informazioni sui prezzi, fai riferimento al [documento dei prezzi](pricing.html).
