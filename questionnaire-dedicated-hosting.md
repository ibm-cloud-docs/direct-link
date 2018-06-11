---

copyright:
  years: 2018
lastupdated: "2018-06-11"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud Direct Link Dedicated Questionnaire

Thank you for opening a request for IBM Cloud Direct Link Dedicated Hosting.  To finalize your request, we’d like to gather some additional information from you.  You can speak with an engineer at any time during the questionnaire process.  Once you've completed the questionnaire, it will be reviewed by our Cloud Design Engineering team and escalated to Network Engineering for implementation.

## Acknowledgements

1. The fees outlined in this questionnaire cover the cost of service termination into the IBM Cloud network infrastructure. Colocation costs, including cabinets, cross-connects, etc. include monthly and non-recurring fees that are outlined separately as part of a colocation contract.

2. IBM Cloud Direct Link Dedicated Hosting provides 1Gbps or 10Gbps fiber cross connects into the IBM Cloud private network. You'll need to provide a router or a Layer 3 switch that can support single mode fiber (SMF) uplinks. The deployment time can vary based on your circuit provider, typical deployment time for this service is 30-60 days.

3. Direct Link Dedicated Hosting requires utilizing a VRF (Virtual Routing and Forwarding) instance.  This allows the customer to define their own remote IP addresses for use in their remote network; however, you must be aware that if you utilize the 10.x.x.x network you still cannot overlap with your hosts within IBM Cloud nor with the SIBM Cloud services network (10.0.0.0/14, 10.198.0.0/15, and 10.200.0.0/14). Transition of your account to a VRF requires a brief private network outage as each VLAN is migrated into the new configuration.  The Network Engineering team will work with you to define a window for this activity.

4. VRF alters the behavior of IBM Cloud SSL, PPTP and IPsec VPN. These typically work when the VPN connection is made to the same data center location as the compute resources being accessed, but they do not allow access globally.  As an alternative, you can use the Direct Dink itself for management of your servers or run your own VPN solution (such as a Vyatta) that can be configured with different types of VPN.  

5. Direct Link Dedicated Hosting requires BGP in order to implement routes to a customer's remote network.  IBM Cloud will not implement filters on the advertisements made to IBM Cloud.  IBM Cloud will advertise all of the private subnets assigned to your account.  Customers will need to properly manage the advertisements received to IBM Cloud.

6. IBM Cloud provides dual uplinks, one to each of IBM Cloud’s cross-connect routers, to allow customers to establish redundant connectivity.  This is accomplished on the customer's router(s) via BGP sessions by leveraging ECMP capabilities or simply weighting the connections.

7. The IBM Cloud services network will not be accessible from your Dedicated Hosting or remote networks directly.

8. IBM Cloud will not allow you to back haul traffic between your remote sites across the IBM Cloud backbone. The Direct Link service is designed for your remote networks to be able to privately communicate with your IBM Cloud infrastructure.

9. IBM Cloud offers Direct Link with Local or Global routing. Please confirm which routing package you require and that you agree to the bandwidth plans associated with those packages listed at the following link: ibm.biz/DirectLink-Docs.

10. Please specify how much traffic you plan to push across your Direct Link, and to which IBM Cloud data centers you plan to push this traffic to.

11. If you are not purchasing co-location services through IBM Cloud, you will be responsible for ordering and paying for cross-connects between your environment and IBM Cloud.  Once connected, we will provide a Letter of Authorization (LOA) detailing our approval of your connection and location to be connected to.

12. Please confirm that you agree to the following pricing for Direct Link:
 * 1Gbps: _LOCATION BASED PRICING_ 
* 2Gbps: _LOCATION BASED PRICING_
* 5Gbps: _LOCATION BASED PRICING_
* 10Gbps: _LOCATION BASED PRICING_
* Optional Global Routing
