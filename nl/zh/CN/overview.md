---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: overview, connectivity, private network, site-to-site, Exchange, Connect, Dedicated, Hosting, OSI, Layer-3, partners, NNI, latency, backbone

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Direct Link 产品概述
{: #overview-of-direct-link-offerings}

{{site.data.keyword.cloud}} Direct Link 产品提供外部源到客户 IBM Cloud 专用网络的连接。Direct Link 可以视为传统站点到站点 VPN 解决方案的替代方案，其设计用来供在远程网络和 IBM Cloud 环境之间需要更一致、更高吞吐量连接的客户使用。可以使用四种类型的连接：
 
 * **IBM Cloud Direct Link Exchange** 允许客户利用 Exchange 提供商来提供与 IBM Cloud 的连接。Exchange 提供商是已经使用多租户、高容量链路（也称为_网络到网络接口_或 NNI）连接到 {{site.data.keyword.cloud_notm}} 网络的主机托管或数据中心提供商。客户通常可以向此提供商购买虚拟电路，以降低提供连接的成本，这是因为从 {{site.data.keyword.cloud_notm}} 到 Exchange 提供商的物理连接已经就位，并与其他客户共享。
 
 * **IBM Cloud Direct Link Connect** 允许客户利用通过拥有并运营基于设施的网络的承运合作伙伴建立的连接。Connect 提供商是已经使用多租户、高容量链路（也称为_网络到网络接口_或 NNI）连接到 {{site.data.keyword.cloud_notm}} 网络的网络服务提供商 (NSP)。客户通常可以向此提供商购买虚拟电路，从而以更低的成本获得连接，因为从 {{site.data.keyword.cloud_notm}} 到 Connect 提供商的物理连接已经就位，并在其他客户之间共享。
 
 * **IBM Cloud Direct Link Dedicated** 允许客户终止接入 {{site.data.keyword.cloud_notm}} 网络的基于光纤的单租户交叉连接。具有 IBM Cloud PoP 和数据中心相邻的主机托管场所的客户，以及向客户场所或其他数据中心提供电路的网络服务提供商可以利用此产品。
 
 * **IBM Cloud Direct Link Dedicated Hosting** 提供类似于 {{site.data.keyword.cloud_notm}} Direct Link Dedicated 的连接，但是连接点邻近 {{site.data.keyword.cloud_notm}} 数据中心，这样可为性能更高的用例缩短等待时间。{{site.data.keyword.cloud_notm}} 随此解决方案提供各种可定制的主机托管服务。
  
{{site.data.keyword.cloud_notm}} Direct Link 服务是已路由的 OSI 第 3 层服务。它提供与 {{site.data.keyword.cloud_notm}} 专用网络主干的直接连接，其具有较低的等待时间且速度提高为 10Gbps。
为了更灵活第创建此第 3 层连接，{{site.data.keyword.cloud_notm}} Direct Link 支持客户利用：
 * 双 IP（为远程主机）
 * NAT
 * 隧道（为 BYOIP）
 
 有关每种产品的详细描述，请参阅[关于 IBM Cloud Direct Link](/docs/infrastructure/direct-link?topic=direct-link-about-ibm-cloud-direct-link)。
