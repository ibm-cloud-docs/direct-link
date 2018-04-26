---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-12"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# A propos d'IBM Cloud Direct Link

Cette section fournit des détails supplémentaires sur les fonctions principales et les avantages de chacune des quatre offres IBM Cloud Direct Link.
  * [**IBM Cloud Direct Link Exchange**](#the-ibm-cloud-direct-link-exchange-solution)
  * [**IBM Cloud Direct Link Connect**](#the-ibm-cloud-direct-link-connect-solution)
  * [**IBM Cloud Direct Link Dedicated**](#the-ibm-cloud-direct-link-dedicated-solution)
  * [**IBM Cloud Direct Link Dedicated Hosting**](#the-ibm-cloud-direct-link-dedicated-hosting-solution)

## La solution IBM Cloud Direct Link Exchange

La solution IBM Cloud Direct Link Exchange permet aux clients de tirer parti d'un fournisseur Cloud Exchange pour fournir la connectivité à {{site.data.keyword.BluSoftlayer_notm}}. Cette offre fournit en général une connectivité à coût réduit, car la connectivité physique de {{site.data.keyword.BluSoftlayer_notm}} au fournisseur Cloud Exchange est déjà en place, partagée avec d'autres clients.

**Cas d'utilisation courants :** _Idéal pour les charges de travail hybrides, les charges de travail inter-fournisseurs, les transferts de données volumineux ou fréquents, les charges de travail privées et l'administration d'environnement.  En général, cette option est sélectionnée lorsque le point de présence (PoP) possède déjà le fournisseur IBM Cloud Direct Link Exchange souhaité._

![Figure 1](/images/Direct-Link-Exchange.PNG)

 * **Emplacement de terminaison : point de présence (PoP) ** {{site.data.keyword.BluSoftlayer_notm}}.

 * **Délai de déploiement typique :** pour le fournisseur Equinix, le délai de déploiement typique sera de quelques heures. Pour les autres fournisseurs, il sera de 5 à 10 jours après que le circuit a atteint l'échange et de 30 à 60 jours en tout, selon votre emplacement et vos besoins.

 * **Détails d'interconnexion :** Les interconnexions physiques pour l'interconnexion avec Cloud Exchange sont conservées entre {{site.data.keyword.BluSoftlayer_notm}} et le fournisseur Cloud Exchange. Les clients demandent un "circuit virtuel" auprès du fournisseur Cloud Exchange, ce qui établit la connectivité logique à {{site.data.keyword.BluSoftlayer_notm}}, une fois qu'ils sont interconnectés au fournisseur Cloud Exchange.

 * **Options de vitesses de port :** Sélectionnez 50 Mbit/s, 100 Mbit/s, 200 Mbit/s, 500 Mbit/s ou 1 Gbit/s.

 * **Temps d'attente approximatif :** Le temps d'attente est d'environ 1,5 ms dans la zone locale (centres de données avec le même préfixe à trois lettres, tel que DAL, AMS, MEL, etc). Voir http://lg.softlayer.com/ pour obtenir les mesures de temps d'attente P2P (PoP-to-PoP) en vigueur.

 * **Services de colocalisation :** Aucun.

 * **Redondance :** Pour établir la redondance pour IBM Cloud Direct Link Exchange, la connectivité à 2 emplacements ou plus est requise, ou la sélection d'un emplacement avec un routeur XCR secondaire disponible dont le fournisseur Cloud Exchange peut tirer parti.

 * **Options de routage local/mondial :** L'option de routage local fournit l'accès aux centres de données avec le même préfixe à trois lettres, tel que le PoP (DAL, AMS, MEL, etc). L'option de routage mondial est requise comme module complémentaire pour accéder aux centres de données en dehors de ces emplacements.
 
## La solution IBM Cloud Direct Link Connect

**Cas d'utilisation courants** Similaires à la solution Direct Link Exchange. Offre un plus grand nombre de vitesses possibles. Un bon point d'entrée à moindre coût.

![Figure 2](/images/Direct-Link-Connect.PNG)

* **Emplacement de terminaison : point de présence (PoP) ** {{site.data.keyword.BluSoftlayer_notm}}.

* **Délai de déploiement standard :** 5 à 10 jours une fois que le circuit a accédé à l'échange. Le délai de déploiement peut prendre de 30 à 60 jours au total, en fonction de votre implantation et des exigences.

* **Détails d'interconnexion :** Les interconnexions physiques pour l'interconnexion avec Cloud Connect sont conservées entre {{site.data.keyword.BluSoftlayer_notm}} et le fournisseur Cloud Connect. Les clients demandent un "circuit virtuel" auprès du fournisseur Cloud Connect, qui établit la connectivité logique à {{site.data.keyword.BluSoftlayer_notm}}, une fois qu'ils sont interconnectés au fournisseur Cloud Connect.

* **Options de vitesses de port :** Sélectionnez 50 Mbit/s, 100 Mbit/s, 200 Mbit/s, 500 Mbit/s, 1 Gbit/s, 2 Gbit/s ou 5 Gbit/s.

* **Temps d'attente approximatif :** Le temps d'attente est d'environ 1,5 ms dans la zone locale (centres de données avec le même préfixe à trois lettres, tel que DAL, AMS, MEL, etc). Voir http://lg.softlayer.com/ pour obtenir les mesures de temps d'attente P2P (PoP-to-PoP) en vigueur.

* **Services de colocalisation :** Aucun.

* **Redondance :** Pour établir la redondance pour IBM Cloud Direct Link Connect, la connectivité à 2 emplacements ou plus est requise, ou la sélection d'un emplacement avec un routeur XCR secondaire disponible dont le fournisseur Cloud Connect peut tirer parti.

* **Options de routage local/mondial :** L'option de routage local fournit l'accès aux centres de données avec le même préfixe à trois lettres, tel que le PoP (DAL, AMS, MEL, etc). L'option de routage mondial est requise comme module complémentaire pour accéder aux centres de données en dehors de ces emplacements.

## La solution IBM Cloud Direct Link Dedicated

La solution IBM Cloud Direct Link Dedicated  permet aux clients de terminer une interconnexion fibre dédiée en mode unique dans leur propre réseau privé {{site.data.keyword.BluSoftlayer_notm}}.

 **Cas d'utilisation courants :** _Idéal pour travailler avec des charges de travail hybrides, des charges de travail inter-fournisseurs, des transferts de données volumineux ou fréquents, des charges de travail privées et l'administration d'environnement. En général, cette option est sélectionnée : (1) lorsque le PoP souhaité n'a pas le fournisseur IBM Cloud Direct Link Exchange souhaité, (2) pour les charges de travail à hautes performances qui nécessitent un débit élevé ou (3) pour les exigences en matière de conformité qui ne peuvent pas être satisfaites par le modèle d'implémentation d'IBM Cloud Direct Link Exchange._

![Figure 3](/images/Direct-link-Dedicated.PNG)

 * **Emplacement de terminaison : point de présence (PoP) ** {{site.data.keyword.BluSoftlayer_notm}}.

 * **Délai de déploiement standard :** 10 à 15 jours ouvrables une fois que le nouveau circuit a accédé au PoP. Le délai de déploiement peut prendre de 30 à 60 jours au total, en fonction de votre implantation et des exigences.

 * **Détails d'interconnexion :** {{site.data.keyword.BluSoftlayer_notm}} fournit une lettre d'autorisation (LOA) utilisée par un client pour commander l'Ethernet fibre (fibre en mode unique seulement, optiques 1Gig-LX ou 10Gig-LR) qui s'exécute d'un fournisseur ou d'une cage client vers le point de terminaison CFA {{site.data.keyword.BluSoftlayer_notm}}, qui sera relié à l'infrastructure du routeur d'interconnexion (XCR). Le support doit être une fibre optique avec une longueur d'onde de 1310nm.

 * **Options de vitesses de port :** Sélectionnez 1 Gbit/s, 2 Gbit/s, 5 Gbit/s ou 10 Gbit/s.

 * **Temps d'attente approximatif :** Le temps d'attente est d'environ 1,5 ms dans la zone locale (centres de données avec le même préfixe à trois lettres, tel que DAL, AMS, MEL, etc).  Voir http://lg.softlayer.com/ pour obtenir les mesures de temps d'attente P2P (PoP-to-PoP) en vigueur.

 * **Services de colocalisation :** Aucun.

 * **Redondance :** Pour établir la redondance, une connectivité IBM Cloud Direct Link à 2 emplacements ou plus est requise, ou la sélection d'un emplacement avec un routeur XCR secondaire disponible et une seconde demande de connexion IBM Cloud Direct Link.

 * **Options de routage local/mondial :** L'option de routage local fournit l'accès aux centres de données avec le même préfixe à trois lettres, tel que le PoP (DAL, AMS, MEL, etc). L'option de routage mondial est requise comme module complémentaire pour accéder aux centres de données en dehors de ces emplacements.

## La solution IBM Cloud Direct Link Dedicated Hosting

La solution IBM Cloud Direct Link Dedicated Hosting offre une connectivité similaire à IBM Cloud Direct Link Dedicated, mais le point de connexion est adjacent à un centre de données {{site.data.keyword.BluSoftlayer_notm}}, ce qui améliores le temps d'attente pour les cas d'utilisation à performance accrue. IBM Cloud offre une large gamme de services de colocalisation personnalisables avec cette solution.

**Cas d'utilisation courants :** _Idéal pour travailler avec des technologies de calcul qui ne sont pas standard, pour les exigences en matière de stockage dédié ou pour tirer parti des investissements informatiques existants._

![Figure 4](/images/Direct-Link-Dedicated-Hosting.png)

* **Emplacement de terminaison :** Centre de données {{site.data.keyword.BluSoftlayer_notm}}.

 * **Délai de déploiement standard :** 30 à 60 jours une fois toutes les exigences satisfaites et les contrats exécutés.

 * **Détails d'interconnexion :** {{site.data.keyword.BluSoftlayer_notm}} fournit des connexions fibre 1G ou 10G de l'infrastructure du routeur interconnexion (XRC) {{site.data.keyword.BluSoftlayer_notm}} à l'environnement de colocalisation du client dans le cadre du déploiement. Si les services de colocalisation ne sont pas demandés (si les environnements existants sont déjà connectés), {{site.data.keyword.BluSoftlayer_notm}} fournit une lettre d'autorisation (LOA) utilisée par le client pour commander l'Ethernet fibre (fibre en mode unique seulement, optiques 1Gig-LX ou 10Gig-LR) qui s'exécute d'une cage client vers le point de terminaison CFA {{site.data.keyword.BluSoftlayer_notm}}, qui sera relié à l'infrastructure du routeur d'interconnexion (XCR). Le support doit être une fibre optique avec une longueur d'onde de 1310nm.

 * **Options de vitesses de port :** Sélectionnez 1 Gbit/s, 2 Gbit/s, 5 Gbit/s ou 10 Gbit/s.

 * **Temps d'attente approximatif :** Le temps d'attente est d'environ 0,5 ms dans le centre données local.

 * **Services de colocalisation :** Oui.

 * **Redondance :** {{site.data.keyword.BluSoftlayer_notm}} fournit des connexions à deux routeurs d'interconnexion (XCR) avec le produit. Pour établir une connectivité redondante, les clients configurent BGP avec ECMP (Equal-Cost Multipath).

 * **Options de routage local/mondial :** L'option de routage local fournit l'accès aux centres de données avec le même préfixe à trois lettres, tel que le PoP (DAL, AMS, MEL, etc). L'option de routage mondial est requise comme module complémentaire pour accéder aux centres de données en dehors de ces emplacements.
