---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-29"

keywords: hybrid, solutions, features, benefits, port speed, cross-connect, use cases, latency, routing, options, colocation

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# A propos d'IBM Cloud Direct Link
{: #about-ibm-cloud-direct-link}

Cette section fournit des détails supplémentaires sur les fonctions principales et les avantages de chacune des quatre solutions {{site.data.keyword.cloud}} Direct Link.
  * [**IBM Cloud Direct Link Exchange**](#direct-link-exchange-solution)
  * [**IBM Cloud Direct Link Connect**](#direct-link-connect-solution)
  * [**IBM Cloud Direct Link Dedicated**](#direct-link-dedicated-solution)
  * [**IBM Cloud Direct Link Dedicated Hosting**](#direct-link-dedicated-hosting-solution)

## La solution IBM Cloud Direct Link Exchange
{: #direct-link-exchange-solution}

La solution IBM Cloud Direct Link Exchange permet aux clients d'utiliser un fournisseur Cloud Exchange pour fournir la connectivité à des emplacements {{site.data.keyword.cloud_notm}}. Cette offre fournit en général une connectivité à coût réduit, car la connectivité physique de {{site.data.keyword.cloud_notm}} au fournisseur Cloud Exchange est déjà en place, partagée avec d'autres clients.

**Cas d'utilisation courants :** _Idéal pour les charges de travail hybrides, les charges de travail inter-fournisseurs, les transferts de données volumineux ou fréquents avec une bande passante sortante élevée, les charges de travail privées et l'administration d'environnement.  En général, cette option est sélectionnée lorsque l'emplacement de point de présence souhaité possède déjà le fournisseur IBM Cloud Direct Link Exchange souhaité._

![Figure 1](/images/Direct-Link-Exchange.png)

 * **Emplacement de terminaison : point de présence (PoP) ** {{site.data.keyword.cloud_notm}}.

 * **Délai de déploiement typique :** pour les fournisseurs Equinix, le délai de déploiement typique sera de quelques heures. Pour les autres fournisseurs, il sera de 5 à 10 jours après que le circuit a atteint l'échange. Il pourra être de 30 à 60 jours en tout, selon votre emplacement et vos besoins lorsque vous commandez un circuit à partir d'un NSP ou d'un transporteur.

 * **Détails d'interconnexion :** les interconnexions physiques pour l'interconnexion sécurisée avec Cloud Exchange sont conservées entre {{site.data.keyword.cloud_notm}} et le fournisseur Cloud Exchange. Les clients demandent un "circuit virtuel" auprès du fournisseur Cloud Exchange, ce qui établit la connectivité logique à {{site.data.keyword.cloud_notm}}, une fois le client interconnecté au fournisseur Cloud Exchange.

 * **Options de vitesses de port :** Sélectionnez 50 Mbit/s, 100 Mbit/s, 200 Mbit/s, 500 Mbit/s, 1 Gbit/s, 2 Gbit/s ou 5 Gbit/s.

 * **Temps d'attente approximatif :** le temps d'attente est d'environ 1,5 ms dans la zone locale (centres de données avec le même préfixe à trois lettres, tel que DAL, AMS, MEL). Voir http://lg.softlayer.com/ pour obtenir les mesures de temps d'attente d'emplacement P2P (PoP-to-PoP) en vigueur.

 * **Services de colocalisation IBM :** Aucun.

 * **Redondance :** {{site.data.keyword.cloud_notm}} fournit des connexions à deux (2) routeurs d'interconnexion (XCR) différents avec le produit. Pour établir la connectivité redondante, les clients doivent configurer le protocole BGP sur chaque connexion Direct Link à leur convenance. Citons par exemple les options suivantes : _prefer Lowest MED_, _prefer highest local-preference_ ou _prefer shorter AS paths_.

 * **Options de routage local/mondial :** l'option Routage local est l'option de routage par défaut. Elle offre un accès aux centres de données au sein du même marché que le point de présence de Direct Link (désigné, par exemple, par DAL, AMS ou MEL). L'option Routage mondial est nécessaire en tant qu'extension pour connecter vos ressources IBM Cloud à d'autres ressources IBM Cloud dans des centres de données situées en dehors du marché local. Elle fournit un moyen de partager des charges de travail entre les ressources IBM Cloud (par exemple Dallas à Ashburn, ou Dallas à Francfort).
 
## La solution IBM Cloud Direct Link Connect
{: #direct-link-connect-solution}

**Cas d'utilisation courants :** _La solution IBM Cloud Direct Link Connect permet aux clients d'optimiser un fournisseur de services réseau (NSP) pour fournir la connectivité à des emplacements {{site.data.keyword.cloud_notm}}. Cette offre fournit en général une connectivité à coût réduit, car la connectivité physique depuis {{site.data.keyword.cloud_notm}} vers le fournisseur de services réseau est déjà en place, partagée avec d'autres clients._ 

![Figure 2](/images/Direct-Link-Connect.png)

* **Emplacement de terminaison : point de présence (PoP) ** {{site.data.keyword.cloud_notm}}.

* **Délai de déploiement standard :** Le délai de déploiement sera de 5 à 10 jours une fois que le circuit a atteint l'échange. Il pourra être de 30 à 60 jours en tout, selon votre emplacement et vos besoins lorsque vous commandez un circuit à partir d'un NSP ou d'un transporteur.

* **Détails d'interconnexion :** Les interconnexions physiques pour l'interconnexion sécurisée avec Direct Link Connect sont conservées entre {{site.data.keyword.cloud_notm}} et le fournisseur Connect. Les clients demandent un "circuit virtuel" auprès du fournisseur Cloud Connect, ce qui établit la connectivité logique à {{site.data.keyword.cloud_notm}}, une fois le client interconnecté au fournisseur Cloud Connect.

* **Options de vitesses de port :** Sélectionnez 50 Mbit/s, 100 Mbit/s, 200 Mbit/s, 500 Mbit/s, 1 Gbit/s, 2 Gbit/s ou 5 Gbit/s.

* **Temps d'attente approximatif :** Le temps d'attente est d'environ 1,5 ms dans la zone locale (centres de données avec le même préfixe à trois lettres, tel que DAL, AMS, MEL). Voir http://lg.softlayer.com/ pour obtenir les mesures de temps d'attente d'emplacement P2P (PoP-to-PoP) en vigueur.

* **Services de colocalisation IBM :** Aucun.

* **Redondance :** {{site.data.keyword.cloud_notm}} fournit des connexions à deux (2) routeurs d'interconnexion (XCR) différents avec le produit. Pour établir la connectivité redondante, les clients doivent configurer le protocole BGP sur chaque connexion Direct Link à leur convenance. Citons par exemple les options suivantes : _prefer Lowest MED_, _prefer highest local-preference_ ou _prefer shorter AS paths_.

* **Options de routage local/mondial :** l'option Routage local est l'option de routage par défaut. Elle offre un accès aux centres de données au sein du même marché que le point de présence de Direct Link (désigné, par exemple, par DAL, AMS ou MEL). L'option Routage mondial est nécessaire en tant qu'extension pour connecter vos ressources IBM Cloud à d'autres ressources IBM Cloud dans des centres de données situées en dehors du marché local. Elle est utilisée pour partager des charges de travail entre les ressources IBM Cloud (par exemple Dallas à Ashburn, ou Dallas à Francfort).

## La solution IBM Cloud Direct Link Dedicated
{: #direct-link-dedicated-solution}

La solution IBM Cloud Direct Link Dedicated permet aux clients de terminer une interconnexion fibre à service exclusif sur leur propre connexion réseau privé {{site.data.keyword.cloud_notm}}. Cette offre peut être utilisée par des clients disposant d'installations de colocalisation adjacents aux points de présence et centres de données IBM Cloud ; il en est de même pour les fournisseurs de services réseau délivrant des circuits dans les locaux ou d'autres centres de données des clients.

 **Cas d'utilisation courants :** _Idéal pour travailler avec des charges de travail hybrides, des charges de travail inter-fournisseurs, des transferts de données volumineux ou fréquents, des charges de travail privées et l'administration d'environnement. En général, cette option est sélectionnée : (1) lorsque le PoP souhaité n'a pas le fournisseur Exchange ou le fournisseur de services réseau souhaité, (2) pour les charges de travail à hautes performances qui nécessitent un débit élevé ou (3) pour les exigences en matière de conformité qui ne peuvent pas être satisfaites par le modèle d'implémentation d'IBM Cloud Direct Link Exchange ou Connect._
 
 **Cas d'utilisation 1 : Installation client vers IBM Cloud.**

![Figure 3](/images/Direct-link-Dedicated.png)

**Cas d'utilisation 2 : Colocalisation du client vers IBM Cloud.**

![Figure 3B](/images/dedicated-model-colo.png)

 * **Emplacement de terminaison :** Point de présence (PoP) ou centre de données (DC) {{site.data.keyword.cloud_notm}}.

 * **Délai de déploiement standard :** Le délai de déploiement sera de 10 à 15 jours ouvrables une fois que le nouveau circuit a atteint le point de présence. Il pourra être de 30 à 60 jours en tout, selon votre emplacement et vos besoins lorsque vous commandez un circuit à partir d'un NSP ou d'un transporteur.

 * **Détails d'interconnexion :** {{site.data.keyword.cloud_notm}} fournit une lettre d'autorisation (LOA) utilisée par un client pour commander l'Ethernet fibre (fibre en mode unique seulement, optiques 1Gig-LX ou 10Gig-LR) qui s'exécute d'une fournisseur ou client vers le point de terminaison CFA {{site.data.keyword.cloud_notm}}, qui sera relié à l'infrastructure du routeur d'interconnexion (XCR). Le support doit être une fibre optique avec une longueur d'onde de 1310nm.

 * **Options de vitesses de port :** Sélectionnez 1 Gbit/s, 2 Gbit/s, 5 Gbit/s ou 10 Gbit/s.

 * **Temps d'attente approximatif :** le temps d'attente est d'environ 1,5 ms dans la zone locale (centres de données avec le même préfixe à trois lettres, tel que DAL, AMS, MEL).  Voir http://lg.softlayer.com/ pour obtenir les mesures de temps d'attente d'emplacement P2P (PoP-to-PoP) en vigueur.

 * **Services de colocalisation IBM :** Aucun.

 * **Redondance :** {{site.data.keyword.cloud_notm}} fournit des connexions à deux (2) routeurs d'interconnexion (XCR) différents avec le produit. Pour établir la connectivité redondante, les clients doivent configurer le protocole BGP sur chaque connexion Direct Link à leur convenance. Citons par exemple les options suivantes : _prefer Lowest MED_, _prefer highest local-preference_ ou _prefer shorter AS paths_.

 * **Options de routage local/mondial :** l'option Routage local est l'option de routage par défaut. Elle offre un accès aux centres de données au sein du même marché que le point de présence de Direct Link (désigné, par exemple, par DAL, AMS ou MEL). L'option Routage mondial est nécessaire en tant qu'extension pour connecter vos ressources IBM Cloud à d'autres ressources IBM Cloud dans des centres de données situées en dehors du marché local. Elle fournit un moyen de partager des charges de travail entre les ressources IBM Cloud (par exemple Dallas à Ashburn, ou Dallas à Francfort).

## La solution IBM Cloud Direct Link Dedicated Hosting
{: #direct-link-dedicated-hosting-solution}

La solution IBM Cloud Direct Link Dedicated Hosting offre une connectivité similaire à IBM Cloud Direct Link Dedicated, mais le point de connexion est adjacent à un centre de données {{site.data.keyword.cloud_notm}}, ce qui améliores le temps d'attente pour les cas d'utilisation à performance accrue. IBM Cloud offre une large gamme de services de colocalisation personnalisables avec cette solution, avec une tarification simple.

**Cas d'utilisation courants :** _Idéal pour travailler avec des technologies de calcul qui ne sont pas standard, pour les exigences en matière de stockage dédié ou pour tirer parti des investissements informatiques existants._

![Figure 4](/images/Direct-Link-Dedicated-Hosting.png)

* **Emplacement de terminaison :** Centre de données {{site.data.keyword.cloud_notm}}.

 * **Délai de déploiement standard :** 30 à 60 jours une fois toutes les exigences satisfaites et les contrats exécutés.

 * **Détails d'interconnexion :** {{site.data.keyword.cloud_notm}} fournit des connexions fibre 1G ou 10G de l'infrastructure du routeur interconnexion (XRC) {{site.data.keyword.cloud_notm}} à l'environnement de colocalisation du client dans le cadre du déploiement.  Si les services de colocalisation ne sont pas demandés (si les environnements existants sont déjà connectés), {{site.data.keyword.cloud_notm}} fournit une lettre d'autorisation (LOA) utilisée par le client pour commander l'Ethernet fibre (fibre en mode unique seulement, optiques 1Gig-LX ou 10Gig-LR) qui s'exécute d'une cage client vers le point de terminaison CFA {{site.data.keyword.cloud_notm}}, qui sera relié à l'infrastructure du routeur d'interconnexion (XCR). Le support doit être une fibre optique avec une longueur d'onde de 1310nm.

 * **Options de vitesses de port :** Sélectionnez 1 Gbit/s, 2 Gbit/s, 5 Gbit/s ou 10 Gbit/s.

 * **Temps d'attente approximatif :** le temps d'attente est d'environ 0,5 ms dans le centre données local.

 * **Services de colocalisation IBM :** Oui.

 * **Redondance :** {{site.data.keyword.cloud_notm}} fournit des connexions à deux (2) routeurs d'interconnexion (XCR) différents avec le produit. Pour établir la connectivité redondante, les clients doivent configurer le protocole BGP sur chaque connexion Direct Link à leur convenance. Citons par exemple les options suivantes : _prefer Lowest MED_, _prefer highest local-preference_ ou _prefer shorter AS paths_.

 * **Options de routage local/mondial :** l'option Routage local est l'option de routage par défaut. Elle offre un accès aux centres de données au sein du même marché que le point de présence de Direct Link (désigné, par exemple, par DAL, AMS ou MEL). L'option Routage mondial est nécessaire en tant qu'extension pour connecter vos ressources IBM Cloud à d'autres ressources IBM Cloud dans des centres de données situées en dehors du marché local. Elle est utilisée pour partager des charges de travail entre les ressources IBM Cloud (par exemple Dallas à Ashburn, ou Dallas à Francfort).
