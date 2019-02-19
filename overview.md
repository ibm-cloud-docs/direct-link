---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-01-18"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Overview of Direct Link Offerings

The {{site.data.keyword.cloud}} Direct Link offerings provide connectivity from an external source into a customer's IBM Cloud private network. Direct Link can be viewed as an alternative to a traditional site-to-site VPN solution, designed for customers that need more consistent, higher-throughput connectivity between a remote network and their IBM Cloud environments. Four types of connections are available:
 
 * **IBM Cloud Direct Link Exchange** lets customers leverage an Exchange provider to deliver connectivity to their IBM Cloud. An Exchange provider is a carrier or network provider that is already connected to the IBM Cloud network, using multi-tenant, high capacity links. Customers typically can purchase a virtual circuit at this provider, bringing connectivity at a reduced cost, because the physical connectivity from {{site.data.keyword.BluSoftlayer_notm}} to the Exchange provider is in place already, shared amongst other customers.
 
 * **IBM Cloud Direct Link Connect** lets customers leverage a connection through our partners who own and operate a facility-based network. With IBM Cloud Direct Link Connect, IBM and the partner connect to customers at Layer 2 and 3 through dual, Layer-2 10G NNIs.
 
 * **IBM Cloud Direct Link Dedicated** lets customers terminate a dedicated, single-mode, fiber cross-connect into their own IBM Cloud private network.
 
 * **IBM Cloud Direct Link Dedicated Hosting** provides connectivity similar to IBM Cloud Direct Link Dedicated, but the connection point is adjacent to a {{site.data.keyword.BluSoftlayer_notm}} data center, which improves latency for higher-performance use cases. IBM Cloud offers a variety of customizable co-location services with this solution.
  
The IBM Cloud Direct Link service is a routed, OSI Layer-3 service. It offers a direct connection to the {{site.data.keyword.BluSoftlayer_notm}} private network backbone, with low latency and speeds up to 10Gbps.
For increased flexibility in creating this Layer-3 connectivity, IBM Cloud Direct Link enables customers to utilize:
 * Dual IP for remote hosts
 * NAT
 * Tunneling for BYOIP
 
 For detailed descriptions of each offering, see [About IBM Cloud Direct Link](/docs/infrastructure/direct-link?topic=direct-link-about-ibm-cloud-direct-link).
