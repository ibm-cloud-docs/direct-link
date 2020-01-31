---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: overview, connectivity, private network, site-to-site, Exchange, Connect, Dedicated, Hosting, OSI, Layer-3, partners, NNI, latency, backbone

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

# Direct Link on Classic offerings
{: #overview-of-direct-link-offerings}

{{site.data.keyword.cloud}} Direct Link offerings provide connectivity from an external source into a customer's {{site.data.keyword.cloud_notm}} private network. Direct Link can be viewed as an alternative to a traditional site-to-site VPN solution, which is designed for customers that need more consistent, higher-throughput connectivity between a remote network and their {{site.data.keyword.cloud_notm}} environments.
{:shortdesc}

Four types of connections are available:

* **Direct Link Connect on Classic** allows customers to use a connection through our Carrier partners who own and operate a facility-based network. A Connect provider is a network service provider (NSP) that is already connected to the {{site.data.keyword.cloud_notm}} network, by using multi-tenant, high capacity links (also known as a _network-to-network interface_, or NNI). Customers typically can purchase a virtual circuit at this provider, bringing connectivity at a reduced cost, because the physical connectivity from {{site.data.keyword.cloud_notm}} to the Connect provider is in place already, shared among other customers.

* **Direct Link Dedicated on Classic** allows customers to terminate a single-tenant, fiber-based cross-connect into the {{site.data.keyword.cloud_notm}} network. This offering can be used by customers with colocation premises that are next to {{site.data.keyword.cloud_notm}} PoPs and data centers; as well as network service providers that deliver circuits to customer premises or other data centers.

* **Direct Link Dedicated Hosting on Classic** provides connectivity similar to Direct Link Dedicated, but the connection point is next to a {{site.data.keyword.cloud_notm}} data center, which improves latency for higher-performance use cases. {{site.data.keyword.cloud_notm}} offers various customizable colocation services with this solution.

* **Direct Link Exchange on Classic** allows customers to use an Exchange provider to deliver connectivity to their {{site.data.keyword.cloud_notm}}. An Exchange provider is a colocation or data center provider that is already connected to the {{site.data.keyword.cloud_notm}} network, by using multi-tenant, high capacity links (also known as a _network-to-network interface_, or NNI). Customers typically can purchase a virtual circuit at this provider, bringing connectivity at a reduced cost, because the physical connectivity from {{site.data.keyword.cloud_notm}} to the Exchange provider is in place already, shared among other customers.

The {{site.data.keyword.cloud_notm}} Direct Link service is a routed, OSI Layer-3 service. It offers a direct connection to the {{site.data.keyword.cloud_notm}} private network backbone, with low latency and speeds up to 10 Gbps.
For increased flexibility in creating this Layer-3 connectivity, {{site.data.keyword.cloud_notm}} Direct Link enables customers to use:
 * Dual IP for remote hosts
 * NAT
 * Tunneling for BYOIP

For detailed descriptions of each offering, see [About {{site.data.keyword.cloud_notm}} Direct Link](/docs/direct-link?topic=direct-link-about-ibm-cloud-direct-link).
