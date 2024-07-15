---

copyright:
  years: 2017, 2024
lastupdated: "2024-07-15"

keywords:

subcollection: direct-link

---

{{site.data.keyword.attribute-definition-list}}

# Virtual routing and forwarding on {{site.data.keyword.cloud_notm}}
{: #overview-of-virtual-routing-and-forwarding-vrf-on-ibm-cloud}

By definition, virtual routing and forwarding (VRF) is a technology that is included in IP network routers. It is delivered as an inherent backbone service.
{: shortdesc}

## Connectivity options for {{site.data.keyword.cloud_notm}}
{: #connectivity-options-for-ibm-cloud}

Dispersed cloud resources are resources in more than one location or in more than one subnet or VLAN. These types of resources require a routing function to communicate among themselves, even within a private network context. This document describes a "multiple isolation" tenancy communication option, which is often called a customer VRF. It is implemented as an MPLS Layer-3 VPN (RFC 4364) across the global {{site.data.keyword.cloud}} backbone.

In general, the {{site.data.keyword.cloud_notm}} platform offers two options for routing across our private network, providing connectivity across pods and data centers:

1. **Multiple isolation:** A dedicated logical network per tenant, which allows no interaction with other tenants’ logical networks.

2. **Shared tenancy:** A common logical network, which is shared by all tenants who use this model, with separation provided by automated Access Control Lists (ACLs), and enabled with VLAN spanning. This option is not described in this document.

The term "customer VRF" is used to describe _multiple isolation_ network connectivity.
{: tip}

## VRF overview: Multiple isolation technology
{: #vrf-overview}

VRF allows multiple instances of a routing table to exist in a router and to work simultaneously. With VRF, each cloud tenant's VRF network is segmented within its routing table. This segmentation allows for IP address overlaps, and it doesn’t create any interaction or interference with other tenant VRFs. {{site.data.keyword.cloud_notm}} uses a large majority of the `10.0.0.0/8` network, which might overlap with many remote networks, for example networks deployed at customer data centers.

Using VRF, {{site.data.keyword.cloud_notm}} tenants are allowed to use remote IP addresses that normally would not be allowed to overlap in the Global table. IBM still reserves the following RFC 1918, link-local addresses, and multicast addresses, which are not routable from this VRF service:

* `10.0.0.0/14`
* `10.200.0.0/14`
* `10.198.0.0/15`
* `169.254.0.0/16`
* `224.0.0.0/4`
* `166.9.0.0/16` (used by the private endpoint service)
* Any IP ranges assigned to your VLANs on the IBM platform.

IBM is moving forward with a next-generation Cloud deployment to enable Virtual Private Cloud (VPC) in our availability zones (AZs). This new VPC capability enables Bring-Your-Own-IP (BYoIP) in the VPC-enabled AZs, which are located in Dallas, Washington DC, London, Frankfurt, Tokyo, and Sydney.

For example, each tenant on the backbone who uses VRF can have only one customer VRF per Direct Link, which provides connectivity among all the tenant’s servers, regardless of location. However, an {{site.data.keyword.cloud_notm}} tenant might have more than one Direct Link account that feeds into a single cross-connect router.
{: note}

* A tenant’s servers in any VLAN, in any pod, in any data center worldwide can reach all of that tenant’s other servers globally.
* Every tenant’s customer VRF is connected to the common shared services network to provide private reachability for those servers to use DNS, shared storage, monitoring, patching, and more.
* The customer VRF is a connectivity service that provides isolation among tenants. Any additional controls that are needed within a tenancy must be provisioned separately by using a gateway, security groups, or host-based controls.

## Benefits of moving to VRF
{: #benefits-of-moving-to-vrf}

Moving to VRF includes the following primary benefits:

* Industry-proven and widely accepted _multiple isolation separation technologies_. Many cloud customers find the Level-3 VPN approach more palatable than ACLs to their auditors and compliance officers.
* {{site.data.keyword.cloud_notm}} customers can extend or migrate the reach of their network significantly, due to addition of new sites or applications throughout the IBM network.
* Tenant-specific routing tables narrow the aperture for IP address overlap, without the risk of overlap with other tenants' subnets or other parts of the network that are not applicable.

Compared to the older ACL model, there are a few minor tradeoffs to take into account:

* Converting to a customer VRF requires a maintenance window, which causes a brief disruption of backbone traffic flows.
* Remote access by using the managed VPN services (SSL, IPsec) is limited to just SSL VPN into a data center; however, the shared ACL over the backbone allows global access from any entry point from either service.
* VLAN spanning is a feature of the shared tenancy model and is not available in a VRF; this will be disabled upon conversion to the Customer VRF.
* IPsec VPN managed service on IBM Cloud classic infrastructure remote access is not available.

Many {{site.data.keyword.cloud_notm}} customers currently operate with a shared tenancy model on the {{site.data.keyword.cloud_notm}} network. During conversion, your shared tenancy is converted to use a customer VRF, most commonly with a new Direct Link subscription.

For specific information about how to initiate a VRF conversion for your account, refer to the conversion instructions for your IBM Cloud offering. For example:

* [VPC conversion instructions](/docs/vpc?topic=vpc-setting-up-access-to-classic-infrastructure&interface=ui#how-you-can-initiate-the-conversion)
* [{{site.data.keyword.cloud_notm}} service endpoints conversion instructions](/docs/account?topic=account-vrf-service-endpoint)
