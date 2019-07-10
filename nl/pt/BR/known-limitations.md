---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-02-26"

keywords: limitations, VRF, account-to-account, VPN, BGP, fees, contract, Exchange, Connect, Dedicated, Hosting

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Limitações conhecidas
{: #known-limitations}

Primeiro, essa seção abrange as limitações que se aplicam a todas as três ofertas do {{site.data.keyword.cloud}} Direct Link e, em seguida, detalha algumas limitações de cada oferta
individualmente.

## Limitações gerais do IBM Cloud Direct Link
{: #general-ibm-cloud-direct-link-limitations}

 * Cada conexão do IBM Cloud Direct Link requer um pedido exclusivo. Se você precisar de múltiplas conexões, abra um pedido
do IBM Cloud Direct Link para cada conexão.
 * A rede de serviços do {{site.data.keyword.BluSoftlayer_notm}} não é
acessível diretamente de suas redes remotas.
 * O {{site.data.keyword.BluSoftlayer_notm}} não permitirá que os clientes retornem o tráfego
entre seus sites remotos e o backbone do {{site.data.keyword.BluSoftlayer_notm}}. O produto IBM Cloud Direct Link se
destina a deixar suas redes remotas se comunicarem privadamente com a infraestrutura do seu {{site.data.keyword.BluSoftlayer_notm}}.
 * O IBM Cloud Direct Link requer que você use uma instância do VRF (Virtual Routing and Forwarding).
 * O VRF não é totalmente compatível com os serviços de VPN do {{site.data.keyword.BluSoftlayer_notm}} SSL e do IPSec.
 * O VRF não é compatível com a ampliação de VLAN conta a conta do
{{site.data.keyword.BluSoftlayer_notm}}.
 * O IBM Cloud Direct Link requer o BGP para estabelecer as rotas para uma rede remota do cliente.
 * Mudanças na infraestrutura do IBM Cloud Direct Link devem ser feitas entre 8h e 17h, fuso horário central dos EUA.
 
## Limitações do IBM Cloud Direct Link Exchange e do Direct Link Connect
{: #ibm-cloud-direct-link-exchange-and-direct-link-connect-limitations}

 * Os clientes são responsáveis por quaisquer taxas associadas ao acesso ao POP de uma rede remota e
por quaisquer taxas incorridas com o provedor Cloud Exchange.
 * O {{site.data.keyword.BluSoftlayer_notm}} não colocará nenhum equipamento do cliente
junto de nossos POPs de rede. Os clientes devem trabalhar com seus provedores para determinar se precisam colocar algum equipamento na instalação em que o PoP de rede do {{site.data.keyword.BluSoftlayer_notm}} existe.
 * A disponibilidade do Direct Link Cloud Exchange varia entre os locais. Os clientes podem entrar em
contato com seu gerente de contas do IBM Cloud para confirmar disponibilidade atual ou futura.
 
## Limitações do IBM Cloud Direct Link Dedicated
{: #ibm-cloud-direct-link-dedicated-limitations}

 * As taxas do {{site.data.keyword.BluSoftlayer_notm}} para o IBM Cloud Direct Link Dedicated cobrem o custo de
rescisão da porta na infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}. Os clientes são responsáveis por quaisquer taxas associadas ao acesso ao PoP de uma rede remota e por quaisquer
conexões cruzadas necessárias no recurso PoP.  O {{site.data.keyword.BluSoftlayer_notm}} não solicitará
uma conexão cruzada em nome de nenhum cliente.
 * O {{site.data.keyword.BluSoftlayer_notm}} não colocará nenhum equipamento do cliente junto de
nossos PoPs de rede. Os clientes devem trabalhar com seus provedores para determinar se precisam colocar algum equipamento na instalação em que o PoP de rede do {{site.data.keyword.BluSoftlayer_notm}} existe.

## Limitações do IBM Cloud Direct Link Dedicated Hosting
{: #ibm-cloud-direct-link-dedicated-hosting-limitations}

 * O IBM Cloud Direct Link Dedicated Hosting requer um contrato específico entre
{{site.data.keyword.BluSoftlayer_notm}} e o cliente. Este contrato define os termos e as condições
para o produto, o preço para o ambiente de colocação e o termo de compromisso para os
serviços. Um contrato de 6, 9 ou 12 meses é necessário.
 * A conectividade do provedor é limitada aos provedores On-Net do datacenter
selecionado.
