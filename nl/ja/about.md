---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-29"

keywords: hybrid, solutions, features, benefits, port speed, cross-connect, use cases, latency, routing, options, colocation

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud Direct Link について
{: #about-ibm-cloud-direct-link}

このセクションでは、{{site.data.keyword.cloud}} Direct Link の 4 つのソリューションそれぞれの主要機能と利点についてさらに詳しく確認できます。

  * [**IBM Cloud Direct Link Exchange**](#direct-link-exchange-solution)
  * [**IBM Cloud Direct Link Connect**](#direct-link-connect-solution)
  * [**IBM Cloud Direct Link Dedicated**](#direct-link-dedicated-solution)
  * [**IBM Cloud Direct Link Dedicated Hosting**](#direct-link-dedicated-hosting-solution)

## IBM Cloud Direct Link Exchange ソリューション
{: #direct-link-exchange-solution}

IBM Cloud Direct Link Exchange ソリューションを使用すると、お客様は Cloud Exchange プロバイダーを利用して {{site.data.keyword.cloud_notm}} ロケーションへの接続を実現できます。{{site.data.keyword.cloud_notm}} から Cloud Exchange プロバイダーへの物理的な接続は既に設置済みであり、他のお客様と共有されるため、このオファリングは通常、低コストで接続を提供します。

**一般的なユース・ケース:** _ハイブリッド・ワークロード、プロバイダー間ワークロード、高い発信帯域幅を使用する大量または頻繁なデータ転送、プライベート・ワークロード、および環境管理に最適です。  このオプションは、通常、必要な PoP ロケーションに必要な IBM Cloud Direct Link Exchange プロバイダーが既に存在する場合に選択されます。_

![図 1](/images/Direct-Link-Exchange.png)

 * **終端場所:** {{site.data.keyword.cloud_notm}} PoP (point of presence)。

 * **標準的な導入時間:** Equinix プロバイダーの場合、標準的な導入時間は数時間です。 他のプロバイダーの場合、回線が交換局に到達後 5 日から 10 日です。 導入時間は、場所、および NSP またはキャリアに回線を注文する際の要件に応じて、全体で 30 日から 60 日かかる可能性があります。

 * **相互接続の詳細:** セキュア Cloud Exchange 相互接続用の物理的な相互接続は、{{site.data.keyword.cloud_notm}} と Cloud Exchange プロバイダーの間で維持されます。 お客様が Cloud Exchange プロバイダーに相互接続された後、お客様は Cloud Exchange プロバイダーに「バーチャル・サーキット」を要求します。これにより {{site.data.keyword.cloud_notm}} への論理接続が確立されます。

 * **ポート速度オプション:** 50 Mbps、100 Mbps、200 Mbps、500 Mbps、1 Gbps、2 Gbps、または 5 Gbps を選択します。

 * **概算待ち時間:** 待ち時間は、ローカル・エリア (3 文字の同じ接頭部 (DAL、AMS、MEL など) を持つデータ・センター) 内で、およそ 1.5 ms です。 稼働中 PoP-to-PoP (P2P) ロケーション待ち時間の計測については、http://lg.softlayer.com/ を参照してください。

 * **IBM コロケーション・サービス:** なし。

 * **冗長性:** {{site.data.keyword.cloud_notm}} には、製品の一部として、2 つの個別の相互接続ルーター (XCR) への接続があります。冗長な接続を確立するには、お客様は、優先して使用する各 Direct Link 接続で BGP を構成する必要があります。例として、「_prefer Lowest MED_」、「_prefer highest local-preference_」、「_prefer shorter AS paths_」のようなオプションがあります。

 * **ローカル/グローバル・ルーティング・オプション** ローカル・ルーティング・オプションが、デフォルトのルーティング・オプションです。 Direct Link PoP と同じマーケット (例えば、DAL、AMS、MEL で示されるもの) の中のデータ・センターへのアクセスを提供します。 「グローバル・ルーティング」オプションは、使用している IBM Cloud リソースを、ローカル・マーケットの外部にあるデータ・センター内の他の IBM Cloud リソースに接続するためのアドオンとして必要です。この「グローバル・ルーティング」オプションを使用して、IBM Cloud リソース間 (例えばダラスとアッシュバーン、ダラスとフランクフルトなど) でワークロードを共有できます。
 
## IBM Cloud Direct Link Connect ソリューション
{: #direct-link-connect-solution}

**一般的なユース・ケース** _IBM Cloud Direct Link Connect ソリューションを使用すると、お客様はネットワーク・サービス・プロバイダー (NSP) を使用して {{site.data.keyword.cloud_notm}} ロケーションへの接続を実現できます。{{site.data.keyword.cloud_notm}} からネットワーク・サービス・プロバイダーへの物理的な接続は既に設置済みであり、他のお客様と共有されるため、このオファリングは通常、低コストで接続を提供します。_

![図 2](/images/Direct-Link-Connect.png)

* **終端場所:** {{site.data.keyword.cloud_notm}} PoP (point of presence)。

* **標準的な導入時間:** 回線が交換局に到達した後、5 日から 10 日。導入時間は、場所、および NSP またはキャリアに回線を注文する際の要件に応じて、全体で 30 日から 60 日かかる可能性があります。

* **相互接続の詳細:** Direct Link Connect 相互接続用の物理的な相互接続は、{{site.data.keyword.cloud_notm}} と Connect プロバイダーの間で維持されます。 お客様が Cloud Connect プロバイダーに相互接続された後、お客様は Cloud Connect プロバイダーに「バーチャル・サーキット」を要求します。これにより {{site.data.keyword.cloud_notm}} への論理接続が確立されます。

* **ポート速度オプション:** 50 Mbps、100 Mbps、200 Mbps、500 Mbps、1 Gbps、2 Gbps、または 5 Gbps を選択します。

* **概算待ち時間:** 待ち時間は、ローカル・エリア (3 文字の同じ接頭部 (DAL、AMS、MEL など) を持つデータ・センター) 内で、およそ 1.5 ms です。 稼働中 PoP-to-PoP (P2P) ロケーション待ち時間の計測については、http://lg.softlayer.com/ を参照してください。

* **IBM コロケーション・サービス:** なし。

* **冗長性:** {{site.data.keyword.cloud_notm}} には、製品の一部として、2 つの個別の相互接続ルーター (XCR) への接続があります。冗長な接続を確立するには、お客様は、優先して使用する各 Direct Link 接続で BGP を構成する必要があります。例として、「_prefer Lowest MED_」、「_prefer highest local-preference_」、「_prefer shorter AS paths_」のようなオプションがあります。

* **ローカル/グローバル・ルーティング・オプション** ローカル・ルーティング・オプションが、デフォルトのルーティング・オプションです。 Direct Link PoP と同じマーケット (例えば DAL、AMS、MEL で示されるもの) の中のデータ・センターへのアクセスを提供します。「グローバル・ルーティング」オプションは、使用している IBM Cloud リソースを、ローカル・マーケットの外部にあるデータ・センター内の他の IBM Cloud リソースに接続するためのアドオンとして必要です。この「グローバル・ルーティング」オプションを使用して、IBM Cloud リソース間 (例えば、ダラスとアッシュバーン、ダラスとフランクフルトなど) でワークロードを共有します。

## IBM Cloud Direct Link Dedicated ソリューション
{: #direct-link-dedicated-solution}

IBM Cloud Direct Link Dedicated ソリューションを使用すると、お客様はシングル・テナントのファイバー・ベースの相互接続を、独自の {{site.data.keyword.cloud_notm}} プライベート・ネットワーク接続に終端させることができます。IBM Cloud PoP およびデータ・センターに隣接するコロケーション・ファシリティーを有するお客様、さらにオンプレミスまたは他のデータ・センターへの回線を提供するネットワーク・サービス・プロバイダーが、このオファリングを利用できます。

 **一般的なユース・ケース:** _ハイブリッド・ワークロード、プロバイダー間ワークロード、大量または頻繁なデータ転送、プライベート・ワークロード、および環境管理の処理に最適です。 このオプションは通常、以下の場合に選択されます。(1) 必要な PoP に適切な Exchange プロバイダーやネットワーク・サービス・プロバイダーが存在しない場合、(2) 高スループットを必要とするハイパフォーマンス・ワークロードの場合、または (3) IBM Cloud Direct Link Exchange 実装モデルや Connect 実装モデルでは満たすことができないコンプライアンス要件がある場合。_
 
 **ユース・ケース 1: IBM Cloud への顧客ファシリティー。**

![図 3](/images/Direct-link-Dedicated.png)

**ユース・ケース 2: IBM Cloud へのお客様のコロケーション。**

![図 3B](/images/dedicated-model-colo.png)

 * **終端場所:** {{site.data.keyword.cloud_notm}} PoP (point of presence) またはデータ・センター (DC)。

 * **標準的な導入時間:** 新しい回線が POP に到達した後、10 営業日から 15 営業日。導入時間は、場所、および NSP またはキャリアに回線を注文する際の要件に応じて、全体で 30 日から 60 日かかる可能性があります。

 * **相互接続の詳細:** {{site.data.keyword.cloud_notm}} は、お客様がファイバー・イーサネット (単一モード・ファイバーのみ、1Gig-LX または 10Gig-LR 光学) を注文するために使用する許可書 (LOA) を提供します。ファイバー・イーサネットは、お客様のケージまたはプロバイダー・ケージから {{site.data.keyword.cloud_notm}} CFA 終端点に配線され、相互接続ルーター (XCR) インフラストラクチャーに結合されます。メディアは、波長が 1310 nm の光ファイバーでなければなりません。

 * **ポート速度オプション:** 1 Gbps、2 Gbps、5 Gbps、または 10 Gbps を選択します。

 * **概算待ち時間:** 待ち時間は、ローカル・エリア (3 文字の同じ接頭部 (DAL、AMS、MEL など) を持つデータ・センター) 内で、およそ 1.5 ms です。  稼働中 PoP-to-PoP (P2P) ロケーション待ち時間の計測については、http://lg.softlayer.com/ を参照してください。

 * **IBM コロケーション・サービス:** なし。

 * **冗長性:** {{site.data.keyword.cloud_notm}} には、製品の一部として、2 つの個別の相互接続ルーター (XCR) への接続があります。冗長な接続を確立するには、お客様は、優先して使用する各 Direct Link 接続で BGP を構成する必要があります。例として、「_prefer Lowest MED_」、「_prefer highest local-preference_」、「_prefer shorter AS paths_」のようなオプションがあります。

 * **ローカル/グローバル・ルーティング・オプション** ローカル・ルーティング・オプションが、デフォルトのルーティング・オプションです。 Direct Link PoP と同じマーケット (例えば DAL、AMS、MEL で示されるもの) の中のデータ・センターへのアクセスを提供します。「グローバル・ルーティング」オプションは、使用している IBM Cloud リソースを、ローカル・マーケットの外部にあるデータ・センター内の他の IBM Cloud リソースに接続するためのアドオンとして必要です。この「グローバル・ルーティング」オプションを使用して、IBM Cloud リソース間 (例えばダラスとアッシュバーン、ダラスとフランクフルトなど) でワークロードを共有できます。

## IBM Cloud Direct Link Dedicated Hosting ソリューション
{: #direct-link-dedicated-hosting-solution}

IBM Cloud Direct Link Dedicated Hosting ソリューションは、IBM Cloud Direct Link Dedicated と同様の接続を提供しますが、接続ポイントが {{site.data.keyword.cloud_notm}} データ・センターに隣接しているため、ハイパフォーマンスのユース・ケースの場合の待ち時間が改善されます。IBM Cloud では、シンプルな料金体系で、このソリューションを使用したカスタマイズ可能な各種のコロケーション・サービスを提供しています。

**一般的なユース・ケース:** _非標準計算テクノロジーの処理、専用ストレージ要件、または既存の IT 投資の活用に最適です。_

![図 4](/images/Direct-Link-Dedicated-Hosting.png)

* **終端場所:** {{site.data.keyword.cloud_notm}} データ・センター (DC)。

 * **標準的なデプロイメント時間::** すべての要件が確定され、契約が実行された後 30 日から 60 日。

 * **相互接続の詳細:** {{site.data.keyword.cloud_notm}} は、デプロイメントの一環として、{{site.data.keyword.cloud_notm}} 相互接続ルーター (XCR) インフラストラクチャーからお客様のコロケーション環境への 1 G または 10 G のファイバー接続を提供します。  コロケーション・サービスが要求されていない場合 (既存の環境が既に接続されている場合)、{{site.data.keyword.cloud_notm}} はお客様がファイバー・イーサネット (単一モード・ファイバーのみ、1Gig-LX または 10Gig-LR 光学) を注文するために使用する許可書 (LOA) を提供します。ファイバー・イーサネットは、お客様のケージから {{site.data.keyword.cloud_notm}} CFA 終端点に配線され、相互接続ルーター (XCR) インフラストラクチャーに結合されます。 メディアは、波長が 1310 nm の光ファイバーでなければなりません。

 * **ポート速度オプション:** 1 Gbps、2 Gbps、5 Gbps、または 10 Gbps を選択します。

 * **概算待ち時間:** 待ち時間は、ローカル・データ・センター内でおよそ 0.5 ms です。

 * **IBM コロケーション・サービス:** あり。

 * **冗長性:** {{site.data.keyword.cloud_notm}} には、製品の一部として、2 つの個別の相互接続ルーター (XCR) への接続があります。冗長な接続を確立するには、お客様は、優先して使用する各 Direct Link 接続で BGP を構成する必要があります。例として、「_prefer Lowest MED_」、「_prefer highest local-preference_」、「_prefer shorter AS paths_」のようなオプションがあります。

 * **ローカル/グローバル・ルーティング・オプション** ローカル・ルーティング・オプションが、デフォルトのルーティング・オプションです。 Direct Link PoP と同じマーケット (例えば、DAL、AMS、MEL で示されるもの) の中のデータ・センターへのアクセスを提供します。 「グローバル・ルーティング」オプションは、使用している IBM Cloud リソースを、ローカル・マーケットの外部にあるデータ・センター内の他の IBM Cloud リソースに接続するためのアドオンとして必要です。この「グローバル・ルーティング」オプションを使用して、IBM Cloud リソース間 (例えば、ダラスとアッシュバーン、ダラスとフランクフルトなど) でワークロードを共有します。
