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

# 如何訂購 IBM Cloud Direct Link Dedicated

1. 驗證您的網路提供者能夠聯繫適當的 PoP 並交叉連接至 {{site.data.keyword.BluSoftlayer_notm}} 環境。
2. 開立 IBM Cloud Direct Link Dedicated 要求並填寫所要求的資訊。（可以要求 IBM 業務工程師協助。）
3. {{site.data.keyword.BluSoftlayer_notm}} 提供連線的授權信 (LOA)。
4. 確認您的電路已聯繫 PoP 並且已由通訊業者完成。
5. 使用 LOA 中的 {{site.data.keyword.BluSoftlayer_notm}} CFA（客戶設施指派）資訊訂購交叉連接，這通常需要 2 到 10 個營業日才能完成。（此時間範圍取決於設備供應商，以及客戶所下訂單的優先順序類型。）此處理程序包含設定 {{site.data.keyword.BluSoftlayer_notm}} 終止埠的修補程式。
6. 在 {{site.data.keyword.BluSoftlayer_notm}} 入口網站問題單中，提供 {{site.data.keyword.BluSoftlayer_notm}} 來自設施提供者的交叉連接完成通知。
7. {{site.data.keyword.BluSoftlayer_notm}} 會驗證完成通知的效力，並訂購要從 LOA/CFA 對交叉連接路由器 (XCR) 和其他裝備進行的修補程式。
8. {{site.data.keyword.BluSoftlayer_notm}} 網路基礎架構上的 IP 指派將在交叉連接完成之後的三個營業日之內完成。

## 位置

下表含有目前有提供 Direct Link Dedicated 的 IBM Cloud 資料中心的相關詳細資料：

|**IBM 位置碼** | **匯接機房操作員**| **操作員網站代碼** | **操作員地址** |
|-----------------|-----------------|--------------------|--------------------|
| **APAC** | | | |
| CHE01 | Tata | PH-01 | 226, Red Hills Road,Kallikuppam, Ambattur |
| HKG01 | Mega-I（透過 PACNET）| Mega-I (iAdvantage Hong Kong) |29F, 399 Chai Wan Road |
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
| OSL02 | Verizon | Verizon Oslo | Hans Møller Gassmanssvei 9 |
| PAR01 | IBM | PAR01 | Société par Actions Simplifiée Unipersonnelle, 7-9 rue Petit |
| PAR02 | Equinix | PA2 | 114 Rue Ambroise Croizat, St Denis |
| STO01 | InterXion | STO01 | Esbogatan 11 |
|  |  |  |
| **IBM PoP / 資料中心代碼** | **匯接機房操作員** | **操作員網站代碼** |
| **Americas** |  |  |
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

## 定價

如需計價資訊，請參閱[定價文件](pricing.html)。

**如果您需要 TOK01 或 TOK02 的確切地址，請與 Direct Link 供應項目管理或銷售團隊聯絡。**
