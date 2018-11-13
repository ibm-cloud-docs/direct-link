---

copyright:
  years: 2017, 2018
lastupdated: "2018-08-09"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 关于 IBM Cloud Direct Link

在本节中，您可以浏览有关四个 IBM Cloud Direct Link 解决方案各自的主要功能和好处的更多详细信息。
  * [**IBM Cloud Direct Link Exchange**](#the-ibm-cloud-direct-link-exchange-solution)
  * [**IBM Cloud Direct Link Connect**](#the-ibm-cloud-direct-link-connect-solution)
  * [**IBM Cloud Direct Link Dedicated**](#the-ibm-cloud-direct-link-dedicated-solution)
  * [**IBM Cloud Direct Link Dedicated Hosting**](#the-ibm-cloud-direct-link-dedicated-hosting-solution)

## IBM Cloud Direct Link Exchange 解决方案

通过 IBM Cloud Direct Link Exchange 解决方案，客户可以利用 Cloud Exchange 提供商来提供与 {{site.data.keyword.BluSoftlayer_notm}} 位置的连接。此产品通常以降低的成本提供连接，这是因为从 {{site.data.keyword.BluSoftlayer_notm}} 到云交换提供商的物理连接已经就位，在其他客户之间共享。

**常见用例：**_最适合混合工作负载、跨提供商工作负载、使用高输出带宽进行大型或频繁数据传输、专用工作负载和环境管理。通常，当所需的 PoP 位置已经具有所需的 IBM Cloud Direct Link Exchange 提供商时，会选择此选项。_

![图 1](/images/Direct-Link-Exchange.png)

 * **终止位置：**{{site.data.keyword.BluSoftlayer_notm}} 存在点 (PoP)。

 * **典型部署时间：**对 Equinix 提供商而言，典型部署时间为几小时。对其他提供商而言，是电路到达交换位置后 5-10 天。总体部署时间可能是 30-60 天，具体取决于向 NSP 或承运方订购电路时您的位置和需求。

 * **交叉连接详细信息：**安全 Cloud Exchange 互连的物理交叉连接在 {{site.data.keyword.BluSoftlayer_notm}} 与 Cloud Exchange 提供商之间维护。客户向云交换提供商请求“虚拟线路”，这会在他们与云交换提供商互连时，建立与 {{site.data.keyword.BluSoftlayer_notm}} 的逻辑连接。

 * **端口速度选项：**选择 50Mbps、100Mbps、200Mbps、500Mbps 或 1Gbps。

 * **估计等待时间：**等待时间在当地区域（具有相同三字母前缀（如 DAL、AMS、MEL 等）的数据中心）大约为 1.5 毫秒。请参阅 http://lg.softlayer.com/ 以获取实时 PoP 到 PoP (P2P) 位置等待时间测量值。

 * **并置服务：**无。

 * **冗余：**要为 IBM Cloud Direct Link Exchange 建立冗余，需要连接到 2 个以上的位置，也可以选择一个位置，而该位置要有 Cloud Exchange 提供商可利用的辅助 XCR。

 * **当地/全球路由选项：**缺省路由选项是当地路由选项。通过该选项，可以访问与 Direct Link PoP 具有相同市场的数据中心（以诸如 DAL、AMS 或 MEL 等表示）。需要全球路由选项作为附加组件，以将市场内的 IBM Cloud 资源与当地市场外的数据中心的其他 IBM Cloud 资源相连。该选项用于在 IBM Cloud 资源之间共享工作负载（例如达拉斯到阿什本，或达拉斯到法兰克福）。
 
## IBM Cloud Direct Link Connect 解决方案

**常见用例**类似于 Direct Link Exchange 解决方案。提供更多速度选项。Direct Link Cloud Connect 解决方案为 IBM Cloud 网络客户提供了更低成本的入口点。

![图 2](/images/Direct-Link-Connect.png)

* **终止位置：**{{site.data.keyword.BluSoftlayer_notm}} 存在点 (PoP)。

* **典型部署时：**在线路到达交换后 5-10 天。总体部署时间可能是 30-60 天，具体取决于向 NSP 或承运方订购电路时您的位置和需求。

* **交叉连接详细信息：**Direct Link Connect 互连的物理交叉连接在 {{site.data.keyword.BluSoftlayer_notm}} 与 Connect 提供商之间维护。客户向 Cloud Connect 提供商请求“虚拟电路”，这会在他们与 Cloud Connect 提供商互连时，建立与 {{site.data.keyword.BluSoftlayer_notm}} 的逻辑连接。

* **端口速度选项：**选择 50Mbps、100Mbps、200Mbps、500Mbps、1Gbps、2Gbps 或 5Gbps。

* **估计等待时间：**等待时间在当地区域（具有相同三字母前缀（如 DAL、AMS、MEL 等）的数据中心）大约为 1.5 毫秒。请参阅 http://lg.softlayer.com/ 以获取实时 PoP 到 PoP (P2P) 位置等待时间测量值。

* **并置服务：**无。

* **冗余：**要为 IBM Cloud Direct Link Connect 建立冗余，需要连接到 2 个以上的位置，也可以选择一个位置，而该位置要有 IBM Cloud Connect 提供商可利用的辅助 XCR。

* **当地/全球路由选项：**缺省路由选项是当地路由选项。通过该选项，可以访问与 Direct Link PoP 具有相同市场的数据中心（以诸如 DAL、AMS 或 MEL 等表示）。需要全球路由选项作为附加组件，以将市场内的 IBM Cloud 资源与当地市场外的数据中心的其他 IBM Cloud 资源相连。该选项用于在 IBM Cloud 资源之间共享工作负载（例如达拉斯到阿什本，或达拉斯到法兰克福）。

## IBM Cloud Direct Link Dedicated 解决方案

通过 IBM Cloud Direct Link Dedicated 解决方案，客户可以终止接入自己 {{site.data.keyword.BluSoftlayer_notm}} 专用网络的专用单模式光纤交叉连接。

 **常见用例：**_适用于混合工作负载、跨提供商工作负载、大型或频繁数据传输、专用工作负载和环境管理。通常在以下情况下会选择此选项：(1) 所需的 PoP 没有所需的 IBM Cloud Direct Link Exchange 提供商，(2) 为了获取需要高吞吐量的高性能工作负载，或者 (3) 为了实现 IBM Cloud Direct Link Exchange 实施模型无法满足的合规性需求。_

![图 3](/images/Direct-link-Dedicated.png)

 * **终止位置：**{{site.data.keyword.BluSoftlayer_notm}} 存在点 (PoP)。

 * **典型部署时：**在新线路到达 POP 之后的 10-15 个工作日。总体部署时间可能是 30-60 天，具体取决于向 NSP 或承运方订购电路时您的位置和需求。

 * **交叉连接详细信息：**{{site.data.keyword.BluSoftlayer_notm}} 提供授权证 (LOA)，客户使用该授权证来订购光纤以太网（仅限单模式光纤：1Gig-LX 或 10Gig-LR 光学），其运行范围从客户框架或提供商到 {{site.data.keyword.BluSoftlayer_notm}} CFA 终止点，从而系结到交叉连接路由器 (XCR) 基础架构。媒体必须为 1310nm 波长的光学媒体。

 * **端口速度选项：**选择 1Gbps、2Gbps、5Gbps 或 10Gbps。

 * **估计等待时间：**等待时间在当地区域（具有相同三字母前缀（如 DAL、AMS、MEL 等）的数据中心）大约为 1.5 毫秒。请参阅 http://lg.softlayer.com/ 以获取实时 PoP 到 PoP (P2P) 位置等待时间测量值。

 * **并置服务：**无。

 * **冗余：**要建立冗余，IBM Cloud Direct Link 需要连接到超过 2 个位置，也可以选择一个位置，而该位置要有可用的辅助 XCR 和第二个 IBM Cloud Direct Link 连接请求。

 * **当地/全球路由选项：**缺省路由选项是当地路由选项。通过该选项，可以访问与 Direct Link PoP 具有相同市场的数据中心（以诸如 DAL、AMS 或 MEL 等表示）。需要全球路由选项作为附加组件，以将市场内的 IBM Cloud 资源与当地市场外的数据中心的其他 IBM Cloud 资源相连。该选项用于在 IBM Cloud 资源之间共享工作负载（例如达拉斯到阿什本，或达拉斯到法兰克福）。

## IBM Cloud Direct Link Dedicated Hosting 解决方案

IBM Cloud Direct Link Dedicated Hosting 解决方案提供类似于 IBM Cloud Direct Link Dedicated 的连接，但是连接点邻近 {{site.data.keyword.BluSoftlayer_notm}} 数据中心，因此可以缩短等待时间，适合性能更高的用例。IBM Cloud 随此解决方案提供各种可定制并置服务并使用简单定价。

**常见用例：**_适用于非标准计算技术、专用存储器需求或利用现有 IT 投资。_

![图 4](/images/Direct-Link-Dedicated-Hosting.png)

* **终止位置：**{{site.data.keyword.BluSoftlayer_notm}} 数据中心 (DC)。

 * **典型部署时：**最终完成所有需求并执行合同后的 30-60 天。

 * **交叉连接详细信息：**在部署过程中，{{site.data.keyword.BluSoftlayer_notm}} 从 {{site.data.keyword.BluSoftlayer_notm}} 交叉连接路由器 (XCR) 基础架构向客户的并置环境提供 1G 或 10G 光纤连接。如果未请求并置服务（如果已经连接现有环境），那么 {{site.data.keyword.BluSoftlayer_notm}} 会提供授权证 (LOA)，客户使用该授权证来订购光纤以太网（仅限单模式光纤：1Gig-LX 或 10Gig-LR 光学），其运行范围从客户框架到 {{site.data.keyword.BluSoftlayer_notm}} CFA 终止点，从而系结到交叉连接路由器 (XCR) 基础架构。媒体必须为 1310nm 波长的光学媒体。

 * **端口速度选项：**选择 1Gbps、2Gbps、5Gbps 或 10Gbps。

 * **估计等待时间：**在当地数据中心内，等待时间大约为 0.5 毫秒。

 * **并置服务：**是。

 * **冗余：**作为产品的一部分，{{site.data.keyword.BluSoftlayer_notm}} 提供与两个交叉连接路由器 (XCR) 的连接。要建立冗余连接，客户必须在每个 Direct Link 连接上根据实现冗余的需要来配置 BGP。示例包括诸如以下内容的选项：_首选最低 MED_、_首选最高 local-preference_ 或_首选更短 AS 路径_。

 * **当地/全球路由选项：**缺省路由选项是当地路由选项。通过该选项，可以访问与 Direct Link PoP 具有相同市场的数据中心（以诸如 DAL、AMS 或 MEL 等表示）。需要全球路由选项作为附加组件，以将市场内的 IBM Cloud 资源与当地市场外的数据中心的其他 IBM Cloud 资源相连。该选项用于在 IBM Cloud 资源之间共享工作负载（例如达拉斯到阿什本，或达拉斯到法兰克福）。
