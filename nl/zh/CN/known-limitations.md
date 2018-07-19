---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-11"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 已知限制

本节首先介绍了适用于所有三个 IBM Cloud Direct Link 产品的限制，然后再分别详细说明每个产品的一些限制。

## 通用 IBM Cloud Direct Link 限制
 * 每个 IBM Cloud Direct Link 连接都需要唯一的订单。如果您需要多个连接，请为每个连接开具一张 IBM Cloud Direct Link 订单。
 * 无法直接通过远程网络访问 {{site.data.keyword.BluSoftlayer_notm}} 服务网络。
 * {{site.data.keyword.BluSoftlayer_notm}} 不允许客户跨 {{site.data.keyword.BluSoftlayer_notm}} 主干在远程站点之间回送流量。IBM Cloud Direct Link 产品旨在让您的远程网络与 {{site.data.keyword.BluSoftlayer_notm}} 基础架构进行专用通信。
 * IBM Cloud Direct Link 需要您使用 VRF（虚拟路由和转发）实例。
 * VRF 与 {{site.data.keyword.BluSoftlayer_notm}} SSL、PPTP 和 IPSec VPN 服务不完全兼容。
 * VRF 与 {{site.data.keyword.BluSoftlayer_notm}} 帐户到帐户 VLAN 生成不兼容。
 * IBM Cloud Direct Link 需要 BGP 才能建立到客户远程网络的路径。
 * 对 IBM Cloud Direct Link 基础架构的更改必须在美国中部时区早上 8 点到下午 5 点之间进行。
 
## IBM Cloud Direct Link Exchange 和 Direct Link Connect 限制
 * 客户负责与从远程网络到达 POP 相关联的任何费用，以及使用云交换提供商所发生的任何费用。
 * {{site.data.keyword.BluSoftlayer_notm}} 在我们的网络 POP 中将不会并置任何客户设备。客户必须与其提供商一起合作，来确定他们是否需要在存在 {{site.data.keyword.BluSoftlayer_notm}} 网络 PoP 的设施中并置任何设备。
 * Direct Link 云交换可用性在不同的位置会有所不同。客户可以联系其 IBM Cloud 客户经理来确认当前或未来可用性。
 
## IBM Cloud Direct Link Dedicated 限制
 * IBM Cloud Direct Link Dedicated 的 {{site.data.keyword.BluSoftlayer_notm}} 费用涵盖 {{site.data.keyword.BluSoftlayer_notm}} 基础架构上的端口终止成本。客户负责与从远程网络到达 PoP 相关联的任何费用，以及 PoP 设施中所需的任何交叉连接。{{site.data.keyword.BluSoftlayer_notm}} 不会代表任何客户来订购交叉连接。
 * {{site.data.keyword.BluSoftlayer_notm}} 在我们的网络 PoP 中将不会并置任何客户设备。客户必须与其提供商一起合作，来确定他们是否需要在存在 {{site.data.keyword.BluSoftlayer_notm}} 网络 PoP 的设施中并置任何设备。

## IBM Cloud Direct Link Dedicated Hosting 限制
 * IBM Cloud Direct Link Dedicated Hosting 要求 {{site.data.keyword.BluSoftlayer_notm}} 与客户之间有特定的合同。此合同概述产品的条款和条件、并置环境的价格以及服务的期限承诺。需要 6、9 或 12 个月的合同。
 * 提供商连接限制为所选数据中心的网络提供商。
