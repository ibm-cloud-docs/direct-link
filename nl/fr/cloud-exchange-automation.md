---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: provisioning, Exchange, order, support, ticket, diverse, virtual circuit, parameters, Terms and Conditions

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

# Mise à disposition d'IBM Cloud Direct Link Exchange
{: #provisioning-ibm-cloud-direct-link-exchange}

Cette page vous indique comment commander le service {{site.data.keyword.cloud}} Direct Link Exchange. Si vous commandez {{site.data.keyword.cloud_notm}} Direct Link pour Equinix Cloud Exchange, la mise à disposition du service est automatique, ce qui signifie que vous pouvez [passer une commande pour une connexion IBM Cloud Direct Link (Equinix) sans ouvrir de ticket de demande de service IBM](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix) comme décrit dans un document connexe.

Cette fonction de mise à disposition automatique est uniquement réservée à Equinix Cloud Exchange pour le moment. Dans les éditions suivantes, elle sera activée pour les autres fournisseurs.
{:note}

## Conditions requises
{: #cloud-exchange-prerequisites}

Pour pouvoir utiliser la fonction d'automatisation, vos VLAN privés doivent être associés à un VRF dans le réseau privé {{site.data.keyword.cloud_notm}}. Si cette condition n'est pas remplie, un ticket de demande de service IBM sera généré lorsque vous passerez une commande via le portail client.

 * [Comment commander Cloud Exchange](#how-to-order-cloud-exchange-no-equinix)
 * [Comment commander Cloud Exchange pour Equinix](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix)

## Comment commander Cloud Exchange
{: #how-to-order-cloud-exchange-no-equinix}

Pour mettre à disposition une connexion IBM Cloud Direct Link Exchange, procédez comme suit :

**Etape 1 :**

Connectez-vous à votre compte client sur le [portail client ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://cloud.ibm.com/).

**Etape 2 :**

Sous l'onglet **Réseau**, sélectionnez **Direct Link -> Exchange** pour ouvrir une page affichant les connexions IBM Cloud Direct Link existantes.

![Etape 2](/images/pup_exchange_list.png)

**Etape 3 :**

Après avoir cliqué sur le bouton de **commande de Direct Link Exchange** en haut de la page, vous verrez apparaître le formulaire de commande dans lequel vous pourrez entrer les paramètres de configuration de la connexion IBM Cloud Direct Link Exchange.

![Etape 3](/images/pup_exchange_create_default.png)

**Etape 3A :**

Eventuellement, si de nombreux ports sont accessibles et que le premier circuit virtuel a déjà été mis à votre disposition, un écran semblable a celui présenté ci-après s'affiche. Il contient deux ports parmi lesquels vous pouvez sélectionner votre second circuit virtuel.

![2-port-image](/images/pup_exchange_create_ports.png)

**Etape 4 :**

Dans le formulaire de commande, entrez les paramètres suivants pour configurer Direct Link :
  * Entrez le nom de la connexion IBM Cloud Direct Link.
  * Dans la liste, sélectionnez l'emplacement dans lequel vous souhaitez établir la connexion IBM Cloud Direct Link.
  * Dans la liste, sélectionnez le nom du fournisseur Cloud Exchange préféré.
  * Sélectionnez la vitesse de liaison requise pour la connexion.
  * Sélectionnez l'option d'acheminement requise pour la connexion.
  * Entrez un numéro ASN compris dans la plage indiquée dans la zone d'information pour les échanges BGP.

**Etape 5 :**

Lorsque vous sélectionnez ou entrez ces valeurs, les frais mensuels approximatifs s'affichent sur le panneau de droite.

![Etape 4-5](/images/pup_exchange_create_prices.png)

**Etape 6.**

Les zones de formulaire sont validées lorsque vous fournissez les entrées.
Vous devez **ACCEPTER** les dispositions pour que le bouton "Créer" soit activé.

**Etape 7 :**

Après avoir accepté les dispositions, un ticket de demande de service IBM est généré lorsque vous passez la commande pour procéder à la mise à disposition du service. Le numéro de ticket sera affiché dans l'interface utilisateur après avoir passé la commande. 

![Etape NE1](/images/pup_exchange_ticket_notification.png)

**Etape 8 :**

En cliquant sur le numéro de ticket qui apparaît dans le message, vous afficherez les détails du ticket.

![Etape NE2](/images/pup_exchange_ticket_details.png)
