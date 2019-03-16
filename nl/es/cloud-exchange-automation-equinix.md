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
{:note: .note}
{:download: .download}


# Suministro de IBM Cloud Direct Link Exchange para Equinix
{: #provisioning-ibm-cloud-direct-link-exchange-for-equinix}

Si el pedido de IBM Cloud Direct Link se realiza en Equinix Cloud Exchange, el suministro de servicio será completamente automatizado, lo que significa que puede realizar un pedido para una conexión de IBM Cloud Direct Link (Equinix) sin abrir una incidencia de soporte de IBM.

Actualmente, las prestaciones de automatización están limitadas a Equinix Cloud Exchange. En releases subsiguientes, la automatización se habilitará para otros proveedores.
{:note}

## Requisitos previos

Para utilizar la función de pedido automatizado, las VLAN privadas deben estar asociadas a un VRF en la red privada de IBM Cloud. Si no se cumple este requisito, se generará una incidencia de soporte de IBM cuando realice un pedido a través del Portal de clientes.

## Pasos para la solicitud y el suministro

**Paso 1:**

Siga los pasos del 1 al 7 de los [Pasos de solicitud de Cloud Exchange](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange) habituales.

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

