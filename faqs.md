---

copyright:
  years: 2017, 2018
lastupdated: "2018-05-03"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# FAQs

This section contains answers to some frequently asked questions about IBM Cloud Direct Link. 

## How does IBM Cloud Direct Link work?
For every Direct Link customer, the IBM Cloud team assigns a small private subnet to build a point-to-point network between the {{site.data.keyword.BluSoftlayer_notm}} cross-connect router (XCR) and the customer's edge router (CER). Then, {{site.data.keyword.BluSoftlayer_notm}} and the customer configure BGP in order to exchange routes between the environments. Finally, {{site.data.keyword.BluSoftlayer_notm}} places the customer into a VRF to allow for the implementation of non-unique routes to the private address space of the customer's remote network.

## Does IBM Cloud meter bandwidth for Direct Link products?
Yes. Bandwidth usage across the Direct Link service between Customers and IBM Cloud is free and unmetered, IBM Cloud does meter outbound bandwidth from IBM Cloud services to the public internet.

## What additional charges will I incur from other parties with Direct Link?
You may have additional charges from your exchange provider or network service provider. Please refer to your provider(s) for their fee information.

## How can I achieve redundancy with IBM Cloud Direct Link?
Direct Link does not provide an inherently Redundant service. Direct Link can provide Diverse connections, that enable customers to create redundancy via BGP. You can achieve diversity with Direct Link by connecting to more than one IBM Cloud Direct Link Dedicated provider or Exchange provider for {{site.data.keyword.BluSoftlayer_notm}}. Alternatively, with Exchange and Connect you can leverage diverse NNIs with the IBM Cloud Direct Link providers.

## What is the difference between the default "local" routing and the Global Routing add-on?
With our standard Direct Link offering, you can send traffic between the data centers in your selected region. If you need access to other data centers outside of the specified region, you must order the Global Routing add-on. This model is based upon ACLs (access control lists) that are put in place at the time your Direct Link connection is ordered. 

## How are the outbound (egress) bandwidth overages billed for the Global Routing add-on?
Overages are billed monthly when your alotment of bandwidth is exceeded, but only for outbound bandwidth. Inbound bandwidth is free of charge and not metered. Outbound bandwidth is billed based on the rate that is the higher of the two regions that your data crosses.  For example, if your Direct Link is configured in DAL03 and your data traffic passes through Mexico, you will be charged the bandwidth rate for Mexico.

## Why does a Global Routing add-on package exist?
We have added the Global Routing add-on to prevent our customers from experiencing unexpected data costs when traversing outside of their data center's region. It keeps costs lower for the majority of our customers, and it provides the ability for customers with a global presence to reach all regions across the globe easily. Usually, however, a customer requires only a local bandwidth package.

## What are the Local Routing and Global Routing options?
Local Routing and Global Routing options are selected by every customer when ordering Direct Link service. If customers need to route their traffic outside the POP in the area within which they are ordering Direct Link, they must add the Global Routing option; otherwise, their traffic is restricted to the services provided by the local POP.

Each month, all customers using 1G Circuits are allotted 10TB of free egress traffic; customers using 10G circuits are allotted 50TB. Overages are based on the following table, with the higher market rate prevailing. If you select Global Routing, you are not charged for any local egress traffic, only for traffic that originates or terminates outside of the local POP.

|Data Market 1|Data Market 2|Data Market 3|
|---|---|---|
|<ul><li>DAL</li><li>WDC</li><li>SEA</li><li>SJC</li><li>NYC*</li><li>CHI*</li><li>DEN*</li><li>MIA*</li><li>ATL*</li><li>LAX*</li><li>TOR</li><li>MON</li><li>AMS</li><li>FRA</li></ul>|<ul><li>TOK</li><li>HKG</li><li>PAR</li><li>MIL</li><li>STK*</li><li>OSL</li></ul>|<ul><li>MEX</li><li>SAO</li><li>SYD</li><li>MEL</li><li>PER*</li><li>CHE</li><li>SEO</li></ul>|
**Table 1: Utilization tiers**<br/>
Direct Link offerings in the markets marked with an asterisk (*) MUST order Global Routing.

## If I am connected to a Direct Link Dedicated, Direct Link Connect, or Direct Link Exchange in a region such as Dallas, do I have access to other regions in the U.S. through Direct Link?
Yes, you are able to gain access to areas outside of your region if you choose the Global Routing add-on. If this option is not selected, your Direct Link traffic will be limited to the region for the PoP location you have selected. Please refer to the [pricing document](pricing.html)for details.

## Can I connect to any available region from a given Direct Link location?
Yes, as long as you order Direct Link with the Global Routing add-on.

## Can I restrict the regions that my Direct Link can reach?
No. IBM Cloud offers two options: (1) a single region only, or (2) all regions, with the Global Routing add-on.

## What if I used the automated ordering process for Equinix Cloud Exchange and I was assigned a subnet that overlaps my internal network?

As of March 2018, the recommended best practice is to cancel your automated order and submit a new ticket to fill out the Direct Link questionnaire. You should indicate whether you prefer another subnet in the 10.254.x.x range or the 172.32.x.x range.

## What is the difference between Direct Link Exchange and Direct Link Connect?

These two services are similar, relatively low-cost, latency tolerant, and rapid entry points to the benefits of IBM Cloud Direct Link. In a nutshell, Exchange utilizes datacenter providers and Connect utilizes Telco carriers. Here are some additional details:

**Direct Link Exchange** is recommended for customers who prefer to utilize an exchange inside a datacenter. With an Exchange service, customers can enable multi-cloud connectivity to their co=location rapidly, because the underlying circuits are provisioned already (these other cloud providers must already have a physical interconnection present within the facility).

Direct Link Exchange can allow for a multi-cloud, shared use environment through a single cloud exchange port, created by a network-to-network (NNI) connection at Layer 2 between IBM Cloud and the Cloud Exchange Service Provider. Port speeds are available up to 1Gb.

**Direct Link Connect** is for customers who prefer to utilize their existing network between their own on-premises deployment and IBM Cloud. With a Direct Link Connect service, customers can use new and existing Telco networks (such as MPLS) to enable IBM Cloud rapidly, by leveraging pre-provisioned underlying circuits.

With Direct Link Connect, customers can connect to IBM Cloud through the Connect provider, over a Network to Network (NNI) connection, operated by IBM partners in facilities worldwide. Port speeds are available up to 5Gb.

## Can we support IPv6 over Direct Link?

Not for the BGP Session. We have to assign our /30 from IPv4, and we need the same in return from the customer.

## Can we do IPV6 on the private network?

No. IPv6 is public only.

## Are there any special requirements for Verizon SCI? Prefix / ASN / VLAN BGP / and so forth?

Verizon SCI is one of several MPLS based, Layer-3 (IP VPN) services. It requires that IBM establish BGP with Verizon instead of directly with the customer. Verizon then establishes BGP with the customer and advertises routes accordingly. Several other Layer-3 based service providers participate in the Direct Link Connect program. Customers need to be aware of what they are ordering and how their account will behave when connecting to IBM Cloud.

## Does Direct Link support any type of QoS?

We are unable to support any QoS guarantees. QoS requires MPLS mapping between each of our service suppliers and IBM Cloud. Cloud Service Providers generally cannot support QoS at this time, because it must reach from end to end and involve every device in between. There is no workaround available by "tunneling" or any other method.
