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

## 既知の制限
最初に、このセクションで IBM Cloud Direct Link の 4 つのオファリングのすべてに適用される制限を説明し、その後で、各オファリングについて個別にいくつかの制限の詳細を示します。

### 一般的な IBM Cloud Direct Link の制限
 * 各 IBM Cloud Direct Link 接続に固有の注文が必要です。複数の接続が必要な場合は、接続ごとに IBM Cloud Direct Link を注文してください。
 * {{site.data.keyword.BluSoftlayer_notm}} サービス・ネットワークには、リモート・ネットワークから直接アクセスすることはできません。
 * {{site.data.keyword.BluSoftlayer_notm}} は、お客様が {{site.data.keyword.BluSoftlayer_notm}} バックボーンを経由してリモート・サイト間でトラフィックにバックホールを利用することを許可しません。 IBM Cloud Direct Link 製品の目的は、リモート・ネットワークがお客様の {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャーとプライベートに通信できるようにすることです。
 * IBM Cloud Direct Link では、VRF (Virtual Routing and Forwarding) インスタンスを使用する必要があります。
 * VRF は、{{site.data.keyword.BluSoftlayer_notm}} SSL、PPTP、および IPSec VPN の各サービスと完全に互換性があるわけではありません。
 * VRF は、{{site.data.keyword.BluSoftlayer_notm}} アカウント間 VLAN スパンニングとは互換性がありません。
 * IBM Cloud Direct Link では、お客様のリモート・ネットワークへの経路を確立するために、BGP が必要です。
 * IBM Cloud Direct Link インフラストラクチャーに対する変更は、米国中部タイム・ゾーンの午前 8 時から午後 5 時の間に行う必要があります。
 
### IBM Cloud Direct Link Exchange および IBM Cloud Direct Link Connect の制限
 * お客様は、リモート・ネットワークから POP への到達に関連した料金、および Cloud Exchange プロバイダーとの間で発生するすべての料金を負担します。
 * {{site.data.keyword.BluSoftlayer_notm}} は、ネットワーク POP 内にあるお客様の機器はコロケーションしません。 お客様は、プロバイダーと協力して、{{site.data.keyword.BluSoftlayer_notm}} ネットワーク PoP が存在する施設内に機器をコロケーションする必要があるかどうかを判断する必要があります。
 * Direct Link Cloud Exchange の可用性は、ロケーション間で異なります。 お客様は、IBM クラウド・アカウント・マネージャーに連絡して、現在または将来の可用性を確認できます。
 
### IBM Cloud Direct Link Dedicated の制限
 * {{site.data.keyword.BluSoftlayer_notm}} の IBM Cloud Direct Link Dedicated に関する料金には、{{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャーでのポート終端のコストが含まれます。お客様は、リモート・ネットワークから PoP への到達に関連した料金、および PoP 施設内で必要な相互接続に関連したすべての料金を負担します。  {{site.data.keyword.BluSoftlayer_notm}} は、お客様に代わって相互接続を注文することはありません。
 * {{site.data.keyword.BluSoftlayer_notm}} は、ネットワーク PoP 内にあるお客様の機器はコロケーションしません。 お客様は、プロバイダーと協力して、{{site.data.keyword.BluSoftlayer_notm}} ネットワーク PoP が存在する施設内に機器をコロケーションする必要があるかどうかを判断する必要があります。

### IBM Cloud Direct Link Dedicated Hosting の制限
 * IBM Cloud Direct Link Dedicated Hosting では、{{site.data.keyword.BluSoftlayer_notm}} とお客様の間の特定の契約が必要です。この契約には、製品のご使用条件、コロケーション環境の価格、およびサービスの期間のコミットメントの概要を記載します。 6 カ月、9 カ月、または 12 カ月の契約が必要です。
 * プロバイダーの接続は、選択されたデータ・センターの On-Net プロバイダーに制限されます。
