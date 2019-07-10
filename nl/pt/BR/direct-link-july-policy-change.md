---
copyright:
  years: 2018, 2019
lastupdated: "2019-04-02"

keywords: Intercloud, Frankfurt, PoPs, Connect, Exchange, Chennai, Equinix, Megaport, Kinx, diversity, Bluefringe, CenturyLink, BT, Sao Paulo, Tokyo, Japan, PCCW, Colt, blog, service provider, partner, Telia, Internexion, Packet Fabric, Global Routing, expanded, market

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:important: .important}

# Anúncio: a mudança de política de roteamento global começa em 1º de julho

Efetiva em 1º de julho de 2019 - Mudança de política de roteamento global do IBM Direct Link
{: important}

Para melhorar a experiência do cliente e fornecer um valor maior, estamos aprimorando o IBM Direct Link Global Routing Service. As melhorias chave incluem:

* **Mercados locais expandidos:** estamos implementando o alinhamento de nossos sites aos quais os clientes podem se conectar dentro de seus Mercados locais. Estamos alinhando cada site do PoP na rede do IBM Cloud para permitir que os clientes se conectem ao IBM Cloud em nossos sites do PoP para se conectarem a recursos em um ou mais de nossos Data centers localizados em todo o globo.

* **Novo modelo de precificação:** para alinhar melhor as velocidades de conexão com as velocidades de conexão selecionadas, estamos mudando o modelo de precificação de nosso serviço do IBM Direct Link Global Routing.

* **Tráfego de link direto ilimitado:** estamos removendo os encargos de excesso de tráfego de rede para clientes que têm roteamento Local ou Global para tráfego de rede privada do Direct Link entre PoPs e Data centers do IBM Cloud globalmente.

## Visão geral do IBM Cloud Direct Link Global Routing
{: #ibm-cloud-direct-link-global-routing-overview}

Todas as ofertas atuais do Direct Link incluem o Roteamento local sem taxas adicionais. Esse serviço inclui acesso aos Data centers no Mercado local no qual a conexão do Direct Link está localizada. Ele fornece ingresso ilimitado e tráfego egresso nas conexões privadas do Direct Link com os recursos do IBM Cloud dentro da conta do cliente. Com a opção de Roteamento local, o tráfego do Direct Link é restrito para os serviços fornecidos por esse Mercado local.

Para rotear o tráfego de rede fora do Mercado local ao qual o Direct Link está conectado (PoP ou Data center), deve-se incluir a opção de Roteamento global, que expande o acesso para incluir todos os Data centers do IBM Cloud globalmente.

O Roteamento global é aplicado a serviços individuais do Direct Link. O Roteamento global não é aplicado por meio de agregação. Ele deve ser especificado em cada serviço do Direct Link que deseje a conectividade fora de um determinado mercado.

## Mercados locais expandidos do IBM Direct Link
{: #announce-expanded-ibm-direct-link-local-markets}

Estamos expandindo os Mercados locais do Direct Link para fornecer mais opções de roteamento local para os nossos clientes globalmente. As novas designações do Mercado local estão listadas abaixo:

* O mercado local de Dallas agora incluirá os PoPs de Denver, Houston e Chicago.
* O mercado local de Washington DC agora incluirá os PoPs de Nova York, Atlanta e Miami.
* O mercado local de San José agora incluirá o PoP de Los Angeles.
* O mercado local de Oslo agora incluirá o PoP de Estocolmo.
* O mercado local de Sydney agora incluirá o PoP de Perth.
* O mercado local de Hong Kong incluirá o PoP de Taipé depois de ativado.
* O mercado local de Tóquio incluirá o PoP de Osaka depois de ativado.
* O mercado local de Chennai incluirá o PoP de Mumbai depois de ativado.

Essas mudanças estão descritas em tabelas localizadas em: https://cloud.ibm.com/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#expanded-ibm-direct-link-local-markets

## Modelo de precificação de roteamento global do IBM Cloud Direct Link
{: #announce-ibm-cloud-direct-link-global-routing-pricing-model}

Com todas as ofertas do IBM Cloud Direct Link, o roteamento de rede dentro de um Mercado local é padrão. Efetiva em 1º de julho, 2019, a precificação para a opção de Roteamento global está sendo alinhada com a velocidade de conexão da conexão do Direct Link. Esse alinhamento fornecerá um valor melhor para os clientes em todas as velocidades de conexão disponíveis para as ofertas do Direct Link.

A precificação está localizada em https://cloud.ibm.com/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-global-routing-add-on

## Encargos de excesso de trânsito de rede de roteamento global do IBM Cloud Direct Link
{: #announce-ibm-cloud-direct-link-global-routing-network-transit-overage-charges}

Juntamente com esse anúncio, estamos retirando os limites de trânsito de rede e os encargos de excesso para os clientes com a opção de Roteamento global. A precificação anterior incluía concessões de trânsito de rede e cobranças excedentes pelo tráfego egresso fora do mercado local do cliente. A nova precificação elimina esses encargos de tráfego de rede. Efetivos com esse anúncio, o ingresso e o tráfego egresso nas conexões do Direct Link não incorrerão em excessos.

## Data de vigência
{: #announce-effective-date}

Essas mudanças serão efetivas na segunda-feira, 1º de julho, 2019 e serão aplicadas a todos os novos pedidos no próximo ciclo de faturamento após essa data.

É importante observar que com essa automação atualizada, quaisquer circuitos do Direct Link que requeiram Roteamento global deverão ser atualizados apropriadamente antes dessa data. Quaisquer upgrades ou downgrades de um serviço do Direct Link resultarão na automação que verificará se o Roteamento global está presente. Se o Roteamento global não estiver presente, qualquer tráfego entre os circuitos do Direct Link será restrito aos mercados locais.

Incentivamos fortemente os clientes a revisarem o roteamento do IBM Cloud em serviços do Direct Link e a abrirem chamados para remediar o roteamento em serviços do Direct Link existentes.
