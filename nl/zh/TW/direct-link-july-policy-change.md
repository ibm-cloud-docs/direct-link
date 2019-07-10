---
copyright:
  years: 2018, 2019
lastupdated: "2019-04-02"

keywords: Intercloud, Frankfurt, PoPs, Connect, Exchange, Chennai, Equinix, Megaport, Kinx, diversity, Bluefringe, CenturyLink, BT, Sao Paulo, Tokyo, Japan, PCCW, Colt, blog, service provider, partner, Telia, Internexion, Packet Fabric, Global Routing, expanded, market

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:important: .important}

# 公告：廣域遞送原則變更從 7 月 1 日開始

2019 年 7 月 1 日生效 - IBM Direct Link 廣域遞送原則變更
{: important}

為了改善客戶體驗並提供更高的價值，我們將加強「IBM Direct Link 廣域遞送」服務。主要改善包括：

* **擴充本地市場：**我們將實作客戶在其「本地市場」內可連接之站台的一致性。我們將讓 IBM Cloud 網路中的每個 PoP 站台都一致，以容許連接至 PoP 站台中 IBM Cloud 的客戶連接至一個以上全球「資料中心」內的資源。

* **新的定價模型：**為了更恰當地讓所選取連線速度的定價一致，我們將變更「IBM Direct Link 廣域遞送」服務的定價模型。

* **無限制的 Direct Link 資料流量：**我們將移除客戶的網路資料流量超額費用，這些客戶在全球範圍內具有 IBM Cloud PoP 與「資料中心」之間 Direct Link 專用網路資料流量的「本端」或「廣域」遞送。

## IBM Cloud Direct Link 廣域遞送概觀
{: #ibm-cloud-direct-link-global-routing-overview}

所有現行 Direct Link 供應項目都包括「本端」遞送，且無額外費用。此服務包括對「本地市場」中 Direct Link 連線所在之「資料中心」的存取權。它透過與客戶帳戶內 IBM Cloud 資源的 Direct Link 專用連線，提供無限制的輸入及輸出資料流量。使用「本端遞送」選項時，Direct Link 資料流量會受限為「本地市場」所提供的服務。

若要在 Direct Link 所連接的「本地市場」（PoP 或「資料中心」）之外遞送網路資料流量，您必須新增「廣域遞送」選項，而此選項可擴充存取權範圍，包括全球所有「IBM Cloud 資料中心」。

「廣域遞送」會套用至個別 Direct Link 服務。「廣域遞送」未透過聚集來套用。其必須指定於偏好給定市場外之連線功能的每個 Direct Link 服務上。

## 擴充 IBM Direct Link 本地市場
{: #announce-expanded-ibm-direct-link-local-markets}

我們將擴充「Direct Link 本地市場」，為全球客戶提供更多的本端遞送選項。下面列出新的「本地市場」指派：

* 達拉斯的本地市場現在將包括丹佛、休斯頓及芝加哥 PoP。
* 華盛頓特區的本地市場現在將包括紐約、亞特蘭大及邁阿密 PoP。
* 聖荷西的本地市場現在將包括洛杉磯 PoP。
* 奧斯陸的本地市場現在將包括斯德哥爾摩 PoP。
* 雪梨的本地市場現在將包括伯斯 PoP。
* 香港的本地市場在啟動之後將包括台北 PoP。
* 東京的本地市場在啟動之後將包括大阪 PoP。
* 清奈的本地市場在啟動之後將包括孟買 PoP。

下列位置中的表格會概述這些變更：https://cloud.ibm.com/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#expanded-ibm-direct-link-local-markets

## IBM Cloud Direct Link 廣域遞送定價模型
{: #announce-ibm-cloud-direct-link-global-routing-pricing-model}

透過所有 IBM Cloud Direct Link 供應項目，「本地市場」內的網路遞送是標準的。在 2019 年 7 月 1 日生效，「廣域遞送」選項的定價會與 Direct Link 連線的連線速度一致。此一致性將透過 Direct Link 供應項目可用的所有連線速度，為客戶提供更好的價值。

定價位於 https://cloud.ibm.com/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-global-routing-add-on

## IBM Cloud Direct Link 廣域遞送網路傳輸超額費用
{: #announce-ibm-cloud-direct-link-global-routing-network-transit-overage-charges}

除了這個公告之外，我們將使用「廣域遞送」選項來撤銷客戶的網路傳輸限制及超額費用。以前的定價包括客戶本地市場之外的輸出資料流量的網路傳輸額度及超額費用。新的定價會刪除這些網路資料流量費用。在此公告生效之後，透過 Direct Link 連線的輸入及輸出資料流量就不會產生超額費用。

## 有效日期
{: #announce-effective-date}

這些變更會在 2019 年 7 月 1 日星期一生效，在此日期之後，將會套用至下一個計費週期的所有新訂單。

請務必注意，如果使用這項更新過的自動化，則在此日期之前，應該適當地更新任何需要「廣域遞送」的 Direct Link 電路。Direct Link 服務的任何升級或降級都會導致自動化，以驗證「廣域遞送」是否存在。如果「廣域遞送」不存在，則所有透過 Direct Link 電路的資料流量都將受限於本地市場。

強烈建議客戶檢閱其在 Direct Link 服務上的 IBM Cloud 遞送，以及開立問題單來重新修補現有 Direct Link 服務上的遞送。
