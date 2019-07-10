---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-01"

keywords: pricing, competition, AWS, Microsoft, Azure, Google, metered, Dedicated, performance, bandwidth, ingress, egress, charges, unmetered, flat rate, apples-to-apples, enterprise, private cloud, costs

subcollection: direct-link

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

企业之所以会选择使用私有云互连（例如，{{site.data.keyword.cloud}} Direct Link），原因有很多，包括卓越的网络性能、安全性和隐私需求，以及更低的带宽成本。虽然公司可能会因为性能和安全性优势而采用私有云互连网络体系结构，但在许多使用方案中，使用 IBM Cloud Direct Link 明显能使关联的网络成本下降更多。 

## 为什么选择 IBM Cloud Direct Link？
{: #why-choose-ibm-cloud-direct-link}

IBM Direct Link 的标准费率对于活跃使用云资源的客户体现了重大价值。通过计算 Direct Link 的 TCO 并与其竞争对手的 TCO 进行比较，可证明这一事实。

目前在北美，10 Gbps 专用 Direct Link 连接的价格为 4,999 美元。此产品允许通过连接对 IBM Cloud 资源进行无限制输入和输出。Direct Link 没有计量选项。

下面的比较反映了针对假定示例的引爆点。本文末尾的表按地理区域显示了此价格比较的详细摘要。

## 公司 A
{: #company-a}

公司“A”提供一种计量产品，其中输入很便宜，但输出的定价差异很大。
* 公司“A”10 Gbps 定价包括端口小时数（1,620 美元的每月经常性费用 (MRC)）以及输出的传输费 0.02 美元/GB（在北美）。
* 从相对于 IBM Cloud Direct Link Dedicated 的同类比较角度，公司“A”Direct Link 的等效 10 Gbps 连接如果在一个月内的输出使用率为 5%（或 170 TB），那么客户的成本将为 5,020 美元，而 Direct Link 10 Gbps 连接的成本为 4,999 美元。如果一个月内的任何数据输出使用率超过 5%（或 170 TB），那么使用 Direct Link 的统一费率定价模型更合算。
* 为了更鲜明地进行比较，假定在一个月内输出使用率达 20%（或 680 TB），公司“A”客户在给定月份的成本将为 15,220 美元，而 10 Gbps Direct Link 连接的成本为 4,999 美元。

## 公司 G
{: #company-g}

公司 G 提供一种计量产品，其中输入很便宜，但输出的定价差异很大。

* Company G 10 Gbps 定价设置为 1,750 美元 MRC 以及输出的传输费 0.02 美元/GB（在北美）。
* 从相对于 IBM Cloud Direct Link Dedicated 的同类比较角度，公司“G”Direct Link 的等效 10 Gbps 连接如果在一个月内的输出使用率为 5% (170 TB)，那么客户的成本将为 5,172 美元，而 Direct Link 10 Gbps 连接的成本为 4,999 美元。 
* 如果一个月内的任何数据输出使用率超过 5%（或 170 TB），那么使用 Direct Link 的统一费率定价模型更合算。
* 为了更鲜明地进行比较，假定在一个月内输出使用率达 20%（或 680 TB），公司“G”客户在给定月份的成本将为 15,330 美元，而 10 Gbps Direct Link 连接的成本为 4,999 美元。

## 公司 M
{: #company-m}

公司“M”（与公司“A”和公司“G”类似）提供了一种计量产品，其中输入很便宜，但输出的定价差异很大。公司“M”还提供了无限制的定价表。后面的各部分中对这两种选项进行了比较。

### 计量
{: #metered}

* 公司“M”10 Gbps 定价包括端口费（5,000 美元 MRC）以及输出的传输费 0.02 美元/GB（在北美）。从一开始，传出的任何数据所用成本就比 IBM Cloud Direct Link 更高！！！
* 从相对于 IBM Cloud Direct Link Dedicated 的同类比较角度，公司“M”Direct Link 的等效 10 Gbps 端口如果在一个月内的输出使用率为 5%（或 170 TB），那么客户的成本将为 8,400 美元，而 Direct Link 10 Gbps 连接的成本为 4,999 美元。 
* 如果一个月内任何数据输出超过 1 TB，那么使用 Direct Link 的统一费率定价模型更合算。
* 为了更鲜明地进行比较，假定在一个月内输出使用率达 20%（或 680 TB），公司“M”客户在给定月份的成本将为 22,000 美元，而 10 Gbps Direct Link 连接的成本为 4,999 美元。


### 不计量 
{: #unmetered}

* 公司“M”Direct Link 的等效 10 Gbps 定价包括端口费 51,000 美元 MRC，支持无限制输入和输出。

* 从同类比较的角度来看 IBM Cloud Direct Link Dedicated，此每月成本总计为 51,000 美元，而 Direct Link 10 Gbps 连接的成本为 4,999 美元。 

## 摘要表
{: #summary-table}

请根据需要水平滚动以查看所有 5 列的比较。

**注：**

* **用于价格比较的是 10 Gbps 连接大小。**
* **使用率基于每月 2 Gbps 持续数据传输率或 680 TB 数据传输量。**


|地区|IBM 无限制| 公司“M”无限制| 公司“M”计量|公司“A”计量（区域内）|
|-----|-----|-----|-----|-----|
|美国 |4,999 美元|51,300 美元|22,000 美元| 15,220 美元 |
|TOR/MON/AMS|5,149 美元|51,300 美元|22,000 美元| 15,220 美元 |
|LON/OSL/STO/MEX|5,349 美元|51,300 美元|22,000 美元| 15,220 美元 |
|PAR/FRA/MIL|5,499 美元|51,300 美元|22,000 美元| 15,220 美元 |
|SEO|5,499 美元|51,300 美元| 39,000 美元 | 30,180 美元 |
|SNG/HKG|5,699 美元|82,000 美元|39,000 美元 | 30,180 美元 |
| TOK/MEL/SYD |5,999 美元|82,000 美元| 39,000 美元 | 30,180 美元 |
|CHE|5,999 美元|82,000 美元|39,000 美元 | 32,220 美元 | 
|SAO|5,999 美元|82,000 美元| 99,500 美元 | 76,420 美元 |

## 相关文章
{: #related-article}

[_The Information_, Companies surprised by cloud bills....![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.theinformation.com/articles/as-aws-use-soars-companies-surprised-by-cloud-bills?utm_medium=email&utm_source=cio)
