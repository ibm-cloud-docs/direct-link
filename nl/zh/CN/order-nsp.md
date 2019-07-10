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

# 如何订购 IBM Cloud Direct Link Dedicated
{: #how-to-order-ibm-cloud-direct-link-dedicated}

1. 验证您的网络提供商是否有能力将适当的 PoP 和交叉连接延伸到 {{site.data.keyword.BluSoftlayer_notm}} 环境。
2. 开具 {{site.data.keyword.cloud}} Direct Link Dedicated 请求并完成所请求的信息。（可以请求 IBM 销售工程师的帮助。）
3. {{site.data.keyword.BluSoftlayer_notm}} 为连接提供授权书 (LOA)。
4. 确认您的线路已经到达 PoP 且已由承运方完成。
5. 使用 LOA 中的 {{site.data.keyword.BluSoftlayer_notm}} CFA（客户设施分配）信息，订购交叉连接，通常需要2 到 10 个工作日即可完成。（此时间范围取决于设施供应商和客户下达订单时的订单优先级类型。）此过程包括设置 {{site.data.keyword.BluSoftlayer_notm}} 终止端口的补丁。
6. 在 {{site.data.keyword.BluSoftlayer_notm}} 门户网站凭单中，从设施提供商向 {{site.data.keyword.BluSoftlayer_notm}} 提供交叉连接完成通知。
7. {{site.data.keyword.BluSoftlayer_notm}} 将验证完成通知的效力，并通过 LOA/CFA 订购要对交叉连接路由器 (XCR) 和其他设备所做的补丁。
8. {{site.data.keyword.BluSoftlayer_notm}} 网络基础架构上的 IP 分配将在完成交叉连接后的 3 个工作日内完成。

## 位置
{: #dedicated-locations}

下表提供了有关 Direct Link Dedicated 在其中可用的 IBM Cloud 数据中心的详细信息：

|**IBM 位置码**|**汇接机房运营商**|**运营商站点代码**|**运营商地址**|
|-----------------|-----------------|--------------------|--------------------|
|**亚太地区**| | | |
| 金奈 1 |Tata|PH-01|226, Red Hills Road,Kallikuppam, Ambattur|
| 香港 1 |Mega-I（通过 PACNET）|Mega-I (iAdvantage Hong Kong)|29F, 399 Chai Wan Road|
|墨尔本 1 |Digital Realty|MEL11|72 Radnor Drive, Deer Park|
| 墨尔本 2 |NextDC|M2|820 Lorimer Street, Port Melbourne|
| 大阪 1 |Equinix| OS1 |  |
| 珀斯 1 |Metronode|F1Z|60 Randell St, Shenton Park, Western Australia|
| 首尔 1 |C&C|Seoul01|46, Pangyo-ro 255beon-gil, Bundang-gu, Seongnam-si, Gyeonggi-do|
| 首尔 2 |KINX|KINX Bundang IDC|3F Hostway IDC ,343-1 Yatap-dong , Gyeonggi-do|
| 新加坡 1 |Digital Realty|SIN10|29A International Business Park, S180|
| 新加坡 2 |Equinix|SG1|20 Ayer Rajan Crescent Industrial Park|
|悉尼 1|Global Switch|SYD01|400 Harris Street aka 273 Pyrmont St Ultimo|
|悉尼 2|Equinix|SY3|47 Bourke Rd|
|悉尼 3|NextDC| S1 |4 Eden Park Drive, Macquarie Park|
|悉尼 4 |Digital Realty|SYD10|1-11 Templar Rd, Erskine Park|
|悉尼 5 |Equinix| SY4 |200 Bourke Rd|
|东京 1|Equinix|TY2| |
|东京 2|At Tokyo|CC2|  |
|东京 3|Equinix| TY4 | |
|东京 4 |SoftBank| | |
| 东京 5 |NTT| | |
|**欧洲、中东和非洲**|  |  |
|阿姆斯特丹 2 |Equinix|AM1 / AM2|Larrderhoogtweg 57|
|Amsterdam 3|KPN|Amsterdam 3|Rondebeltweg 62|
|Frankfurt 1|InterXion|FRA01|Hanauer Landstrasse 302|
|法兰克福 2|Zenium|FRA1|Leonhard - Heisswolf Str 4., Frankfurt am Main|
|法兰克福 3|Equinix|FRA6|Larchenstrasse 110, Frankfurt Griesheim|
|法兰克福 4 |E-Shelter|Frankfurt 1|Eschborner Landstrasse 100, Building H| 
|法兰克福 5 |InterXion|FRA05|Weismüllerstraße 40|
|伦敦 1|Equinix (fTelecity)|LD8|6/7 Harbour Exchange  E14 9GE|
|伦敦 2|Digital Realty|LHR13|Fountain Court, Cox Lane|
|伦敦 3|Equinix|LD5|8 Buckingham Ave|
|伦敦 4 |ARK|A103|A57 Cody Technology Park Old, Victor Way, Farnborough|
|伦敦 6 |Zenium|LON1|12 Liverpool Rd, Trading Estate|
|米兰 1 |Data IV| |Via Monzoro 101-105 , 20010 Cornaredo (MI)|
|米兰 2 |Infracom Italia|Infracom 21 Via Caldera Way|Infracom Italia Spa, Building D, Caldera Business Park, Via Caldera, 21|
|奥斯陆 1 |EVRY|DigiPlex - Fetsund|9,, Heiaveien, 1900 Fetsund|
|奥斯陆 2 |Verizon |Verizon Oslo|Hans Møller Gassmanssvei 9|
|巴黎 1 |Global Switch|PAR01|Société par Actions Simplifiée Unipersonnelle, 7-9 rue Petit|
|巴黎 2 |Equinix|PA2|114 Rue Ambroise Croizat, St Denis|
|斯德哥尔摩 1 |InterXion|STO01|Esbogatan 11|
|  |  |  |
|**IBM PoP/数据中心代码**|**汇接机房运营商**|**运营商站点代码**|
|**美洲地区**|  |  |
| 亚特兰大 1*|Digital Realty|ATL13|56 Marietta Street|
|芝加哥 1 |Equinix|CH4|350 E. Cermak|
|达拉斯 3|Equinix|DA1|1950 N. Stemmons Freeway|
|达拉斯 4|Digital Realty|DFW14|2323 Bryan St|
|达拉斯 9|Digital Realty|DFW35|900 Quality Way|
|达拉斯 10|QTS|IRV|6431 Longhorn Drive|
|达拉斯 12|Digital Realty|DFW18|907 Security Row|
|达拉斯 13|Cyrus One|Carrollton - Frankford|1649 W. Frankford Rd|
|丹佛 1* |Coresite|DE1|910 15th Street| 
|休斯顿 2* |IBM|HOU02|855 Greens Parkway| 
| 洛杉矶 1* |Coresite|LA1|624 S. Grand Ave. AKA 1 Wilshire Blvd|
| 墨西哥 1 |Alestra|Alestra Queretaro Datacenter|Lateral Carretera Estatal 431,Parque Tecnologico Inovacion Lote 79, El Marqués|
| 迈阿密 1 |Terremark / Verizon|NAP|50 NE 9th Street|
| 蒙特利尔 1 |COLO-D|COLO-D1|2525 Rue Canadien|
| 蒙特利尔 2 |Cologix|MTL3|1155 University Street|
| 纽约市 1 |Digital Realty|JFK10|111 8th Ave|
| 纽约市 2* |Equinix|NY4|755 Secaucus Rd, Secaucus, NJ|
| 纽约市 3* |Equinix|NY5|800 Secaucus Rd, Secaucus, NJ|
| 圣保罗 1 |Ascenty|SP1|Rua Presbitero Plinio Alves de Souza, 757 J. Ermida II,Jundiai|
| 圣保罗 2 |Equinix|SP2|Alameda Araguaia, 3641 - Alphaville, Barueri|
| 西雅图 2 |The Westin Building|WBX|2001 6th Avenue|
| 圣何塞 2 |Equinix|SV1|11 Great Oaks Blvd|
| 圣何塞 3 |Digital Realty|SJC31|1100 Space Park Drive|
| 圣何塞 4 |Infomart|SJC1|2001 Fortune Drive|
| 多伦多 1 |Digital Realty|YYZ11|371 Gough Rd|
| 多伦多 2 |Cologix|TOR1|151 Front Street|
|华盛顿特区 2 |Equinix|DC2|21715 Filigree Ct|
|华盛顿特区 4 |Digital Realty|IAD38|44060 Digital Loudoun Plaza (Bldg K)|
|华盛顿特区 5 |Coresite|DC2|12098 Sunrise Valley Dr|
|华盛顿特区 6 |Raging Wire|VA2|44610 Guilford Drive|
|华盛顿特区 7 |Sabey|Sabey Intergate.Ashburn|21741 Red Rum Dr|

## 定价
{: #dedicated-pricing}

有关定价信息，请参阅[定价文档](/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-direct-link-dedicated)。

如果您需要 TOK01 或 TOK02 的准确地址，请联系 Direct Link 产品管理或销售团队。
{:note}
