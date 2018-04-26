---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-11"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Solicitar IBM Cloud Direct Link

Mientras se prepara para solicitar el tipo de IBM Cloud Direct Link que mejor se adapte a sus necesidades, puede seguir los enlaces siguientes (o desplazarse por el documento) para obtener una visión general del proceso. Cuando esté listo para realizar el pedido, encontrará instrucciones paso a paso que le guiarán durante el proceso de solicitud en nuestra serie de documentos "paso a paso".

* [Cómo solicitar IBM Cloud Direct Link Exchange](how-to-order.html#how-to-order-ibm-cloud-direct-link-exchange)
* [Cómo solicitar IBM Cloud Direct Link Connect](how-to-order.html#how-to-order-ibm-cloud-direct-link-connect)
* [Cómo solicitar IBM Cloud Direct Link Dedicated](how-to-order.html#how-to-order-ibm-cloud-direct-link-dedicated)
* [Cómo solicitar IBM Cloud Direct Link Dedicated Hosting](how-to-order.html#how-to-order-ibm-cloud-direct-link-dedicated-hosting)

## Cómo solicitar IBM Cloud Direct Link Exchange

 * Verifique las capacidades del proveedor de la red para llegar al PoP apropiado y conectarse al proveedor asociado de Cloud Exchange.
 * Utilice el [Portal de cliente ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/) para abrir una solicitud de IBM Cloud Direct Link Exchange y completar la información solicitada. (Se puede solicitar la ayuda de ingenieros de ventas de IBM). Si utiliza el proveedor de Equinix, el proceso de pedido y suministro estará [completamente automatizado](cloud-exchange-automation.html).
 * Póngase en contacto con el proveedor de Exchange y negocie la conectividad con su intercambio.
 * Solicite la conectividad entre el proveedor de red y el proveedor de Exchange.
 * Solicite un "circuito virtual" a través del proveedor de Exchange, y consulte el ID de incidencia de la solicitud de IBM Cloud Direct Link de {{site.data.keyword.BluSoftlayer_notm}} como "ID de solicitud" o "ID de autorización"
 * La asignación de IP en la infraestructura de red de {{site.data.keyword.BluSoftlayer_notm}} se completará en 3 días hábiles una vez que se complete la solicitud de circuito virtual.

## Cómo solicitar IBM Cloud Direct Link Connect

 * Verifique las capacidades del proveedor de la red para llegar al PoP adecuado y conectarse al proveedor asociado de Connect.
 * Utilice el [Portal de cliente ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/) para abrir una solicitud de IBM Cloud Direct Link Connect y completar la información solicitada. (Se puede solicitar la ayuda de ingenieros de ventas de IBM). 
 * Póngase en contacto con el proveedor de Connect y negocie la conectividad con su intercambio.
 * Solicite la conectividad entre el proveedor de red y el proveedor de Connect.
 * Solicite un "circuito virtual" a través del proveedor de Connect, y consulte el ID de incidencia de la solicitud de IBM Cloud Direct Link de {{site.data.keyword.BluSoftlayer_notm}} como "ID de solicitud" o "ID de autorización".
 * La asignación de IP en la infraestructura de red de {{site.data.keyword.BluSoftlayer_notm}} se completará dentro de 3 días hábiles una vez que se complete la solicitud de circuito virtual.

## Cómo solicitar IBM Cloud Direct Link Dedicated

 * Verifique las capacidades del proveedor de la red para llegar al PoP apropiado y conectarse al entorno de {{site.data.keyword.BluSoftlayer_notm}}.
 * Abra una solicitud de IBM Cloud Direct Link Dedicated y complete la información solicitada. (Se puede solicitar la ayuda de ingenieros de ventas de IBM).
 * {{site.data.keyword.BluSoftlayer_notm}} proporciona la Carta de autorización (Letter of Authorization, LOA) para la conexión.
 * Confirme que el circuito haya llegado al PoP y que el operador lo haya completado.
 * Solicite la conexión utilizando la información de {{site.data.keyword.BluSoftlayer_notm}} CFA (Customer Facility Assignment) en la LOA, que normalmente tarda entre 2 y 10 días hábiles en completarse. (Este plazo depende del proveedor de instalaciones y del tipo de prioridad de solicitud, ya que la coloca el cliente). Este proceso incluye la configuración del parche al puerto de terminación de {{site.data.keyword.BluSoftlayer_notm}}.
 * Proporcione {{site.data.keyword.BluSoftlayer_notm}} con la notificación de terminación de conexión desde el proveedor de recursos en la incidencia del portal de {{site.data.keyword.BluSoftlayer_notm}}.
 * {{site.data.keyword.BluSoftlayer_notm}} verificará la eficacia del aviso de terminación y solicitará que el parche se cree desde LOA/CFA al direccionador de conexión (XCR) y a otros engranajes.
 * Su asignación de IP en la infraestructura de red de {{site.data.keyword.BluSoftlayer_notm}} se completará dentro de 3 días hábiles una vez que se complete la conexión.

## Cómo solicitar IBM Cloud Direct Link Dedicated Hosting

 * Identifique los requisitos de colocación y de conectividad, y trabaje con el equipo de ventas de IBM para finalizar y ejecutar un contrato y una adición técnica.
 * {{site.data.keyword.BluSoftlayer_notm}} ejecuta una solicitud de compilación con el proveedor de colocación para el entorno y los servicios solicitados. El despliegue normalmente se completa dentro de 30 días desde que se realiza la solicitud de compilación.
 * Cuando se haya completado la compilación de su caja de colocación, el proceso para interconectar entre la caja de colocación y el engranaje XCR del entorno de POD {{site.data.keyword.BluSoftlayer_notm}} seguirá el proceso de IBM Cloud Direct Link Dedicated mostrado anteriormente, empezando por el Paso 3.
