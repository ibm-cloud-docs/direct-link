---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: order, provider, capabilities, Exchange, cross-connect, locations, PoP, datacenter, data, center, pricing

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud Direct Link Exchange の注文方法
{: # how-to-order-ibm-cloud-direct-link-exchange}

1. 適切な PoP に到達し、関連付けられた Exchange プロバイダーに相互接続するための、ネットワーク・プロバイダーの機能を確認します。
2. [カスタマー・ポータル ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/) を使用して {{site.data.keyword.cloud}} Direct Link Exchange 申し込みを開き、要求された情報を記入します。 (IBM セールス・エンジニアからの支援を要求できます。) Equinix プロバイダーを使用する場合は、[自動注文](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix)を使用できます。
3. Exchange プロバイダーに連絡し、交換局への接続を交渉します。
4. ネットワーク・プロバイダーと Exchange プロバイダーの間の接続を注文します。
5. Exchange プロバイダーを介して「バーチャル・サーキット」を注文し、{{site.data.keyword.BluSoftlayer_notm}} Direct Link 要求のチケット ID を「申し込み ID」または「許可 ID」として参照します。
6. {{site.data.keyword.BluSoftlayer_notm}} ネットワーキング・インフラストラクチャー上の IP の割り当ては、バーチャル・サーキット要求の完了後 3 営業日以内に完了します。
 
## 場所
{: #exchange-locations}
 
 この表では、どの IBM Cloud データ・センターが Direct Link Exchange 接続を提供しているのかを示します。
 
| Exchange プロバイダー	| IBM データ・センター・コード |
|-------------|-----------------------|
| AT Tokyo | 東京 2 |
| Ascenty | サンパウロ 1* |
| Cologix | モントリオール 2、トロント 2 |
| Cyrus One | ダラス 13 |
| DE-CIX | フランクフルト 3 |
| Equinix | ホンコン 1、シンガポール 2、シドニー 2、東京 1、アムステルダム 2、パリ 2、シカゴ 1、ダラス 3、ニューヨーク市 2、ニューヨーク市 3、サンパウロ 2、サンノゼ 2、トロント 2、ワシントン DC 2、ロンドン 1、フランクフルト 3 |							
| InterXion | フランクフルト 1、ストックホルム 1 |
| KINX	| ソウル 2 |
| NextDC | メルボルン 2、シドニー 3 |
| SK C&C | ソウル 1 |

* 近日公開

## 料金
{: #exchange-pricing}

料金情報については、[料金の資料](/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-direct-link-exchange)を参照してください。
