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

# Paso a paso: Solicitar IBM Cloud Direct Link Exchange

Esta página le indica cómo solicitar el servicio de IBM Cloud Direct Link Exchange. Si el pedido de IBM Cloud Direct Link se realiza en Equinix Cloud Exchange, el suministro de servicio será completamente automatizado, lo que significa que puede realizar un pedido para una conexión de IBM Cloud Direct Link (Equinix) sin abrir una incidencia de soporte de IBM.

**(Nota: Actualmente, las prestaciones de automatización están limitadas a Equinix Cloud Exchange. En releases subsiguientes, la automatización se habilitará para otros proveedores).**

## Requisitos previos

Para utilizar la función de automatización, las VLAN privadas deben estar asociadas a un VRF en la red privada de IBM Cloud. Si no se cumple este requisito, se generará una incidencia de soporte de IBM cuando realice un pedido a través del Portal de clientes.

 * [Cómo solicitar Cloud Exchange](#how-to-order-cloud-exchange)
 * [Cómo solicitar Cloud Exchange para Equinix](#how-to-order-cloud-exchange-for-equinix)

## Cómo solicitar Cloud Exchange

Para suministrar una conexión de IBM Cloud Direct Link Exchange, siga estos pasos:

**Paso 1:**

Inicie sesión en la cuenta del cliente en el [Portal de clientes ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/).

**Paso 2:**

En el separador **Red**, seleccione **Direct Link -> Exchange**, para abrir una página que muestra las conexiones de IBM Cloud Direct Link existentes, si las hay.

![Paso 2](/images/Equinix-Step2.png)

**Paso 3:**

Después de pulsar el botón **Solicitar Direct Link Exchange** en la parte superior de la página, verá el formulario de pedido en el que puede especificar los parámetros de configuración para la conexión de IBM Cloud Direct Link Exchange.

![Paso 3](/images/Equinix-Step3.png)

**Paso 3A:**

Opcionalmente, si se puede acceder a diversos puertos, y previamente ha suministrado el primer circuito virtual, verá una pantalla parecida a la siguiente, que muestra dos puertos, en la que puede seleccionar su segundo circuito virtual.

![imagen de 2 puertos](/images/exchange-2-ports-image.png)

**Paso 4:**

En el formulario de pedido, especifique los parámetros siguientes para configurar Direct Link:
  * Especifique el nombre de conexión de IBM Cloud Direct Link.
  * En la lista, seleccione la ubicación PoP en la que desea establecer la conexión de IBM Cloud Direct Link.
  * En la lista, seleccione el nombre del proveedor Cloud Exchange que prefiera.
  * Seleccione la velocidad de enlace necesaria para la conexión.
  * Seleccione la opción de direccionamiento para la conexión.
  * Especifique un número de ASN del rango proporcionado en el recuadro de información de los intercambios BGP.

**Paso 5:**

A medida que seleccione o especifique estos valores, verá un cargo mensual aproximado en el panel de la izquierda.

![Paso 4-5](/images/Equinix-Step4-5.png)

**Paso 6.**

Cuando haya proporcionado los valores de entrada, la pantalla de la IU siguiente mostrará los precios mensuales actuales en función de las opciones que haya seleccionado.

**Paso 7:**

Debe **ACEPTAR** los términos y condiciones antes de poder realizar un pedido de IBM Cloud Direct Link. Lea los términos y condiciones cuidadosamente, ya que contienen información técnica importante que debe comprender antes de continuar. **(Nota: Si no se aceptan los términos y condiciones, se generará una incidencia de soporte de IBM cuando realice el pedido).** La siguiente figura muestra las pantallas que verá, en función de lo que haya seleccionado en este paso.

La figura siguiente muestra la pantalla de términos y condiciones:

![Paso 7](images/Equinix-Step7.png)

La figura siguiente muestra la pantalla que verá si no acepta los términos y condiciones cuando realice el pedido. La pantalla muestra el número de incidencia generado:

![Aceptación de paso 7](/images/Equinix-Step7-NoAgree.png)

La figura siguiente muestra un ejemplo de apertura de incidencia:

![Incidencia del paso 7](/images/Equinix-Step7-NoAgree-Ticket.png)

**Paso 8:**

Después de realizar el pedido y de aceptar los términos y condiciones, se generará una incidencia de soporte de IBM para continuar con el suministro del servicio. El número de incidencia se mostrará en la IU después de realizar el pedido. 

![Paso NE1](/images/Non-Equinix-Step1.png)

**Paso 9:**

Al pulsar en el número de incidencia del mensaje verá los detalles de la incidencia.

![Paso NE2](/images/Non-Equinix-Step2.png)

## Cómo solicitar Cloud Exchange para Equinix

**Paso 1:**

Siga los pasos 1 al 7 de los pasos para la realización del pedido de Cloud Exchange anteriores

**Paso 2:**

Cuando haya realizado el pedido, se iniciará el suministro de IBM Cloud Direct Link.

![Paso 8](/images/Equinix-Step8.png)

**Paso 3:**

Podrá ver el estado de su conexión una vez haya realizado el pedido. Si la configuración se completa correctamente por parte de IBM, verá el estado **Suministrado**. Si la configuración no ha finalizado, verá el estado **En curso**. Si la configuración ha fallado, verá el estado **Creación fallida**. Si la configuración no se ha completado correctamente y la conexión BGP está activa, verá el estado **ACTIVO**.

![Paso 9 en curso](/images/Equinix-Step9-InProgress.png)

La figura siguiente muestra varios estados de conexión cuando se haya realizado el pedido:

![Paso 9 activo](/images/Equinix-Step9-UP.png)

**Paso 4:**

Si el estado de la conexión es **Suministrado**, expanda la conexión pulsando **>** delante de la conexión **Nombre**. A continuación, anote la información **Dirección IP del cliente** y **Clave de servicio**. Esta información será necesaria para configurar el direccionador de extremo del cliente y como clave de autorización para la configuración del lado del proveedor de nube (Equinix), respectivamente.

![Paso 10](/images/Equinix-Step10-Provisioned.png)

**Paso 5:**

Para las conexiones con estado **Suministrado**, después de expandir la conexión pulsando **>** delante de la conexión, verá un mensaje de error si hay una discrepancia con Peer Link Speed. Cuando la velocidad sea la misma en IBM y Equinix, ya no se mostrará esta notificación de error.

![Paso 11](/images/Equinix-Step11-PortMismatch.png)

**Paso 6:**

En las conexiones con el estado **Creación fallida**, se generará una incidencia de soporte de IBM y se comunicarán más detalles a través de la incidencia de soporte. Cuando expanda la conexión, verá los detalles de la incidencia de soporte.

![Paso 12](/images/Equinix-Step12-CreateFailed.png)

**Paso 7:**

En las conexiones con los estados **Suministrado**, **ACTIVO** o **INACTIVO**, podrá **suprimir** la conexión pulsando en la columna **ACCIONES** junto a la conexión.

![Paso 13](/images/Equinix-Step13-Delete.png)

**Paso 8:**

En las conexiones con el estado **Creación fallida** podrá **cancelar** la conexión pulsando en la columna **ACCIONES** junto a la conexión.

