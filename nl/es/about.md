---

copyright:
  years: 2017, 2018
lastupdated: "2018-08-09"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Acerca de IBM Cloud Direct Link

Esta sección contiene más detalles sobre las principales características y ventajas de cada una de las cuatro ofertas de las soluciones IBM Cloud Direct Link.
  * [**IBM Cloud Direct Link Exchange**](#the-ibm-cloud-direct-link-exchange-solution)
  * [**IBM Cloud Direct Link Connect**](#the-ibm-cloud-direct-link-connect-solution)
  * [**IBM Cloud Direct Link Dedicated**](#the-ibm-cloud-direct-link-dedicated-solution)
  * [**IBM Cloud Direct Link Dedicated Hosting**](#the-ibm-cloud-direct-link-dedicated-hosting-solution)

## La solución IBM Cloud Direct Link Exchange

La solución IBM Cloud Direct Link Exchange permite a los clientes aprovechar un proveedor de Cloud Exchange para ofrecer conectividad a ubicaciones de {{site.data.keyword.BluSoftlayer_notm}}. Esta oferta normalmente proporciona conectividad a un coste reducido, porque la conectividad física de {{site.data.keyword.BluSoftlayer_notm}} al Cloud Exchange Provider ya está en vigor, compartida entre otros clientes.

**Casos de uso común:** _Mejor para cargas de trabajo híbridas, cargas de trabajo de proveedor, transferencias de datos grandes o frecuentes con altos anchos de banda de salida, cargas de trabajo privadas y administración de entorno.  Esta opción normalmente se selecciona cuando la ubicación de PoP deseada ya tiene el proveedor de IBM Cloud Direct Link Exchange deseado._

![Figura 1](/images/Direct-Link-Exchange.png)

 * **Ubicación de terminación:** PoP (point of presence, punto de presencia) de {{site.data.keyword.BluSoftlayer_notm}}.

 * **Tiempo de despliegue típico:** Para los proveedores de Equinix, el tiempo de despliegue típico se indicará en horas. Para otros proveedores, entre 5 y 10 días una vez que el circuito alcance el intercambio. El tiempo de despliegue puede estar posiblemente entre los 30 y los 60 días en total, dependiendo de su ubicación y de los requisitos cuando se solicita un circuito de NSP o de un operador.

 * **Detalles de conexión:** Las conexiones físicas para la interconexión segura de Cloud Exchange se mantienen entre {{site.data.keyword.BluSoftlayer_notm}} y el proveedor de Cloud Exchange. Los clientes solicitan un "Circuito virtual" del Cloud Exchange Provider, que establece conectividad lógica a {{site.data.keyword.BluSoftlayer_notm}}, una vez que se interconecten al Cloud Exchange Provider.

 * **Opciones de velocidad de puerto:** Seleccione 50 Mbps, 100 Mbps, 200 Mbps, 500 Mbps o 1 Gbps.

 * **Latencia aproximada:** La latencia es aproximadamente 1,5 ms dentro del área local (centros de datos con el mismo prefijo de tres letras, como por ejemplo DAL, AMS, MEL, etc). Consulte http://lg.softlayer.com/ para ver las mediciones de latencia de ubicaciones PoP-to-PoP (P2P) en directo.

 * **Servicios de colocación:** Ninguno.

 * **Redundancia:** Para establecer la redundancia de IBM Cloud Direct Link Exchange, se necesita conectividad en más de 2 ubicaciones, o la selección de una ubicación con XCR secundario disponible que pueda aprovechar el proveedor de Cloud Exchange.

 * ** Opciones de direccionamiento local/global:** La opción Direccionamiento local es la opción de direccionamiento predeterminada. Proporciona acceso a los centros de datos dentro del mismo mercado que Direct Link PoP (indicado, por ejemplo, como DAL, AMS o MEL). La opción de direccionamiento global es necesaria como un complemento para conectar sus recursos de IBM Cloud en el mercado con otros recursos de IBM Cloud en centros de datos fuera del mercado local. Se utiliza para compartir cargas de trabajo entre los recursos de IBM Cloud (por ejemplo, Dallas a Ashburn, o Dallas a Frankfurt).
 
## La solución IBM Cloud Direct Link Connect

**Casos de uso comunes** Similar a la solución de Direct Link Exchange. Ofrece más opciones de velocidad. La solución Direct Link Cloud Connect proporciona un punto de partida de bajo coste para los clientes de red de IBM Cloud.

![Figura 2](/images/Direct-Link-Connect.png)

* **Ubicación de terminación:** PoP (point of presence, punto de presencia) de {{site.data.keyword.BluSoftlayer_notm}}.

* **Tiempo de despliegue típico:** de 5 a 10 días una vez que el circuito alcance el intercambio. El tiempo de despliegue puede estar posiblemente entre los 30 y los 60 días en total, dependiendo de su ubicación y de los requisitos cuando se solicita un circuito de NSP o de un operador.

* **Detalles de conexión:** Las conexiones físicas para la interconexión segura de Direct Link Connect se mantienen entre {{site.data.keyword.BluSoftlayer_notm}} y el proveedor de Connect. Los clientes solicitan un "Circuito virtual" del Cloud Connect Provider, que establece conectividad lógica a {{site.data.keyword.BluSoftlayer_notm}}, una vez que se interconecten al Cloud Connect Provider.

* **Opciones de velocidad de puerto:** Seleccione 50 Mbps, 100 Mbps, 200 Mbps, 500 Mbps, 1 Gbps, 2 Gbps o 5 Gbps.

* **Latencia aproximada:** La latencia es aproximadamente 1,5 ms dentro del área local (centros de datos con el mismo prefijo de tres letras, como por ejemplo DAL, AMS, MEL, etc). Consulte http://lg.softlayer.com/ para ver las mediciones de latencia de ubicaciones PoP-to-PoP (P2P) en directo.

* **Servicios de colocación:** Ninguno.

* **Redundancia:** Para establecer la redundancia para IBM Cloud Direct Link Connect, se necesita la conectividad en más de 2 ubicaciones, o la selección de una ubicación con XCR secundario disponible que pueda aprovechar el proveedor de IBM Cloud Connect.

* **Opciones de direccionamiento local/global:** La opción Direccionamiento local es la opción de direccionamiento predeterminada. Proporciona acceso a los centros de datos dentro del mismo mercado que Direct Link PoP (indicado, por ejemplo, como DAL, AMS o MEL). La opción de direccionamiento global es necesaria como un complemento para conectar sus recursos de IBM Cloud en el mercado con otros recursos de IBM Cloud en centros de datos fuera del mercado local. Se utiliza para compartir cargas de trabajo entre los recursos de IBM Cloud (por ejemplo, Dallas a Ashburn, o Dallas a Frankfurt).

## La solución IBM Cloud Direct Link Dedicated

La solución IBM Cloud Direct Link Dedicated permite a los clientes terminar una conexión dedicada, individual y de fibra en su propia red privada de {{site.data.keyword.BluSoftlayer_notm}}.

 **Casos de uso común:** _Mejor para trabajar con cargas de trabajo híbridas, cargas de trabajo de proveedores, transferencias de datos grandes o frecuentes, cargas de trabajo privadas y administración de entorno.  Esta opción está normalmente seleccionada: (1) cuando el PoP deseado no tiene el proveedor IBM Cloud Direct Link Exchange deseado, (2) para cargas de trabajo de alto rendimiento que requieren un alto rendimiento, o (3) para requisitos de conformidad que no puede satisfacer el modelo de implementación de IBM Cloud Direct Link Exchange._

![Figura 3](/images/Direct-link-Dedicated.png)

 * **Ubicación de terminación:** PoP (point of presence, punto de presencia) de {{site.data.keyword.BluSoftlayer_notm}}.

 * **Tiempo de despliegue típico:** De 10 a 15 días hábiles una vez que el circuito nuevo alcance el POP. El tiempo de despliegue puede estar posiblemente entre los 30 y los 60 días en total, dependiendo de su ubicación y de los requisitos cuando se solicita un circuito de NSP o de un operador.

 * **Detalles de conexión:** {{site.data.keyword.BluSoftlayer_notm}} proporciona una Carta de autorización (Letter of Authorization, LOA) que un cliente utiliza para solicitar Ethernet de fibra (sólo fibra de un único modo, ya sea de óptica 1Gig-LX o 10Gig-LR) que se ejecuta desde una caja de cliente o proveedor a un punto de terminación de {{site.data.keyword.BluSoftlayer_notm}} CFA, que se conectará a la infraestructura de direccionador de conexión (XCR). El soporte debe ser una óptica de 1310 nm de longitud de onda.

 * **Opciones de velocidad de puerto:** Seleccione 1 Gbps, 2 Gbps, 5 Gbps o 10 Gbps.

 * **Latencia aproximada:** La latencia es aproximadamente de 1,5 ms dentro del área local (centros de datos con el mismo prefijo de tres letras, como por ejemplo DAL, AMS, MEL, etc).  Consulte http://lg.softlayer.com/ para ver las mediciones de latencia de ubicaciones PoP-to-PoP (P2P) en directo.

 * **Servicios de colocación:** Ninguno.

 * **Redundancia:** Para establecer la redundancia, se requiere conectividad de IBM Cloud Direct Link en más de 2 ubicaciones, o la selección de una ubicación con un XCR secundario disponible y una segunda solicitud de conexión de IBM Cloud Direct Link.

 * **Opciones de direccionamiento local/global:** La opción Direccionamiento local es la opción de direccionamiento predeterminada. Proporciona acceso a los centros de datos dentro del mismo mercado que Direct Link PoP (indicado, por ejemplo, como DAL, AMS o MEL). La opción de direccionamiento global es necesaria como un complemento para conectar sus recursos de IBM Cloud en el mercado con otros recursos de IBM Cloud en centros de datos fuera del mercado local. Se utiliza para compartir cargas de trabajo entre los recursos de IBM Cloud (por ejemplo, Dallas a Ashburn, o Dallas a Frankfurt).

## La solución IBM Cloud Direct Link Dedicated Hosting

La solución IBM Cloud Direct Link Dedicated Hosting proporciona conectividad similar a IBM Cloud Direct Link Dedicated, pero el punto de conexión es adyacente a un centro de datos de {{site.data.keyword.BluSoftlayer_notm}}, que mejora la latencia para casos de uso de mayor rendimiento. IBM Cloud ofrece una variedad de servicios de coubicación personalizables con esta solución, con un sistema sencillo de cálculo de precios.

**Casos de uso común:** _Mejor para trabajar con tecnologías de cálculo no estándares, para los requisitos de almacenamiento dedicados o para aprovechar las inversiones de TI existentes._

![Figura 4](/images/Direct-Link-Dedicated-Hosting.png)

* **Ubicación de terminación:** Centro de datos (DC) de {{site.data.keyword.BluSoftlayer_notm}}.

 * **Tiempo de despliegue típico:** De 30 a 60 días una vez que finalicen todos los requisitos y que se hayan ejecutado los contratos.

 * **Detalles de conexión:** {{site.data.keyword.BluSoftlayer_notm}} proporciona conexiones de fibra de 1 G o 10 G desde la infraestructura de direccionador de conexión (XCR) de {{site.data.keyword.BluSoftlayer_notm}} al entorno de colocación del cliente como parte del despliegue.  Si los servicios de colocación no se solicitan (si ya están conectados los entornos existentes), {{site.data.keyword.BluSoftlayer_notm}} proporciona una Carta de autorización (Letter of Authorization, LOA) que un cliente utiliza para solicitar Ethernet de fibra (sólo fibra de un único modo, ya sea de óptica 1Gig-LX o 10Gig-LR) que se ejecuta desde una caja de cliente a un punto de terminación de {{site.data.keyword.BluSoftlayer_notm}} CFA, que se conectará a la infraestructura de direccionador de conexión (XCR). El soporte debe ser una óptica de 1310 nm de longitud de onda.

 * **Opciones de velocidad de puerto:** Seleccione 1 Gbps, 2 Gbps, 5 Gbps o 10 Gbps.

 * **Latencia aproximada:** La latencia es aproximadamente de 0,5 ms dentro del centro de datos local.

 * **Servicios de colocación:** Sí.

 * **Redundancia:** {{site.data.keyword.BluSoftlayer_notm}} proporciona conexiones a dos direccionadores de conexión (XCR) como parte del producto. Para establecer conectividad redundante, los clientes deben configurar BGP en cada conexión de Direct Link, tal y como lo consideren adecuado para lograr redundancia. Los ejemplos incluyen opciones como estas: _preferible el MED más bajo_, _preferible la preferencia local más alta_ o _preferible las vías de acceso AS más cortas_.

 * **Opciones de direccionamiento local/global:** La opción Direccionamiento local es la opción de direccionamiento predeterminada. Proporciona acceso a los centros de datos dentro del mismo mercado que Direct Link PoP (indicado, por ejemplo, como DAL, AMS o MEL). La opción de direccionamiento global es necesaria como un complemento para conectar sus recursos de IBM Cloud en el mercado con otros recursos de IBM Cloud en centros de datos fuera del mercado local. Se utiliza para compartir cargas de trabajo entre los recursos de IBM Cloud (por ejemplo, Dallas a Ashburn, o Dallas a Frankfurt).
