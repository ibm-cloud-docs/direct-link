---

copyright:
  years: 2017, 2018
lastupdated: "2018-07-12"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Foire aux questions

Cette section contient les réponses aux questions les plus fréquentes sur IBM Cloud Direct Link. 

## Comment fonctionne IBM Cloud Direct Link ?
Pour chaque client Direct Link, l'équipe IBM Cloud affecte un petit sous-réseau privé pour construire un réseau point à point entre le routeur d'interconnexion (XCR) {{site.data.keyword.BluSoftlayer_notm}} et le routeur edge du client (CER). Puis, {{site.data.keyword.BluSoftlayer_notm}} et le client configurent BGP pour échanger les routes entre les environnements. Et enfin, {{site.data.keyword.BluSoftlayer_notm}} met le client dans une instance VRF pour permettre l'implémentation de routes non uniques vers l'espace d'adresse privé du réseau distant de ce client.

## Est-ce qu'IBM Cloud mesure la bande passante pour les produits Direct Link ?
Oui. L'utilisation de la bande passante dans le service Direct Link entre les clients et IBM Cloud est gratuite et non mesurée. IBM Cloud ne mesure pas la bande passante sortante à partir des services IBM Cloud vers l'internet public.

## A quelle moment la facturation commence-t-elle pour Direct Link ?
Les frais relatifs à Direct Link Connect couvrent le coût lié à la résiliation du service sur l'infrastructure IBM Cloud. 

Les services d'infrastructure sont facturés à l'avance et cette facturation commence dès l'acceptation de la commande de notre client ; cependant, en raison de la nature d'IBM Cloud Direct Link, la facturation du service Direct Link commence lorsqu'une session BGP (Border Gateway Protocol) est établie avec IBM Cloud, ou 30 jours après la communication de la clé de service au client. 

La facturation cesse après (1) qu'un client a demandé la suppression d'un circuit ET (2) que le fournisseur Connect Provider ou Network Service Provider a annulé la mise à disposition du circuit.

## Quels sont les frais supplémentaires encourus pour les parties prenantes avec Direct Link ?
Vous pourrez avoir des frais supplémentaires facturés par votre fournisseur d'échange ou votre fournisseur de services réseau. Consultez votre ou vos fournisseurs pour obtenir les informations concernant leurs tarifs.

## Comment peut-on établir la redondance avec IBM Cloud Direct Link ?
Direct Link ne fournit pas de service intrinsèquement redondant. Direct Link peut fournir plusieurs connexions, qui permettent aux clients de créer la redondance via BGP. Vous pouvez atteindre la diversité avec Direct Link en connectant plusieurs fournisseurs IBM Cloud Direct Link Dedicated ou Exchange à {{site.data.keyword.BluSoftlayer_notm}}. Sinon, avec Exchange et Connect, vous pouvez optimiser plusieurs NNI avec les fournisseurs IBM Cloud Direct Link.

## Quelle est la différence entre un routage "local" par défaut et le module complémentaire Routage mondial ?
Avec notre offre Direct Link standard, vous pouvez envoyer du trafic entre les centres de données de votre région sélectionnée. Si vous devez accéder à d'autres centres de données situés hors de la région spécifiée, vous devez commander le module complémentaire Routage mondial. Ce modèle est basé sur des listes de contrôle d'accès (ACL) mises en place lors de votre commande de connexion Direct Link. 

## Comment les dépassements de bande passante sortante sont-ils facturés pour le module complémentaire Routage mondial ?
Les dépassements sont facturés par mois si vous dépassez la bande passante qui vous est allouée, mais uniquement pour la bande passante sortante. La bande passante entrante est gratuite et ne fait pas l'objet de mesures. La bande passante sortante est facturée en fonction du taux le plus élevé des deux régions parcourues par vos données.  Par exemple, si votre solution Direct Link est configurée dans DAL03 et que vos données circulent via Mexico, le débit de bande passante vous sera facturé au tarif de Mexico.

## Pourquoi un module complémentaire Routage mondial ?
Nous avons ajouté le module complémentaire Routage mondial pour éviter à nos clients de faire l'expérience de coûts de données imprévus lorsqu'ils franchissent la région de leur centre de données. Cela permet de réduire les coûts pour la majorité de nos clients tout en leur donnant la possibilité d'être présents au niveau international pour atteindre facilement toutes les régions du monde. En règle générale, un client ne nécessite qu'un module de bande passante local.

