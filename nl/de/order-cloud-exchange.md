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

# Vorgehensweise zur Bestellung von IBM Cloud Direct Link Exchange
{: # how-to-order-ibm-cloud-direct-link-exchange}

1. Überprüfen Sie die Funktionalität Ihres Netzbetreibers zum Erreichen des geeigneten Bereitstellungspunkts und zur Querverbindung mit dem zugehörigen Exchange-Provider.
2. Verwenden Sie das [Kundenportal ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com/), um eine Anforderung für {{site.data.keyword.cloud}} Direct Link Exchange zu öffnen und die angeforderten Informationen auszufüllen. (Unterstützung von IBM Sales Engineers kann angefordert werden.) Wenn Sie den Equinix-Provider verwenden, können Sie die [automatisierte Bestellung](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix) nutzen.
3. Wenden Sie sich an Ihren Exchange-Provider und vereinbaren Sie Konnektivität für Ihren Datenaustausch.
4. Bestellen Sie Konnektivität zwischen Ihrem Netzbetreiber und dem Exchange-Provider.
5. Bestellen Sie eine "virtuelle Verbindung" durch den Exchange-Provider und verweisen Sie auf die Ticket-ID der {{site.data.keyword.BluSoftlayer_notm}} Direct Link-Anforderung als Ihre "Anforderungs-ID" oder "Berechtigungs-ID".
6. Die IP-Zuordnung für die Netzinfrastruktur von {{site.data.keyword.BluSoftlayer_notm}} erfolgt innerhalb von drei Werktagen nach erfolgreicher Abwicklung der Anforderung für eine virtuelle Verbindung.
 
## Standorte
{: #exchange-locations}
 
 In der Tabelle sind die IBM Cloud-Rechenzentren aufgeführt, die Direct Link Exchange-Konnektivität bieten:
 
| Exchange-Provider	| Code für IBM Rechenzentrum |
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

* Demnächst verfügbar

## Preise
{: #exchange-pricing}

Informationen zu Preisen finden Sie im [Preisdokument](/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-direct-link-exchange).
