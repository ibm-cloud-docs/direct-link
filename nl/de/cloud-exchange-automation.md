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

# Bereitstellung von IBM Cloud Direct Link Exchange
{: #provisioning-ibm-cloud-direct-link-exchange}

Auf dieser Seite erfahren Sie, wie der {{site.data.keyword.cloud}} Direct Link Exchange-Service bestellt wird. Ist die Bestellung von {{site.data.keyword.cloud_notm}} Direct Link für Equinix Cloud Exchange vorgesehen, geschieht die Servicebereitstellung voll automatisiert, d. h. Sie können [eine Bestellung für eine IBM Cloud Direct Link-Verbindung (Equinix) aufgeben, ohne ein IBM Support-Ticket öffnen zu müssen](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix), wie in einem zugehörigen Dokument beschrieben.

Die Automatisierungsfunktionalität ist derzeit auf Equinix Cloud Exchange beschränkt. In nachfolgenden Releases wird die Automatisierung auch für andere Provider aktiviert sein.
{:note}

## Voraussetzungen
{: #cloud-exchange-prerequisites}

Um die Automatisierungsfunktion nutzen zu können, müssen Ihre privaten VLANs einer VRF-Instanz im privaten {{site.data.keyword.cloud_notm}}-Netz zugeordnet sein. Ist diese Voraussetzung nicht erfüllt, so wird bei Ihrer Bestellung über das Kundenportal ein IBM Support-Ticket generiert.

 * [Vorgehensweise zur Bestellung von Cloud Exchange](#how-to-order-cloud-exchange-no-equinix)
 * [Vorgehensweise zur Bestellung von Cloud Exchange für Equinix](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix)

## Vorgehensweise zur Bestellung von Cloud Exchange
{: #how-to-order-cloud-exchange-no-equinix}

Um eine IBM Cloud Direct Link Exchange-Verbindung bereitzustellen, gehen Sie nach folgenden Schritten vor:

**Schritt 1:**

Melden Sie sich bei Ihrem Kundenkonto im [Kundenportal ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://cloud.ibm.com/) an.

**Schritt 2:**

Wählen Sie auf der Registerkarte **Netz** die Optionen **Direct Link -> Exchange**, um eine Seite mit ggf. vorhandenen IBM Cloud Direct Link-Verbindungen zu öffnen.

![Schritt 2](/images/pup_exchange_list.png)

**Schritt 3:**

Nachdem Sie auf die Schaltfläche **Direct Link Exchange bestellen** oben auf der Seite geklickt haben, wird ein Bestellformular angezeigt, in dem Sie die Konfigurationsparameter für die IBM Cloud Direct Link Exchange-Verbindung angeben können.

![Schritt 3](/images/pup_exchange_create_default.png)

**Schritt 3a:**

(Optional) Wenn diverse Ports zugänglich sind und Sie zuvor die erste virtuelle Verbindung bereitgestellt haben, wird eine Anzeige ähnlich der folgenden geöffnet. Die Anzeige enthält zwei Ports und ermöglicht Ihnen das Auswählen der zweiten virtuellen Verbindung.

![Darstellung mit zwei Ports](/images/pup_exchange_create_ports.png)

**Schritt 4:**

Im Bestellformular geben Sie die folgenden Parameter ein, um Direct Link zu konfigurieren:
  * Geben Sie den Verbindungsnamen für die IBM Cloud Direct Link-Verbindung ein.
  * Wählen Sie aus der Liste den Standort aus, an dem die IBM Cloud Direct Link-Verbindung hergestellt werden soll.
  * Wählen Sie aus der Liste den Namen des bevorzugten Cloud-Providers für den Datenaustausch aus.
  * Wählen Sie die für die Verbindung erforderliche Verbindungsgeschwindigkeit aus.
  * Wählen Sie die für die Verbindung erforderliche Routing-Option aus.
  * Geben Sie eine ASN-Nummer aus dem Bereich ein, der in dem Informationsfenster für den BGP-Austausch angegeben ist.

**Schritt 5:**

Während Sie diese Werte auswählen oder eingeben, wird Ihnen im rechten Fensterbereich eine näherungsweise berechnete monatliche Gebühr angezeigt.

![Schritte 4 und 5](/images/pup_exchange_create_prices.png)

**Schritt 6:**

Die Formularfelder werden validiert, wenn Sie die Eingaben vornehmen.
Sie müssen den Vertragsbedingungen **ZUSTIMMEN**, bevor die Schaltfläche "Erstellen" aktiviert wird.

**Schritt 7:**

Nachdem Sie den Vertragsbedingungen zugestimmt haben und die Bestellung aufgeben, wird anschließend ein IBM Support-Ticket generiert, sodass Sie mit der Servicebereitstellung fortfahren können. Die Ticketnummer wird nach Aufgabe der Bestellung in der Benutzerschnittstelle angezeigt. 

![Schritt NE1](/images/pup_exchange_ticket_notification.png)

**Schritt 8:**

Indem Sie auf die Ticketnummer in der Nachricht klicken, können Sie die Ticketdetails anzeigen.

![Schritt NE2](/images/pup_exchange_ticket_details.png)
