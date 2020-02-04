---
copyright:
  years: 2018, 2019
lastupdated: "2019-06-24"

keywords: Intercloud, Frankfurt, PoPs, Connect, Exchange, Chennai, Equinix, Megaport, Kinx, diversity, Bluefringe, CenturyLink, BT, Sao Paulo, Tokyo, Japan, PCCW, Colt, blog, service provider, partner, Telia, Internexion, Packet Fabric, global routing, expanded, market

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:DomainName: data-hd-keyref="DomainName"}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:external: target="_blank" .external}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:term: .term}  
{:generic: data-hd-programlang="generic"}
{:download: .download}  

# Announcement: Global routing policy change

Effective 1 July 2019 -  IBM Direct Link global routing policy change
{: important}

To enhance customer experience and provide greater value, the IBM Direct Link global routing service includes the following key improvements:

* **Expanded local markets:** Implemented the alignment of the sites that customers can connect to within their local markets. Aligned each PoP site in the IBM Cloud network to allow customers, which connect to the IBM Cloud in the PoP sites, to connect to resources in the data centers that are located across the globe.

* **New pricing model:** To better align pricing to connection speeds selected, the pricing model of the IBM Direct Link global routing service changed.

* **Unlimited Direct Link traffic:** Removed the network traffic overage charges for customers that have either Local or Global routing for Direct Link private network traffic between IBM Cloud PoPs and data centers globally.

## IBM Cloud Direct Link global routing overview
{: #ibm-cloud-direct-link-global-routing-overview}

All current Direct Link offerings include local routing with no additional fees. This service includes access to data centers in the local market where the Direct Link connection is located. It provides unlimited ingress and egress traffic across Direct Link private connections to IBM Cloud resources within the customer’s account. With Local routing, Direct Link traffic is restricted to the services provided by this local market.

To route network traffic outside of the local market to which the Direct Link is connected (PoP or data center), you must add the Global routing option, which expands access to include all of IBM Cloud data centers globally.

Global routing is applied to individual Direct Link services. Global routing is not applied via aggregation. It must be specified on each Direct Link service desiring connectivity outside of a given market.

## Expanded IBM Direct Link local markets
{: #announce-expanded-ibm-direct-link-local-markets}

We're expanding the Direct Link local markets to provide more local routing options to our customers globally.

New local market assignments:

* The Dallas local market includes Denver, Houston, and Chicago PoPs.
* The Washington DC local market includes New York, Atlanta, and Miami PoPs.
* The San Jose local market includes the Los Angeles PoP.
* The Oslo local market includes the Stockholm PoP.
* The Sydney local market includes the Perth PoP.
* The Hong Kong local market includes the Taipei PoP once launched.
* The Tokyo local market includes the Osaka PoP.
* The Chennai local market includes the Mumbai PoP once launched.

These changes are outlined in tables that are found at [Expanded IBM Direct Link local markets](/docs/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#expanded-ibm-cloud-direct-link-local-markets).

## IBM Cloud Direct Link global routing pricing model
{: #announce-ibm-cloud-direct-link-global-routing-pricing-model}

With all IBM Cloud Direct Link offerings, network routing within a local market is standard. Effective on 1 July 2019, pricing for the Global routing option is being aligned to the connection speed of the Direct Link connection. This alignment provides better value to customers across all connection speeds available for Direct Link offerings.

Pricing is at [Pricing for global routing add-on](/docs/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-global-routing-add-on).

## IBM Cloud Direct Link global routing network transit overage charges
{: #announce-ibm-cloud-direct-link-global-routing-network-transit-overage-charges}

Along with this announcement, IBM is withdrawing the network transit limits and overage charges for customers with the Global routing option. Previous pricing included network transit allowances and overage charges for egress traffic outside of the customer’s local market. New pricing eliminates these network traffic charges. Effective with this announcement, ingress and egress traffic across Direct Link connections do not incur overages.

## Effective date
{: #announce-effective-date}

These changes are effective on Monday, July 1, 2019 and will be applied to all new orders on the next billing cycle after this date.

It is important to note that with this updated automation, you should update any Direct Link circuits that require global routing before this date. Any upgrades or downgrades of a Direct Link service results in automation that verifies whether global routing is present. If global routing is not present, any traffic across Direct Link circuits is restricted to the local markets.

IBM strongly encourages customers to review their {{site.data.keyword.cloud_notm}} routing on Direct Link services, and  open cases to remediate routing on existing Direct Link services.
