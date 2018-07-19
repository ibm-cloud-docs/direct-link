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

# Questionário do IBM Cloud Direct Link Exchange

Obrigado por abrir uma solicitação para o IBM Cloud Direct Link Exchange. Para finalizar a sua solicitação, gostaríamos de reunir algumas informações adicionais de você.  É possível falar com um engenheiro a qualquer momento durante o processo de questionário.  Após você ter concluído o questionário, ele será revisado por nossa equipe de Engenharia de design de nuvem e escalado para a Engenharia de rede para implementação.

## Você reconhece e concorda com os itens a seguir?

1. Cada conexão do Direct Link requer um pedido exclusivo. Se você requerer múltiplas conexões, abra pedidos separados do Direct Link para cada conexão.

2. As taxas para o serviço do Direct Link Exchange cobrem o custo de rescisão de serviço na infraestrutura do IBM Cloud. 

 * Os Serviços de infraestrutura são faturados antecipadamente e começam na aceitação do seu pedido; no entanto, devido à natureza do IBM Cloud Direct Link, o faturamento do serviço Direct Link começará no início de uma sessão do Protocolo de Roteamento de Borda (BGP) com o IBM Cloud ou 30 dias após a chave de serviço ser fornecida ao cliente. 

 * O faturamento é interrompido após:
   * Um cliente solicita que um circuito seja excluído **e** 
   * O Exchange Provider ou o Network Service Provider desprovisionou o circuito.
  * Para obter mais informações, veja **Seção 5 - Encargos** no Cloud Services Agreement no link a seguir: [ibm.biz/service-agreement](ibm.biz/service-agreement)
  * Como alternativa, o faturamento poderá ser parado para um cliente se ele for notificado de que o serviço Direct Link será desligado e não funcionará mais.

3. Pedindo o serviço Direct Link, você será responsável por quaisquer taxas associadas ao acesso do ponto de Presença (PoP) por meio de sua rede remota e por qualquer conexão cruzada necessária dentro da instalação do PoP para acessar o seu provedor do Exchange. Você (ou o seu provedor) também será responsável por comprar o circuito virtual para o IBM Cloud. Se o seu provedor exigir que um roteador ou outro dispositivo esteja fisicamente no PoP, você também será responsável pelos custos associados à instalação desse equipamento. Confirme se o provedor de Rede ou PoP pode atingir o Direct Link Exchange e precificar os custos associados.

4. O IBM Cloud não instalará nenhum equipamento do cliente em nossos POPs de rede.  Você precisará trabalhar com o seu provedor para determinar se precisa ou não instalar qualquer equipamento no mesmo local em que o IBM Cloud PoP existe.

5. O serviço Direct Link Exchange é fornecido de tal maneira que o seu link e o roteador do IBM Cloud podem ser finalizados em ambos os pontos de falha (SPOF). Se desejar obter redundância por meio do serviço do Direct Link Exchange, será necessário terminar os links em dois PoPs de rede do IBM Cloud separados ou solicitar duas conexões em um local do Direct Link Exchange com um roteador secundário.

6. A rede de serviços do IBM Cloud não será acessível por meio de suas redes remotas diretamente. Se isso mudar no futuro, você será notificado.

7. O IBM Cloud não permitirá que os clientes voltem a transportar o tráfego entre os seus sites remotos por meio do backbone do IBM Cloud. O produto Direct Link Exchange é destinado às suas redes remotas para permitir a comunicação privada com sua infraestrutura do IBM Cloud.

8. Depois de ter confirmado que seu circuito atingiu o PoP do Direct Link Exchange, será necessário fazer um pedido no provedor de troca de nuvem e fornecer todas as informações relevantes para o provedor de troca de nuvem e o IBM Cloud. Para provedores do Equinix, o tempo de implementação típico pode levar horas. O tempo de implementação típico para a oferta do IBM Cloud Direct Link Exchange leva de 5 a 10 dias para ser concluído. 

9. O IBM Cloud Direct Link Exchange requer a utilização de uma instância VRF (Virtual Routing and Forwarding) no lado do IBM Cloud Network. Isso permite que o cliente defina os próprios endereços IP remotos para uso na rede remota; no entanto, você deve estar ciente de que, se for capaz de utilizar a rede 10.x.x.x, mesmo assim não poderá a sobrepor a seus hosts dentro do IBM Cloud nem à rede de serviços do IBM Cloud (10.0.0.0/14, 10.198.0.0/15 e 10.200.0.0/14). A transição de sua conta para um VRF requererá uma breve indisponibilidade de rede privada conforme cada VLAN for migrada para a nova configuração.  A equipe de Engenharia de rede trabalhará com você para definir uma janela para essa atividade.

10. O VRF não é compatível com os serviços de SSL, PPTP e IPSEC VPN do IBM Cloud.  Uma alternativa é usar o próprio Direct Link para o gerenciamento de seus servidores ou executar a sua própria solução de VPN (como um Vyatta) que pode ser configurada com tipos diferentes de VPN.  Após migrar para um VRF, a VPN de SSL geralmente funcionará quando uma conexão de VPN for feita com o mesmo local do DC no qual o cálculo está sendo acessado, mas não permitirá acesso globalmente.

11. O IBM Cloud Direct Link Exchange requer o BGP para implementar rotas para a rede remota de um cliente. Quando o seu serviço Direct Link tiver sido implementado, o IBM Cloud anunciará todas as sub-redes privadas designadas à sua conta. O IBM Cloud não implementará filtros customizados, pré-anexação do AS-Path e preferências locais customizadas em propagandas para o peer do BGP remoto do Cliente. O IBM Cloud não implementará filtros nas propagandas recebidas para o IBM Cloud. Os clientes precisarão gerenciar adequadamente as propagandas para/do IBM Cloud por meio do roteador de borda do cliente. 

## Outras perguntas

* **Você reconhece e aceita a precificação de _SEU LOCAL_ para a conexão do IBM Cloud Direct Link Exchange?**

* **O IBM Cloud designará um ASN privado para você para propósitos de configuração do BGP para anunciar suas redes remotas em sua rede privada do IBM Cloud. Isso é aceitável ou você prefere utilizar o seu próprio ASN público?**

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
