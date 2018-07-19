---

copyright:
  years: 2018
lastupdated: "2018-04-24"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Utilización conjunta de IBM Cloud Direct Link e IBM Cloud Object Storage

En este documento se describe cómo configurar IBM Cloud Direct Link de forma que tenga acceso a IBM Cloud Object Storage y a otros servicios de IBM Cloud. Existen varios métodos para la creación de puentes entre la red privada de IBM Cloud IaaS, en la que existe IBM Cloud Direct Link, y la red "pública" que da soporte a las funciones de IBM Cloud PaaS y SaaS, sin abandonar realmente la red troncal de IaaS.

De acuerdo con la política actual, no se puede acceder a los puntos finales de servicio privado de IBM Cloud a través de IBM Cloud Direct Link. Las técnicas que se describen en este documento se basan en el acceso indirecto a través de sistemas alojados en IBM Cloud. Aunque no se puede acceder a los puntos finales de servicio privados mediante Direct Link, los servidores privados y los dispositivos de un cliente pueden llegar a ser accesibles.

## ¿Qué es IBM Cloud Object Storage (COS)?

IBM Cloud Object Storage es una plataforma de escala web que almacena datos no estructurados. Proporciona fiabilidad, seguridad, disponibilidad y recuperación tras desastre sin réplica. 

La información almacenada en IBM Cloud Object Storage está cifrada y distribuida entre varias ubicaciones geográficas. Se puede acceder a esta información a través de una implementación de la API S3. Este servicio utiliza las tecnologías de almacenamiento distribuido que proporciona el servicio IBM Cloud Object Storage.

IBM COS está disponible en dos configuraciones: **Cross Region (varias regiones)** y **Regional**. El servicio Cross Region proporciona una mayor durabilidad y disponibilidad que el uso de una sola región, pero a costa de una latencia ligeramente superior. Actualmente este servicio está disponible en Estados Unidos y en la UE. El servicio Regional proporciona lo contrario: distribuye los objetos en varias zonas de disponibilidad dentro de una sola región. Si no se puede acceder a una determinada región o zona de disponibilidad, el almacén de objetos continúa funcionando correctamente. Los cambios que falten se aplicarán cuando el centro de datos inaccesible vuelva a estar en línea.

## ¿Qué es IBM Cloud Direct Link?

IBM Cloud Direct Link es una suite de productos que proporciona a los clientes la posibilidad de crear conexiones privadas entre sus entornos de red remota y sus despliegues de IBM Cloud. 

## Utilización de Cloud Object Storage (COS) sobre IBM Cloud Direct Link

La familia de soluciones de conectividad de IBM Cloud Direct Link es una oferta de IaaS, que está pensada para permitir la conectividad de WAN privada con nuestros servicios IaaS. La mayoría de las soluciones de IBM Cloud PaaS y SaaS se crean sobre IaaS. Por lo tanto, puede iniciar estos tipos de conexiones desde dentro de IBM Cloud.

Estos tres enfoques pueden ayudarle a conectarse a IBM Cloud PaaS y SaaS mediante IBM Cloud Direct Link. Actualmente, el método 3 es el enfoque recomendado, porque se ha probado más exhaustivamente.

## Tres métodos para la conexión con PaaS y SaaS con Direct Link


### Método 1: Utilizar un dispositivo de direccionador virtual (VRA, a veces llamado Vyatta) para crear un "salto a público"
 
![vyatta-flow.png](images/vyatta-flow.png)



**Premisa básica: se conecta a IBM COS con un "salto público" para conectarse a los puntos finales de almacenamiento** *Este "salto público" nunca abandona la red troncal de IBM Cloud IaaS.*

