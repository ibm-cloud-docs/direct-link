---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-06-12"

keywords: provisioning, order, Exchange, Equinix, automated, status, connection, legacy, customer, portal, Softlayer

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


# Bereitstellung von IBM Cloud Direct Link Exchange für Equinix über das traditionelle Kundenportal
{: #provisioning-ibm-cloud-direct-link-exchange-for-equinix-legacy}

Dieses Dokument enthält schrittweise Anweisungen für die Bereitstellung von Direct Link Exchange für Equinix unter Verwendung des traditionellen IBM Cloud-Kundenportals.
{: shortdesc}

Ist die Bestellung von {{site.data.keyword.cloud}} Direct Link für Equinix Cloud Exchange vorgesehen, geschieht die Servicebereitstellung voll automatisiert, d. h. Sie können eine Bestellung für eine {{site.data.keyword.cloud_notm}} Direct Link-Verbindung (Equinix) aufgeben, ohne ein IBM Support-Ticket öffnen zu müssen.

Die Automatisierungsfunktionalität ist derzeit auf Equinix Cloud Exchange beschränkt. In nachfolgenden Releases wird die Automatisierung auch für andere Provider aktiviert sein.
{:note}

## Voraussetzungen
{: #cloud-exchange-equinix-prerequisites-legacy}

Damit Sie die automatisierte Bestellfunktion verwenden können, müssen Ihre privaten VLANs einer VRF-Instanz im privaten {{site.data.keyword.cloud_notm}}-Netz zugeordnet sein. Ist diese Voraussetzung nicht erfüllt, so wird bei Ihrer Bestellung über das Kundenportal ein IBM Support-Ticket generiert.

## Schritte für die Bestellung und Bereitstellung
{: #cloud-exchange-steps-for-ordering-and-provisioning-legacy}

**Schritt 1:**

Führen Sie die Schritte 1 bis 7 des normalen [Bestellverfahrens für Cloud Exchange](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-legacy) aus.

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
