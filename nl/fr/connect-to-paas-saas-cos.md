---

copyright:
  years: 2018
lastupdated: "2018-04-24"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Utilisation conjointe d'IBM Cloud Direct Link et d'IBM Cloud Object Storage

Le présent document explique comment configurer IBM Cloud Direct Link de manière à pouvoir accéder à IBM Cloud Object Storage et à d'autres services IBM Cloud. Il existe plusieurs méthodes pour réaliser un pontage à partir du réseau IBM Cloud IaaS privé, sur lequel IBM Cloud Direct Link existe, vers le réseau "public" qui prend en charge les fonctions IBM Cloud PaaS et SaaS, sans quitter réellement le réseau principal IaaS.

Selon la règle en cours, les noeuds finaux de service privés IBM Cloud ne sont pas accessibles via IBM Cloud Direct Link. Les techniques décrites dans le présent document s'appuient sur un accès indirect via des systèmes hébergés par IBM Cloud. Si les noeuds finaux de service privés ne sont pas accessibles via Direct Link, les serveurs et les dispositifs privés d'un client peuvent devenir accessibles.

## Qu'est-ce qu'IBM Cloud Object Storage (COS) ?

IBM Cloud Object Storage est une plateforme basée sur le Web qui stocke des données non structurées. Elle fournit fiabilité, sécurité, disponibilité et reprise après incident sans réplication. 

Les informations stockées à l'aide d'IBM Cloud Object Storage sont chiffrées et réparties dans plusieurs emplacements géographiques. Elles sont accessibles via une implémentation de l'API S3. Ce service utilise les technologies de stockage réparti fournies par le service IBM Cloud Object Storage.

IBM COS est disponible dans deux types de configuration : **Inter-régional** et **Régional**. Le service de type Inter-régional fournit une plus grande durabilité et une meilleure disponibilité que lorsqu'une seule région est utilisée, mais au détriment de temps d'attente légèrement plus élevés. Ce service est disponible aujourd'hui aux Etats-Unis et dans l'UE. Le service de type Régional fournit le contraire : il distribue des objets sur plusieurs zones de disponibilité dans une seule région. Si une région ou une zone de disponibilité donnée est inaccessible, le conteneur d'objets continue de fonctionner sans problèmes. Les éventuelles modifications manquées sont appliquées lorsque le centre de données inaccessible est à nouveau en ligne.

## Qu'est-ce qu'IBM Cloud Direct Link ?

IBM Cloud Direct Link est une suite de produits qui permet aux clients de créer des connexions privées entre leurs environnements de réseau distant et leurs déploiements IBM Cloud. 

## Utilisation de Cloud Object Storage (COS) sur IBM Cloud Direct Link

La famille IBM Cloud Direct Link de solutions de connectivité est une offre IaaS, destinée à permettre la connectivité WAN privée à nos services IaaS. La plupart des solutions IBM Cloud PaaS et SaaS sont construites par dessus notre infrastructure IaaS. Par conséquent, vous pouvez initier ces types de connexion à partir d'IBM Cloud.

Ces trois approches peuvent vous aider à vous connecter à IBM Cloud PaaS et SaaS à l'aide d'IBM Cloud Direct Link. Actuellement, la méthode 3 est l'approche recommandée, car elle a été testée en profondeur.

## Trois méthodes de connexion à PaaS et SaaS à l'aide de Direct Link


### Méthode 1 : Utilisation d'un dispositif de routeur virtuel (parfois appelé un Vyatta) pour créer un “tronçon vers le public”
 
![vyatta-flow.png](images/vyatta-flow.png)



**Principe de base : Se connecter à IBM COS à l'aide d'un "tronçon public" pour établir une connexion aux noeuds finaux de stockage**
*Ce "tronçon public" ne quitte jamais le réseau principal IBM Cloud IaaS.*

