---

copyright:
  years: 2019
lastupdated: "2019-06-21"

keywords: 

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

# Your responsibilities by using IBM Cloud Direct Link
{: #responsibilities-direct-link}

Learn about management responsibilities that you have when you use {{site.data.keyword.cloud}} Direct Link on Classic. For overall terms of use, refer to the IBM Cloud Terms and Notices.
{: shortdesc}

## Management responsibilities
{: #responsibilities}

IBM provides you with the ability to connect to an enterprise cloud platform to deploy your workload. You choose how to set up, integrate, back up, and operate your workloads in the cloud.

### Direct Link and IBM Cloud infrastructure

IBM's responsibilities:
- Provide partner relationships with physical locations for Direct Link interconnects.
- Deploy a fully managed, highly available, secured, IBM-owned infrastructure.
- Fulfill requests for Direct Link connections.

Your responsibilities:
- Use the provided capabilities, and adjust networking configurations to meet the needs of your workload.
- Establish diversity and redundancy as needed.
- Make sure that any self-provided BGP addresses do not conflict with blocks that are used by IBM or by resources external to your deployment
- Design and deploy your workload in a way that achieves the wanted availability and DR capabilities by using our provided tools. For example, deploy in different zones of a region, use at least two load balancers that are located in different zones, and either use DNS records to point to the load balancers, or ensure that your application can handle a list of IP addresses that it can connect to.

### Security-rich environment
{: #security-rick-environment}

IBM's responsibilities:
- Provide infrastructure only.
- Maintain controls commensurate to current industry compliance standards.
- Enable security features.

Your responsibilities:
- Restrict user access to the appropriate resources.
- Encrypt your data.
- Assess and implement your wanted security measures.

## Abuse of IBM Cloud Virtual Private Cloud
{: #abuse-of-vpc}

Clients must not misuse IBM Cloud infrastructure.

Misuse includes:
- Any illegal activity
- Distribution or execution of malware
- Harming IBM Cloud infrastructure or interfering with the use of IBM Cloud infrastructure
- Harming or interfering with the use of any other service or system
- Unauthorized access to any service or system
- Unauthorized modification of any service or system
- Violation of the personal rights of others

See [Cloud Services terms](/docs/overview/terms-of-use?topic=overview-terms) for overall terms of use.
