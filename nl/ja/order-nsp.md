---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-24"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud Direct Link Dedicated の注文方法

1. 適切な PoP に到達して {{site.data.keyword.BluSoftlayer_notm}} 環境に相互接続するための、ネットワーク・プロバイダーの機能を確認します。
2. IBM Cloud Direct Link Dedicated 要求を開き、要求された情報を記入します。 (IBM セールス・エンジニアからの支援を要求できます。)
3. {{site.data.keyword.BluSoftlayer_notm}} は、接続用の許可書 (LOA) を提供します。
4. 回線が PoP に到達しており、キャリアによって完了済みであることを確認します。
5. LOA 内の {{site.data.keyword.BluSoftlayer_notm}} CFA (Customer Facility Assignment) 情報を使用して相互接続を注文します。これは、完了までに通常 2 営業日から 10 営業日かかります。 (この時間フレームは、施設のベンダーとお客様が設定した注文優先順位のタイプによって異なります。) このプロセスには、{{site.data.keyword.BluSoftlayer_notm}} 終端ポートへのパッチのセットアップが含まれます。
6. {{site.data.keyword.BluSoftlayer_notm}} ポータル・チケットで、施設のプロバイダーからの相互接続完了通知を {{site.data.keyword.BluSoftlayer_notm}} に提供します。
7. {{site.data.keyword.BluSoftlayer_notm}} は、完了通知の有効性を確認し、LOA/CFA から、相互接続ルーター (XCR) および他のギアへのパッチの作成を注文します。
8. {{site.data.keyword.BluSoftlayer_notm}} ネットワーキング・インフラストラクチャー上の IP 割り当ては、相互接続の完了後 3 営業日以内に完了します。

## 場所

この表では、Direct Link Dedicated が使用可能な IBM Cloud データ・センターに関する詳細を示します。

|**IBM PoP またはデータ・センター・コード** | **Meet Me Room オペレーター**| **オペレーター・サイト・コード** |
|-----------------|-----------------|--------------------|
| **APAC** | | |
| CHE01 | Tata | PH-01 |
| HKG01 | Mega-I (PACNET 経由) | Mega-I (iAdvantage Hong Kong) |
| MEL01 | Digital Realty | MEL11 |
| MEL02 | NextDC | M2 |
| PER01 | Metronode | F1Z |
| SEO01 | C&C | Seoul01 |
| SEO02 | KINX | KINX Bundang IDC |
| SNG01 | Digital Realty | SIN10 |
| SNG02 | Equinix | SG1 |
| SYD01 | Global Switch | SYD01 |
| SYD02 | Equinix | SY3 |
| SYD04 | Digital Realty | SYD10 |
| TOK01 | Equinix | TY2 |
| TOK02 | At Tokyo | CC2 |
| **EMEA** |  |  |
| AMS02 | Equinix | AM1 / AM2 |
| AMS03 | KPN | Amsterdam 3 |
| FRA01 | InterXion | FRA01 |
| FRA02 | Zenium | FRA1 |
| FRA03 | Equinix| FRA6 |
| FRA05 | InterXion | FRA05 |
| LON01 | Telecity | LD1 |
| LON02 | Digital Realty | LHR13 |
| LON03 | Equinix | LD5 |
| LON04 | ARK | A103 |
| LON06 | Zenium | LON1 |
| MIL02 | Infracom Italia | Infracom 21 Via Caldera Way |
| OSL01 | Ervy | DigiPlex - Fetsund |
| OSL02 | Verizon | Verizon Oslo |
| PAR01 | IBM | PAR01 |
| PAR02 | Equinix | PA2 |
| STO01 | InterXion | STO01 |
|  |  |  |
| **IBM PoP / データ・センター・コード** | **Meet Me Room オペレーター** | **オペレーター・サイト・コード** |
| **アメリカ大陸** |  |  |
| ATL01*| Digital Realty | ATL13 |
| CHI01* | Equinix | CH4 |
| DAL03 | Equinix | DA1 |
| DAL04 | Digital Realty | DFW14 |
| DAL09 | Digital Realty | DFW35 |
| DAL10 | QTS | IRV |
| DAL12 |Digital Realty | DFW18 |
| DAL13 | Cyrus One | Carrollton - Frankford |
| DEN01* | Coresite | DE1 |
| HOU02* | IBM | HOU02 |
| LAX01* | Coresite | LA1 |
| MEX01 | Alestra | Alestra Queretaro Datacenter |
| MIA01* | Terremark / Verizon | NAP |
| MON01 | COLO-D | COLO-D1 |
| MON02 | Cologix | MTL3 |
| NYC01 | Digital Realty | JFK10 |
| NYC02 | Equinix | NY4 |
| NYC03 | Equinix | NY5 |
| SAO01 | Ascenty | SP1 |
| SAO02 | Equinix | SP2 |
| SEA02* | The Westin Building | WBX |
| SJC02 | Equinix | SV1 |
| SJC03 | Digital Realty | SJC31 |
| SJC04 | Infomart | SJC1 |
| TOR01 | Digital Realty | YYZ11 |
| TOR02 | Cologix | TOR1 |
| WDC02 | Equinix | DC2 |
| WDC04 | Digital Realty | IAD38 |
| WDC05 | Coresite | DC2 |
| WDC06 | Raging Wire | VA2 |
| WDC07 | Sabey | Sabey Intergate.Ashburn |

## 料金

料金情報については、[料金の資料](pricing.html)を参照してください。
