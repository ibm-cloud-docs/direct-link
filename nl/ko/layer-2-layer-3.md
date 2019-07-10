---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-30"

keywords: layer 2, layer 3, interconnect, partner, multi-cloud, other clouds, BGP, XCR

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Direct Link에 대한 계층 2 및 계층 3 연결 비교
{: #comparing-layer-2-layer-3}

{{site.data.keyword.cloud}} Direct Link는 네트워크 서비스 제공자(NSP)로부터의 OSI 계층 2 및 계층 3 파트너 상호 연결을 허용합니다. 일부 네트워크 서비스 제공자는 여러 네트워크에서 이러한 계층 모두에 대한 서비스를 제공하지만 일부 제공자는 모든 네트워크를 {{site.data.keyword.cloud_notm}}로 상호 연결하지 **않도록** 선택했을 수 있습니다. 

{{site.data.keyword.cloud_notm}} Direct Link 배치를 계획할 때 요구사항에 가장 적합한 배치를 작성할 수 있도록 계층 2 및 계층 3 연결과 연관된 특성을 고려하십시오.

## 계층 2 연결에 대한 고려사항
{: #layer-2-networks}

계층 2 파트너 상호 연결을 통해 작성할 각 VLAN 기반 가상 회선의 경우 온프레미스 라우터 및 IBM Cloud XCR 간의 BGP 세션을 구성하고 설정해야 합니다. IBM Cloud는 라우터와의 BGP 세션을 설정하기 위해 `/31` IPv4 지정을 제공합니다.

* 계층 2 네트워크는 엔터프라이즈와 {{site.data.keyword.cloud_notm}} 사이의 단순한 일대일 연결 옵션을 제공합니다. 
* 계층 2 서비스는 IP 주소 대신 VLAN에 의존합니다. 
* 계층 2 서비스는 계층 3 서비스에 비해 비용이 낮고 대기 시간이 짧을 수 있으며 오버헤드를 덜 이용할 수 있습니다. 
* 계층 2 네트워크는 엔터프라이즈에서 사용할 수 있는 계층 3 기능에 제한을 두지 않습니다.

## 계층 3 연결에 대한 고려사항
{: #layer-3-networks}

계층 3 연결의 경우 서비스 제공자가 각 가상 회선에 대해 IBM Cloud XCR 및 제공자의 에지 라우터 간의 BGP 세션을 설정합니다. 서비스 제공자가 IBM Cloud에 대한 BGP 구성을 관리하기 때문에 온프레미스 라우터에 대해 IBM Cloud로 BGP를 구성할 필요가 없습니다.

* 계층 3 IP VPN 또는 AVPN 네트워크는 "임의(any-to-any)" 연결을 가능하게 합니다. 
* 계층 3 네트워크에서는 네트워크 서비스 제공자가 엔터프라이즈와 {{site.data.keyword.cloud_notm}} 간의 BGP 세션을 유지보수해야 합니다. 
* 특정 네트워크 서비스 제공자가 계층 3 연결 사용 시 해당 네트워크에서 ASN 추가, GRE 터널링 등과 같은 특정 기능을 제한할 수 있습니다. 가능한 제한사항에 대해서는 제공자에게 문의하십시오.

## 파트너 상호 연결 표
{: #partner-interconnection-table}

다음 표에는 각 {{site.data.keyword.cloud_notm}} 파트너가 제공하는 연결의 유형이 요약되어 있습니다. 

|파트너 |상호 연결 유형 |  
|-------|-------|
|AT&T NetBond® for Cloud |계층 3 |
| AT&T Cloud Gateway(이전에는 RedFringe)|계층 3 |
|Bell Canada |계층 3 | 
|British Telecom |계층 3 | 
|CenturyLink IP VPN |계층 3 | 
|CenturyLink Dynamic Connections |계층 2 | 
| Chief Telecomm |계층 2 |
|Colt |계층 2 | 
| Console Connect by PCCW |계층 2 |
|Digital Realty Service Exchange |계층 2 | 
| Epsilon |계층 2 | 
| IBM BlueFringe |계층 3 | 
| Intercloud |계층 3 |
|Megaport |계층 2 |
|MWS GNPP |계층 3 |
|Neutrona |계층 2 |
| NTT |계층 3 |
|PacketFabric |계층 2 |
| Softbank |계층 3 |
| SES Networks |계층 2 |
|Tata IZO™ Private Connect |계층 3 | 
|Telia |계층 3 |
|Telstra |계층 3 |
|Tokai |계층 2 | 
|Verizon SCI|계층 3 |
|Zayo Cloud Link |계층 2 |
