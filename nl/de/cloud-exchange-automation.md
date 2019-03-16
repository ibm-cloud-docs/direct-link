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

# Bereitstellung von IBM Cloud Direct Link Exchange
{: #provisioning-ibm-cloud-direct-link-exchange}

Auf dieser Seite erfahren Sie, wie der {{site.data.keyword.cloud}} Direct Link Exchange-Service bestellt wird. Ist die Bestellung von IBM Cloud Direct Link für Equinix Cloud Exchange, ist die Servicebereitstellung voll automatisiert, d. h., Sie können [eine Bestellung für eine IBM Cloud Direct Link-Verbindung (Equinix) aufgeben, ohne ein IBM Support-Ticket öffnen zu müssen]/(docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix) wie in einem zugehörigen Dokument beschrieben. 

Die Automatisierungsfunktionalität ist derzeit auf Equinix Cloud Exchange beschränkt. In nachfolgenden Releases wird die Automatisierung auch für andere Provider aktiviert sein.
{:note}

## Voraussetzungen

Um die Automatisierungsfunktion nutzen zu können, müssen Ihre privaten VLANs einer VRF-Instanz im privaten IBM Cloud-Netz zugeordnet sein. Ist diese Voraussetzung nicht erfüllt, so wird bei Ihrer Bestellung über das Kundenportal ein IBM Support-Ticket generiert.

 * [Vorgehensweise zur Bestellung von Cloud Exchange](#how-to-order-cloud-exchange)
 * [Vorgehensweise zur Bestellung von Cloud Exchange für Equinix](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix)

## Vorgehensweise zur Bestellung von Cloud Exchange

Um eine IBM Cloud Direct Link Exchange-Verbindung bereitzustellen, gehen Sie nach folgenden Schritten vor:

**Schritt 1:**

Melden Sie sich bei Ihrem Kundenkonto im [Kundenportal ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com/) an.

**Schritt 2:**

Wählen Sie auf der Registerkarte **Netz** die Optionen **Direct Link -> Exchange**, um eine Seite mit ggf. vorhandenen IBM Cloud Direct Link-Verbindungen zu öffnen.

![Schritt 2](/images/Equinix-Step2.png)

**Schritt 3:**

Nachdem Sie auf die Schaltfläche **Direct Link Exchange bestellen** oben auf der Seite geklickt haben, wird ein Bestellformular angezeigt, in dem Sie die Konfigurationsparameter für die IBM Cloud Direct Link Exchange-Verbindung angeben können.

![Schritt 3](/images/Equinix-Step3.png)

**Schritt 3a:**

(Optional) Wenn diverse Ports zugänglich sind und Sie zuvor die erste virtuelle Verbindung bereitgestellt haben, wird eine Anzeige ähnlich der folgenden geöffnet. Die Anzeige enthält zwei Ports und ermöglicht Ihnen das Auswählen der zweiten virtuellen Verbindung.

![Darstellung mit zwei Ports](/images/exchange-2-ports-image.png)

**Schritt 4:**

Im Bestellformular geben Sie die folgenden Parameter ein, um Direct Link zu konfigurieren:
  * Geben Sie den Verbindungsnamen für die IBM Cloud Direct Link-Verbindung ein.
  * Wählen Sie aus der Liste den Ort für den Bereitstellungspunkt aus, an dem die IBM Cloud Direct Link-Verbindung hergestellt werden soll.
  * Wählen Sie aus der Liste den Namen des bevorzugten Cloud-Providers für den Datenaustausch aus.
  * Wählen Sie die für die Verbindung erforderliche Verbindungsgeschwindigkeit aus.
  * Wählen Sie die für die Verbindung erforderliche Routing-Option aus.
  * Geben Sie eine ASN-Nummer aus dem Bereich ein, der in dem Informationsfenster für den BGP-Austausch angegeben ist.

**Schritt 5:**

Während Sie diese Werte auswählen oder eingeben, wird Ihnen im linken Fensterbereich eine näherungsweise berechnete monatliche Gebühr angezeigt.

![Schritte 4 und 5](/images/Equinix-Step4-5.png)

**Schritt 6:**

Nachdem Sie die Werte eingegeben haben, wird im nächsten Bildschirm der Benutzerschnittstelle der monatliche Preis auf Grundlage der ausgewählten Optionen angezeigt.

**Schritt 7:**

Bevor Sie die Bestellung für IBM Cloud Direct Link aufgeben können, müssen Sie den Vertragsbedingungen **ZUSTIMMEN**. Bitte lesen Sie die Vertragsbedingungen sorgfältig, da sie wichtige technische Informationen enthalten, die Sie wissen müssen, bevor Sie fortfahren. **(Hinweis: Werden die Vertragsbedingungen nicht akzeptiert, so wird beim Aufgeben der Bestellung ein IBM Support-Ticket generiert.)** Die folgenden Abbildungen zeigen die möglicherweise angezeigten Bildschirme, je nach Ihrer Auswahl im jeweiligen Schritt.

Die folgende Abbildung zeigt den Bildschirm mit den Vertragsbedingungen:

![Schritt 7](images/Equinix-Step7.png)

Die folgende Abbildung zeigt den Bildschirm, der möglicherweise angezeigt wird, wenn Sie den Vertragsbedingungen beim Aufgeben der Bestellung nicht zustimmen. Der Bildschirm zeigt die generierte Ticketnummer an:

![Schritt 7 bei Zustimmung](/images/Equinix-Step7-NoAgree.png)

Die folgende Abbildung zeigt ein Beispiel für das Öffnen eines Tickets:

![Schritt 7 mit Ticket](/images/Equinix-Step7-NoAgree-Ticket.png)

**Schritt 8:**

Nachdem Sie den Vertragsbedingungen zugestimmt haben und die Bestellung aufgeben, wird anschließend ein IBM Support-Ticket generiert, sodass Sie mit der Servicebereitstellung fortfahren können. Die Ticketnummer wird nach Aufgabe der Bestellung in der Benutzerschnittstelle angezeigt. 

![Schritt NE1](/images/Non-Equinix-Step1.png)

**Schritt 9:**

Indem Sie auf die Ticketnummer in der Nachricht klicken, können Sie die Ticketdetails anzeigen.

![Schritt NE2](/images/Non-Equinix-Step2.png)
