---

copyright:
  years: 2017, 2018
lastupdated: "2018-06-25"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud Direct Link Exchange の注文方法

1. 適切な PoP に到達し、関連付けられた Exchange プロバイダーに相互接続するための、ネットワーク・プロバイダーの機能を確認します。
2. [カスタマー・ポータル ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/) を使用して IBM Cloud Direct Link Exchange 申し込みを開き、要求された情報を記入します。 (IBM セールス・エンジニアからの支援を要求できます。) Equinix プロバイダーを使用する場合は、[自動注文](cloud-exchange-automation.html)を使用できます。
3. Exchange プロバイダーに連絡し、交換局への接続を交渉します。
4. ネットワーク・プロバイダーと Exchange プロバイダーの間の接続を注文します。
5. Exchange プロバイダーを介して「バーチャル・サーキット」を注文し、{{site.data.keyword.BluSoftlayer_notm}} Direct Link 要求のチケット ID を「申し込み ID」または「許可 ID」として参照します。
6. {{site.data.keyword.BluSoftlayer_notm}} ネットワーキング・インフラストラクチャー上の IP の割り当ては、バーチャル・サーキット要求の完了後 3 営業日以内に完了します。
 
## 場所
 
 この表では、どの IBM Cloud データ・センターが Direct Link Exchange 接続を提供しているのかを示します。
 
| Exchange プロバイダー	| IBM データ・センター・コード |
|-------------|-----------------------|
| AT Tokyo	| TOK02 |
| Cologix	| MON02、TOR02 |
| Equinix	| SNG02、SYD02、TOK01、AMS02、PAR02、CHI01、DAL03、NYC02、NYC03、SAO02、SJC02、TOR02、WDC02、LON01、FRA03 |									
| InterXion	| FRA01、STO01 |
| KINX	| SEO02* |
| NextDC | 	MEL02* |
| SK C&C | 	SEO01 |

* 近日公開

## 料金

料金情報については、[料金の資料](pricing.html)を参照してください。
