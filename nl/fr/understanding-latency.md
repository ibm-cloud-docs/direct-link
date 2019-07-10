---
copyright:
  years: 1994, 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: hybrid, solution, latency, connected, milliseconds, high-capacity, performance, security, data, path, resiliency, PoPs, globe, infrastructure, backbone, traffic, workloads

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Comprendre le temps d'attente
{: #understanding-latency}

_Passez à l'hybride avec {{site.data.keyword.cloud}} Direct Link et optimisez vos charges de travail partout dans le monde_

{{site.data.keyword.cloud}} offre des centres de données avec des fonctionnalités Direct Link à travers le monde. Par conséquent, vous pouvez compter sur une latence minimale lorsque vous utilisez Direct Link pour créer votre solution de cloud hybride en reliant votre {{site.data.keyword.cloud_notm}} à votre infrastructure existante.

Que vous disposiez d'un magasin en ligne, que vous exécutiez des solutions de données volumineuses ou que vos employés connectés en réseau puissent accéder à des fichiers dans le monde entier, vous ne voulez surtout pas entendre que la lenteur du chargement de page sur le Web ou la lenteur du transfert de données à partir d'une base de données vous empêche de réaliser une vente ou réduit la productivité de vos employés. Les ralentissements peuvent être provoqués par le temps d'attente de réseau, qui mesure la rapidité avec laquelle les données circulent entre deux points connectés sur Internet. Vous pouvez comparer ce temps d'attente au temps nécessaire à un paquet de données pour aller d'un point à un autre.

Au niveau mondial, le temps d'attente global d'Internet peut varier de manière significative en fonction de la distance que les données doivent parcourir physiquement, du nombre de fois que les données doivent sauter entre les fournisseurs de services, de la quantité de bande passante disponible le long de leur parcours, de la façon dont les données voyagent sur le même chemin, en plus d'autres variables. {{site.data.keyword.cloud_notm}} Direct Link offre un temps d'attente déterministe avec une sécurité renforcée associé à Internet pour des performances prévisibles.


## Comprendre le temps d'attente de réseau
{: #understanding-network-latency}

En tant que meilleure pratique, chaque fournisseur de réseau souhaite offrir le plus faible temps d'attente de réseau au plus grand nombre de clients, et chaque client souhaite obtenir le temps d'attente le plus bas possible. Fournisseurs et clients aspirent à atteindre ce même objectif.

Théoriquement, les données peuvent se déplacer à la vitesse de la lumière sur les câbles réseau à fibre optique, mais pour toutes les raisons évoquées précédemment, les données circulent généralement beaucoup plus lentement. Par exemple, si une connexion réseau spécifique a atteint sa capacité de bande passante, il se peut que les paquets de données fassent la queue temporairement en attendant de pouvoir à leur tour parcourir ce trajet. Autre exemple, si un réseau de fournisseur de services spécifique sélectionne un itinéraire réseau qui n'est pas optimal, les paquets de données peuvent être envoyés à des centaines ou des milliers de kilomètres de leur destination ! Ce sont ces types de retards et de détours qui augmentent le tempsd'attente de réseau et ralentissent les transferts de données.

Le temps d'attente de réseau est exprimé en millisecondes (autrement dit, 1 000 millisecondes par seconde). Quelques millièmes de seconde peuvent ne pas représenter beaucoup pour nous dans notre vie quotidienne, mais des millisecondes deviennent souvent un facteur décisif lorsque nous naviguons sur le Web ou dans nos transactions commerciales. Par exemple, dans le secteur financier, des millisecondes peuvent faire la différence et représenter quotidiennement des milliards de dollars de gains ou de pertes dans des transactions commerciales.

## Approches communes permettant de réduire le temps d'attente de réseau
{: #common-approaches-that-minimize-network-latency}

Etant donné que notre objectif commun est de réduire le temps d'attente, il peut être judicieux de limiter le nombre de variables potentielles pouvant affecter la vitesse de transfert des données. Aucun fournisseur ne peut totalement maîtriser la façon dont les données sont transmises via Internet, mais voici quelques meilleures pratiques pour réduire le temps d'attente de réseau :

 * Distribuer des données à travers le monde : les clients situés dans différents emplacements peuvent extraire des données à partir d'un emplacement qui est proche d'eux géographiquement. Les données étant plus proches des clients, elles sont transférées moins souvent. Lorsque les données ont une plus courte distance à parcourir, le routage est moins susceptible d'avoir un impact significatif sur les performances.

 * Mettre à disposition des serveurs avec des ports réseau haute capacité : d'importants volumes de données peuvent parcourir un serveur chaque seconde. Si des paquets sont retardés en raison de ports complètement saturés, des millisecondes s'écoulent, les pages se chargent plus lentement, les vitesses de téléchargement chutent et les utilisateurs sont mécontents.

 * Comprendre comment vos fournisseurs acheminent le trafic : mieux comprendre de quelle façon vos données sont transférées vers les clients dans le monde entier vous permet de décider de manière plus avisée de l'endroit où vous devez héberger vos données.

## De quelle manière IBM Cloud réduit-il le temps d'attente de réseau ?
{: #how-ibm-cloud-minimizes-network-latency}

Afin de réduire le temps d'attente, {{site.data.keyword.cloud_notm}} a utilisé une approche unique pour construire notre réseau. Tous nos centres de données sont connectés à des points de présence de réseau et tous nos points de présence de réseau sont connectés entre eux via notre réseau principal mondial. Etant donné que nous gérons notre propre réseau principal mondial, notre équipe chargée des opérations de réseau peut contrôler les chemins de réseau et les transferts de données avec plus de précision que si nous devions nous fier à d'autres fournisseurs pour déplacer des données entre différentes zones géographiques.
 
Par exemple, si un client {{site.data.keyword.cloud_notm}} à Berlin souhaite regarder une vidéo de chat hébergée sur un serveur {{site.data.keyword.cloud_notm}} à Dallas, les paquets de données qui constituent cette vidéo de chat parcourent notre réseau principal (utilisé exclusivement par le trafic {{site.data.keyword.cloud_notm}}) vers Francfort, où les paquets sont envoyés à l'un de nos fournisseurs de services de transport en commun ou d'appairage, pour finalement atteindre l'utilisateur à Berlin. Mieux encore, si notre client utilise la fonction CDN d'{{site.data.keyword.cloud_notm}}, les paquets sont envoyés à partir d'un serveur d'équilibrage des charges situé près du client, et il n'est jamais nécessaire de les envoyer depuis Dallas.

Sans un réseau principal mondial, les paquets de vidéo sont envoyés à un fournisseur de services de transport en commun ou d'appairage à Dallas, puis ce fournisseur achemine les paquets via son réseau ou les envoie à un autre fournisseur au niveau d'un segment réseau, et les paquets se fraient un chemin vers l'Allemagne. Il se peut tout à fait que les paquets puissent aller de Dallas à Berlin avec le même temps d'attente de réseau sans utiliser le réseau principal mondial, mais, dans ce cas, d'autres variables existent. Le temps d'attente total est beaucoup plus difficile à garantir ou à prédire.

En plus d'utiliser notre réseau principal mondial, {{site.data.keyword.cloud_notm}} segmente également un trafic public, privé et de gestion sur différents ports réseau. Cela signifie que différents types de trafic sont transférés sans interférer les uns avec les autres.

## Récapitulatif : temps d'attente de réseau
{: #summary-network-latency}

Vos clients estiment que vous devez être capable de leur fournir vos données le plus rapidement possible. Le temps nécessaire à vos données pour atteindre vos clients via Internet est appelé temps d'attente de réseau. Plus vous contrôlez votre chemin réseau de données, plus le temps d'attente de votre réseau est cohérent (et réduit).

* Direct Link vous permet de contrôler le chemin parcouru par vos données et de faire en sorte qu'il ne soit pas interrompu ou bloqué par un autre trafic.

* {{site.data.keyword.cloud_notm}} offre des fournisseurs de service de pointe qui assurent performances élevées, sécurité et résilience.

* Chez {{site.data.keyword.cloud_notm}}, nous continuons d'ajouter des points de présence de réseau dans le monde entier pour amener au plus près de vos clients les données de vos clients et ainsi améliorer le temps d'attente et les performances globales afin de répondre aux besoins de vos charges de travail de cloud hybride.

