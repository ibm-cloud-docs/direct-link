---

copyright:
  years: 2022
lastupdated: "2024-06-18"

keywords:  direct link prerequisites

subcollection: direct-link

---

{{site.data.keyword.attribute-definition-list}}

# {{site.data.keyword.dl_short}} Dedicated prerequisites
{: #ibm-cloud-dl-dedicated-prerequisites}

When you are ready to finalize your {{site.data.keyword.dl_short}} order, you are asked to read and agree to the following prerequisites. You can speak with an {{site.data.keyword.cloud}} Sales specialist at any time about these terms.
{: shortdesc}

1. Each {{site.data.keyword.dl_full_notm}} connection requires a unique order. If you require multiple connections, order a {{site.data.keyword.dl_short}} for each connection.

1. The {{site.data.keyword.cloud_notm}} fees for {{site.data.keyword.dl_short}} cover the cost of service termination on the {{site.data.keyword.cloud_notm}} infrastructure.

   You are responsible for any fees that are associated with reaching the Point of Presence (PoP) from your remote network and any cross-connects needed within the PoP facility to reach your provider.

   You (or your provider) are also responsible for buying the virtual circuit to {{site.data.keyword.cloud_notm}}. If your provider requires that a router or other device be physically in the PoP, you are responsible for the costs that are associated with colocating that equipment as well. You should confirm that your service or PoP provider can reach the {{site.data.keyword.dl_short}} and price out the associated costs.

1. {{site.data.keyword.cloud_notm}} will not colocate any customer equipment in our network PoPs.

1. The {{site.data.keyword.dl_short}} service is an unprotected path into the {{site.data.keyword.cloud_notm}} environment. If you require redundancy through the {{site.data.keyword.dl_short}} service, you can purchase two separate Direct link connections in a single {{site.data.keyword.cloud_notm}} network PoP on two separate routers, or you can order two single connections into two geographically diverse {{site.data.keyword.dl_short}} PoP locations. It is your responsibility to configure the routing protocols to ensure resiliency between the two links.

1. {{site.data.keyword.cloud_notm}} will not allow customers to backhaul traffic between their remote sites across the {{site.data.keyword.cloud_notm}} backbone.

   The {{site.data.keyword.dl_short}} product is meant for your remote networks to be able to privately communicate with your {{site.data.keyword.cloud_notm}} infrastructure.

1. After you confirm that your circuit reached the {{site.data.keyword.dl_short}} PoP, you must place an order with the service provider to extend service to the {{site.data.keyword.dl_short}} Demarcation point.

   IBM will supply a Letter of Authorization/Connecting Facility Assignment (LOA/CFA) with port information to order the cross connect.

1. Be aware if you use Classic IaaS, that infrastructure uses the `10.x.x.x` network and you cannot overlap your on-premises hosts within {{site.data.keyword.cloud_notm}} or with the {{site.data.keyword.cloud_notm}} services network (`10.0.0.0/14`, `10.198.0.0/15`, and `10.200.0.0/14`).

1. Virtual Routing and Forwarding (VRF) is not compatible with {{site.data.keyword.cloud_notm}} SSL and IPsec VPN services. An alternative is to use the {{site.data.keyword.dl_short}} itself for management of your servers, or run your own VPN solution (such as a Vyatta) that can be configured with different types of VPNs.

   After migrating to a VRF, SSL VPN typically works when a VPN connection is made to the same data center location as the compute that's being accessed, but does not allow access globally.

1. {{site.data.keyword.dl_short}} Cloud requires Border Gateway Protocol (BGP) to implement routes to a customer's remote network.

1. If you choose to use auto-assign IP addressing, IBM will assign two IP addresses from this network, `169.254.0.0/16` for the BGP point-to-point addresses.

   IBM will use the first IP address in the `/30` subnet. The customer can use the second IP address from this subnet.
