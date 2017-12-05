---

copyright:
  years: 2017
lastupdated: "2017-08-21"

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
Yes. IBM Cloud does meter all outbound bandwidth on Direct Link Products. Inbound bandwidth is free and unmetered.

## What additional charges will I incur from other parties with Direct Link?
You may have additional charges from your exchange provider or network service provider. Please refer to your provider(s) for their fee information.

## How can I achieve redundancy with Direct Link?
You can achieve redundancy with Direct Link by connecting to more than one Network Service Provider or Cloud Exchange to {{site.data.keyword.BluSoftlayer_notm}}.

## If I have an overlapping network with {{site.data.keyword.BluSoftlayer_notm}} how can I facilitate connectivity?
We recommend using NAT or building IPSec tunnels from your VLAN(s) to the remote location. For NAT, {{site.data.keyword.BluSoftlayer_notm}} assigns a 172.x.x.x range, which is unique on our side, and you would NAT into that range. The IPSec solution is implemented with a Vyatta, by using IPSec with GRE.

## What is the difference between the default "local" routing and the Global Routing add-on?
With our standard Direct Link offering, you can send traffic between the data centers in your selected region. If you need access to other data centers outside of the specified region, you must order the Global Routing add-on. This model is based upon ACLs (access control lists) that are put in place at the time your Direct Link connection is ordered. For a list of regions by datacenter and POP, please see [here]().

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

## If I am connected to a Direct Link NSP or Direct Link Cloud Exchange in a region such as Dallas, do I have access to other regions in the U.S. through Direct Link?
Yes, you are able to gain access to areas outside of your region if you choose the Global Routing add-on. If this option is not selected, your Direct Link traffic will be limited to the region for the POP you have selected.

## Can I connect to any available region from a given Direct Link location?
Yes, as long as you order Direct Link with the Global Routing add-on.

## Can I restrict the regions that my Direct Link can reach?
No. IBM Cloud offers two options: (1) a single region only, or (2) all regions, with the Global Routing add-on.
