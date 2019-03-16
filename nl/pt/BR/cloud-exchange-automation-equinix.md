---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-02-19"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:note: .note}
{:download: .download}


# Fornecimento do IBM Cloud Direct Link Exchange for Equinix
{: #provisioning-ibm-cloud-direct-link-exchange-for-equinix}

Se o pedido do IBM Cloud Direct Link for para o
Equinix Cloud Exchange, o fornecimento do serviço será totalmente automatizado, o que significa que você poderá fazer um pedido
para uma conexão do IBM Cloud Direct Link (Equinix) sem abrir um chamado de suporte IBM.

Atualmente, os recursos de automação são limitados ao Equinix Cloud Exchange. Em liberações subsequentes, a automação
será ativada para outros provedores.
{:note}

## Pré-requisitos

Para usar o recurso de pedido automatizado, suas VLANs privadas devem ser associadas a um VRF na rede privada do
IBM Cloud. Se esse
requisito não for atendido, um chamado de suporte IBM será gerado quando você fizer o pedido por meio do portal do cliente.

## Etapas para o pedido e o fornecimento

**Etapa 1:**

Siga as etapas de 1 a 7 das
[etapas
regulares do pedido do Cloud Exchange](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange).

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

