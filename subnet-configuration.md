---

copyright:
  years: 2017, 2025
lastupdated: "2025-06-03"

keywords:

subcollection: direct-link

---

{{site.data.keyword.attribute-definition-list}}

# Configuring Direct Link on Classic
{: #configure-ibm-cloud-direct-link}
{: help}
{: support}

After your {{site.data.keyword.cloud}} Direct Link on Classic connectivity is established, you can follow the steps that are given in this document to configure your subnet to interact with {{site.data.keyword.cloud_notm}}.
{: shortdesc}

In general, to get your Direct Link on Classic connection working, you must do some basic network configuration steps, and then set up Border Gateway Protocol (BGP). During the setup process, an IBM engineer works with you to enable your network to use Virtual Routing Function (VRF) capability, which is required.

## Basic network configuration
{: #basic-network-configuration}

1. Define your remote network that uses the standard RFC1918 private address space.
   * For new environments, the `10.0.0.0/8` space.
   * For existing environments that use `10.0.0.0/8`, we recommend that you obtain a more detailed assessment to ensure that there is not a conflict with the {{site.data.keyword.cloud_notm}} services network, or with the networks that are already assigned to your account.

1. Our staff at {{site.data.keyword.cloud_notm}} assigns a `/31` or `/30` for each connection and configures an interface IP address on the {{site.data.keyword.cloud_notm}} cross-connect router (XCR) infrastructure.

1. Configure the interface on your customer edge router (CER) by using the IP address provided: use the {{site.data.keyword.cloud_notm}} XCR IP as a next-hop for any traffic that is destined to {{site.data.keyword.cloud_notm}}.

1. For return traffic, {{site.data.keyword.cloud_notm}} uses the assigned CER IP as a next-hop for any traffic destined for the remote network, as advertised via BGP.

## Configuring BGP
{: #configuring-bgp}

To exchange route information with your environment, {{site.data.keyword.cloud_notm}} requires BGP to be configured. Options are as follows:

* **ASN**: {{site.data.keyword.cloud_notm}} assigns a private ASN for each customer's use. Alternatively, you can use your own public ASN. Your preference is requested at the time you place your order. Your assigned private ASN is provided to you during the implementation process.

* **VRF**: Using VRF, {{site.data.keyword.cloud_notm}} advertises the specific private subnets that are assigned to your customer account. You must advertise the remote networks that you want to be reachable from the {{site.data.keyword.cloud_notm}} private network. It is your responsibility as a customer to manage the advertisements to and from the IBM Cloud network. (More details about VRF are included in the next section.)

   The following networks are filtered out and cannot be accepted: `10.0.0.0/14`, `10.198.0.0/15`, `10.200.0.0/14`, `169.254.0.0/16`, `224.0.0.0/4`.
   {: note}

* **ECMP**: For customers who elect to build redundancy at a supported location, {{site.data.keyword.cloud_notm}} supports the implementation of equal-cost multipath (ECMP) to provide load balancing and redundancy across the two links. This ECMP setup should be requested at the time of order.

## BGP specifications for IBM Cloud Direct Link
{: #bgp-specifications-for-ibm-cloud-direct-link}

The BGP specifications are as follows:

As stated in the preceding section, BGP is mandatory for managing your routing through Direct Link. An account that orders Direct Link is migrated to a VRF environment.

**Caveats for VLANS and VRF:**
* Inter-account VLAN spanning isn't allowed in the VRF environment.
* IPsec VPN service is limited.

VRF doesn't prevent SSL VPN access, but the behavior changes. Without VRF, one VPN connection is enough to see all servers on your account. With VRF, you can access resources only in the market that is associated with your VPN. So if you connect to the DAL VPN, you can connect to DAL servers only.
{: note}

IBM Cloud ASN is **13884**, for public and private services.
* The default ASN for a customer when ordering is **64999**, but the default can be changed by customer request.
* Optionally, a 4-byte private ASN `4201000000` - `4294967294` can be supported.
* Excluded ASNs: `0`, `13884`, `36351`, `64512`, `64513`, `65100`, `65201-65234`,`65402-65433`, `65500` and 4-Byte ASNs: `4201065000-4201065999`
* If you're using Direct Link Connect with a layer-3 service, such as IP VPN, IBM Cloud establishes BGP with the Direct Link Connect provider's ASN.

**Recommendations, Defaults, and Limits:**

* Tunneling (that is, GRE) is supported and recommended if IP overlap becomes an issue.
* BGP timer defaults are `Keepalive:30`, `Holdtime:90`.
* Authentication is not enabled by default.
* BGP BFD is not enabled by default.
* Maximum received (from customer or provider) prefix limit is 200 per VRF.

## Strict limitations on IP assignments
{: #strict-limitations-on-ip-assignments}

* If you use the 10.x.x.x network, you still cannot create overlap with your hosts within IBM Cloud nor with the IBM Cloud services network, which occupies `10.0.0.0/14`, `10.198.0.0/15`, and `10.200.0.0/14`.

* The following ranges are not allowed in the Federal system and they are rejected by IBM servers: `169.254.0.0/16`, `224.0.0.0/4`.

## Redundancy and diversity
{: #redundancy-and-diversity}

{{site.data.keyword.cloud_notm}} Direct Link provides diversity, and customers are responsible for implementing redundancy through their BGP schemas.

If you select ECMP for redundancy, both BGP sessions must exist on the same XCR; therefore, you give up router diversity and are exposed to risk if the router fails. You gain Layer-3 redundancy, but you lose router diversity.

## Understanding BGP forwarding decisions
{: #understanding-bgp-routing}

{{site.data.keyword.cloud_notm}} BGP Routing and Forward varies by vendor implementation on the on-premises side. This is critical for understanding how you configure your on-premises equipment to work with Direct Link. Failure to understand and plan can result in undesired behavior such as assymetric routing paths or incorrectly preferred routing choices. The following table is ordered from most important to least important. This applies to single paths. Using multiple paths changes this behavior. Follow your router's configuration guide for deviations from these general rules.

|BGP Consideration|Meaning|Preferred Value|
|---|---|---|
|Next Hop Reachable|BGP will not select a route that it cannot communicate with.|N/A|
|Weight (Cisco Only)|Cisco-specific metric for preferring a path.|Higher Value Preferred|
|Local_Pref|Vendor-agnostic metric for preferring a path.|Higher Value Preferred|
|Locally Injected Routes|If your router is originating the routes, prefer it to iBGP/eBGP.|N/A|
|AS_Path length|Number of AS's a route must pass through.|Lower Value Preferred|
|Origin|What **protocol** originated the route.|Internal BGP preferred over External BGP|
|MED|Multi Exit Discriminator, which can prefer one exit path between ASs.|Lower Value is Preferred|
|Neighbor Type|What is the protocol relationship between two ASs?|Prefer Internal BGP to External BGP|
|IGP Metric|What was the IGP Metric of the route?|Lower Value is Preferred|
|Route Age|How old are the routes?|Prefer the oldest route|
{: caption="Figure 1."BGP considerations" caption-side="bottom"}

## More about using VRF
{: #more-about-using-vrf}

All accounts that use an {{site.data.keyword.cloud_notm}} Direct Link solution must migrate to a VRF. For more information, see [FAQs about VRF account migration](/docs/account?topic=account-vrf-faqs).

By using VRF, customers advertise the available routes to their self-defined remote networks. This configuration does not permit you to use self-defined IP addresses on the {{site.data.keyword.cloud_notm}} network.

Migrating to a VRF requires a short outage window (up to 30 minutes for large accounts with multiple VLANs/locations), during which the backend network VLANs lose mutual connectivity while they are moved to the VRF.

VRF eliminates the "VLAN Spanning" option for your account, including any account-to-account VLAN spanning capabilities, because all VLANs are able to communicate unless a gateway appliance is introduced to manage traffic. VRF also limits the ability to use {{site.data.keyword.cloud_notm}} VPN services because it is not compatible with {{site.data.keyword.cloud_notm}} SSL and IPsec VPN services.

An alternative is to use the IBM Cloud Direct Link offering itself to manage your servers, or to run your own VPN solution (such as a Vyatta) that can be configured with different types of VPN. After migrating to a VRF, SSL VPN typically works when a VPN connection is made to the same data center location in which a compute VM is running, but it does not allow access globally.

## Using BYOIP and NAT with Direct Link
{: #using-byoip-and-nat-with-direct-link}

IBM Cloud Direct Link does not offer BYOIP on the private network. Therefore, traffic with a destination IP address that was not assigned by {{site.data.keyword.cloud_notm}} is dropped. However, customers can encapsulate traffic between the remote network and their {{site.data.keyword.cloud_notm}} network that uses GRE, IPsec, or VLAN.

Most commonly, the BYOIP environment is implemented within the scope of either a Network Gateway (Vyatta) or a VMWare NSX deployment. This configuration enables customers to use any desirable IP space on the {{site.data.keyword.cloud_notm}} side, and to route back across the tunnel to the remote network. This configuration must be managed and supported by the customer, independent of {{site.data.keyword.cloud_notm}}. Furthermore, this configuration can break connectivity to the {{site.data.keyword.cloud_notm}} services network if the customer assigns a 10.x.x.x block that {{site.data.keyword.cloud_notm}} has in use for services.

This solution also requires that each host that needs connectivity to the {{site.data.keyword.cloud_notm}} services network and the remote network must have two IP addresses assigned: one from the IBM `10.x.x.x` block, and one from the remote network block. Static routes must be set up on the host to ensure that traffic is routed. You cannot assign IP space directly on the {{site.data.keyword.cloud_notm}} hosts (BYOIP) and have it routable on the {{site.data.keyword.cloud_notm}} network inherently. The only way to implement this ability is as outlined previously, but it is not supported by {{site.data.keyword.cloud_notm}}.

Alternatively, customers frequently assign a remote network block for use in a NAT table that is configured on their remote edge router. This configuration allows customers to limit the changes that are required to both networks, while still translating traffic into a network address space that is compatible with both networks.