* El cliente elige un punto final público con la ayuda del equipo de soporte al cliente de IBM COS y de incorporación y recibe una clave de API.
* En su direccionador local, el cliente añade rutas a subredes específicas, con lo que se garantiza un flujo de tráfico fluido que utiliza IBM Cloud Direct Link
* En su VRA, el cliente crea una ruta para atravesar la red pública y llegar al punto final público para los servicios de IBM COS
* El cliente debe suministrar un par de alta disponibilidad de hardware VRA (@x)
* Cada miembro de VRA recibe 20 TB al mes de ancho de banda incluido, para desplazar los cargos a su medición y facturación de nube pública
* Utilice la agrupación de ancho de banda entre los servidores alojados para acumular ancho de banda de prepago.


### Método 2: Paso a través de servidor de nube (privado-a-privado)

![reverse=proxy](images/reverse-proxy.png)

**Premisa básica: servidores de nube fiables con credenciales de COS**

 * El cliente proporciona uno varios servidores, VSI o nativos, en IBM Cloud
 * Cada servidor aloja una aplicación basada en la web o de script (Java, Python, PHP, etc.) que escucha las conexiones y realiza solicitudes únicamente en la interfaz privada
 * La app del servidor utiliza su propia API o partes de S3
 * Las interfaces privadas del servidor de IBM Cloud son bastante seguras. Segregue el acceso dentro de la red privada mediante VLAN, grupos de seguridad, cortafuegos de SO o VRA
 * Las medidas para validar el interlocutor y limitar el alcance de la API son adecuadas
 * Los clientes de la red local del cliente utilizan direcciones IP privadas del servidor de paso a través de la nube como destinos de las solicitudes
 * Requiere direccionamiento del cliente y cambios de DNS
 * La aplicación alojada en servidor maneja cada solicitud emitiendo una llamada de API autenticada a un punto final de COS privado, y devuelve la respuesta al interlocutor

### Método 3: Proxy inverso (privado-a-privado)

Este método es el enfoque recomendado actualmente.

**Premisa básica: interlocutores del cliente local fiables con credenciales de COS**

 

 * Como una adaptación del Método 2, en lugar de alojar apps web en los servidores de Cloud, se alojan servidores HTTPS de host (por ejemplo, NGINX) configurados para el proxy inverso.
 * Cada servidor escucha en HTTPS, con certificado autoemitido, y pasa las solicitudes directamente a los puntos finales de COS privados que se indican en el documento siguiente:
 
 ![Puntos finales de COS](https://console.bluemix.net/docs/services/cloud-object-storage/basics/endpoints.html)
 
### Vea un ejemplo de cómo mejorar la fiabilidad y el rendimiento de la nube (no específico de COS): `serverfault.com`

 * Para aumentar el escalado y la capacidad de recuperación, se pueden desplegar varios servidores proxy. 
 * Utilice DNS en rueda en la parte del cliente para conseguir funciones rudimentarias de migración tras error y equilibrio de carga.
 * Los servidores proxy se pueden colocar detrás de un dispositivo direccionador virtual (VRA) por motivos de protección y registro centralizado.
 
 ## Gestión y suministro de prestaciones de IBM Cloud 
 
Esta sección contiene enlaces rápidos a la documentación de algunas ofertas de IBM Cloud PaaS y SaaS con las que puede conectar mediante IBM Cloud Direct Link.

## Cómo suministrar servidores nativos

Para obtener instrucciones detalladas sobre cómo suministrar servidores nativos, consulte [este documento](https://console.bluemix.net/docs/bare-metal/about.html#getting-started-with-bare-metal-servers).

## Cómo suministrar un dispositivo direccionador virtual (VRA)

Para obtener instrucciones detalladas sobre cómo suministrar un VRA, consulte [este documento](https://console.bluemix.net/docs/infrastructure/virtual-router-appliance/getting-started.html#getting-started).

## Cómo suministrar IBM Cloud Object Storage (COS)

 * Para obtener instrucciones detalladas sobre cómo suministrar COS, consulte [este documento](https://console.bluemix.net/catalog/services/cloud-object-storage).
 
 * Utilice uno de los puntos finales privados (mostrados anteriormente) para que actúe como interfaz con el contenedor u objeto de su cuenta de COS suministrada.
