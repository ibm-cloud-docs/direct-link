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

# Comparación entre conexiones de capa 2 y de capa 3 para Direct Link
{: #comparing-layer-2-layer-3}

{{site.data.keyword.cloud}} Direct Link acepta interconexiones de socios OSI de capa 2 y de capa 3 procedentes de proveedores de servicios de red (NSP). Algunos proveedores de servicios de red ofrecen servicios para ambas capas en diferentes redes; sin embargo, algunos proveedores pueden haber optado por **no** interconectar todas sus redes en {{site.data.keyword.cloud_notm}}. 

Cuando planifique el despliegue de {{site.data.keyword.cloud_notm}} Direct Link, tenga en cuenta las características asociadas a las conexiones de capa 2 y de capa 3 para poder crear el despliegue que mejor se adapte a sus necesidades.

## Consideraciones sobre las conexiones de capa 2
{: #layer-2-networks}

Para cada circuito virtual basado en VLAN, que creará con una interconexión de socio de capa 2, debe configurar y establecer una sesión BGP entre los direccionadores locales y XRC de IBM Cloud. IBM Cloud le proporcionará una asignación de IPv4 `/31` para establecer una sesión de BGP con el direccionador.

* Las redes de capa 2 ofrecen opciones para conexiones simples entre uno y uno entre las empresas e {{site.data.keyword.cloud_notm}}. 
* Los servicios de capa 2 se basan en las VLAN en lugar de en las direcciones IP. 
* Los servicios de capa 2 pueden ofrecer un menor coste y una menor latencia, y pueden consumir menos sobrecarga que los servicios de capa 3. 
* Las redes de capa 2 no imponen restricciones en cuanto a las características de capa 3 que puede habilitar una empresa.

## Consideraciones sobre las conexiones de capa 3
{: #layer-3-networks}

Para las conexiones de capa 3, para cada circuito virtual el proveedor de servicios establece una sesión BGP entre los XRC de IBM Cloud y los direccionadores de extremo del proveedor. No tendrá que configurar BGP con IBM Cloud para el direccionador local, ya que el proveedor de servicios gestionará la configuración de BGP en IBM Cloud.

* Las redes VPN o AVPN de IP de capa 3 permiten la conectividad entre "cualquiera y cualquiera". 
* Las redes de capa 3 requieren que el proveedor de servicios de red mantenga una sesión BGP entre la empresa e {{site.data.keyword.cloud_notm}}. 
* Algunos proveedores de servicios de red pueden restringir ciertas funcionalidades a través de su red cuando se utilizan conexiones de capa 3, como por ejemplo el prefijo ASN, el túnel GRE, etc. Asegúrese de consultar con su proveedor acerca de las posibles restricciones.

## Tabla de interconexiones de socios
{: #partner-interconnection-table}

En la tabla siguiente se resume el tipo de conexiones que proporciona cada socio de {{site.data.keyword.cloud_notm}}. 

| Socios | Tipo de interconexión |  
|-------|-------|
| AT&T NetBond® for Cloud | Capa 3 |
| AT&T Cloud Gateway (antes denominado RedFringe)| Capa 3 |
| Bell Canada | Capa 3 | 
| British Telecom | Capa 3  | 
| CenturyLink IP VPN | Capa 3 | 
| CenturyLink Dynamic Connections | Capa 2 | 
| Chief Telecomm | Capa 2 |
| Colt | Capa 2  | 
| Console Connect by PCCW | Capa 2 |
| Digital Realty Service Exchange | Capa 2 | 
| Epsilon | Capa 2 | 
| IBM BlueFringe | Capa 3 | 
| Intercloud | Capa 3 |
| Megaport | Capa 2 |
| MWS GNPP | Capa 3 |
| Neutrona | Capa 2 |
| NTT | Capa 3 |
| PacketFabric | Capa 2  |
| Softbank | Capa 3 |
| SES Networks | Capa 2  |
| Tata IZO™ Private Connect  | Capa 3 | 
| Telia | Capa 3 |
| Telstra | Capa 3 |
| Tokai | Capa 2 | 
| Verizon SCI| Capa 3 |
| Zayo Cloud Link | Capa 2 |
