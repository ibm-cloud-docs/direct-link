---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: provisioning, order, Exchange, Equinix, automated, status, connection

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


# IBM Cloud Direct Link Exchange for Equinix 프로비저닝
{: #provisioning-ibm-cloud-direct-link-exchange-for-equinix}

{{site.data.keyword.cloud}} Direct Link 주문이 Equinix Cloud Exchange에 대한 주문인 경우 서비스 프로비저닝이 완전히 자동화되며, 이는 IBM 지원 티켓을 열지 않고도 {{site.data.keyword.cloud_notm}} Direct Link 연결(Equinix)을 주문할 수 있음을 의미합니다.

자동화 기능은 현재 Equinix Cloud Exchange로 제한되어 있습니다. 후속 릴리스에서는 다른 제공자도 자동화를 사용할 수 있습니다.
{:note}

## 전제조건
{: #cloud-exchange-equinix-prerequisites}

자동화된 주문 기능을 사용하려면 사설 VLAN을 {{site.data.keyword.cloud_notm}} 사설 네트워크의 VRF와 연관시켜야 합니다. 이 요구사항이 충족되지 않으면 고객 포털을 통해 주문할 때 IBM 지원 티켓이 생성됩니다.

## 주문 및 프로비저닝 단계
{: #cloud-exchange-steps-for-ordering-and-provisioning}

**단계 1:**

일반 [Cloud Exchange 주문 단계](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange)에서 1 ~ 7 단계를 수행하십시오.

**단계 2:**

주문 후 IBM Cloud Direct Link 프로비저닝이 시작됩니다.

주문 후 연결 상태를 볼 수 있습니다. IBM 측에서 구성이 완료되면 상태가 **프로비저닝됨**으로 표시됩니다. 구성이 완료되지 않으면 상태가 **진행 중**으로 표시됩니다. 구성이 실패하면 상태가 **작성 실패**로 표시됩니다. 구성이 완료되었고 BGP 연결이 작동되면 상태가 **UP**으로 표시됩니다.

![단계 9 진행 중](/images/pup_exchange_equinix_inProgress.png)

**단계 3:**

연결이 **프로비저닝됨** 상태인 경우 **<connection_name>** 링크를 클릭하여 연결 이름을 클릭하십시오. 세부사항 페이지로 이동해야 합니다.

![단계 10](/images/pup_exchange_equinix_provisioned.png)

다음 그림에는 주문 후의 다양한 연결 상태가 표시됩니다.

![단계 9 작동됨](/images/pup_exchange_equinix_up.png)

**단계 4:**

**고객 IP 주소** 및 **서비스 키** 정보를 기록하십시오. 고객 IP 주소는 고객 에지 라우터를 구성하는 데 필요하며 서비스 키는 클라우드 제공자 측(Equinix) 구성을 위한 권한 키로 필요합니다.

![단계 9 작동됨](/images/pup_exchange_equinix_provisioned_details.png)

**단계 5:**

**프로비저닝됨** 상태의 연결의 경우 **<connection_name>**을 클릭하여 연결 이름을 클릭한 후 피어 링크 속도에 불일치가 나타나면 오류 메시지가 표시됩니다. 속도가 IBM 측과 Equinix 측에서 동일하면 이 오류 알림이 더 이상 표시되지 않습니다.

![단계 11](/images/pup_exchange_equinix_provisioned_details_portSpeedMismatch.png)

**단계 6:**

**작성 실패** 상태의 연결의 경우에는 IBM 지원 티켓이 생성되고 추가 세부사항이 지원 티켓을 통해 전달됩니다. 연결을 확장하면 지원 티켓 세부사항을 볼 수 있습니다.

![단계 12](/images/pup_exchange_equinix_list_createFailed.png)

**단계 7:**

**프로비저닝됨**, **UP** 또는 **DOWN** 상태의 연결에서는 연결 옆에 있는 **조치** 열의 오버플로우를 클릭하여 연결을 **삭제**할 수 있습니다.

![단계 13](/images/pup_exchange_equinix_list_delete.png)

**단계 8:**

**작성 실패** 상태의 연결에서는 연결 다음에 있는 **조치** 열을 클릭하여 연결을 **취소**할 수 있습니다.

![단계 14](/images/pup_exchange_equinix_list_delete.png)
