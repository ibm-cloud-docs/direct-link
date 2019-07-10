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

# Annonce : Modification des règles de routage mondial à compter du 1er juillet

Effectif au 1er juillet 2019 - Modification des règles de routage mondiale d'IBM Direct Link
{: important}

Afin d'améliorer l'expérience client et d'offrir une valeur supérieure, nous étendons le service de routage mondial d'IBM Direct Link. Améliorations clé apportées :

* **Marchés locaux étendus :** Nous mettons en oeuvre l'alignement de nos sites auxquels les clients peuvent se connecter au sein de leurs marchés locaux. Nous alignons chaque site PoP sur le réseau IBM Cloud afin de permettre aux clients qui se connectent à IBM Cloud sur nos sites PoP de se connecter aux ressources d'un ou plusieurs de nos centres de données dans le monde.

* **Nouveau modèle de tarification :** Afin de mieux aligner la tarification sur les vitesses de connexion sélectionnées, nous changeons le modèle de tarification de notre service de routage mondial IBM Direct Link.

* **Trafic Direct Link illimité :** Nous retirons les frais d'utilisation excédentaires concernant le trafic réseau des clients qui disposent du routage local ou global pour le trafic réseau privé Direct Link entre les points de présence (PoP) et les centres de données IBM Cloud, globalement.

## Routage mondial IBM Cloud Direct Link - Présentation
{: #ibm-cloud-direct-link-global-routing-overview}

Toutes les offres Direct Link actuelles incluent le routage local sans coût supplémentaire. Ce service comprend l'accès aux centres de données du marché local où se trouve la connexion Direct Link. Il fournit un trafic entrant et sortant illimité via les connexions privées Direct Link vers des ressources IBM Cloud sur le compte du client. Avec l'option de routage local, le trafic Direct Link est limité aux services fournis par ce marché local. 

Pour router le trafic réseau hors du marché local auquel Direct Link est connecté (PoP ou data center), vous devez ajouter l'option de routage mondial, lequel étend l'accès afin d'inclure globalement tous les centres de données IBM Cloud. 

Le routage mondial est appliqué à des services Direct Link individuels. Il n'est pas appliqué via l'agrégation. Il doit être spécifié pour chaque service Direct Link souhaitant une connectivité hors d'un marché donné.

## Marchés locaux IBM Direct Link étendus
{: #announce-expanded-ibm-direct-link-local-markets}

Nous étendons nos marchés locaux Direct Link afin de fournir davantage d'options de routage local à nos clients dans le monde. Les nouvelles affectations de marché local sont répertoriées ci-après :

* Le marché local de Dallas inclura désormais les points de présence de Denver, Houston et Chicago.
* Le marché local de Washington DC inclura désormais les points de présence de New York, Atlanta et Miami.
* Le marché local de San José inclura désormais le point de présence de Los Angeles.
* Le marché local d'Oslo inclura désormais le point de présence de Stockholm.
* Le marché local de Sydney inclura désormais le point de présence de Perth.
* Le marché local de Hong Kong inclura le point de présence de Taipei une fois celui-ci lancé.
* Le marché local de Tokyo inclura le point de présence d'Osaka une fois celui-ci lancé.
* Le marché local de Chennai inclura le point de présence de Mombai une fois celui-ci lancé.

Ces changements sont présentés dans des tableaux à l'adresse suivante : https://cloud.ibm.com/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#expanded-ibm-direct-link-local-markets

## Routage mondial IBM Cloud Direct Link - Modèle de tarification
{: #announce-ibm-cloud-direct-link-global-routing-pricing-model}

Pour l'ensemble des offres IBM Cloud Direct Link, le routage au sein d'un marché local est standard. Effective à compter du 1er juillet 2019, la tarification de l'option Routage mondial est en cours d'alignement sur la vitesse de la connexion Direct Link. Cet alignement assurera une meilleure valeur aux clients sur l'ensemble des vitesses de connexion disponibles pour les offres Direct Link.

La tarification est accessible à l'adresse https://cloud.ibm.com/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-global-routing-add-on

## Routage mondial IBM Cloud Direct Link - Frais supplémentaires liés au transit réseau
{: #announce-ibm-cloud-direct-link-global-routing-network-transit-overage-charges}

Dans le cadre de cette annonce, nous retirons les limites et les frais supplémentaires liés au transit réseau pour les clients bénéficiant de l'option Routage mondial. La tarification précédente incluait des franchises et des frais supplémentaires de transit réseau pour le trafic sortant hors du marché local du client. La nouvelle tarification supprime des frais de trafic réseau. Effective à compter de cette annonce, le trafic entrant et sortant sur les connexions Direct Link n'engendrera pas de dépassement.

## Date d'effet
{: #announce-effective-date}

Ces changements seront effectifs le lundi 1er juillet 2019 et seront appliqués à toute nouvelle commande passée sur le prochain cycle de facturation à compter de cette date.

Il est important de noter que, grâce à la mise à jour de cette automatisation, tout circuit Direct Link nécessitant le routage mondial devrait être mis à jour de manière appropriée avant cette date. Les mises à niveau et rétromigrations d'un service Direct Link se traduira par la vérification automatique de la présence du routage mondiale. Si le routage mondial n'est pas présent, tout trafic sur des circuits Direct Link sera restreint aux marchés locaux. 

Nous encourageons vivement les clients à vérifier leur routage IBM Cloud sur des services Direct Link et à ouvrir des tickets afin remédier aux éventuels problèmes de routage sur des services Direct Link existants.
