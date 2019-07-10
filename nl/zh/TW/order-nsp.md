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

# 如何訂購 IBM Cloud Direct Link Dedicated
{: #how-to-order-ibm-cloud-direct-link-dedicated}

1. 驗證您的網路提供者能夠聯繫適當的 PoP 並交叉連接至 {{site.data.keyword.BluSoftlayer_notm}} 環境。
2. 開立 {{site.data.keyword.cloud}} Direct Link Dedicated 要求並填寫所要求的資訊。（可以要求 IBM 業務工程師協助。）
3. {{site.data.keyword.BluSoftlayer_notm}} 提供連線的授權信 (LOA)。
4. 確認您的電路已聯繫 PoP 並且已由通訊業者完成。
5. 使用 LOA 中的 {{site.data.keyword.BluSoftlayer_notm}} CFA（客戶設施指派）資訊訂購交叉連接，這通常需要 2 到 10 個營業日才能完成。（此時間範圍取決於設備供應商，以及客戶所下訂單的優先順序類型。）此處理程序包含設定 {{site.data.keyword.BluSoftlayer_notm}} 終止埠的修補程式。
6. 在 {{site.data.keyword.BluSoftlayer_notm}} 入口網站問題單中，提供 {{site.data.keyword.BluSoftlayer_notm}} 來自設施提供者的交叉連接完成通知。
7. {{site.data.keyword.BluSoftlayer_notm}} 會驗證完成通知的效力，並訂購要從 LOA/CFA 對交叉連接路由器 (XCR) 和其他裝備進行的修補程式。
8. {{site.data.keyword.BluSoftlayer_notm}} 網路基礎架構上的 IP 指派將在交叉連接完成之後的三個營業日之內完成。

## 位置
{: #dedicated-locations}

下表含有目前有提供 Direct Link Dedicated 的 IBM Cloud 資料中心的相關詳細資料：

|**IBM 位置碼** | **匯接機房操作員**| **操作員網站代碼** | **操作員地址** |
|-----------------|-----------------|--------------------|--------------------|
| **APAC** | | | |
| 清奈 1 | Tata | PH-01 | 226, Red Hills Road,Kallikuppam, Ambattur |
| 香港 1 | Mega-I（透過 PACNET）| Mega-I (iAdvantage Hong Kong) |29F, 399 Chai Wan Road |
| 墨爾本 1 | Digital Realty | MEL11 |  72 Radnor Drive, Deer Park |
| 墨爾本 2 | NextDC | M2 | 820 Lorimer Street, Port Melbourne |
| 大阪 1 | Equinix | OS1 |  |
| 伯斯 1 | Metronode | F1Z | 60 Randell St, Shenton Park, Western Australia |
| 首爾 1 | C&C | Seoul01 | 46, Pangyo-ro 255beon-gil, Bundang-gu, Seongnam-si, Gyeonggi-do |
| 首爾 2 | KINX | KINX Bundang IDC | 3F Hostway IDC ,343-1 Yatap-dong , Gyeonggi-do |
| 新加坡 1 | Digital Realty | SIN10 | 29A International Business Park, S180 |
| 新加坡 2 | Equinix | SG1 | 20 Ayer Rajan Crescent Industrial Park |
| 雪梨 1 | Global Switch | SYD01 | 400 Harris Street aka 273 Pyrmont St Ultimo  |
| 雪梨 2 | Equinix | SY3 | 47 Bourke Rd |
| 雪梨 3 | NextDC | S1 | 4 Eden Park Drive, Macquarie Park |
| 雪梨 4 | Digital Realty | SYD10 | 1-11 Templar Rd, Erskine Park |
| 雪梨 5 | Equinix | SY4 | 200 Bourke Rd |
| 東京 1 | Equinix | TY2 | |
| 東京 2 | At Tokyo | CC2 |  |
| 東京 3 | Equinix | TY4 | |
| 東京 4 | SoftBank | | |
| 東京 5 | NTT | | |
| **EMEA** |  |  |
| 阿姆斯特丹 2 | Equinix | AM1 / AM2 | Larrderhoogtweg 57 |
| Amsterdam 3 | KPN | Amsterdam 3 | Rondebeltweg 62 |
| Frankfurt 1 | InterXion | FRA01 | Hanauer Landstrasse 302 |
| 法蘭克福 2 | Zenium | FRA1 | Leonhard - Heisswolf Str 4., Frankfurt am Main |
| 法蘭克福 3 | Equinix| FRA6 | Larchenstrasse 110, Frankfurt Griesheim |
| 法蘭克福 4 | E-Shelter | Frankfurt 1 | Eschborner Landstrasse 100, Building H | 
| 法蘭克福 5 | InterXion | FRA05 | Weismüllerstraße 40 |
| 倫敦 1 | Equinix (fTelecity) | LD8 | 6/7 Harbour Exchange  E14 9GE |
| 倫敦 2 | Digital Realty | LHR13 | Fountain Court, Cox Lane |
| 倫敦 3 | Equinix | LD5 | 8 Buckingham Ave |
| 倫敦 4 | ARK | A103 |  A57 Cody Technology Park Old, Victor Way, Farnborough |
| 倫敦 6 | Zenium | LON1 | 12 Liverpool Rd, Trading Estate |
| 米蘭 1 | Data IV | | Via Monzoro 101-105 , 20010 Cornaredo (MI) |
| 米蘭 2 | Infracom Italia | Infracom 21 Via Caldera Way | Infracom Italia Spa, Building D, Caldera Business Park, Via Caldera, 21|
| 奧斯陸 1 | EVRY | DigiPlex - Fetsund | 9,, Heiaveien, 1900 Fetsund |
| 奧斯陸 2 | Verizon | Verizon Oslo | Hans Møller Gassmanssvei 9 |
| 巴黎 1 | Global Switch | PAR01 | Société par Actions Simplifiée Unipersonnelle, 7-9 rue Petit |
| 巴黎 2 | Equinix | PA2 | 114 Rue Ambroise Croizat, St Denis |
| 斯德哥爾摩 1 | InterXion | STO01 | Esbogatan 11 |
|  |  |  |
| **IBM PoP / 資料中心代碼** | **匯接機房操作員** | **操作員網站代碼** |
| **Americas** |  |  |
| 亞特蘭大 1*| Digital Realty | ATL13 | 56 Marietta Street |
| 芝加哥 1 | Equinix | CH4 | 350 E. Cermak |
| 達拉斯 3 | Equinix | DA1 | 1950 N. Stemmons Freeway |
| 達拉斯 4 |Digital Realty | DFW14 | 2323 Bryan St |
| 達拉斯 9 | Digital Realty | DFW35 | 900 Quality Way |
| 達拉斯 10 | QTS | IRV | 6431 Longhorn Drive |
| 達拉斯 12 |Digital Realty | DFW18 | 907 Security Row |
| 達拉斯 13 | Cyrus One | Carrollton - Frankford | 1649 W. Frankford Rd |
| 丹佛 1* | Coresite | DE1 | 910 15th Street | 
| 休斯頓 2* | IBM | HOU02 | 855 Greens Parkway | 
| 洛杉磯 1* | Coresite | LA1 | 624 S. Grand Ave. AKA 1 Wilshire Blvd |
| 墨西哥 1 | Alestra | Alestra Queretaro Datacenter | Lateral Carretera Estatal 431,Parque Tecnologico Inovacion Lote 79, El Marqués |
| 邁阿密 1 | Terremark / Verizon | NAP | 50 NE 9th Street |
| 蒙特婁 1 | COLO-D | COLO-D1 | 2525 Rue Canadien |
| 蒙特婁 2 | Cologix | MTL3 | 1155 University Street |
| 紐約市 1 | Digital Realty | JFK10 | 111 8th Ave |
| 紐約市 2* | Equinix | NY4 | 755 Secaucus Rd, Secaucus, NJ |
| 紐約市 3* | Equinix | NY5 | 800 Secaucus Rd, Secaucus, NJ |
| 聖保羅 1 | Ascenty | SP1 | Rua Presbitero Plinio Alves de Souza, 757 J. Ermida II,Jundiai |
| 聖保羅 2 | Equinix | SP2 | Alameda Araguaia, 3641 - Alphaville, Barueri |
| 西雅圖 2 | The Westin Building | WBX | 2001 6th Avenue |
| 聖荷西 2 | Equinix | SV1 | 11 Great Oaks Blvd |
| 聖荷西 3 | Digital Realty | SJC31 | 1100 Space Park Drive |
| 聖荷西 4 | Infomart | SJC1 | 2001 Fortune Drive |
| 多倫多 1 | Digital Realty | YYZ11 | 371 Gough Rd |
| 多倫多 2 | Cologix | TOR1 | 151 Front Street |
| 華盛頓特區 2 | Equinix | DC2 | 21715 Filigree Ct |
| 華盛頓特區 4 | Digital Realty | IAD38 | 44060 Digital Loudoun Plaza (Bldg K) |
| 華盛頓特區 5 | Coresite | DC2 | 12098 Sunrise Valley Dr |
| 華盛頓特區 6 | Raging Wire | VA2 | 44610 Guilford Drive |
| 華盛頓特區 7 | Sabey | Sabey Intergate.Ashburn | 21741 Red Rum Dr|

## 定價
{: #dedicated-pricing}

如需計價資訊，請參閱[定價文件](/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-direct-link-dedicated)。

如果您需要 TOK01 或 TOK02 的確切地址，請與 Direct Link 供應項目管理或銷售團隊聯絡。
{:note}
