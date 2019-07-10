---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-02-26"

keywords: limitations, VRF, account-to-account, VPN, BGP, fees, contract, Exchange, Connect, Dedicated, Hosting

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 已知的限制
{: #known-limitations}

首先，本節介紹適用於所有三種 {{site.data.keyword.cloud}} Direct Link 供應項目的限制，然後詳細地個別介紹每項供應項目的部分限制。

## 一般 IBM Cloud Direct Link 限制
{: #general-ibm-cloud-direct-link-limitations}

 * 每個 IBM Cloud Direct Link 連線都需要唯一的訂單。如果您需要多個連線，請為每個連線開立一張 IBM Cloud Direct Link 訂單。
 * 無法直接從您的遠端網路存取 {{site.data.keyword.BluSoftlayer_notm}} 服務網路。
 * {{site.data.keyword.BluSoftlayer_notm}} 將不允許客戶跨越 {{site.data.keyword.BluSoftlayer_notm}} 骨幹回送其遠端網站之間的資料流量。IBM Cloud Direct Link 產品是要讓您的遠端網路與您的 {{site.data.keyword.BluSoftlayer_notm}} 基礎架構私密地進行通訊。
 * IBM Cloud Direct Link 要求您使用 VRF（虛擬遞送及轉遞）實例。
 * VRF 與 {{site.data.keyword.BluSoftlayer_notm}} SSL 及 IPSec VPN 服務並不完全相容。
 * VRF 與 {{site.data.keyword.BluSoftlayer_notm}} 帳戶對帳戶 VLAN 跨距不相容。
 * IBM Cloud Direct Link 需要 BGP 才能建立對客戶遠端網路的路徑。
 * 對於 IBM Cloud Direct Link 基礎架構的變更，必須在美國中部時區上午 8 點到下午 5 點之間進行。
 
## IBM Cloud Direct Link Exchange 及 Direct Link Connect 限制
{: #ibm-cloud-direct-link-exchange-and-direct-link-connect-limitations}

 * 客戶需負擔與從遠端網路聯繫 POP 相關聯的任何費用，以及因 Cloud Exchange 提供者所致的任何費用。
 * {{site.data.keyword.BluSoftlayer_notm}} 不會在我們的網路 POP 中主機託管任何客戶設備。客戶必須與提供者合作，確定他們是否需要主機託管 {{site.data.keyword.BluSoftlayer_notm}} 網路 PoP 所在之設施裡的任何設備。
 * 各地點的 Direct Link Cloud Exchange 可用性會有所不同。客戶可以與 IBM Cloud 客戶經理聯絡，確認目前或未來的可用性。
 
## IBM Cloud Direct Link Dedicated 限制
{: #ibm-cloud-direct-link-dedicated-limitations}

 * IBM Cloud Direct Link Dedicated 的 {{site.data.keyword.BluSoftlayer_notm}} 費用，包含了 {{site.data.keyword.BluSoftlayer_notm}} 基礎架構上的埠終止成本。客戶需負擔與從遠端網路聯繫 PoP 相關聯的任何費用，以及 PoP 設施內所需的任何交叉連接。{{site.data.keyword.BluSoftlayer_notm}} 不會代表任何客戶訂購交叉連接。
 * {{site.data.keyword.BluSoftlayer_notm}} 不會在我們的網路 PoP 中主機託管任何客戶設備。客戶必須與提供者合作，確定他們是否需要主機託管 {{site.data.keyword.BluSoftlayer_notm}} 網路 PoP 所在之設施裡的任何設備。

## IBM Cloud Direct Link Dedicated Hosting 限制
{: #ibm-cloud-direct-link-dedicated-hosting-limitations}

 * IBM Cloud Direct Link Dedicated Hosting 需要 {{site.data.keyword.BluSoftlayer_notm}} 與客戶之間的特定合約。這份合約概述了產品的條款、主機託管環境的定價，以及服務的條款承諾。需要 6、9 或 12 個月的合約。
 * 提供者連線功能受限於所選取資料中心的 On-Net（網內）提供者。
