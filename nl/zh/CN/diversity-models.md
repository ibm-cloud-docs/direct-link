---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-19"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Direct Link 中的多样性和冗余模型
{: #models-for-diversity-and-redundancy-in-direct-link}

本文档提供了一系列与冗余和多样性问题相关的简要图表，可帮助您找到用于创建满足您需求的最成功 {{site.data.keyword.cloud}} Direct Link 部署的模型。简要图表按复杂性程度从低到高进行排列，同时还依据每个简要图表所演示的 Direct Link 产品。Direct Link 不是交叉连接路由器 (XCR) 上的固有冗余服务，客户负责通过其边界网关协议 (BGP) 模式来创建冗余。 

## 第 1 部分：实现多样性的相对简单配置

此组中显示的配置依赖的事实情况是：所有资产位于同一 PoP 中以及同一全球市场中。

**图 1：同一 PoP（非 AZ）中使用多样性的 Direct Link Exchange**

![同一 PoP 中使用多样性的 Exchange](/images/exchange-diversity-same-pop.png)

**图 2：同一 PoP（非 AZ）中使用多样性的 Direct Link Connect**

![同一 PoP 中使用多样性的 Connect](/images/connect-diversity-same-pop.png)

**图 3：同一 PoP（非 AZ）中使用多样性的 Direct Link Dedicated**

![同一 PoP 中使用多样性的 Dedicated](/images/dedicated-diversity-same-pop.png)

## 第 2 部分：包含 AZ 和全球路由选项的多样性

此组中显示的配置提供用于跨当地可用性专区和市场进行连接的选项。

### A 部分：当地可用性专区 (AZ) 中的多样性

**图 4：当地 AZ（WDC、DAL、FRA 和 LON）中使用多样性的 Direct Link Exchange**

![当地 AZ 中使用多样性的 Exchange](/images/exchange-diversity-local-az.png)

**图 5：当地 AZ（WDC、DAL、FRA 和 LON）中使用多样性的 Direct Link Connect**

![当地 AZ 中使用多样性的 Connect](/images/connect-diversity-local-az.png)

**图 6：当地 AZ（WDC、DAL、FRA 和 LON）中使用多样性的 Direct Link Dedicated**

![当地 AZ 中使用多样性的 Dedicated](/images/dedicated-diversity-local-az.png)

### B 部分：不同的地区市场中的多样性（使用全球路由）

**图 7：使用多样性和全球路由的 Direct Link Connect**

![使用多样性和全球路由的 Connect](/images/connect-diversity-global.png)

**图 8：使用多样性和全球路由的 Direct Link Exchange**

![使用多样性和全球路由的 Exchange](/images/exchange-diversity-global.png)

**图 9：使用多样性和全球路由的 Direct Link Dedicated**

![使用多样性和全球路由的 Dedicated](/images/dedicated-diversity-global.png)

## 关于 ECMP 的更多信息

ECMP 是 BGP 的一个功能。一些客户已经要求我们使用 ECMP 作为实现冗余的方法。但是，仅仅使用 ECMP 是不够的。本部分将说明个中原因。

**问：ECMP 是实现冗余连接的方法吗？有哪些替代方法？**

ECMP 并不用于创建冗余连接，而是用于均衡两个链路上的负载。通过 IBM Cloud 上的 ECMP，两个连接都必须终止接入同一个 IBM Cloud 交叉连接路由器 (XCR)，这会使其成为单一故障点。（换言之，ECMP 只能在同一个 IBM Cloud XCR 上作为两个会话供应。）

**图 10：ECMP 供应**

![ECMP Dedicated 模型](/images/ecmp-without-diversity.png)

### 如何实现多样性和冗余

如果需要高可用性 (HA) 或完全冗余：请在同一数据中心（例如 DAL03）中设置两个接入不同 XCR 的链路。然后，根据需要使用 BGP 配置进行故障转移。

**图 11：具有双 XCR 的 ECMP**

![ECMP 双 XCR 模型](/images/ecmp-with-diversity.png)
