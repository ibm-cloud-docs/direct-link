---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-05-21"

keywords: faq, faqs, questions, answer, billing, fees, point-to-point, bandwidth, charges, redundancy, Global Routing, diversity, IPv6, BGP, charges, jumbo frames

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}
{:faq: data-hd-content-type='faq'}

# FAQ
{: #faqs}

이 섹션에는 {{site.data.keyword.cloud}} Direct Link에 대해 자주 묻는 질문에 대한 답변이 포함되어 있습니다. 

## IBM Cloud Direct Link는 어떻게 작동합니까?
{: #how-does-ibm-cloud-direct-link-work}
{:faq}

모든 Direct Link 고객을 위해 IBM Cloud 팀은 {{site.data.keyword.BluSoftlayer_notm}} 교차 연결 라우터(XCR) 및 고객의 에지 라우터(CER) 간의 지점간 네트워크를 빌드하도록 소형 사설 서브넷을 지정합니다. 그러면 {{site.data.keyword.BluSoftlayer_notm}} 및 고객은 환경 간의 라우트를 교환하기 위해 BGP를 구성합니다. 마지막으로, {{site.data.keyword.BluSoftlayer_notm}}는 고객의 원격 네트워크의 사설 주소 공간으로 고유하지 않은 라우트의 구현을 허용하기 위해 고객을 VRF에 배치합니다.

## IBM Cloud는 Direct Link 제품에 대한 대역폭을 측정합니까?
{: #does-ibm-cloud-meter-bandwidth-for-direct-link-products}
{:faq}

예. 고객과 IBM Cloud 간의 Direct Link 서비스에서의 대역폭 사용은 무료이며 측정되지 않습니다. IBM Cloud는 IBM Cloud 서비스에서 공용 인터넷으로의 아웃바운드 대역폭을 측정합니다.

## Direct Link에 대한 청구는 언제 시작됩니까?
{: #when-does-billing-begin-with-direct-link}
{:faq}

Direct Link Connect 요금에는 IBM Cloud 인프라의 서비스 종료 비용이 포함됩니다. 

인프라 서비스는 사전에 청구되며 클라이언트의 주문을 수락할 때 시작됩니다. 그러나 IBM Cloud Direct Link의 속성으로 인해 IBM Cloud와의 BGP(Border Gateway Protocol) 세션이 설정되거나 서비스 키가 클라이언트에 제공되고 나서 30일 후에 Direct Link 서비스 청구가 시작됩니다. 

다음이 발생한 후 청구가 중지됩니다. (1) 고객이 회선을 삭제하도록 요청합니다. 그리고 (2) Connect 제공자 또는 네트워크 서비스 제공자가 회선을 디프로비저닝했습니다.

## Direct Link의 다른 당사자로부터 어떤 추가 비용이 발생합니까?
{: #what-additional-charges-will-i-incur-from-other-parties-with-direct-link}
{:faq}

교환 제공자 또는 네트워크 서비스 제공자로부터 추가 비용이 있을 수 있습니다. 요금 정보는 제공자를 참조하십시오.

## IBM Cloud Direct Link로 중복성을 획득할 수 있는 방법은 무엇입니까?
{: #how-can-i-achieve-redundancy-with-ibm-cloud-direct-link}
{:faq}

Direct Link는 본질적으로 중복 서비스를 제공하지 않습니다. Direct Link는 다양한 연결을 제공하여 BGP를 통해 중복성을 작성할 수 있도록 합니다. 둘 이상의 {{site.data.keyword.BluSoftlayer_notm}}용 IBM Cloud Direct Link Dedicated 제공자 또는 Exchange 제공자에 연결하여 Direct Link로 다양성을 획득할 수 있습니다. 또는 Exchange 및 Connect를 사용하는 경우 IBM Cloud Direct Link 제공자와의 다양한 NNI를 활용할 수 있습니다.

## 기본 "로컬" 라우팅과 Direct Link용 글로벌 라우팅 추가 기능 간의 차이점은 무엇입니까?
{: #what-is-the-difference-between-the-default-local-routing-and-the-global-routing-add-on-for-direct-link}
{:faq}

표준 Direct Link 오퍼링을 사용하여 선택한 지역의 데이터 센터 사이에서 트래픽을 전송할 수 있습니다. 지정된 지역 외부의 다른 데이터 센터에 액세스해야 하는 경우, 글로벌 라우팅 추가 기능을 주문해야 합니다. 이 모델은 Direct Link 연결이 지시된 시간에 위치에 있었던 ACL(Access Control List)을 기반으로 합니다. 

## Direct Link용 글로벌 라우팅 추가 기능 패키지가 존재하는 이유는 무엇입니까?
{: #why-does-a-global-routing-add-on-package-exist-for-direct-link}
{:faq}

데이터 센터의 로컬 마켓 외부를 순회할 때 고객이 예기치 않은 데이터 비용을 경험하지 않도록 글로벌 라우팅 추가 기능을 추가했습니다. 이는 대부분의 우리 고객에게 더 낮은 비용을 유지하고, 쉽게 전세계의 모든 지역에 접속하기 위한 글로벌 인식으로 고객을 위한 기능을 제공합니다. 그러나 일반적으로 고객에게는 로컬 대역폭 패키지만 필요합니다.

## 달라스와 같은 지역에서 Direct Link Dedicated, Direct Link Connect 또는 Direct Link Exchange에 연결된 경우 Direct Link를 통해 미국의 다른 지역에 대한 액세스할 수 있습니까?
{: #if-i-am-connected-to-a-direct-link-dedicated}
{:faq}

예, 글로벌 라우팅 추가 기능을 선택하면 로컬 마켓의 외부 영역에 대한 액세스 권한을 얻을 수 있습니다. 이 옵션이 선택되지 않은 경우 Direct Link 트래픽은 사용자가 선택한 PoP 또는 DC 위치에 대한 로컬 마켓으로 제한됩니다. 세부사항은 [가격 문서](/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link)를 참조하십시오.

## 지정된 Direct Link 위치에서 사용 가능한 지역에 연결할 수 있습니까?
{: #can-i-connect-to-any-available-region-from-a-given-direct-link-location}
{:faq}

예, 글로벌 라우팅 추가 기능으로 Direct Link를 주문하는 경우라면 가능합니다.

## 내 Direct Link가 연결할 수 있는 지역을 제한할 수 있습니까?
{: #can-i-restrict-the-regions-that-my-direct-link-can-reach}
{:faq}

아니요. IBM Cloud는 다음 두 가지 옵션을 제공합니다. (1) 로컬 마켓만, (2) 글로벌 라우팅 추가 기능과 함께 모든 지역.

## Equinix Cloud Exchange에 대한 Direct Link 자동화 주문 프로세스를 사용했으며 내 내부 네트워크와 겹치는 서브넷이 지정된 경우 어떻게 됩니까?
{: #what-if-i-used-the-direct-link-automated-ordering-process}
{:faq}

2018년 3월 현재, 권장되는 우수 사례는 자동화된 주문을 취소하고 새 티켓을 제출하여 Direct Link 질문지를 채우는 것입니다. 10.254.x.x 범위와 172.32.x.x 범위 중 선호하는 서브넷을 표시해야 합니다.

## Direct Link Exchange와 Direct Link Connect의 차이점은 무엇입니까?
{: #what-is-the-difference-between-direct-link-exchange-and-direct-link-connect}
{:faq}

두 서비스는 유사하며 상대적으로 저비용이고 대기 시간을 허용하며 IBM Cloud Direct Link의 이점을 이용하는 빠른 시작점입니다. 즉, Exchange는 데이터 센터 제공자를 이용하고 Connect는 Telco 캐리어를 이용합니다. 다음은 추가 세부사항입니다.

**Direct Link Exchange**는 데이터 센터 내에서 교환을 이용하려는 고객에게 권장됩니다. Exchange 서비스를 사용하면 기본 회선이 이미 프로비저닝되어 있으므로(이미 다른 클라우드 제공자에 설비 내 물리적 상호 연결이 있어야 함) 고객은 코로케이션에 대한 다중 클라우드 연결을 신속하게 사용할 수 있습니다.

Direct Link Exchange는 IBM Cloud와  Cloud Exchange Service Provider 간 계층 2의 NNI(Network-to-Network Interface) 연결로 작성된 단일 클라우드 교환 포트를 통해 다중 클라우드 공유 사용 환경을 허용할 수 있습니다. 포트 속도는 5Gb까지 사용 가능합니다.

**Direct Link Connect**는 고유 온프레미스 배치와 IBM Cloud 간에 기존 네트워크를 이용하려는 고객을 위한 오퍼링입니다. Direct Link Connect 서비스를 사용하면 고객은 사전 프로비저닝된 기본 회선을 활용하여 새 Telco 네트워크(예: MPLS) 및 기존 Telco 네트워크에서 IBM Cloud를 신속하게 사용할 수 있습니다.

Direct Link Connect를 사용하는 경우 고객이 전세계 설비에서 IBM 파트너가 운영하는 NN(Network-to-Network Interfaces) 연결에서 Connect 제공자를 통해 IBM Cloud에 연결할 수 있습니다. 포트 속도는 5Gb까지 사용 가능합니다.

## Direct Link Connect 및 Direct Link Exchange 제공자를 어떻게 비교합니까?
{: #how-do-direct-link-connect-and-direct-link-exchange-providers-compare}
{:faq}

Connect 제공자는 데이터 센터 이상의 네트워크 범위를 갖는 통신 회사입니다. Exchange 제공자는 해당 데이터 센터로 제한됩니다. 두 경우 모두 고객을 위한 다중 클라우드 환경을 사용하도록 설정할 수 있습니다. Exchange 제공자는 보통 데이터 센터에 코로케이션이 필요한 반면 Connect 제공자는 고객의 온프레미스 사이트 및 데이터 센터에 접속할 수 있습니다.

## IBM에서 Direct Link를 통해 IPv6을 지원할 수 있습니까?
{: #can-ibm-support-ipv6-over-direct-link}
{:faq}

BGP 세션에는 해당되지 않습니다. IPv4에서 /30을 지정해야 하며 고객으로부터 리턴되는 것도 동일해야 합니다.

## IBM에서 사설 네트워크에 대한 IPV6을 수행할 수 있습니까?
{: #can-ibm-do-ipv6-on-the-private-network}
{:faq}

아니요. IPv6을 공용으로만 사용됩니다.

## Verizon SCI에 대한 특별한 요구사항이 있습니까? (접두부/ASN/VLAN BGP 등)이 있습니까?
{: #are-there-any-special-direct-link-requirements-for-verizon-sci}
{:faq}

Verizon SCI는 여러 MPLS 기반 계층 3(IP VPN) 서비스 중 하나입니다. IBM에서 직접 고객과의 BGP를 설정하는 대신 Verizon과의 BGP를 설정해야 합니다. 그런 다음 Verizon이 고객과의 BGP를 설정하고 그에 따라 라우트를 광고합니다. 여러 다른 계층 3 기반 서비스 프로그램이 Direct Link Connect 프로그램에 참여합니다. 고객은 자신이 주문하는 내용과 IBM Cloud에 연결할 때 해당 계정이 작동하는 방식을 알고 있어야 합니다.

## Direct Link는 모든 유형의 QoS를 지원합니까?
{: #does-direct-link-support-any-type-of-qos}
{:faq}

QoS 보증을 지원할 수 없습니다. QoS에는 각 서비스 공급자와 IBM Cloud 간의 MPLS 맵핑이 필요합니다. 일반적으로 클라우드 서비스 제공자는 현재 QoS를 지원할 수 없습니다. 종단에서 종단으로 연결하고 중간에 모든 디바이스를 포함해야 하기 때문입니다. "터널링" 또는 다른 방법으로 사용 가능한 임시 해결책은 없습니다.

## Direct Linkr가 Jumbo Frame을 지원합니까?
{: #does-direct-link-support-jumbo-frames}
{:faq}

Jumbo Frame(최대 9214바이트)은 Dedicated 및 Dedicated Hosting에서 지원됩니다. 
Connect 및 Exchange에 대한 지원이 이론적으로 가능하지만 서비스 제공자가 IBM과 협업하여 엔드-투-엔드 연결이 기본 NNI(Network-to Network-Interface)를 포함하여 Jumbo Frame을 지원하는지 확인해야 합니다.
기본적으로 Exchange 및 Connect는 1500바이트 MTU 지원으로 설정됩니다.

## Direct Link Connect를 사용하는 경우 고객이 동일한 캐리어(예: DAL03의 Verizon)를 통해 라우터 다양성을 보장하는 방법은 무엇입니까?
{: #with-diret-link-connect-how-does-a-customer-ensure-router-diversity-through-the-same-carrier}
{:faq}

IBM에는 캐리어에 대한 다양한 NNI 링크를 작성하는 다양한 XCR이 있습니다. 이 지점에서 다양성을 유지하는 것은 캐리어의 책임입니다.

## Direct Link Connect의 경우 고객이 중복성을 위해 두 개의 링크를 주문해야 합니까, 아니면 Direct Link Connect가 본질적으로 중복성을 제공합니까?
{: #for-diret-link-connect-does-a-customer-need-to-order-2-links-for-redundancy}
{:faq}

다양성을 위해 두 개의 링크를 주문하십시오. 스위치 또는 라우터 간의 중복성을 제공하지 않습니다. 고객이 각 Direct Link에서 해당 BGP 구성을 사용하여 중복성을 작성합니다.

## 내 Direct Link 연결의 대역폭을 얼마나 쉽게 업그레이드할 수 있습니까(예: 1GB에서 5GB로)?
{: #how-easy-is-it-to-upgrade-the-bandwidth-of-my-direct-link-connection}
{:faq}

일반적으로 1G 광학에 1G 이하의 속도로 설치합니다. 2G - 10G 속도의 경우 10G 광학을 설치합니다. 따라서 1G에서 5G로 업그레이드하려면 새 광학이 지정되거나 삽입되어야 합니다. 이는 서비스에 영향을 미치는 이벤트일 수 있습니다. 이러한 유형의 성장을 예상하는 경우 Direct Link 배치를 시작할 때 10G 광섬유가 설치되도록 요청하거나 10G 광학이 준비될 수 있도록 처음에 2G를 주문할 수 있습니다.

## ECMP를 통해 중복 Direct Link 연결을 사용할 수 있습니까?  어떤 대안이 있습니까?
{: #is-ecmp-the-way-to-go-for-redundant-direct-link-connections}
{:faq}

ECMP는 중복 연결에 사용되는 것이 아니라 두 개의 링크 간 로드를 밸런싱하는 데 사용됩니다. ECMP를 사용하면 두 개의 연결이 모두 동일한 IBM Cloud 교차 연결 라우터(XCR)로 종료되어야 하므로 단일 장애 지점이 됩니다. (즉, ECMP는 동일한 IBM Cloud XCR의 두 개 세션으로만 프로비저닝할 수 있습니다.) 

ECMP는 BGP의 기능입니다. 중복성을 원하는 경우 두 개의 Direct Link 연결을 확보하십시오. 각 XCR마다 하나씩 연결됩니다. ECMP를 사용하고 중복성을 얻으려면 두 개의 ECMP 세션이 동시에 진행될 수 있도록 각 XCR에 두 개의 Direct Link 연결이 필요합니다.

또는 일부 고객은 동일한 데이터 센터(예: WDC02)의 다른 XCR에 대한 두 개의 링크를 설정한 다음 필요에 따라 BGP 구성을 사용하여 장애를 복구합니다. 이 구성은 두 개의 별도 데이터 센터(예: WDC02 및 WDC05)로의 Direct Link 연결을 보유하는 것보다 중복성이 낮습니다(덜 안전함).

## Direct Link XCR 연결에 계정의 BCR 연결까지의 SLA가 존재합니까?
{: #is-there-an-sla-on-the-diret-link-xr-connections}
{:faq}

현재는 Direct Link에 SLA가 존재하지 않습니다. 고객은 BGP를 사용하여 장애 복구에 대해 적절히 구성된 2개 이상의 Direct Link를 통해 99.999% 효과적으로 달성할 수 있으나, IBM은 이를 제어하거나 이에 대한 SLA를 제공할 수 없습니다.

## Direct Link를 설정할 때 어디에서 도움을 받을 수 있습니까?
{: #where-can-i-get-help-setting-up-a-direct-link}
{:faq}

Direct Link에 연결하는 경우 [{{site.data.keyword.cloud_notm}} Direct Link 구성](/docs/infrastructure/direct-link?topic=direct-link-how-to-order-ibm-cloud-direct-link-dedicated)을 참조하십시오. 추가적인 도움이 필요한 경우 새 서비스에 대해 열린 티켓에서 기술 지원을 요청할 수 있습니다. Equinix가 포함된 API 서비스의 경우에도 티켓을 열면 엔지니어가 이를 확인할 수 있습니다. 또는 IBM 영업 담당자에게 문의할 수 있습니다.

## Direct Link Exchange의 경우 IBM에서 BGP 비밀번호를 설정합니까?
{: #on-direct-link-exchange-does-ibm-set-a-bgp-password}
{:faq}

기본적으로 IBM은 Direct Link Exchange에 대한 어떠한 BGP 비밀번호도 설정하지 않습니다. BGP ASN을 지정하고 IBM에서 BGP IP 주소를 지정하는 옵션은 존재합니다. 또한 인증 용도로 BGP 비밀번호를 설정할 수 있으며, 엔지니어가 이를 인지하도록 해야 합니다.
