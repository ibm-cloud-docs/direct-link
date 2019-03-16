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

# Direct Link 中的多樣性及備援性的模型
{: #models-for-diversity-and-redundancy-in-direct-link}

本文件提供一系列與備援性和多樣性問題相關的圖表，可協助您尋找建立最成功 {{site.data.keyword.cloud}} Direct Link 部署的模型，以符合您的需求。這些圖表是按照遞增的複雜性層次來排列，同時亦根據每個圖表所說明的 Direct Link 供應項目來排列。Direct Link 不是交叉連接路由器 (XCR) 上的固有備援服務，客戶有責任透過其邊界閘道通訊協定 (BGP) 綱目來建立備援。 

## 第 1 節：達成多樣性的超簡單配置

此群組中顯示的配置是根據所有資產均位於相同 PoP 及相同的全球市場之事實。

**圖 1：具有多樣性的 Direct Link Exchange，位於相同 PoP（非 AZ）**

![具有多樣性的 Exchange，位於相同 PoP](/images/exchange-diversity-same-pop.png)

**圖 2：具有多樣性的 Direct Link Connect，位於相同 PoP（非 AZ）**

![具有多樣性的 Connect，位於相同 PoP](/images/connect-diversity-same-pop.png)

**圖 3：具有多樣性的 Direct Link Dedicated，位於相同 PoP（非 AZ）**

![具有多樣性的 Dedicated，位於相同 PoP](/images/dedicated-diversity-same-pop.png)

## 第 2 節：包含 AZ 和「廣域遞送」選項的多樣性

此群組中顯示的配置提供跨本端可用性區域及市場連接的選項。

### A 部分：本端可用性區域 (AZ) 中的多樣性

**圖 4：具有多樣性的 Direct Link Exchange，位於本端 AZ（WDC、DAL、FRA、LON）**

![具有多樣性的 Exchange，位於本端 AZ](/images/exchange-diversity-local-az.png)

**圖 5：具有多樣性的 Direct Link Connect，位於本端 AZ（WDC、DAL、FRA、LON）**

![具有多樣性的 Connect，位於本端 AZ](/images/connect-diversity-local-az.png)

**圖 6：具有多樣性的 Direct Link Dedicated，位於本端 AZ（WDC、DAL、FRA、LON）**

![具有多樣性的 Dedicated，位於本端 AZ](/images/dedicated-diversity-local-az.png)

### B 部分：不同當地市場的多樣性，具備「廣域遞送」

**圖 7：具有多樣性和「廣域遞送」的 Direct Link Connect**

![具有多樣性和「廣域遞送」的 Connect](/images/connect-diversity-global.png)

**圖 8：具有多樣性和「廣域遞送」的 Direct Link Exchange**

![具有多樣性和「廣域遞送」的 Exchange](/images/exchange-diversity-global.png)

**圖 9：具有多樣性和「廣域遞送」的 Direct Link Dedicated**

![具有多樣性和「廣域遞送」的 Dedicated](/images/dedicated-diversity-global.png)

## ECMP 的相關資訊

ECMP 是 BGP 的一項特性。有些客戶會詢問我們如何使用 ECMP 作為達到備援的方法。不過，單靠 ECMP 是不夠的。本節說明原因。

**Q：ECMP 是處理備援連線應採取的方法嗎？是否有替代方案？**

ECMP 並非設計來建立備援連線，而是為了平衡兩個鏈結的負載。透過 IBM Cloud 上的 ECMP，兩個連線都必須終止回到相同的 IBM Cloud 交叉連接路由器 (XCR)，而使它成為單一失敗點。（換句話說，當兩個階段作業是位於相同的 IBM Cloud XCR 上時，才能佈建 ECMP）。

**圖 10：ECMP 佈建**

![ECMP Dedicated 模型](/images/ecmp-without-diversity.png)

### 如何達到多樣性和備援

如果您要尋找「高可用性 (HA)」或完全備援，請將兩個鏈結設定到相同資料中心（例如，DAL03）的不同 XCR。然後，視需要使用 BGP 配置來進行失效接手。

**圖 11：具有雙重 XCR 的 ECMP**

![ECMP 雙重 XCR 模型](/images/ecmp-with-diversity.png)