## Si je suis connecté à Direct Link Dedicated, Direct Link Connect ou Direct Link Exchange dans une région telle que Dallas, ai-je accès à d'autres régions aux Etats-Unis via Direct Link ?
Oui, vous pouvez accéder à des zones situées hors de votre région si vous choisissez le module complémentaire Routage mondial. Si cette option n'est pas sélectionnée, votre trafic Direct Link sera limité à la région de l'emplacement de point de présence que vous avez sélectionné. Pour plus d'informations, voir la [rubrique sur la tarification](pricing.html).

## Puis-je me connecter à une région disponible à partir d'un emplacement Direct Link donné ?
Oui, à condition de commander Direct Link avec le module complémentaire Routage mondial.

## Puis-je limiter les régions auxquelles Direct Link peut accéder ?
Non. IBM Cloud offre deux options : (1) une seule région uniquement ou (2) toutes les régions avec le module complémentaire Routage mondial.

## Que se passe-t-il si j'ai utilisé le processus de commande automatisé pour Equinix Cloud Exchange et qu'on m'a attribué un sous-réseau qui chevauche mon réseau interne ?

A compter de mars 2018, il est recommandé d'annuler votre commande automatisée et de soumettre un nouveau ticket pour remplir le questionnaire Direct Link. Vous devez indiquer si vous préférez un autre sous-réseau dans la plage 10.254.x.x ou 172.32.x.x.

## Quelle est la différence entre Direct Link Exchange et Direct Link Connect ?

Ces deux services sont relativement peu coûteux, tolérants aux temps de latence et offrent un accès rapide aux avantages d'IBM Cloud Direct Link similaire. En bref, Exchange fait appel à des fournisseurs de centres de données et Connect fait appel à des opérateurs télécoms. Voici quelques détails supplémentaires :

