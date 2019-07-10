---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-02"

keywords: Dedicated, finalize, questionnaire, Special Network Services, billing, fees, VRF, BGP, ticket, cross-connect, link speed, VPN, data, center, PoP, ECMP

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Questionnaire concernant IBM Cloud Direct Link Dedicated
{: #ibm-cloud-direct-link-dedicated-questionnaire}

Merci d'avoir ouvert une demande pour {{site.data.keyword.cloud}} Direct Link Dedicated. Afin de pouvoir finaliser votre demande, nous aurions besoin d'informations supplémentaires. Vous pouvez parler avec un ingénieur à tout moment durant le questionnaire. Une fois le questionnaire rempli, il sera examiné par notre équipe d'ingénieurs spécialisés dans la conception de cloud et transmis aux spécialistes des réseaux pour implémentation.

## Reconnaissez-vous et acceptez-vous ce qui suit ?
{: #dedicated-do-you-agree}

1. Chaque connexion Direct Link nécessite une commande unique. Si vous avez besoin de plusieurs connexions, créez une commande Direct Link distincte pour chacune d'elles.

2. Les frais relatifs à Direct Link Connect couvrent le coût lié à la résiliation du service sur l'infrastructure IBM Cloud. 

 * Les services d'infrastructure sont facturés à l'avance et cette facturation commence dès l'acceptation de votre commande ; cependant, en raison de la nature d'IBM Cloud Direct Link, la facturation du service Direct Link commence lors du lancement d'une session BGP (Border Gateway Protocol) avec IBM Cloud, ou 30 jours après la communication de la clé de service au client. 

 * La facturation prend fin après :
   * qu'un client a demandé la suppression d'un circuit **et** 
   * que le fournisseur Exchange Provider ou Network Service Provider a annulé la mise à disposition du circuit.
  * Pour plus d'informations, voir **Section 5 - Redevances, Taxes et Paiements** dans le contrat sur les services Cloud consultable en cliquant sur le lien suivant : [https://www.ibm.com/support/customer/zz/en/selectcountrylang.html](https://www.ibm.com/support/customer/zz/en/selectcountrylang.html). Par exemple, les clients en France afficheront [ce contrat Cloud Services](https://www.ibm.com/support/customer/csol/contractexplorer/cloud/csa/fr-fr).

3. En commandant le service Direct Link, vous êtes redevable de tous les frais associés à l'accessibilité du point de présence depuis votre réseau distant et aux interconnexions nécessaires dans le site de point de présence. Si votre fournisseur exige qu'un routeur ou un autre dispositif soit physiquement installé dans le point de présence, vous êtes également redevable des coûts associés à la colocalisation de ces équipements.

4. IBM Cloud ne commandera pas d'interconnexion pour le compte d'un client.

5. IBM Cloud ne colocalisera pas d'équipement du client dans les points de présence de notre réseau. Nous acceptons uniquement les interconnexions reposant sur l'Ethernet à fibre optique (fibre en mode unique seulement, optiques 1Gig-LX ou 10Gig-LR 1310nm) qui s'exécute à partir de votre cage or provider. Nous n'acceptons pas les lignes T1, DS3, ISDN, POT, etc. Vous devrez collaborer avec votre fournisseur afin de déterminer si vous devez ou non colocaliser des équipements dans le même site que celui où réside le point de présence de réseau IBM Cloud.

6. Le service Direct Link est fourni de telle manière que votre liaison et le routeur IBM Cloud dans lequel elle se termine sont tous deux des points de défaillance uniques. Si vous souhaitez obtenir de la redondance via le service Direct Link Connect, vous devrez commander deux connexions dans un emplacement Direct Link Connect avec un routeur secondaire ou terminer les liaisons dans deux points de présence IBM Cloud distincts.

7. Le réseau de services IBM Cloud n'est pas directement accessible depuis vos réseaux distants. Si cela venait à changer, vous en seriez averti.

8. IBM Cloud n'autorise pas les clients à renvoyer le trafic entre leurs sites distants via le réseau principal IBM Cloud. Le produit Direct Link a été conçu pour permettre à vos réseaux distants de communiquer en privé avec votre infrastructure IBM Cloud.

9. Une fois que vous avez vérifié que votre circuit a atteint le point de présence et a été traité par le transporteur, vous devez commander l'interconnexion au routeur XCR IBM Cloud, ce qui prend généralement 2 à 10 jours ouvrables. Cela inclut l'application du correctif sur le port d'arrêt SoftLayer. Une fois l'opération terminée, vous devez fournir à IBM Cloud l'avis d'achèvement de l'interconnexion que vous obtenez auprès du fournisseur de site. L'affectation d'une adresse IP sur l'infrastructure réseau IBM Cloud sera effective dans les trois jours ouvrables une fois une fois l'interconnexion terminée.

10. IBM Cloud Direct Link Dedicated requiert l'utilisation d'une instance VRF (Virtual Routing and Forwarding).Cette fonctionnalité permet aux clients de définir leurs propres adresses IP distantes pour les utiliser dans leur réseau distant ; cependant, sachez que si vous utilisez le réseau 10.x.x.x, vous ne pouvez toujours pas créer un chevauchement avec vos hôtes dans IBM Cloud ni avec le réseau des services IBM Cloud (10.0.0.0/14, 10.198.0.0/15 et 10.200.0.0/14). La transition de votre compte vers une instance VRF requiert une brève indisponibilité du réseau privé lorsque chaque VLAN est migré dans la nouveau configuration.L'équipe de spécialistes des réseaux travaillera avec vous afin de définir une fenêtre pour cette activité. L'équipe de spécialistes des réseaux est à votre disposition du lundi au vendredi de 8 h à 17 h (heure d'été du Centre des E-U). Toute activité d'activation en dehors de ce créneau doit faire l'objet d'une demande via un ticket et doit être préalablement approuvée si des ingénieurs sont disponibles.

11. VRF n'est pas compatible avec les services IBM Cloud (ancien nom SoftLayer) SSL, PPTP et IPSEC VPN. En guise d'alternative, vous pouvez utiliser Direct Link à proprement parler pour gérer vos serveurs ou pour exécuter votre propre solution VPN (par exemple Vyatta) pouvant être configurée avec différents types de VPN. Après la migration vers une instance VRF, en principe, le réseau VPN SSL fonctionne lorsqu'une connexion VPN est établie avec le même emplacement de centre de données que celui où réside le centre de calcul qui fait l'objet d'un accès, mais il n'autorise pas l'accès mondial.

12. IBM Cloud Direct Link Dedicated requiert BGP afin d'implémenter des routes vers le réseau distant d'un client. Une fois votre service Direct Link déployé, IBM Cloud prévient tous les sous-réseaux privés affectés à votre compte.IBM Cloud n'implémente pas de filtres personnalisés, d'attributs AS-Path ajoutés en préfixe et de préférences locales personnalisées sur les annonces envoyées à l'homologue BGP distant du client.IBM Cloud n'implémente pas de filtres sur les annonces émises vers IBM Cloud. Les clients doivent gérer correctement les annonces envoyées vers/par IBM Cloud à partir de leur routeur périphérique.

## Autres questions
{: #dedicated-other-questions}

* **Dans quel point de présence souhaitez-vous terminer Direct Link ?**

* **De quelle vitesse de liaison avez-vous besoin (1, 2, 5 ou 10 Gbit/s) ?**

* **Avez-vous besoin que l'option BGP MultiPath avec ECMP soit configurée pour installer et configurer une connexion redondante avec IBM Cloud ?**  

    _Si oui, ajoutez l'ID de ticket pour l'autre connexion. Numéro de ticket ____________  (notez que ECMP ne peut être mis à disposition que sur deux sessions sur le même  routeur XCR IBM Cloud.  Si vous souhaitez utiliser ECMP, sachez que les deux services Direct Link doivent aboutir sur le même réseau.)_

* **Avez-vous besoin d'un accès via un routage local ou mondial ?**

    _Les clients qui choisissent le routage local pourront uniquement transmettre des données entre les centres de données traités depuis le point de présence où le service Direct Link a été commandé. Les clients qui souhaitent transmettre des données en dehors du point de présence où le service Direct Link a été commandé devront ajouter l'option Routage mondial._

* **Acceptez-vous de prendre en charge les frais liés à l'option Routage mondial incluant les frais mensuels liés à _VOTRE EMPLACEMENT_ et les frais de dépassement mentionnés ci-dessous ?**

    _L'option Routage local inclut l'accès à tous les centres de données connectés directement à l'emplacement du point de présence et elle fournit un trafic entrant et sortant illimité. L'option Routage mondial développe l'accès et inclut tous les centres de données IBM Cloud au niveau mondial. La bande passante est mesurée lorsque le service peut mesurer le trafic. Lorsqu'un décompte de bande passante est réalisé, vous êtes facturé mensuellement sur la base du prix du marché, comme illustré dans le tableau ci-dessous._


### Tarification de l'option Routage mondial
{: #dedicated-global-routing-pricing}

| Routage mondial (trafic entrant) | Routage mondial (trafic sortant) |
|---|---|
| Gratuit | Circuit 1, 2 ou 5 Gbit/s - 10 To de bande passante gratuite |
| Gratuit | Circuit 10G bps - 50 To de bande passante gratuite |


| Frais de dépassement de bande passante |
|---|
| Marché 1 : 0,05 $ par Go |
| Marché 2 : 0,10 $ par Go |
| Marché 3 : 0,15 $ par Go |
