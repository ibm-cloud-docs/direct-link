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

# How to order IBM Cloud Direct Link Exchange
{: # how-to-order-ibm-cloud-direct-link-exchange}

1. Verify your network provider's capabilities to reach the appropriate PoP and cross-connect into the associated Exchange provider.
2. Use the [Customer Portal ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/) to open an {{site.data.keyword.cloud}} Direct Link Exchange request and complete the requested information. (Assistance from IBM sales engineers can be requested.) If you use the Equinix provider, you can use [automated ordering](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix).
3. Contact your Exchange provider and negotiate connectivity to your exchange.
4. Order connectivity between your network provider and the Exchange provider.
5. Order a "virtual circuit" through the Exchange provider, and refer the Ticket ID of the {{site.data.keyword.BluSoftlayer_notm}} Direct Link request as your "Request ID" or "Authorization ID"
6. IP assignment on the {{site.data.keyword.BluSoftlayer_notm}} networking infrastructure will be completed within 3 business days after the virtual circuit request is complete.
 
## Locations
{: #exchange-locations}
 
 The table shows which IBM Cloud datacenters offer Direct Link Exchange connectivity:
 
| Exchange Provider	| IBM Data Center Code |
|-------------|-----------------------|
| AT Tokyo | Tokyo 2 |
| Ascenty | Sao Paulo 1* |
| Cologix | Montreal 2, Toronto 2 |
| Cyrus One | Dallas 13 |
| DE-CIX | Frankfurt 3 |
| Equinix | **APAC:** Hong Kong 1,Singapore 2, Sydney 2, Tokyo 1, **EU:** Amsterdam 2, Frankfurt 3,London 1, Paris 2, **Americas:** Chicago 1, Dallas 3, New York City 2, New York City 3, Sao Paulo 2, San Jose 2, Toronto 2, Washington DC 2,  |							
| InterXion | Frankfurt 1, Stockholm 1 |
| KINX	| Seoul 2 |
| NextDC | Melbourne 2, Sydney 3 |
| SK C&C | Seoul 1 |

* Coming Soon

## Pricing
{: #exchange-pricing}

For pricing information, please refer to the [pricing document](/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-direct-link-exchange).
