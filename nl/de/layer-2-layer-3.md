---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-30"

keywords: layer 2, layer 3, interconnect, partner, multi-cloud, other clouds, BGP, XCR

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Vergleich von Layer-2- und Layer-3-Verbindungen für Direct Link
{: #comparing-layer-2-layer-3}

{{site.data.keyword.cloud}} Direct Link akzeptiert OSI-Layer-2- und -Layer-3-Partnerverbindungen von Netzserviceanbietern. Einige Netzserviceanbieter bieten Services für beide dieser Layer in unterschiedlichen Netzen an. Einige Anbieter haben sich jedoch möglicherweise entschieden, **nicht** alle ihre Netze mit {{site.data.keyword.cloud_notm}} zu verbinden. 

Berücksichtigen Sie bei der Planung Ihrer {{site.data.keyword.cloud_notm}} Direct Link-Bereitstellung die Merkmale von Layer-2- und Layer-3-Verbindungen, damit Sie eine Bereitstellung erstellen können, die Ihren Anforderungen am besten entspricht.

## Hinweise zu Layer-2-Verbindungen
{: #layer-2-networks}

Für jede VLAN-basierte virtuelle Verbindung, die Sie mit einer Layer-2-Partnerverbindung erstellen, müssen Sie eine BGP-Sitzung zwischen Ihren lokalen Routern und dem IBM Cloud-XCR-Router konfigurieren und erstellen. IBM Cloud stellt Ihnen für die Einrichtung einer BGP-Sitzung mit Ihrem Router eine `/31`-IPv4-Zuweisung bereit.

* Layer-2-Netze bieten Optionen für einfache Eins-zu-eins-Verbindungen zwischen Unternehmen und {{site.data.keyword.cloud_notm}}. 
* Layer-2-Services setzen auf VLANs statt IP-Adressen. 
* Im Vergleich zu Layer-3-Services führen Layer-2-Services möglicherweise zu niedrigeren Kosten, geringerer Latenz und weniger Systemaufwand. 
* Layer-2-Netze führen nicht zu Einschränkungen für die Layer-3-Funktionen, die ein Unternehmen aktivieren kann.

## Hinweise zu Layer-3-Verbindungen
{: #layer-3-networks}

Für Layer-3-Verbindungen richtet Ihr Service-Provider für jede virtuelle Verbindung eine BGP-Sitzung zwischen IBM Cloud XCR-Routern und den Edge-Routern des Anbieters ein. Sie müssen BGP nicht mit IBM Cloud für Ihren lokalen Router konfigurieren, da Ihr Service-Provider die BGP-Konfiguration für IBM Cloud verwaltet.

* Layer-3-IP VPN- oder -AVPN-Netze ermöglichen Any-to-any-Konnektivität. 
* Für Layer-3-Netze ist es erforderlich, dass der Netzserviceanbieter eine BGP-Sitzung zwischen dem Unternehmen und {{site.data.keyword.cloud_notm}} aufrechterhält. 
* Bestimmte Netzserviceanbieter schränken möglicherweise bestimmte Funktionen in ihrem Netzwerk ein, wenn Layer-3-Verbindungen verwendet werden, z. B. ASN-Voranstellung, GRE-Tunnelung usw. Informieren Sie sich bei Ihrem Provider über mögliche Einschränkungen.

## Partnerverbindungstabelle
{: #partner-interconnection-table}

In der folgenden Tabelle werden die Verbindungstypen zusammengefasst, die von den einzelnen {{site.data.keyword.cloud_notm}}-Partnern bereitgestellt werden. 

| Partner | Verbindungstyp |  
|-------|-------|
| AT&T NetBond® for Cloud | Layer 3 |
| AT&T Cloud Gateway (bisher unter der Bezeichnung RedFringe)| Layer 3 |
| Bell Canada | Layer 3 | 
| British Telecom | Layer 3  | 
| CenturyLink IP VPN | Layer 3 | 
| CenturyLink Dynamic Connections | Layer 2 | 
| Chief Telecomm | Layer 2 |
| Colt | Layer 2  | 
| Console Connect by PCCW | Layer 2 |
| Digital Realty Service Exchange | Layer 2 | 
| Epsilon | Layer 2 | 
| IBM BlueFringe | Layer 3 | 
| Intercloud | Layer 3 |
| Megaport | Layer 2 |
| MWS GNPP | Layer 3 |
| Neutrona | Layer 2 |
| NTT | Layer 3 |
| PacketFabric | Layer 2  |
| Softbank | Layer 3 |
| SES Networks | Layer 2  |
| Tata IZO™ Private Connect  | Layer 3 | 
| Telia | Layer 3 |
| Telstra | Layer 3 |
| Tokai | Layer 2 | 
| Verizon SCI| Layer 3 |
| Zayo Cloud Link | Layer 2 |
