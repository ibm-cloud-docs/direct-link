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

Obrigado por abrir uma solicitação para o IBM Cloud Direct Link Dedicated. Para finalizar a sua solicitação, gostaríamos de reunir algumas informações adicionais de você.  É possível falar com um engenheiro a qualquer momento durante o processo de questionário.  Após você ter concluído o questionário, ele será revisado por nossa equipe de Engenharia de design de nuvem e escalado para a Engenharia de rede para implementação.

## Você reconhece e concorda com os itens a seguir?

1. Cada conexão do Direct Link requer um pedido exclusivo. Se você requerer múltiplas conexões, abra pedidos separados do Direct Link para cada conexão.

2. As taxas para o seu serviço Direct Link Connect cobrem o custo de rescisão de serviço na infraestrutura do IBM Cloud. 

 * Os Serviços de infraestrutura são faturados antecipadamente e começam na aceitação do seu pedido; no entanto, devido à natureza do IBM Cloud Direct Link, o faturamento do serviço Direct Link começará no início de uma sessão do Protocolo de Roteamento de Borda (BGP) com o IBM Cloud ou 30 dias após a chave de serviço ser fornecida ao cliente. 

 * O faturamento é interrompido após:
   * Um cliente solicita que um circuito seja excluído **e** 
   * O Exchange Provider ou o Network Service Provider desprovisionou o circuito.
  * Para obter mais informações, consulte **Seção 5 - Encargos** no Contrato de Serviços de nuvem no link a seguir: [ibm.biz/service-agreement](ibm.biz/service-agreement)

3. Ao solicitar o serviço do Direct Link, você será responsável por quaisquer taxas associadas ao acesso ao Ponto de Presença (PoP) de sua rede remota e por qualquer conexão cruzada necessária dentro do recurso PoP. Se o seu provedor exigir que um roteador ou outro dispositivo esteja fisicamente no PoP, você também será responsável pelos custos associados à instalação desse equipamento. 

4. O IBM Cloud não solicitará uma conexão cruzada em nome de um cliente.

5. O IBM Cloud não colocará nenhum equipamento do cliente em nossos POPs de rede. Nós aceitamos apenas 'conexões cruzadas', que são uma Ethernet de fibra (somente Fibra de Modo Único, óticas de 1 Gig-LX ou 10 Gig-LR de 1310 nm) executada por meio de seu compartimento ou provedor. Nós não aceitamos T1s, DS3s, ISDN, linha POTs, etc. Será necessário trabalhar com seu provedor para determinar se você precisa ou não colocar qualquer equipamento na mesma instalação em que o PoP de rede do IBM Cloud existe.

6. O serviço Direct Link é fornecido de tal maneira que o link e o roteador IBM Cloud no qual ele finaliza são ambos pontos únicos de falha (SPOF). Se desejar obter redundância por meio do serviço do Direct Link, será necessário solicitar duas conexões em um local do Direct Link com um roteador secundário ou finalizar links em dois PoPs do IBM Cloud separados.

7. A rede de serviços do IBM Cloud não será acessível por meio de suas redes remotas diretamente. Se essa capacidade mudar no futuro, nós o notificaremos.

8. O IBM Cloud não permitirá que os clientes voltem a transportar o tráfego entre os seus sites remotos por meio do backbone do IBM Cloud. O produto Direct Link é destinado às suas redes remotas para poder se comunicar privadamente com sua infraestrutura do IBM Cloud.

9. Depois de ter confirmado que seu circuito atingiu o PoP e foi concluído pela operadora, será necessário pedir a conexão cruzada com o IBM Cloud XCR (roteador de conexão cruzada) que geralmente leva entre 2 a 10 dias úteis para ser concluído. Isso inclui a correção até a porta de finalização da SoftLayer. Depois de concluído, será solicitado que você forneça ao IBM Cloud o aviso de conclusão de conexão cruzada do provedor de recursos. A volta do IP na infraestrutura de rede do IBM Cloud será concluída dentro de 3 dias úteis após a conclusão da conexão cruzada.

