---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-29"

keywords: hybrid, solutions, features, benefits, port speed, cross-connect, use cases, latency, routing, options, colocation

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Acerca de IBM Cloud Direct Link
{: #about-ibm-cloud-direct-link}

Esta sección contiene más detalles sobre las principales características y ventajas de cada una de las cuatro ofertas de las soluciones {{site.data.keyword.cloud}} Direct Link.
  * [**IBM Cloud Direct Link Exchange**](#direct-link-exchange-solution)
  * [**IBM Cloud Direct Link Connect**](#direct-link-connect-solution)
  * [**IBM Cloud Direct Link Dedicated**](#direct-link-dedicated-solution)
  * [**IBM Cloud Direct Link Dedicated Hosting**](#direct-link-dedicated-hosting-solution)

## La solución IBM Cloud Direct Link Exchange
{: #direct-link-exchange-solution}

La solución IBM Cloud Direct Link Exchange permite a los clientes utilizar un proveedor de Cloud Exchange para ofrecer conectividad a ubicaciones de {{site.data.keyword.cloud_notm}}. Esta oferta normalmente proporciona conectividad a un coste reducido, porque la conectividad física de {{site.data.keyword.cloud_notm}} al Cloud Exchange Provider ya está en vigor, compartida entre otros clientes.

**Casos de uso común:** _Mejor para cargas de trabajo híbridas, cargas de trabajo de proveedor, transferencias de datos grandes o frecuentes con altos anchos de banda de salida, cargas de trabajo privadas y administración de entorno.  Esta opción normalmente se selecciona cuando la ubicación de PoP deseada ya tiene el proveedor de IBM Cloud Direct Link Exchange deseado._

![Figura 1](/images/Direct-Link-Exchange.png)

 * **Ubicación de terminación:** Punto de presencia (PoP) de {{site.data.keyword.cloud_notm}}.

 * **Tiempo de despliegue típico:** Para los proveedores de Equinix, el tiempo de despliegue típico se indicará en horas. Para otros proveedores, entre 5 y 10 días una vez que el circuito alcance el intercambio. El tiempo de despliegue puede estar posiblemente entre los 30 y los 60 días en total, dependiendo de su ubicación y de los requisitos cuando se solicita un circuito de NSP o de un operador.

 * **Detalles de conexión:** Las conexiones físicas para la interconexión segura de Cloud Exchange se mantienen entre {{site.data.keyword.cloud_notm}} y el proveedor de Cloud Exchange. Los clientes solicitan un "Circuito virtual" del Cloud Exchange Provider, que establece conectividad lógica a {{site.data.keyword.cloud_notm}}, una vez que el cliente se interconecte al Cloud Exchange Provider.

 * **Opciones de velocidad de puerto:** Seleccione 50 Mbps, 100 Mbps, 200 Mbps, 500 Mbps, 1 Gbps, 2 Gbps o 5 Gbps.

 * **Latencia aproximada:** La latencia es aproximadamente 1,5 ms dentro del área local (centros de datos con el mismo prefijo de tres letras, como por ejemplo DAL, AMS, MEL, etc). Consulte http://lg.softlayer.com/ para ver las mediciones de latencia de ubicaciones PoP-to-PoP (P2P) en directo.

 * **Servicios de coubicación de IBM:** Ninguno.

 * **Redundancia:** {{site.data.keyword.cloud_notm}} proporciona conexiones a dos (2) direccionadores de conexión (XCR) como parte del producto. Para establecer conectividad redundante, los clientes deben configurar BGP en cada conexión de Direct Link, tal y como lo consideren adecuado. Los ejemplos incluyen opciones como estas: _preferible el MED más bajo_, _preferible la preferencia local más alta_ o _preferible las vías de acceso AS más cortas_.

 * **Opciones de direccionamiento local/global:** La opción Direccionamiento local es la opción de direccionamiento predeterminada. Proporciona acceso a los centros de datos dentro del mismo mercado que Direct Link PoP (indicado, por ejemplo, como DAL, AMS o MEL). La opción de direccionamiento global es necesaria como un complemento para conectar sus recursos de IBM Cloud con otros recursos de IBM Cloud en centros de datos fuera del mercado local. Proporciona un modo de compartir cargas de trabajo entre los recursos de IBM Cloud (por ejemplo, Dallas a Ashburn, o Dallas a Frankfurt).
 
## La solución IBM Cloud Direct Link Connect
{: #direct-link-connect-solution}

**Casos de uso comunes** _La solución IBM Cloud Direct Link Connect permite a los clientes aprovechar un proveedor de servicios de red (NSP) para proporcionar conectividad con las ubicaciones de {{site.data.keyword.cloud_notm}}. Esta oferta normalmente proporciona conectividad a un coste reducido, porque la conectividad física de {{site.data.keyword.cloud_notm}} con el proveedor de servicios de red ya está establecida y se comparte con otros clientes._

![Figura 2](/images/Direct-Link-Connect.png)

* **Ubicación de terminación:** Punto de presencia (PoP) de {{site.data.keyword.cloud_notm}}.

* **Tiempo de despliegue típico:** De 5 a 10 días, una vez que el circuito alcance el intercambio. El tiempo de despliegue puede estar posiblemente entre los 30 y los 60 días en total, dependiendo de su ubicación y de los requisitos cuando se solicita un circuito de NSP o de un operador.

* **Detalles de conexión:** Las conexiones físicas para la interconexión segura de Direct Link Connect se mantienen entre {{site.data.keyword.cloud_notm}} y el proveedor de Connect. Los clientes solicitan un "Circuito virtual" del proveedor de Cloud Connect, que establece conectividad lógica a {{site.data.keyword.cloud_notm}}, una vez que el cliente se interconecte al proveedor de Cloud Connect.

* **Opciones de velocidad de puerto:** Seleccione 50 Mbps, 100 Mbps, 200 Mbps, 500 Mbps, 1 Gbps, 2 Gbps o 5 Gbps.

* **Latencia aproximada:** La latencia es aproximadamente 1,5 ms dentro del área local (centros de datos con el mismo prefijo de tres letras, como por ejemplo DAL, AMS, MEL, etc). Consulte http://lg.softlayer.com/ para ver las mediciones de latencia de ubicaciones PoP-to-PoP (P2P) en directo.

* **Servicios de coubicación de IBM:** Ninguno.

* **Redundancia:** {{site.data.keyword.cloud_notm}} proporciona conexiones a dos (2) direccionadores de conexión (XCR) como parte del producto. Para establecer conectividad redundante, los clientes deben configurar BGP en cada conexión de Direct Link, tal y como lo consideren adecuado. Los ejemplos incluyen opciones como estas: _preferible el MED más bajo_, _preferible la preferencia local más alta_ o _preferible las vías de acceso AS más cortas_.

* **Opciones de direccionamiento local/global:** La opción Direccionamiento local es la opción de direccionamiento predeterminada. Proporciona acceso a los centros de datos dentro del mismo mercado que Direct Link PoP (indicado, por ejemplo, como DAL, AMS o MEL). La opción de direccionamiento global es necesaria como un complemento para conectar sus recursos de IBM Cloud con otros recursos de IBM Cloud en centros de datos fuera del mercado local. Se utiliza para compartir cargas de trabajo entre los recursos de IBM Cloud (por ejemplo, Dallas a Ashburn, o Dallas a Frankfurt).

## La solución IBM Cloud Direct Link Dedicated
{: #direct-link-dedicated-solution}

La solución IBM Cloud Direct Link Dedicated permite a los clientes terminar una conexión cruzada de un solo arrendatario basada en fibra en su propia conexión de red privada de {{site.data.keyword.cloud_notm}}. Pueden utilizar esta oferta los clientes con instalaciones de coubicación adyacentes a los PoP y centros de datos de IBM Cloud, así como los proveedores de servicios de red que distribuyen circuitos a los clientes localmente o a otros centros de datos.

 **Casos de uso común:** _Mejor para trabajar con cargas de trabajo híbridas, cargas de trabajo de proveedores, transferencias de datos grandes o frecuentes, cargas de trabajo privadas y administración de entorno. Esta opción se selecciona normalmente: (1) cuando el PoP deseado no tiene el proveedor de servicios de red o de Exchange deseado, (2) para las cargas de trabajo de alto rendimiento que requieren un alto rendimiento, o (3) para los requisitos de conformidad que no se pueden satisfacer mediante el modelo de implementación de IBM Cloud Direct Link Exchange o de Connect._
 
 **Caso de uso 1: Instalación del cliente a IBM Cloud.**

![Figura 3](/images/Direct-link-Dedicated.png)

**Caso de uso 2: Coubicación del cliente a IBM Cloud.**

![Figura 3B](/images/dedicated-model-colo.png)

 * **Ubicación de terminación:** Punto de presencia (PoP) o Centro de datos (CD) de {{site.data.keyword.cloud_notm}}.

 * **Tiempo de despliegue típico:** De 10 a 15 días hábiles una vez que el circuito nuevo alcance el POP. El tiempo de despliegue puede estar posiblemente entre los 30 y los 60 días en total, dependiendo de su ubicación y de los requisitos cuando se solicita un circuito de NSP o de un operador.

 * **Detalles de conexión:** {{site.data.keyword.cloud_notm}} proporciona una Carta de autorización (Letter of Authorization, LOA) que un cliente utiliza para solicitar Ethernet de fibra (sólo fibra de un único modo, ya sea de óptica 1Gig-LX o 10Gig-LR) que se ejecuta desde una caja de cliente o proveedor a un punto de terminación de {{site.data.keyword.cloud_notm}} CFA, que se conectará a la infraestructura de direccionador de conexión (XCR). El soporte debe ser una óptica de 1310 nm de longitud de onda.

 * **Opciones de velocidad de puerto:** Seleccione 1 Gbps, 2 Gbps, 5 Gbps o 10 Gbps.

 * **Latencia aproximada:** La latencia es aproximadamente de 1,5 ms dentro del área local (centros de datos con el mismo prefijo de tres letras, como por ejemplo DAL, AMS, MEL, etc).  Consulte http://lg.softlayer.com/ para ver las mediciones de latencia de ubicaciones PoP-to-PoP (P2P) en directo.

 * **Servicios de coubicación de IBM:** Ninguno.

 * **Redundancia:** {{site.data.keyword.cloud_notm}} proporciona conexiones a dos (2) direccionadores de conexión (XCR) como parte del producto. Para establecer conectividad redundante, los clientes deben configurar BGP en cada conexión de Direct Link, tal y como lo consideren adecuado. Los ejemplos incluyen opciones como estas: _preferible el MED más bajo_, _preferible la preferencia local más alta_ o _preferible las vías de acceso AS más cortas_.

 * **Opciones de direccionamiento local/global:** La opción Direccionamiento local es la opción de direccionamiento predeterminada. Proporciona acceso a los centros de datos dentro del mismo mercado que Direct Link PoP (indicado, por ejemplo, como DAL, AMS o MEL). La opción de direccionamiento global es necesaria como un complemento para conectar sus recursos de IBM Cloud con otros recursos de IBM Cloud en centros de datos fuera del mercado local. Proporciona un modo de compartir cargas de trabajo entre los recursos de IBM Cloud (por ejemplo, Dallas a Ashburn, o Dallas a Frankfurt).

## La solución IBM Cloud Direct Link Dedicated Hosting
{: #direct-link-dedicated-hosting-solution}

La solución IBM Cloud Direct Link Dedicated Hosting proporciona conectividad similar a IBM Cloud Direct Link Dedicated, pero el punto de conexión es adyacente a un centro de datos de {{site.data.keyword.cloud_notm}}, que mejora la latencia para casos de uso de mayor rendimiento. IBM Cloud ofrece una variedad de servicios de coubicación personalizables con esta solución, con un sistema sencillo de cálculo de precios.

**Casos de uso común:** _Mejor para trabajar con tecnologías de cálculo no estándares, para los requisitos de almacenamiento dedicados o para aprovechar las inversiones de TI existentes._

![Figura 4](/images/Direct-Link-Dedicated-Hosting.png)

* **Ubicación de terminación:** Centro de datos (CD) de {{site.data.keyword.cloud_notm}}.

 * **Tiempo de despliegue típico:** De 30 a 60 días una vez que finalicen todos los requisitos y que se hayan ejecutado los contratos.

 * **Detalles de conexión:** {{site.data.keyword.cloud_notm}} proporciona conexiones de fibra de 1 G o 10 G desde la infraestructura de direccionador de conexión (XCR) de {{site.data.keyword.cloud_notm}} al entorno de colocación del cliente como parte del despliegue.  Si los servicios de colocación no se solicitan (si ya están conectados los entornos existentes), {{site.data.keyword.cloud_notm}} proporciona una Carta de autorización (Letter of Authorization, LOA) que un cliente utiliza para solicitar Ethernet de fibra (sólo fibra de un único modo, ya sea de óptica 1Gig-LX o 10Gig-LR) que se ejecuta desde una caja de cliente a un punto de terminación de {{site.data.keyword.cloud_notm}} CFA, que se conectará a la infraestructura de direccionador de conexión (XCR). El soporte debe ser una óptica de 1310 nm de longitud de onda.

 * **Opciones de velocidad de puerto:** Seleccione 1 Gbps, 2 Gbps, 5 Gbps o 10 Gbps.

 * **Latencia aproximada:** La latencia es aproximadamente de 0,5 ms dentro del centro de datos local.

 * **Servicios de coubicación de IBM:** Sí.

 * **Redundancia:** {{site.data.keyword.cloud_notm}} proporciona conexiones a dos (2) direccionadores de conexión (XCR) como parte del producto. Para establecer conectividad redundante, los clientes deben configurar BGP en cada conexión de Direct Link, tal y como lo consideren adecuado. Los ejemplos incluyen opciones como estas: _preferible el MED más bajo_, _preferible la preferencia local más alta_ o _preferible las vías de acceso AS más cortas_.

 * **Opciones de direccionamiento local/global:** La opción Direccionamiento local es la opción de direccionamiento predeterminada. Proporciona acceso a los centros de datos dentro del mismo mercado que Direct Link PoP (indicado, por ejemplo, como DAL, AMS o MEL). La opción de direccionamiento global es necesaria como un complemento para conectar sus recursos de IBM Cloud con otros recursos de IBM Cloud en centros de datos fuera del mercado local. Se utiliza para compartir cargas de trabajo entre los recursos de IBM Cloud (por ejemplo, Dallas a Ashburn, o Dallas a Frankfurt).
