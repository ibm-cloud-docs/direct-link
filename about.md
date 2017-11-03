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

# More about Direct Link

This section gives more details about the key features and benefits of each of the three Direct Link offerings. 
  * [**Cloud Exchange**](#the-direct-link-cloud-exchange-solution)
  * [**Network Service Provider**](#the-direct-link-network-service-provider-solution)
  * [**Colocation**](#the-direct-link-colocation-solution)

## The Direct Link Cloud Exchange solution

The Direct Link Cloud Exchange solution lets customers leverage a Cloud Exchange provider to deliver connectivity to {{site.data.keyword.BluSoftlayer_notm}}. This offering typically provides connectivity at a reduced cost, because the physical connectivity from {{site.data.keyword.BluSoftlayer_notm}} to the Cloud Exchange Provider is already in place, shared amongst other customers.

**Common Use Cases:** _Best for hybrid workloads, cross-provider workloads, large or frequent data transfers, private workloads, and environment administration.  This option usually is selected when the desired PoP already has the desired Direct Link Cloud Exchange provider._

![Figure 1](/images/direct_link_cloud.jpg)

 * **Termination Location:** IBM Cloud {{site.data.keyword.BluSoftlayer_notm}} point of presence (PoP).

 * **Typical Deployment Time:** 5-10 days after circuit reaches the exchange. Deployment time can possibly be 30-60 days overall, depending on your location and requirements.

 * **Cross-Connect Details:** Physical cross-connects for the Cloud Exchange interconnect are maintained between {{site.data.keyword.BluSoftlayer_notm}} and the Cloud Exchange provider. Customers request a "Virtual Circuit" from the Cloud Exchange Provider, which establishes logical connectivity to {{site.data.keyword.BluSoftlayer_notm}}, once they are interconnected to the Cloud Exchange Provider.

 * **Port Speed Options:** Select either 1Gbps or 10Gbps.

 * **Approximate Latency:** Latency is approximately 1.5ms within the local area (data centers with the same three-letter prefix, such as DAL, AMS, MEL, etc). See http://lg.softlayer.com/ for live PoP-to-PoP (P2P) latency measurements.

 * **Colocation Services:** None.

 * **Redundancy:** To establish redundancy for Direct Link Cloud Exchange, connectivity into 2+ locations is required, or the selection of a location with a secondary XCR available that can be leveraged by the Cloud Exchange provider.

 * **Local/Global Routing Options:** The Local Routing option provides access to data centers with the same three-letter prefix as the PoP (DAL, AMS, MEL, etc). The Global Routing option is required as an add-on to reach data centers outside those locations.
 
## The Direct Link Network Service Provider solution

The Direct Link Network Service Provider (NSP) solution lets customers terminate a dedicated, single-mode, fiber cross-connect into their own {{site.data.keyword.BluSoftlayer_notm}} private network.

 **Common Use Cases:** _Best for working with hybrid workloads, cross-provider workloads, large or frequent data transfers, private workloads, and environment administration.  This option usually is selected: (1) when the desired PoP does not have the desired Direct Link Cloud Exchange provider, (2) for high-performance workloads requiring high throughput, or (3) for compliance requirements that cannot be satisfied by the Direct Link Cloud Exchange implementation model._

![Figure 2](/images/direct_link_nsp.jpg)

 * **Termination Location:** IBM Cloud {{site.data.keyword.BluSoftlayer_notm}} point of presence (PoP).

 * **Typical Deployment Time:** 10-15 business days after the new circuit reaches the POP. Deployment time can possibly be 30-60 days overall, depending on your location and requirements.

 * **Cross-Connect Details:** {{site.data.keyword.BluSoftlayer_notm}} provides a Letter of Authorization (LOA) that a customer uses to order fiber Ethernet (Single-Mode Fiber only, either 1Gig-LX or 10Gig-LR optics) that runs from a customer cage or provider to the {{site.data.keyword.BluSoftlayer_notm}} CFA termination point, which will be tied down to the cross-connect router (XCR) infrastructure. The media must be a 1310nm wavelength optic.

 * **Port Speed Options:** Select either 1Gbps or 10Gbps.

 * **Approximate Latency:** Latency is approxiately 1.5ms within the local area (data centers with the same three-letter prefix, such as DAL, AMS, MEL, etc).  See http://lg.softlayer.com/ for live PoP-to-PoP (P2P) latency measurements.

 * **Colocation Services:** None.

 * **Redundancy:** To establish redundancy requires Direct Link connectivity into 2+ locations, or the selection of a location with a secondary XCR available and a second Direct Link connection request.

 * **Local/Global Routing Options:** The Local Routing option provides access to data centers with the same three-letter prefix as the PoP (DAL, AMS, MEL, etc). The Global Routing option is required as an add-on to reach data centers outside those locations.

## The Direct Link Colocation solution

The Direct Link Colocation solution provides connectivity similar to Direct Link NSP, but the connection point is adjacent to a {{site.data.keyword.BluSoftlayer_notm}} Data Center, which improves latency for higher performance use cases. IBM Cloud offers a variety of customizable co-location services with this solution.

**Common Use Cases:** _Best for working with non-standard compute technologies, for dedicated storage requirements, or for leveraging existing IT investments._

![Figure 3](/images/direct_link_colo.jpg)

* **Termination Location:** IBM Cloud {{site.data.keyword.BluSoftlayer_notm}} Data Center (DC).

 * **Typical Deployment Time:** 30-60 days after all requirements are finalized and contracts are executed.

 * **Cross-Connect Details:** {{site.data.keyword.BluSoftlayer_notm}} provides 1G or 10G fiber connections from the {{site.data.keyword.BluSoftlayer_notm}} cross-connect router (XCR) infrastructure to the customer's colocation environment as part of the deployment.  If colocation services are not requested (if existing environments are connected already), {{site.data.keyword.BluSoftlayer_notm}} provides a Letter of Authorization (LOA) that a customer uses to order fiber Ethernet (Single-Mode Fiber only, either 1Gig-LX or 10Gig-LR optics) that runs from a customer cage to the {{site.data.keyword.BluSoftlayer_notm}} CFA termination point, which will be tied down to the cross-connect router (XCR) infrastructure. The media must be a 1310nm wavelength optic.

 * **Port Speed Options:** Select either 1Gbps or 10Gbps.

 * **Approximate Latency:** Latency is approximately 0.5ms within the local data center.

 * **Colocation Services:** Yes.

 * **Redundancy:** {{site.data.keyword.BluSoftlayer_notm}} provides connections to two cross-connect routers (XCRs) as part of the product. To establish redundant connectivity, customers configure BGP with equal-cost multipath (ECMP).

 * **Local/Global Routing Options:** The Local Routing option provides access to data centers with the same three-letter prefix as the PoP (DAL, AMS, MEL, etc). The Global Routing option is required as an add-on to reach data centers outside those locations.
