---
copyright:
  years: 2018, 2019
lastupdated: "2019-03-28"

keywords: Intercloud, Frankfurt, PoPs, Connect, Exchange, Chennai, Equinix, Megaport, Kinx, diversity, Bluefringe, CenturyLink, BT, Sao Paulo, Tokyo, Japan, PCCW, Colt, blog, service provider, partner, Telia, Internexion, Packet Fabric, Global Routing, expanded, market

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:important: .important}

# Announcement: Global Routing Policy Change Begins July 1

Effective July 1, 2019 -  IBM Direct Link Global Routing Policy Change
{: important}

To improve customer experience and provide greater value, we are enhancing the IBM Direct Link Global Routing Service. The key improvements include:

* **Expanded Local Markets:** We’re implementing the alignment of our sites that customers can connect to within their Local Markets. We are aligning each PoP site in the IBM Cloud network to allow customers connecting to the IBM Cloud in our PoP sites to connect to resources in one or more of our Data Centers located across the globe.

* **New pricing model:** To better align pricing to connection speeds selected, we’re changing the pricing model of our IBM Direct Link Global Routing service.

* **Unlimited Direct Link Traffic:** We’re removing the network traffic overage charges for customers that have either Local or Global routing for Direct Link private network traffic between IBM Cloud PoPs and Data Centers globally.

## IBM Cloud Direct Link Global Routing Overview
All current Direct Link offerings include Local routing with no additional fees. This service includes access to Data Centers in the Local Market where the Direct Link connection is located. It provides unlimited ingress and egress traffic across Direct Link private connections to IBM Cloud resources within the customer’s account. With the Local Routing option, Direct Link traffic is restricted to the services provided by this Local Market.

To route network traffic outside of the Local Market to which the Direct Link is connected (PoP or Data Center), you must add the Global Routing option, which expands access to include all of IBM Cloud Data Centers globally.

Global Routing is applied to individual Direct Link services. Global Routing is Not applied via aggregation. It must be specified on each Direct Link service desiring connectivity outside of a given market.

## Expanded IBM Direct Link Local Markets
We are expanding the Direct Link Local Markets to provide more local routing options to our customers globally. The new Local Market assignments are listed below:

* The Dallas local Market will now include Denver, Houston and Chicago PoPs.
* The Washington DC local Market will now include New York , Atlanta and Miami PoPs.
* The San Jose local market will now include the Los Angeles PoP .
* The Oslo local market will now include the Stockholm PoP.
* The Sydney local market will now include the Perth PoP.
* The Hong Kong local market will include the Taipei PoP once launched.
* The Tokyo local market will include the Osaka PoP once launched.
* The Chennai local market will include the Mumbai PoP once launched.

These changes are outlined in tables found at: https://cloud.ibm.com/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#expanded-ibm-direct-link-local-markets

## IBM Cloud Direct Link Global Routing Pricing Model
With all IBM Cloud Direct Link offerings, network routing within a Local Market is standard. Effective on  July 1st, 2019, pricing for the Global Routing option is being aligned to the connection speed of the Direct Link connection. This alignment will provide better value to customers across all connection speeds available for Direct Link offerings.

Pricing is located at https://cloud.ibm.com/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-global-routing-add-on

## IBM Cloud Direct Link Global Routing Network Transit Overage Charges
Along with this announcement, we are withdrawing the network transit limits and overage charges for customers with the Global Routing option. Previous pricing included network transit allowances and overage charges for egress traffic outside of the customer’s local market. New pricing eliminates these network traffic charges. Effective with this announcement, ingress and egress traffic across Direct Link connections will not incur overages.

## Effective Date
These changes are effective on Monday, July 1st , 2019 and will be applied to all new orders on the next billing cycle after this date.

It is important to note that with this updated automation, any Direct Link circuits requiring Global Routing should be updated appropriately before this date. Any upgrades or downgrades of a Direct Link service will result in automation that verifies whether Global Routing is present. If Global Routing is not present, any traffic across Direct Link circuits will be restricted to the local markets.

We strongly encourage customers to review their IBM Cloud routing on Direct Link services, and open tickets to remediate routing on existing Direct Link services.
