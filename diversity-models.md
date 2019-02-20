---

copyright:
  years: 2018, 2019
lastupdated: "2019-01-18"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Models for Diversity and Redundancy in Direct Link

This document gives a series of schematics related to issues of redundancy and diversity, which can help you find a model for creating the most successful {{site.data.keyword.cloud}} Direct Link deployment to meet your needs. The schematics are arranged in increasing levels of complexity and also according to the Direct Link offering that each one is illustrating. Direct Link is not an inherently redundant service at the cross-connect router (XCR), customers have the responsibility for creating redundancy through their border gateway protocol (BGP) schemas. 

## Section 1: Relatively simple configurations that achieve diversity

The configurations shown in this group rely on the fact that all of the assets are located in the same PoP and in the same global market.

**Figure 1: Direct Link Exchange with diversity, in the same PoP (non-AZ)**

![Exchange with diversity in the same PoP](/images/exchange-diversity-same-pop.png)

**Figure 2: Direct Link Connect with diversity in the same PoP (non-AZ)**

![Connect with diversity in the same PoP](/images/connect-diversity-same-pop.png)

**Figure 3: Direct Link Dedicated with diversity in same PoP (non-AZ)**

![Dedicated with diversity in the same PoP](/images/dedicated-diversity-same-pop.png)

## Section 2: Diversity that includes AZs and Global Routing options

The configurations shown in this group offer options for connecting across local availability zones and markets.

### Part A: Diversity in a local availability zone (AZ)

**Figure 4: Direct Link Exchange with diversity in a local AZ (WDC, DAL, FRA, LON)**

![Exchange with diversity in the local AZ](/images/exchange-diversity-local-az.png)

**Figure 5: Direct Link Connect with diversity in a local AZ (WDC, DAL, FRA, LON)**

![Connect with diversity in the local AZ](/images/connect-diversity-local-az.png)

**Figure 6: Direct Link Dedicated with diversity in a local AZ (WDC, DAL, FRA, LON)**

![Dedicated with diversity in the local AZ](/images/dedicated-diversity-local-az.png)

### Part B: Diversity in different local markets, with Global Routing

**Figure 7: Direct Link Connect with diversity and Global Routing**

![Connect with diversity and Global Routing](/images/connect-diversity-global.png)

**Figure 8: Direct Link Exchange with diversity and Global Routing**

![Exchange with diversity and Global Routing](/images/exchange-diversity-global.png)

**Figure 9: Direct Link Dedicated with diversity and Global Routing**

![Dedicated with diversity and Global Routing](/images/dedicated-diversity-global.png)

## More about ECMP

ECMP is a feature of BGP. Some customers have asked us about using ECMP as a way to achieve redundancy. However, ECMP alone is not sufficient. This section explains why.

**Q: Is ECMP the way to go for redundant connections? What alternatives exist?**

ECMP isn’t designed for creating redundant connections but for balancing the load over two links. With ECMP on IBM Cloud, both connections must terminate to the same IBM Cloud cross-connect router (XCR), which makes it a single point of failure. (In other words, ECMP can only be provisioned as two sessions on the same IBM Cloud XCR.)

**Figure 10: ECMP provisioning**

![ECMP Dedicated model](/images/ecmp-without-diversity.png)

### How to achieve Diversity and Redundancy

If you are looking for High Availability (HA) or full redundancy: set up two links into different XCRs in the same data center (for example DAL03). Then failover as needed using BGP configurations.

**Figure 11: ECMP with Dual XCRs**

![ECMP Dual XCR Model](/images/ecmp-with-diversity.png)
