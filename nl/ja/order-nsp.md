---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-25"

keywords: order, provider, capabilities, Dedicated, cross-connect, locations, PoP, datacenter, data, center, pricing, Letter of Authorization, LOA, 

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:note: .note}
{:download: .download}

# IBM Cloud Direct Link Dedicated の注文方法
{: #how-to-order-ibm-cloud-direct-link-dedicated}

1. 適切な PoP に到達して {{site.data.keyword.BluSoftlayer_notm}} 環境に相互接続するための、ネットワーク・プロバイダーの機能を確認します。
2. {{site.data.keyword.cloud}} Direct Link Dedicated 要求を開き、要求された情報を記入します。 (IBM セールス・エンジニアからの支援を要求できます。)
3. {{site.data.keyword.BluSoftlayer_notm}} は、接続用の許可書 (LOA) を提供します。
4. 回線が PoP に到達しており、キャリアによって完了済みであることを確認します。
5. LOA 内の {{site.data.keyword.BluSoftlayer_notm}} CFA (Customer Facility Assignment) 情報を使用して相互接続を注文します。これは、完了までに通常 2 営業日から 10 営業日かかります。 (この時間フレームは、施設のベンダーとお客様が設定した注文優先順位のタイプによって異なります。) このプロセスには、{{site.data.keyword.BluSoftlayer_notm}} 終端ポートへのパッチのセットアップが含まれます。
6. {{site.data.keyword.BluSoftlayer_notm}} ポータル・チケットで、施設のプロバイダーからの相互接続完了通知を {{site.data.keyword.BluSoftlayer_notm}} に提供します。
7. {{site.data.keyword.BluSoftlayer_notm}} は、完了通知の有効性を確認し、LOA/CFA から、相互接続ルーター (XCR) および他のギアへのパッチの作成を注文します。
8. {{site.data.keyword.BluSoftlayer_notm}} ネットワーキング・インフラストラクチャー上の IP 割り当ては、相互接続の完了後 3 営業日以内に完了します。

## 場所
{: #dedicated-locations}

この表では、Direct Link Dedicated が使用可能な IBM Cloud データ・センターに関する詳細を示します。

|**IBM ロケーション・コード** | **Meet Me Room オペレーター**| **オペレーター・サイト・コード** | **オペレーターの住所** |
|-----------------|-----------------|--------------------|--------------------|
| **APAC** | | | |
| チェンナイ 1 | Tata | PH-01 | 226, Red Hills Road,Kallikuppam, Ambattur |
| 香港 1 | Mega-I (PACNET 経由) | Mega-I (iAdvantage Hong Kong) |29F, 399 Chai Wan Road |
| メルボルン 1 | Digital Realty | MEL11 | 72 Radnor Drive, Deer Park |
| メルボルン 2 | NextDC | M2 | 820 Lorimer Street, Port Melbourne |
| 大阪 1 | Equinix | OS1 |  |
| パース 1 | Metronode | F1Z | 60 Randell St, Shenton Park, Western Australia |
| ソウル 1 | C&C | Seoul01 | 46, Pangyo-ro 255beon-gil, Bundang-gu, Seongnam-si, Gyeonggi-do |
| ソウル 2 | KINX | KINX Bundang IDC | 3F Hostway IDC ,343-1 Yatap-dong , Gyeonggi-do |
| シンガポール 1 | Digital Realty | SIN10 | 29A International Business Park, S180 |
| シンガポール 2 | Equinix | SG1 | 20 Ayer Rajan Crescent Industrial Park |
| シドニー 1 | Global Switch | SYD01 | 400 Harris Street aka 273 Pyrmont St Ultimo  |
| シドニー 2 | Equinix | SY3 | 47 Bourke Rd |
| シドニー 3 | NextDC | S1 | 4 Eden Park Drive, Macquarie Park |
| シドニー 4 | Digital Realty | SYD10 | 1-11 Templar Rd, Erskine Park |
| シドニー 5 | Equinix | SY4 | 200 Bourke Rd |
| 東京 1 | Equinix | TY2 | |
| 東京 2 | At Tokyo | CC2 |  |
| 東京 3 | Equinix | TY4 | |
| 東京 4 | ソフトバンク | | |
| 東京 5 | NTT | | |
| **EMEA** |  |  |
| アムステルダム 2 | Equinix | AM1 / AM2 | Larrderhoogtweg 57 |
| Amsterdam 3 | KPN | Amsterdam 3 | Rondebeltweg 62 |
| Frankfurt 1 | InterXion | FRA01 | Hanauer Landstrasse 302 |
| フランクフルト 2 | Zenium | FRA1 | Leonhard - Heisswolf Str 4., Frankfurt am Main |
| フランクフルト 3 | Equinix| FRA6 | Larchenstrasse 110, Frankfurt Griesheim |
| フランクフルト 4 | E-Shelter | Frankfurt 1 | Eschborner Landstrasse 100, Building H | 
| フランクフルト 5 | InterXion | FRA05 | Weismüllerstraße 40 |
| ロンドン 1 | Equinix (fTelecity) | LD8 | 6/7 Harbour Exchange  E14 9GE |
| ロンドン 2 | Digital Realty | LHR13 | Fountain Court, Cox Lane |
| ロンドン 3 | Equinix | LD5 | 8 Buckingham Ave |
| ロンドン 4 | ARK | A103 | A57 Cody Technology Park Old, Victor Way, Farnborough |
| ロンドン 6 | Zenium | LON1 | 12 Liverpool Rd, Trading Estate |
| ミラノ 1 | Data IV | | Via Monzoro 101-105 , 20010 Cornaredo (MI) |
| ミラノ 2 | Infracom Italia | Infracom 21 Via Caldera Way | Infracom Italia Spa, Building D, Caldera Business Park, Via Caldera, 21|
| オスロ 1 | EVRY | DigiPlex - Fetsund | 9,, Heiaveien, 1900 Fetsund |
| オスロ 2 | Verizon | Verizon Oslo | Hans Møller Gassmanssvei 9 |
| パリ 1 | Global Switch | PAR01 | Société par Actions Simplifiée Unipersonnelle, 7-9 rue Petit |
| パリ 2 | Equinix | PA2 | 114 Rue Ambroise Croizat, St Denis |
| ストックホルム 1 | InterXion | STO01 | Esbogatan 11 |
|  |  |  |
| **IBM PoP / データ・センター・コード** | **Meet Me Room オペレーター** | **オペレーター・サイト・コード** |
| **アメリカ大陸** |  |  |
| アトランタ 1*| Digital Realty | ATL13 | 56 Marietta Street |
| シカゴ 1 | Equinix | CH4 | 350 E. Cermak |
| ダラス 3 | Equinix | DA1 | 1950 N. Stemmons Freeway |
| ダラス 4 | Digital Realty | DFW14 | 2323 Bryan St |
| ダラス 9 | Digital Realty | DFW35 | 900 Quality Way |
| ダラス 10 | QTS | IRV | 6431 Longhorn Drive |
| ダラス 12 |Digital Realty | DFW18 | 907 Security Row |
| ダラス 13 | Cyrus One | Carrollton - Frankford | 1649 W. Frankford Rd |
| デンバー 1* | Coresite | DE1 | 910 15th Street | 
| ヒューストン 2* | IBM | HOU02 | 855 Greens Parkway | 
| ロサンゼルス 1* | Coresite | LA1 | 624 S. Grand Ave. AKA 1 Wilshire Blvd |
| メキシコ 1 | Alestra | Alestra Queretaro Datacenter | Lateral Carretera Estatal 431,Parque Tecnologico Inovacion Lote 79, El Marqués |
| マイアミ 1 | Terremark / Verizon | NAP | 50 NE 9th Street |
| モントリオール 1 | COLO-D | COLO-D1 | 2525 Rue Canadien |
| モントリオール 2 | Cologix | MTL3 | 1155 University Street |
| ニューヨーク市 1 | Digital Realty | JFK10 | 111 8th Ave |
| ニューヨーク市 2* | Equinix | NY4 | 755 Secaucus Rd, Secaucus, NJ |
| ニューヨーク市 3* | Equinix | NY5 | 800 Secaucus Rd, Secaucus, NJ |
| サンパウロ 1 | Ascenty | SP1 | Rua Presbitero Plinio Alves de Souza, 757 J. Ermida II,Jundiai |
| サンパウロ 2 | Equinix | SP2 | Alameda Araguaia, 3641 - Alphaville, Barueri |
| シアトル 2 | The Westin Building | WBX | 2001 6th Avenue |
| サンノゼ 2 | Equinix | SV1 | 11 Great Oaks Blvd |
| サンノゼ 3 | Digital Realty | SJC31 | 1100 Space Park Drive |
| サンノゼ 4 | Infomart | SJC1 | 2001 Fortune Drive |
| トロント 1 | Digital Realty | YYZ11 | 371 Gough Rd |
| トロント 2 | Cologix | TOR1 | 151 Front Street |
| ワシントン DC 2 | Equinix | DC2 | 21715 Filigree Ct |
| ワシントン DC 4 | Digital Realty | IAD38 | 44060 Digital Loudoun Plaza (Bldg K) |
| ワシントン DC 5 | Coresite | DC2 | 12098 Sunrise Valley Dr |
| ワシントン DC 6 | Raging Wire | VA2 | 44610 Guilford Drive |
| ワシントン DC 7 | Sabey | Sabey Intergate.Ashburn | 21741 Red Rum Dr|

## 料金
{: #dedicated-pricing}

料金情報については、[料金の資料](/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-direct-link-dedicated)を参照してください。

TOK01 または TOK02 の詳細な住所が必要な場合は、担当の Direct Link オファリング管理または営業チームにお問い合わせください。
{:note}
