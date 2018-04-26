---

copyright:
  years: 2017
lastupdated: "2017-12-04"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud Direct Link konfigurieren

Nachdem die IBM Cloud Direct Link-Konnektivität hergestellt wurde, können Sie den Schritten in diesem Dokument folgen, um Ihr Teilnetz für die Interaktion mit IBM Cloud zu konfigurieren.

Im Allgemeinen müssen Sie, um Ihre IBM Cloud Direct Link-Verbindung zu aktivieren, einige Schritte zur grundlegenden Netzkonfiguration durchführen. Anschließend muss ein Border Gateway Protocol (BGP) eingerichtet werden. Während des Einrichtungsprozesses wird ein IBM Servicetechniker Sie dabei unterstützen, Ihr Netz für die Verwendung der obligatorischen VRF-Funktion (VRF, Virtual Routing Function) zu unterstützen.

## Grundlegende Netzkonfiguration

1. Definieren Sie Ihr fernes Netz mithilfe des in RFC1918 festgelegten privaten Standardadressraums. 
 * Bei neuen Umgebungen wird empfohlen, **nicht** den Adressraum 10.0.0.0/8 zu verwenden. 
 * Bei vorhandenen Umgebungen, die 10.0.0.0/8 verwenden, sollten Sie eine genauere Beurteilung durchführen, um sicherzustellen, dass es keine Konflikte mit dem {{site.data.keyword.BluSoftlayer_notm}}-Servicenetz oder den Netzen gibt, die Ihrem Konto bereits zugewiesen sind.

2. Unsere Mitarbeiter bei {{site.data.keyword.BluSoftlayer_notm}} weisen entweder /31 oder /30 für jede Verbindung zu und konfigurieren eine Schnittstellen-IP-Adresse für die XCR-Infrastruktur von {{site.data.keyword.BluSoftlayer_notm}}.  

3. Konfigurieren Sie die Schnittstelle auf dem Edge-Router des Kunden (CER, Customer Edge Router) und verwenden Sie dabei die von uns bereitgestellte IP-Adresse: Nutzen Sie die XCR-IP von {{site.data.keyword.BluSoftlayer_notm}} ganz einfach als nächste Station für den an {{site.data.keyword.BluSoftlayer_notm}} gerichteten Datenverkehr. 

4. Bei zurückfließendem Datenverkehr verwendet {{site.data.keyword.BluSoftlayer_notm}} die zugewiesene CER-IP als nächste Station für den gesamten Datenverkehr, der für das ferne Netz bestimmt ist, wie über BGP angegeben.

## BGP konfigurieren

Zum Austausch von Routeninformationen mit Ihrer Umgebung muss für {{site.data.keyword.BluSoftlayer_notm}} BGP konfiguriert sein.  

1. **ASN**: {{site.data.keyword.BluSoftlayer_notm}} weist ein privates ASN für die einzelnen Kunden zu. Alternativ können Sie Ihr eigenes öffentliches ASN verwenden. Ihre bevorzugte Methode müssen Sie zum Zeitpunkt Ihrer Bestellung angeben. Das Ihnen zugewiesene private ASN wird Ihnen im Rahmen des Implementierungsprozesses bereitgestellt.

2. **VRF**: Bei der Verwendung von VRF macht {{site.data.keyword.BluSoftlayer_notm}} die Ihrem Kundenkonto zugewiesenen privaten Teilnetze zugänglich.  Sie müssen die fernen Netze zugänglich machen, die über das private {{site.data.keyword.BluSoftlayer_notm}}-Netz erreichbar sein sollen. Die folgenden Netze werden herausgefiltert und können nicht akzeptiert werden: 0.0.0.0, 10.0.0.0/14, 10.198.0.0/15, 10.200.0.0/14, 169.254.0.0/16, 224.0.0.0/4. Es liegt in Ihrer Verantwortung als Kunde, die Werbung rund um das IBM Cloud-Netz zu verwalten. (Weitere Informationen zu VRF finden Sie im nächsten Abschnitt.)

3. **ECMP**: Für Kunden, die eine Redundanz an einem unterstützten Standort schaffen möchten, unterstützt {{site.data.keyword.BluSoftlayer_notm}} die Implementierung von Equal Cost Multipath (ECMP), um Lastausgleich und Redundanz über beide Verbindungen hinweg bereitzustellen. Diese ECMP-Konfiguration sollte zum Zeitpunkt der Bestellung angefordert werden.

