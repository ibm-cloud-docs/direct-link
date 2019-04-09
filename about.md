---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-01"

keywords: hybrid, solutions, features, benefits, port speed, cross-connect, use cases, latency, routing, options, colocation

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# About IBM Cloud Direct Link
{: #about-ibm-cloud-direct-link}

This section lets you browse more details about the key features and benefits of each of the four {{site.data.keyword.cloud}}
 Direct Link solutions.
  * [**IBM Cloud Direct Link Exchange**](#direct-link-exchange-solution)
  * [**IBM Cloud Direct Link Connect**](#direct-link-connect-solution)
  * [**IBM Cloud Direct Link Dedicated**](#direct-link-dedicated-solution)
  * [**IBM Cloud Direct Link Dedicated Hosting**](#direct-link-dedicated-hosting-solution)

## The IBM Cloud Direct Link Exchange solution
{: #direct-link-exchange-solution}

The IBM Cloud Direct Link Exchange solution lets customers utilize a Cloud Exchange provider to deliver connectivity to {{site.data.keyword.cloud_notm}} locations. This offering typically provides connectivity at a reduced cost, because the physical connectivity from {{site.data.keyword.cloud_notm}} to the Cloud Exchange Provider is already in place, shared among other customers.

**Common Use Cases:** _Best for hybrid workloads, cross-provider workloads, large or frequent data transfers with high-egress bandwidth, private workloads, and environment administration.  This option usually is selected when the desired PoP location already has the desired IBM Cloud Direct Link Exchange provider._

![Figure 1](/images/Direct-Link-Exchange.png)

 * **Termination Location:** {{site.data.keyword.cloud_notm}} point of presence (PoP).

 * **Typical Deployment Time:** For Equinix providers, typical deployment time will be in hours. For other providers, 5-10 days after circuit reaches the exchange. Deployment time can possibly be 30 to 60 days overall, depending on your location and requirements when ordering a circuit from an NSP or carrier.

 * **Cross-Connect Details:** Physical cross-connects for the secure Cloud Exchange interconnect are maintained between {{site.data.keyword.cloud_notm}} and the Cloud Exchange provider. Customers request a "Virtual Circuit" from the Cloud Exchange Provider, which establishes logical connectivity to {{site.data.keyword.cloud_notm}}, once the customer is interconnected to the Cloud Exchange Provider.

 * **Port Speed Options:** Select 50Mbps, 100Mbps, 200Mbps, 500Mbps, 1Gbps, 2Gbps, or 5Gbps.

 * **Approximate Latency:** Latency is approximately 1.5ms within the local area (datacenters with the same three-letter prefix, such as DAL, AMS, MEL). See http://lg.softlayer.com/ for live PoP-to-PoP (P2P) location latency measurements.

 * **IBM Colocation Services:** None.

 * **Redundancy:** {{site.data.keyword.cloud_notm}} provides connections to two (2) diverse cross-connect routers (XCRs) as part of the product. To establish redundant connectivity, customers must configure BGP on each Direct Link connection as they prefer. Examples include options such as these: _prefer Lowest MED_, _prefer highest local-preference_, or _prefer shorter AS paths_.

 * **Local/Global Routing Options:** The Local Routing option is the default routing option. It provides access to datacenters within the same Market as the Direct Link PoP (denoted, for example, as DAL, AMS, or MEL). The Global Routing option is required as an add-on to connect your IBM cloud resources to other IBM Cloud resources in datacenters outside the local market. It provides a way to share workloads between IBM Cloud resources (for example Dallas to Ashburn, or Dallas to Frankfurt).
 
## The IBM Cloud Direct Link Connect solution
{: #direct-link-connect-solution}

**Common Use Cases** The IBM Cloud Direct Link Connect solution lets customers leverage a network service provider (NSP) to deliver connectivity to {{site.data.keyword.cloud_notm}} locations. This offering typically provides connectivity at a reduced cost, because the physical connectivity from {{site.data.keyword.cloud_notm}} to the Network Service Provider is already in place, shared among other customers.

![Figure 2](/images/Direct-Link-Connect.png)

* **Termination Location:** {{site.data.keyword.cloud_notm}} point of presence (PoP).

* **Typical Deployment Time:** 5 to 10 days after circuit reaches the exchange. Deployment time can possibly be 30 to 60 days overall, depending on your location and requirements when ordering a circuit from an NSP or carrier.

* **Cross-Connect Details:** Physical cross-connects for the secure Direct Link Connect interconnect are maintained between {{site.data.keyword.cloud_notm}} and the Connect provider. Customers request a "Virtual Circuit" from the Cloud Connect provider, which establishes logical connectivity to {{site.data.keyword.cloud_notm}}, once the customer is interconnected to the Cloud Connect provider.

* **Port Speed Options:** Select 50Mbps, 100Mbps, 200Mbps, 500Mbps, 1Gbps, 2Gbps, or 5Gbps.

* **Approximate Latency:** Latency is approximately 1.5ms within the local area (datacenters with the same three-letter prefix, such as DAL, AMS, MEL). See http://lg.softlayer.com/ for live PoP-to-PoP (P2P) location latency measurements.

* **IBM Colocation Services:** None.

* **Redundancy:** {{site.data.keyword.cloud_notm}} provides connections to two (2) diverse cross-connect routers (XCRs) as part of the product. To establish redundant connectivity, customers must configure BGP on each Direct Link connection as they prefer. Examples include options such as these: _prefer Lowest MED_, _prefer highest local-preference_, or _prefer shorter AS paths_.

* **Local/Global Routing Options:** The Local Routing option is the default routing option. It provides access to datacenters within the same market as the Direct Link PoP (denoted, for example, as DAL, AMS, or MEL). The Global Routing option is required as an add-on to connect your IBM cloud resources to other IBM Cloud resources in datacenters outside the local market. It is used to share workloads between IBM Cloud resources (for example Dallas to Ashburn, or Dallas to Frankfurt).

## The IBM Cloud Direct Link Dedicated solution
{: #direct-link-dedicated-solution}

The IBM Cloud Direct Link Dedicated solution lets customers terminate a single-tenant, fiber-based cross-connect into their own {{site.data.keyword.cloud_notm}} private network connection. This offering can be utilized by customers with co-location facilities adjacent to IBM Cloud PoPs and datacenters, as well as by network service providers that deliver circuits to customer premises or to other datacenters.

 **Common Use Cases:** _Best for working with hybrid workloads, cross-provider workloads, large or frequent data transfers, private workloads, and environment administration. This option usually is selected: (1) when the desired PoP does not have the desired Exchange or network service provider, (2) for high-performance workloads requiring high throughput, or (3) for compliance requirements that cannot be satisfied by either the IBM Cloud Direct Link Exchange or Connect implementation model._
 
 **Use Case 1: Customer facility to IBM Cloud.**

![Figure 3](/images/Direct-link-Dedicated.png)

**Use Case 2: Customer colocation to IBM Cloud.**

![Figure 3B](/images/dedicated-model-colo.png)

 * **Termination Location:** {{site.data.keyword.cloud_notm}} point of presence (PoP) or Data Center (DC).

 * **Typical Deployment Time:** 10 to 15 business days after the new circuit reaches the POP. Deployment time can possibly be 30-60 days overall, depending on your location and requirements when ordering a circuit from a NSP or carrier.

 * **Cross-Connect Details:** {{site.data.keyword.cloud_notm}} provides a Letter of Authorization (LOA) that a customer uses to order fiber Ethernet (Single-Mode Fiber only, either 1Gig-LX or 10Gig-LR optics) that runs from a customer cage or provider cage to the {{site.data.keyword.cloud_notm}} CFA termination point, which will be tied down to the cross-connect router (XCR) infrastructure. The media must be a 1310nm wavelength optic.

 * **Port Speed Options:** Select 1Gbps, 2Gbps, 5Gbps, or 10Gbps.

 * **Approximate Latency:** Latency is approxiately 1.5ms within the local area (datacenters with the same three-letter prefix, such as DAL, AMS, MEL).  See http://lg.softlayer.com/ for live PoP-to-PoP (P2P) location latency measurements.

 * **IBM Colocation Services:** None.

 * **Redundancy:** {{site.data.keyword.cloud_notm}} provides connections to two (2) diverse cross-connect routers (XCRs) as part of the product. To establish redundant connectivity, customers must configure BGP on each Direct Link connection as they prefer. Examples include options such as these: _prefer Lowest MED_, _prefer highest local-preference_, or _prefer shorter AS paths_.

 * **Local/Global Routing Options:** The Local Routing option is the default routing option. It provides access to datacenters within the same market as the Direct Link PoP (denoted, for example, as DAL, AMS, or MEL). The Global Routing option is required as an add-on to connect your IBM cloud resources to other IBM Cloud resources in datacenters outside the local market. It provides a way to share workloads between IBM Cloud resources (for example Dallas to Ashburn, or Dallas to Frankfurt).

## The IBM Cloud Direct Link Dedicated Hosting solution
{: #direct-link-dedicated-hosting-solution}

The IBM Cloud Direct Link Dedicated Hosting solution provides connectivity similar to IBM Cloud Direct Link Dedicated, but the connection point is adjacent to a {{site.data.keyword.cloud_notm}} data center, which improves latency for higher performance use cases. IBM Cloud offers a variety of customizable co-location services with this solution, with simple pricing.

**Common Use Cases:** _Best for working with non-standard compute technologies, for dedicated storage requirements, or for leveraging existing IT investments._

![Figure 4](/images/Direct-Link-Dedicated-Hosting.png)

* **Termination Location:** {{site.data.keyword.cloud_notm}} Data Center (DC).

 * **Typical Deployment Time:** 30-60 days after all requirements are finalized and contracts are executed.

 * **Cross-Connect Details:** {{site.data.keyword.cloud_notm}} provides 1G or 10G fiber connections from the {{site.data.keyword.cloud_notm}} cross-connect router (XCR) infrastructure to the customer's colocation environment as part of the deployment.  If colocation services are not requested (if existing environments are connected already), {{site.data.keyword.cloud_notm}} provides a Letter of Authorization (LOA) that a customer uses to order fiber Ethernet (Single-Mode Fiber only, either 1Gig-LX or 10Gig-LR optics) that runs from a customer cage to the {{site.data.keyword.cloud_notm}} CFA termination point, which will be tied down to the cross-connect router (XCR) infrastructure. The media must be a 1310nm wavelength optic.

 * **Port Speed Options:** Select 1Gbps, 2Gbps, 5Gbps, or 10Gbps.

 * **Approximate Latency:** Latency is approximately 0.5ms within the local datacenter.

 * **IBM Colocation Services:** Yes.

 * **Redundancy:** {{site.data.keyword.cloud_notm}} provides connections to two (2) diverse cross-connect routers (XCRs) as part of the product. To establish redundant connectivity, customers must configure BGP on each Direct Link connection as they prefer. Examples include options such as these: _prefer Lowest MED_, _prefer highest local-preference_, or _prefer shorter AS paths_.

 * **Local/Global Routing Options:** The Local Routing option is the default routing option. It provides access to datacenters within the same Market as the Direct Link PoP (denoted, for example, as DAL, AMS, or MEL). The Global Routing option is required as an add-on to connect your IBM cloud resources to other IBM Cloud resources in datacenters outside the local market. It is used to share workloads between IBM Cloud resources (for example Dallas to Ashburn, or Dallas to Frankfurt).