**Direct Link Exchange** est recommandé pour les clients qui préfèrent utiliser un échange à l'intérieur d'un centre de données. Avec un service Exchange, les clients peuvent activer rapidement la connectivité multi-cloud à leur colocalisation, car les circuits sous-jacents sont déjà mis à disposition (ces autres fournisseurs de cloud doivent déjà avoir une interconnexion physique présente dans l'installation).

Direct Link Exchange peut permettre un environnement d'utilisation partagée et multi-cloud grâce à un seul port d'échange cloud, créé par une connexion réseau à réseau (NNI) à la couche 2 entre IBM Cloud et le fournisseur de services Cloud Exchange. Les vitesses de port disponibles vont jusqu'à 1 Gb.

**Direct Link Connect** s'adresse aux clients qui préfèrent utiliser leur réseau existant entre leur propre déploiement sur site et IBM Cloud. Avec le service Direct Link Connect, les clients peuvent utiliser les réseaux de télécommunication nouveaux et existants (tels que MPLS) pour activer rapidement IBM Cloud, en tirant parti des circuits sous-jacents déjà mis à disposition.

Avec Direct Link Connect, les clients peuvent se connecter à IBM Cloud via le fournisseur Connect, sur une connexion réseau à réseau (NNI) exploitée par des partenaires IBM dans des installations du monde entier. Les vitesses de port disponibles vont jusqu'à 5 Gbit/s.

## Comment peut-on comparer les fournisseurs Direct Link Connect et Direct Link Exchange ?

Les fournisseurs Connect sont des entreprises de télécommunications qui ont une portée réseau au-delà du centre de données. Les fournisseurs Exchange sont limités à leurs centres de données. Les deux peuvent permettre aux clients de profiter de l'expérience multi-cloud. Les fournisseurs d'accès Exchange ont généralement besoin d'une colocalisation dans leurs centres de données, tandis que les fournisseurs Connect peuvent atteindre le site et les centres de données locaux d'un client. 

## Peut-on prendre en charge IPv6 sur Direct Link ?

Pas pour la session BGP. Nous avons affecté /30 à partir de IPv4 et nous avons utilisé la même valeur en retour à partir du client.

## Peut-on prendre en charge IPv6 sur le réseau privé ?

Non, IPv6 est public uniquement.

## Existe-t-il des exigences particulières pour Verizon SCI ? Préfixe/ASN/VLAN BGP/etc ?

Verizon SCI est l'une des différentes connexions MPLS basées sur des services de couche 3 (IP VPN). Elle nécessite qu'IBM établisse une connexion BGP avec Verizon au lieu d'une connexion directe avec le client. Verizon établit ensuite une connexion BGP avec le client et annonce les routes en conséquence. Plusieurs autres fournisseurs de service de couche 3 participent au programme Direct Link Connect. Les clients doivent avoir conscience de ce qu'ils commandent et du comportement que leur compte adoptera lors de la connexion à IBM Cloud.

## Tous les types de qualité de service sont-ils pris en charge par Direct Link ?

Nous ne pouvons pas prendre en charge toutes les garanties de qualité de service. La qualité de service requiert un mappage MPLS entre chacun des fournisseurs de serveur et IBM Cloud. La plupart des fournisseurs de service Cloud ne peuvent pas prendre en charge la qualité de service pour l'instant, car elle doit être établie de bout en bout et impliquer chaque unité entre ces deux extrémités. Il n'existe pas de solution de contournement disponible via la tunnellisation ou toute autre méthode.

## Les trames jumbo sont-elles prises en charge par Direct Link ?

Les trames Jumbo (jusqu'à 9214 octets) sont prises en charge sur Dedicated et Dedicated Hosting. 
La prise en charge sur Connect et Exchange est théoriquement possible, mais elle nécessite que votre fournisseur de services collabore avec IBM et s'assure que la connexion de bout en bout prenne en charge les trames Jumbo, y compris l'interface réseau à réseau (NNI) sous-jacente.
Par défaut, Exchange et Connect sont configurés avec une prise en charge MTU de 1500 octets.

## Avec Direct Link Connect, comment un client peut-il s'assurer de la diversité des routeurs via le même transporteur (par exemple, Verizon dans DAL03) ?

Nous avons différents routeurs XCR qui créent plusieurs liens NNI vers le transporteur. Il incombe au transporteur de maintenir la diversité à partir de là.

## Pour Direct Link Connect, un client doit-il commander 2 liaisons pour la redondance ou Direct Link Connect est-il intrinsèquement redondant ?

Commandez 2 liaisons pour la diversité. Nous n'offrons pas la redondance entre les commutateurs ou les routeurs. Les clients créent la redondance avec leurs configurations BGP sur chaque Direct Link.

## Est-il facile à mettre à niveau ma bande passante de connexion, par exemple de 1 Go à 5 Go ?

En général, nous installons des vitesses de 1G et inférieures sur des fibres optiques de 1G. Pour les vitesses de 2G à 10G, nous installons des fibres optiques de 10G. Par conséquent, la mise à niveau à partir de 1G vers 5G nécessiterait d'affecter ou d'insérer de nouvelles fibres optiques. Cet événement pourrait affecter le service. Si vous anticipez le type de croissance, il est possible de demander l'installation de fibres optiques de 10G dès le début de votre déploiement Direct Link ou de commander initialement 2G de sorte que les fibres optiques de 10G soient en place.

## ECMP doit-il être utilisé pour créer des connexions redondantes ?  Existe-t-il d'autres méthodes ?

Notez que ECMP ne permet pas de créer des connexions redondantes, mais d'obtenir l'équilibrage de la charge sur deux liaisons. Avec ECMP, les deux connexions doivent aller jusqu'au même routeur d'interconnexion (XCR) IBM Cloud, ce qui en fait un point de défaillance unique. (En d'autres termes, ECMP peut être mis à disposition uniquement sous forme de deux sessions sur le même routeur XCR IBM Cloud.) 

ECMP est une fonction de BGP. Si vous cherchez à établir de la redondance, procurez-vous deux connexions Direct Link, une pour chaque routeur XCR. Si vous souhaitez utiliser ECMP et disposer de redondance, vous aurez besoin de deux connexions Direct Link sur chaque routeur XCR, de sorte que 2 sessions ECMP soient actives simultanément.

Sinon, certains de nos clients ont configuré deux liaisons dans des routeurs XCR différents dans le même centre de données (par exemple, WDC02), puis le basculement nécessaire à l'aide de configurations BGP. Cette configuration est moins redondante (moins sécurisée) que l'établissement de deux connexions Direct Link dans des centres de données distincts, par exemple, WDC02 et WDC05.

## Existe-t-il un accord sur les niveaux de service pour les connexions XCR jusqu'à la connexion BCR du compte ?

Il n'existe pas d'accord sur les niveaux de services pour DirectLink à l'heure actuelle. Les clients peuvent atteindre un taux de succès de 99,999% avec 2 Direct Links ou plus correctement configurés pour le basculement à l'aide de BGP, mais IBM ne peut pas contrôler cela ou fournir un accord sur les niveaux de service pour cela.
