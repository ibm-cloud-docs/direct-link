---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: provisioning, order, Exchange, Equinix, automated, status, connection

subcollection: direct-link

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

Si vous commandez {{site.data.keyword.cloud}} Direct Link pour Equinix Cloud Exchange, la mise à disposition du service est entièrement automatisée, ce qui signifie que vous pouvez passer une commande pour une connexion {{site.data.keyword.cloud_notm}} Direct Link (Equinix) sans ouvrir de ticket de demande de service IBM.

Cette fonction de mise à disposition automatique est uniquement réservée à Equinix Cloud Exchange pour le moment. Dans les éditions suivantes, elle sera activée pour les autres fournisseurs.
{:note}

## Conditions requises
{: #cloud-exchange-equinix-prerequisites}

Pour pouvoir utiliser la fonction de commande automatisée, vos VLAN privés doivent être associés à un VRF dans le réseau privé {{site.data.keyword.cloud_notm}}. Si cette condition n'est pas remplie, un ticket de demande de service IBM sera généré lorsque vous passerez une commande via le portail client.

## Procédure de commande et de mise à disposition
{: #cloud-exchange-steps-for-ordering-and-provisioning}

**Etape 1 :**

Suivez les étapes 1 à 7 de la procédure habituelle de commande [Cloud Exchange](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange).

**Etape 2 :**

Après avoir passé la commande, la mise à disposition d'IBM Cloud Direct Link commence.

Vous pouvez voir le statut de votre connexion après avoir passé la commande. Si la configuration réussit du côté d'IBM, le statut sera **Mis à disposition**. Si la configuration n'est pas terminée, le statut sera **En cours**. Et si la configuration échoue, la mention **Echec de la création** s'affichera. Si la configuration aboutit et la connexion BGP est active, le statut sera **Actif**.

![Etape 9 en cours](/images/pup_exchange_equinix_inProgress.png)

**Etape 3 :**

Si la connexion a le statut **Mis à disposition**, cliquez sur le nom de la connexion en cliquant sur le lien **<connection_name>**.  Vous devriez accéder à la page des informations détaillées.

![Etape 10](/images/pup_exchange_equinix_provisioned.png)

La figure suivante affiche les différents états de connexion qui suivent une passation de commande :

![Etape 9 actif](/images/pup_exchange_equinix_up.png)

**Etape 4 :**

Notez les informations concernant l'**adresse IP du client** et la **clé de service**. Ces informations seront nécessaires pour configurer le routeur périphérique du client et comme clé d'autorisation pour la configuration du côté du fournisseur de cloud (Equinix), respectivement.

![Etape 9 actif](/images/pup_exchange_equinix_provisioned_details.png)

**Etape 5 :**

Pour les connexions dont le statut est **Mis à disposition**, après avoir cliqué sur le nom de la connexion via le lien **<connection_name>**, un message d'erreur s'affiche en cas de non correspondance avec la vitesse de liaison homologue. Une fois que la vitesse est la même du côté d'IBM et du côté d'Equinix, cette notification d'erreur disparaît.

![Etape 11](/images/pup_exchange_equinix_provisioned_details_portSpeedMismatch.png)

**Etape 6 :**

Pour les connexions affichant le statut **Echec de la création**, un ticket de demande de service IBM est généré et des détails supplémentaires sont communiqués à travers le ticket de demande de service. Pour afficher les détails du ticket, développez la connexion.

![Etape 12](/images/pup_exchange_equinix_list_createFailed.png)

**Etape 7 :**

Pour les connexions affichant le statut **Mis à disposition**, **Actif** ou **Inactif**, vous pouvez **supprimer** la connexion en cliquant sur le dépassement dans la colonne **ACTIONS** en regard de la connexion.

![Etape 13](/images/pup_exchange_equinix_list_delete.png)

**Etape 8 :**

Pour les connexions affichant le statut **Echec de la création**, vous pouvez **annuler** la connexion en cliquant sur la colonne **ACTIONS** en regard de la connexion.

![Etape 14](/images/pup_exchange_equinix_list_delete.png)
