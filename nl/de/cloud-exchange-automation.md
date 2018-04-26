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

# Schritt für Schritt: Bestellung von IBM Cloud Direct Link Exchange

Auf dieser Seite erfahren Sie, wie der IBM Cloud Direct Link Exchange-Service bestellt wird. Ist die Bestellung von IBM Cloud Direct Link für Equinix Cloud Exchange vorgesehen, so geschieht die Servicebereitstellung voll automatisiert, d. h. Sie können eine Bestellung für eine IBM Cloud Direct Link-Verbindung (Equinix) aufgeben, ohne ein IBM Support-Ticket öffnen zu müssen.

**(Hinweis: Die Automatisierungsfunktionalität ist derzeit auf Equinix Cloud Exchange beschränkt. In nachfolgenden Releases wird die Automatisierung auch für andere Provider aktiviert sein.)**

## Voraussetzungen

Um die Automatisierungsfunktion nutzen zu können, müssen Ihre privaten VLANs einer VRF-Instanz im privaten IBM Cloud-Netz zugeordnet sein. Ist diese Voraussetzung nicht erfüllt, so wird bei Ihrer Bestellung über das Kundenportal ein IBM Support-Ticket generiert.

 * [Vorgehensweise zur Bestellung von Cloud Exchange](#how-to-order-cloud-exchange)
 * [Vorgehensweise zur Bestellung von Cloud Exchange für Equinix](#how-to-order-cloud-exchange-for-equinix)

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

## Vorgehensweise zur Bestellung von Cloud Exchange für Equinix

**Schritt 1:**

Folgen Sie den Schritten 1 bis 7 aus dem oben beschriebenen Bestellverfahren für Cloud Exchange

**Schritt 2:**

Nachdem Sie die Bestellung aufgegeben haben, beginnt die Bereitstellung von IBM Cloud Direct Link.

![Schritt 8](/images/Equinix-Step8.png)

**Schritt 3:**

Nach der Aufgabe der Bestellung wird Ihnen der Status Ihrer Verbindung angezeigt. Wenn die Konfiguration auf Seiten von IBM erfolgreich abgeschlossen wurde, wird Ihnen der Status **Bereitgestellt** angezeigt. Ist die Konfiguration noch nicht fertiggestellt, wird der Status **In Bearbeitung** angezeigt. Ist die Konfiguration fehlgeschlagen, wird der Status **Erstellung fehlgeschlagen** angezeigt. Wurde die Konfiguration erfolgreich abgeschlossen und die BGP-Verbindung ist aktiv, wird der Status **AKTIV** angezeigt.

![Schritt 9, ](/images/Equinix-Step9-InProgress.png)

Die folgende Abbildung zeigt die verschiedenen Zustände der Verbindung nach dem Aufgeben der Bestellung:

![Schritt 9, ](/images/Equinix-Step9-UP.png)

**Schritt 4:**

Hat die Verbindung den Status **Bereitgestellt**, können Sie die Verbindung einblenden, indem Sie vor dem **Namen** der Verbindung auf **>** klicken. Vermerken Sie anschließend die Angaben zur **IP-Adresse des Kunden** und zum **Serviceschlüssel**. Diese Informationen werden jeweils zur Konfiguration des Edge-Routers des Kunden sowie als Berechtigungsschlüssel für die Konfiguration auf Seiten des Cloud-Providers (Equinix) benötigt.

![Schritt 10](/images/Equinix-Step10-Provisioned.png)

**Schritt 5:**

Haben die Verbindungen den Status **Bereitgestellt**, so wird Ihnen, nachdem Sie durch Klicken auf **>** vor der Verbindung die Verbindung erweitert haben, bei fehlender Übereinstimmung mit der Peer-Linkgeschwindigkeit eine Fehlernachricht angezeigt. Ist die Geschwindigkeit auf Seiten von IBM und Equinix dieselbe, wird diese Fehlerbenachrichtigung nicht mehr angezeigt.

![Schritt 11](/images/Equinix-Step11-PortMismatch.png)

**Schritt 6:**

Haben die Verbindungen den Status **Erstellung fehlgeschlagen**, wird ein IBM Support-Ticket generiert und weitere Details werden über das Support-Ticket kommuniziert. Wenn Sie die Verbindung einblenden, werden die Details zum Support-Ticket angezeigt.

![Schritt 12](/images/Equinix-Step12-CreateFailed.png)

**Schritt 7:**

Haben die Verbindungen den Status **Bereitgestellt**, **AKTIV** oder **INAKTIV**, dann können Sie die Verbindung **löschen**, indem Sie auf die Spalte **AKTIONEN** neben der Verbindung klicken.

![Schritt 13](/images/Equinix-Step13-Delete.png)

**Schritt 8:**

Haben die Verbindungen den Status **Erstellung fehlgeschlagen**, dann können Sie die Verbindung **abbrechen**, indem Sie auf die Spalte **AKTIONEN** neben der Verbindung klicken.

