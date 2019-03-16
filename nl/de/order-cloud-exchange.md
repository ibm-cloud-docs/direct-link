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

# Vorgehensweise zur Bestellung von IBM Cloud Direct Link Exchange
{ # how-to-order-ibm-cloud-direct-link-exchange}

1. Überprüfen Sie die Funktionalität Ihres Netzbetreibers zum Erreichen des geeigneten Bereitstellungspunkts und zur Querverbindung mit dem zugehörigen Exchange-Provider.
2. Verwenden Sie das [Kundenportal ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com/), um eine Anforderung für {{site.data.keyword.cloud}} Direct Link Exchange zu öffnen und die angeforderten Informationen auszufüllen. (Unterstützung von IBM Sales Engineers kann angefordert werden.) Wenn Sie den Equinix-Provider verwenden, können Sie die [automatisierte Bestellung](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix) nutzen.
3. Wenden Sie sich an Ihren Exchange-Provider und vereinbaren Sie Konnektivität für Ihren Datenaustausch.
4. Bestellen Sie Konnektivität zwischen Ihrem Netzbetreiber und dem Exchange-Provider.
5. Bestellen Sie eine "virtuelle Verbindung" durch den Exchange-Provider und verweisen Sie auf die Ticket-ID der {{site.data.keyword.BluSoftlayer_notm}} Direct Link-Anforderung als Ihre "Anforderungs-ID" oder "Berechtigungs-ID".
6. Die IP-Zuordnung für die Netzinfrastruktur von {{site.data.keyword.BluSoftlayer_notm}} erfolgt innerhalb von drei Werktagen nach erfolgreicher Abwicklung der Anforderung für eine virtuelle Verbindung.
 
## Standorte
 
 In der Tabelle sind die IBM Cloud-Rechenzentren aufgeführt, die Direct Link Exchange-Konnektivität bieten:
 
| Exchange-Provider	| Code für IBM Rechenzentrum |
|-------------|-----------------------|
| AT Tokyo | TOK02 |
| Ascenty | SAO01* |
| Cologix | MON02, TOR02 |
| Cyrus One | DAL13 |
| DE-CIX | FRA01 |
| Equinix | HKG01,SNG02, SYD02, TOK01, AMS02, PAR02, CHI01, DAL03, NYC02, NYC03, SAO02, SJC02, TOR02, WDC02, LON01, FRA03 |							
| InterXion | FRA01, STO01 |
| KINX	| SEO02 |
| NextDC | MEL02, SYD03* |
| SK C&C | SEO01 |

* Demnächst verfügbar

## Preise

Informationen zu Preisen finden Sie im [Preisdokument](/docs/infrastructure/direct-link/pricing.html).
