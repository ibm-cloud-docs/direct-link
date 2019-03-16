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

# Übersicht über VRF (Virtual Routing and Forwarding) in IBM Cloud
{: #overview-of-virtual-routing-and-forwarding-vrf-on-ibm-cloud}

Per Definition ist die virtuelle Routenwahl und Weiterleitung (Virtual Routing and Forwarding, VRF) eine Technologie, die in IP-Netzroutern (IP = Internet Protocol) enthalten ist. Sie wird als ein inhärenter Backbone-Service bereitgestellt.

## Konnektivitätsoptionen für IBM Cloud

**Verteilte Cloudressourcen** sind Ressourcen, die auf mehrere Standorte oder sogar auf mehrere Teilnetze bzw. VLANs verteilt sind. Für diese Ressourcen ist eine Routingfunktion erforderlich, damit sie untereinander kommunizieren können; dies ist sogar innerhalb eines privaten Netzes nötig. In diesem Dokument wird eine Tenantkommunikationsoption für mehrfache Isolierung (Multiple Isolation) beschrieben, die auch oft als _Kunden-VRF_ bezeichnet wird. Sie wird als MPLS-Layer-3-VPN (RFC 4364) für den globalen {{site.data.keyword.cloud}}-Backbone implementiert. 

Im Allgemeinen bietet die IBM Cloud-Plattform zwei Optionen für die Routenwahl für das private Netz und stellt Konnektivität für Pods und Rechenzentren bereit:

1. **Gemeinsam genutzter Tenant:** Ein einheitliches logisches Netz, das von allen Tenants gemeinsam genutzt wird, die dieses Modell verwenden; für die Trennung werden hierbei automatisierte Zugriffssteuerungslisten (ACLs) verwendet und das VLAN-Spanning ist aktiviert. (Diese Option wird in diesem Dokument nicht beschrieben.)

2. **Mehrfache Isolierung:** Ein dediziertes logisches Netz pro Tenant, das keine Interaktion mit den logischen Netzen anderer Tenants zulässt.  

In diesem Dokument wird der Begriff **Kunden-VRF** verwendet, um die Netzkonnektivität _mehrfache Isolierung_ zu beschreiben.

## VRF-Übersicht (Technologie für mehrfache Isolierung)

VRF (Virtual Routing and Forwarding) ermöglicht das Vorhandensein mehrerer Instanzen einer Routing-Tabelle und ihre gleichzeitige Verwendung in einem Router. Mit VRF wird das VRF-Netz jedes Cloud-Tenants innerhalb der Routing-Tabelle segmentiert. Diese Segmentierung ermöglicht Überschneidungen von IP-Adressen und führt nicht zu Interaktionen oder Interferenzen mit den VRFs anderer Tenants. IBM Cloud nutzt den Großteil des `10.0.0.0/8`-Netzes, das sich mit vielen fernen Netzen überschneiden kann, z. B. mit Netzen, die in Rechenzentren von Kunden bereitgestellt sind. 

Bei Verwendung von VRF (Virtual Routing and Forwarding) können IBM Cloud-Tenants ferne IP-Adressen verwenden, für die normalerweise keine Überschneidung in der globalen Tabelle zulässig wäre. Von IBM werden trotzdem die folgenden Link-Local-Adressen und Multicastadressen des Typs RFC 1918 reserviert, für die von diesem VRF-Service kein Routing möglich ist: 

* `10.0.0.0/14`
* `10.200.0.0/14`
* `10.198.0.0/15`
* `169.254.0.0/16`
* `224.0.0.0/4`
* `166.9.0.0/16` (wird vom privaten Endpunktservice verwendet)
* Alle IP-Bereiche, die Ihren VLANs auf der IBM Plattform zugeordnet sind.

IBM arbeitet an der Bereitstellung einer Cloud der nächsten Generation, um Virtual Private Cloud (VPC) in unseren Verfügbarkeitszonen (Availability Zones, AZs) zu ermöglichen. Diese neue VPC-Funktion ermöglicht BYoIP (Bring Your own IP) in den VPC-fähigen Verfügbarkeitszonen, die sich in Dallas, Washington DC, London, Frankfurt, Tokio und Sydney befinden. 

Jeder Tenant mit Zugang zum Backbone, der VRF verwendet, kann über (nur) einen _Kunden-VRF_-Service pro Direct Link verfügen; dies ermöglicht Verbindungen zwischen allen Servern des Tenants unabhängig vom Standort. Ein IBM Cloud-Tenant kann jedoch über mehrere Direct Link-Konten verfügen, die über einen einzigen Router für Querverbindungen verwendet werden können.   

* Von den Servern eines Tenants in einem beliebigen VLAN, in einem beliebigen Pod und einem beliebigen weltweiten Rechenzentrum können alle anderen Server des Tenants auf der Welt erreicht werden.

* Jeder Service des Typs 'Kunden-VRF' eines Tenants ist mit den gängigen gemeinsam genutzten Servicenetzen verbunden, um eine private Erreichbarkeit für diese Server bereitzustellen, damit DNS, gemeinsamer Speicher, Überwachungen, usw. verwendet werden können.

* Der Service 'Kunden-VRF' ist ein Verbindungsservice, von dem eine Isolierung zwischen den Tenants bereitgestellt wird. Alle weiteren Steuerungen, die für einen Tenant erforderlich sind, müssen separat mithilfe von Gateways, Sicherheitsgruppen oder hostbasierten Steuerungen bereitgestellt werden.

## Vorteile des Wechsels zu VRF

**Die primären Vorteile sind: **

* Bewährte und weithin anerkannte Trenntechnik _Mehrfache Isolierung_. Für die Auditoren und Compliance-Manager vieler Cloudkunden ist der Ansatz eines Level-3-VPNs überzeugender (als Zugriffssteuerungslisten).    

* IBM Cloud-Kunden können die Reichweite ihres Netzes erheblich erweitern oder verlagern, da im gesamten IBM Netz zusätzliche neue Standorte oder Anwendungen bereitgestellt werden. 

* Tenantspezifische Routing-Tabellen reduzieren die Möglichkeit von IP-Adressüberschneidungen, ohne das Risiko einer Überschneidung mit Teilnetzen anderer Tenants oder anderen Teilen des Netzes, die nicht anwendbar sind.

**Einige kleine Nachteile im Vergleich zum älteren ACL-Modell sind: **  

* Für den Wechsel zu 'Kunden-VRF' ist ein Wartungsfenster erforderlich, was eine kurze Unterbrechung der Datenübertragung auf dem Backbone mit sich bringt.

* Der Fernzugriff über die verwalteten VPN-Services (SSL, IPSec) ist auf das lokale Rechenzentrum beschränkt; der gemeinsam genutzte ACL-Backbone ermöglicht jedoch den globalen Zugriff von jedem beliebigen Eingangspunkt aus.

* VLAN-Spanning ist innerhalb Ihres Mietverhältnisses mit _mehrfacher Isolierung_ nicht verfügbar. 

## Was geschieht während des Kontokonvertierungsvorgangs?

Viele IBM Cloud-Kunden arbeiten derzeit mit einem gemeinsam genutzten Tenant-Modell im IBM Cloud-Netz. Während der Konvertierung wird der Wechsel des Tenants zur Verwendung des Service 'Kunden-VRF' vollzogen; dies ist meistens mit einem neuen Direct Link-Abonnement oder einer anderen Anforderung verbunden.  

Der Konvertierungsprozess ist mit einer Netzunterbrechung verbunden, bei dem die VLANs und ihre Teilnetze vom ACL-Backbone abgehängt und anschließend wieder an den Service 'Kunden-VRF' angehängt werden. Als Ergebnis dieses Vorgangs gehen für einen Moment Pakete des Datenverkehrs in die VLANs oder aus den VLANs verloren. Der Datenfluss der Pakete in den VLANs wird davon nicht beeinträchtigt. In den Fällen, in denen ein Netzgateway wie zum Beispiel 'FortiGate Security Appliance' oder 'Virtual Router Appliance' beteiligt ist, tritt zwischen den an dieses Gateway angeschlossenen VLANs keine Unterbrechung auf. Auf den Servern selbst kommt es zu keinen Netzausfällen und die meisten Workloads werden automatisch wiederhergestellt, wenn der Datenfluss wieder aufgenommen wird. Die Gesamtdauer der Unterbrechung hängt vom Ausmaß der Topologie des Tenants ab, also der Anzahl der Teilnetze, VLANs und Pods, die das Mietverhältnis umfasst. 

![Der Konvertierungsprozess](/images/vrf-on-ibm-cloud.png)

Während der Migration werden die VLANs vom Backbone getrennt; danach wird die Verbindung zum Service 'Kunden-VRF' wiederhergestellt. Die Dauer der Unterbrechung variiert abhängig von der Menge der beteiligten VLANs, Pods und Rechenzentren. Der Datenverkehr zwischen den VLANs wird zwar unterbrochen, die Server bleiben jedoch mit dem Netz verbunden. Eine Anwendung kann abhängig von ihrer Sensitivität in Bezug auf Paketverluste beeinträchtigt werden.

## Vorgehensweise zum Starten der Umwandlung
{: #how-you-can-initiate-the-conversion}

IBM Cloud-Bestandskunden können ein Support-Ticket über ihre [IBM Cloud-Konsole ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")]( https://control.bluemix.net/support/unifiedConsole/tickets/add) für das Konto öffnen und die Migration zu VRF anfordern. Für das Ticket muss 'Private Network Question' angegeben werden und im Support-Ticket muss der folgende Text enthalten sein:

'We are requesting that account _Kontonummer des Kunden_ is moved to its own VRF. We understand the risks and approve the change.  Please reply back with the scheduled window(s) of time where this change will be made so we can prepare for the migration.'

Die Migration wird von einem Team von IBM Cloud Network Engineering durchgeführt. Bis auf den vereinbarten Zeitplan sind von Ihnen keine weiteren Informationen erforderlich. Abhängig von der Komplexität Ihres Kontos kann der Paketverlust in der Regel 15 bis 30 Minuten dauern. (Er kann länger dauern, wenn Ihr Konto über traditionelle Direct Link-Verbindungen verfügt.) Der Prozess ist hochgradig automatisiert; er erfordert eine minimale Interaktion durch das IBM Team und sollte transparent sein. 
