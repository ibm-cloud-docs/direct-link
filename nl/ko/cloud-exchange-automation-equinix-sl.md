---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-06-12"

keywords: provisioning, order, Exchange, Equinix, automated, status, connection, legacy, customer, portal, Softlayer

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


# 레거시 고객 포털을 통해 IBM Cloud Direct Link Exchange for Equinix 프로비저닝
{: #provisioning-ibm-cloud-direct-link-exchange-for-equinix-legacy}

이 문서에서는 IBM Cloud 레거시 고객 포털을 사용하여 Direct Link Exchange for Equinix를 프로비저닝하기 위한 단계별 지시사항을 제공합니다.
{: shortdesc}

{{site.data.keyword.cloud}} Direct Link 주문이 Equinix Cloud Exchange에 대한 주문인 경우 서비스 프로비저닝이 완전히 자동화되며, 이는 IBM 지원 티켓을 열지 않고도 {{site.data.keyword.cloud_notm}} Direct Link 연결(Equinix)을 주문할 수 있음을 의미합니다.

자동화 기능은 현재 Equinix Cloud Exchange로 제한되어 있습니다. 후속 릴리스에서는 다른 제공자도 자동화를 사용할 수 있습니다.
{:note}

## 전제조건
{: #cloud-exchange-equinix-prerequisites-legacy}

자동화된 주문 기능을 사용하려면 사설 VLAN을 {{site.data.keyword.cloud_notm}} 사설 네트워크의 VRF와 연관시켜야 합니다. 이 요구사항이 충족되지 않으면 고객 포털을 통해 주문할 때 IBM 지원 티켓이 생성됩니다.

## 주문 및 프로비저닝 단계
{: #cloud-exchange-steps-for-ordering-and-provisioning-legacy}

**단계 1:**

일반 [Cloud Exchange 주문 단계](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-legacy)에서 1 ~ 7 단계를 수행하십시오.

**단계 2:**

주문 후 IBM Cloud Direct Link 프로비저닝이 시작됩니다.

![단계 8](/images/Equinix-Step8.png)

**단계 3:**

주문 후 연결 상태를 볼 수 있습니다. IBM 측에서 구성이 완료되면 상태가 **프로비저닝됨**으로 표시됩니다. 구성이 완료되지 않으면 상태가 **진행 중**으로 표시됩니다. 구성이 실패하면 상태가 **작성 실패**로 표시됩니다. 구성이 완료되었고 BGP 연결이 작동되면 상태가 **UP**으로 표시됩니다.

![단계 9 진행 중](/images/Equinix-Step9-InProgress.png)

다음 그림에는 주문 후의 다양한 연결 상태가 표시됩니다.

![단계 9 작동됨](/images/Equinix-Step9-UP.png)

**단계 4:**

연결이 **프로비저닝됨** 상태인 경우 연결 **이름**의 앞에 있는 **>**를 클릭하여 연결을 확장하십시오. 그런 다음 **고객 IP 주소** 및 **서비스 키** 정보를 기록하십시오. 고객 IP 주소는 고객 에지 라우터를 구성하는 데 필요하며 서비스 키는 클라우드 제공자 측(Equinix) 구성을 위한 권한 키로 필요합니다.

![단계 10](/images/Equinix-Step10-Provisioned.png)

**단계 5:**

**프로비저닝됨** 상태의 연결의 경우 연결 앞에 있는 **>**를 클릭하여 연결을 확장한 후 피어 링크 속도에 불일치가 나타나면 오류 메시지가 표시됩니다. 속도가 IBM 측과 Equinix 측에서 동일하면 이 오류 알림이 더 이상 표시되지 않습니다.

![단계 11](/images/Equinix-Step11-PortMismatch.png)

**단계 6:**

**작성 실패** 상태의 연결의 경우에는 IBM 지원 티켓이 생성되고 추가 세부사항이 지원 티켓을 통해 전달됩니다. 연결을 확장하면 지원 티켓 세부사항을 볼 수 있습니다.

![단계 12](/images/Equinix-Step12-CreateFailed.png)

**단계 7:**

**프로비저닝됨**, **UP** 또는 **DOWN** 상태의 연결에서는 연결 다음에 있는 **조치** 열을 클릭하여 연결을 **삭제**할 수 있습니다.

![단계 13](/images/Equinix-Step13-Delete.png)

**단계 8:**

**작성 실패** 상태의 연결에서는 연결 다음에 있는 **조치** 열을 클릭하여 연결을 **취소**할 수 있습니다.
