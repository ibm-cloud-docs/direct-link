---

copyright:
  years: 2017
lastupdated: "2017-09-08"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Overview of Features

The Direct Link offerings provide connectivity from an external source into a customer's IBM Cloud private network. Direct Link can be viewed as an alternative to a traditional site-to-site VPN solution, designed for customers that need more consistent, higher-throughput connectivity between a remote network and their IBM Cloud environments. Three types of connections are available:
 
 * **Direct Link Cloud Exchange** lets customers leverage a Cloud Exchange provider to deliver connectivity to their IBM Cloud. A Cloud Exchange provider is a carrier or network provider that is already connected to the IBM Cloud network, using multi-tenant, high capacity links. Customers typically can purchase a virtual circuit at this provider, bringing connectivity at a reduced cost, because the physical connectivity from {{site.data.keyword.BluSoftlayer_notm}} to the Cloud Exchange Provider is in place already, shared amongst other customers.
 
 * **Direct Link Network Service Provider (NSP)** lets customers terminate a dedicated, single-mode, fiber cross-connect into their own IBM Cloud private network.
 
 * **Direct Link Colocation** provides connectivity similar to Direct Link NSP, but the connection point is adjacent to a {{site.data.keyword.BluSoftlayer_notm}} data center, which improves latency for higher-performance use cases. IBM Cloud offers a variety of customizable co-location services with this solution.
  
The IBM Cloud Direct Link service is a routed, OSI Layer-3 service. It offers a direct connection to the {{site.data.keyword.BluSoftlayer_notm}} private network backbone, with low latency and speeds up to 10Gbps.
For increased flexibility in creating this Layer-3 connectivity, Direct Link enables customers to utilize:
 * Dual IP for remote hosts
 * NAT
 * Tunneling for BYOIP
