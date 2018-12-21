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

# IBM Cloud Direct Link Exchange 問卷

謝謝您提出對 IBM Cloud Direct Link Exchange 的要求。為了完成您的要求，我們想要向您收集一些其他資訊。在問卷處理期間，您隨時可以與工程師交談。完成問卷之後，我們的 Cloud Design Engineering 團隊將檢閱它，並將其呈報給 Special Network Services 以進行實作。

## 您確認並同意下列事項嗎？

1. 每個 Direct Link 連線都需要唯一的訂單。如果您需要多個連線，請針對每一個連線開啟個別的 Direct Link 訂單。

2. Direct Link Exchange 服務的費用涵蓋 IBM Cloud 基礎架構上的服務終止的成本。 

 * 「基礎架構服務」會事先計費，並從接受您的訂單之後開始；不過，由於 IBM Cloud Direct Link 的本質，Direct Link 服務計費將在起始與 IBM Cloud 的「邊界閘道通訊協定 (BGP)」階段作業時開始，或在提供服務金鑰給客戶之後 30 天開始。 

 * 計費將在發生下列情況之後停止：
   * 客戶要求要刪除電路，**且** 
   * 「Exchange 提供者」或「網路服務提供者」已取消佈建電路。
  * 如需相關資訊，請參閱下列鏈結的「雲端服務合約」中的**第 5 項 - 費用**：[ibm.biz/service-agreement](ibm.biz/service-agreement)
  * 或者，如果通知客戶其 Direct Link 服務將關閉且不再運作，則會對客戶停止計費。

3. 訂購 Direct Link 服務之後，從您的遠端網路連上「據點 (PoP)」以及在 PoP 設施內為了連上 Exchange 提供者所需要的任何交叉連接，其任何相關聯費用將由您負責。您（或您的提供者）也要負責購買通往 IBM Cloud 的虛擬電路。如果您的提供者需要路由器或其他裝置實際位於 PoP 中，則主機託管該設備的相關聯成本也將由您負責。請確認您的網路或 PoP 提供者可以連上 Direct Link Exchange，並且可以將相關聯的成本定出價格。

4. IBM Cloud 將不會在我們的網路 POP 中主機託管任何客戶設備。您需要與提供者合作，以判定是否需要將任何設備主機託管於 IBM Cloud PoP 所在的相同設施中。

5. Direct Link Exchange 服務的提供方式是讓您的鏈結及可讓它終止的 IBM Cloud 路由器均成為單一失敗點 (SPOF)。如果您要透過 Direct Link Exchange 服務達到備援，則需要將鏈結終止於兩個不同的 IBM Cloud 網路 PoP，或訂購兩個連線透過次要路由器進入 Direct Link Exchange 位置。

6. IBM Cloud 服務網路將無法直接從您的遠端網路存取。如果這在未來有所變更，您會收到通知。

7. IBM Cloud 不容許客戶跨越 IBM Cloud 骨幹回送其遠端網站之間的資料流量。Direct Link Exchange 產品是為了讓您的遠端網路能夠與 IBM Cloud 基礎架構進行私人通訊。

8. 在確認電路已達到 Direct Link Exchange PoP 之後，您需要向 Cloud Exchange 提供者下訂單，並將所有相關資訊提供給 Cloud Exchange 提供者及 IBM Cloud。若為 Equinix 提供者，一般部署時間可能需要數小時。IBM Cloud Direct Link Exchange 供應項目的一般部署時間需要 5-10 天才能完成。 

9. IBM Cloud Direct Link Exchange 需要在 IBM Cloud 網路端使用 VRF（虛擬遞送與轉遞）實例。這可讓客戶定義自己要使用於其遠端網路的遠端 IP 位址；不過，您必須知道，即使您可以使用 10.x.x.x 網路，但仍然無法與 IBM Cloud 內的主機或 IBM Cloud 服務網路（10.0.0.0/14、10.198.0.0/15 及 10.200.0.0/14）重疊。當每個 VLAN 移轉至新的配置時，將您的帳戶轉移至 VRF 需要使專用網路短暫中斷。Special Network Services 團隊將與您一起定義此活動的時間範圍，且正常上班時間為星期一到五的 8-5 CST（美國中部標準時間）。在此時間範圍外的任何啟動活動，將需要事先透過問題單要求並核准，如果工程師有空的話。 

10. VRF 與 IBM Cloud SSL、PPTP 及 IPSEC VPN 服務並不相容。替代方案是使用 Direct Link 本身來管理您的伺服器，或執行您自己的 VPN 解決方案（例如，Vyatta），它可以用不同類型的 VPN 來配置。移轉至 VRF 之後，與所存取之運算系統相同的 DC 位置之間建立 VPN 連線時，SSL VPN 通常會正常運作，但不容許廣域存取。

11. IBM Cloud Direct Link Exchange 需要 BGP 才能實作遞送至客戶的遠端網路。當部署 Direct Link 服務之後，IBM Cloud 會通告所有將指派至您帳戶的專用子網路。IBM Cloud 不會對「客戶」的遠端 BGP 對等節點的通告實作自訂過濾器、AS-Path prepend 及自訂本端喜好設定。IBM Cloud 將不會對 IBM Cloud 接收的通告實作過濾器。客戶需要從客戶的邊緣路由器妥善管理傳給或來自 IBM Cloud 的通告。

## 其他問題

* **您是否確認並接受_您的位置_對於 IBM Cloud Direct Link Exchange 連線的定價？**

* **IBM Cloud 將指派專用 ASN 給您，以便配置 BGP 向 IBM Cloud 專用網路通告您的遠端網路。這樣您可以接受嗎？或是您偏好使用自己的公開 ASN？**

* **您是否需要配置具有 ECMP 的 BGP MultiPath，來設定 IBM Cloud 的備援連線？**  

    _如果是，請包含其他連線的問題單 ID。問題單號碼 ____________（請注意，ECMP 只能佈建在相同 IBM Cloud XCR 上的兩個階段作業中。如果 ECMP 符合您的期望，則請瞭解兩個 Direct Link 必須位於相同的路由器上。） 

* **您需要「區域」或「廣域遞送」存取權？**

    _選取區域遞送的客戶只能在已訂購 Direct Link 的 PoP 所處理的資料中心之間傳遞資料流量。想要在已訂購 Direct Link 的 PoP 外面傳遞資料流量的客戶，需要附加廣域遞送選項。_

* **您是否同意「廣域遞送」的費用，包括_您的位置_的月費以及下列超額費用？**

    _區域遞送包括對直接連接到 PoP 的所有「資料中心」的存取，並提供無限制輸入/輸出資料流量。廣域遞送擴大存取範圍，能包括全球所有 IBM Cloud 資料中心。當服務可以為資料流量計量時，頻寬即開始計量。發生頻寬計量時，將根據您的市場價格按月收費，如下表所示。_


### 廣域遞送定價

| 廣域遞送輸入 | 廣域遞送輸出 |
|---|---|
| 免費 | 1、2 或 5Gbps 電路 - 10TB 免費頻寬|
| 免費 | 10Gbps 電路 - 50TB 免費頻寬|


|頻寬超額費用|
|---|
| 市場 1：每 GB $0.05|
| 市場 2：每 GB $0.10|
| 市場 3：每 GB $0.15|
