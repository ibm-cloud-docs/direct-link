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

# 競争力の高い価格設定の概要
{: #competitive-pricing-overview}

企業は、ネットワーク・パフォーマンスの向上、セキュリティー要件やプライバシー要件への対応、帯域幅のコスト削減といったさまざまな理由で、{{site.data.keyword.cloud}} Direct Link などのプライベート・クラウド相互接続の使用を選択します。お客様の会社では、パフォーマンスとセキュリティーの利点からプライベート・クラウド相互接続ネットワーク・アーキテクチャーを採用するかもしれませんが、関連するネットワーク費用の削減を見れば、多くの使用シナリオにおいて IBM Cloud Direct Link が群を抜いていることは明確です。 

## IBM Cloud Direct Link を選ぶ理由
{: #why-choose-ibm-cloud-direct-link}

IBM の Direct Link の標準の料金設定は、積極的にクラウド・リソースを利用するお客様にとっての大きな価値を反映しています。 このことは、Direct Link と競合で TCO を算出して比較することで裏付けられています。

10Gbps Dedicated Direct Link 接続は現在、北アメリカでは $4,999 に価格設定されています。 このオファリングでは、接続されている IBM Cloud リソース全体への無制限の発着信が可能です。 Direct Link には、従量制オプションはありません。

以下に示す比較では、想定される例に対する優位性を示しています。この記事の最後にある表は、この価格比較を地理的地域別に詳しくまとめたものです。

## A 社
{: #company-a}

A 社が提供する従量制のオファリングは、着信の費用を抑えられますが、発信に対する料金が大きく変動します。
* A 社の 10Gbps の料金設定は、ポート時間の月額料金 (MRC) $1,620 と、発信時に発生する $.02/GB の転送料金から成ります (北アメリカの場合)。
* IBM Cloud Direct Link Dedicated と同一条件で見ると、A 社の Direct Link 相当サービスの 10Gbps 接続で月あたりの発信利用が 5% (つまり 170TB) である場合、お客様は $5,020 の費用を負担することになりますが、これに対して Direct Link の 10Gbps 接続では $4,999 になります。月あたりのデータ発信が 5% (つまり 170TB) を超える場合は、Direct Link の定額料金設定モデルが有利になります。
* より明確な違いを示すために、月あたりの発信利用が 20% (つまり 680 TB) であるとすると、A 社の顧客は月に $15,220 を費やしますが、これに対して 10Gbps Direct Link 接続の場合は $4,999 になります。

## G 社
{: #company-g}

G 社が提供する従量制のオファリングは、着信の費用を抑えられますが、発信に対する料金が大きく変動します。

* G 社の 10Gbps の料金設定は、$1,750 MRC と、発信時に発生する $.02/GB の転送料金から成ります (北アメリカの場合)。
* IBM Cloud Direct Link Dedicated と同一条件で見ると、G 社の Direct Link 相当サービスの 10Gbps ポートで月あたりの発信利用が 5% (170TB) である場合、お客様は $5,172 の費用を負担することになりますが、これに対して Direct Link の 10Gbps 接続では $4,999 になります。 
* 月あたりのデータ発信が 5% (つまり 170TB) を超える場合は、Direct Link の定額料金設定モデルが有利になります。
* より明確な違いを示すために、月あたりの発信利用が 20% (つまり 680 TB) であるとすると、G 社の顧客は月に $15,330 を費やしますが、これに対して 10Gbps Direct Link 接続の場合は $4,999 になります。

## M 社
{: #company-m}

(A 社や G 社と同様に) M 社が提供する従量制のオファリングは、着信の費用を抑えられますが、発信に対する料金が大きく変動します。M 社も無制限価格設定表を提供しています。両方のオプションを、次のセクションで比較します。

### 従量制
{: #metered}

* M 社の料金設定は、ポート料金 ($5,000 MRC) と、発信時に発生する $.02/GB の転送料金から成ります (北アメリカの場合)。最初の時点で、どのようなデータを転送する場合でも IBM Cloud Direct Link よりも費用がかかります。
* IBM Cloud Direct Link Dedicated と同一条件で見ると、M 社の Direct Link 相当サービスの 10Gbps ポートで月あたりの発信利用が 5% (つまり 170TB) である場合、お客様は $8,400 の費用を負担することになりますが、これに対して Direct Link の 10Gbps 接続では $4,999 になります。 
* 月あたりのデータ発信が 1TB を超える場合は、Direct Link の定額価格設定モデルが有利になります。
* より明確な違いを示すために、月あたりの発信利用が 20% (つまり 680 TB) であるとすると、M 社の顧客は月に $22,000 を費やしますが、これに対して 10Gbps Direct Link 接続の場合は $4,999 になります。


### 定額制 
{: #unmetered}

* M 社の Direct Link 相当サービスの 10Gbps 料金設定は、ポート料金が $51,000 MRC で発着信は無制限です。

* IBM Cloud Direct Link Dedicated と同一条件で見ると、この月額費用は $51,000 になりますが、一方 10Gbps Direct Link 接続の場合は $4,999 になります。 

## 要約表
{: #summary-table}

比較の 5 列すべてを見るには、必要に応じて水平にスクロールしてください。

**注:**

* **価格比較には 10 Gbps 接続サイズを使用しています。**
* **使用量は月あたり 2 Gbps 連続 (つまり 680 TB) のデータ転送に基づいています。**


| 地域 | IBM 無制限 | M 社の無制限 | M 社の従量制 | A 社の従量制 (地域内) |
|-----|-----|-----|-----|-----|
| USA | $4,999 | $51,300 | $22,000 | $15,220 |
| TOR/MON/AMS | $5,149 | $51,300 | $22,000 | $15,220 |
| LON/OSL/STO/MEX | $5,349 | $51,300 | $22,000 | $15,220 |
| PAR/FRA/MIL | $5,499 | $51,300 |$22,000 | $15,220 |
| SEO | $5,499 | $51,300 | $39,000 | $30,180 |
| SNG/HKG | $5,699 | $82,000 | $39,000 | $30,180 |
| TOK/MEL/SYD | $5,999 |$82,000 | $39,000 | $30,180 |
| CHE | $5,999 |$82,000 | $39,000 | $32,220 | 
| SAO | $5,999 |$82,000 | $99,500 | $76,420 |

## 関連記事
{: #related-article}

[_The Information_, Companies surprised by cloud bills....![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.theinformation.com/articles/as-aws-use-soars-companies-surprised-by-cloud-bills?utm_medium=email&utm_source=cio)
