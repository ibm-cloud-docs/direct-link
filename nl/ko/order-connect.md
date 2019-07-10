---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-14"

keywords: order, provider, capabilities, Connect, cross-connect, locations, PoP, datacenter, data, center, pricing, virtual circuit, Request ID, Authorization ID

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud Direct Link Connect 주문 방법
{: #how-to-order-ibm-cloud-direct-link-connect}

 * 적합한 PoP 및 교차 연결을 연관된 Connect 제공자에 연결하기 위해 네트워크 제공자의 기능을 확인하십시오.
 * [고객 포털 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/)을 사용하여 {{site.data.keyword.cloud}} Cloud Direct Link Connect 요청을 열고 요청된 정보를 작성하십시오. (IBM 영업 엔지니어의 지원을 요청할 수 있습니다.) 
 * Connect 제공자에게 문의하여 교환에 대한 연결을 조정하십시오.
 * 네트워크 제공자와 Connect 제공자 간의 연결을 주문하십시오.
 * Connect 제공자를 통해 "가상 회선"을 주문하고 {{site.data.keyword.BluSoftlayer_notm}} IBM Cloud Direct Link 요청의 티켓 ID를 사용자의 "요청 ID" 또는 "권한 ID"로 참조하십시오.
 * {{site.data.keyword.BluSoftlayer_notm}} 네트워킹 인프라에서 IP 지정은 가상 회선 요청이 완료된 이후 3 영업일 이내에 완료됩니다.
 

## 위치
{: #connect-locations}

IBM Cloud Direct Link Connect 제공자에는 다음 위치가 포함됩니다.

|파트너 | 사용 가능한 마켓 |
|--------------|--------------|
|AT&T; NetBond® for Cloud |싱가포르 2, 프랑크푸르트 1, 런던 1, 댈러스 3, 산호세 2, 워싱턴 DC 2 |
| AT&T Cloud Gateway(이전에는 RedFringe)|댈러스 3, 워싱턴 DC 2 |
|Bell Canada |몬트리올 2, 토론토 2 |
|British Telecom |런던 1, 프랑크푸르트 1, 워싱턴 DC 2, 상파울루 2, 홍콩 1* |
| CenturyLink |댈러스 3, 상파울루 2, 마이애미 1 |
| Chief Telecomm |홍콩 1* |
|Colt |암스테르담 2, 프랑크푸르트 1, 파리 2, 도쿄 1, 싱가포르 2, 런던 1*, 홍콩 1* |
| Console Connect by PCCW |홍콩 1, 도쿄 1, 싱가포르 2, 런던 1, 산호세 2 |
|Digital Realty Service Exchange |	암스테르담 2, 프랑크푸르트 1, 런던 3, 스톡홀름 1, 댈러스 3, 산호세 2, 토론토 2, 워싱턴 DC 2의 Megaport에서 지원됨 |
| Epsilon |암스테르담 2*, 댈러스 3*, 프랑크푸르트 1*, 홍콩 1*, 런던 1*, 싱가포르 2*, 워싱턴 DC 2* |
| IBM BlueFringe |댈러스 3, 워싱턴 DC 2, 첸나이 1 |
| Intercloud |프랑크푸르트 1, 프랑크푸르트 3, 암스테르담 2 |
|Megaport |멜버른 2, 시드니 2, 싱가포르 2, 암스테르담 2, 프랑크푸르트 1, 런던 3, 스톡홀름 1, 시카고 1, 댈러스 4, 산호세 2, 몬트리올 2*, 토론토 2, 워싱턴 DC 2, 홍콩 1 |
|MWS GNPP |암스테르담 2, 프랑크푸르트 3, 댈러스 3, 워싱턴 DC 2 |
|Neutrona |워싱턴 DC 2 |
| NTT |도쿄 5 |
|PacketFabric |댈러스 4, 산호세 2, 워싱턴 DC 2 |
| Softbank |도쿄 4* |
| SES Networks |워싱턴 DC 2 |
|Tata |첸나이 1, 홍콩 1 | 
|Telia |스톡홀름 1, 오슬로 2* |
|Telstra |멜버른 2, 시드니 2 |
|Tokai |도쿄 3| 
|Verizon |시드니 2, 암스테르담 2, 프랑크푸르트 1, 댈러스 3, 산호세 2, 워싱턴 DC 2 |
| Zayo |워싱턴 DC 2, 댈러스 3, 토론토 2, 몬트리올 2* |

* = 근일 공개

## 가격
{: #connect-pricing}

가격 정보는 [가격 문서](/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-direct-link-connect)를 참조하십시오.
