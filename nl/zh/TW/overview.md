---

copyright:
  years: 2017, 2018
lastupdated: "2018-03-14"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 功能概述

IBM Cloud Direct Link 产品提供从外部源到客户 IBM Cloud 专用网络的连接。Direct Link 可以视为传统站点到站点 VPN 解决方案的替代方案，其设计用来供在远程网络和 IBM Cloud 环境之间需要更一致、更高吞吐量连接的客户使用。可以使用四种类型的连接：
 
 * **IBM Cloud Direct Link Exchange** 让客户可以利用 Exchange 提供商来提供与 IBM Cloud 的连接。Exchange 提供商是使用多租户、高容量链接已经连接到 IBM Cloud 网络的承运方或网络提供商。客户通常可以向此提供商购买虚拟电路，以降低提供连接的成本，这是因为从 {{site.data.keyword.BluSoftlayer_notm}} 到 Exchange 提供商的物理连接已经就位，并与其他客户共享。
 
 * **IBM Cloud Direct Link Connect** 让客户可以利用通过合作伙伴建立的连接（合作伙伴拥有并运营基于设施的网络）。利用 IBM Cloud Direct Link Connect，IBM 以及合作伙伴通过第 2 层 10G 双 NNI 在第 2 层和第 3 层与客户连接。
 
 * **IBM Cloud Direct Link Dedicated** 让客户终止接入自己 IBM Cloud 专用网络的专用单模式光纤交叉连接。
 
 * **IBM Cloud Direct Link Dedicated Hosting** 提供类似于 IBM Cloud Direct Link Dedicated 的连接，但是连接点邻近 {{site.data.keyword.BluSoftlayer_notm}} 数据中心，因此可以缩短等待时间，适合性能更高的用例。IBM Cloud 随此解决方案提供各种可定制并置服务。
  
IBM Cloud Direct Link 服务是已传递的 OSI 层 3 服务。它提供与 {{site.data.keyword.BluSoftlayer_notm}} 专用网络主干的直接连接，其具有较低的等待时间且速度提高为 10Gbps。
为了提高创建此第 3 层连接的灵活性，IBM Cloud Direct Link 让客户可以利用：
 * 双 IP（为远程主机）
 * NAT
 * 隧道（为 BYOIP）
