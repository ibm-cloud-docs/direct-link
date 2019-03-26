---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-03-26"

keywords: overview, connectivity, private network, site-to-site, Exchange, Connect, Dedicated, Hosting, OSI, Layer-3, partners, NNI, latency, backbone

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Overview of Direct Link Offerings
{: #overview-of-direct-link-offerings}

The {{site.data.keyword.cloud}} Direct Link offerings provide connectivity from an external source into a customer's IBM Cloud private network. Direct Link can be viewed as an alternative to a traditional site-to-site VPN solution, designed for customers that need more consistent, higher-throughput connectivity between a remote network and their IBM Cloud environments. Four types of connections are available:
 
 * **IBM Cloud Direct Link Exchange** allows customers to utilize an Exchange provider to deliver connectivity to their IBM Cloud. An Exchange provider is a co-location or data center provider that is already connected to the IBM Cloud network, using multi-tenant, high capacity links (also known as a _network-to-network interface_, or NNI). Customers typically can purchase a virtual circuit at this provider, bringing connectivity at a reduced cost, because the physical connectivity from {{site.data.keyword.BluSoftlayer_notm}} to the Exchange provider is in place already, shared amongst other customers.
 
 * **IBM Cloud Direct Link Connect** allows customers to utilize a connection through our Carrier partners who own and operate a facility-based network. A Connect provider is a network service provider (NSP) that is already connected to the IBM Cloud network, using multi-tenant, high capacity links (also known as a _network-to-network interface_, or NNI). Customers typically can purchase a virtual circuit at this provider, bringing connectivity at a reduced cost, because the physical connectivity from {{site.data.keyword.BluSoftlayer_notm}} to the Connect provider is in place already, shared among other customers.
 
 * **IBM Cloud Direct Link Dedicated** allows customers to terminate a single-tenant, fiber-based cross-connect into the IBM Cloud network. This offering can be utilized by customers with co-location premises that are adjacent to IBM Cloud PoPs and data centers; as well as network service providers that deliver circuits to customer premises or other data centers.
 
 * **IBM Cloud Direct Link Dedicated Hosting** provides connectivity similar to IBM Cloud Direct Link Dedicated, but the connection point is adjacent to a {{site.data.keyword.BluSoftlayer_notm}} data center, which improves latency for higher-performance use cases. IBM Cloud offers a variety of customizable co-location services with this solution.
  
The IBM Cloud Direct Link service is a routed, OSI Layer-3 service. It offers a direct connection to the {{site.data.keyword.BluSoftlayer_notm}} private network backbone, with low latency and speeds up to 10Gbps.
For increased flexibility in creating this Layer-3 connectivity, IBM Cloud Direct Link enables customers to utilize:
 * Dual IP for remote hosts
 * NAT
 * Tunneling for BYOIP
 
 For detailed descriptions of each offering, see [About IBM Cloud Direct Link](/docs/infrastructure/direct-link?topic=direct-link-about-ibm-cloud-direct-link).
