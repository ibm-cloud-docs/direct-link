---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: overview, connectivity, private network, site-to-site, Exchange, Connect, Dedicated, Hosting, OSI, Layer-3, partners, NNI, latency, backbone

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Visión general de la oferta Direct Link
{: #overview-of-direct-link-offerings}

Las ofertas de {{site.data.keyword.cloud}} Direct Link proporcionan conectividad desde un origen externo a una red privada de IBM Cloud del cliente. Direct Link puede considerarse como una alternativa a una solución VPN de sitio a sitio tradicional, diseñado para clientes que necesitan una conectividad más coherente y de mayor rendimiento entre una red remota y sus entornos de IBM Cloud. Hay disponibles cuatro tipos de conexiones:
 
 * **IBM Cloud Direct Link Exchange** permite a los clientes utilizar un proveedor de Exchange para ofrecer conectividad a su IBM Cloud. Un proveedor de Exchange es un proveedor de centro de datos o de coubicación que ya está conectado a la red de {{site.data.keyword.cloud_notm}}, mediante enlaces de varios arrendatarios de alta capacidad (también conocidos como _interfaz de red a red_ o NNI). Los clientes pueden comprar normalmente un circuito virtual en este proveedor, proporcionando conectividad a un coste reducido, porque la conectividad física de {{site.data.keyword.cloud_notm}} al proveedor de Exchange ya está en marcha, compartida entre otros clientes.
 
 * **IBM Cloud Direct Link Connect** permite a los proveedores utilizar una conexión mediante nuestros socios de transporte que poseen y operan una red basada en la instalación. Un proveedor de Connect es un proveedor de servicios de red (NSP) que ya está conectado a la red de {{site.data.keyword.cloud_notm}}, mediante enlaces de varios arrendatarios de alta capacidad (también conocidos como _interfaz de red a red_ o NNI). Los clientes pueden comprar normalmente un circuito virtual en este proveedor, proporcionando conectividad a un coste reducido, porque la conectividad física de {{site.data.keyword.cloud_notm}} al proveedor de Connect ya está en marcha, compartida entre otros clientes.
 
 * **IBM Cloud Direct Link Dedicated** permite a los clientes terminar una conexión cruzada de un solo arrendatario basada en fibra en la red de {{site.data.keyword.cloud_notm}}. Pueden utilizar esta oferta los clientes con instalaciones de coubicación adyacentes a los PoP y centros de datos de IBM Cloud, así como los proveedores de servicios de red que distribuyen circuitos a los clientes localmente o a otros centros de datos.
 
 * **IBM Cloud Direct Link Dedicated Hosting** proporciona conectividad similar a {{site.data.keyword.cloud_notm}} Direct Link Dedicated, pero el punto de conexión es adyacente a un centro de datos de {{site.data.keyword.cloud_notm}}, que mejora la latencia para casos de uso de mayor rendimiento. {{site.data.keyword.cloud_notm}} ofrece una variedad de servicios de coubicación personalizables con esta solución.
  
El servicio {{site.data.keyword.cloud_notm}} Direct Link es un servicio direccionado de 3 capas de OSI. Ofrece una conexión directa a la red troncal privada de {{site.data.keyword.cloud_notm}}, con baja latencia y velocidades de hasta 10 Gbps.
Para una mayor flexibilidad para crear esta conectividad de 3 capas, {{site.data.keyword.cloud_notm}} Direct Link permite a los clientes utilizar:
 * IP dual para los hosts remotos
 * NAT
 * Tunelado para BYOIP
 
 Para ver descripciones detalladas de cada una de las ofertas, consulte [Acerca de IBM Cloud Direct Link](/docs/infrastructure/direct-link?topic=direct-link-about-ibm-cloud-direct-link).
