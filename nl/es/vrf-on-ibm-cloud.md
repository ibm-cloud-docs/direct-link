---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-05-21"

keywords: VRF, IP, routers, backbone, service, VLAN, multiple isolation, tenant, tenancy, datacenters, data, center, shared tenancy, private endpoint, Customer VRF, Private Network Question, support, ticket

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Visión general de Virtual Routing and Forwarding (VRF) en IBM Cloud
{: #overview-of-virtual-routing-and-forwarding-vrf-on-ibm-cloud}

Por definición, el direccionamiento y reenvío virtual (VRF) es una tecnología que se incluye en direccionadores de red de Protocolo de Internet (IP). Se entrega como un servicio troncal inherente.

## Opciones de conectividad para IBM Cloud
{: #connectivity-options-for-ibm-cloud}

Los **recursos de nube dispersos** son recursos en más de una ubicación, o incluso en más de una subred o VLAN. Estos recursos requieren que una función de direccionamiento se comunique entre sí, incluso dentro de un contexto de red privada. En este documento se describe una opción de comunicación de tenencia de "aislamiento múltiple", que a menudo se denomina _VRF de cliente_. Se implementa como una VPN de MPLS Layer-3 (RFC 4364) en toda la red troncal global de {{site.data.keyword.cloud}}.

En general, IBM Cloud Platform ofrece dos opciones para el direccionamiento a través de nuestra red privada, lo que proporciona conectividad entre pods y centros de datos:

1. **Tenencia compartida:** Una red lógica común, compartida por todos los arrendatarios que utilizan este modelo, con la separación proporcionada por las Listas de control de acceso (ACL) automatizadas, y habilitadas con la expansión de VLAN. (Esta opción no se describe en este documento.)

2. **Aislamiento múltiple:** Una red lógica dedicada por arrendatario, que no permite la interacción con las redes lógicas de otros arrendatarios.  

En este documento se utiliza el término **VRF de cliente** para describir la conectividad de red de _aislamiento múltiple_.

## Visión general de VRF (tecnología de aislamiento múltiple)
{: #vrf-overview}

El direccionamiento y reenvío virtual (VRF) permite que varias instancias de una tabla de direccionamiento exista en un direccionador y que trabajen simultáneamente. Con direccionamiento y reenvío virtual (VRF), la red VRF de cada arrendatario está segmentada dentro de su tabla de direccionamiento. Esta segmentación permite la superposición de direcciones IP, y no crea ninguna interacción o interferencia con otros VRF de arrendatario. IBM Cloud utiliza una gran parte de la red `10.0.0.0/8`, que puede solaparse con muchas redes remotas, por ejemplo con las redes desplegadas en los centros de datos de los clientes.

Mediante Virtual Routing and Forwarding (VRF), los arrendatarios de IBM Cloud pueden utilizar direcciones IP remotas que normalmente no se pueden solapar en la tabla Global. IBM sigue reservando las siguientes direcciones RFC 1918, direcciones locales de enlace y direcciones de multidifusión, a las que no se puede direccionar desde este servicio VRF:

* `10.0.0.0/14`
* `10.200.0.0/14`
* `10.198.0.0/15`
* `169.254.0.0/16`
* `224.0.0.0/4`
* `166.9.0.0/16` (que utiliza el servicio de punto final privado)
* Cualquier rango de IP asignado a sus VLAN en la plataforma IBM.

IBM está avanzando con un despliegue de próxima generación en la nube para habilitar Virtual Private Cloud (VPC) en nuestras Zonas de disponibilidad. Esta nueva función de VPC permite a los clientes traer su propia IP (BYoIP) en las zonas de disponibilidad habilitadas para VPC (las AZ), que se encuentran en Dallas, Washington DC, Londres, Frankfurt, Tokio y Sídney.

Cada arrendatario de la red troncal que utiliza Virtual Routing and Forwarding (VRF) puede tener una (y sólo una) _VRF de cliente_ por Direct Link, que proporciona conectividad entre todos los servidores del arrendatario, independientemente de la ubicación. Sin embargo, un arrendatario de IBM Cloud puede tener más de una cuenta de Direct Link que se alimenta en un único direccionador de interconexión.  

* Los servidores de un arrendatario en cualquier VLAN, en cualquier pod, en cualquier centro de datos de todo el mundo puede llegar a todos los otros servidores de ese arrendatario de forma global.

* El VRF de cliente de cada arrendatario está conectado a la red de servicios compartidos comunes, para proporcionar accesibilidad privada para estos servidores para que utilicen DNS, almacenamiento compartido, supervisión, parches, etc.

* VRF de cliente es un servicio de conectividad que proporciona aislamiento entre los arrendatarios. Cualquier control adicional necesario dentro de una tenencia debe suministrarse por separado, utilizando una pasarela, grupos de seguridad o controles basados en host.

## Ventajas de pasar a VRF
{: #benefits-of-moving-to-vrf}

**Las ventajas principales son las siguientes:**

* Tecnología de separación de _aislamiento múltiple_ probada y ampliamente aceptada por el sector. Muchos clientes de nube encuentran el enfoque de VPN de nivel 3 más agradable (que las ACL) para sus auditores y los responsables de la conformidad.   

* Los clientes de IBM Cloud pueden ampliar o migrar el alcance de su red de forma significativa, debido a la adición de nuevos sitios o aplicaciones en toda la red de IBM.

* Las tablas de direccionamiento específicas de arrendatarios acotan la apertura de la superposición de direcciones IP, sin el riesgo de solapamiento con las subredes de otros arrendatarios u otras partes de la red que no son aplicables.

**Se han producido algunos intercambios menores, en comparación con el modelo de ACL anterior:**  

* La conversión a un VRF de cliente requiere una ventana de mantenimiento, lo que provoca una interrupción breve de los flujos de tráfico de la red troncal.

* El acceso remoto por medio de los servicios VPN gestionados (SSL, IPSec) está limitado al centro de datos local; sin embargo, la base de datos de ACL compartida permite el acceso global desde cualquier punto de entrada.

* La VLAN que abarca el arrendamiento _de aislamiento múltiple_ no está disponible.

## Qué sucede durante el proceso de conversión de la cuenta
{: #what-happens-during-the-account-conversion-process}

Muchos clientes de IBM Cloud operan actualmente con un modelo de arrendamiento compartido en la red de IBM Cloud. Durante la conversión, la tenencia se convierte para utilizar un VRF de cliente, más habitualmente con una nueva suscripción de Direct Link, o como se requiere o se solicita de otro modo.  

El proceso de conversión implica una interrupción de la red, mientras que las VLAN y sus subredes se separan de la red troncal ACL y luego se conectan a la VRF del cliente. Este proceso da como resultado algunos momentos de pérdida de paquetes para el tráfico de entrada o salida de las VLAN. Los paquetes dentro de la VLAN siguen fluyendo. En los casos en los que se ha implicado una pasarela de red, como por ejemplo un dispositivo de seguridad FortiGate o un dispositivo de direccionador virtual, no se producen interrupciones entre las VLAN conectadas a dicha pasarela. Los servidores no ven por sí mismos una interrupción de red y la mayoría de las cargas de trabajo se recuperan automáticamente cuando se reanuda el flujo de tráfico. La duración total de la interrupción depende del alcance de la topología del arrendatario, es decir, del número de subredes, de las VLAN y de los pods que incluye el arrendamiento.

![El proceso de conversión](/images/vrf-on-ibm-cloud.png)

Durante la migración, las VLAN se desconectan de la red troncal y se vuelven a conectar al VRF del cliente.  La duración de la interrupción varía en función de la cantidad de LAN, POD y centros de datos implicados. El tráfico entre las VLAN se ha interrumpido, pero los servidores se mantienen conectados a la red. La aplicación puede o no verse afectada, dependiendo de su sensibilidad a la pérdida de paquetes.

## Cómo puede iniciar la conversión
{: #how-you-can-initiate-the-conversion}

Los clientes de IBM Cloud pueden [abrir una incidencia de soporte](https://cloud.ibm.com/unifiedsupport/cases/add) a través de su cuenta de la [consola de IBM Cloud ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")]( https://cloud.ibm.com/unifiedsupport/cases/add), solicitando que se migren a un VRF. En la incidencia se debe indicar: "Pregunta de red privada" y se debe incluir el texto siguiente en la incidencia de soporte:

"Estamos solicitando que la cuenta _rellene su número de cuenta_ se mueva a su propio VRF. Comprendemos los riesgos y aprobamos el cambio. Vuelva a responder con la ventana (s) planificada (s) de tiempo en la que se realizará este cambio para que podamos prepararnos para la migración."

La migración la ha completado el equipo de IBM Cloud Network Engineering. No es necesaria ninguna otra información, excepto una planificación acordada. Por lo general, la pérdida de paquetes puede durar de 15 a 30 minutos, dependiendo de la complejidad de la cuenta. (Puede ser más largo si la cuenta tiene conexiones antiguas de Direct Link). El proceso está muy automatizado y requiere una interacción mínima por parte del equipo de IBM, que debería resultar transparente.

Cuando abra una incidencia, se recomienda seleccionar la opción "Técnica" tal como se muestra en la figura siguiente, aunque cualquier opción puede funcionar si incluye el texto que se ha proporcionado anteriormente:

![imagen](https://media.github.ibm.com/user/11495/files/4474c300-4bd9-11e9-9bc7-d6242d7997e9)
