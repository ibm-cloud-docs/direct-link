---

copyright:
  years: 2018
lastupdated: "2018-06-11"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud Direct Link Dedicated 問卷

謝謝您提出對 IBM Cloud Direct Link Dedicated Hosting 的要求。為了完成您的要求，我們想要向您收集一些其他資訊。在問卷處理期間，您隨時可以與工程師交談。完成問卷之後，我們的 Cloud Design Engineering 團隊將檢閱它，並將其呈報「網路工程」以進行實作。

## 確認

1. 本問卷所概述的費用，涵蓋 IBM Cloud 網路基礎架構中的服務終止成本。主機託管成本（包括檔案櫃、交叉連接等）包括主機託管合約中另行概述的月費和一次性費用。

2. IBM Cloud Direct Link Dedicated Hosting 提供 1Gbps 或 10Gbps 光纖交叉連接至 IBM Cloud 專用網路。您需要提供可支援單一模式光纖 (SMF) 上行鏈路的路由器或第 3 層交換器。部署時間會根據您的電路提供者而有所不同，此服務的一般部署時間為 30-60 天。

3. Direct Link Dedicated Hosting 需要您使用 VRF（虛擬遞送及轉遞）實例。這可讓客戶定義自己要使用於其遠端網路的遠端 IP 位址；不過，您必須知道，即使您使用 10.x.x.x 網路，仍然無法與 IBM Cloud 內的主機或 SIBM Cloud 服務網路（10.0.0.0/14、10.198.0.0/15 及 10.200.0.0/14）重疊。當每個 VLAN 移轉至新的配置時，將您的帳戶轉移至 VRF 需要使專用網路短暫中斷。「網路工程」團隊將與您一起定義此活動的時間範圍。

4. VRF 會改變 IBM Cloud SSL、PPTP 及 IPsec VPN 的行為。與所存取之運算系統相同的資料中心位置之間建立 VPN 連線時，這些通常會正常運作，但不容許廣域存取。替代方案是使用 Direct Link 本身來管理您的伺服器，或執行您自己的 VPN 解決方案（例如，Vyatta），它可以用不同類型的 VPN 來配置。 

5. Direct Link Dedicated Hosting 需要 BGP 才能實作遞送至客戶的遠端網路。IBM Cloud 將不會對 IBM Cloud 的通告實作過濾器。IBM Cloud 會通告所有專用子網路指派至您的帳戶。客戶需要妥善管理 IBM Cloud 接收的通告。

6. IBM Cloud 提供雙重上行鏈路（一個針對一個 IBM Cloud 的交叉連接路由器），讓客戶能夠建立備援連線功能。這是運用 ECMP 功能或簡單加權連線，透過 BGP 階段作業在客戶的路由器上達成的。

7. 將無法直接從 Dedicated Hosting 或遠端網路存取 IBM Cloud 服務網路。

8. IBM Cloud 不容許您透過 IBM Cloud 骨幹在遠端網站之間讓資料流量回程。Direct Link 服務是為了讓您的遠端網路能夠與 IBM Cloud 基礎架構進行私人通訊而設計。

9. IBM Cloud 提供具有「區域」或「廣域遞送」的 Direct Link。請確認您需要哪一個遞送套件，並確認您同意與下列鏈結所列的那些套件相關聯的頻寬方案：ibm.biz/DirectLink-Docs。

10. 請指定您計劃透過 Direct Link 推送多少資料流量，以及您打算將此資料流量推送至哪些 IBM Cloud 資料中心。

11. 如果您未透過 IBM Cloud 採購主機託管服務，您將負責訂購並支付環境與 IBM Cloud 之間的交叉連接。連接之後，我們將提供「授權書 (LOA)」，詳述我們核准您的連線及要連接的位置。

12. 請確認您同意 Direct Link 的下列定價：
 * 1Gbps：_依位置定價_ 
* 2Gbps：_依位置定價_
* 5Gbps：_依位置定價_
* 10Gbps：_依位置定價_
* 選用的廣域遞送
