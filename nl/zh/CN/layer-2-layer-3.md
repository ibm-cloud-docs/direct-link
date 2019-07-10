---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-30"

keywords: layer 2, layer 3, interconnect, partner, multi-cloud, other clouds, BGP, XCR

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 比较 Direct Link 的第 2 层和第 3 层连接
{: #comparing-layer-2-layer-3}

{{site.data.keyword.cloud}} Direct Link 接受来自网络服务提供商 (NSP) 的 OSI 第 2 层和第 3 层合作伙伴互连。某些网络服务提供商为不同网络上的这两个层都提供了服务，但是某些提供商可能选择了**不**将其所有网络互连到 {{site.data.keyword.cloud_notm}} 中。 

规划 {{site.data.keyword.cloud_notm}} Direct Link 部署时，请考虑与第 2 层和第 3 层连接关联的特征，以便您可以创建最符合您需求的部署。

## 第 2 层连接的注意事项
{: #layer-2-networks}

对于每个基于 VLAN 的虚拟电路（您将使用第 2 层合作伙伴互连来创建），您必须在内部部署路由器和 IBM Cloud XCR 之间配置和建立 BGP 会话。IBM Cloud 将为您提供 `/31` IPv4 分配，以与路由器建立 BGP 会话。

* 第 2 层网络为企业和 {{site.data.keyword.cloud_notm}} 之间的简单一对一连接提供选项。 
* 第 2 层服务依赖于 VLAN，而不是 IP 地址。 
* 第 2 层服务可能成本更低，等待时间较短，并且可能消耗的开销低于第 3 层服务。 
* 第 2 层网络不对企业可以启用的第 3 层功能施加限制。

## 第 3 层连接的注意事项
{: #layer-3-networks}

对于第 3 层连接，对于每个虚拟电路，服务提供商会在 IBM Cloud XCR 与提供商的边缘路由器之间建立 BGP 会话。您无需为内部部署路由器配置 IBM Cloud 的 BGP，因为您的服务提供商将管理 IBM Cloud 的 BGP 配置。

* 第 3 层 IP VPN 或 AVPN 网络支持任意位置之间的连接。 
* 第 3 层网络要求网络服务提供商在企业和 {{site.data.keyword.cloud_notm}} 之间维护 BGP 会话。 
* 在使用第 3 层连接（例如 ASN 前置、GRE 隧道等）时，某些网络服务提供商可能会限制其网络中的某些功能。请务必向提供商核实可能的限制。

## 合作伙伴互连表
{: #partner-interconnection-table}

下表汇总了每个 {{site.data.keyword.cloud_notm}} 合作伙伴提供的连接类型。 

|合作伙伴 | 互连类型 |  
|-------|-------|
| AT&T NetBond® for Cloud | 第 3 层|
|AT&T Cloud Gateway（以前称为 RedFringe）| 第 3 层|
|Bell Canada | 第 3 层| 
|British Telecom | 第 3 层| 
| CenturyLink IP VPN | 第 3 层| 
| CenturyLink Dynamic Connections |第 2 层| 
|Chief Telecomm|第 2 层|
|Colt |第 2 层| 
|Console Connect by PCCW |第 2 层|
| Digital Realty Service Exchange |第 2 层| 
|Epsilon|第 2 层| 
|IBM BlueFringe| 第 3 层| 
|Intercloud| 第 3 层|
|Megaport |第 2 层|
| MWS GNPP | 第 3 层|
| Neutrona |第 2 层|
|NTT| 第 3 层|
|PacketFabric |第 2 层|
|Softbank| 第 3 层|
|SES Networks|第 2 层|
| Tata IZO™ Private Connect  | 第 3 层| 
|Telia | 第 3 层|
|Telstra | 第 3 层|
| Tokai |第 2 层| 
| Verizon SCI| 第 3 层|
| Zayo Cloud Link |第 2 层|
