---

copyright:
 years: 2017, 2018
lastupdated: "2018-04-05"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Preguntas más frecuentes

Esta sección contiene respuestas a algunas de las preguntas más frecuentes acerca de IBM Cloud Direct Link. 

## ¿Cómo funciona IBM Cloud Direct Link?
Para cada cliente de Direct Link, el equipo de IBM Cloud asigna una pequeña subred privada para construir una red punto a punto entre el direccionador de conexión (XCR) de {{site.data.keyword.BluSoftlayer_notm}} y el direccionador de extremo del cliente (CER). A continuación, {{site.data.keyword.BluSoftlayer_notm}} y el cliente configuran BGP para intercambiar rutas entre los entornos. Finalmente, {{site.data.keyword.BluSoftlayer_notm}} coloca el cliente en un VRF para permitir la implementación de rutas no exclusivas para el espacio de direcciones privado de la red remota del cliente.

## ¿Mide IBM Cloud el ancho de banda para los productos de Direct Link?
Sí. IBM Cloud mide todo el ancho de banda saliente en los productos de Direct Link. El ancho de banda de entrada es gratuito y no se mide.

## ¿Qué cargos adicionales de otras partes tendré con Direct Link?
Puede tener cargos adicionales del proveedor de intercambio o del proveedor de servicio de red. Consulte a su/s proveedor/es para obtener la información de pago.

## ¿Cómo puedo conseguir redundancia con IBM Cloud Direct Link?
Puede conseguir redundancia con Direct Link conectándose a más de un proveedor de IBM Cloud Direct Link Dedicated o Exchange de {{site.data.keyword.BluSoftlayer_notm}}. De forma alternativa, puede optimizar uno de los proveedores de IBM Cloud Direct Link que añade redundancia al servicio.

## ¿Cuál es la diferencia entre el direccionamiento "local" predeterminado y el complemento Global Routing?
Con nuestra oferta Direct Link estándar, puede enviar tráfico entre los centros de datos en su región seleccionada. Si necesita acceso a otros centros de datos fuera de la región especificada, debe solicitar el complemento Global Routing. Este modelo se basa en ACL (listas de control de acceso) que se ponen en marcha en el momento en el que solicite la conexión de Direct Link. 

## ¿Cómo se facturan los excesos de datos del ancho de banda saliente (egress) para el complemento Global Routing?
Los excesos de datos se facturan mensualmente cuando se supera la cuota de ancho de banda, pero sólo para ancho de banda de salida. El ancho de banda de entrada es gratuito y no se mide. El ancho de banda de salida se factura basándose en la tarifa mayor de las dos regiones que cruzan los datos.  Por ejemplo, si Direct Link está configurado en DAL03 y su tráfico de datos pasa por México, se le cobrará la tarifa de ancho de banda para México.

## ¿Por qué existe un paquete de complementos de Global Routing?
Hemos añadido el complemento de Global Routing para evitar que nuestros clientes experimenten costes de datos inesperados al atravesar fuera de la región de su centro de datos. Mantiene los costes más bajos para la mayoría de nuestros clientes, y ofrece la capacidad a los clientes con una presencia global de llegar a todas las regiones del mundo fácilmente. Normalmente, sin embargo, un cliente sólo requiere un paquete de ancho de banda local.

## ¿Qué son las opciones Local Routing y Global Routing?
Las opciones Local Routing y Global Routing las selecciona cada cliente al solicitar el servicio de Direct Link. Si los clientes necesitan direccionar su tráfico fuera del POP en el área dentro de la cual están solicitando Direct Link, deben añadir la opción Global Routing; de lo contrario, su tráfico se restringirá a los servicios proporcionados por el POP local.

Cada mes, todos los clientes que utilizan Circuitos 1G se les asignan 10 TB de tráfico de salida gratuito; a los clientes que utilizan circuitos de 10 G se les asignarán 50 TB. Los excesos de datos se basan en la tabla siguiente, con la mayor tasa de mercado imperante. Si selecciona Global Routing, no se le cobrará ningún tráfico de salida local, sólo para el tráfico que se origina o termina fuera del POP local.

