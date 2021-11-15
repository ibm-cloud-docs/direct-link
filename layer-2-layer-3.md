---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-30"

keywords: 

subcollection: direct-link

---

{{site.data.keyword.attribute-definition-list}}

# Comparing Layer-2 and Layer-3 connections for Direct Link
{: #comparing-layer-2-layer-3}

{{site.data.keyword.cloud}} Direct Link accepts OSI Layer-2 and Layer-3 partner interconnections from network service providers (NSPs). Some network service providers offer services for both of these layers on different networks, however, some providers might choose **not** to interconnect all of their networks into {{site.data.keyword.cloud_notm}}.
{: shortdesc}

When planning your {{site.data.keyword.cloud_notm}} Direct Link deployment, consider the characteristics that are associated with Layer-2 and Layer-3 connections, so you can create a deployment that best suits your needs.

## Considerations for Layer-2 connections
{: #layer-2-networks}

For each VLAN-based virtual circuit, which you create with a Layer-2 partner interconnection, you must configure and establish a BGP session between your on-premises routers and the IBM Cloud XCR. IBM Cloud provides you with a `/31` IPv4 assignment to establish a BGP session with your router.

* Layer-2 networks offer options for simple one-to-one connections between enterprises and {{site.data.keyword.cloud_notm}}.
* Layer-2 services rely on VLANs instead of IP addresses.
* Layer-2 services might be lower cost and lower latency, and they might consume less overhead than Layer-3 services.
* Layer-2 networks do not impose restrictions on the Layer-3 features that an enterprise can enable.

## Considerations for Layer-3 connections
{: #layer-3-networks}

For Layer-3 connections, for each virtual circuit, your service provider establishes a BGP session between {{site.data.keyword.cloud_notm}} XCRs and the provider's edge routers. You do not need to configure BGP with {{site.data.keyword.cloud_notm}} for your on-premises router because your service provider manages the BGP configuration to {{site.data.keyword.cloud_notm}}. **This means when you order Direct Link Connect via the IBM Portal, you need to populate the Layer 3 providers ASN for the BGP session, not your customer ASN**

* Layer-3 IP VPN or AVPN networks enable "any-to-any" connectivity.
* Layer-3 networks require the network service provider to maintain a BGP session between the enterprise and {{site.data.keyword.cloud_notm}}.
* Certain network service providers might restrict certain functionalities across their network when using Layer-3 connections, such as ASN prepend, GRE tunneling, and so forth. Be sure to check with your provider about possible restrictions.

## Partner interconnection table
{: #partner-interconnection-table}

The following table summarizes the type of connections that each {{site.data.keyword.cloud_notm}} partner provides.

| Partners | Interconnection type |  
|-------|-------|
| AT&T NetBond for Cloud | **Layer 3** |
| AT&T Cloud Gateway (formerly known as RedFringe)| **Layer 3** |
| Bell Canada | **Layer 3** |
| British Telecom | **Layer 3**  |
| CenturyLink IP VPN | **Layer 3** |
| CenturyLink Dynamic Connections | Layer 2 |
| Chief Telecomm | Layer 2 |
| China Unicom | **Layer 3** |
| Colt | Layer 2  |
| Console Connect by PCCW | Layer 2 |
| Digital Realty Service Exchange | Layer 2 |
| Epsilon | Layer 2 |
| EU Networks | Layer 2 |
| IBM BlueFringe | **Layer 3** |
| Intercloud | **Layer 3** |
| IXReach | Layer 2 |
| Megaport | Layer 2 |
| Neutrona | Layer 2 |
| nextGen GNPP | **Layer 3** |
| NTT | **Layer 3** |
| Orange Business Services | **Layer 3** |
| PacketFabric | Layer 2  |
| Softbank | **Layer 3** |
| SES Networks | Layer 2  |
| Tata IZO™ Private Connect  | **Layer 3** |
| Telia | **Layer 3** |
| Telstra | **Layer 3** |
| Tokai | Layer 2 |
| Verizon SCI| **Layer 3** |
| Vodafone| **Layer 3** |
| Zayo Cloud Link | Layer 2 |
{: caption="Table 1. Partner interconnection table" caption-side="bottom"}
