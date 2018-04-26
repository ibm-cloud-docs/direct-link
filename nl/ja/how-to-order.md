---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-11"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud Direct Link の注文

お客様のニーズに最適な IBM Cloud Direct Link のタイプを注文する準備が整ったら、以下リンクをたどって (または単にこの資料をスクロールして)、プロセスの全般的な概要を知ることができます。注文を行う準備ができたら、この資料の一連の「ステップバイステップ」の記述の個所で、注文プロセスについてのステップバイステップの説明を確認することができます。

* [IBM Cloud Direct Link Exchange の注文方法](how-to-order.html#how-to-order-ibm-cloud-direct-link-exchange)
* [IBM Cloud Direct Link Connect の注文方法](how-to-order.html#how-to-order-ibm-cloud-direct-link-connect)
* [IBM Cloud Direct Link Dedicated の注文方法](how-to-order.html#how-to-order-ibm-cloud-direct-link-dedicated)
* [IBM Cloud Direct Link Dedicated Hosting の注文方法](how-to-order.html#how-to-order-ibm-cloud-direct-link-dedicated-hosting)

## IBM Cloud Direct Link Exchange の注文方法

 * 適切な PoP に到達し、関連付けられた Cloud Exchange プロバイダーに相互接続するための、ネットワーク・プロバイダーの機能を確認します。
 * [カスタマー・ポータル ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/) を使用して IBM Cloud Direct Link Exchange 申し込みを開き、要求された情報を記入します。(IBM セールス・エンジニアからの支援を要求できます。) Equinix プロバイダーを使用する場合、注文とプロビジョニングのプロセスは、[完全に自動化](cloud-exchange-automation.html)されています。
 * Exchange プロバイダーに連絡し、交換局への接続を交渉します。
 * ネットワーク・プロバイダーと Exchange プロバイダーの間の接続を注文します。
 * Exchange プロバイダーを介して「バーチャル・サーキット」を注文し、{{site.data.keyword.BluSoftlayer_notm}} IBM Cloud Direct Link 要求のチケット ID を「申し込み ID」または「許可 ID」として参照します。
 * {{site.data.keyword.BluSoftlayer_notm}} ネットワーキング・インフラストラクチャー上の IP の割り当ては、バーチャル・サーキット要求の完了後 3 営業日以内に完了します。

## IBM Cloud Direct Link Connect の注文方法

 * 適切な PoP に到達し、関連付けられた Connect プロバイダーに相互接続するための、ネットワーク・プロバイダーの機能を確認します。
 * [カスタマー・ポータル ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/) を使用して IBM Cloud Direct Link Connect 要求を開き、要求された情報を記入します。(IBM セールス・エンジニアからの支援を要求できます。) 
 * Connect プロバイダーに連絡し、交換局への接続を交渉します。
 * ネットワーク・プロバイダーと Connect プロバイダーの間の接続を注文します。
 * Connect プロバイダーを介して「バーチャル・サーキット」を注文し、{{site.data.keyword.BluSoftlayer_notm}} IBM Cloud Direct Link 要求のチケット ID を「申し込み ID」または「許可 ID」として参照します。
 * {{site.data.keyword.BluSoftlayer_notm}} ネットワーキング・インフラストラクチャー上の IP の割り当ては、バーチャル・サーキット要求の完了後 3 営業日以内に完了します。

## IBM Cloud Direct Link Dedicated の注文方法

 * 適切な PoP に到達して {{site.data.keyword.BluSoftlayer_notm}} 環境に相互接続するための、ネットワーク・プロバイダーの機能を確認します。
 * IBM Cloud Direct Link Dedicated 要求を開き、要求された情報を記入します。(IBM セールス・エンジニアからの支援を要求できます。)
 * {{site.data.keyword.BluSoftlayer_notm}} は、接続用の許可書 (LOA) を提供します。
 * 回線が PoP に到達しており、キャリアによって完了済みであることを確認します。
 * LOA 内の {{site.data.keyword.BluSoftlayer_notm}} CFA (Customer Facility Assignment) 情報を使用して相互接続を注文します。これは、完了までに通常 2 営業日から 10 営業日かかります。 (この時間フレームは、施設のベンダーとお客様が設定した注文優先順位のタイプによって異なります。) このプロセスには、{{site.data.keyword.BluSoftlayer_notm}} 終端ポートへのパッチのセットアップが含まれます。
 * {{site.data.keyword.BluSoftlayer_notm}} ポータル・チケットで、施設のプロバイダーからの相互接続完了通知を {{site.data.keyword.BluSoftlayer_notm}} に提供します。
 * {{site.data.keyword.BluSoftlayer_notm}} は、完了通知の有効性を確認し、LOA/CFA から、相互接続ルーター (XCR) および他のギアへのパッチの作成を注文します。
 * {{site.data.keyword.BluSoftlayer_notm}} ネットワーキング・インフラストラクチャー上の IP 割り当ては、相互接続の完了後 3 営業日以内に完了します。

## IBM Cloud Direct Link Dedicated Hosting の注文方法

 * コロケーションおよび接続の要件を特定し、IBM 営業チームと協力して、契約および技術的補足を最終決定して実行します。
 * {{site.data.keyword.BluSoftlayer_notm}} は、要求された環境およびサービスについて、コロケーション・プロバイダーと共に構築注文を実行します。 設置は通常、構築注文の発注から 30 日以内に完了します。
 * コロケーション・ケージの構築が完了したら、コロケーション・ケージと {{site.data.keyword.BluSoftlayer_notm}} POD 環境の XCR ギア間を相互接続するプロセスは、すでに記述している IBM Cloud Direct Link Dedicated のプロセス (ステップ 3 から) に従います。
