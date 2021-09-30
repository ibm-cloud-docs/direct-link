---

copyright:
  years: 2018, 2019
lastupdated: "2019-03-29"


keywords: dedicated, hosting, finalize, questionnaire, Network Engineering, billing, fees, VRF, BGP, case, cross-connects, datacenters, data, center, backhaul, single mode, single-mode, fiber, Letter of Authorization, LOA, contract

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

# Direct Link Dedicated Hosting on Classic questionnaire
{: #ibm-cloud-direct-link-dedicated-hosting-questionnaire}

Thank you for opening a request for IBM Cloud™ Direct Link Dedicated Hosting. To finalize your request, we’d like to gather some additional information from you. You can speak with an engineer at any time during the questionnaire process. After you've completed the questionnaire, it is reviewed by our Cloud Design Engineering team and escalated to Special Network Services for implementation.

## Do you acknowledge and agree to the following?
{: #ibm-cloud-direct-link-dl-agreement}

1. The fees that are outlined in this questionnaire cover the cost of service termination into the IBM Cloud network infrastructure. Colocation costs, including cabinets, cross-connect, etc. include monthly and non-recurring fees that are outlined separately as part of a colocation contract.
2. Direct Link Dedicated Hosting provides 1 Gbps or 10 Gbps fiber cross connects into the IBM Cloud Private network. You need to provide a router or a Layer 3 switch that can support single mode fiber (SMF) uplinks. The deployment time can vary based on your circuit provider. Typical deployment time for this service is 30 - 60 days.
3. Direct Link Dedicated Hosting requires the use of a VRF (Virtual Routing and Forwarding) instance. This allows the customer to define their own remote IP addresses for use in their remote network. However, you must be aware that if you use the `10.x.x.x` network you still cannot overlap with your hosts within IBM Cloud nor with the IBM Cloud services network (`10.0.0.0/14`, `10.198.0.0/15`, and `10.200.0.0/14`). Transition of your account to a VRF requires a brief private network outage as each VLAN is migrated into the new configuration. The Network Engineering team works with you to define a window for this activity.
4. VRF alters the behavior of IBM Cloud SSL and IPsec VPN. These typically work when the VPN connection is made to the same data center location as the compute resources being accessed, but they do not allow access globally. As an alternative, you can use the Direct Link itself for management of your servers or run your own VPN solution (such as a Vyatta) that can be configured with different types of VPN. 
5. Direct Link Dedicated Hosting requires BGP to implement routes to a customer's remote network. IBM Cloud will not implement filters on the advertisements that are made to IBM Cloud. IBM Cloud will advertise all of the private subnets that are assigned to your account. Customers must properly manage the advertisements received to IBM Cloud.
6. IBM Cloud provides dual uplinks, one to each of IBM Cloud’s cross-connect routers to allow customers to establish redundant connectivity. This is accomplished on the customer's routers via BGP sessions by using ECMP capabilities or simply weighting the connections.
7. The IBM Cloud services network will not be accessible from your Dedicated Hosting or remote networks directly.
8. IBM Cloud will not allow you to back haul traffic between your remote sites across the IBM Cloud backbone. The Direct Link service is designed for your remote networks to be able to privately communicate with your IBM Cloud infrastructure.
9. IBM Cloud offers Direct Link with local or global routing. Confirm which routing package you require and that you agree to the bandwidth plans associated with those packages that are listed at the following link: ibm.biz/DirectLink-Docs.
10. Specify how much traffic you plan to push across your Direct Link, and to which IBM Cloud data centers you plan to push this traffic to.
11. If you are not purchasing colocation services through IBM Cloud, you are responsible for ordering and paying for cross-connects between your environment and IBM Cloud. Once connected, a Letter of Authorization (LOA) is provided detailing our approval of your connection and location to be connected to.
12.  Confirm that you agree to the following pricing for Direct Link:

   * 1 Gbps: _location-based pricing_
   * 2 Gbps: _location-based pricing_
   * 5 Gbps: _location-based pricing_
   * 10 Gbps: _location-based pricing_
   * Optional global routing
