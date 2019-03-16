---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-02-19"

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

この表では、Direct Link Dedicated が使用可能な IBM Cloud データ・センターに関する詳細を示します。

|**IBM ロケーション・コード** | **Meet Me Room オペレーター**| **オペレーター・サイト・コード** | **オペレーターの住所** |
|-----------------|-----------------|--------------------|--------------------|
| **APAC** | | | |
| CHE01 | Tata | PH-01 | 226, Red Hills Road,Kallikuppam, Ambattur |
| HKG01 | Mega-I (PACNET 経由) | Mega-I (iAdvantage Hong Kong) |29F, 399 Chai Wan Road |
| MEL01 | Digital Realty | MEL11 | 72 Radnor Drive, Deer Park |
| MEL02 | NextDC | M2 | 820 Lorimer Street, Port Melbourne |
| PER01 | Metronode | F1Z | 60 Randell St, Shenton Park, Western Australia |
| SEO01 | C&C | Seoul01 | 46, Pangyo-ro 255beon-gil, Bundang-gu, Seongnam-si, Gyeonggi-do |
| SEO02 | KINX | KINX Bundang IDC | 3F Hostway IDC ,343-1 Yatap-dong , Gyeonggi-do |
| SNG01 | Digital Realty | SIN10 | 29A International Business Park, S180 |
| SNG02 | Equinix | SG1 | 20 Ayer Rajan Crescent Industrial Park |
| SYD01 | Global Switch | SYD01 | 400 Harris Street aka 273 Pyrmont St Ultimo  |
| SYD02 | Equinix | SY3 | 47 Bourke Rd |
| SYD03 | NextDC | 4 Eden Park Drive, Macquarie Park |
| SYD04 | Digital Realty | SYD10 | 1-11 Templar Rd, Erskine Park |
| SYD05 | Equinix | 200 Bourke Rd |
| TOK01 | Equinix | TY2 |
| TOK02 | At Tokyo | CC2 | 
| TOK03 | Equinix | 
| TOK04 | ソフトバンク |
| TOK05 | NTT |
| **EMEA** |  |  |
| AMS02 | Equinix | AM1 / AM2 | Larrderhoogtweg 57 |
| AMS03 | KPN | Amsterdam 3 | Rondebeltweg 62 |
| FRA01 | InterXion | FRA01 | Hanauer Landstrasse 302 |
| FRA02 | Zenium | FRA1 | Leonhard - Heisswolf Str 4., Frankfurt am Main |
| FRA03 | Equinix| FRA6 | Larchenstrasse 110, Frankfurt Griesheim |
| FRA04 | E-Shelter | Frankfurt 1 | Eschborner Landstrasse 100, Building H | 
| FRA05 | InterXion | FRA05 | Weismüllerstraße 40 |
| LON01 | Equinix (fTelecity) | LD8 | 6/7 Harbour Exchange  E14 9GE |
| LON02 | Digital Realty | LHR13 | Fountain Court, Cox Lane |
| LON03 | Equinix | LD5 | 8 Buckingham Ave |
| LON04 | ARK | A103 | A57 Cody Technology Park Old, Victor Way, Farnborough |
| LON06 | Zenium | LON1 | 12 Liverpool Rd, Trading Estate |
| MIL01 | Data IV | Via Monzoro 101-105 , 20010 Cornaredo (MI) |
| MIL02 | Infracom Italia | Infracom 21 Via Caldera Way | Infracom Italia Spa, Building D, Caldera Business Park, Via Caldera, 21|
| OSL01 | EVRY | DigiPlex - Fetsund | 9,, Heiaveien, 1900 Fetsund |
| OSL02 | Verizon | Verizon Oslo | Hans Møller Gassmanssvei 9 |
| PAR01 | Global Switch | PAR01 | Société par Actions Simplifiée Unipersonnelle, 7-9 rue Petit |
| PAR02 | Equinix | PA2 | 114 Rue Ambroise Croizat, St Denis |
| STO01 | InterXion | STO01 | Esbogatan 11 |
|  |  |  |
| **IBM PoP / データ・センター・コード** | **Meet Me Room オペレーター** | **オペレーター・サイト・コード** |
| **アメリカ大陸** |  |  |
| ATL01*| Digital Realty | ATL13 | 56 Marietta Street |
| CHI01 | Equinix | CH4 | 350 E. Cermak |
| DAL03 | Equinix | DA1 | 1950 N. Stemmons Freeway |
| DAL04 | Digital Realty | DFW14 | 2323 Bryan St |
| DAL09 | Digital Realty | DFW35 | 900 Quality Way |
| DAL10 | QTS | IRV | 6431 Longhorn Drive |
| DAL12 |Digital Realty | DFW18 | 907 Security Row |
| DAL13 | Cyrus One | Carrollton - Frankford | 1649 W. Frankford Rd |
| DEN01* | Coresite | DE1 | 910 15th Street | 
| HOU02* | IBM | HOU02 | 855 Greens Parkway | 
| LAX01* | Coresite | LA1 | 624 S. Grand Ave. AKA 1 Wilshire Blvd |
| MEX01 | Alestra | Alestra Queretaro Datacenter | Lateral Carretera Estatal 431,Parque Tecnologico Inovacion Lote 79, El Marqués |
| MIA01 | Terremark / Verizon | NAP | 50 NE 9th Street |
| MON01 | COLO-D | COLO-D1 | 2525 Rue Canadien |
| MON02 | Cologix | MTL3 | 1155 University Street |
| NYC01 | Digital Realty | JFK10 | 111 8th Ave |
| NYC02* | Equinix | NY4 | 755 Secaucus Rd, Secaucus, NJ |
| NYC03* | Equinix | NY5 | 800 Secaucus Rd, Secaucus, NJ |
| SAO01 | Ascenty | SP1 | Rua Presbitero Plinio Alves de Souza, 757 J. Ermida II,Jundiai |
| SAO02 | Equinix | SP2 | Alameda Araguaia, 3641 - Alphaville, Barueri |
| SEA02 | The Westin Building | WBX | 2001 6th Avenue |
| SJC02 | Equinix | SV1 | 11 Great Oaks Blvd |
| SJC03 | Digital Realty | SJC31 | 1100 Space Park Drive |
| SJC04 | Infomart | SJC1 | 2001 Fortune Drive |
| TOR01 | Digital Realty | YYZ11 | 371 Gough Rd |
| TOR02 | Cologix | TOR1 | 151 Front Street |
| WDC02 | Equinix | DC2 | 21715 Filigree Ct |
| WDC04 | Digital Realty | IAD38 | 44060 Digital Loudoun Plaza (Bldg K) |
| WDC05 | Coresite | DC2 | 12098 Sunrise Valley Dr |
| WDC06 | Raging Wire | VA2 | 44610 Guilford Drive |
| WDC07 | Sabey | Sabey Intergate.Ashburn | 21741 Red Rum Dr|

## 料金

料金情報については、[料金の資料](/docs/infrastructure/direct-link/pricing.html)を参照してください。

TOK01 または TOK02 の詳細な住所が必要な場合は、担当の Direct Link オファリング管理または営業チームにお問い合わせください。
{:note}
