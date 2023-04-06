---

copyright:
  years: 2017, 2023
lastupdated: "2023-03-27"

keywords: 

subcollection: direct-link

---

{{site.data.keyword.attribute-definition-list}}

# FAQs for Direct Link on Classic
{: #faqs}

You can review answers to some frequently asked questions about {{site.data.keyword.cloud}} Direct Link.
{: shortdesc}

## How does Direct Link on Classic differ from the new Direct Link offering?
{: #differentiators}
{: faq}
{: support}

The new IBM Cloud Direct Link offering differs from "Direct Link on Classic" in that the new Direct Link is decoupled from classic IaaS, and exists only in the local cross-connect router (XCR). This design enables native connectivity to VPC and future capabilities without being forced into the classic IaaS network.

The zone-region model allows for multiple data centers to exist in a single zone.

 The new Direct Link offering allows connectivity to both Classic IaaS as well as VPCs, whereas the Classic Direct Link always connects to IaaS network and a global VRF first. Classic Direct Link can only reach VPC on a limited basis utilizing a VPC feature called Classic Access and by adding global routing to the direct link. For more information, see [Setting up access to your Classic Infrastructure from VPC](/docs/vpc?topic=vpc-setting-up-access-to-classic-infrastructure).

For information about the differences between the new Direct Link offerings and the "on Classic" versions, see [How do I know which Direct Link solution to order?](/docs/direct-link?topic=direct-link-get-started-with-ibm-cloud-direct-link#get-started-solution-to-order) and [Getting started with IBM Cloud Direct Link Dedicated](/docs/dl?topic=dl-get-started-with-ibm-cloud-dl).
{: tip}

## How does IBM Cloud Direct Link work?
{: #how-does-ibm-cloud-direct-link-work}
{: faq}
{: support}

For every Direct Link customer, the {{site.data.keyword.cloud}} team assigns a small private subnet to build a point-to-point network between the {{site.data.keyword.cloud_notm}} cross-connect router (XCR) and the customer's edge router (CER). Then, {{site.data.keyword.cloud_notm}} and the customer configure Border Gateway Protocol (BGP) to exchange routes between the environments. Finally, {{site.data.keyword.cloud_notm}} places the customer into a VRF to allow for the implementation of non-unique routes to the private address space of the customer's remote network.

## Where do I find cost estimates for Direct Link offerings?
{: #pricing-estimator}
{: faq}

You can estimate the cost of a service using the cost estimator on the provisioning pages for Direct Link on Classic offerings. For example, select a tile from the [IBM Cloud catalog](/catalog?category=compute%20network&search=direct%20link%20%22on%20classic%22%20label%3Aibm_created#search_results) to view the service's ordering page. As you complete the ordering form, cost estimates appear in the Summary side panel.

## Does IBM Cloud meter bandwidth for Direct Link products?
{: #does-ibm-cloud-meter-bandwidth-for-direct-link-products}
{: faq}

Yes. Bandwidth usage across the Direct Link service between customers and {{site.data.keyword.cloud_notm}} is free and unmetered, {{site.data.keyword.cloud_notm}} does meter outbound bandwidth from {{site.data.keyword.cloud_notm}} services to the public internet.

## When does billing begin with Direct Link?
{: #when-does-billing-begin-with-direct-link}
{: faq}
{: support}

The fees for Direct Link Connect cover the cost of service termination on the {{site.data.keyword.cloud_notm}} infrastructure.

Infrastructure services are billed in advance and begin upon acceptance of a client’s order, however, due to the nature of IBM Cloud Direct Link, the Direct Link service billing begins when a Border Gateway Protocol (BGP) session is established with {{site.data.keyword.cloud_notm}}, or 30 days after the service key is provided to the client.

Billing stops after (1) a customer requests a circuit to be deleted AND (2) the Connect Provider or Network Service Provider has de-provisioned the circuit.

## What extra charges will I incur from other parties with Direct Link?
{: #what-additional-charges-will-i-incur-from-other-parties-with-direct-link}
{: faq}

You might have extra charges from your exchange provider or network service provider. Refer to your providers for their fee information.

## How can I achieve redundancy with IBM Cloud Direct Link?
{: #how-can-i-achieve-redundancy-with-ibm-cloud-direct-link}
{: faq}

Direct Link does not provide an inherently Redundant service. Direct Link can provide Diverse connections that enable customers to create redundancy via BGP. You can achieve diversity with Direct Link by connecting to more than one IBM Cloud Direct Link Dedicated provider or Exchange provider for {{site.data.keyword.cloud_notm}}. Alternatively, with Exchange and Connect you can use diverse network-to-networks (NNIs) with the IBM Cloud Direct Link providers.

## What is the difference between the default "local" routing and the global routing add-on for Direct Link?
{: #what-is-the-difference-between-the-default-local-routing-and-the-global-routing-add-on-for-direct-link}
{: faq}
{: support}

The local routing option is the default routing option. If your Direct Link is connected at the local PoP, it provides access to all data centers within that same market. In some markets, local routing is applicable for stand-alone PoP locations and direct links that are terminated at the data center.

With our standard Direct Link offering, you can send traffic between the data centers in your selected region. If you need access to other data centers outside of the specified region, you must order the global routing add-on. For example, you might use global routing to share workloads between dispersed IBM Cloud resources (such as Dallas to Ashburn, or Dallas to Frankfurt).

## Why does a global routing add-on package exist for Direct Link?
{: #why-does-a-global-routing-add-on-package-exist-for-direct-link}
{: faq}

The global routing add-on prevents our customers from experiencing unexpected data costs when traversing outside of their data center's local market. It keeps costs lower for most of our customers, and it provides the ability for customers with a global presence to reach all regions across the globe easily. However, usually a customer requires only a local bandwidth package.

## If I am connected to a Direct Link Dedicated, Direct Link Connect, or Direct Link Exchange in a region such as Dallas, do I have access to other regions in the US through Direct Link?
{: #if-i-am-connected-to-a-direct-link-dedicated}
{: faq}

Yes, you are able to gain access to areas outside of your local market if you choose the global routing add-on. If this option is not selected, your Direct Link traffic is limited to the local market for the PoP or DC location you selected.

## Can I connect to any available region from a given Direct Link location?
{: #can-i-connect-to-any-available-region-from-a-given-direct-link-location}
{: faq}

Yes, as long as you order Direct Link with the global routing add-on.

## Can I restrict the regions that my Direct Link can reach?
{: #can-i-restrict-the-regions-that-my-direct-link-can-reach}
{: faq}

No. IBM Cloud offers two options: (1) a local market only, or (2) all regions, with the global routing add-on.

## What if I used the Direct Link automated ordering process for Equinix Cloud Exchange and I was assigned a subnet that overlaps my internal network?
{: #what-if-i-used-the-direct-link-automated-ordering-process}
{: faq}

The recommended best practice is to cancel your automated order and submit a new case to complete the Direct Link questionnaire. You should indicate whether you prefer another subnet in the `10.254.x.x` range or the `172.16.x.x` range.

## What is the difference between Direct Link Exchange and Direct Link Connect?
{: #what-is-the-difference-between-direct-link-exchange-and-direct-link-connect}
{: faq}
{: support}

These two services are similar, relatively low-cost, latency tolerant, and rapid entry points to the benefits of IBM Cloud Direct Link. In a nutshell, Exchange uses data center providers and Connect uses Telco carriers. Here are some additional details:

**Direct Link Exchange** is recommended for customers who prefer to use an exchange inside a data center. With an Exchange service, customers can enable multi-cloud connectivity to their colocation rapidly because the underlying circuits are provisioned already (these other cloud providers must already have a physical interconnection present within the facility).

Direct Link Exchange can allow for a multi-cloud, shared-use environment through a single cloud exchange port, created by an NNI connection at Layer 2 between IBM Cloud and the Cloud Exchange Service Provider. Port speeds are available up to 5 Gb.

**Direct Link Connect** is for customers who prefer to use their existing network between their own on-premises deployment and IBM Cloud. With a Direct Link Connect service, customers can use new and existing Telco networks (such as MPLS) to enable IBM Cloud rapidly, by using pre-provisioned underlying circuits.

With Direct Link Connect, customers can connect to IBM Cloud through the Connect provider, over a Network-to-Network Interface (NNI) connection, operated by IBM partners in facilities worldwide. Port speeds are available up to 5 Gb.

## How do Direct Link Connect and Direct Link Exchange providers compare?
{: #how-do-direct-link-connect-and-direct-link-exchange-providers-compare}
{: faq}

Connect providers are Telcos who have network reach beyond the data center. Exchange providers are limited to their data centers. Both can enable the multi-cloud experience for customers. Exchange providers usually require colocation in their data centers, while Connect providers can reach a customer's on-premises site and data centers.

## Can IBM Support IPv6 over Direct Link?
{: #can-ibm-support-ipv6-over-direct-link}
{: faq}
{: support}

Not for the BGP Session. We must assign our /30 from IPv4, and we need the same in return from the customer.

## Can IBM do IPV6 on the private network?
{: #can-ibm-do-ipv6-on-the-private-network}
{: faq}

No. IPv6 is public only.

## Are there any special Direct Link requirements for Verizon SCI? Prefix / ASN / VLAN BGP / and so forth?
{: #are-there-any-special-direct-link-requirements-for-verizon-sci}
{: faq}

Verizon SCI is one of several MPLS based, Layer-3 (IP VPN) services. It requires that IBM establish BGP with Verizon instead of directly with the customer. Verizon then establishes BGP with the customer and advertises routes accordingly. Several other Layer-3 based service providers participate in the Direct Link Connect program. Customers need to be aware of what they are ordering and how their account will behave when connecting to IBM Cloud.

## Does Direct Link support any type of QoS?
{: #does-direct-link-support-any-type-of-qos}
{: faq}

We are unable to support any QoS guarantees. QoS requires MPLS mapping between each of our service suppliers and IBM Cloud. Cloud Service providers generally cannot support QoS because it must reach from end-to-end and involve every device in between. No workaround is currently available by "tunneling" or any other method.

## Does Direct Link support Jumbo frames?
{: #does-direct-link-support-jumbo-frames}
{: faq}

Jumbo frames (up to 9214 bytes) are supported on Dedicated and Dedicated Hosting.
Support on Connect and Exchange is theoretically possible, but it requires your Service Provider to work with IBM and ensure that the end-to-end connection supports Jumbo Frames, including the underlying Network-to Network-Interface (NNI).

Exchange and Connect support up to a 1500-byte Maximum Transmission Unit (MTU). 
{: important} 

## With Direct Link Connect how does a customer ensure router diversity through the same carrier (for example, Verizon in DAL03)?
{: #with-direct-link-connect-how-does-a-customer-ensure-router-diversity-through-the-same-carrier}
{: faq}

We have diverse cross-connect routers (XCRs) creating diverse NNI links to the carrier. It is up to the carrier to maintain diversity from that point.

## For Direct Link Connect does a customer need to order two links for redundancy, or is the Direct Link Connect inherently redundant?
{: #for-direct-link-connect-does-a-customer-need-to-order-2-links-for-redundancy}
{: faq}

Order two links for diversity. We do not offer redundancy between switches or routers. Customers create redundancy with their BGP configurations on each Direct Link.

## How easy is it to upgrade the bandwidth of my Direct Link connection, for example 1 - 5 GB?
{: #how-easy-is-it-to-upgrade-the-bandwidth-of-my-direct-link-connection}
{: faq}

Typically, we install speeds of 1G and lower on 1G optics. For speeds of 2 - 10 GB, we install 10 GB optics. Thus, the upgrade 1 - 5 GB would require new optics to be assigned or inserted. It would be a service-affecting event. If you anticipate that type of growth, it's possible to request 10 GB optical fibers to be installed at the beginning of your Direct Link deployment, or to order 2 GB initially so that the 10 GB optics are in place.

## Is ECMP the way to go for redundant Direct Link connections? What alternatives exist?
{: #is-ecmp-the-way-to-go-for-redundant-direct-link-connections}
{: faq}

ECMP isn’t for redundant connections, but for balancing the load over the two links. With ECMP, both connections must terminate to the same {{site.data.keyword.cloud_notm}} cross-connect router (XCR), which makes it a single point of failure. (In other words, ECMP can be provisioned only as two sessions on the same {{site.data.keyword.cloud_notm}} XCR.)

**IBM Cloud does NOT recommend the use of ECMP. ECMP balancing with IBM cloud only extends to the XCRs. Past the XCRs, the ECMP-based traffic presents itself as the same IP address to IBM Cloud network, and the IBM Cloud network routing defaults to the shortest path found. This means that only one of the Direct Links in the ECMP configuration is usable at a given time.**

ECMP is a feature of BGP. If you are looking for redundancy, get two Direct Link connections, one going into each XCR. If you want to use ECMP and have redundancy, you need two Direct Link connections on each XCR so that you can have 2 ECMP sessions running simultaneously.

Alternatively, some of our customers set up two links into different XCR in the same data center, for example WDC02, then failover as needed by using BGP configurations. This configuration is less redundant (less safe) than having Direct Link connections into two separate data centers, such as WDC02 and WDC05.

## Is there an SLA on the Direct Link XCR connections up to the account’s BCR connection?
{: #is-there-an-sla-on-the-diret-link-xr-connections}
{: faq}

There is no SLA on Direct Link today. Customers can achieve 99.99% effectively with two or more Direct Links that are properly configured for failover by using BGP, but IBM cannot control that or provide an SLA on it.

## Where can I get help setting up a Direct Link?
{: #where-can-i-get-help-setting-up-a-direct-link}
{: faq}
{: support}

For connecting to Direct Link, see [Configuring {{site.data.keyword.cloud_notm}} Direct Link](/docs/direct-link?topic=direct-link-configure-ibm-cloud-direct-link). If you need more help, you can request engineering support in the case that was opened for the new service. Even if it is an API service with Equinix, opening a case enables an engineer to look at it. Or you can contact your IBM Sales representative.

## On Direct Link Exchange, does IBM set a BGP password?
{: #on-direct-link-exchange-does-ibm-set-a-bgp-password}
{: faq}

BGP passwords for Direct Link Exchange aren't set up, by default. There is an option to specify BGP ASN and we assign BGP IP addresses. Also, it's possible to set up a BGP password for authentication purposes, we just need to let the engineers know.
