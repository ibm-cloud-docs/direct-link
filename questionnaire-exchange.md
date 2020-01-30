---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-02"

keywords: Exchange, finalize, questionnaire, Special Network Services, billing, fees, VRF, BGP, case, ASN, VPN, metering, data, center, datacenter

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

# Direct Link Exchange on Classic questionnaire
{: #ibm-cloud-direct-link-exchange-questionnaire}

Thank you for opening a request for IBM Cloud™ Direct Link Exchange. To finalize your request, we’d like to gather some additional information from you. You can speak with an engineer at any time during the questionnaire process. After you've completed the questionnaire, it is reviewed by our Cloud Design Engineering team and escalated to Special Network Services for implementation.

## Do you acknowledge and agree to the following?
{: #ibm-cloud-direct-link-exchange-agreement}

1. Each Direct Link connection requires a unique order. If you require multiple connections, you must open separate Direct Link orders for each connection.
2. The fees for your Direct Link Exchange service cover the cost of service termination on the IBM Cloud infrastructure.

* Infrastructure Services are billed in advance and begin when your order is accepted. However, due to the nature of IBM Cloud Direct Link, the Direct Link service billing begins when a Border Gateway Protocol (BGP) session with IBM Cloud is initiated, or 30 days after the service key is provided to the client.

* Billing stops after:
   * A customer requests a circuit to be deleted, **and**
   * The Exchange Provider or Network Service Provider de-provisioned the circuit.
   For more information, select your location and go to **Section 5 - Charges** in the Cloud Services Agreement on the [IBM Customer Support website](https://www.ibm.com/support/customer/zz/en/selectcountrylang.html). For example, customers in the United States would view this [Cloud Services Agreement](https://www.ibm.com/support/customer/csol/contractexplorer/cloud/csa/us-en).

   Alternatively, billing can stop for a customer if a customer is notified that their Direct Link service will be turned off and no longer work.

3. By ordering the Direct Link service, you are responsible for any fees that are associated with reaching the Point of Presence (PoP) from your remote network and any cross-connects needed within the PoP facility to reach your exchange provider. You (or your provider) are also responsible for buying the virtual circuit to IBM Cloud. If your provider requires that a router or other device physically sit in the PoP, you are responsible for the costs that are associated with collocating that equipment as well. Confirm that your network or PoP provider can reach the Direct Link Exchange and can price out the associated costs.
4. IBM Cloud does not colocate any customer equipment in our network PoPs. You must work with your provider to determine whether you must colocate any equipment into the same facility where the IBM Cloud PoP exists.
5. The Direct Link Exchange service is provided in such a way where your link and the IBM Cloud router it can terminate into are both single points of failure (SPOF). If you want to achieve redundancy through the Direct Link Exchange service, you must terminate links into two separate IBM Cloud network PoPs, or order two connections into a Direct Link Exchange location with a secondary router.
6. The IBM Cloud services network is not accessible from your remote networks directly. If this changes in the future, you are notified.
7. IBM Cloud does not allow customers to back haul traffic between their remote sites across the IBM Cloud backbone. The Direct Link Exchange product is meant for your remote networks to be able to privately communicate with your IBM Cloud infrastructure.
8. After you confirm that your circuit reached the Direct Link Exchange PoP, you must place an order with the cloud exchange provider and supply all relevant information to the cloud exchange provider and IBM Cloud. For Equinix providers, typical deployment time can take hours. The typical deployment time for the IBM Cloud Direct Link Exchange offering takes 5 - 10 days to complete.
9. IBM Cloud Direct Link Exchange requires the use of a VRF (Virtual Routing and Forwarding) instance on the IBM Cloud Network side. This allows the customer to define their own remote IP addresses for use in their remote network. However, you must be aware that if you’re able to use the `10.x.x.x` network, you still cannot overlap with your hosts within IBM Cloud nor with the IBM Cloud services network (`10.0.0.0/14`, `10.198.0.0/15`, and `10.200.0.0/14`). Transition of your account to a VRF requires a brief private network outage as each VLAN is migrated into the new configuration. The Special Network Services team works with you to define a window for this activity. The Special Network Services team is normally available Monday through Friday, 8-5 CST (US Central Standard time). Any activation activity outside this window needs to be requested via ticket and approved in advance if engineers are available.
10. VRF is not compatible with IBM Cloud SSL and IPsec VPN services. An alternative is to use the direct link itself for management of your servers, or run your own VPN solution (such as a Vyatta) that can be configured with different types of VPN. After migrating to a VRF, SSL VPN typically works when a VPN connection is made to the same DC location as the compute that is being accessed, but does not allow access globally.
11. IBM Cloud Direct Link Exchange requires BGP to implement routes to a customer's remote network. When your Direct Link service is deployed, IBM Cloud advertises all of the private subnets that are assigned to your account. IBM Cloud will not implement custom filters, AS-Path prepend and custom local-preference to advertisements to the Customer's remote BGP peer. IBM Cloud will not implement filters on the advertisements received to IBM Cloud. Customers need to properly manage the advertisements to and from IBM Cloud from the customer's edge router. 

## Other questions
{: #exchange-other-questions}

* Do you acknowledge and accept the pricing of _YOUR LOCATION_ for the IBM Cloud Direct Link Exchange connection?
* IBM Cloud assigns a private ASN to you for purposes of configuring BGP to advertise your remote networks to your IBM Cloud Private network. Is this private ASN acceptable, or would you prefer to use your own public ASN?
* Do you require BGP MultiPath with ECMP to be configured for setting up a redundant connection to IBM Cloud?

   _If yes, include the case ID for the other connection._   Case Number: ____________

   ECMP can be provisioned only on two sessions on the same IBM Cloud XCR. If ECMP is what you want, know that both Direct Links must land on the same router.
{: note}

* Do you require local or global routing access?

    _Customers selecting local routing can pass traffic only between the data centers being serviced from the PoP where the Direct Link was ordered. Customers wanting to pass traffic outside of the PoP where the Direct Link was ordered must add on the global routing option._
* Do you agree to the fee for global routing including the _YOUR LOCATION_ monthly fee?

    Local routing includes access to all of the data centers connected directly to the PoP and provides unlimited ingress/egress traffic. Global routing expands access to include all IBM Cloud data centers globally. 
