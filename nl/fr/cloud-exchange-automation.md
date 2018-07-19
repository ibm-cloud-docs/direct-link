---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-11"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Procédure de commande d'IBM Cloud Direct Link Exchange étape par étape

Cette page vous indique comment commander le service IBM Cloud Direct Link Exchange. Si vous commandez IBM Cloud Direct Link pour Equinix Cloud Exchange, la mise à disposition du service est automatique, ce qui signifie que vous pouvez passer une commande pour une connexion IBM Cloud Direct Link (Equinix) sans ouvrir un ticket de support IBM.

**(Remarque : cette fonction de mise à disposition automatique est uniquement réservée à Equinix Cloud Exchange pour le moment. Dans les éditions suivantes, elle sera activée pour les autres fournisseurs.)**

## Conditions requises

Pour pouvoir utiliser la fonction d'automatisation, vos VLAN privés doivent être associés à un VRF dans le réseau privé IBM Cloud. Si cette condition n'est pas remplie, un ticket de support IBM sera généré lorsque vous passerez une commande via le portail client.

 * [Comment commander Cloud Exchange](#how-to-order-cloud-exchange)
 * [Comment commander Cloud Exchange pour Equinix](#how-to-order-cloud-exchange-for-equinix)

## Comment commander Cloud Exchange

Pour mettre à disposition une connexion IBM Cloud Direct Link Exchange, procédez comme suit :

**Etape 1 :**

Connectez-vous à votre compte client sur le [portail client ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/).

**Etape 2 :**

Sous l'onglet **Réseau**, sélectionnez **Direct Link -> Exchange** pour ouvrir une page affichant les connexions IBM Cloud Direct Link existantes.

![Etape 2](/images/Equinix-Step2.png)

**Etape 3 :**

Après avoir cliqué sur le bouton de **commande de Direct Link Exchange** en haut de la page, vous verrez apparaître le formulaire de commande dans lequel vous pourrez entrer les paramètres de configuration de la connexion IBM Cloud Direct Link Exchange.

![Etape 3](/images/Equinix-Step3.png)

**Etape 3A :**

Eventuellement, si de nombreux ports sont accessibles et que le premier circuit virtuel a déjà été mis à votre disposition, un écran semblable a celui présenté ci-après s'affiche. Il contient deux ports parmi lesquels vous pouvez sélectionner votre second circuit virtuel. 

![2-port-image](/images/exchange-2-ports-image.png)

**Etape 4 :**

Dans le formulaire de commande, entrez les paramètres suivants pour configurer Direct Link :
  * Entrez le nom de la connexion IBM Cloud Direct Link.
  * Dans la liste, sélectionnez l'emplacement du point de présence dans lequel vous souhaitez établir la connexion IBM Cloud Direct Link.
  * Dans la liste, sélectionnez le nom du fournisseur Cloud Exchange préféré.
  * Sélectionnez la vitesse de liaison requise pour la connexion.
  * Sélectionnez l'option d'acheminement requise pour la connexion.
  * Entrez un numéro ASN compris dans la plage indiquée dans la zone d'information pour les échanges BGP.

**Etape 5 :**

Lorsque vous sélectionnez ou entrez ces valeurs, les frais mensuels approximatifs s'affichent sur le panneau de gauche.

![Etape 4-5](/images/Equinix-Step4-5.png)

**Etape 6.**

Après avoir fourni les valeurs, l'écran suivant de l'interface utilisateur affiche les tarifs mensuels applicables en fonction des options sélectionnées.

**Etape 7 :**

Vous devez **ACCEPTER** les dispositions générales avant de pouvoir commander IBM Cloud Direct Link. Veuillez lire attentivement les dispositions générales car elles contiennent des informations techniques importantes que vous devez comprendre avant de procéder. **(Remarque : si les dispositions générales ne sont pas acceptées, un ticket de support IBM sera généré lors de la passation de commande).** Les figures ci-dessous montrent les écrans qui s'affichent suivant la sélection effectuée à cette étape.

La figure suivante montre l'écran des dispositions :

![Etape 7](images/Equinix-Step7.png)

La figure suivante montre l'écran qui s'affiche si vous n'acceptez pas les dispositions générales lorsque vous passez la commande. L'écran illustre le numéro de ticket généré :

![Etape 7 acceptation](/images/Equinix-Step7-NoAgree.png)

La figure suivante montre un exemple de ticket ouvert :

![Ticket de l'étape 7](/images/Equinix-Step7-NoAgree-Ticket.png)

**Etape 8 :**

Après avoir accepté les dispositions générales, un ticket de support IBM est généré lorsque vous passez la commande pour procéder à la mise à disposition du service. Le numéro de ticket sera affiché dans l'interface utilisateur après avoir passé la commande. 

![Etape NE1](/images/Non-Equinix-Step1.png)

**Etape 9 :**

En cliquant sur le numéro de ticket qui apparaît dans le message, vous afficherez les détails du ticket.

![Etape NE2](/images/Non-Equinix-Step2.png)

## Comment commander Cloud Exchange pour Equinix

**Etape 1 :**

Suivez les étapes 1 à 7 ci-dessus pour la commande de Cloud Exchange

**Etape 2 :**

Après avoir passé la commande, la mise à disposition d'IBM Cloud Direct Link commence.

![Etape 8](/images/Equinix-Step8.png)

**Etape 3 :**

Vous pouvez voir le statut de votre connexion après avoir passé la commande. Si la configuration réussit du côté d'IBM, le statut sera **Mis à disposition**. Si la configuration n'est pas terminée, le statut sera **En cours**. Et si la configuration échoue, la mention **Echec de la création** s'affichera. Si la configuration aboutit et la connexion BGP est active, le statut sera **Actif**.

![Etape 9 en cours](/images/Equinix-Step9-InProgress.png)

La figure suivante affiche les différents états de connexion qui suivent une passation de commande :

![Etape 9 actif](/images/Equinix-Step9-UP.png)

**Etape 4 :**

Si le statut de connexion est **Mis à disposition**, développez la connexion en cliquant sur le signe **>** en regard du **nom** de la connexion. Notez ensuite les informations concernant l'**adresse IP du client** et la **clé de service**. Ces informations seront nécessaires pour configurer le routeur périphérique du client et comme clé d'autorisation pour la configuration du côté du fournisseur de cloud (Equinix), respectivement.

![Etape 10](/images/Equinix-Step10-Provisioned.png)

**Etape 5 :**

Pour les connexions dont le statut est **Mis à disposition**, après avoir développé la connexion en cliquant sur le signe **>** en regard de la connexion, vous verrez apparaître un message d'erreur si la vitesse de liaison homologue ne correspond pas. Une fois que la vitesse est la même du côté d'IBM et du côté d'Equinix, cette notification d'erreur disparaît.

![Etape 11](/images/Equinix-Step11-PortMismatch.png)

**Etape 6 :**

Pour les connexions affichant le statut **Echec de la création**, un ticket de support IBM est généré et des détails supplémentaires sont communiqués à travers le ticket de support. Pour afficher les détails du ticket, développez la connexion.

![Etape 12](/images/Equinix-Step12-CreateFailed.png)

**Etape 7 :**

Pour les connexions affichant le statut **Mis à disposition**, **Actif** ou **Inactif**, vous pouvez **supprimer** la connexion en cliquant sur la colonne **ACTIONS** en regard de la connexion.

![Etape 13](/images/Equinix-Step13-Delete.png)

**Etape 8 :**

Pour les connexions affichant le statut **Echec de la création**, vous pouvez **annuler** la connexion en cliquant sur la colonne **ACTIONS** en regard de la connexion.

