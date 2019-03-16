---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-02-19"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 競爭定價概觀
{: #competitive-pricing-overview}

企業選擇使用專用雲端交互連接（例如，{{site.data.keyword.cloud}} Direct Link、AWS Direct Connect、Google Cloud Interconnect 以及 Microsoft Azure ExpressRoute）的原因有很多，包括卓越的網路效能、安全與隱私權需求，以及降低頻寬成本。雖然您的公司可能因為效能及安全優點而採用專用雲端交互連接網路架構，但是在許多使用實務中，相關聯的網路成本降低是一個明確支持 IBM Cloud Direct Link 的測量指標。 

## 為何選擇 IBM Direct Link？
{: #why-choose-ibm-cloud-direct-link}

IBM 的 Direct Link 標準費率對於積極使用雲端資源的客戶來說意義重大。計算 Direct Link 與其競爭對手的 TCO 即可證明此事實。

目前，10Gbps 的 Dedicated Direct Link 連線在北美的定價為 $4,999。此供應項目提供透過該連線，無限輸入及輸出 IBM Cloud 資源。Direct Link 沒有計量選項。

下列比較反映最具競爭力的價格點。本文章最後面的表格依照地理區域，顯示此價格比較的詳細摘要。

## AWS
{ #aws}

AWS（例如，Google 及 Microsoft）推出計量供應項目，輸入便宜，但輸出卻價格差異很大。
* AWS 10Gbps 定價包含埠小時數，每月 $1,620 循環計價 (MRC)，加上輸出的 $.02/GB 傳送費用（北美）。
* 公平比較 IBM Cloud Direct Link Dedicated，AWS Direct Connect 10Gbps 連線一個月輸出 5% 用量（或 170TB）會花費客戶 $5,020，而 Direct Link 10Gbps 連線則需 $4,999。任何資料輸出只要一個月超過 5% （或 170TB）便以 Direct Link 的固定費率定價模型較為划算。
* 更明顯的比較是，假設 AWS 客戶一個月輸出 50% 用量（或 1.7PB），需花費 $35,620，而 10Gbps Direct Link 連線則需 $4,999。

## Google
{: #google}

Google（例如，AWS 及 Microsoft）推出計量供應項目，輸入便宜，但輸出卻價格差異很大。

* Google 10Gbps 定價設為 $1,750 MRC，加上輸出的 $.02/GB 傳送費用（北美）。
* 公平比較 IBM Cloud Direct Link Dedicated，Google Cloud (GCP) 10Gbps 埠一個月輸出 5% 用量 (170TB) 會花費客戶 $5,172，而 Direct Link 10Gbps 連線則需 $4,999。 
* 任何資料輸出只要一個月超過 5% （或 170TB）便以 Direct Link 的固定費率定價模型較為划算。
* 更明顯的比較是，假設 Google 客戶一個月輸出 50% 用量（或 1.7 PB），需花費 $35,772，而 10Gbps Direct Link 連線則需 $4,999。

## Microsoft
{ #microsoft}

Microsoft（例如，Google 及 AWS）推出計量供應項目，輸入便宜，但輸出卻價格差異很大。Microsoft 也提供無限定價表。下一節會比較這兩個選項。

### 計量
{: #metered}

* Microsoft Azure 10Gbps 定價包含埠費用 ($5,000 MRC)，加上輸出的 $.02/GB 傳送費用（北美）。從一開始，「所有」資料傳送都比 IBM Cloud Direct Link 更昂貴！！！
* 公平比較 IBM Cloud Direct Link Dedicated，Microsoft Azure Express Route 10Gbps 埠一個月輸出 5% 用量（或 170TB）會花費客戶 $8,400，而 Direct Link 10Gbps 連線則需 $4,999。 
* 任何資料輸出只要一個月超過 1TB，便以 Direct Link 的固定費率定價模型較為划算。
* 更明顯的比較是，假設 Microsoft Azure 客戶一個月輸出 50% 用量（或 1.7 PB），需花費 $47,500，而 10Gbps Direct Link 連線則需 $4,999。


### 非計量 
{: #unmetered}

* Microsoft Azure 10Gbps 定價包含埠費用 $51,000 MRC，無限輸入及輸出。

* 公平比較 IBM Cloud Direct Link Dedicated，這個每月花費金額 $51,000，而 10Gbps Direct Link 連線則需 $4,999。 

## 摘要表格
{: #summary-table}

請視需要水平捲動，以檢視全部 5 個直欄的比較。

**附註：**
* **下表中的資訊取自這些公司的公用網站。**
* **10 Gbps 連線量用於比較價格。**
* **用量根據每月持續使用 5 Gbps 或資料傳送 1.7 PB。**


|地區| IBM 無限 | Azure 無限 | Azure 計量 |AWS 計量（地區內部）|
|-----|-----|-----|-----|-----|
|USA | $4,999 | $51,300 | $47,500 | $35,620 |
| TOR/MON/AMS | $5,149 | $51,300 | $47,500 | $35,620 |
| LON/OSL/STO/MEX | $5,349 | $51,300 | $47,500 | $35,620 |
| PAR/FRA/MIL | $5,499 | $51,300 | $47,500 | $35,620 |
|SEO| $5,499 | $51,300 | $90,000 | $73,020 |
| SNG/HKG | $5,699 | $82,000 | $90,000 | $73,020 |
|TOK| $5,999 |$82,000 | $90,000 | $73,020 |
| MEL/SYD | $5,999 |$82,000 | $90,000 | $73,020 |
|CHE| $5,999 |$82,000 | $90,000 | $78,120 |
|SAO| $5,999 |$82,000 | $242,350 | $188,620 |


