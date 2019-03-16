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
{:download: .download}

# Visão geral das ofertas do Direct Link
{ #overview-of-direct-link-offerings}

As ofertas do {{site.data.keyword.cloud}} Direct Link fornecem conectividade de uma origem externa para
uma rede privada do IBM Cloud do cliente. O Direct Link pode ser visualizado como uma alternativa para uma solução
VPN entre sites tradicional, projetada para clientes que precisam de uma conectividade mais consistente e de
maior rendimento entre uma rede remota e seus ambientes do IBM Cloud. Quatro tipos de conexões estão disponíveis:
 
 * O **IBM Cloud Direct Link Exchange** permite que os clientes utilizem um provedor Exchange para
fornecer conectividade com o IBM Cloud. Um provedor Exchange é um provedor de operadora ou de rede que já está conectado à rede do
IBM Cloud, usando links de múltiplos locatários de alta capacidade. Os clientes normalmente podem comprar um circuito virtual nesse
provedor, trazendo conectividade a um custo reduzido, porque a conectividade física do
{{site.data.keyword.BluSoftlayer_notm}} para o provedor Exchange já está em vigor, compartilhada entre outros clientes.
 
 * O **IBM Cloud Direct Link Connect** permite que os clientes utilizam uma conexão por meio de
nossos parceiros que possuem e operam uma rede baseada em recurso. Com o IBM Cloud Direct Link Connect, a IBM e o parceiro se
conectam aos clientes na Camada 2 e 3 por meio de NNIs duais de camada 2 com 10 G.
 
 * O **IBM Cloud Direct Link Dedicated** permite que os clientes finalizem uma conexão de fibra cruzada
dedicada de modo único em sua própria rede privada do IBM Cloud.
 
 * O **IBM Cloud Direct Link Dedicated Hosting** fornece conectividade similar ao IBM Cloud Direct Link
Dedicated, mas o ponto de conexão é adjacente a um data center do {{site.data.keyword.BluSoftlayer_notm}}, que melhora a
latência para casos de uso de alto desempenho. O IBM Cloud oferece com esta solução uma variedade de serviços de colocação customizáveis.
  
O serviço do IBM Cloud Direct Link é um serviço OSI de Camada 3 roteado. Ele oferece uma conexão direta
com o backbone de rede privada do {{site.data.keyword.BluSoftlayer_notm}}, com
baixa latência e velocidades de até 10 Gbps.
Para maior flexibilidade na criação desta conectividade de camada 3, o IBM Cloud Direct Link permite que os clientes utilizem:
 * IP dual para hosts remotos
 * NAT
 * Tunelamento para BYOIP
 
 Para obter descrições detalhadas de cada oferta, consulte [Sobre o IBM Cloud Direct Link](/docs/infrastructure/direct-link?topic=direct-link-about-ibm-cloud-direct-link).
