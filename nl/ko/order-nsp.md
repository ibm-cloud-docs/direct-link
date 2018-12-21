---

copyright:
  years: 2017, 2018
lastupdated: "2018-07-23"

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

|**IBM 위치 코드** | **MMR(Meet Me Room）운영자**| **운영자 사이트 코드** | **운영자 주소** |
|-----------------|-----------------|--------------------|--------------------|
| **APAC** | | | |
|CHE01 |Tata | PH-01 | 226, Red Hills Road,Kallikuppam, Ambattur |
| HKG01 | Mega-I(PACNET을 통해) | Mega-I(iAdvantage Hong Kong) |29F, 399 Chai Wan Road |
| MEL01 | Digital Realty | MEL11 |  72 Radnor Drive, Deer Park |
| MEL02 | NextDC | M2 | 820 Lorimer Street, Port Melbourne |
| PER01 | Metronode | F1Z | 60 Randell St, Shenton Park, Western Australia |
| SEO01 | C&C | Seoul01 | 46, Pangyo-ro 255beon-gil, Bundang-gu, Seongnam-si, Gyeonggi-do |
| SEO02 | KINX | KINX Bundang IDC | 3F Hostway IDC ,343-1 Yatap-dong , Gyeonggi-do |
| SNG01 | Digital Realty | SIN10 | 29A International Business Park, S180 |
| SNG02 | Equinix | SG1 | 20 Ayer Rajan Crescent Industrial Park |
| SYD01 | Global Switch | SYD01 | 400 Harris Street aka 273 Pyrmont St Ultimo  |
| SYD02 | Equinix | SY3 | 47 Bourke Rd |
| SYD04 | Digital Realty | SYD10 | 1-11 Templar Rd, Erskine Park |
| TOK01 | Equinix | TY2 |
| TOK02 | At Tokyo | CC2 | 
| TOK03 | Equinix | 
| TOK04 | SoftBank |
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
| LON04 | ARK | A103 |  A57 Cody Technology Park Old, Victor Way, Farnborough |
| LON06 | Zenium | LON1 | 12 Liverpool Rd, Trading Estate |
| MIL02 | Infracom Italia | Infracom 21 Via Caldera Way | Infracom Italia Spa, Building D, Caldera Business Park, Via Caldera, 21|
| OSL01 | EVRY | DigiPlex - Fetsund | 9,, Heiaveien, 1900 Fetsund |
| OSL02 |Verizon | Verizon Oslo | Hans Møller Gassmanssvei 9 |
| PAR01 |IBM | PAR01 | Société par Actions Simplifiée Unipersonnelle, 7-9 rue Petit |
| PAR02 | Equinix | PA2 | 114 Rue Ambroise Croizat, St Denis |
| STO01 | InterXion | STO01 | Esbogatan 11 |
|  |  |  |
| **IBM PoP / 데이터 센터 코드** | **MMR(Meet Me Room）운영자** | **운영자 사이트 코드** |
| **미국** |  |  |
| ATL01*| Digital Realty | ATL13 | 56 Marietta Street |
| CHI01 | Equinix | CH4 | 350 E. Cermak |
| DAL03 | Equinix | DA1 | 1950 N. Stemmons Freeway |
| DAL04 | Digital Realty | DFW14 | 2323 Bryan St |
| DAL09 | Digital Realty | DFW35 | 900 Quality Way |
| DAL10 | QTS | IRV | 6431 Longhorn Drive |
| DAL12 |Digital Realty | DFW18 | 907 Security Row |
| DAL13 | Cyrus One | Carrollton - Frankford | 1649 W. Frankford Rd |
| DEN01* | Coresite | DE1 | 910 15th Street | 
| HOU02* |IBM | HOU02 | 855 Greens Parkway | 
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

## 가격

가격 정보는 [가격 문서](pricing.html)를 참조하십시오.

**TOK01 또는 TOK02에 대한 정확한 주소가 필요한 경우에는 Direct Link 오퍼링 관리 또는 영업 팀에 문의하십시오.**
