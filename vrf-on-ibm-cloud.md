---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-02-26"

keywords: VRF, IP, routers, backbone, service, VLAN, multiple isolation, tenant, tenancy, datacenters, data, center, shared tenancy, private endpoint, Customer VRF, Private Network Question, support, ticket

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Overview of Virtual Routing and Forwarding (VRF) on IBM Cloud
{: #overview-of-virtual-routing-and-forwarding-vrf-on-ibm-cloud}

By definition, virtual routing and forwarding (VRF) is a technology included in Internet Protocol (IP) network routers. It is delivered as an inherent backbone service.

## Connectivity Options for IBM Cloud

**Dispersed cloud resources** are resources in more than one location, or even in more than one subnet or VLAN. These resources require a routing function to communicate amongst themselves, even within a private network context. This document describes a "multiple isolation" tenancy communication option, which often is called a _Customer VRF_. It is implemented as an MPLS Layer-3 VPN (RFC 4364) across the global {{site.data.keyword.cloud}} backbone.

In general, the IBM Cloud Platform offers two options for routing across our private network, providing connectivity across pods and datacenters:

1. **Shared tenancy:** A common logical network, shared by all tenants who use this model, with separation provided by automated Access Control Lists (ACLs), and enabled with VLAN spanning. (This option is not described in this document.)

2. **Multiple isolation:** A dedicated logical network per tenant, which allows no interaction with other tenants’ logical networks.  

This document uses the term **Customer VRF** to describe _multiple isolation_ network connectivity.

## VRF Overview (multiple isolation technology)

Virtual routing and forwarding (VRF) allows multiple instances of a routing table to exist in a router and to work simultaneously. With virtual routing and forwarding (VRF), each cloud tenant's VRF network is segmented within its routing table. This segmentation allows for IP address overlaps, and it doesn’t create any interaction or interference with other tenant VRFs. IBM Cloud utilizes a large majority of the `10.0.0.0/8` network, which may overlap with many remote networks, for example networks deployed at customer datacenters.

Using Virtual Routing and Forwarding (VRF), IBM Cloud tenants are allowed to use remote IP addresses that normally would not be allowed to overlap in the Global table. IBM still reserves the following RFC 1918, link-local addresses, and multicast addresses, which are not routable from this VRF service:

* `10.0.0.0/14`
* `10.200.0.0/14`
* `10.198.0.0/15`
* `169.254.0.0/16`
* `224.0.0.0/4`
* `166.9.0.0/16`(which the private endpoint service uses)
* Any IP ranges assigned to your VLANs on the IBM platform.

IBM is moving forward with a next-generation Cloud deployment to enable Virtual Private Cloud (VPC) in our Availability Zones. This new VPC capability enables Bring Your own IP (BYoIP) in the VPC-enabled Availability Zones (AZs), which are located in Dallas, Washington DC, London, Frankfurt, Tokyo, and Sydney.

Each tenant on the backbone who utilizes Virtual Routing and Forwarding (VRF) may have one (and only one) _Customer VRF_ per Direct Link, which provides connectivity amongst all the tenant’s servers, regardless of location. However, an IBM Cloud tenant may have more than one Direct Link account that feeds into a single cross-connect router.  

* A tenant’s servers in any VLAN, in any pod, in any datacenter worldwide can reach all of that tenant’s other servers globally.

* Every tenant’s Customer VRF is connected to the common shared services network, to provide private reachability for those servers to use DNS, shared storage, monitoring, patching, and so forth.

* The Customer VRF is a connectivity service that provides isolation among tenants. Any additional controls needed within a tenancy must be provisioned separately, using a gateway, security groups, or host-based controls.

## Benefits of moving to VRF

**The primary benefits include:**

* Industry-proven and widely accepted _multiple isolation_ separation technology. Many cloud customers find the Level-3 VPN approach more palatable (than ACLs) to their auditors and compliance officers.   

* IBM Cloud customers can extend or migrate the reach of their network significantly, due to addition of new sites or applications throughout the IBM network.

* Tenant-specific routing tables narrow the aperture for IP address overlap, without the risk of overlap with other tenants' subnets or other parts of the network that are not applicable.

**A few minor trade-offs, compared to the older ACL model:**  

* Converting to a Customer VRF requires a maintenance window, which causes a brief disruption of backbone traffic flows.

* Remote access by means of the managed VPN services (SSL, IPSec) is limited to the local datacenter; however, the shared ACL backbone allows global access from any entry point.

* VLAN spanning within your _multiple isolation_ tenancy is not available.

## What happens during account conversion process

Many IBM Cloud customers currently operate with a shared tenancy model on the IBM Cloud network. During conversion, the tenancy is converted to use a Customer VRF, most commonly with a new Direct Link subscription, or as otherwise required or requested.  

The conversion process involves a network disruption, while the VLANs and their subnets are detached from the ACL backbone and then attached to the Customer VRF. This process results in a few moments of packet loss for traffic entering or exiting the VLANs. Packets within the VLAN continue to flow. In the cases where a network gateway, such as a FortiGate Security Appliance or Virtual Router Appliance is involved, no disruption occurs among the VLANs attached to that gateway. The servers see no network outage themselves, and most workloads automatically recover when the traffic flow resumes. The total duration of the disruption depends on the extent of the tenant’s topology, that is, the number of subnets, VLANs, and pods that your tenancy includes.

![The conversion process](/images/vrf-on-ibm-cloud.png)

During migration, the VLANs are disconnected from the backbone and reconnected to the Customer VRF.  The duration of disruption varies, depending on the quantity of VLANs, PODs, and datacenters involved. Traffic among VLANs is disrupted, yet the servers stay connected to the network. The application may or may not be affected, depending on its sensitivity to packet loss.

## How you can initiate the conversion
{: #how-you-can-initiate-the-conversion}

Existing IBM Cloud customers can open a support ticket through their [IBM Cloud Console ![External link icon](../../icons/launch-glyph.svg "External link icon")]( https://control.bluemix.net/support/unifiedConsole/tickets/add) account, requesting to be migrated to a VRF. The ticket should state: “Private Network Question” and include the following text in the support ticket:

"We are requesting that account _fill in your account number_ is moved to its own VRF. We understand the risks and approve the change. Please reply back with the scheduled window(s) of time where this change will be made so we can prepare for the migration."

Migration is completed by the IBM Cloud Network Engineering team. No other information is required from you, except an agreed-to schedule. Typically, packet loss may last 15-30 minutes, depending on the complexity of your account. (It may be longer if your account has legacy Direct Link connections). The process is highly automated, requiring minimal interaction by the IBM team, and it should be transparent.