|Datos del mercado 1|Datos del mercado 2|Datos del mercado 3|
|---|---|---|
|<ul><li>DAL</li><li>WDC</li><li>SEA</li><li>SJC</li><li>NYC*</li><li>CHI*</li><li>DEN*</li><li>MIA*</li><li>ATL*</li><li>LAX*</li><li>TOR</li><li>MON</li><li>AMS</li><li>FRA</li></ul>|<ul><li>TOK</li><li>HKG</li><li>PAR</li><li>MIL</li><li>STK*</li><li>OSL</li></ul>|<ul><li>MEX</li><li>SAO</li><li>SYD</li><li>MEL</li><li>PER*</li><li>CHE</li><li>SEO</li></ul>|
**Tabla 1: Utilización de capas**<br/>
Las ofertas de Direct Link en los mercados marcados con un asterisco (*) DEBEN solicitar Global Routing.

## Si estoy conectado a un Direct Link NSP o Direct Link Cloud Exchange en una región como Dallas, ¿tendré acceso a otras regiones de EE.UU. mediante Direct Link?
Sí, podrá tener acceso a áreas fuera de su región si elige el complemento Global Routing. Si no se selecciona esta opción, el tráfico de Direct Link se limitará a la región para el POP que haya seleccionado.

## ¿Puedo conectarme a cualquier región disponible desde una ubicación de Direct Link determinada?
Sí, siempre que solicite Direct Link con el complemento Global Routing.

## ¿Puedo restringir las regiones a las que puede llegar mi Direct Link?
No. IBM Cloud ofrece dos opciones: (1) una región única, o (2) todas las regiones, con el complemento Global Routing.

## ¿Qué pasa si he utilizado el proceso de pedido automatizado para Equinix Cloud Exchange y se me ha asignado una subred que se solapa con mi red interna?

A partir de marzo de 2018, la práctica recomendada es cancelar el pedido automatizado y enviar una incidencia nueva para rellenar el cuestionario de Direct Link. Debe indicar si prefiere otra subred en el rango 10.254.x.x o 172.32.x.x.

## ¿Cuál es la diferencia entre Direct Link Exchange y Direct Link Connect?

Estos dos servicios son similares, de coste relativamente bajo, tolerantes a la latencia y son puntos de entrada rápidos a los beneficios de IBM Cloud Direct Link. En resumen, Exchange utiliza proveedores de centros de datos y Connect utiliza transportistas Telco. A continuación, se muestran detalles adicionales:

**Direct Link Exchange** es para los clientes que prefieren utilizar un intercambio dentro de un centro de datos. Con un servicio de Exchange, los clientes pueden habilitar rápidamente la conectividad multinube para Colocation, ya que los circuitos subyacentes ya se suministran (el resto de los proveedores de nube ya deben tener una interconexión física en el recurso).

Direct Link Exchange puede permitir un entorno compartido multinube mediante un puerto de intercambio de nube único, creado por una conexión NNI en la capa 2 entre IBM Cloud y el proveedor de Cloud Exchange Service. Hay disponibles velocidades del puerto de hasta 1 GB.

**Direct Link Connect** es para los clientes que prefieren utilizar una red existente entre su propio despliegue local e IBM Cloud. Con un servicio de Direct Link Connect, los clientes pueden utilizar redes Telco nuevas y existentes (como por ejemplo MPLS) para habilitar IBM Cloud rápidamente, optimizando circuitos subyacentes subministrados previamente.

Con Direct Link Connect, IBM y el socio se conectarán con el cliente en las capas 2 y 3 mediante NNI (Network-to-Network Interfaces) duales de 10G de 2 capas, operadas por socios de IBM en servicios de todo el mundo. Hay disponibles velocidades de puerto de hasta 5 GB.

