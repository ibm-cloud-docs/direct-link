---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: overview, connectivity, private network, site-to-site, Exchange, Connect, Dedicated, Hosting, OSI, Layer-3, partners, NNI, latency, backbone

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Visão geral das ofertas do Direct Link
{: #overview-of-direct-link-offerings}

As ofertas do {{site.data.keyword.cloud}} Direct Link fornecem conectividade de uma origem externa para
uma rede privada do IBM Cloud do cliente. O Direct Link pode ser visualizado como uma alternativa para uma solução
VPN entre sites tradicional, projetada para clientes que precisam de uma conectividade mais consistente e de
maior rendimento entre uma rede remota e seus ambientes do IBM Cloud. Quatro tipos de conexões estão disponíveis:
 
 * O **IBM Cloud Direct Link Exchange** permite que os clientes utilizem um provedor do Exchange para entregar conectividade ao seu IBM Cloud. Um provedor do Exchange é um provedor de co-locação ou do data center que já está conectado à rede do {{site.data.keyword.cloud_notm}}, usando links de alta capacidade de múltiplos locatários (também conhecidos como uma _interface de rede para rede_ ou NNI). Os clientes normalmente podem comprar um circuito virtual nesse
provedor, trazendo conectividade a um custo reduzido, porque a conectividade física do
{{site.data.keyword.cloud_notm}} para o provedor Exchange já está em vigor, compartilhada entre outros clientes.
 
 * O **IBM Cloud Direct Link Connect** permite que os clientes utilizem uma conexão por meio de nossos parceiros da Transportadora que possuam e operem uma rede baseada em recurso. Um provedor do Connect é um provedor de serviços de rede (NSP) que já está conectado à rede do {{site.data.keyword.cloud_notm}}, usando links de alta capacidade de múltiplos locatários (também conhecidos como _interface de rede para rede_ ou NNI). Os clientes geralmente podem comprar um circuito virtual nesse provedor, levando a conectividade a um custo reduzido, porque a conectividade física do {{site.data.keyword.cloud_notm}} para o provedor do Connect já está em vigor, compartilhada entre outros clientes.
 
 * O **IBM Cloud Direct Link Dedicated** permite que os clientes finalizem uma conexão cruzada baseada em fibra, de locatário único na rede do {{site.data.keyword.cloud_notm}}. Essa oferta pode ser utilizada por clientes com instalações de co-locação adjacentes a PoPs e data centers do IBM Cloud, bem como provedores de serviços de rede que fornecem circuitos para instalações do cliente ou outros data centers.
 
 * O **IBM Cloud Direct Link Dedicated Hosting** fornece conectividade semelhante ao {{site.data.keyword.cloud_notm}} Direct Link Dedicated, mas o ponto de conexão é adjacente a um data center do {{site.data.keyword.cloud_notm}}, que melhora a latência para casos de uso de maior desempenho. O {{site.data.keyword.cloud_notm}} oferece uma variedade de serviços de co-locação customizáveis com essa solução.
  
O serviço do {{site.data.keyword.cloud_notm}} Direct Link é um serviço roteado, do OSI de Camada 3. Ele oferece uma conexão direta
com o backbone de rede privada do {{site.data.keyword.cloud_notm}}, com
baixa latência e velocidades de até 10 Gbps.
Para maior flexibilidade na criação desta conectividade de Camada 3, o {{site.data.keyword.cloud_notm}} Direct Link permite que os clientes utilizem:
 * IP dual para hosts remotos
 * NAT
 * Tunelamento para BYOIP
 
 Para obter descrições detalhadas de cada oferta, consulte [Sobre o IBM Cloud Direct Link](/docs/infrastructure/direct-link?topic=direct-link-about-ibm-cloud-direct-link).
