---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-02-19"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 具有竞争力的定价概述
{: #competitive-pricing-overview}

企业之所以会选择使用私有云互连（例如，{{site.data.keyword.cloud}} Direct Link、AWS Direct Connect、Google Cloud Interconnect 和 Microsoft Azure Express Route），原因有很多，包括卓越的网络性能、安全性和隐私需求，以及降低带宽成本。虽然公司可能会因为性能和安全性优势而采用私有云互连网络体系结构，但在许多使用方案中，使用 IBM Cloud Direct Link 明显能使关联的网络成本下降更多。 

## 为什么要选择 IBM Direct Link？
{: #why-choose-ibm-cloud-direct-link}

IBM Direct Link 的标准费率对于活跃使用云资源的客户体现了重大价值。通过计算 Direct Link 的 TCO 并与其竞争对手的 TCO 进行比较，可证明这一事实。

目前在北美，10 Gbps 专用 Direct Link 连接的价格为 4,999 美元。此产品允许通过连接对 IBM Cloud 资源进行无限制输入和输出。Direct Link 没有计量选项。

下面的比较反映了针对最大竞争对手的引爆点。本文末尾的表按地理区域显示了此价格比较的详细摘要。

## AWS
{ #aws}

AWS（像 Google 和 Microsoft 一样）提供了一种计量产品，其中输入十分便宜，但输出的定价差异很大。
* AWS 10 Gbps 定价包括端口小时数（1,620 美元每月经常性费用 (MRC)）以及输出的传输费 0.02 美元/GB（在北美）。
* 从同类比较的角度来看 IBM Cloud Direct Link Dedicated，对于 AWS Direct Connect 10 Gbps 连接，如果一个月内的输出使用率为 5%（或 170 TB），那么客户的成本为 5,020 美元，而 Direct Link 10 Gbps 连接的成本为 4,999 美元。如果一个月内的任何数据输出使用率超过 5%（或 170 TB），那么使用 Direct Link 的统一费率定价模型更合算。
* 为了更鲜明地进行比较，假定一位 AWS 客户在一个月内的输出使用率达到 50%（或 1.7 PB），那么成本为 35,620 美元，而 10 Gbps Direct Link 连接的价格为 4,999 美元。

## Google
{: #google}

Google（像 AWS 和 Microsoft 一样）提供了一种计量产品，其中输入十分便宜，但输出的定价差异很大。

* Google 10 Gbps 定价设置为 1,750 美元 MRC 以及输出的传输费 0.02 美元/GB（在北美）。
* 从同类比较的角度来看 IBM Cloud Direct Link Dedicated，对于 Google Cloud (GCP) 10 Gbps 端口，如果一个月内的输出使用率为 5%（或 170 TB），那么客户的成本为 5,172 美元，而 Direct Link 10 Gbps 连接的成本为 4,999 美元。 
* 如果一个月内的任何数据输出使用率超过 5%（或 170 TB），那么使用 Direct Link 的统一费率定价模型更合算。
* 为了更鲜明地进行比较，假定一位 Google 客户在一个月内的输出使用率达到 50%（或 1.7 PB），那么成本为 35,772 美元，而 10 Gbps Direct Link 连接的价格为 4,999 美元。

## Microsoft
{ #microsoft}

Microsoft（像 Google 和 AWS 一样）提供了一种计量产品，其中输入十分便宜，但输出的定价差异很大。Microsoft 还提供了无限定价表。后面的各部分中对这两种选项进行了比较。

### 计量
{: #metered}

* Microsoft Azure 10 Gbps 定价包括端口费（5,000 美元 MRC）以及输出的传输费 0.02 美元/GB（在北美）。从一开始，传出的任何数据所用成本就比 IBM Cloud Direct Link 更高！！！
* 从同类比较的角度来看 IBM Cloud Direct Link Dedicated，对于 Microsoft Azure Express Route 10 Gbps 连接，如果一个月内的输出使用率为 5%（或 170 TB），那么客户的成本为 8,400 美元，而 Direct Link 10 Gbps 连接的成本为 4,999 美元。 
* 如果一个月内任何数据输出超过 1 TB，那么使用 Direct Link 的统一费率定价模型更合算。
* 为了更鲜明地进行比较，假定一位 Microsoft Azure 客户在一个月内的输出使用率达到 50%（或 1.7 PB），那么成本为 47,500 美元，而 10 Gbps Direct Link 连接的价格为 4,999 美元。


### 不计量 
{: #unmetered}

* Microsoft Azure 10 Gbps 定价包括端口费 51,000 美元 MRC，支持无限制输入和输出。

* 从同类比较的角度来看 IBM Cloud Direct Link Dedicated，此每月成本总计为 51,000 美元，而 Direct Link 10 Gbps 连接的成本为 4,999 美元。 

## 摘要表
{: #summary-table}

请根据需要水平滚动以查看所有 5 列的比较。

**注：**
* **下表中的信息是从这些公司的公共 Web 站点获取的。**
* **用于价格比较的是 10 Gbps 连接大小。**
* **使用率基于每月 5 Gbps 持续数据率或每月 1.7 PB 数据传输量。**


|地区|IBM 无限制|Azure 无限制|Azure 计量|AWS 计量（区域内）|
|-----|-----|-----|-----|-----|
|美国 |4,999 美元|51,300 美元|47,500 美元|35,620 美元|
|TOR/MON/AMS|5,149 美元|51,300 美元|47,500 美元|35,620 美元|
|LON/OSL/STO/MEX|5,349 美元|51,300 美元|47,500 美元|35,620 美元|
|PAR/FRA/MIL|5,499 美元|51,300 美元|47,500 美元|35,620 美元|
|SEO|5,499 美元|51,300 美元|90,000 美元|73,020 美元|
|SNG/HKG|5,699 美元|82,000 美元|90,000 美元|73,020 美元|
|TOK|5,999 美元|82,000 美元|90,000 美元|73,020 美元|
|MEL/SYD|5,999 美元|82,000 美元|90,000 美元|73,020 美元|
|CHE|5,999 美元|82,000 美元|90,000 美元|78,120 美元|
|SAO|5,999 美元|82,000 美元|242,350 美元|188,620 美元|