## Redundanz und Diversität

IBM Cloud Direct Link bietet Diversität. Die Kunden sind für die Bereitstellung von Redundanz über ihre BGP-Schemas verantwortlich.

Wenn Sie ECMP zwecks Redundanz auswählen, müssen beide BGP-Sitzungen auf demselben Router für Querverbindungen (XCR) vorhanden sein. Sie geben also die Diversität des Routers auf und sind bei Fehlern des Routers einem Risiko ausgesetzt. Sie erhalten Layer-3-Redundanz, verlieren aber die Layer-2-Redundanz.

## Weitere Informationen zur Verwendung von VRF

Alle Konten, die eine IBM Cloud Direct Link-Lösung nutzen, müssen auf eine VRF-Instanz migrieren. Durch die Verwendung von VRF machen Kunden die verfügbaren Routen in den eigens definierten Netzen zugänglich. Beachten Sie, dass es im Rahmen dieser Konfiguration nicht möglich ist, selbstdefinierte IP-Adressen für das {{site.data.keyword.BluSoftlayer_notm}}-Netz zu verwenden.

Die Migration auf eine VRF-Instanz wird während der Installation durchgeführt. Dazu wird ein kurzes Ausfallfenster (bis zu 30 Minuten bei großen Konten mit mehreren VLANs/Standorten) benötigt. Während dieses Zeitfensters gehen während der Verschiebung in die VRF-Instanz die Verbindungen zwischen den Back-End-VLANs verloren. Die VRF-Migration wird mit dem Entwickler geplant, der für die Implementierung verantwortlich ist.

Beachten Sie, dass bei der Verwendung von VRF die Option für das VLAN-Spanning nicht verwendet werden kann, einschließlich aller VLAN-Spanning-Funktionen zwischen Konten, da alle VLANs miteinander kommunizieren können, es sei denn, für die Verwaltung des Datenverkehrs wird eine Gateway-Appliance eingeführt. Mit VRF können zudem VPN-Services von {{site.data.keyword.BluSoftlayer_notm}} nur eingeschränkt genutzt werden, da die Funktion nicht mit den SSL-, PPTP- und IPSec VPN-Services von {{site.data.keyword.BluSoftlayer_notm}} kompatibel ist.   

Eine Alternative ist die Verwendung des IBM Cloud Direct Link-Angebots selbst zur Verwaltung Ihrer Server oder die Ausführung einer eigenen VPN-Lösung (z. B. Vyatta), die mit unterschiedlichen VPN-Typen konfiguriert werden kann. Nach der Migration auf eine VRF-Instanz kann SSL VPN für gewöhnlich verwendet werden, wenn eine VPN-Verbindung zu dem Rechenzentrumsstandort hergestellt wird, an dem eine Compute-VM ausgeführt wird. Ein globaler Zugriff ist hierbei allerdings nicht zulässig.

