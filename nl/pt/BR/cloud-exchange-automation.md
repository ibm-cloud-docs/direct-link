---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-11"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Passo a passo: peça um IBM Cloud Direct Link Exchange

Esta página informa como pedir o serviço do IBM Cloud Direct Link Exchange. Se o pedido do IBM Cloud Direct Link for para o
Equinix Cloud Exchange, o fornecimento de serviço será totalmente automatizado, o que significa que você poderá fazer um pedido
para uma conexão do IBM Cloud Direct Link (Equinix) sem abrir um chamado de suporte IBM.

**(Nota: atualmente os recursos de automação são limitados aos Equinix Cloud Exchange. Em liberações subsequentes, a
automação será ativada para outros provedores.)**

## Pré-requisitos

Para usar o recurso de automação, suas VLANs privadas devem ser associadas a um VRF na rede privada do IBM Cloud. Se esse
requisito não for atendido, um chamado de suporte IBM será gerado quando você fizer o pedido por meio do portal do cliente.

 * [Como pedir o Cloud Exchange](#how-to-order-cloud-exchange)
 * [Como pedir o Cloud Exchange for Equinix](#how-to-order-cloud-exchange-for-equinix)

## Como pedir o Cloud Exchange

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

Deve-se **CONCORDAR** com os Termos e condições antes de poder fazer o pedido do IBM Cloud Direct Link. Leia os Termos e condições atentamente porque eles contêm informações técnicas importantes que devem ser entendidas antes de continuar. **(Nota: se os Termos e condições não forem aceitos, um chamado de suporte IBM será gerado na realização do pedido.)** As figuras a seguir mostram as telas que você pode ver com base em sua seleção nessa etapa.

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

## Como pedir o Cloud Exchange for Equinix

**Etapa 1:**

Siga as etapas de 1 a 7 das etapas de pedido do Cloud Exchange acima

**Etapa 2:**

Depois de fazer o pedido, o fornecimento do IBM Cloud Direct Link é iniciado.

![Etapa 8](/images/Equinix-Step8.png)

**Etapa 3:**

É possível ver o status de sua conexão após fazer o pedido. Se a configuração for concluída no lado da IBM com êxito, você
verá o status como **Fornecido**. Se a configuração não for concluída, você verá o status como **Em
andamento**. Se a configuração tiver falhado, você verá o status como **Criação com falha**. Se a
configuração for concluída com êxito e a conexão BGP estiver ativa, você verá o status como **ATIVADO**.

![Etapa 9 Em andamento](/images/Equinix-Step9-InProgress.png)

A figura a seguir mostra os vários estados da conexão após a realização do pedido:

![Etapa 9 Ativado](/images/Equinix-Step9-UP.png)

**Etapa 4:**

Se a conexão estiver no status **Fornecido**, expanda-a clicando no **>** em frente à conexão **Nome**. Então, anote as informações de **Endereço IP do
cliente** e **Chave de serviço**. Essas serão necessárias para configurar o roteador de borda do
cliente e a chave de autorização para a configuração do lado do provedor de nuvem (Equinix), respectivamente.

![Etapa 10](/images/Equinix-Step10-Provisioned.png)

**Etapa 5:**

Para conexões no status **Fornecido**, depois de expandir a conexão clicando no **>** em frente à conexão, você verá uma mensagem de erro se houver uma incompatibilidade com a velocidade do link peer. Como a velocidade é a mesma no lado da IBM e no lado do Equinix, essa notificação de erro não será mais exibida.

![Etapa 11](/images/Equinix-Step11-PortMismatch.png)

**Etapa 6:**

Para conexões no status **Criação com falha**, um chamado de suporte IBM será gerado e detalhes
adicionais serão comunicados por meio do chamado de suporte. Ao expandir a conexão, será possível ver os detalhes do chamado de
suporte.

![Etapa 12](/images/Equinix-Step12-CreateFailed.png)

**Etapa 7:**

Para conexões em status **Fornecido**, **ATIVADO** ou
**DESATIVADO**, é possível **Excluir** a conexão clicando na coluna
**AÇÕES** ao lado da conexão.

![Etapa 13](/images/Equinix-Step13-Delete.png)

**Etapa 8:**

Para as conexões no status **Criação com falha**, é possível **Cancelar** a
conexão clicando na coluna **AÇÕES** ao lado da conexão.