10. O IBM Cloud Direct Link Dedicated requer a utilização de uma instância VRF (Virtual Routing and Forwarding). Isso permite que o cliente defina seus próprios endereços IP remotos para uso em sua rede remota; no entanto, deve-se estar ciente de que, se você utilizar a rede 10.x.x.x, ainda não poderá se sobrepor com seus hosts dentro do IBM Cloud nem com a rede de serviços do IBM Cloud (10.0.0.0/14, 10.198.0.0/15 e 10.200.0.0/14). A transição de sua conta para um VRF requererá uma breve indisponibilidade de rede privada conforme cada VLAN for migrada para a nova configuração. A equipe de Engenharia de rede trabalhará com você para definir uma janela para essa atividade.

11. O VRF não é compatível com os serviços de SSL, PPTP e VPN IPSEC do IBM Cloud (SoftLayer anterior). Uma alternativa é usar o próprio Direct Link para o gerenciamento de seus servidores ou executar a sua própria solução de VPN (como um Vyatta) que pode ser configurada com tipos diferentes de VPN.  Após migrar para um VRF, a VPN de SSL geralmente funcionará quando uma conexão de VPN for feita com o mesmo local do DC no qual o cálculo está sendo acessado, mas não permitirá acesso globalmente.

12. O IBM Cloud Direct Link Dedicated requer o BGP para implementar rotas para a rede remota de um cliente. Quando o seu serviço Direct Link tiver sido implementado, o IBM Cloud anunciará todas as sub-redes privadas designadas à sua conta. O IBM Cloud não implementará filtros customizados, pré-anexação do AS-Path e preferências locais customizadas em propagandas para o peer do BGP remoto do Cliente. O IBM Cloud não implementará filtros nas propagandas recebidas para o IBM Cloud. Os clientes precisarão gerenciar adequadamente as propagandas para/do IBM Cloud por meio do roteador de borda do cliente. 

## Outras perguntas

* **Em qual PoP você deseja finalizar o Direct Link?**

* **De qual velocidade de link você precisa (1, 2, 5 ou 10 Gbps)?**

* **Você requer que o BGP MultiPath com ECMP seja definido para configurar uma conexão redundante com o IBM Cloud?**  

    _ Se sim, inclua o ID do chamado da outra conexão. Número do chamado ____________ (observe que o ECMP pode ser provisionado apenas em duas sessões no mesmo IBM Cloud XCR.  Se você desejar o ECMP, saiba que ambos os Direct Links deverão ter o mesmo roteador como destino.)_

* **Você requer Acesso de roteamento local ou global?**

    _Os clientes que selecionam o roteamento local serão capazes apenas de passar o tráfego entre os data centers que estiverem sendo atendidos por meio do PoP no qual o Direct Link foi pedido.  Os clientes que desejarem passar o tráfego para fora do PoP no qual o Direct Link foi pedido precisarão incluir a opção de roteamento global._

* **Você concorda com a taxa para Roteamento global, incluindo a taxa mensal do _SEU LOCAL_ e as taxas excedentes descritas abaixo?**

    _O roteamento local inclui acesso a todos os Data centers conectados diretamente ao PoP e fornece tráfego de ingresso/egresso ilimitado.  O roteamento global expande o acesso para incluir todos os data centers do IBM Cloud globalmente.  A largura da banda será medida quando o serviço puder medir o tráfego. Quando a medição da largura da banda ocorrer, você será cobrado mensalmente com base em seu preço de mercado, conforme mostrado na tabela a seguir._


### Precificação de Roteamento Global

| Ingresso de Roteamento Global | Egresso de Roteamento Global |
|---|---|
| Livre | Circuito de 1, 2 ou 5 Gbps - largura da banda grátis de 10 TB |
| Livre | Largura de banda grátis de 10 Gbps - 50 TB grátis |


| Tarifas de Supervisão da Largura da B |
|---|
| Mercado 1: US$ 0,05 por GB |
| Mercado 2: $0,10 por GB |
| Mercado 3: US$ 0,15 por GB |