## BYOIP und NAT mit Direct Link verwenden
IBM Cloud Direct Link bietet BYOIP nicht für das private Netz. Ausgenommen sind einige besondere Umstände, die im Abschnitt zur [individuellen privaten Adressierung](#custom-private-addressing) aufgeführt sind. Datenverkehr mit einer Ziel-IP-Adresse, die nicht durch {{site.data.keyword.BluSoftlayer_notm}} zugewiesen wurde, wird daher gelöscht. Kunden können jedoch den Datenverkehr zwischen dem fernen Netz und ihrem {{site.data.keyword.BluSoftlayer_notm}}-Netz mithilfe von GRE, IPSec (Internet Protocol Security) oder VXLAN einkapseln.  

Am häufigsten wird die BYOIP-Umgebung im Rahmen eines Netzgateways (Vyatta) oder einer VMWare-NSX-Bereitstellung implementiert. Mit dieser Konfiguration können Kunden {{site.data.keyword.BluSoftlayer_notm}}-seitig und für die Rückleitung über den Tunnel zurück zum fernen Netz einen beliebigen IP-Bereich verwenden. Beachten Sie, dass diese Konfiguration unabhängig von {{site.data.keyword.BluSoftlayer_notm}} vom Kunden verwaltet und unterstützt werden muss. Außerdem kann es im Rahmen dieser Konfiguration zu einer Unterbrechung der Verbindung zum {{site.data.keyword.BluSoftlayer_notm}}-Servicenetz kommen, wenn der Kunde einen 10.x.x.x-Block zuweist, der von {{site.data.keyword.BluSoftlayer_notm}} für Services verwendet wird. 

Diese Lösung erfordert auch, dass jedem Host, der Konnektivität zum {{site.data.keyword.BluSoftlayer_notm}}-Servicenetz und zum fernen Netz benötigt, 2 IP-Adressen zugewiesen sind: Eine muss über den IBM 10.x.x.x-Block und eine über den Block des fernen Netzes zugewiesen sein. Statische Routen müssen auf dem Host eingerichtet werden, um sicherzustellen, dass der Datenverkehr entsprechend weitergeleitet wird. Sie können einen IP-Bereich nicht direkt für die {{site.data.keyword.BluSoftlayer_notm}}-Hosts (BYOIP) zuweisen und diesen inhärent im {{site.data.keyword.BluSoftlayer_notm}} weiterleiten. Die einzige Möglichkeit, dies zu implementieren, wurde bereits an anderer Stelle erläutert, wird jedoch nicht von {{site.data.keyword.BluSoftlayer_notm}} unterstützt.

Alternativ weisen Kunden häufig einen fernen Netzblock für die Verwendung in einer NAT-Tabelle zu, die auf ihrem fernen Edge-Router konfiguriert ist. Mit dieser Konfiguration können Kunden die an beiden Netzen erforderlichen Änderungen beschränken, während Datenverkehr weiterhin in einen Netzadressraum verschoben wird, der mit beiden Netzen kompatibel ist.

## Informationen zur individuellen privaten Adressierung

Es kann vorkommen, dass ein Kunde beim Onboarding bei IBM Cloud Direct Link nicht in der Lage ist, Konflikte von IP-Adressen zwischen dem lokalen und dem privaten {{site.data.keyword.BluSoftlayer_notm}}-Netz anhand der zuvor beschriebenen Methoden zu lösen. Falls eine solche Situation auftritt, kann ein {{site.data.keyword.BluSoftlayer_notm}}-Entwickler oder -Vertriebsbeauftragter empfehlen, dass Sie die _individuelle private Adressierung_ (CPA, Custom Private Adressing) verwenden. Die individuelle private Adressierung ist kostenfrei; diese Funktion unterliegt jedoch speziellen Anforderungen und Einschränkungen, die Sie unbedingt kennen sollten, bevor Sie sie verwenden. Die entsprechenden Details finden Sie in der Dokumentation, die Ihnen von dem IBM Cloud-Ansprechpartner bereitgestellt wird, der Ihnen diese Funktion empfiehlt. 

Die _wichtigste Anforderung_ ist, dass die individuelle private Adressierung nur für ein neues, leeres {{site.data.keyword.BluSoftlayer_notm}}-Konto und eine neue Direct Link-Verbindung aktiviert werden kann. Es ist nicht möglich, vorhandene Ressourcen in/auf die individuelle private Adressierung zu konvertieren oder zu migrieren.

Mit der individuellen privaten Adressierung können Sie {{site.data.keyword.BluSoftlayer_notm}}-Server in einem gültigen privaten IPv4-Adressbereich Ihrer Wahl (10.x.x.x, 192.168.x.x oder 172.16.x.x) hosten. Die Funktion stellt eine Untergruppe allgemeiner IBM Cloud-Services in einem speziellen, intern gerouteten Adressbereich (161.26.x.x) zur Verfügung, der private IP-Adressen für die Verwendung durch den Kunden frei lässt. Während Sie im Rahmen der individuellen privaten Adressierung bis zu fünf private IP-Bereiche (auch als _CPA-Netze_ bezeichnet) definieren können, stellt Direct Link die Verbindung mit nur einem CPA-Netz her. Wenn im Konto weitere CPA-Netze vorhanden sind, sind diese nicht über Direct Link zugänglich.

Die individuelle private Adressierung nutzt VRF und BGP. Der Entwickler, der für die Implementierung verantwortlich ist, liefert Ihnen die nötigen Details zu dieser Funktion.
