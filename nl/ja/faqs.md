---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-05-21"

keywords: faq, faqs, questions, answer, billing, fees, point-to-point, bandwidth, charges, redundancy, Global Routing, diversity, IPv6, BGP, charges, jumbo frames

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}
{:faq: data-hd-content-type='faq'}

# FAQ
{: #faqs}

このセクションには、{{site.data.keyword.cloud}} Direct Link に関するよくある質問とその回答を記載します。 

## IBM Cloud Direct Link はどのように機能しますか
{: #how-does-ibm-cloud-direct-link-work}
{:faq}

Direct Link のすべてのお客様に対して、IBM Cloud チームは、{{site.data.keyword.BluSoftlayer_notm}} 相互接続ルーター (XCR) とお客様のエッジ・ルーター (CER) の間に Point-to-Point ネットワークを構築するために、小規模なプライベート・サブネットを割り当てます。 次に、{{site.data.keyword.BluSoftlayer_notm}} とお客様は、これらの環境間で経路を交換するために、BGP を構成します。 最後に、{{site.data.keyword.BluSoftlayer_notm}} はお客様を VRF に移行し、お客様のリモート・ネットワークの専用アドレス・スペースへの非固有の経路を実装できるようにします。

## IBM Cloud では Direct Link 製品の帯域幅に課金しますか
{: #does-ibm-cloud-meter-bandwidth-for-direct-link-products}
{:faq}

はい。 お客様と IBM Cloud 間の Direct Link サービス全体での帯域幅使用量は無料で課金されませんが、IBM Cloud では、IBM Cloud サービスから公衆インターネットへのアウトバウンド帯域幅に対して課金します。

## Direct Link での課金はいつ開始されますか?
{: #when-does-billing-begin-with-direct-link}
{:faq}

Direct Link Connect に関する料金には、IBM Cloud インフラストラクチャーでのサービス終端のコストが含まれます。 

インフラストラクチャー・サービスは事前に課金され、お客様の注文の受け入れ時に開始します。ただし、IBM Cloud Direct Link の性質のため、Direct Link サービスの課金は、Border Gateway Protocol (BGP) セッションが IBM Cloud と確立されたとき、またはサービス・キーがお客様に提供されてから 30 日後に開始します。 

請求の停止は、(1) お客様が回線の削除を要求し、かつ (2) Connect プロバイダーまたはネットワーク・サービス・プロバイダーが回線をプロビジョン解除した後です。

## Direct Link では、他の関係者からどの程度の追加料金が発生しますか
{: #what-additional-charges-will-i-incur-from-other-parties-with-direct-link}
{:faq}

交換プロバイダーまたはネットワーク・サービス・プロバイダーから追加料金が生じる可能性があります。 プロバイダーの料金情報を参照してください。

## IBM Cloud Direct Link で冗長性を実現するにはどのようにしますか
{: #how-can-i-achieve-redundancy-with-ibm-cloud-direct-link}
{:faq}

Direct Link は、本質的に冗長なサービスを提供しません。 Direct Link は、多様な接続を提供することができ、お客様が BGP を介して冗長性を実現できるようにします。 {{site.data.keyword.BluSoftlayer_notm}} 用の複数の IBM Cloud Direct Link Dedicated プロバイダーまたは Exchange プロバイダーに接続することによって、Direct Link で多様性を実現できます。 あるいは、Exchange および Connect を使用すると、IBM Cloud Direct Link プロバイダーでさまざまな NNI を利用できます。

## Direct Link のデフォルトの「ローカル」ルーティングとグローバル・ルーティング・アドオンの違いは何ですか
{: #what-is-the-difference-between-the-default-local-routing-and-the-global-routing-add-on-for-direct-link}
{:faq}

標準 Direct Link オファリングでは、選択した地域内のデータ・センター間でトラフィックを送信できます。 指定された地域の外部にある他のデータ・センターにアクセスする必要がある場合は、グローバル・ルーティング・アドオンを注文する必要があります。 このモデルは、Direct Link 接続を注文した時点で導入される ACL (アクセス制御リスト) に基づきます。 

## Direct Link のグローバル・ルーティング・アドオン・パッケージが存在する理由は何ですか
{: #why-does-a-global-routing-add-on-package-exist-for-direct-link}
{:faq}

お客様のデータがデータ・センターのローカル・マーケットの外部を通過する場合、お客様に予想外のデータ・コストが発生しないようにするために、グローバル・ルーティング・アドオンを追加しました。これは、大多数のお客様のコストを低く抑え、グローバルに存在するお客様が、地球全体のすべての地域に容易に到達できるようにします。 ただし、通常は、お客様にはローカル帯域幅パッケージだけで十分です。

## ダラスなど、ある地域で Direct Link Dedicated、Direct Link Connect、または Direct Link Exchange に接続されている場合、Direct Link を使用して米国内の他の地域にアクセスすることはできますか
{: #if-i-am-connected-to-a-direct-link-dedicated}
{:faq}

はい、グローバル・ルーティング・アドオンを選択した場合は、ご使用のローカル・マーケットの外部の地域にアクセスできます。このオプションを選択しない場合、Direct Link トラフィックは、選択した PoP または DC の場所のローカル・マーケットに限定されます。詳しくは、[料金の資料](/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link)を参照してください。

## 特定の Direct Link ロケーションから、使用可能などの地域にでも接続できますか
{: #can-i-connect-to-any-available-region-from-a-given-direct-link-location}
{:faq}

はい、グローバル・ルーティング・アドオンを指定して Direct Link を注文している限りは、可能です。

## Direct Link が到達できる地域を制限することはできますか
{: #can-i-restrict-the-regions-that-my-direct-link-can-reach}
{:faq}

いいえ。IBM Cloud では次の 2 つのオプションを提供しています。(1) 1 つのローカル・マーケットのみ、または (2) すべての地域 (グローバル・ルーティング・アドオンを使用)。

## Equinix Cloud Exchange の Direct Link 自動注文プロセスを使用したときに、内部ネットワークにオーバーラップするサブネットが割り当てられた場合はどうすればいいですか
{: #what-if-i-used-the-direct-link-automated-ordering-process}
{:faq}

2018 年 3 月の時点で、推奨されるベスト・プラクティスは、自動注文をキャンセルし、新しいチケットを実行依頼して Direct Link の質問項目に記入することです。 別のサブネットに 10.254.x.x 範囲と 172.32.x.x 範囲のどちらを希望するかを指示する必要があります。

## Direct Link Exchange と Direct Link Connect の違いは何ですか
{: #what-is-the-difference-between-direct-link-exchange-and-direct-link-connect}
{:faq}

これらの 2 つのサービスは似ていて、どちらも比較的低コストで、待ち時間にも寛容であり、IBM Cloud Direct Link の利点をすぐに体験できます。 一言で言えば、Exchange はデータ・センター・プロバイダーを利用し、Connect は 通信キャリアを利用します。 以下に、さらに詳しく説明します。

**Direct Link Exchange** は、データ・センター内での交換の利用を希望するお客様にお勧めです。 Exchange サービスでは、基礎となる回線がすでにプロビジョンされているため、お客様はそのコロケーションへの複数クラウドの接続を迅速に使用可能にできます (これらの他のクラウド・プロバイダーは、設備内の物理的な相互接続が既に存在することが必要です)。

Direct Link Exchange は、IBM Cloud と Cloud Exchange Service Provider 間のレイヤー 2 のネットワーク間 (NNI) 接続によって作成された、単一のクラウド交換ポートを介した複数クラウドの共有使用環境を可能にします。 ポート速度は、5 Gb まで使用可能です。

**Direct Link Connect** は、自社のオンプレミス・デプロイメントと IBM Cloud の間で既存のネットワークを利用することを希望するお客様向けです。 Direct Link Connect サービスを使用すると、お客様は、基礎となるプロビジョニング済みの回線を活用して、新規および既存の電話会社ネットワーク (MPLS など) を利用して、IBM Cloud を迅速に使用可能にすることができます。

Direct Link Connect を使用すると、お客様は、Connect プロバイダーを使用して、IBM パートナーが世界中の施設で運用しているネットワーク間 (NNI) 接続を介して、IBM Cloud に接続できます。 ポート速度は、5 Gb まで使用可能です。

## Direct Link Connect プロバイダーと Direct Link Exchange プロバイダーはどう対比されますか?
{: #how-do-direct-link-connect-and-direct-link-exchange-providers-compare}
{:faq}

Connect プロバイダーは、データ・センターの先のネットワークにまでわたる通信事業者です。 Exchange プロバイダーは、データ・センターに限定されます。 どちらも、マルチクラウドのエクスペリエンスを顧客に実現できます。 Exchange プロバイダーは通常、データ・センター内のコロケーションを必要とします。一方、Connect プロバイダーは、顧客のオンプレミス・サイトとデータ・センターに達することが可能です。

## IBM は IPv6 over Direct Link をサポートできますか
{: #can-ibm-support-ipv6-over-direct-link}
{:faq}

BGP セッションではできません。 IPv4 から IBM の /30 を割り当てる必要があり、同様にお客様からのものも必要です。

## IBM はプライベート・ネットワークで IPV6 を実行できますか
{: #can-ibm-do-ipv6-on-the-private-network}
{:faq}

いいえ、IPv6 はパブリックのみです。

## Verizon SCI の特別な Direct Link の要件はありますか。 プレフィックス / ASN / VLAN BGP などです。
{: #are-there-any-special-direct-link-requirements-for-verizon-sci}
{:faq}

Verizon SCI は、複数の MPLS ベースのレイヤー 3 (IP VPN) サービスの 1 つです。 IBM は、お客様と直接ではなく、Verizon と BGP を確立する必要があります。 その後、Verizon がお客様と BGP を確立し、それに従って経路を通知します。 その他の複数のレイヤー 3 ベースのサービス・プロバイダーが Direct Link Connect プログラムに参加しています。 お客様は、注文内容、および IBM Cloud への接続時のアカウントの動作について認識しておく必要があります。

## Direct Link はいずれかのタイプの QoS をサポートしますか?
{: #does-direct-link-support-any-type-of-qos}
{:faq}

QoS 保証をサポートすることはできません。 QoS には、IBM の各サービス・サプライヤーと IBM Cloud の間の MPLS マッピングが必要です。 一般に、クラウド・サービス・プロバイダーは、この時点で QoS をサポートできません。これは、終端から終端まで到達しなければならず、その間にあるすべてのデバイスを通る必要があるためです。 「トンネリング」やその他の方法で使用できる回避策はありません。

## Direct Link はジャンボ・フレームをサポートしますか?
{: #does-direct-link-support-jumbo-frames}
{:faq}

ジャンボ・フレーム (最大 9214 バイト) は、Dedicated および Dedicated Hosting でサポートされます。 
Connect および Exchange でのサポートは理論的には可能ですが、サービス・プロバイダーが IBM と連携し、基盤のネットワーク間インターフェース (NNI) を含め、エンドツーエンド接続でジャンボ・フレームを確実にサポートするようにする必要があります。
デフォルトでは、Exchange および Connect は 1500 バイトの MTU サポートを使用してセットアップされます。

## Direct Link Connect では、同じキャリア (例: DAL03 での Verizon) を使用してどのようにルーターの多様性を確保しますか?
{: #with-diret-link-connect-how-does-a-customer-ensure-router-diversity-through-the-same-carrier}
{:faq}

キャリアへの多様な NNI リンクを作成するさまざまな XCR があります。 そこから多様性を維持するのは、キャリア次第です。

## Direct Link Connect では、冗長性のために 2 つのリンクを注文する必要がありますか、それとも Direct Link Connect は本質的に冗長性を備えていますか?
{: #for-diret-link-connect-does-a-customer-need-to-order-2-links-for-redundancy}
{:faq}

多様性のためには、2 つのリンクを注文します。 スイッチやルーター間で冗長性は備えていません。 お客様は、各 Direct Link で BGP 構成を使用して冗長性を実現します。

## Direct Link 接続の帯域幅を (例えば、1 GB から 5 GB に) アップグレードするのは、どの程度の難易度ですか
{: #how-easy-is-it-to-upgrade-the-bandwidth-of-my-direct-link-connection}
{:faq}

通常、1 G 以下の速度の場合、1 G 光ファイバーを設置します。 2 G から 10 G の速度の場合、10 G 光ファイバーを設置します。 そのため、1 G から 5 G にアップグレードするには、新しい光ファイバーを割り当てるか挿入する必要があります。 これは、サービスに影響するイベントになります。 このようなタイプの拡張が予期される場合は、Direct Link デプロイメントの開始時に 10 G 光ファイバーを要求することや、最初に 2 G を注文して 10 G 光ファイバーが配備されるようにすることも可能です。

## ECMP は、冗長 Direct Link 接続のための手段ですか。  どのような代替手段が存在しますか?
{: #is-ecmp-the-way-to-go-for-redundant-direct-link-connections}
{:faq}

ECMP は冗長接続のためのものではなく、2 つのリンクで負荷のバランスを取るためのものであることに注意してください。 ECMP では、両方の接続の終端を、同じ IBM Cloud 相互接続ルーター (XCR) にする必要があるため、それが Single Point of Failure になります。 (言い換えれば、ECMP は、同じ IBM Cloud XCR 上の 2 つのセッションとしてのみプロビジョンできます)。 

ECMP は BGP のフィーチャーです。 冗長性を求めている場合は、2 つの Direct Link 接続を用意し、1 つの接続を各 XCR へのものにします。 ECMP を使用し、冗長性を備える場合は、2 つの ECMP セッションが同時に利用できるように、各 XCR に 2 つの Direct Link 接続が必要です。

あるいは、一部のお客様は、同じデータ・センター (WDC02 など) 内の異なる XCR への 2 つのリンクをセットアップし、必要に応じて、BGP 構成を使用してフェイルオーバーしています。 この構成は、2 つの別個のデータ・センター (WDC02 と WDC05 など) への Direct Link 接続を用意するよりも冗長性が低下します (安全性が低下します)。

## アカウントの BCR 接続に至るまで Direct Link XCR 接続に関する SLA はありますか
{: #is-there-an-sla-on-the-diret-link-xr-connections}
{:faq}

現在、Direct Link に関する SLA はありません。 BGP を使用してフェイルオーバーについて適切に構成された Direct Link が 2 つ以上ある場合、お客様は実際上 99.999% を達成することが可能ですが、IBM が制御することはできず、それに関する SLA は提供しません。

## Direct Link の設定に関するヘルプはどこで入手できますか
{: #where-can-i-get-help-setting-up-a-direct-link}
{:faq}

Direct Link への接続については、[{{site.data.keyword.cloud_notm}} Direct Link の構成](/docs/infrastructure/direct-link?topic=direct-link-how-to-order-ibm-cloud-direct-link-dedicated)を参照してください。 さらに支援が必要な場合は、新しいサービス用に開かれたチケットで技術サポートを要求できます。 Equinix を使用した API サービスであっても、チケットを開くと、エンジニアはそれを見ることができます。 または、IBM 営業担当員にお問い合わせください。

## Direct Link Exchange で、IBM は BGP パスワードを設定しますか
{: #on-direct-link-exchange-does-ibm-set-a-bgp-password}
{:faq}

デフォルトでは、Direct Link Exchange の BGP パスワードは設定されていません。 BGP ASN を指定するオプションがあり、BGP IP アドレスが割り当てられます。 また、認証のために BGP パスワードを設定することもできますが、これはエンジニアに知らせるだけです。
