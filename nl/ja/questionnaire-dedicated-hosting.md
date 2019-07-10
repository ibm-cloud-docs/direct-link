---

copyright:
  years: 2018, 2019
lastupdated: "2019-03-29"


keywords: Dedicated, Hosting, finalize, questionnaire, Network Engineering, billing, fees, VRF, BGP, ticket, cross-connects, datacenters, data, center, backhaul, single mode, single-mode, fiber, Letter of Authorization, LOA, contract

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud Direct Link Dedicated Hosting のアンケート
{: #ibm-cloud-direct-link-dedicated-hosting-questionnaire}

{{site.data.keyword.cloud}} Direct Link Dedicated Hosting をご注文いただき、ありがとうございます。 ご注文の最後に、追加情報を収集させてください。 アンケート・プロセス中、いつでもエンジニアとお話いただけます。 アンケートは、完了後、IBM のクラウド設計エンジニアリング・チームによって確認され、実装のためにネットワーク・エンジニアリングにエスカレートされます。

## 確認
{: #dedicated-hosting-acknowledgements}

1. このアンケートで概要を示している料金には、IBM Cloud ネットワーク・インフラストラクチャーへのサービス終端のコストが含まれます。 キャビネットや相互接続などのコロケーション・コストには、コロケーション契約の一部として別途概要が示されている月額料金および非反復的料金が含まれます。

2. IBM Cloud Direct Link Dedicated Hosting は、IBM Cloud プライベート・ネットワークへの 1 Gbps または 10 Gbps ファイバー相互接続を提供します。 シングル・モード・ファイバー (SMF) アップリンクをサポートできるルーターまたはレイヤー 3 スイッチを用意する必要があります。 デプロイメント時間は、ご使用の回線プロバイダーによって異なりますが、このサービスの標準的なデプロイメント時間は 30 日から 60 日です。

3. Direct Link Dedicated Hosting では、VRF (Virtual Routing and Forwarding) インスタンスを使用する必要があります。 これにより、お客様はリモート・ネットワークで使用するための独自のリモート IP アドレスを定義できます。ただし、10.x.x.x ネットワークを使用した場合でも、IBM Cloud 内のホストおよび IBM Cloud サービス・ネットワーク (10.0.0.0/14、10.198.0.0/15、および 10.200.0.0/14) とオーバーラップすることはできないことに留意してください。 VRF へのアカウントの移行には、各 VLAN が新規構成にマイグレーションされる間、プライベート・ネットワークを短時間停止する必要があります。 ネットワーク・エンジニアリング・チームがお客様と連携して、このアクティビティーの期間を定義いたします。

4. VRF は、IBM Cloud SSL、PPTP、および IPsec VPN の動作を変更します。 通常、アクセス対象のコンピュート・リソースと同じデータ・センター・ロケーションへの VPN 接続が確立されると、これらは機能しますが、グローバルなアクセスは許可されません。  代替手段として、サーバーの管理のために Direct Link 自体を使用したり、さまざまなタイプの VPN を使用して構成可能な独自の VPN ソリューション (Vyatta など) を実行したりすることができます。 

5. Direct Link Dedicated Hosting では、お客様のリモート・ネットワークへの経路を実装するために BGP を必要とします。 IBM Cloud は、IBM Cloud に行われた通知に対してフィルターを実装することはありません。 IBM Cloud は、アカウントに割り当てられているすべてのプライベート・サブネットを通知します。 お客様が、IBM Cloud で受信された通知を適切に管理する必要があります。

6. IBM Cloud はデュアル・アップリンク (IBM Cloud の各相互接続ルーターに 1 つのアップリンク) を提供し、お客様が冗長接続を確立できるようにします。 これは、ECMP 機能を利用するか、単に接続に重み付けすることで、BGP セッションを介してお客様のルーターで実現されます。

7. IBM Cloud サービス・ネットワークは、Dedicated Hosting およびリモート・ネットワークから直接アクセス可能ではありません。

8. IBM Cloud は、お客様が IBM Cloud バックボーンを介してリモート・サイト間でトラフィックをバックホールすることを許可しません。 Direct Link サービスは、ご使用のリモート・ネットワークが IBM Cloud インフラストラクチャーと非公開通信できるようにするために設計されています。

9. IBM Cloud は、ローカル・ルーティングまたはグローバル・ルーティングを使用した Direct Link を提供します。 必要なルーティング・パッケージを確認し、ibm.biz/DirectLink-Docs にリストされている各パッケージに関連付けられた帯域幅プランに同意してください。

10. Direct Link を介してプッシュする予定のトラフィック量、および当該トラフィックのプッシュ先にする予定の IBM Cloud データ・センターを指定してください。

11. IBM Cloud でコロケーション・サービスを購入しない場合は、お客様側で、ご使用の環境と IBM Cloud 間の相互接続を注文してお支払いください。 接続後、接続の承認と接続先ロケーションについて詳述した許可書 (LOA) を提供します。

12. Direct Link の以下の料金に同意することを確認してください。
 * 1 Gbps: _ロケーション・ベースの料金_ 
 * 2 Gbps: _ロケーション・ベースの料金_
 * 5 Gbps: _ロケーション・ベースの料金_
 * 10 Gbps: _ロケーション・ベースの料金_
 * オプションのグローバル・ルーティング