* Le client choisit un noeud final public avec l'aide du support technique et de l'équipe d'intégration IBM COS et reçoit une clé d'API.
* Sur son routeur local, le client ajoute des routes à des sous-réseaux spécifiques, ce qui permet d'assurer des flux de circulation homogènes à l'aide d'IBM Cloud Direct Link
* Sur son dispositif de routeur virtuel, le client crée une route pour traverser le réseau public et pour atteindre le noeud final public pour les services IBM COS
* Le client doit mettre à disposition une paire haute disponibilité de matériel VRA (@x)
* Chaque membre VRA reçoit 20 To par mois de bande passante incluse, pour décaler les frais vers le décompte et la facturation du cloud public
* Utilisez le partage de bande passante (pooling) entre vos serveurs hébergés pour cumuler de la bande passante prépayée.


### Méthode 2 : Passe-système de serveur Cloud (privé à privé)

![reverse=proxy](images/reverse-proxy.png)

**Principe de base : Sécuriser les serveurs Cloud avec des données d'identification COS**

 * Le client met à disposition un ou plusieurs serveurs, VSI ou Bare Metal, dans IBM Cloud.
 * Chaque serveur héberge une application Web ou à base de script (Java, Python, PHP, etc.) pour écouter les connexions et les demandes uniquement sur son interface privée.
 * L'application de serveur utilise sa propre API ou imite (des parties de) S3.
 * Les interfaces privées de serveur IBM Cloud sont correctement sécurisées. Séparez l'accès dans un réseau privé à l'aide de réseaux locaux virtuels, de groupes de sécurité, de pare-feu de système d'exploitation ou de dispositif de routeur virtuel.
 * Les mesures visant à valider l'appelant et à limiter la portée de l'API sont recommandées.
 * Les clients sur le réseau local du client utilisent les adresses IP privées de serveurs passe-système comme cibles pour les demandes.
 * Le routage client et les modifications DNS sont requis.
 * L'application hébergée sur le serveur traite chaque demande en émettant un appel API authentifié vers un noeud final COS privé, en renvoyant une réponse à l'appelant.

### Méthode 3 : Proxy inverse (privé à privé)

Il s'agit de la méthode qui est actuellement recommandée.

**Principe de base : Sécuriser les appelants client locaux avec des données d'identification COS**

 

 * Adaptée de la méthode 2, qui héberge des applications Web sur des serveurs Cloud, cette méthode héberge des serveurs HTTPS (par exemple, NGINX) qui sont configurés pour le proxy inverse.
 * Chaque serveur est en mode écoute sur HTTPS, avec un certificat auto-émis, et transmet des demandes directement à des noeuds finaux COS privés indiqués dans le document référencé ci-dessous :
 
 ![Noeuds finaux COS](https://console.bluemix.net/docs/services/cloud-object-storage/basics/endpoints.html)
 
### Voici un exemple montrant comment améliorer la fiabilité et les performances de votre cloud (non propre à COS) :`serverfault.com`

 * Pour accélérer la mise à l'échelle et la résilience, plusieurs serveurs proxy peuvent être déployés. 
 * Utilisez DNS de façon circulaire côté client pour des fonctions de basculement et d'équilibrage de charge rudimentaires.
 * Les serveurs proxy peuvent être placés derrière le dispositif de routeur virtuel à des fins de protection et de journalisation centralisée.
 
 ## Gestion et mise à disposition de fonctions IBM Cloud 
 
Cette section contient des liens rapides vers la documentation de certaines offres IBM Cloud PaaS et SaaS auxquelles vous pouvez vous connecter à l'aide d'IBM Cloud Direct Link.

## Comment mettre à disposition des serveurs bare metal

Pour obtenir des instructions détaillées sur la mise à disposition de serveurs bare metal, voir [ce document](https://console.bluemix.net/docs/bare-metal/about.html#getting-started-with-bare-metal-servers).

## Comment mettre à disposition un dispositif de routeur virtuel (VRA)

Pour obtenir des instructions détaillées sur la mise à disposition d'un dispositif de routeur virtuel, voir [ce document](https://console.bluemix.net/docs/infrastructure/virtual-router-appliance/getting-started.html#getting-started).

## Comment mettre à disposition IBM Cloud Object Storage (COS)

 * Pour obtenir des instructions détaillées sur la mise à disposition de COS, voir [ce document](https://console.bluemix.net/catalog/services/cloud-object-storage).
 
 * Utilisez l'un des noeuds finaux privés (indiqués précédemment) pour assurer l'interface avec votre compartiment ou un objet dans votre compte COS mis à disposition.
