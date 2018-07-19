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

# IBM Cloud Direct Link Dedicated 주문 방법

1. 적합한 PoP 및 교차 연결을 {{site.data.keyword.BluSoftlayer_notm}} 환경에 연결하기 위해 네트워크 제공자의 기능을 확인하십시오.
2. IBM Cloud Direct Link Dedicated 요청을 열고 요청된 정보를 완료하십시오. (IBM 영업 엔지니어의 지원을 요청할 수 있습니다.)
3. {{site.data.keyword.BluSoftlayer_notm}}는 연결을 위해 LOA(Letter of Authorization)를 제공합니다.
4. 사용자의 회선이 PoP에 연결되었으며 캐리어에 의해 완료되었음을 확인하십시오.
5. LOA에서 {{site.data.keyword.BluSoftlayer_notm}} CFA(Customer Facility Assignment) 정보를 사용하여 교차 연결을 주문하십시오. 완료되려면 일반적으로 2 -10 영업일이 소요됩니다. (이 시간 범위는 설비 벤더 및 고객이 주문을 배치할 때 주문 우선순위의 유형에 따라 달라집니다.) 이 프로세스에는 {{site.data.keyword.BluSoftlayer_notm}} 종료 포트에 패치 설정이 포함됩니다.
6. {{site.data.keyword.BluSoftlayer_notm}}에 {{site.data.keyword.BluSoftlayer_notm}} 포털 티켓의 설비 제공자로부터 교차 연결 완료 통지를 제공하십시오.
7. {{site.data.keyword.BluSoftlayer_notm}}는 완료 통지의 유효성을 확인하고 LOA/CFA에서 교차 연결 라우터(XCR) 및 기타 기어에 패치를 만들도록 주문합니다.
8. {{site.data.keyword.BluSoftlayer_notm}} 네트워킹 인프라에서 IP 지정은 교차 연결이 완료된 이후 3 영업일 이내에 완료됩니다.

## 위치

다음 표에는 Direct Link Dedicated가 사용 가능한 IBM Cloud 데이터 센터에 대한 세부사항이 제공됩니다.

|**IBM PoP 또는 데이터 센터 코드** | **MMR(Meet Me Room）운영자**| **운영자 사이트 코드** |
|-----------------|-----------------|--------------------|
| **APAC** | | |
|CHE01 |Tata | PH-01 |
| HKG01 | Mega-I(PACNET을 통해) | Mega-I(iAdvantage Hong Kong) |
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
| OSL02 |Verizon | Verizon Oslo |
| PAR01 |IBM | PAR01 |
| PAR02 | Equinix | PA2 |
| STO01 | InterXion | STO01 |
|  |  |  |
| **IBM PoP / 데이터 센터 코드** | **MMR(Meet Me Room）운영자** | **운영자 사이트 코드** |
| **미국** |  |  |
| ATL01*| Digital Realty | ATL13 |
| CHI01* | Equinix | CH4 |
| DAL03 | Equinix | DA1 |
| DAL04 | Digital Realty | DFW14 |
| DAL09 | Digital Realty | DFW35 |
| DAL10 | QTS | IRV |
| DAL12 |Digital Realty | DFW18 |
| DAL13 | Cyrus One | Carrollton - Frankford |
| DEN01* | Coresite | DE1 |
| HOU02* |IBM | HOU02 |
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

## 가격 책정

가격 책정 정보는 [가격 책정 문서](pricing.html)를 참조하십시오.
