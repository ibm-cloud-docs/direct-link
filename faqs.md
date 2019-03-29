---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-02-26"

keywords: faq, faqs, questions, answer, billing, fees, point-to-point, bandwidth, charges, redundancy, Global Routing, diversity, IPv6, BGP, charges, jumbo frames

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}
{:faq: data-hd-content-type='faq'}

# FAQs
{: #faqs}

This section contains answers to some frequently asked questions about {{site.data.keyword.cloud}} Direct Link. 

## How does IBM Cloud Direct Link work?
{: #how-does-ibm-cloud-direct-link-work}
{:faq}

For every Direct Link customer, the IBM Cloud team assigns a small private subnet to build a point-to-point network between the {{site.data.keyword.BluSoftlayer_notm}} cross-connect router (XCR) and the customer's edge router (CER). Then, {{site.data.keyword.BluSoftlayer_notm}} and the customer configure BGP in order to exchange routes between the environments. Finally, {{site.data.keyword.BluSoftlayer_notm}} places the customer into a VRF to allow for the implementation of non-unique routes to the private address space of the customer's remote network.

## Does IBM Cloud meter bandwidth for Direct Link products?
{: #does-ibm-cloud-meter-bandwidth-for-direct-link-products}
{:faq}

Yes. Bandwidth usage across the Direct Link service between Customers and IBM Cloud is free and unmetered, IBM Cloud does meter outbound bandwidth from IBM Cloud services to the public internet.

## When does billing begin with Direct Link?
{: #when-does-billing-begin-with-direct-link}
{:faq}

The fees for Direct Link Connect cover the cost of service termination on the IBM Cloud infrastructure. 

Infrastructure Services are billed in advance and begin upon acceptance of our client’s order; however, due to the nature of IBM Cloud Direct Link, the Direct Link service billing begins when a Border Gateway Protocol (BGP) session is established with IBM Cloud, or 30 days after the service key is provided to the client. 

Billing stops after (1) a customer requests a circuit to be deleted AND (2) the Connect Provider or Network Service Provider has de-provisioned the circuit.

## What additional charges will I incur from other parties with Direct Link?
{: #what-additional-charges-will-i-incur-from-other-parties-with-direct-link}
{:faq}

You may have additional charges from your exchange provider or network service provider. Please refer to your provider(s) for their fee information.

## How can I achieve redundancy with IBM Cloud Direct Link?
{: #how-can-i-achieve-redundancy-with-ibm-cloud-direct-link}
{:faq}

Direct Link does not provide an inherently Redundant service. Direct Link can provide Diverse connections, that enable customers to create redundancy via BGP. You can achieve diversity with Direct Link by connecting to more than one IBM Cloud Direct Link Dedicated provider or Exchange provider for {{site.data.keyword.BluSoftlayer_notm}}. Alternatively, with Exchange and Connect you can leverage diverse NNIs with the IBM Cloud Direct Link providers.

## What is the difference between the default "local" routing and the Global Routing add-on for Direct Link?
{:faq}

With our standard Direct Link offering, you can send traffic between the data centers in your selected region. If you need access to other data centers outside of the specified region, you must order the Global Routing add-on. This model is based upon ACLs (access control lists) that are put in place at the time your Direct Link connection is ordered. 

## Why does a Global Routing add-on package exist for Direct Link?
{:faq}

We have added the Global Routing add-on to prevent our customers from experiencing unexpected data costs when traversing outside of their data center's Local Market. It keeps costs lower for the majority of our customers, and it provides the ability for customers with a global presence to reach all regions across the globe easily. Usually, however, a customer requires only a local bandwidth package.

## If I am connected to a Direct Link Dedicated, Direct Link Connect, or Direct Link Exchange in a region such as Dallas, do I have access to other regions in the U.S. through Direct Link?
{:faq}

Yes, you are able to gain access to areas outside of your Local Market if you choose the Global Routing add-on. If this option is not selected, your Direct Link traffic will be limited to the Local Market for the PoP or DC location you have selected. Please refer to the [pricing document](/docs/infrastructure/direct-link/pricing.html)for details.

## Can I connect to any available region from a given Direct Link location?
{:faq}

Yes, as long as you order Direct Link with the Global Routing add-on.

## Can I restrict the regions that my Direct Link can reach?
{:faq}

No. IBM Cloud offers two options: (1) a Local Market only, or (2) all regions, with the Global Routing add-on.

## What if I used the Direct Link automated ordering process for Equinix Cloud Exchange and I was assigned a subnet that overlaps my internal network?
{:faq}

As of March 2018, the recommended best practice is to cancel your automated order and submit a new ticket to fill out the Direct Link questionnaire. You should indicate whether you prefer another subnet in the 10.254.x.x range or the 172.32.x.x range.

## What is the difference between Direct Link Exchange and Direct Link Connect?
{:faq}

These two services are similar, relatively low-cost, latency tolerant, and rapid entry points to the benefits of IBM Cloud Direct Link. In a nutshell, Exchange utilizes datacenter providers and Connect utilizes Telco carriers. Here are some additional details:

**Direct Link Exchange** is recommended for customers who prefer to utilize an exchange inside a datacenter. With an Exchange service, customers can enable multi-cloud connectivity to their co=location rapidly, because the underlying circuits are provisioned already (these other cloud providers must already have a physical interconnection present within the facility).

Direct Link Exchange can allow for a multi-cloud, shared use environment through a single cloud exchange port, created by a network-to-network (NNI) connection at Layer 2 between IBM Cloud and the Cloud Exchange Service Provider. Port speeds are available up to 5Gb.

**Direct Link Connect** is for customers who prefer to utilize their existing network between their own on-premises deployment and IBM Cloud. With a Direct Link Connect service, customers can use new and existing Telco networks (such as MPLS) to enable IBM Cloud rapidly, by leveraging pre-provisioned underlying circuits.

With Direct Link Connect, customers can connect to IBM Cloud through the Connect provider, over a Network to Network (NNI) connection, operated by IBM partners in facilities worldwide. Port speeds are available up to 5Gb.

## How do Direct Link Connect and Direct Link Exchange providers compare?
{:faq}

Connect providers are Telcos who have network reach beyond the datacenter. Exchange providers are limited to their datacenters. Both can enable the multi-cloud experience for customers. Exchange providers usually require co-location in their datacenters, while Connect providers can reach a customer's on-premise site and datacenters.

## Can IBM support IPv6 over Direct Link?
{: #can-ibm-support-ipv6-over-direct-link}
{:faq}

Not for the BGP Session. We have to assign our /30 from IPv4, and we need the same in return from the customer.

## Can IBM do IPV6 on the private network?
{: #can-ibm-do-ipv6-on-the-private-network}
{:faq}

No. IPv6 is public only.

## Are there any special Direct Link requirements for Verizon SCI? Prefix / ASN / VLAN BGP / and so forth?
{:faq}

Verizon SCI is one of several MPLS based, Layer-3 (IP VPN) services. It requires that IBM establish BGP with Verizon instead of directly with the customer. Verizon then establishes BGP with the customer and advertises routes accordingly. Several other Layer-3 based service providers participate in the Direct Link Connect program. Customers need to be aware of what they are ordering and how their account will behave when connecting to IBM Cloud.

## Does Direct Link support any type of QoS?
{:faq}

We are unable to support any QoS guarantees. QoS requires MPLS mapping between each of our service suppliers and IBM Cloud. Cloud Service Providers generally cannot support QoS at this time, because it must reach from end to end and involve every device in between. There is no workaround available by "tunneling" or any other method.

## Does Direct Link support Jumbo frames?
{: #does-direct-link-support-jumbo-frames}
{:faq}

Jumbo frames (up to 9214 bytes) are supported on Dedicated and Dedicated Hosting. 
Support on Connect and Exchange is theoretically possible, but it requires your Service Provider to work with IBM and ensure that the end-to-end connection supports Jumbo Frames, including the underlying Network-to Network-Interface (NNI).
By default, Exchange and Connect are set up with 1500-byte MTU support.

## With Direct Link Connect how does a customer ensure router diversity through the same carrier (Example: Verizon in DAL03)?
{:faq}

We have diverse XCRs creating diverse NNI links to the carrier. It is up to the carrier to maintain diversity from that point.

## For Direct Link Connect does a customer need to order 2 links for redundancy, or is the Direct Link Connect inherently redundant?
{:faq}

Order 2 links for diversity. We do not offer redundancy between switches or routers. Customers create redundancy with their BGP configurations on each Direct Link.

## How easy is it to upgrade the bandwidth of my Direct Link connection, for example from 1GB to 5GB?
{:faq}

Typically, we install speeds of 1G and below on 1G optics. For speeds of 2G to 10G, we install 10G optics. Thus, the upgrade from 1G to 5G would require new optics to be assigned or inserted. It would be a service-affecting event. If you anticipate that type of growth, it's possible to request 10G optical fibers to be installed at the beginning of your Direct Link deployment, or to order 2G initially so that the 10G optics are in place.

## Is ECMP the way to go for redundant Direct Link connections?  What alternatives exist?
{:faq}

Note that ECMP isn’t for redundant connections but for balancing the load over the two links. With ECMP, both connections must terminate to the same IBM Cloud cross-connect router (XCR), which makes it a single point of failure. (In other words, ECMP can only be provisioned as two sessions on the same IBM Cloud XCR.) 

ECMP is a feature of BGP. If you are looking for redundancy, get two Direct Link connections, one going into each XCR. If you want to use ECMP and have redundancy, you’ll need two Direct Link connections on each XCR, so that you can have 2 ECMP sessions going simultaneously.

Alternatively, some of our customers have set up two links into different XCR in the same datacenter, for example WDC02, then failover as needed using BGP configurations. This configuration is less redundant (less safe) than having Direct Link connections into two separate datacenters, such as WDC02 and WDC05.

## Is there an SLA on the Direct Link XCR connections up to the account’s BCR connection?
{:faq}

There is no SLA on Direct Link today. Customers can achieve 99.999% effectively with 2 or more Direct Links properly configured for failover using BGP, but IBM cannot control that or provide an SLA on it.

## Where can I get help setting up a Direct Link?
{: #where-can-i-get-help-setting-up-a-direct-link}
{:faq}

For connecting to Direct Link, see [Configure {{site.data.keyword.cloud_notm}} Direct Link](/docs/infrastructure/direct-link?topic=direct-link-how-to-order-ibm-cloud-direct-link-dedicated). If you need more help, you can request engineering support in the ticket that was opened for the new service. Even if it is an API service with Equinix, opening a ticket will enable an engineer to look at it. Or you can contact your IBM Sales representative.

## On Direct Link Exchange, does IBM set a BGP password?
{: #on-direct-link-exchange-does-ibm-set-a-bgp-password}
{:faq}

We don’t set any BGP password for Direct Link Exchange by default. There is an option to specify BGP ASN and we assign BGP IP addresses. Also, it is possible to set up a BGP password for authentication purposes, we just have to let the engineers know.
