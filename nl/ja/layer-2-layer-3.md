---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-30"

keywords: layer 2, layer 3, interconnect, partner, multi-cloud, other clouds, BGP, XCR

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Direct Link のレイヤー 2 とレイヤー 3 の接続の比較
{: #comparing-layer-2-layer-3}

{{site.data.keyword.cloud}} Direct Link は、ネットワーク・サービス・プロバイダー (NSP) からの OSI レイヤー 2 およびレイヤー 3 パートナー相互接続を受け入れます。ネットワーク・サービス・プロバイダーの中には、さまざまなネットワークでこの両方のレイヤーに関するサービスを提供しているプロバイダーもあれば、すべてのネットワークを {{site.data.keyword.cloud_notm}} に相互接続**しない**ことを選択しているプロバイダーもあります。 

{{site.data.keyword.cloud_notm}} Direct Link デプロイメントを計画する際には、レイヤー 2 とレイヤー 3 の接続に関連する特性を考慮し、ニーズを満たす最適なデプロイメントを作成できるようにしてください。

## レイヤー 2 接続に関する考慮事項
{: #layer-2-networks}

レイヤー 2 パートナー相互接続を使って作成する VLAN ベースのバーチャル・サーキットごとに、オンプレミスのルーターと IBM Cloud XCR の間の BGP セッションを構成して確立する必要があります。IBM Cloud では、ルーターとの BGP セッションを確立するための `/31` IPv4 割り当てが行われます。

* レイヤー 2 ネットワークには、企業と {{site.data.keyword.cloud_notm}} の間のシンプルな 1 対 1 接続用オプションが備わっています。 
* レイヤー 2 サービスは、IP アドレスではなく VLAN に依存しています。 
* レイヤー 2 サービスはレイヤー 3 サービスと比較して低コストで、待ち時間が短く、オーバーヘッドが少なくなる可能性があります。 
* レイヤー 2 ネットワークでは、企業が実行可能なレイヤー 3 機能に関する制限はありません。

## レイヤー 3 接続に関する考慮事項
{: #layer-3-networks}

レイヤー 3 接続では、それぞれのバーチャル・サーキット用に、サービス・プロバイダーが IBM Cloud XCR とプロバイダーのエッジ・ルーターの間で BGP セッションを確立します。サービス・プロバイダーが IBM Cloud に対する BGP 構成を管理するので、お客様がオンプレミス・ルーター用に IBM Cloud で BGP を構成する必要はありません。

* レイヤー 3 IP VPN ネットワークまたは AVPN ネットワークでは「any-to-any」接続が可能です。 
* レイヤー 3 ネットワークの場合、ネットワーク・サービス・プロバイダーが企業と {{site.data.keyword.cloud_notm}} の間の BGP セッションを保守する必要があります。 
* ネットワーク・サービス・プロバイダーによっては、レイヤー 3 接続の使用時に自社のネットワークにおける特定の機能 (ASN プリペンド、GRE トンネリングなど) を制限している場合があります。可能性がある制限について、プロバイダーに必ず確認してください。

## パートナー相互接続の表
{: #partner-interconnection-table}

以下の表に、それぞれの {{site.data.keyword.cloud_notm}} パートナーが提供する接続のタイプをまとめます。 

| パートナー | 相互接続タイプ |  
|-------|-------|
| AT&T NetBond® for Cloud | レイヤー 3 |
| AT&T Cloud Gateway (旧 RedFringe)| レイヤー 3 |
| Bell Canada | レイヤー 3 | 
| British Telecom | レイヤー 3  | 
| CenturyLink IP VPN | レイヤー 3 | 
| CenturyLink Dynamic Connections | レイヤー 2 | 
| Chief Telecomm | レイヤー 2 |
| Colt | レイヤー 2  | 
| PCCW による Console Connect | レイヤー 2 |
| Digital Realty Service Exchange | レイヤー 2 | 
| Epsilon | レイヤー 2 | 
| IBM BlueFringe | レイヤー 3 | 
| Intercloud | レイヤー 3 |
| Megaport | レイヤー 2 |
| MWS GNPP | レイヤー 3 |
| Neutrona | レイヤー 2 |
| NTT | レイヤー 3 |
| PacketFabric | レイヤー 2  |
| ソフトバンク | レイヤー 3 |
| SES Networks | レイヤー 2  |
| Tata IZO™ Private Connect  | レイヤー 3 | 
| Telia | レイヤー 3 |
| Telstra | レイヤー 3 |
| Tokai | レイヤー 2 | 
| Verizon SCI| レイヤー 3 |
| Zayo Cloud Link | レイヤー 2 |
