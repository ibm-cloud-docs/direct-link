---

copyright:
  years: 2017
lastupdated: "2017-09-06"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Configure Direct link

Once your Direct Link connectivity has been established, you can follow the steps given in this document to configure your subnet to interact with IBM Cloud through Direct Link.

In general, to get your Direct Link connection working, you'll need to do some basic network configuration steps, and then you'll need to set up Border Gateway Protocol (BGP). During the setup process, an IBM engineer will work with you to enable your network to use Virtual Routing Function (VRF) capability, which is required.

## Basic Network Configuration

1. Define your remote network using the standard RFC1918 private address space. 
 * For new environments, it is recommended **not** to use the 10.0.0.0/8 space. 
 * For existing environments that utilize 10.0.0.0/8, we recommend that you obtain a more detailed assessment, to ensure that there is not a conflict with the {{site.data.keyword.BluSoftlayer_notm}} services network, or with the networks already assigned to your account.

2. Our staff at {{site.data.keyword.BluSoftlayer_notm}} assigns a /31 or /30 for each connection and configures an interface IP address on the {{site.data.keyword.BluSoftlayer_notm}} cross-connect router (XCR) infrastructure.  

3. Configure the interface on your customer edge router (CER), using the IP address we've provided: just utilize the {{site.data.keyword.BluSoftlayer_notm}} XCR IP as a next-hop for any traffic destined to {{site.data.keyword.BluSoftlayer_notm}}. 

4. For return traffic, {{site.data.keyword.BluSoftlayer_notm}} utilizes the assigned CER IP as a next-hop for any traffic destined for the remote network, as advertised via BGP.

## Configuring BGP

To exchange route information with your environment, {{site.data.keyword.BluSoftlayer_notm}} requires BGP to be configured.  

1. **ASN**: {{site.data.keyword.BluSoftlayer_notm}} assigns a private ASN for each customer's use. Alternatively, you can utilize your own public ASN. Your preference is requested at the time you place your order. Your assigned private ASN is provided to you during the implementation process.

2. **VRF**: Using VRF, {{site.data.keyword.BluSoftlayer_notm}} advertises the specific private subnets assigned to your customer account.  You must advertise the remote networks that you wish to be reachable from the {{site.data.keyword.BluSoftlayer_notm}} private network. The following networks are filtered out and can not be accepted: 0.0.0.0, 10.0.0.0/14, 10.198.0.0/15, 10.200.0.0/14, 169.254.0.0/16, 224.0.0.0/4. It is your responsbility as a customer to manage the advertisements to and from the IBM Cloud network. (More details about VRF are included in the next section.)

3. **ECMP**: For customers who elect to build redundancy at a supported location, {{site.data.keyword.BluSoftlayer_notm}} supports the implementation of equal-cost multipath (ECMP) to provide load balancing and redundancy across the two links. This ECMP setup should be requested at the time of order.

## More about using VRF

All accounts that utilize a Direct Link solution must migrate to a VRF. By using VRF, customers advertise the available routes to their self-defined remote networks. Note that this configuration does not permit you to utilize self-defined IP addresses on the {{site.data.keyword.BluSoftlayer_notm}} network.

Migrating to a VRF is done during the setup process. It requires a short outage window (up to 30 minutes for large accounts with multiple VLANs/locations), during which the backend network VLANs will lose mutual connectivity while they are moved to the VRF. The VRF migration is scheduled with the implementing engineer.

Please note that VRF eliminates the "VLAN Spanning" option for your account, including any account-to-account VLAN spanning capabilities, because all VLANs are able to communicate unless a Gateway Appliance is introduced to manage traffic. VRF also limits the ability to use {{site.data.keyword.BluSoftlayer_notm}} VPN services, because it is not compatible with {{site.data.keyword.BluSoftlayer_notm}} SSL, PPTP, and IPSec VPN services.   

An alternative is to use the Direct Link offering itself to manage your servers, or to run your own VPN solution (such as a Vyatta) that can be configured with different types of VPN. After migrating to a VRF, SSL VPN typically works when a VPN connection is made to the same data center location in which a compute VM is running, but it does not allow access globally.

## Using BYOIP and NAT with Direct Link
IBM Cloud Direct Link does not offer BYOIP on the private network, except in special circumstances covered under the section on [Custom Private Addressing](#custom-private-addressing). Therefore, traffic with a destination IP address that was not assigned by {{site.data.keyword.BluSoftlayer_notm}} will be dropped. However, customers can encapsulate traffic between the remote network and their {{site.data.keyword.BluSoftlayer_notm}} network using GRE, IPSec, or VXLAN.  

Most commonly, the BYOIP environment is implemented within the scope of either a Network Gateway (Vyatta) or a VMWare NSX deployment. This configuration enables customers to use any desirable IP space on the {{site.data.keyword.BluSoftlayer_notm}} side, and to route back across the tunnel to the remote network. Note that this configuration must be managed and supported by the customer, independent of {{site.data.keyword.BluSoftlayer_notm}}. Furthermore, this configuration can break connectivity to the {{site.data.keyword.BluSoftlayer_notm}} services network if the customer assigns a 10.x.x.x block that {{site.data.keyword.BluSoftlayer_notm}} has in use for services. 

This solution also requires that each host needing connectivity to the {{site.data.keyword.BluSoftlayer_notm}} services network and the remote network must have 2 IPs assigned: one must be assigned from the IBM 10.x.x.x block, and one from the remote network block. Static routes must be set up on the host, to ensure that traffic is routed appropriately. You will not be able to assign IP space directly on the {{site.data.keyword.BluSoftlayer_notm}} hosts (BYOIP) and have it routable on the {{site.data.keyword.BluSoftlayer_notm}} network inherently. The only way to implement this ability is as outlined previously, but it is not supported by {{site.data.keyword.BluSoftlayer_notm}}.

Alternatively, customers frequently assign a remote network block for use in a NAT table configured on their remote edge router. This configuration allows customers to limit the changes required to both networks, while still translating traffic into a network address space that is compatible with both networks.

## About Custom Private Addressing

Occasionally, during Direct Link on-boarding, a customer is unable to resolve IP addressing conflicts between their on-premise and {{site.data.keyword.BluSoftlayer_notm}} private networks using the methods described previously. If this situation occurs, a {{site.data.keyword.BluSoftlayer_notm}} engineering or sales representative may recommend that you use _Custom Private Addressing_ (CPA). No additional cost associated with CPA; however, this feature has unique requirements and limitations that you should understand thoroughly before agreeing to its use. These details are described in documentation that will be provided to you by the IBM Cloud representative that recommends CPA. 

The _key requirement_ is that custom private addressing can be activated only on a new, empty {{site.data.keyword.BluSoftlayer_notm}} account and a new Direct Link connection. It is not possible to convert or migrate existing resources to CPA.

Custom private addressing lets you host {{site.data.keyword.BluSoftlayer_notm}} servers in a valid, private IPv4 address range of your choice (10.x.x.x, 192.168.x.x or 172.16.x.x). CPA provides a subset of common IBM Cloud services in a special internally-routed address range, 161.26.x.x, which leaves private IP addresses free for customer use. While CPA enables you to define up to 5 private IP ranges (referred to as _CPA Networks_), each Direct Link connects with only one CPA Network. If additional CPA Networks exist in the account, they will not be accessible through Direct Link.

Custom private addressing leverages VRF and BGP. The implementing engineer will assist you with the details related to CPA.
