---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-06-12"

keywords: provisioning, Exchange, order, support, ticket, diverse, virtual circuit, parameters, Terms and Conditions, legacy, customer, portal

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

# Provisionando o IBM Cloud Direct Link Exchange por meio do portal do cliente anterior
{: #provisioning-ibm-cloud-direct-link-exchange-legacy}

Esta página informa a você como pedir o serviço do {{site.data.keyword.cloud}} Direct Link Exchange, por meio do portal do cliente anterior do {{site.data.keyword.cloud_notm}}.
{: shortdesc}

Se o pedido do {{site.data.keyword.cloud_notm}} Direct Link for para o Equinix Cloud Exchange, o fornecimento de serviço será totalmente automatizado, o que significa que é possível [fazer um pedido para uma conexão do IBM Cloud Direct Link (Equinix) sem abrir um chamado de suporte IBM](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix-legacy) conforme descrito em um documento relacionado.

Atualmente, os recursos de automação são limitados ao Equinix Cloud Exchange. Em liberações subsequentes, a automação será ativada para outros provedores.
{:note}

## Pré-requisitos
{: #cloud-exchange-prerequisites-legacy}

Para usar o recurso de automação, suas VLANs privadas devem ser associadas a um VRF na rede privada do {{site.data.keyword.cloud_notm}}. Se esse
requisito não for atendido, um chamado de suporte IBM será gerado quando você fizer o pedido por meio do portal do cliente.

 * [Como pedir o Cloud Exchange](#how-to-order-cloud-exchange-no-equinix-legacy)
 * [Como pedir o Cloud Exchange for Equinix](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix-legacy)

## Como pedir o Cloud Exchange
{: #how-to-order-cloud-exchange-no-equinix-legacy}

Para fornecer uma conexão do IBM Cloud Direct Link Exchange, conclua as etapas a seguir:

**Etapa 1:**

Efetue login em sua conta do cliente no [portal do
cliente![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/).

**Etapa 2:**

Na guia **Rede**, selecione **Direct Link-> Exchange**, para abrir uma página que
mostra as conexões existentes do IBM Cloud Direct Link, se houver.

![Etapa 2](/images/Equinix-Step2.png)

**Etapa 3:**

Depois de clicar no botão **Pedir o Direct Link Exchange** na parte superior da página, você
verá o formulário de pedido no qual pode inserir os parâmetros de configuração para a conexão do IBM Cloud Direct Link
Exchange.

![Etapa 3](/images/Equinix-Step3.png)

** Etapa 3A: **

Opcionalmente, se as portas Diversas estiverem acessíveis e você tiver provisionado anteriormente o primeiro Circuito Virtual, você verá uma tela semelhante à seguinte, mostrando duas portas, nas quais é possível selecionar seu segundo Circuito Virtual.

![2-port-image](/images/exchange-2-ports-image.png)

**Etapa 4:**

No formulário de ordem, insira os parâmetros a seguir para configurar o Direct Link:
  * Insira o nome de conexão do IBM Cloud Direct Link.
  * Na lista, selecione o local de PoP no qual você deseja estabelecer a conexão do IBM Cloud Direct Link.
  * Na lista, selecione o nome do provedor do Cloud Exchange que você preferir.
  * Selecione a Velocidade do link necessária para a conexão.
  * Selecione a opção de roteamento necessária para a conexão.
  * Insira um número do ASN do intervalo especificado na caixa de informações para as trocas do BGP.

**Etapa 5:**

Conforme você seleciona ou insere esses valores, é possível ver um encargo mensal aproximado no painel do lado esquerdo.

![Etapa 4-5](/images/Equinix-Step4-5.png)

**Etapa 6.**

Depois que você fornece os valores de entrada, a próxima tela de UI mostra a precificação mensal real com base nas opções selecionadas.

**Etapa 7:**

Deve-se **CONCORDAR** com os Termos e condições antes de poder fazer o pedido do IBM Cloud Direct Link. Leia os Termos e condições atentamente porque eles contêm informações técnicas importantes que devem ser entendidas antes de continuar. 

Se os termos e condições não forem aceitos, um chamado de suporte IBM será gerado ao colocar o pedido.
{:note}

As figuras a seguir mostram as telas que você pode ver com base em sua seleção nessa etapa.

A figura a seguir mostra a tela Termos e condições:

![Etapa 7](images/Equinix-Step7.png)

A figura a seguir mostra a tela que poderá ser exibida se você não concordar com os Termos e condições ao fazer o pedido. A tela mostra o número de chamado gerado:

![Etapa 7 acordar](/images/Equinix-Step7-NoAgree.png)

A figura a seguir mostra um exemplo do chamado que está sendo aberto:

![Etapa 7 chamado](/images/Equinix-Step7-NoAgree-Ticket.png)

**Etapa 8:**

Após concordar com os Termos e condições ao fazer o pedido, um chamado de suporte IBM será gerado após o pedido para continuar com o fornecimento do serviço. O número do chamado será exibido na UI depois da execução do pedido. 

![Etapa NE1](/images/Non-Equinix-Step1.png)

**Etapa 9:**

Ao clicar no número do chamado na mensagem, é possível ver os detalhes do chamado.

![Etapa NE2](/images/Non-Equinix-Step2.png)
