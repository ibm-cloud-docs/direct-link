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
{:note: .note}
{:download: .download}


# Mise à disposition d'IBM Cloud Direct Link Exchange pour Equinix
{: #provisioning-ibm-cloud-direct-link-exchange-for-equinix}

Si vous commandez IBM Cloud Direct Link pour Equinix Cloud Exchange, la mise à disposition du service est automatique, ce qui signifie que vous pouvez passer une commande pour une connexion IBM Cloud Direct Link (Equinix) sans ouvrir un ticket de support IBM.

Cette fonction de mise à disposition automatique est uniquement réservée à Equinix Cloud Exchange pour le moment. Dans les éditions suivantes, elle sera activée pour les autres fournisseurs. {:note}

## Conditions requises

Pour pouvoir utiliser la fonction de commande automatisée, vos VLAN privés doivent être associés à un VRF dans le réseau privé IBM Cloud. Si cette condition n'est pas remplie, un ticket de support IBM sera généré lorsque vous passerez une commande via le portail client.

## Procédure de commande et de mise à disposition

**Etape 1 :**

Suivez les étapes 1 à 7 de la procédure habituelle de commande [Cloud Exchange](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange). 

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

