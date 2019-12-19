---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-02"

keywords: diversity, redundancy, schematics, deployment, configuration, global routing, ECMP, Dual XCRs, model

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

# Models for diversity and redundancy in Direct Link on Classic
{: #models-for-diversity-and-redundancy-in-direct-link}

This document gives a series of schematics that are related to issues of redundancy and diversity, which can help you find a model for creating the most successful {{site.data.keyword.cloud}} Direct Link deployment to meet your needs. The schematics are arranged in increasing levels of complexity and also according to the Direct Link offering that each one is illustrating. Direct Link is not an inherently redundant service at the cross-connect router (XCR), customers have the responsibility for creating redundancy through their border gateway protocol (BGP) schemas.
{:shortdesc}

## Section 1: Relatively simple configurations that achieve diversity
{: #section-1-diversity-models}

The configurations that are shown in this group rely on the fact that all of the assets are located in the same PoP and in the same global market.


![Exchange with diversity in the same PoP](/images/exchange-diversity-same-pop.png "Exchange with diversity in the same PoP"){: caption="Figure 1. Direct Link Exchange with diversity, in the same PoP (non-AZ)" caption-side="top"}

![Connect with diversity in the same PoP](/images/connect-diversity-same-pop.png "Connect with diversity in the same PoP"){: caption="Figure 2: Direct Link Connect with diversity in the same PoP (non-AZ)" caption-side="top"}

![Dedicated with diversity in the same PoP](/images/dedicated-diversity-same-pop.png "Dedicated with diversity in the same PoP"){: caption="Figure 3: Direct Link Dedicated with diversity in same PoP (non-AZ)" caption-side="top"}

## Section 2: Diversity that includes AZs and global routing options
{: #section-2-diversity-models}

The configurations that are shown in this group offer options for connecting across local availability zones and markets.

### Part A: Diversity in a local availability zone (AZ)
{: #section-2-part-a}

![Exchange with diversity in the local AZ](/images/exchange-diversity-local-az.png "Exchange with diversity in the local AZ"){: caption="Figure 4: Direct Link Exchange with diversity in a local AZ (WDC, DAL, FRA, LON)" caption-side="top"}

![Connect with diversity in the local AZ](/images/connect-diversity-local-az.png "Connect with diversity in the local AZ"){: caption="Figure 5: Direct Link Connect with diversity in a local AZ (WDC, DAL, FRA, LON)" caption-side="top"}

![Dedicated with diversity in the local AZ](/images/dedicated-diversity-local-az.png "Dedicated with diversity in the local AZ"){: caption="Figure 6: Direct Link Dedicated with diversity in a local AZ (WDC, DAL, FRA, LON)" caption-side="top"}

### Part B: Diversity in different local markets, with global routing
{: #section-2-part-b}

![Connect with diversity and global routing](/images/connect-diversity-global.png "Connect with diversity and global routing"){: caption="Figure 7: Direct Link Connect with diversity and global routing" caption-side="top"}

![Exchange with diversity and global routing](/images/exchange-diversity-global.png "Exchange with diversity and global routing"){: caption="Figure 8: Direct Link Exchange with diversity and global routing" caption-side="top"}

![Dedicated with diversity and global routing](/images/dedicated-diversity-global.png "Dedicated with diversity and global routing"){: caption="Figure 9: Direct Link Dedicated with diversity and global routing" caption-side="top"}

## More about ECMP
{: #more-about-ecmp}

ECMP is a feature of BGP. Some customers asked us about using ECMP as a way to achieve redundancy. However, ECMP alone is not sufficient. This section explains why.

**Q: Is ECMP the way to go for redundant connections? What alternatives exist?**

ECMP isn’t designed for creating redundant connections but for balancing the load over two links. With ECMP on {{site.data.keyword.cloud_notm}}, both connections must terminate to the same IBM Cloud cross-connect router (XCR), which makes it a single point of failure. (In other words, ECMP can be provisioned as two sessions only on the same {{site.data.keyword.cloud_notm}} XCR.)

![ECMP Dedicated model](/images/ecmp-without-diversity.png "ECMP Dedicated model"){: caption="Figure 10: ECMP provisioning" caption-side="top"}

### Achieving diversity and redundancy
{: #how-to-achieve-diversity-and-redundancy}

If you are looking for High Availability (HA), or full redundancy, set up two links into different XCRs in the same data center (for example DAL03). Then, fail over as needed using BGP configurations.

![ECMP Dual XCR Model](/images/ecmp-with-diversity.png "ECMP Dual XCR Model"){: caption="Figure 11: ECMP with Dual XCRs" caption-side="top"}
