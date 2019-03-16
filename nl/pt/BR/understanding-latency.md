---
copyright:
  years: 1994, 2017, 2018, 2019
lastupdated: "2019-02-19"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Entendendo a Latência
{: #understanding-latency}

_Acesse Híbrido com o {{site.data.keyword.cloud}} Direct Link: fazendo com que suas cargas de trabalho
sejam executadas mais rapidamente no mundo todo_

O IBM Cloud oferece data centers com recursos do Direct Link ao redor do globo. Portanto, é possível contar com a latência mínima ao usar o Direct Link para criar sua solução de nuvem híbrida vinculando seu IBM Cloud à infraestrutura existente.

Independentemente de você ter uma loja on-line, de executar grandes soluções de dados ou de ter seus funcionários configurados em uma rede com acesso a arquivos ao redor do mundo — você nunca desejará ouvir que o carregamento lento de uma página na web, ou a transferência lenta de dados de um banco de dados, está impedindo que você realize uma venda ou reduzindo a produtividade do funcionário. As lentidões podem ser causadas por latência de rede, que é a medida da rapidez como que os dados viajam entre dois pontos conectados na Internet. Pode-se pensar nisso como a quantidade de tempo que leva para um pacote de dados ir de um lugar para outro.

Globalmente, a latência geral da Internet pode variar significativamente, dependendo do quão longe os dados devem viajar fisicamente, de quantas vezes os dados precisam pular entre provedores de serviços, de quanta largura da banda está disponível ao longo do caminho, de quais outros dados estão viajando pelo mesmo caminho, além de outras variáveis. O IBM Cloud Direct Link oferece latência determinística com segurança maior, em relação à Internet, para desempenho previsível.


## Entendendo a Latência de Rede

Como uma melhor prática, cada provedor de rede deseja oferecer a latência de rede mais baixa para o maior número de clientes e cada cliente deseja obter a menor latência possível. É um resultado desejável e compartilhado.

Teoricamente, os dados podem viajar na velocidade da luz entre os cabos de rede de fibra ótica, mas por todos os motivos fornecidos, os dados geralmente viajam muito mais lentamente. Por exemplo, se uma conexão de rede específica atingiu sua capacidade de largura da banda, os pacotes de dados poderão entrar em fila temporariamente para esperarem sua vez de atravessar esse caminho. Como outro exemplo, se uma rede do provedor de serviços específica selecionar uma rota de rede que não é ideal, os pacotes de dados poderão ser enviados centenas ou milhares de milhas de distância de seu destino no processo chegar ao seu destino! Esses tipos de atrasos e desvios são as causas de latência de rede mais alta — e de transferências de dados mais lentas.

Nós expressamos a latência de rede em milissegundos (isto é, 1.000 milissegundos por segundo). Um pouco de milésimos de segundo pode não significar muito para nós quando estamos vivendo nossa vida diária, mas milissegundos se tornam frequentemente um fator decisivo em nossa navegação na web ou em nossas transações de negócios. Por exemplo, no setor financeiro, milissegundos podem significar bilhões de dólares de diferença em ganhos ou perdas de transações comerciais em uma base diária.

## Abordagens Comuns que Minimizam a Latência de Rede

Dado que nosso objetivo comum é minimizar a latência, faz sentido limitar o número de variáveis potenciais que podem afetar a velocidade da movimentação de dados. Nenhum provedor pode obter controle completo sobre como os dados viajam na Internet, mas aqui estão algumas melhores práticas para minimizar a latência de rede:

 * Distribua dados ao redor do mundo: clientes em locais diferentes podem extrair dados de um local que está geograficamente próximo a eles. Como os dados estão mais próximos dos clientes, eles são transferidos menos vezes. Quando os dados têm uma distância mais curta para viajar, o roteamento tem menos probabilidade de causar um impacto significativo no desempenho.

 * Servidores de provisão com portas de rede de alta capacidade: grandes volumes de dados podem viajar através de um servidor a cada segundo. Se os pacotes forem atrasados devido a portas totalmente saturadas, milissegundos de tempo passarão, as páginas serão carregadas mais lentamente, as velocidades de download cairão e os usuários ficarão insatisfeitos.

 * Entenda como seus provedores roteiam o tráfego: quando você sabe mais detalhes sobre como seus dados são transferidos para clientes ao redor do mundo, é possível tomar decisões melhores sobre onde hospedar seus dados.

## Como o IBM Cloud Minimiza a Latência de Rede

Para minimizar a latência, o IBM Cloud utilizou uma abordagem exclusiva para construir nossa rede. Todos os nossos data centers estão conectados a pontos de presença (PoPs) de rede e todos os nossos pontos de presença de rede estão conectados entre si por meio de nossa rede global de backbone. Como mantemos nossa própria rede global de backbone, nossa equipe de operações de rede pode controlar os caminhos de rede e as transferências de dados mais precisamente do que se dependêssemos de outros provedores para mover dados entre geografias.
 
Por exemplo, se um cliente do IBM Cloud em Berlim quiser assistir a um vídeo de gato hospedado em um servidor IBM Cloud em Dallas, os pacotes de dados que compõem esse vídeo de gato viajarão através de nossa rede de backbone (que é exclusivamente usada pelo tráfego do IBM Cloud) para Frankfurt, onde os pacotes serão enviados para um de nossos Provedores de Serviço de rede pública de peering ou de trânsito para, finalmente, chegar ao usuário em Berlim. Ainda melhor, se nosso cliente usar o recurso CDN do IBM Cloud, os pacotes serão enviados de um servidor de borda localizado próximo ao cliente e eles nunca sequer precisarão ser enviados de Dallas.

Sem uma rede global de backbone, os pacotes de vídeo são enviados para um provedor de rede pública de peering ou de trânsito em Dallas, em seguida, esse provedor roteia os pacotes através de sua rede ou envia os pacotes para outro provedor em um hop de rede e os pacotes finalmente saltam para a Alemanha. É totalmente possível que os pacotes possam chegar de Dallas a Berlim com a mesma latência de rede sem usar a rede global de backbone, mas sem a rede global de backbone, há mais variáveis; a latência total é muito mais difícil de garantir ou prever.

Além de usar nossa própria rede global de backbone, o IBM Cloud também segmenta o tráfego público, privado e de gerenciamento em portas de rede diferentes. Isso significa que diferentes tipos de tráfego serão transferidos sem interferir um no outro.

## Resumo: latência de rede

Seus clientes desejam obter seus dados o mais rápido possível. O tempo que leva para os dados chegarem a eles pela Internet é chamado de latência de rede. Quanto mais controle você tiver sobre o caminho de rede de seus dados, mais consistente (e menor) sua latência de rede poderá ser.

* Com o Direct Link, nós lhe damos o controle sobre o caminho que seus dados viajam, assim a viagem de seus dados não será interrompida ou bloqueada por outro tráfego.

* O IBM Cloud oferece Service Providers líderes de mercado -- fornecendo alto desempenho, segurança e resiliência.

* No IBM Cloud, continuamos incluindo Pontos de Presença (PoPs) de rede em todo o globo para trazer os dados de seus clientes para mais perto deles -- melhorando, assim, a latência e o desempenho geral para atender às necessidades de suas cargas de trabalho de nuvem híbrida.

