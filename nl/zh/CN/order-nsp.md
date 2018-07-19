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

# 如何订购 IBM Cloud Direct Link Dedicated

1. 验证您的网络提供商是否有能力将适当的 PoP 和交叉连接延伸到 {{site.data.keyword.BluSoftlayer_notm}} 环境。
2. 打开 IBM Cloud Direct Link Dedicated 请求并完成所请求的信息。（可以请求 IBM 销售工程师的帮助。）
3. {{site.data.keyword.BluSoftlayer_notm}} 为连接提供授权证 (LOA)。
4. 确认您的线路已经到达 PoP 且已由承运方完成。
5. 使用 LOA 中的 {{site.data.keyword.BluSoftlayer_notm}} CFA（客户设施分配）信息，订购交叉连接，通常需要2 到 10 个工作日即可完成。（此时间范围取决于设施供应商和客户下达订单时的订单优先级类型。）此过程包括设置 {{site.data.keyword.BluSoftlayer_notm}} 终止端口的补丁。
6. 在 {{site.data.keyword.BluSoftlayer_notm}} 门户网站凭单中，从设施提供商向 {{site.data.keyword.BluSoftlayer_notm}} 提供交叉连接完成通知。
7. {{site.data.keyword.BluSoftlayer_notm}} 将验证完成通知的效力，并通过 LOA/CFA 订购要对交叉连接路由器 (XCR) 和其他设备所做的补丁。
8. {{site.data.keyword.BluSoftlayer_notm}} 网络基础架构上的 IP 分配将在完成交叉连接后的 3 个工作日内完成。

## 位置

下表提供了有关 Direct Link Dedicated 在其中可用的 IBM Cloud 数据中心的详细信息：

|**IBM PoP 或数据中心代码**|**汇接机房运营商**|**运营商站点代码**|
|-----------------|-----------------|--------------------|
|**亚太地区**| | |
|CHE01|Tata|PH-01|
|HKG01|Mega-I（通过 PACNET）|Mega-I (iAdvantage Hong Kong)|
|MEL01|Digital Realty|MEL11|
|MEL02|NextDC|M2|
|PER01|Metronode|F1Z|
|SEO01|C&C|Seoul01|
|SEO02|KINX|KINX Bundang IDC|
|SNG01|Digital Realty|SIN10|
|SNG02|Equinix|SG1|
|SYD01|Global Switch|SYD01|
|SYD02|Equinix|SY3|
|SYD04|Digital Realty|SYD10|
|TOK01|Equinix|TY2|
|TOK02|At Tokyo|CC2|
|**欧洲、中东和非洲**|  |  |
|AMS02|Equinix|AM1 / AM2|
|AMS03|KPN|Amsterdam 3|
|FRA01|InterXion|FRA01|
|FRA02|Zenium|FRA1|
|FRA03|Equinix|FRA6|
|FRA05|InterXion|FRA05|
|LON01|Telecity|LD1|
|LON02|Digital Realty|LHR13|
|LON03|Equinix|LD5|
|LON04|ARK|A103|
|LON06|Zenium|LON1|
|MIL02|Infracom Italia|Infracom 21 Via Caldera Way|
|OSL01|Ervy|DigiPlex - Fetsund|
|OSL02|Verizon |Verizon Oslo|
|PAR01|IBM|PAR01|
|PAR02|Equinix|PA2|
|STO01|InterXion|STO01|
|  |  |  |
|**IBM PoP/数据中心代码**|**汇接机房运营商**|**运营商站点代码**|
|**美洲地区**|  |  |
|ATL01*|Digital Realty|ATL13|
|CHI01*|Equinix|CH4|
|DAL03|Equinix|DA1|
|DAL04|Digital Realty|DFW14|
|DAL09|Digital Realty|DFW35|
|DAL10|QTS|IRV|
|DAL12|Digital Realty|DFW18|
|DAL13|Cyrus One|Carrollton - Frankford|
|DEN01*|Coresite|DE1|
|HOU02*|IBM|HOU02|
|LAX01*|Coresite|LA1|
|MEX01|Alestra|Alestra Queretaro Datacenter|
|MIA01*|Terremark / Verizon|NAP|
|MON01|COLO-D|COLO-D1|
|MON02|Cologix|MTL3|
|NYC01|Digital Realty|JFK10|
|NYC02|Equinix|NY4|
|NYC03|Equinix|NY5|
|SAO01|Ascenty|SP1|
|SAO02|Equinix|SP2|
|SEA02*|The Westin Building|WBX|
|SJC02|Equinix|SV1|
|SJC03|Digital Realty|SJC31|
|SJC04|Infomart|SJC1|
|TOR01|Digital Realty|YYZ11|
|TOR02|Cologix|TOR1|
|WDC02|Equinix|DC2|
|WDC04|Digital Realty|IAD38|
|WDC05|Coresite|DC2|
|WDC06|Raging Wire|VA2|
|WDC07|Sabey|Sabey Intergate.Ashburn|

## 定价

有关定价信息，请参阅[定价文档](pricing.html)。
