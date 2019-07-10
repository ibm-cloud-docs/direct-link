---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-05-21"

keywords: VRF, IP, routers, backbone, service, VLAN, multiple isolation, tenant, tenancy, datacenters, data, center, shared tenancy, private endpoint, Customer VRF, Private Network Question, support, ticket

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Aperçu du service Routage et transfert virtuel (VRF) sur IBM Cloud
{: #overview-of-virtual-routing-and-forwarding-vrf-on-ibm-cloud}

Par définition, la technologie de routage et transfert virtuel (VRF) est incluse dans les routeurs IP. Il s'agit d'un service inhérent du réseau principal.

## Options de connectivité d'IBM Cloud
{: #connectivity-options-for-ibm-cloud}

**Les ressources de cloud dispersées** sont des ressources réparties sur plusieurs sites, ou même sur plusieurs sous-réseaux ou réseaux locaux virtuels. Ces ressources ont besoin d'une fonction de routage pour communiquer entre elles, même dans un contexte de réseau privé. Ce document décrit l'option de communication de la location à "isolement multiple", souvent appelée _VRF client_. Elle est implémentée en tant que VPN MPLS de couche 3 (RFC 4364) sur le réseau principal {{site.data.keyword.cloud}} global.

En général, la plateforme IBM Cloud offre deux options de routage à travers notre réseau privé pour fournir une connectivité entre les pods et les centres de données :

1. **Location partagée :** un réseau logique commun, partagé par tous les locataires qui utilisent ce modèle, avec une séparation fournie par des listes de contrôle d'accès automatisées (LCA) et activé avec le spanning VLAN. Cette option n'est pas décrite dans ce document.

2. **Isolement multiple :** un réseau logique dédié par locataire qui ne permet aucune interaction avec les réseaux logiques des autres locataires.  

Ce document utilise le terme **VRF client** pour décrire la connectivité réseau à _isolement multiple_.

## Vue d'ensemble du VRF (technologie à isolement multiple)
{: #vrf-overview}

Le routage et transfert virtuel (VRF) permet à plusieurs instances d'une table de routage d'exister dans un routeur et de travailler simultanément. Avec le service de routage et transfert virtuel, le réseau VRF de chaque locataire de cloud est segmenté au sein de sa table de routage. Cette segmentation permet les chevauchements d'adresses IP et ne crée aucune interaction ou interférence avec les VRF des autres locataires. IBM Cloud utilise une grande majorité du réseau `10.0.0.0/8` qui peut chevaucher un grand nombre de réseaux distants, par exemple les réseaux déployés dans des centres de données client.

En utilisant le VRF, les locataires IBM Cloud sont autorisés à utiliser des adresses IP distantes qui, normalement, ne se chevauchent pas dans la table globale. IBM réserve néanmoins les adresses lien-local suivantes définies par la RFC 1918 et les adresses de multidiffusion qui ne peuvent pas être routées à partir de ce service VRF.

* `10.0.0.0/14`
* `10.200.0.0/14`
* `10.198.0.0/15`
* `169.254.0.0/16`
* `224.0.0.0/4`
* `166.9.0.0/16` (utilisé par le service de noeud final privé)
* Toutes les plages d'adresses IP assignées à vos réseaux locaux virtuels sur la plateforme IBM.

IBM se lance dans le déploiement d'une nouvelle génération de cloud pour activer le cloud privé virtuel dans nos zones de disponibilité. Cette nouvelle fonctionnalité du cloud privé virtuel active la fonction BYoIP (Bring Your own IP) dans les zones de disponibilité équipées d'un cloud privé virtuel, situées à Dallas, Washington DC, Londres, Francfort, Tokyo et Sydney.

Chaque locataire du réseau principal utilisant le service de routage et transfert virtuel (VRF) ne peut avoir qu'un seul _VRF client_ par Direct Link, ce qui assure la connectivité entre tous les serveurs du locataire, quel que soit leur emplacement. Toutefois, un locataire IBM Cloud peut avoir plus d'un compte Direct Link qui alimente un seul routeur à connexion croisée.  

* Les serveurs d'un locataire se trouvant dans n'importe quel réseau local virtuel, pod, ou centre de données du monde entier peuvent atteindre tous les autres serveurs de ce locataire dans le monde entier.

* Le VRF client de chaque locataire est connecté au réseau commun de services partagés, afin de permettre une accessibilité privée à ces serveurs pour utiliser le DNS, le stockage partagé, la surveillance, les correctifs, etc.

* Le VRF client est un service de connectivité qui permet d'isoler les locataires. Tous les contrôles supplémentaires nécessaires dans une location doivent être fournis séparément, à l'aide d'une passerelle, de groupes de sécurité ou de contrôles basés sur l'hôte.

## Avantages du passage à un VRF
{: #benefits-of-moving-to-vrf}

**Les principaux avantages sont les suivants :**

* La technologie de séparation à _isolement multiple_ est largement acceptée et éprouvée dans l'industrie. De nombreux clients de cloud trouvent l'approche VPN de niveau 3 plus acceptable (que les LCA) pour leurs auditeurs et leurs responsables de la conformité.   

* Les clients IBM Cloud peuvent étendre ou migrer la portée de leur réseau de manière significative, grâce à l'ajout de nouveaux sites ou applications sur l'ensemble du réseau IBM.

* Les tables de routage spécifiques aux locataires réduisent l'ouverture pour le chevauchement des adresses IP, sans risque de chevauchement avec les sous-réseaux des autres locataires ou d'autres parties du réseau qui ne sont pas applicables.

**Quelques inconvénients mineurs par rapport à l'ancien modèle de LCA :**  

* La conversion au VRF client nécessite une fenêtre de maintenance, ce qui provoque une brève interruption des flux de trafic sur le réseau principal.

* L'accès à distance au moyen des services VPN gérés (SSL, IPSec) est limité au centre de données local ; cependant, le réseau principal de la LCA partagée permet un accès global depuis n'importe quel point d'entrée.

* Le spanning VLAN n'est pas disponible dans le cadre de la location à _isolement multiple_.

## Que se passe-t-il durant le processus de conversion de compte ?
{: #what-happens-during-the-account-conversion-process}

De nombreux clients IBM Cloud utilisent actuellement un modèle de location partagée sur le réseau IBM Cloud. Pendant la conversion, la location est convertie pour utiliser un VRF client, le plus souvent avec un nouvel abonnement Direct Link, ou de la manière requise ou demandée.  

Le processus de conversion implique une interruption du réseau pendant que les réseaux locaux virtuels et leurs sous-réseaux sont détachés du réseau principal de la LCA puis connectés au VRF client. Ce processus entraîne quelques pertes de paquets pour le trafic entrant ou sortant des réseaux locaux virtuels. Les paquets se trouvant dans le réseau local virtuel continuent à circuler. Si une passerelle réseau, telle qu'un dispositif de sécurité FortiGate ou un dispositif de routeur virtuel, est impliquée, aucune perturbation ne se produit parmi les réseaux locaux virtuels connectés à cette passerelle. Les serveurs ne voient aucune panne de réseau et la plupart des charges de travail se rétablissent automatiquement lorsque le flux de trafic reprend. La durée totale de l'interruption dépend de l'étendue de la topologie du locataire, c'est-à-dire du nombre de sous-réseaux, de réseaux locaux virtuels et de pods que comprend votre location.

![Le processus de conversion](/images/vrf-on-ibm-cloud.png)

Pendant la migration, les réseaux locaux virtuels sont déconnectés du réseau principal et reconnectés au VRF client.  La durée de l'interruption varie en fonction du nombre de réseaux locaux virtuels, de pods et de centres de données impliqués. Le trafic entre les réseaux locaux virtuels est perturbé, mais les serveurs restent connectés au réseau. L'application peut être affectée ou non, selon sa sensibilité à la perte de paquets.

## Comment lancer la conversion ?
{: #how-you-can-initiate-the-conversion}

Les clients IBM Cloud existants peuvent [ouvrir un ticket de demande de service](https://cloud.ibm.com/unifiedsupport/cases/add) via leur compte [IBM Cloud ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")]( https://cloud.ibm.com/unifiedsupport/cases/add), en demandant leur migration vers un VRF. Le ticket doit indiquer “Question de réseau privé” et inclure le texte suivant :

"Nous demandons que le compte _entrez votre numéro de compte_ soit déplacé vers son propre VRF. Nous comprenons les risques et approuvons le changement. Veuillez répondre en indiquant les fenêtres de temps prévues pour ce changement afin que nous puissions nous préparer à la migration."

La migration est effectuée par l'équipe IBM Cloud Network Engineering. Aucune autre information n'est requise de votre part, à l'exception d'un calendrier convenu. En général, la perte de paquets peut durer de 15 à 30 minutes, selon la complexité de votre compte. (La durée peut être supérieure si votre compte dispose de connexions Direct Link existantes.) Le processus est fortement automatisé, nécessitant une interaction minimale de la part de l'équipe IBM et doit être transparent.

Lorsque vous ouvrez le ticket, il est recommandé de sélectionner l'option "Technique" comme illustré à la figure suivante, bien que les autres options fonctionnent si vous incluez le texte fourni précédemment :

![image](https://media.github.ibm.com/user/11495/files/4474c300-4bd9-11e9-9bc7-d6242d7997e9)
