---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-02-19"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Configuration d'IBM Cloud Direct Link
{ #configure-ibm-cloud-direct-link}

Lorsque votre connectivité IBM Cloud Direct Link a été établie, vous pouvez suivre la procédure indiquée dans ce document pour configurer votre réseau afin qu'il interagisse avec IBM Cloud.

En général, pour que votre connexion IBM Cloud Direct Link fonctionne, vous devez effectuer quelques étapes de configuration du réseau de base, puis configurer le protocole BGP (Border Gateway Protocol). Lors du processus de configuration, un ingénieur IBM vous aidera à activer votre réseau pour l'utilisation de la fonction Virtual Routing and Forwarding (VRF), qui est requise.

## Configuration du réseau de base

1. Définissez votre réseau distant à l'aide de l'espace d'adresse privé RFC1918 standard. 
 * Pour les nouveaux environnements, il est recommandé de **ne pas** utiliser l'espace 10.0.0.0/8. 
 * Pour les environnements existants qui utilisent 10.0.0.0/8, nous vous recommandons d'obtenir une évaluation plus détaillée, pour garantir qu'il n'y a pas de conflit avec le réseau de services {{site.data.keyword.BluSoftlayer_notm}} ou les réseaux déjà affectés à votre compte.

2. Notre personnel chez {{site.data.keyword.BluSoftlayer_notm}} affecte /31 ou /30 pour chaque connexion et configure une adresse IP d'interface sur l'infrastructure du routeur d'interconnexion (XCR) {{site.data.keyword.BluSoftlayer_notm}}.  

3. Configurez l'interface de votre routeur CER (Customer Edge Router) à l'aide de l'adresse IP que nous avons fournie : il vous suffit d'utiliser l'adresse IP XCR {{site.data.keyword.BluSoftlayer_notm}} comme tronçon suivant pour tout trafic destiné à {{site.data.keyword.BluSoftlayer_notm}}. 

4. Pour le trafic de retour, {{site.data.keyword.BluSoftlayer_notm}} utilise l'adresse IP CER affectée comme tronçon suivant pour tout trafic destiné au réseau distant, comme annoncé via BGP.

## Configuration de BGP

Pour échanger des informations de route avec votre environnement, {{site.data.keyword.BluSoftlayer_notm}} nécessite la configuration de BGP.  

1. **ASN** : {{site.data.keyword.BluSoftlayer_notm}} affecte un numéro ASN privé pour chaque utilisateur. Sinon vous pouvez utiliser votre propre ASN public. Votre préférence vous sera demandée au moment où vous passez la commande. Votre numéro ASN privé vous est fourni lors du processus d'implémentation.

2. **VRF** : Avec VRF, {{site.data.keyword.BluSoftlayer_notm}} annonce les sous-réseaux privés spécifiques affectés à votre compte client.  Vous devez déclarer les réseaux distants que vous souhaitez accessibles depuis le réseau privé {{site.data.keyword.BluSoftlayer_notm}}. Les réseaux suivants sont exclus et ne peuvent pas être acceptés : 0.0.0.0, 10.0.0.0/14, 10.198.0.0/15, 10.200.0.0/14, 169.254.0.0/16, 224.0.0.0/4. Il vous incombe en tant que client de gérer les annonces en provenance et à destination du réseau IBM Cloud. (Vous trouverez plus de détails sur VRF à la section suivante).

3. **ECMP** : Pour les clients qui optent pour intégrer la redondance à un emplacement pris en charge, {{site.data.keyword.BluSoftlayer_notm}} prend en charge l'implémentation de la fonction ECMP (Equal-Cost MultiPath) pour fournir l'équilibrage de charge et la redondance sur les deux liaisons. Cette configuration ECMP doit être demandée au moment de la commande.

## Spécifications de protocole BGP pour IBM Cloud Direct Link 

Les spécifications de protocole BGP sont les suivantes :

Comme indiqué dans la section précédente, le protocole BGP est obligatoire pour gérer votre routage via Direct Link. Un compte qui commande Direct Link sera migré vers l'environnement VRF.

**Avertissements relatifs aux VLAN et à l'environnement VRF :**
 * Le spanning VLAN entre les comptes n'est pas admis dans l'environnement VRF. 
 * Le service VPN IPSEC est limité. 
 
**Remarque :** VRF n'empêche pas l'accès SSL ou VPN PPTP, mais son comportement change. Sans VRF, une connexion VPN suffit pour voir tous les serveurs sur votre compte. Avec VRF, vous ne pouvez accéder qu'aux ressources présentes sur le marché associé à votre réseau privé virtuel (VPN). Par conséquent, si vous vous connectez au VPN DAL, vous ne pouvez vous connecter qu'aux serveurs DAL.

Le numéro de système autonome (ASN) d'IBM Cloud est **13884**, pour les services publics et privés. 
 * L'ASN par défaut d'un client lors d'une commande est **64999**, mais elle peut être modifiée à la demande du client. 
 * Un ASN privé de 4 octets compris entre 4201000000 et 4201064511 peut éventuellement être pris en charge.
 * Si vous utilisez Direct Link Connect avec un service à 3 couches, par exemple, IP VPN, IBM Cloud établit un protocole BGP avec l'ASN du fournisseur Direct Link Connect.
   
**Limitations strictes pour les affectations d'adresse IP :**
 * Si vous utilisez le réseau 10.x.x.x, vous ne pouvez toujours pas créer un chevauchement avec vos hôtes dans IBM Cloud ni avec le réseau des services IBM Cloud, qui occupe `10.0.0.0/14`, `10.198.0.0/15` et `10.200.0.0/14`.  

 * Les plages suivantes ne sont pas admises dans le système fédéral, par conséquent, elles seront rejetées par les serveurs IBM : `169.254.0.0/16`, `224.0.0.0/4`.

**Recommandations, valeurs par défaut et limites :**

 * La tunnellisation (c'est-à-dire GRE) est prise en charge et recommandée si le chevauchement d'adresses IP devient un problème.
 * Les valeurs par défaut du temporisateur BGP sont `Keepalive:30`, `Holdtime:60.`
 * L'authentification n'est pas activée par défaut.
 * BGP BFD n'est pas activé par défaut.
 * La limite de réception maximale (de la part des clients ou des fournisseurs) est 200 par VRF.

## Redondance et diversité

IBM Cloud Direct Link offre la diversité et les clients sont responsables d'implémenter la redondance à travers leurs schémas BGP.

Si vous sélectionnez ECMP pour la redondance, les deux sessions BGP doivent exister sur le même XCR, et vous renoncez donc à la diversité du routeur et êtes exposé à des risques en cas de défaillance du routeur. Vous gagnez la redondance de la couche 3 mais vous perdez la diversité du routeur.

## En savoir plus sur VRF

Tous les comptes qui utilisent une solution IBM Cloud Direct Link doivent migrer vers une instance VRF. En utilisant VRF, les clients annoncent les routes disponibles vers leurs réseaux distants auto-définis. Notez que cette configuration ne vous autorise pas à utiliser des adresses IP auto-définies sur le réseau {{site.data.keyword.BluSoftlayer_notm}}.

La migration vers une instance VRF s'effectue lors du processus de configuration. Elle nécessite une fenêtre d'indisponibilité momentanée (jusqu'à 30 mn pour les comptes importants avec plusieurs réseaux locaux virtuels (VLAN)/emplacements), période pendant laquelle les réseaux VLAN du réseau back-end perdront leur connectivité mutuelle lors de leur transfert sur l'instance VRF. La migration VRF est planifiée avec l'ingénieur chargé de l'implémentation.

Notez que VRF élimine l'option "Spanning VLAN" de votre compte, y compris les fonctions éventuelles de spanning VLAN de compte à compte, car tous les réseaux VLAN sont en mesure de communiquer sauf si un dispositif de passerelle est mis en place pour gérer le trafic. VRF limite également la possibilité d'utiliser les services VPN {{site.data.keyword.BluSoftlayer_notm}}, car ce n'est pas compatible avec les services VPN SSL, PPTP et IPSec de {{site.data.keyword.BluSoftlayer_notm}}.   

En guise d'alternative, vous pouvez utiliser l'offre IBM Cloud Direct Link même pour gérer vos serveurs ou pour exécuter votre propre solution VPN (par exemple Vyatta) pouvant être configurée avec différents types de VPN. Après avoir effectué la migration sur VRF, le réseau VPN SSL fonctionne en principe lorsqu'une connexion VPN est réalisée avec le même emplacement de centre de données dans lequel s'exécute une machine virtuelle (VM) de calcul, mais il n'autorise pas l'accès mondial.

## Utilisation de BYOIP et NAT avec Direct Link
IBM Cloud Direct Link n'offre pas BYOIP sur le réseau privé. Par conséquent, le trafic avec une adresse IP de destination qui n'a pas été affectée par {{site.data.keyword.BluSoftlayer_notm}} ne sera pas traité. Les clients peuvent toutefois encapsuler le trafic entre le réseau distant et leur réseau {{site.data.keyword.BluSoftlayer_notm}} à l'aide de GRE, IPSec ou VXLAN.  

En règle générale, l'environnement BYOIP est implémenté dans le cadre d'une passerelle de réseau (Vyatta) ou d'un déploiement VMWare NSX. Cette configuration permet aux clients d'utiliser tout espace IP souhaitable côté {{site.data.keyword.BluSoftlayer_notm}} et d'effectuer un routage inverse via le tunnel vers le réseau distant. Notez que cette configuration doit être gérée et prise en charge par le client, indépendamment de {{site.data.keyword.BluSoftlayer_notm}}. De plus, cette configuration peut interrompre la connectivité au réseau de services {{site.data.keyword.BluSoftlayer_notm}} si le client affecte un bloc 10.x.x.x utilisé par {{site.data.keyword.BluSoftlayer_notm}} pour les services. 

Avec cette solution, il faut également que chaque hôte nécessitant une connectivité au réseau de services {{site.data.keyword.BluSoftlayer_notm}} et au réseau distant ait 2 adresses IP affectées : une devant être affectée à partir du bloc IBM 10.x.x.x et l'autre à partir du bloc du réseau distant. Les routes statiques doivent être configurées sur l'hôte, pour garantir que le trafic soit routé correctement. Vous ne pourrez pas affecter d'espace IP directement sur les hôtes {{site.data.keyword.BluSoftlayer_notm}} (BYOIP) et le rendre acheminable sur le réseau {{site.data.keyword.BluSoftlayer_notm}} intrinsèquement. La seule manière d'implémenter cette possibilité est soulignée précédemment, mais elle n'est pas prise en charge par {{site.data.keyword.BluSoftlayer_notm}}.

Sinon, les clients affectent souvent un bloc de réseau distant à utiliser dans une table NAT configurée sur leur routeur edge distant. Cette configuration permet aux clients de limiter les modifications requises sur les deux réseaux, tout en continuant à acheminer le trafic dans un espace d'adresse réseau compatible avec les deux réseaux.


