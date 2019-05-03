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

# Comparing Layer-2 and Layer-3 connections for Direct Link
{: #comparing-layer-2-layer-3}

{{site.data.keyword.cloud}} Direct Link accepts OSI Layer-2 and Layer-3 partner interconnections from network service providers (NSPs). Some network service providers offer services for both of these layers on different networks, however some providers may have chosen **not** to interconnect all of their networks into {{site.data.keyword.cloud_notm}}. 

When planning your {{site.data.keyword.cloud_notm}} Direct Link deployment, consider the characteristics associated with Layer-2 and Layer-3 connections, so you can create a deployment that best suits your needs.

## Considerations for Layer-2 connections
{: #layer-2-networks}

For each VLAN-based Virtual Circuit--which you will create with a Layer-2 partner interconnection--you must configure and establish a BGP session between your on-premises routers and the IBM Cloud XCR. IBM Cloud will provide you with a `/31` IPv4 assignment to establish a BGP session with your router.

* Layer-2 networks offer options for simple one-to-one connections between enterprises and {{site.data.keyword.cloud_notm}}. 
* Layer-2 services rely on VLANs instead of IP addresses. 
* Layer-2 services may be lower cost and lower latency, and they may consume less overhead than Layer-3 services. 
* Layer-2 networks do not impose restrictions on the Layer-3 features that an enterprise can enable.

## Considerations for Layer-3 connections
{: #layer-3-networks}

For Layer-3 connections, for each Virtual Circuit, your service provider establishes a BGP session between IBM Cloud XCRs and the provider's edge routers. You will not need to configure BGP with IBM Cloud for your on-premises router, because your service provider will manage the BGP configuration to IBM Cloud.

* Layer-3 IP VPN or AVPN networks enable "any-to-any" connectivity. 
* Layer-3 networks require the network service provider to maintain a BGP session between the enterprise and {{site.data.keyword.cloud_notm}}. 
* Certain network service providers may restrict certain functionalities across their network when using Layer-3 connections, such as ASN prepend, GRE tunneling, and so forth. Be sure to check with your provider about possible restrictions.

## Partner interconnection table
{: #partner-interconnection-table}

The following table summarizes the type of connections that each {{site.data.keyword.cloud_notm}} partner provides. 

| Partners | Interconnection type |  
|-------|-------|
| AT&T NetBond® for Cloud | Layer 3 |
| AT&T Cloud Gateway (formerly known as RedFringe)| Layer 3 |
| Bell Canada | Layer 3 | 
| British Telecom | Layer 3  | 
| CenturyLink IP VPN | Layer 3 | 
| CenturyLink Dynamic Connections | Layer 2 | 
| Chief Telecomm | Layer 2 |
| Colt | Layer 2  | 
| Console Connect by PCCW | Layer 2 |
| Digital Realty Service Exchange | Layer 2 | 
| Epsilon | Layer 2 | 
| IBM BlueFringe | Layer 3 | 
| Intercloud | Layer 3 |
| Megaport | Layer 2 |
| MWS GNPP | Layer 3 |
| Neutrona | Layer 2 |
| NTT | Layer 3 |
| PacketFabric | Layer 2  |
| Softbank | Layer 3 |
| SES Networks | Layer 2  |
| Tata IZO™ Private Connect  | Layer 3 | 
| Telia | Layer 3 |
| Telstra | Layer 3 |
| Tokai | Layer 2 | 
| Verizon SCI| Layer 3 |
| Zayo Cloud Link | Layer 2 |
