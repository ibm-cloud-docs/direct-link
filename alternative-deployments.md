---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-01"

keywords: use case, alternatives, deployments, diverse, redundant, default, multi-cloud, other clouds, schematic

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

# Alternatives for your Direct Link on Classic deployment
{: #alternatives-for-your-ibm-cloud-direct-link-deployment}

Here are alternatives that customers sometimes choose as use cases for their Direct Link on Classic deployments.
{:shortdesc}

## Diverse deployments for Connect and Exchange on Classic
{: #diverse-deployments-for-exchange-and-connect}

The default deployments of Direct Link Connect and Direct Link Exchange on Classic do not include redundant configuration, although they can be deployed diversely on discrete routers.

Many customers choose to create redundant deployments by setting up an additional Direct Link connection. This document presents some schematic representations of alternative Direct Link on Classic deployments.

![Diverse Exchange](/images/Direct-Link-Exchange-Diverse.png "Diverse Exchange"){: caption="Figure 1. A diverse IBM Cloud Direct Link Exchange deployment" caption-side="bottom"}

IBM Cloud Direct Link also makes it easy to establish diverse Connect deployments, as shown in the following figure.

![Diverse Connect](/images/Direct-Link-Connect-Diverse.png "Diverse Connect"){: caption="Figure 2. A redundant and diverse IBM Cloud Direct Link Connect on Classic deployment" caption-side="bottom"}

## Using Connect and Exchange on Classic along with other clouds
{: #using-exchange-and-connect-in-conjunction-with-other-clouds}

Some customers want to use Direct Link Connect on Classic along with other cloud providers, such as AWS, Azure, or Google Cloud. The following schematic shows an overview of how to establish this type of connection with a Telco (NSP).

![Other Clouds Connect](/images/Direct-Link-Connect-other-clouds.png "Other Clouds Connect"){: caption="Figure 4. Using Direct Link Connect in conjunction with other clouds" caption-side="bottom"}

Some customers want to use Direct Link Exchange on Classic along with other cloud providers, such as AWS, Azure, or Google Cloud. The following schematic shows an overview of how to establish this type of connection with a Cloud Exchange provider.

![Other Clouds Exchange](/images/Direct-Link-Exchange-Other-Clouds.png "Other Clouds Exchange"){: caption="Figure 3. Using IBM Cloud Direct Link Exchange in conjunction with other clouds" caption-side="bottom"}
