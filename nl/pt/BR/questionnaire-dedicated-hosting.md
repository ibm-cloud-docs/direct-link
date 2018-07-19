---

copyright:
  years: 2018
lastupdated: "2018-06-11"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Questionário Dedicado do IBM Cloud Direct Link

Obrigado por abrir uma solicitação para o IBM Cloud Direct Link Dedicated Hosting. Para finalizar a sua solicitação, gostaríamos de reunir algumas informações adicionais de você.  É possível falar com um engenheiro a qualquer momento durante o processo de questionário.  Após você ter concluído o questionário, ele será revisado por nossa equipe de Engenharia de design de nuvem e escalado para a Engenharia de rede para implementação.

## Confirmações

1. As taxas descritas neste questionário cobrem o custo da rescisão do serviço na infraestrutura de rede do IBM Cloud. Os custos de colocação, incluindo gabinetes, conexões cruzadas, etc. incluem taxas mensais e não recorrentes que são descritas separadamente como parte de um contrato de colocação.

2. O IBM Cloud Direct Link Dedicated Hosting fornece conexões cruzadas de fibra de 1 Gbps ou 10 Gbps na rede privada do IBM Cloud. Será necessário fornecer um roteador ou um comutador de Camada 3 que possa suportar uplinks de fibra de modo único (SMF). O tempo de implementação pode variar com base em seu provedor de circuito, o tempo de implementação típico para esse serviço é de 30 a 60 dias.

3. O Direct Link Dedicated Hosting requer a utilização de uma instância VRF (Virtual Routing and Forwarding). Isso permite que o cliente defina seus próprios endereços IP remotos para uso em sua rede remota; no entanto, deve-se estar ciente de que, se você utilizar a rede 10.x.x.x, ainda não poderá se sobrepor com seus hosts dentro do IBM Cloud nem com a rede de serviços do SIBM Cloud (10.0.0.0/14, 10.198.0.0/15 e 10.200.0.0/14). A transição de sua conta para um VRF requererá uma breve indisponibilidade de rede privada conforme cada VLAN for migrada para a nova configuração.  A equipe de Engenharia de rede trabalhará com você para definir uma janela para essa atividade.

4. O VRF altera o comportamento de SSL, PPTP e VPN IPsec do IBM Cloud. Eles geralmente funcionam quando a conexão VPN é feita no mesmo local do data center que os recursos de cálculo que estão sendo acessados, mas não permitem acesso globalmente. Como alternativa, é possível usar o próprio Direct Link para gerenciamento de seus servidores ou executar sua própria solução VPN (como um Vyatta) que pode ser configurada com tipos diferentes de VPN. 

5. O Direct Link Dedicated Hosting requer BGP para implementar rotas para a rede remota de um cliente. O IBM Cloud não implementará filtros nas propagandas feitas no IBM Cloud. O IBM Cloud anunciará todas as sub-redes privadas designadas à sua conta. Os clientes precisarão gerenciar adequadamente as propagandas recebidas no IBM Cloud.

6. O IBM Cloud fornece uplinks duais, um para cada um dos roteadores de conexão cruzada do IBM Cloud, para permitir que os clientes estabeleçam conectividade redundante. Isso é realizado nos roteadores do cliente por meio de sessões BGP, alavancando recursos do ECMP ou simplesmente ponderando as conexões.

7. A rede de serviços do IBM Cloud não será acessível diretamente por meio de suas redes do Dedicated Hosting ou remotas.

8. O IBM Cloud não permitirá que você volte a transportar o tráfego entre seus sites remotos por meio do backbone do IBM Cloud. O serviço do Direct Link foi projetado para que suas redes remotas possam se comunicar privadamente com sua infraestrutura do IBM Cloud.

9. O IBM Cloud oferece o Direct Link com roteamento Local ou Global. Confirme qual pacote de roteamento você requer e que você concorda com os planos de largura da banda associados a esses pacotes listados no link a seguir: ibm.biz/DirectLink-Docs.

10. Especifique quanto tráfego você planeja enviar por push pelo Direct Link e para quais data centers do IBM Cloud você planeja enviar esse tráfego por push.

11. Se você não estiver comprando serviços de colocação por meio do IBM Cloud, será responsável por pedir e pagar pelas conexões cruzadas entre seu ambiente e o IBM Cloud. Uma vez conectado, forneceremos uma Carta de Autorização (LOA) detalhando nossa aprovação de sua conexão e do local de conexão.

12. Confirme se você concorda com a precificação a seguir para o Direct Link:
 * 1 Gbps: _PRECIFICAÇÃO COM BASE EM LOCAL_ 
* 2 Gbps: _PRECIFICAÇÃO COM BASE EM LOCAL_
* 5 Gbps: _PRECIFICAÇÃO COM BASE EM LOCAL_
* 10 Gbps: _PRECIFICAÇÃO COM BASE EM LOCAL_
* Roteamento global opcional
