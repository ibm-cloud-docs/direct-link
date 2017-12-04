---

copyright:
  years: 2017
lastupdated: "2017-12-04"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# More about IBM Cloud Direct Link

This section gives more details about the key features and benefits of each of the three IBM Cloud Direct Link offerings.
  * [**IBM Cloud Direct Link Exchange**](#the-direct-link-cloud-exchange-solution)
  * [**IBM Cloud Direct Link Dedicated**](#the-direct-link-network-service-provider-solution)
  * [**IBM Cloud Direct Link Dedicated Hosting**](#the-direct-link-colocation-solution)

## The IBM Cloud Direct Link Exchange solution

The IBM Cloud Direct Link Exchange solution lets customers leverage a Cloud Exchange provider to deliver connectivity to {{site.data.keyword.BluSoftlayer_notm}}. This offering typically provides connectivity at a reduced cost, because the physical connectivity from {{site.data.keyword.BluSoftlayer_notm}} to the Cloud Exchange Provider is already in place, shared amongst other customers.

**Common Use Cases:** _Best for hybrid workloads, cross-provider workloads, large or frequent data transfers, private workloads, and environment administration.  This option usually is selected when the desired PoP already has the desired IBM Cloud Direct Link Exchange provider._

![Figure 1](/images/direct_link_cloud.jpg)

 * **Termination Location:** {{site.data.keyword.BluSoftlayer_notm}} point of presence (PoP).

 * **Typical Deployment Time:** 5-10 days after circuit reaches the exchange. Deployment time can possibly be 30-60 days overall, depending on your location and requirements.

 * **Cross-Connect Details:** Physical cross-connects for the Cloud Exchange interconnect are maintained between {{site.data.keyword.BluSoftlayer_notm}} and the Cloud Exchange provider. Customers request a "Virtual Circuit" from the Cloud Exchange Provider, which establishes logical connectivity to {{site.data.keyword.BluSoftlayer_notm}}, once they are interconnected to the Cloud Exchange Provider.

 * **Port Speed Options:** Select either 50Mbps, 100Mbps, 200Mbps, 500Mbps, and 1Gbps.

 * **Approximate Latency:** Latency is approximately 1.5ms within the local area (data centers with the same three-letter prefix, such as DAL, AMS, MEL, etc). See http://lg.softlayer.com/ for live PoP-to-PoP (P2P) latency measurements.

 * **Colocation Services:** None.

 * **Redundancy:** To establish redundancy for Direct Link Cloud Exchange, connectivity into 2+ locations is required, or the selection of a location with a secondary XCR available that can be leveraged by the Cloud Exchange provider.

 * **Local/Global Routing Options:** The Local Routing option provides access to data centers with the same three-letter prefix as the PoP (DAL, AMS, MEL, etc). The Global Routing option is required as an add-on to reach data centers outside those locations.

## The IBM Cloud Direct Link Dedicated solution

The IBM Cloud Direct Link Dedicated solution lets customers terminate a dedicated, single-mode, fiber cross-connect into their own {{site.data.keyword.BluSoftlayer_notm}} private network.

 **Common Use Cases:** _Best for working with hybrid workloads, cross-provider workloads, large or frequent data transfers, private workloads, and environment administration.  This option usually is selected: (1) when the desired PoP does not have the desired IBM Cloud Direct Link Exchange provider, (2) for high-performance workloads requiring high throughput, or (3) for compliance requirements that cannot be satisfied by the  IBM Cloud Direct Link Exchange implementation model._

![Figure 2](/images/direct_link_nsp.jpg)

 * **Termination Location:** {{site.data.keyword.BluSoftlayer_notm}} point of presence (PoP).

 * **Typical Deployment Time:** 10-15 business days after the new circuit reaches the POP. Deployment time can possibly be 30-60 days overall, depending on your location and requirements.

 * **Cross-Connect Details:** {{site.data.keyword.BluSoftlayer_notm}} provides a Letter of Authorization (LOA) that a customer uses to order fiber Ethernet (Single-Mode Fiber only, either 1Gig-LX or 10Gig-LR optics) that runs from a customer cage or provider to the {{site.data.keyword.BluSoftlayer_notm}} CFA termination point, which will be tied down to the cross-connect router (XCR) infrastructure. The media must be a 1310nm wavelength optic.

 * **Port Speed Options:** Select either 1Gbps, 2Gbps, 5Gbps, and 10Gbps.

 * **Approximate Latency:** Latency is approxiately 1.5ms within the local area (data centers with the same three-letter prefix, such as DAL, AMS, MEL, etc).  See http://lg.softlayer.com/ for live PoP-to-PoP (P2P) latency measurements.

 * **Colocation Services:** None.

 * **Redundancy:** To establish redundancy requires IBM Cloud Direct Link connectivity into 2+ locations, or the selection of a location with a secondary XCR available and a second IBM Cloud Direct Link connection request.

 * **Local/Global Routing Options:** The Local Routing option provides access to data centers with the same three-letter prefix as the PoP (DAL, AMS, MEL, etc). The Global Routing option is required as an add-on to reach data centers outside those locations.

## The IBM Cloud Direct Link Dedicated Hosting solution

The IBM Cloud Direct Link Dedicated Hosting solution provides connectivity similar to IBM Cloud Direct Link Dedicated, but the connection point is adjacent to a {{site.data.keyword.BluSoftlayer_notm}} Data Center, which improves latency for higher performance use cases. IBM Cloud offers a variety of customizable co-location services with this solution.

**Common Use Cases:** _Best for working with non-standard compute technologies, for dedicated storage requirements, or for leveraging existing IT investments._

![Figure 3](/images/direct_link_colo.jpg)

* **Termination Location:** {{site.data.keyword.BluSoftlayer_notm}} Data Center (DC).

 * **Typical Deployment Time:** 30-60 days after all requirements are finalized and contracts are executed.

 * **Cross-Connect Details:** {{site.data.keyword.BluSoftlayer_notm}} provides 1G or 10G fiber connections from the {{site.data.keyword.BluSoftlayer_notm}} cross-connect router (XCR) infrastructure to the customer's colocation environment as part of the deployment.  If colocation services are not requested (if existing environments are connected already), {{site.data.keyword.BluSoftlayer_notm}} provides a Letter of Authorization (LOA) that a customer uses to order fiber Ethernet (Single-Mode Fiber only, either 1Gig-LX or 10Gig-LR optics) that runs from a customer cage to the {{site.data.keyword.BluSoftlayer_notm}} CFA termination point, which will be tied down to the cross-connect router (XCR) infrastructure. The media must be a 1310nm wavelength optic.

<<<<<<< HEAD
 * **Port Speed Options:** Select either 1Gbps, 2Gbps, 5Gbps, and 10Gbps.
=======
 * **Port Speed Options:** Select either 1Gbps or 10Gbps.
>>>>>>> 224d6c71057bf300385a74b93be36ff063e6db39

 * **Approximate Latency:** Latency is approximately 0.5ms within the local data center.

 * **Colocation Services:** Yes.

 * **Redundancy:** {{site.data.keyword.BluSoftlayer_notm}} provides connections to two cross-connect routers (XCRs) as part of the product. To establish redundant connectivity, customers configure BGP with equal-cost multipath (ECMP).

 * **Local/Global Routing Options:** The Local Routing option provides access to data centers with the same three-letter prefix as the PoP (DAL, AMS, MEL, etc). The Global Routing option is required as an add-on to reach data centers outside those locations.
