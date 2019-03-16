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

# Direct Link の多様性と冗長性のモデル
{: #models-for-diversity-and-redundancy-in-direct-link}

この資料では、冗長性と多様性の問題に関する一連の図式を示します。これは、お客様のニーズを満たすために最も効果的な {{site.data.keyword.cloud}} Direct Link デプロイメントを作成するためのモデルを見つけるのに役立ちます。 図式は複雑さのレベルの低い順に、またそれぞれが示している Direct Link オファリングに従って配置されています。 Direct Link は、相互接続ルーター (XCR) で本質的に冗長性のあるサービスではありません。Border Gateway Protocol (BGP) スキーマを介した冗長性の構成は、お客様自身で行ってください。 

## セクション 1: 多様性を実現するための比較的単純な構成

このグループで示されている構成は、すべての資産が同じ PoP および同じグローバル市場にあるという事実に依拠しています。

**図 1: 同じ PoP (非 AZ) 内にある、多様性を備えた Direct Link Exchange**

![同じ PoP 内にある、多様性を備えた Exchange](/images/exchange-diversity-same-pop.png)

**図 2: 同じ PoP (非 AZ) 内にある、多様性を備えた Direct Link Connect**

![同じ PoP 内にある、多様性を備えた Connect](/images/connect-diversity-same-pop.png)

**図 3: 同じ PoP (非 AZ) 内にある、多様性を備えた Direct Link Dedicated**

![同じ PoP 内にある、多様性を備えた Dedicated](/images/dedicated-diversity-same-pop.png)

## セクション 2: AZ およびグローバル・ルーティング・オプションが組み込まれた多様性

このグループで示されている構成は、ローカル・アベイラビリティー・ゾーンおよび市場全体で接続するためのオプションを提供します。

### パート A: ローカル・アベイラビリティー・ゾーン (AZ) の多様性

**図 4: ローカル AZ (WDC、DAL、FRA、LON) にある、多様性を備えた Direct Link Exchange**

![ローカル AZ にある、多様性を備えた Exchange](/images/exchange-diversity-local-az.png)

**図 5: ローカル AZ (WDC、DAL、FRA、LON) にある、多様性を備えた Direct Link Connect**

![ローカル AZ にある、多様性を備えた Connect](/images/connect-diversity-local-az.png)

**図 6: ローカル AZ (WDC、DAL、FRA、LON) にある、多様性を備えた Direct Link Dedicated**

![ローカル AZ にある、多様性を備えた Dedicated](/images/dedicated-diversity-local-az.png)

### パート B: グローバル・ルーティングを使用した、異なるローカル市場での多様性

**図 7: グローバル・ルーティングを使用した、多様性を備えた Direct Link Connect**

![グローバル・ルーティングを使用した、多様性を備えた Connect](/images/connect-diversity-global.png)

**図 8: グローバル・ルーティングを使用した、多様性を備えた Direct Link Exchange**

![グローバル・ルーティングを使用した、多様性を備えた Exchange](/images/exchange-diversity-global.png)

**図 9: グローバル・ルーティングを使用した、多様性を備えた Direct Link Dedicated**

![グローバル・ルーティングを使用した、多様性を備えた Dedicated](/images/dedicated-diversity-global.png)

## ECMP の詳細

ECMP は BGP のフィーチャーです。 一部のお客様から、冗長性を実現するための手段として ECMP の使用に関する問い合わせを受けてきました。 ただし、ECMP だけでは十分ではありません。 このセクションでは、その理由について説明します。

**Q: ECMP は、冗長接続のための手段ですか? どのような代替手段が存在しますか?**

ECMP は、冗長接続を実現するためではなく、2 つのリンクで負荷のバランスを取るために設計されています。 IBM Cloud 上の ECMP では、両方の接続の終端を、同じ IBM Cloud 相互接続ルーター (XCR) にする必要があるため、それが Single Point of Failure になります。 (言い換えれば、ECMP は、同じ IBM Cloud XCR 上の 2 つのセッションとしてのみプロビジョンできます)。

**図 10: ECMP のプロビジョニング**

![ECMP Dedicated モデル](/images/ecmp-without-diversity.png)

### 多様性と冗長性を実現する方法

高可用性 (HA) またはフル冗長性を求めている場合は、同じデータ・センター (例えば、DAL03) 内の異なる XCR への 2 つのリンクをセットアップします。 次に、BGP 構成を使用して必要に応じてフェイルオーバーします。

**図 11: デュアル XCR を使用した ECMP**

![ECMP デュアル XCR モデル](/images/ecmp-with-diversity.png)
