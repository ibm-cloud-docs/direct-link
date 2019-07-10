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

# 発表: グローバル・ルーティング・ポリシーの変更が 7 月 1 日以降有効に

2019 年 7 月 1 日以降、IBM Direct Link グローバル・ルーティング・ポリシーの変更が有効になります
{: important}

カスタマー・エクスペリエンスを向上させて価値を高めるために、IBM Direct Link グローバル・ルーティング・サービスを強化します。主な改善点を以下に示します。

* **ローカル・マーケットの拡張:** ローカル・マーケット内でお客様が接続できるサイトを調整中です。IBM Cloud ネットワーク内の各 PoP サイトを調整し、PoP サイトで IBM Cloud に接続するお客様が、世界中の 1 つ以上の当社のデータ・センターにあるリソースに接続できるようにします。

* **新しい料金設定モデル:** 選択した接続速度に料金設定をより適合させるために、IBM Direct Link グローバル・ルーティング・サービスの料金設定モデルを変更します。

* **無制限の Direct Link トラフィック:** グローバルな IBM Cloud PoP およびデータ・センター間の Direct Link プライベート・ネットワーク・トラフィック用にローカルまたはグローバル・ルーティングを使用するお客様に関して、ネットワーク・トラフィック超過料金がなくなります。

## IBM Cloud Direct Link グローバル・ルーティングの概要
{: #ibm-cloud-direct-link-global-routing-overview}

現在、すべての Direct Link オファリングには、追加料金のないローカル・ルーティングが含まれています。このサービスには、Direct Link 接続が配置されているローカル・マーケットのデータ・センターへのアクセスが含まれます。お客様のアカウント内の IBM Cloud リソースに対する Direct Link プライベート接続で、無制限の着信および発信トラフィックが提供されます。ローカル・ルーティング・オプションを使用する場合、Direct Link トラフィックは、このローカル・マーケットで提供されるサービスに限定されます。

Direct Link の接続先であるローカル・マーケット (PoP またはデータ・センター) の外にネットワーク・トラフィックをルーティングするには、グローバル・ルーティング・オプションを追加する必要があります。これにより、アクセスが拡張されて世界中のすべての IBM Cloud データ・センターが含まれるようになります。

グローバル・ルーティングは、個々の Direct Link サービスに適用されます。グローバル・ルーティングは集約を介して適用されることはありません。特定のマーケット外の接続を必要とするそれぞれの Direct Link サービスでこれを指定する必要があります。

## IBM Direct Link ローカル・マーケットの拡張
{: #announce-expanded-ibm-direct-link-local-markets}

Direct Link ローカル・マーケットを拡張し、世界中のお客様のために追加的なローカル・ルーティング・オプションを提供します。新しいローカル・マーケット割り当ては以下のとおりです。

* 「ダラス」ローカル・マーケットには、デンバー、ヒューストン、シカゴの PoP が含まれるようになります。
* 「ワシントン DC」ローカル・マーケットには、ニューヨーク、アトランタ、マイアミの PoP が含まれるようになります。
* 「サンノゼ」ローカル・マーケットには、ロサンゼルス PoP が含まれるようになります。
* 「オスロ」ローカル・マーケットには、ストックホルム PoP が含まれるようになります。
* 「シドニー」ローカル・マーケットには、パース PoP が含まれるようになります。
* 「香港」ローカル・マーケットには、台北 PoP が運用開始次第含まれるようになります。
* 「東京」ローカル・マーケットには、大阪 PoP が運用開始次第含まれるようになります。
* 「チェンナイ」ローカル・マーケットには、ムンバイ PoP が運用開始次第含まれるようになります。

これらの変更については、以下の表を参照してください: https://cloud.ibm.com/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#expanded-ibm-direct-link-local-markets

## IBM Cloud Direct Link グローバル・ルーティング料金設定モデル
{: #announce-ibm-cloud-direct-link-global-routing-pricing-model}

すべての IBM Cloud Direct Link オファリングでは、ローカル・マーケット内のネットワーク・ルーティングが標準です。2019 年 7 月 1 日以降、グローバル・ルーティング・オプションの料金設定が Direct Link 接続の接続速度に合わせて調整されます。この調整により、Direct Link オファリングで利用可能なすべての接続速度で、より優れた価値をお客様に提供できます。

料金設定については https://cloud.ibm.com/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-global-routing-add-on を参照してください

## IBM Cloud Direct Link グローバル・ルーティング・ネットワーク伝送の超過料金
{: #announce-ibm-cloud-direct-link-global-routing-network-transit-overage-charges}

この発表に伴い、グローバル・ルーティング・オプションをご利用のお客様向けのネットワーク伝送制限と超過料金を廃止します。旧料金設定では、お客様のローカル・マーケットの外部における発信トラフィックに対して、ネットワーク転送割り当て量と超過料金が設定されていました。これらのネットワーク・トラフィック料金が、新料金設定では廃止されています。この発表以降、Direct Link 接続における着信/発信トラフィックで超過料金は発生しなくなります。

## 発効日
{: #announce-effective-date}

これらの変更は 2019 年 7 月 1 日、月曜日に有効になり、この日付以降の新しい注文を対象として、次の請求サイクルで適用されます。

重要: 自動処理がこのように更新されるので、グローバル・ルーティングを必要とするすべての Direct Link 回線をこの日より前に適切に更新してください。Direct Link サービスをアップグレードまたはダウングレードすると、自動処理が行われ、グローバル・ルーティングが存在するかどうか検証されます。グローバル・ルーティングが存在しない場合、Direct Link 回線を介したトラフィックはローカル・マーケットに限定されます。

推奨: Direct Link サービスでお客様の IBM Cloud ルーティングを再確認し、既存の Direct Link サービスにおけるルーティングを修正するためにチケットをオープンすることをぜひお勧めします。
