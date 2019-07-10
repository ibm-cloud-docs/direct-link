---
copyright:
  years: 2018, 2019
lastupdated: "2019-04-02"

keywords: Intercloud, Frankfurt, PoPs, Connect, Exchange, Chennai, Equinix, Megaport, Kinx, diversity, Bluefringe, CenturyLink, BT, Sao Paulo, Tokyo, Japan, PCCW, Colt, blog, service provider, partner, Telia, Internexion, Packet Fabric, Global Routing, expanded, market

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:important: .important}

# Ankündigung: Global Routing-Richtlinienänderung ab 1. Juli

Wirksam ab 1. Juli 2019 - IBM Direct Link Global Routing-Richtlinienänderung
{: important}

Um das Kundenerlebnis zu verbessern und einen erhöhten Nutzen zu bieten, erweitern wir den IBM Direct Link Global Routing-Service. Zu den wichtigsten Verbesserungen zählen:

* **Erweiterte lokale Märkte:** Wir führen eine Anpassung unserer Standorte durch, zu denen Kunden innerhalb ihrer lokalen Märkte eine Verbindung herstellen können. Wir passen alle Bereitstellungspunktstandorte im IBM Cloud-Netz an, damit Kunden, die an unseren Bereitstellungspunktstandorten eine Verbindung mit der IBM Cloud herstellen, Verbindungen zu Ressourcen in einem oder mehreren unserer Rechenzentren auf der ganzen Welt herstellen können.

* **Neues Preismodell:** Um die Preisgestaltung besser an die ausgewählten Verbindungsgeschwindigkeiten anzupassen, ändern wir das Preismodell für unseren IBM Direct Link Global Routing-Service.

* **Unbegrenzter Direct Link-Datenverkehr:** Wir schaffen global die Gebühren für Netzdatenverkehrsüberschreitungen für Kunden ab, die entweder Local oder Global Routing für Direct Link-Datenverkehr bei privatem Netz zwischen IBM Cloud-Bereitstellungspunkten und -Rechenzentren verwenden.

## Übersicht über IBM Cloud Direct Link Global Routing
{: #ibm-cloud-direct-link-global-routing-overview}

Alle aktuellen Direct Link-Angebote beinhalten Local Routing ohne zusätzliche Gebühren. Dieser Service umfasst den Zugriff auf Rechenzentren in dem lokalen Markt, in dem sich die Direct Link-Verbindung befindet. Er stellt unbegrenzten eingehenden und ausgehenden Datenverkehr über private Direct Link-Verbindungen zu IBM Cloud-Ressourcen innerhalb des Kontos des Kunden bereit. Mit der Option 'Local Routing' ist der Direct Link-Datenverkehr auf die Services beschränkt, die von diesem lokalen Markt bereitgestellt werden.

Um Netzdatenverkehr außerhalb des lokalen Marktes, an den Direct Link angeschlossen ist (Bereitstellungspunkt oder Rechenzentrum), weiterzuleiten, müssen Sie die Option 'Global Routing' hinzufügen, um den Zugriff auf alle IBM Cloud-Rechenzentren weltweit zu erweitern.

Global Routing wird auf einzelne Direct Link-Services angewendet. Global Routing wird nicht über Aggregation angewendet. Es muss für jeden Direct Link-Service angegeben werden, für den Konnektivität außerhalb eines bestimmten Marktes gewünscht wird.

## Erweiterte lokale IBM Direct Link-Märkte
{: #announce-expanded-ibm-direct-link-local-markets}

Wir erweitern die lokalen Direct Link-Märkte, um unseren Kunden weltweit mehr lokale Routing-Optionen zur Verfügung zu stellen. Die neuen Zuordnungen zu lokalen Märkten sind im Folgenden aufgelistet:

* Zum lokalen Markt Dallas gehören jetzt die Bereitstellungspunkte Denver, Houston und Chicago.
* Zum lokalen Markt Washington (D.C.) gehören jetzt die Bereitstellungspunkte New York, Atlanta und Miami.
* Zum lokalen Markt San Jose gehört jetzt der Bereitstellungspunkt Los Angeles.
* Zum lokalen Markt Oslo gehört jetzt der Bereitstellungspunkt Stockholm.
* Zum lokalen Markt Sydney gehört jetzt der Bereitstellungspunkt Perth.
* Zum lokalen Markt Hongkong gehört nach dessen Start der Bereitstellungspunkt Taipeh.
* Zum lokalen Markt Tokio gehört nach dessen Start der Bereitstellungspunkt Osaka.
* Zum lokalen Markt Chennai gehört nach dessen Start der Bereitstellungspunkt Mumbai.

Diese Änderungen sind unter der folgenden Adresse in Tabellen zusammengefasst: https://cloud.ibm.com/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#expanded-ibm-direct-link-local-markets

## Preismodell für IBM Cloud Direct Link Global Routing
{: #announce-ibm-cloud-direct-link-global-routing-pricing-model}

Alle IBM Cloud Direct Link-Angebote umfassen standardmäßig das Netzrouting innerhalb eines lokalen Marktes. Ab dem 1. Juli 2019 wird die Preisgestaltung für die Option 'Global Routing' an die Verbindungsgeschwindigkeit der Direct Link-Verbindung angepasst. Durch diese Anpassung erhalten Kunden über alle für Direct Link-Angebote verfügbaren Verbindungsgeschwindigkeiten hinweg einen Mehrwert.

Die Preisstruktur finden Sie unter https://cloud.ibm.com/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-global-routing-add-on

## Netztransitüberschreitungsgebühren für IBM Cloud Direct Link Global Routing
{: #announce-ibm-cloud-direct-link-global-routing-network-transit-overage-charges}

Mit dieser Ankündigung streichen wir die Netztransitgrenzwerte und Überschreitungsgebühren für Kunden mit der Option 'Global Routing'. Die bisherige Preisstruktur enthielt Netztransitkontingente sowie Überschreitungsgebühren für ausgehenden Datenverkehr außerhalb des lokalen Marktes des Kunden. Durch die neue Preisstruktur werden diese Netzverkehrgebühren abgeschafft. Ab der Wirksamkeit dieser Ankündigung gibt es für eingehenden und ausgehenden Datenverkehr über Direct Link-Verbindungen keine Überschreitungen mehr.

## Wirksamkeitsdatum
{: #announce-effective-date}

Diese Änderungen werden am Montag, dem 1. Juli 2019, wirksam und auf alle neuen Bestellungen beim nächsten Abrechnungszyklus nach diesem Datum angewendet.

Beachten Sie dringend, dass in Verbindung mit dieser aktualisierten Automatisierung alle Direct Link-Verbindungen, die Global Routing erfordern, vor diesem Datum entsprechend aktualisiert werden sollten. Alle Upgrades oder Downgrades eines Direct Link-Service werden zu einer Automatisierung führen, die prüft, ob Global Routing vorhanden ist. Wenn Global Routing nicht vorhanden ist, wird jeder Datenverkehr über Direct Link-Verbindungen auf die lokalen Märkte beschränkt.

Wir empfehlen den Kunden dringend, ihr IBM Cloud-Routing über Direct Link-Services zu überprüfen und Tickets zu öffnen, um das Routing über bestehende Direct Link-Services zu korrigieren.
