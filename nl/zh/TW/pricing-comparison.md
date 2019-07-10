---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-01"

keywords: pricing, competition, AWS, Microsoft, Azure, Google, metered, Dedicated, performance, bandwidth, ingress, egress, charges, unmetered, flat rate, apples-to-apples, enterprise, private cloud, costs

subcollection: direct-link

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

企業選擇使用專用雲端交互連接（例如，{{site.data.keyword.cloud}} Direct Link）的原因有很多，包括卓越的網路效能、安全與隱私權需求，以及降低頻寬成本。雖然您的公司可能因為效能及安全優點而採用專用雲端交互連接網路架構，但是在許多使用實務中，相關聯的網路成本降低是一個明確支持 IBM Cloud Direct Link 的測量指標。 

## 為何選擇 IBM Cloud Direct Link？
{: #why-choose-ibm-cloud-direct-link}

IBM 的 Direct Link 標準費率對於積極使用雲端資源的客戶來說意義重大。計算 Direct Link 與其競爭對手的 TCO 即可證明此事實。

目前，10Gbps 的 Dedicated Direct Link 連線在北美的定價為 $4,999。此供應項目提供透過該連線，無限輸入及輸出 IBM Cloud 資源。Direct Link 沒有計量選項。

下列比較反映假設範例的價格點。本文章最後面的表格依照地理區域，顯示此價格比較的詳細摘要。

## 公司 A
{: #company-a}

公司 "A" 提供一個計量供應項目，適合低價的「輸入」，然而「輸出」價格差異很大。
* 公司 "A" 10Gbps 定價包含埠小時數，每月 $1,620 循環計價 (MRC)，加上輸出的 $.02/GB 傳送費用（北美）。
* 公平比較 IBM Cloud Direct Link Dedicated，公司 "A" Direct Link 對等 10Gbps 連線一個月輸出 5% 用量（或 170TB）會花費客戶 $5,020，而 Direct Link 10Gbps 連線則需 $4,999。任何資料輸出只要一個月超過 5% （或 170TB）便以 Direct Link 的固定費率定價模型較為划算。
* 更明顯的比較是，假設一個月輸出 20% 用量（或 680 TB）需花費公司 "A" 客戶指定月份的 $15,220，而 10Gbps Direct Link 連線則需 $4,999。

## 公司 G
{: #company-g}

公司 G 提供一個計量供應項目，適合低價的「輸入」，然而「輸出」價格差異很大。

* 公司 G 10Gbps 定價設為 $1,750 MRC，加上輸出的 $.02/GB 傳送費用（北美）。
* 公平比較 IBM Cloud Direct Link Dedicated，公司 "G" Direct Link 對等 10Gbps 埠一個月輸出 5% 用量 (170TB) 會花費客戶 $5,172，而 Direct Link 10Gbps 連線則需 $4,999。 
* 任何資料輸出只要一個月超過 5% （或 170TB）便以 Direct Link 的固定費率定價模型較為划算。
* 更明顯的比較是，假設一個月輸出 20% 用量（或 680 TB）需花費公司 "G" 客戶指定月份的 $15,330，而 10Gbps Direct Link 連線則需 $4,999。

## 公司 M
{: #company-m}

公司 "M"（例如公司 "A" 及公司 "G"）推出計量供應項目，適合便宜的輸入，然而輸出價格差異很大。公司 "M" 也提供無限制定價表。下一節會比較這兩個選項。

### 計量
{: #metered}

* 公司 "M" 10Gbps 定價包含埠費用 ($5,000 MRC)，加上輸出的 $.02/GB 傳送費用（北美）。從一開始，「所有」資料傳送都比 IBM Cloud Direct Link 更昂貴！！！
* 公平比較 IBM Cloud Direct Link Dedicated，公司 "M" Direct Link 對等 10Gbps 埠一個月輸出 5% 用量（或 170TB）會花費客戶 $8,400，而 Direct Link 10Gbps 連線則需 $4,999。 
* 任何資料輸出只要一個月超過 1TB，便以 Direct Link 的固定費率定價模型較為划算。
* 更明顯的比較是，假設一個月輸出 20% 用量（或 680 TB）需花費公司 "M" 客戶指定月份的 $22,000，而 10Gbps Direct Link 連線則需 $4,999。


### 非計量 
{: #unmetered}

* 公司 "M" Direct Link 對等 10Gbps 定價包含埠費用 $51,000 MRC，無限制輸入及輸出。

* 公平比較 IBM Cloud Direct Link Dedicated，這個每月花費金額 $51,000，而 10Gbps Direct Link 連線則需 $4,999。 

## 摘要表格
{: #summary-table}

請視需要水平捲動，以檢視全部 5 個直欄的比較。

**附註：**

* **10 Gbps 連線量用於比較價格。**
* **用量根據每月持續使用 2 Gbps 或資料傳送 680 TB。**


|地區| IBM 無限制 | 公司 "M" 無限制 | 公司 "M" 計量 | 公司 "A" 計量（地區內部）|
|-----|-----|-----|-----|-----|
|USA | $4,999 | $51,300 | $22,000 | $15,220 |
| TOR/MON/AMS | $5,149 | $51,300 | $22,000 | $15,220 |
| LON/OSL/STO/MEX | $5,349 | $51,300 | $22,000 | $15,220 |
| PAR/FRA/MIL | $5,499 | $51,300 |$22,000 | $15,220 |
|SEO| $5,499 | $51,300 | $39,000 | $30,180 |
| SNG/HKG | $5,699 | $82,000 | $39,000 | $30,180 |
| TOK/MEL/SYD | $5,999 |$82,000 | $39,000 | $30,180 |
|CHE| $5,999 |$82,000 | $39,000 | $32,220 | 
|SAO| $5,999 |$82,000 | $99,500 | $76,420 |

## 相關文章
{: #related-article}

[_The Information_, Companies surprised by cloud bills....![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.theinformation.com/articles/as-aws-use-soars-companies-surprised-by-cloud-bills?utm_medium=email&utm_source=cio)
