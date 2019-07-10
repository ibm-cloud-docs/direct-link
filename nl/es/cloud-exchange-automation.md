---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: provisioning, Exchange, order, support, ticket, diverse, virtual circuit, parameters, Terms and Conditions

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:note: .note}
{:download: .download}

# Suministro de IBM Cloud Direct Link Exchange
{: #provisioning-ibm-cloud-direct-link-exchange}

En esta página se indica cómo solicitar el servicio {{site.data.keyword.cloud}} Direct Link Exchange. Si el pedido de {{site.data.keyword.cloud_notm}} Direct Link es para Equinix Cloud Exchange, el suministro del servicio está completamente automatizado, lo que significa que puede [realizar un pedido de una conexión de IBM Cloud Direct Link (Equinix) sin abrir una incidencia de soporte de IBM](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix), tal como se describe en un documento relacionado.

Actualmente, las prestaciones de automatización están limitadas a Equinix Cloud Exchange. En releases subsiguientes, la automatización se habilitará para otros proveedores.
{:note}

## Requisitos previos
{: #cloud-exchange-prerequisites}

Para utilizar la función de pedido automatizado, las VLAN privadas deben estar asociadas a un VRF en la red privada de {{site.data.keyword.cloud_notm}}. Si no se cumple este requisito, se generará una incidencia de soporte de IBM cuando realice un pedido a través del Portal de clientes.

 * [Cómo solicitar Cloud Exchange](#how-to-order-cloud-exchange-no-equinix)
 * [Cómo solicitar Cloud Exchange para Equinix](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix)

## Cómo solicitar Cloud Exchange
{: #how-to-order-cloud-exchange-no-equinix}

Para suministrar una conexión de IBM Cloud Direct Link Exchange, siga estos pasos:

**Paso 1:**

Inicie sesión en la cuenta del cliente en el [Portal de clientes ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://cloud.ibm.com/).

**Paso 2:**

En el separador **Red**, seleccione **Direct Link -> Exchange**, para abrir una página que muestra las conexiones de IBM Cloud Direct Link existentes, si las hay.

![Paso 2](/images/pup_exchange_list.png)

**Paso 3:**

Después de pulsar el botón **Solicitar Direct Link Exchange** en la parte superior de la página, verá el formulario de pedido en el que puede especificar los parámetros de configuración para la conexión de IBM Cloud Direct Link Exchange.

![Paso 3](/images/pup_exchange_create_default.png)

**Paso 3A:**

Opcionalmente, si se puede acceder a diversos puertos, y previamente ha suministrado el primer circuito virtual, verá una pantalla parecida a la siguiente, que muestra dos puertos, en la que puede seleccionar su segundo circuito virtual.

![imagen de 2 puertos](/images/pup_exchange_create_ports.png)

**Paso 4:**

En el formulario de pedido, especifique los parámetros siguientes para configurar Direct Link:
  * Especifique el nombre de conexión de IBM Cloud Direct Link.
  * En la lista, seleccione la ubicación en la que desea establecer la conexión de IBM Cloud Direct Link.
  * En la lista, seleccione el nombre del proveedor Cloud Exchange que prefiera.
  * Seleccione la velocidad de enlace necesaria para la conexión.
  * Seleccione la opción de direccionamiento para la conexión.
  * Especifique un número de ASN del rango proporcionado en el recuadro de información de los intercambios BGP.

**Paso 5:**

A medida que seleccione o especifique estos valores, verá un cargo mensual aproximado en el panel de la derecha.

![Paso 4-5](/images/pup_exchange_create_prices.png)

**Paso 6.**

Los campos del formulario se validan a medida que especifica los valores. 
Debe **ACEPTAR** los términos y condiciones para que se habilite el botón "Crear".

**Paso 7:**

Después de realizar el pedido y de aceptar los términos y condiciones, se generará una incidencia de soporte de IBM para continuar con el suministro del servicio. El número de incidencia se mostrará en la IU después de realizar el pedido. 

![Paso NE1](/images/pup_exchange_ticket_notification.png)

**Paso 8:**

Al pulsar en el número de incidencia del mensaje verá los detalles de la incidencia.

![Paso NE2](/images/pup_exchange_ticket_details.png)
