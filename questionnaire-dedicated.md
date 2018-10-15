---

copyright:
  years: 2018
lastupdated: "2018-10-15"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud Direct Link Dedicated Questionnaire

Thank you for opening a request for IBM Cloud Direct Link Dedicated.  To finalize your request, we’d like to gather some additional information from you.  You can speak with an engineer at any time during the questionnaire process.  Once you've completed the questionnaire, it will be reviewed by our Cloud Design Engineering team and escalated to Special Network Services for implementation.

## Do you acknowledge and agree to the following?

1. Each Direct Link connection requires a unique order.  If you require multiple connections, please open separate Direct Link orders for each connection.

2. The fees for your Direct Link Connect service cover the cost of service termination on the IBM Cloud infrastructure. 

 * Infrastructure Services are billed in advance and begin upon acceptance of your order; however due to the nature of IBM Cloud Direct Link, the Direct Link service billing will begin upon the initiation of a Border Gateway Protocol (BGP) session with IBM Cloud, or 30 days after the service key is provided to the client. 

 * Billing stops after:
   * A customer requests a circuit to be deleted, **and** 
   * The Exchange Provider or Network Service Provider has de-provisioned the circuit.
  * For more information see **Section 5 - Charges** in the Cloud Services Agreement at the following link: [ibm.biz/service-agreement](ibm.biz/service-agreement)

3. By ordering the Direct Link service, you will be responsible for any fees associated with reaching the Point of Presence (PoP) from your remote network and any cross connects needed within the PoP facility.  If your provider requires that a router or other device physically sit in the PoP, you will be responsible for the costs associated with collocating that equipment as well. 

4. IBM Cloud will not order a cross-connect on a customer's behalf.

5. IBM Cloud will not co-locate any customer equipment in our network POPs. We only accept ‘cross connects’ which is a fiber Ethernet (Single Mode Fiber only, either 1Gig-LX or 10Gig-LR 1310nm optics) run from your cage or provider. We do not accept T1s, DS3s, ISDN, POTs line, etc.  You will need to work with your provider to determine whether or not you need to collocate any equipment in the same facility where the IBM Cloud network PoP exists.

6. The Direct Link service is provided in such a way that when you link and the IBM Cloud router it terminates into are both single points of failure (SPOF). If you want to achieve redundancy through the Direct Link service, you will need to either order two connections into a Direct Link location with a secondary router, or terminate links into two separate IBM Cloud PoPs .

7. The IBM Cloud services network will not be accessible from your remote networks directly. If this capability changes in the future, we will notify you.

8. IBM Cloud will not allow customers to back haul traffic between their remote sites across the IBM Cloud backbone. The Direct Link product is meant for your remote networks to be able to privately communicate with your IBM Cloud infrastructure.

9. After you’ve confirmed your circuit has reached the PoP and is completed by the carrier, you will need to order the cross connect to the IBM Cloud XCR (cross connect router) which usually takes between 2 and 10 business days to complete. This includes the patch down to the SoftLayer termination port.  Once complete, you will be required to provide IBM Cloud with the cross connect completion notice from the facility provider. IP turn up on the IBM Cloud networking infrastructure will be completed within 3 business days after the cross connect is complete.

10. IBM Cloud Direct Link Dedicated requires utilizing a VRF (Virtual Routing and Forwarding) instance. This capability allows customers to define their own remote IP addresses for use in their remote network; however, be aware that if you utilize the 10.x.x.x network you still cannot overlap with your hosts within IBM Cloud nor with the IBM Cloud services network (10.0.0.0/14, 10.198.0.0/15, and 10.200.0.0/14). Transition of your account to a VRF requires a brief private network outage as each VLAN is migrated into the new configuration. The Special Network Services team will work with you to define a window for this activity. The Special Network Services team is available Monday through Friday, 8-5 CST (U.S. Central Standard time). Any activation activity outside this window must be requested by ticket and approved in advance when engineers are available.

11. VRF is not compatible with IBM Cloud (legacy SoftLayer) SSL, PPTP, and IPSEC VPN services.  An alternative is to use the direct link itself for management of your servers or run your own VPN solution (such as a Vyatta) that can be configured with different types of VPN.  After migrating to a VRF, SSL VPN typically works when a VPN connection is made to the same DC location as the compute that is being accessed, but does not allow access globally.

12. IBM Cloud Direct Link Dedicated requires BGP in order to implement routes to a customer's remote network.  When your Direct Link service has been deployed, IBM Cloud will advertise all of the private subnets assigned to your account. IBM Cloud will not implement custom filters, AS-Path prepend and custom local-preference to advertisements to the Customer's remote BGP peer. IBM Cloud will not implement filters on the advertisements received to IBM Cloud. Customers will need to properly manage the advertisements to/from IBM Cloud from the customer's edge router. 

## Other questions

* **Which PoP do you want to terminate the Direct Link into?**

* **What link speed to you require (1, 2, 5 or 10Gbps)?**

* **Do you require BGP MultiPath with ECMP to be configured for setting up a redundant connection to IBM Cloud?**  

    _If yes, please include the ticket ID for the other connection. Ticket Number ____________  (note that ECMP can only be provisioned on two sessions on the same IBM Cloud XCR.  If ECMP is your desire, know that both Direct Links must land on the same router.)_

* **Do you require Local or Global Routing Access?**

    _Customers selecting local routing will only be able to pass traffic between the data centers being serviced from the PoP where the Direct Link was ordered.  Customers wishing to pass traffic outside of the PoP where the Direct Link was ordered will need to add on the global routing option._

* **Do you agree to the fee for Global Routing including the _YOUR LOCATION_ monthly fee and the overage fees outlined below?**

    _Local routing includes access to all of the Data Centers connected directly to the PoP and provides unlimited ingress/egress traffic.  Global routing expands access to include all IBM Cloud’s data centers globally.  Bandwidth is metered when the service can meter traffic. When bandwidth metering occurs, you will be charged monthly based on your market price, as shown in the following table._


### Global Routing Pricing

| Global Routing Ingress | Global Routing Egress |
|---|---|
| Free | 1, 2, or 5Gbps Circuit - 10TB Free bandwidth |
| Free | 10Gbps Circuit - 50TB Free bandwidth |


| Bandwidth Overage Fees |
|---|
| Market 1: $0.05 per GB |
| Market 2: $0.10 per GB |
| Market 3: $0.15 per GB |
