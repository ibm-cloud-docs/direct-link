---

copyright:
  years: 2017
lastupdated: "2017-12-12"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Configure IBM Cloud Direct Link

Once your IBM Cloud Direct Link connectivity has been established, you can follow the steps given in this document to configure your subnet to interact with IBM Cloud.

In general, to get your IBM Cloud Direct Link connection working, you'll need to do some basic network configuration steps, and then you'll need to set up Border Gateway Protocol (BGP). During the setup process, an IBM engineer will work with you to enable your network to use Virtual Routing Function (VRF) capability, which is required.

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

All accounts that utilize an IBM Cloud Direct Link solution must migrate to a VRF. By using VRF, customers advertise the available routes to their self-defined remote networks. Note that this configuration does not permit you to utilize self-defined IP addresses on the {{site.data.keyword.BluSoftlayer_notm}} network.

Migrating to a VRF is done during the setup process. It requires a short outage window (up to 30 minutes for large accounts with multiple VLANs/locations), during which the backend network VLANs will lose mutual connectivity while they are moved to the VRF. The VRF migration is scheduled with the implementing engineer.

Please note that VRF eliminates the "VLAN Spanning" option for your account, including any account-to-account VLAN spanning capabilities, because all VLANs are able to communicate unless a Gateway Appliance is introduced to manage traffic. VRF also limits the ability to use {{site.data.keyword.BluSoftlayer_notm}} VPN services, because it is not compatible with {{site.data.keyword.BluSoftlayer_notm}} SSL, PPTP, and IPSec VPN services.   

An alternative is to use the IBM Cloud Direct Link offering itself to manage your servers, or to run your own VPN solution (such as a Vyatta) that can be configured with different types of VPN. After migrating to a VRF, SSL VPN typically works when a VPN connection is made to the same data center location in which a compute VM is running, but it does not allow access globally.
