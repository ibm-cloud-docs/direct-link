---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-02"

keywords: dedicated, finalize, questionnaire, special network services, billing, fees, VRF, BGP, case, cross-connect, Link Speed, VPN, data center, PoP, ECMP

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

# Direct Link Dedicated on Classic questionnaire
{: #ibm-cloud-direct-link-dedicated-questionnaire}

Thank you for opening a request for IBM Cloud™ Direct Link Dedicated. To finalize your request, we’d like to gather some additional information from you. You can speak with an engineer at any time during the questionnaire process. After you've completed the questionnaire, it is reviewed by our Cloud Design Engineering team and escalated to Special Network Services for implementation.
{:shortdesc}

## Do you acknowledge and agree to the following?
{: #ibm-cloud-direct-link-dedicated-agreement}

1. Each Direct Link connection requires a unique order. If you require multiple connections, open separate Direct Link orders for each connection.
2. The fees for your Direct Link Connect service cover the cost of service termination on the IBM Cloud infrastructure.
   * Infrastructure Services are billed in advance and begin when your order is accepted. However, the Direct Link service billing begins when a Border Gateway Protocol (BGP) session with IBM Cloud is initiated, or 30 days after the service key is provided to the client.

   * Billing stops after:
      * A customer requests a circuit to be deleted, **and**
      * The Dedicated Provider or Network Service Provider de-provisioned the circuit.
   For more information, select your location and go to **Section 5 - Charges** in the Cloud Services Agreement on the [IBM Customer Support website](https://www.ibm.com/support/customer/zz/en/selectcountrylang.html). For example, customers in the United States would view this [Cloud Services Agreement](https://www.ibm.com/support/customer/csol/contractexplorer/cloud/csa/us-en).
3. By ordering the Direct Link service, you are responsible for any fees that are associated with reaching the Point of Presence (PoP) from your remote network and any cross connects needed within the PoP facility. If your provider requires that a router or other device physically sit in the PoP, you're responsible for costs that are associated with collocating that equipment as well. 
4. IBM Cloud will not order a cross-connect on a customer's behalf.
5. IBM Cloud will not colocate any customer equipment in our network PoPs. We accept only ‘cross connects’ which is a fiber Ethernet (single mode fiber only, either 1Gig-LX or 10Gig-LR 1310 nm optics) run from your cage or provider. We do not accept T1s, DS3s, ISDN, POTS line, and so on.  You need to work with your provider to determine whether you must colocate any equipment in the same facility where the IBM Cloud network PoP exists.
6. The Direct Link service is provided in such a way that when you link and the IBM Cloud router it terminates into are both single points of failure (SPOF). If you want to achieve redundancy through the Direct Link service, you need to either order two connections into a Direct Link location with a secondary router, or terminate links into two separate IBM Cloud PoPs.
7. The IBM Cloud services network will not be accessible from your remote networks directly. If this capability changes in the future, you are notified.
8. IBM Cloud will not allow customers to back haul traffic between their remote sites across the IBM Cloud backbone. The Direct Link product is meant for your remote networks to be able to privately communicate with your IBM Cloud infrastructure.
9. After you confirmed that your circuit reached the PoP and is completed by the carrier, you must order the cross connect to the IBM Cloud XCR (cross connect router), which usually takes 2 - 10 business days to complete. This includes the patch down to the IBM Cloud termination port. After completion, you are required to provide IBM Cloud with the cross connect completion notice from the facility provider. IP turn up on the IBM Cloud networking infrastructure is completed within three business days after the cross connect is complete.
10. IBM Cloud Direct Link Dedicated requires the use of a VRF (Virtual Routing and Forwarding) instance. This capability allows customers to define their own remote IP addresses for use in their remote network. However, be aware that if you use the `10.x.x.x` network, you still cannot overlap with your hosts within IBM Cloud nor with the IBM Cloud services network (`10.0.0.0/14`, `10.198.0.0/15`, and `10.200.0.0/14`). Transition of your account to a VRF requires a brief private network outage as each VLAN is migrated into the new configuration. The Special Network Services team works with you to define a window for this activity. The Special Network Services team is available Monday through Friday, 8-5 CST (US Central Standard time). Any activation activity outside this window must be requested through an IBM Support case and approved in advance when engineers are available.
11. VRF is not compatible with IBM Cloud SSL and IPsec VPN services. An alternative is to use the direct link itself for management of your servers or run your own VPN solution (such as a Vyatta) that can be configured with different types of VPN. After migrating to a VRF, SSL VPN typically works when a VPN connection is made to the same DC location as the compute that's being accessed, but does not allow access globally.
12. IBM Cloud Direct Link Dedicated requires BGP to implement routes to a customer's remote network. When your Direct Link service is deployed, IBM Cloud advertises all of the private subnets that are assigned to your account. IBM Cloud does not implement custom filters, AS-Path prepend and custom local-preference to advertisements to the Customer's remote BGP peer. IBM Cloud does not implement filters on the advertisements that are received to IBM Cloud. Customers must properly manage the advertisements to and from IBM Cloud from the customer's edge router. 

## Other questions
{: #dedicated-other-questions}

* Which PoP do you want to terminate the Direct Link into?
* What link speed do you require (1, 2, 5 or 10 Gbps)?
* Do you require BGP MultiPath with ECMP to be configured for setting up a redundant connection to IBM Cloud?

   _If yes, include the case ID for the other connection._   Case Number: ____________

   ECMP can be provisioned only on two sessions on the same IBM Cloud XCR. If ECMP is what you want, know that both Direct Links must land on the same router.
{: note}

* Do you require local or global routing access?

   _Customers selecting local routing are only able to pass traffic between the data centers being serviced from the PoP where the Direct Link was ordered. Customers wanting to pass traffic outside of the PoP where the Direct Link was ordered must dd on the global routing option._

* Do you agree to the fee for global routing including the _YOUR LOCATION_ monthly fee?

   Local routing includes access to all of the data centers connected directly to the PoP and provides unlimited ingress/egress traffic. Global routing expands access to include all IBM Cloud data centers globally. 
