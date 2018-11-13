---

copyright:
  years: 2017, 2018
lastupdated: "2018-08-09"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# A propos d'IBM Cloud Direct Link

Cette section fournit des détails supplémentaires sur les fonctions principales et les avantages de chacune des quatre solutions IBM Cloud Direct Link.
  * [**IBM Cloud Direct Link Exchange**](#the-ibm-cloud-direct-link-exchange-solution)
  * [**IBM Cloud Direct Link Connect**](#the-ibm-cloud-direct-link-connect-solution)
  * [**IBM Cloud Direct Link Dedicated**](#the-ibm-cloud-direct-link-dedicated-solution)
  * [**IBM Cloud Direct Link Dedicated Hosting**](#the-ibm-cloud-direct-link-dedicated-hosting-solution)

## La solution IBM Cloud Direct Link Exchange

La solution IBM Cloud Direct Link Exchange permet aux clients d'optimiser un fournisseur Cloud Exchange pour fournir la connectivité à des emplacements {{site.data.keyword.BluSoftlayer_notm}}. Cette offre fournit en général une connectivité à coût réduit, car la connectivité physique de {{site.data.keyword.BluSoftlayer_notm}} au fournisseur Cloud Exchange est déjà en place, partagée avec d'autres clients.

**Cas d'utilisation courants :** _Idéal pour les charges de travail hybrides, les charges de travail inter-fournisseurs, les transferts de données volumineux ou fréquents avec une bande passante sortante élevée, les charges de travail privées et l'administration d'environnement.  En général, cette option est sélectionnée lorsque l'emplacement de point de présence souhaité possède déjà le fournisseur IBM Cloud Direct Link Exchange souhaité._

![Figure 1](/images/Direct-Link-Exchange.png)

 * **Emplacement de terminaison : point de présence (PoP) ** {{site.data.keyword.BluSoftlayer_notm}}.

 * **Délai de déploiement typique :** pour les fournisseurs Equinix, le délai de déploiement typique sera de quelques heures. Pour les autres fournisseurs, il sera de 5 à 10 jours après que le circuit a atteint l'échange. Il pourra être de 30 à 60 jours en tout, selon votre emplacement et vos besoins lorsque vous commandez un circuit à partir d'un NSP ou d'un transporteur.

 * **Détails d'interconnexion :** les interconnexions physiques pour l'interconnexion sécurisée avec Cloud Exchange sont conservées entre {{site.data.keyword.BluSoftlayer_notm}} et le fournisseur Cloud Exchange. Les clients demandent un "circuit virtuel" auprès du fournisseur Cloud Exchange, ce qui établit la connectivité logique à {{site.data.keyword.BluSoftlayer_notm}}, une fois qu'ils sont interconnectés au fournisseur Cloud Exchange.

 * **Options de vitesses de port :** Sélectionnez 50 Mbit/s, 100 Mbit/s, 200 Mbit/s, 500 Mbit/s ou 1 Gbit/s.

 * **Temps d'attente approximatif :** le temps d'attente est d'environ 1,5 ms dans la zone locale (centres de données avec le même préfixe à trois lettres, tel que DAL, AMS, MEL). Voir http://lg.softlayer.com/ pour obtenir les mesures de temps d'attente d'emplacement P2P (PoP-to-PoP) en vigueur.

 * **Services de colocalisation :** Aucun.

 * **Redondance :** Pour établir la redondance pour IBM Cloud Direct Link Exchange, la connectivité à 2 emplacements ou plus est requise, ou la sélection d'un emplacement avec un routeur XCR secondaire disponible dont le fournisseur Cloud Exchange peut tirer parti.

 * **Options de routage local/mondial :** l'option Routage local est l'option de routage par défaut. Elle offre un accès aux centres de données au sein du même marché que le point de présence de Direct Link (désigné, par exemple, par DAL, AMS ou MEL). L'option Routage mondial est nécessaire en tant qu'extension pour connecter les ressources IBM Cloud de votre marché interne à d'autres ressources IBM Cloud dans des centres de données situées en dehors du marché local. Elle est utilisée pour partager des charges de travail entre les ressources IBM Cloud (par exemple Dallas à Ashburn, ou Dallas à Francfort).
 
## La solution IBM Cloud Direct Link Connect

**Cas d'utilisation courants** Similaires à la solution Direct Link Exchange. Offre un plus grand nombre de vitesses possibles. La solution Direct Link Cloud Connect fournit un point d'entrée de plus faible coût pour les clients IBM Cloud.

![Figure 2](/images/Direct-Link-Connect.png)

* **Emplacement de terminaison : point de présence (PoP) ** {{site.data.keyword.BluSoftlayer_notm}}.

* **Délai de déploiement standard :** le délai de déploiement sera de 5 à 10 jours une fois que le circuit a atteint l'échange. Il pourra être de 30 à 60 jours en tout, selon votre emplacement et vos besoins lorsque vous commandez un circuit à partir d'un NSP ou d'un transporteur.

* **Détails d'interconnexion :** les interconnexions physiques pour l'interconnexion sécurisée avec Direct Link Connect sont conservées entre {{site.data.keyword.BluSoftlayer_notm}} et le fournisseur Connect. Les clients demandent un "circuit virtuel" auprès du fournisseur Cloud Connect, qui établit la connectivité logique à {{site.data.keyword.BluSoftlayer_notm}}, une fois qu'ils sont interconnectés au fournisseur Cloud Connect.

* **Options de vitesses de port :** Sélectionnez 50 Mbit/s, 100 Mbit/s, 200 Mbit/s, 500 Mbit/s, 1 Gbit/s, 2 Gbit/s ou 5 Gbit/s.

* **Temps d'attente approximatif :** le temps d'attente est d'environ 1,5 ms dans la zone locale (centres de données avec le même préfixe à trois lettres, tel que DAL, AMS, MEL). Voir http://lg.softlayer.com/ pour obtenir les mesures de temps d'attente d'emplacement P2P (PoP-to-PoP) en vigueur.

* **Services de colocalisation :** Aucun.

* **Redondance :** afin d'établir la redondance pour IBM Cloud Direct Link Connect, la connectivité à 2 emplacements ou plus est requise, ou la sélection d'un emplacement avec un routeur XCR secondaire disponible dont le fournisseur IBM Cloud Connect peut tirer parti.

* **Options de routage local/mondial :** l'option Routage local est l'option de routage par défaut. Elle offre un accès aux centres de données au sein du même marché que le point de présence de Direct Link (désigné, par exemple, par DAL, AMS ou MEL). L'option Routage mondial est nécessaire en tant qu'extension pour connecter les ressources IBM Cloud de votre marché interne à d'autres ressources IBM Cloud dans des centres de données situées en dehors du marché local. Elle est utilisée pour partager des charges de travail entre les ressources IBM Cloud (par exemple Dallas à Ashburn, ou Dallas à Francfort).

## La solution IBM Cloud Direct Link Dedicated

La solution IBM Cloud Direct Link Dedicated permet aux clients de terminer une interconnexion fibre dédiée en mode unique dans leur propre réseau privé {{site.data.keyword.BluSoftlayer_notm}}.

 **Cas d'utilisation courants :** _Idéal pour travailler avec des charges de travail hybrides, des charges de travail inter-fournisseurs, des transferts de données volumineux ou fréquents, des charges de travail privées et l'administration d'environnement.  En général, cette option est sélectionnée : (1) lorsque le PoP souhaité n'a pas le fournisseur IBM Cloud Direct Link Exchange souhaité, (2) pour les charges de travail à hautes performances qui nécessitent un débit élevé ou (3) pour les exigences en matière de conformité qui ne peuvent pas être satisfaites par le modèle d'implémentation d'IBM Cloud Direct Link Exchange._

![Figure 3](/images/Direct-link-Dedicated.png)

 * **Emplacement de terminaison : point de présence (PoP) ** {{site.data.keyword.BluSoftlayer_notm}}.

 * **Délai de déploiement standard :** le délai de déploiement sera de 10 à 15 jours ouvrables une fois que le nouveau circuit a atteint le point de présence. Il pourra être de 30 à 60 jours en tout, selon votre emplacement et vos besoins lorsque vous commandez un circuit à partir d'un NSP ou d'un transporteur.

 * **Détails d'interconnexion :** {{site.data.keyword.BluSoftlayer_notm}} fournit une lettre d'autorisation (LOA) utilisée par un client pour commander l'Ethernet fibre (fibre en mode unique seulement, optiques 1Gig-LX ou 10Gig-LR) qui s'exécute d'un fournisseur ou d'une cage client vers le point de terminaison CFA {{site.data.keyword.BluSoftlayer_notm}}, qui sera relié à l'infrastructure du routeur d'interconnexion (XCR). Le support doit être une fibre optique avec une longueur d'onde de 1310nm.

 * **Options de vitesses de port :** Sélectionnez 1 Gbit/s, 2 Gbit/s, 5 Gbit/s ou 10 Gbit/s.

 * **Temps d'attente approximatif :** le temps d'attente est d'environ 1,5 ms dans la zone locale (centres de données avec le même préfixe à trois lettres, tel que DAL, AMS, MEL).  Voir http://lg.softlayer.com/ pour obtenir les mesures de temps d'attente d'emplacement P2P (PoP-to-PoP) en vigueur.

 * **Services de colocalisation :** Aucun.

 * **Redondance :** Pour établir la redondance, une connectivité IBM Cloud Direct Link à 2 emplacements ou plus est requise, ou la sélection d'un emplacement avec un routeur XCR secondaire disponible et une seconde demande de connexion IBM Cloud Direct Link.

 * **Options de routage local/mondial :** l'option Routage local est l'option de routage par défaut. Elle offre un accès aux centres de données au sein du même marché que le point de présence de Direct Link (désigné, par exemple, par DAL, AMS ou MEL). L'option Routage mondial est nécessaire en tant qu'extension pour connecter les ressources IBM Cloud de votre marché interne à d'autres ressources IBM Cloud dans des centres de données situées en dehors du marché local. Elle est utilisée pour partager des charges de travail entre les ressources IBM Cloud (par exemple Dallas à Ashburn, ou Dallas à Francfort).

## La solution IBM Cloud Direct Link Dedicated Hosting

La solution IBM Cloud Direct Link Dedicated Hosting offre une connectivité similaire à IBM Cloud Direct Link Dedicated, mais le point de connexion est adjacent à un centre de données {{site.data.keyword.BluSoftlayer_notm}}, ce qui améliores le temps d'attente pour les cas d'utilisation à performance accrue. IBM Cloud offre une large gamme de services de colocalisation personnalisables avec cette solution, avec une tarification simple.

**Cas d'utilisation courants :** _Idéal pour travailler avec des technologies de calcul qui ne sont pas standard, pour les exigences en matière de stockage dédié ou pour tirer parti des investissements informatiques existants._

![Figure 4](/images/Direct-Link-Dedicated-Hosting.png)

* **Emplacement de terminaison :** Centre de données {{site.data.keyword.BluSoftlayer_notm}}.

 * **Délai de déploiement standard :** 30 à 60 jours une fois toutes les exigences satisfaites et les contrats exécutés.

 * **Détails d'interconnexion :** {{site.data.keyword.BluSoftlayer_notm}} fournit des connexions fibre 1G ou 10G de l'infrastructure du routeur interconnexion (XRC) {{site.data.keyword.BluSoftlayer_notm}} à l'environnement de colocalisation du client dans le cadre du déploiement.  Si les services de colocalisation ne sont pas demandés (si les environnements existants sont déjà connectés), {{site.data.keyword.BluSoftlayer_notm}} fournit une lettre d'autorisation (LOA) utilisée par le client pour commander l'Ethernet fibre (fibre en mode unique seulement, optiques 1Gig-LX ou 10Gig-LR) qui s'exécute d'une cage client vers le point de terminaison CFA {{site.data.keyword.BluSoftlayer_notm}}, qui sera relié à l'infrastructure du routeur d'interconnexion (XCR). Le support doit être une fibre optique avec une longueur d'onde de 1310nm.

 * **Options de vitesses de port :** Sélectionnez 1 Gbit/s, 2 Gbit/s, 5 Gbit/s ou 10 Gbit/s.

 * **Temps d'attente approximatif :** le temps d'attente est d'environ 0,5 ms dans le centre données local.

 * **Services de colocalisation :** Oui.

 * **Redondance :** {{site.data.keyword.BluSoftlayer_notm}} fournit des connexions à deux routeurs d'interconnexion (XCR) avec le produit. Pour établir la connectivité redondante, les clients doivent configurer le protocole BGP sur chaque connexion Direct Link à leur convenance. Citons par exemple les options suivantes : _prefer Lowest MED_, _prefer highest local-preference_ ou _prefer shorter AS paths_.

 * **Options de routage local/mondial :** l'option Routage local est l'option de routage par défaut. Elle offre un accès aux centres de données au sein du même marché que le point de présence de Direct Link (désigné, par exemple, par DAL, AMS ou MEL). L'option Routage mondial est nécessaire en tant qu'extension pour connecter les ressources IBM Cloud de votre marché interne à d'autres ressources IBM Cloud dans des centres de données situées en dehors du marché local. Elle est utilisée pour partager des charges de travail entre les ressources IBM Cloud (par exemple Dallas à Ashburn, ou Dallas à Francfort).
