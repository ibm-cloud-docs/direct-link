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

# Peça o IBM Cloud Direct Link

Ao se preparar para pedir o tipo de IBM Cloud Direct Link que melhor se adequa às suas necessidades, é possível seguir
os links abaixo (ou apenas rolar este documento) para ver uma visão geral do processo. Quando estiver pronto para fazer seu
pedido, será possível localizar as instruções passo a passo que o levarão pelo processo do pedido, em nossa série de documentos "passo a
passo".

* [Como pedir o IBM Cloud Direct Link Exchange](how-to-order.html#how-to-order-ibm-cloud-direct-link-exchange)
* [Como pedir o IBM Cloud Direct Link Connect](how-to-order.html#how-to-order-ibm-cloud-direct-link-connect)
* [Como pedir o IBM Cloud Direct Link Dedicated](how-to-order.html#how-to-order-ibm-cloud-direct-link-dedicated)
* [Como pedir o IBM Cloud Direct Link Dedicated Hosting](how-to-order.html#how-to-order-ibm-cloud-direct-link-dedicated-hosting)

## Como pedir o IBM Cloud Direct Link Exchange

 * Verifique os recursos do provedor de rede para atingir o PoP e a conexão cruzada apropriados para o provedor associado do Cloud Exchange.
 * Use o [Portal do cliente ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/) para abrir uma solicitação do IBM Cloud Direct Link Exchange e preencha as informações solicitadas. (A assistência dos engenheiros de vendas da IBM pode ser solicitada). 
Se você usar o provedor Equinix, o processo de pedido e de fornecimento será
[totalmente automatizado](cloud-exchange-automation.html).
 * Entre em contato com o fornecedor do Exchange e negocie a conectividade para o seu câmbio.
 * Peça a conectividade entre o seu provedor de rede e o provedor Exchange.
 * Peça um "circuito virtual" por meio do provedor do Exchange e consulte o ID de chamado da solicitação do
{{site.data.keyword.BluSoftlayer_notm}} IBM Cloud Direct Link como o seu "ID de solicitação" ou "ID de
autorização"
 * A designação de IP na infraestrutura de rede do {{site.data.keyword.BluSoftlayer_notm}} será concluída dentro de três dias úteis após a conclusão da solicitação de circuito virtual.

## Como pedir o IBM Cloud Direct Link Connect

 * Verifique os recursos do provedor de rede para atingir o PoP e a conexão cruzada apropriados no provedor Connect associado.
 * Use o [Portal do cliente ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/) para abrir uma solicitação do IBM Cloud Direct Link Connect e preencha as informações solicitadas. (A assistência dos engenheiros de vendas da IBM pode ser solicitada). 
 * Entre em contato com o fornecedor do Connect e negocie a conectividade para o seu câmbio.
 * Peça a conectividade entre o seu provedor de rede e o provedor Connect.
 * Peça um "circuito virtual" por meio do provedor Connect e consulte o ID de chamado da solicitação do IBM Cloud Direct Link do {{site.data.keyword.BluSoftlayer_notm}} como o seu "ID de solicitação" ou "ID de autorização"
 * A designação de IP na infraestrutura de rede do {{site.data.keyword.BluSoftlayer_notm}} será concluída dentro de três dias úteis após a conclusão da solicitação de circuito virtual.

## Como pedir o IBM Cloud Direct Link Dedicated

 * Verifique os recursos do provedor de rede para atingir o PoP e a conexão cruzada apropriados para o ambiente do {{site.data.keyword.BluSoftlayer_notm}}.
 * Abra uma solicitação do IBM Cloud Direct Link Dedicated e conclua as informações solicitadas. (A assistência dos engenheiros de vendas da IBM pode ser solicitada).
 * O {{site.data.keyword.BluSoftlayer_notm}} fornece a Carta de autorização (LOA) para a conexão.
 * Confirme que o seu circuito atingiu o PoP e que foi concluído pela operadora.
 * Peça a conexão cruzada usando as informações do {{site.data.keyword.BluSoftlayer_notm}} CFA (Customer Facility Assignment) na LOA, o que geralmente leva entre 2 e 10 dias úteis para conclusão. (Esse intervalo de tempo depende do fornecedor da instalação e do tipo de prioridade de pedido que é colocada pelo cliente). Esse processo inclui a configuração da correção para a porta de rescisão do {{site.data.keyword.BluSoftlayer_notm}}.
 * Forneça a {{site.data.keyword.BluSoftlayer_notm}} o aviso de conclusão de conexão cruzada do provedor de instalação no chamado do portal do {{site.data.keyword.BluSoftlayer_notm}}.
 * O {{site.data.keyword.BluSoftlayer_notm}} verificará a eficácia do aviso de conclusão e pedirá que a correção seja feita na LOA/CFA para o roteador de conexão cruzada (XCR) e outros mecanismos.
 * Sua designação do IP na infraestrutura de rede do {{site.data.keyword.BluSoftlayer_notm}} será concluída dentro de três dias úteis após a conexão cruzada ser concluída.

## Como pedir o IBM Cloud Direct Link Dedicated Hosting

 * Identifique seus requisitos de colocação e de conectividade e trabalhe com a equipe de vendas da IBM para finalizar e assinar um contrato e um anexo técnico.
 * O {{site.data.keyword.BluSoftlayer_notm}} executa um pedido de construção com o provedor de colocação para o ambiente e os serviços solicitados. A implementação geralmente é concluída dentro de 30 dias de quando o pedido de construção foi feito.
 * Quando a construção de seu compartimento de colocação estiver concluída, o processo de interconexão entre seu compartimento
de colocação e o mecanismo XCR do ambiente POD do {{site.data.keyword.BluSoftlayer_notm}} seguirá o processo do IBM
Cloud Direct Link Dedicated mostrado anteriormente, iniciando na etapa 3.
