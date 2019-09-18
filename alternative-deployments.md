---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-01"

keywords: use case, alternatives, deployments, diverse, redundant, default, multi-cloud, other clouds, schematic

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Alternatives for your IBM Cloud Direct Link Deployment
{: #alternatives-for-your-ibm-cloud-direct-link-deployment}

This document illustrates some alternatives that our customers sometimes choose as use cases for their {{site.data.keyword.cloud}} Direct Link deployments.

## Diverse deployments for Exchange and Connect
{: #diverse-deployments-for-exchange-and-connect}

The default deployments of Direct Link Connect and Direct Link Exchange do not include redundant configuration, although they can be deployed diversely on discrete routers.

Many of our customers choose to create redundant deployments by setting up an additional Direct Link connection. This document presents some schematic representations of alternate IBM Cloud Direct Link deployments.

![Diverse Exchange](/images/Direct-Link-Exchange-Diverse.png "Diverse Exchange"){: caption="Figure 1. A diverse IBM Cloud Direct Link Exchange deployment" caption-side="bottom"}

IBM Cloud Direct Link also makes it easy to establish diverse Connect deployments, as shown in the following figure.

![Diverse Connect](/images/Direct-Link-Connect-Diverse.png "Diverse Connect"){: caption="Figure 2. A redundant and diverse IBM Cloud Direct Link Connect deployment" caption-side="bottom"}

## Using Exchange and Connect in conjunction with other clouds
{: #using-exchange-and-connect-in-conjunction-with-other-clouds}

Some of our customers wish to use Direct Link Exchange in conjunction with other cloud providers, such as AWS, Azure, or Google Cloud. The following schematic shows an overview of how to establish this type of connection with a Cloud Exchange provider.

![Other Clouds Exchange](/images/Direct-Link-Exchange-Other-Clouds.png "Other Clouds Exchange"){: caption="Figure 3. Using IBM Cloud Direct Link Exchange in conjunction with other clouds" caption-side="bottom"}

Some of our customers wish to use Direct Link Connect  in conjunction with other cloud providers, such as AWS, Azure, or Google Cloud. The following schematic shows an overview of how to establish this type of connection with a Telco/NSP.

![Other Clouds Connect](/images/Direct-Link-Connect-other-clouds.png "Other Clouds Connect"){: caption="Figure 4. Using IBM Cloud Direct Link Connect in conjunction with other clouds" caption-side="bottom"}
