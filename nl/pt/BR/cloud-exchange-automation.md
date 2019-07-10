---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: provisioning, Exchange, order, support, ticket, diverse, virtual circuit, parameters, Terms and Conditions

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

# Fornecimento do IBM Cloud Direct Link Exchange
{: #provisioning-ibm-cloud-direct-link-exchange}

Esta página informa como pedir o serviço {{site.data.keyword.cloud}} Direct Link Exchange. Se o pedido do {{site.data.keyword.cloud_notm}} Direct Link for para o Equinix Cloud Exchange, o fornecimento de serviço será totalmente automatizado, o que significa que é possível [fazer um pedido para uma conexão do IBM Cloud Direct Link (Equinix) sem abrir um chamado de suporte IBM](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix) conforme descrito em um documento relacionado.

Atualmente, os recursos de automação são limitados ao Equinix Cloud Exchange. Em liberações subsequentes, a automação será ativada para outros provedores.
{:note}

## Pré-requisitos
{: #cloud-exchange-prerequisites}

Para usar o recurso de automação, suas VLANs privadas devem ser associadas a um VRF na rede privada do {{site.data.keyword.cloud_notm}}. Se esse
requisito não for atendido, um chamado de suporte IBM será gerado quando você fizer o pedido por meio do portal do cliente.

 * [Como pedir o Cloud Exchange](#how-to-order-cloud-exchange-no-equinix)
 * [Como pedir o Cloud Exchange for Equinix](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix)

## Como pedir o Cloud Exchange
{: #how-to-order-cloud-exchange-no-equinix}

Para fornecer uma conexão do IBM Cloud Direct Link Exchange, conclua as etapas a seguir:

**Etapa 1:**

Efetue login em sua conta do cliente no [portal do
cliente![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://cloud.ibm.com/).

**Etapa 2:**

Na guia **Rede**, selecione **Direct Link-> Exchange**, para abrir uma página que
mostra as conexões existentes do IBM Cloud Direct Link, se houver.

![Etapa 2](/images/pup_exchange_list.png)

**Etapa 3:**

Depois de clicar no botão **Pedir o Direct Link Exchange** na parte superior da página, você
verá o formulário de pedido no qual pode inserir os parâmetros de configuração para a conexão do IBM Cloud Direct Link
Exchange.

![Etapa 3](/images/pup_exchange_create_default.png)

** Etapa 3A: **

Opcionalmente, se as portas Diversas estiverem acessíveis e você tiver provisionado anteriormente o primeiro Circuito Virtual, você verá uma tela semelhante à seguinte, mostrando duas portas, nas quais é possível selecionar seu segundo Circuito Virtual.

![2-port-image](/images/pup_exchange_create_ports.png)

**Etapa 4:**

No formulário de ordem, insira os parâmetros a seguir para configurar o Direct Link:
  * Insira o nome de conexão do IBM Cloud Direct Link.
  * Na lista, selecione o local no qual você deseja estabelecer a conexão do IBM Cloud Direct Link.
  * Na lista, selecione o nome do provedor do Cloud Exchange que você preferir.
  * Selecione a Velocidade do link necessária para a conexão.
  * Selecione a opção de roteamento necessária para a conexão.
  * Insira um número do ASN do intervalo especificado na caixa de informações para as trocas do BGP.

**Etapa 5:**

Conforme você seleciona ou insere esses valores, é possível ver um encargo mensal aproximado no painel do lado direito.

![Etapa 4-5](/images/pup_exchange_create_prices.png)

**Etapa 6.**

Os campos de formulário são validados conforme você fornece as entradas.
Deve-se **CONCORDAR** com os Termos e condições para que o botão "Criar" seja ativado.

**Etapa 7:**

Após concordar com os Termos e condições ao fazer o pedido, um chamado de suporte IBM será gerado após o pedido para continuar com o fornecimento do serviço. O número do chamado será exibido na UI depois da execução do pedido. 

![Etapa NE1](/images/pup_exchange_ticket_notification.png)

**Etapa 8:**

Ao clicar no número do chamado na mensagem, é possível ver os detalhes do chamado.

![Etapa NE2](/images/pup_exchange_ticket_details.png)
