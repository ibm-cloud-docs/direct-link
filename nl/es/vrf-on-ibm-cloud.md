---

copyright:
  years: 2017, 2018
lastupdated: "2018-07-25"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Visión general de Virtual Routing and Forwarding (VRF) en IBM Cloud

Por definición, el direccionamiento y reenvío virtual (VRF) es una tecnología que se incluye en direccionadores de red de Protocolo de Internet (IP). Se entrega como un servicio troncal inherente.

## Opciones de conectividad para IBM Cloud

Los **recursos de cloud dispersos** son recursos en más de una ubicación, o incluso en más de una subred o VLAN. Estos recursos requieren que una función de direccionamiento se comunique entre sí, incluso dentro de un contexto de red privada. En este documento se describe una opción de comunicación de tenencia de "aislamiento múltiple", que a menudo se denomina _VRF de cliente_. Se implementa como una VPN de MPLS Layer-3 (RFC 4364) en toda la red troncal global de IBM Cloud.

En general, IBM Cloud Platform ofrece dos opciones para el direccionamiento a través de nuestra red privada, lo que proporciona conectividad entre pods y centros de datos: 

1. **Tenencia compartida:** Una red lógica común, compartida por todos los arrendatarios que utilizan este modelo, con la separación proporcionada por las Listas de control de acceso (ACL) automatizadas, y habilitadas con la expansión de VLAN. (Esta opción no se describe en este documento.)

2. **Aislamiento múltiple:** Una red lógica dedicada por arrendatario, que no permite la interacción con las redes lógicas de otros arrendatarios.  

En este documento se utiliza el término **VRF de cliente** para describir la conectividad de red de _aislamiento múltiple_.

## Visión general de VRF de cliente

El direccionamiento y reenvío virtual (VRF) permite que varias instancias de una tabla de direccionamiento exista en un direccionador y que trabajen simultáneamente. Con direccionamiento y reenvío virtual (VRF), la red VRF de cada cliente está segmentada dentro de su tabla de direccionamiento. Esta segmentación permite la superposición de direcciones IP, y no crea ninguna interacción o interferencia con otros VRF de cliente. IBM Cloud utiliza una gran parte de la red `10.0.0.0/8 `, que puede solaparse con las redes remotas de muchos clientes. 

Al utilizar Virtual Routing and Forwarding (VRF), los clientes pueden utilizar direcciones IP remotas que normalmente no se pueden solapar en la tabla Global. IBM sigue reservando las siguientes direcciones RFC 1918, direcciones locales de enlace y direcciones de multidifusión, que son indireccionables a partir de este servicio VRF:

* `10.0.0.0/14` 
* `10.200.0.0/14` 
* `10.198.0.0/15` 
* `169.254.0.0/16` 
* `224.0.0.0/4` 
* `166.9.0.0/16` (que utiliza el servicio de punto final privado)
* Cualquier rango de IP asignado a sus VLAN en la plataforma IBM.

IBM está avanzando con un despliegue de próxima generación en la nube para habilitar Virtual Private Cloud (VPC) en nuestras Zonas de disponibilidad (AZ). Esta nueva función de VPC permite a los clientes utilizar su propia IP (BYoIP) en las AZ, habilitadas para VPC, que se encuentran en Dallas, Washington DC, Londres, Frankfurt, Tokio y Sídney. 

Cada arrendatario de la red troncal que utiliza Virtual Routing and Forwarding (VRF) puede tener una (y sólo una) _VRF de cliente_ por Direct Link, que proporciona conectividad entre todos los servidores del arrendatario, independientemente de la ubicación. Sin embargo, un cliente puede tener más de una cuenta de Direct Link que se alimenta en un único direccionador de interconexión.  

* Los servidores de un arrendatario en cualquier VLAN, en cualquier pod, en cualquier centro de datos de todo el mundo puede llegar a todos los otros servidores de ese arrendatario de forma global. 

* El VRF de cliente de cada arrendatario está conectado a la red de servicios compartidos comunes, para proporcionar accesibilidad privada para estos servidores para que utilicen DNS, almacenamiento compartido, supervisión, parches, etc.

* El cliente de VRF es un servicio de conectividad que proporciona aislamiento entre los arrendatarios. Cualquier control adicional necesario dentro de una tenencia debe suministrarse por separado, utilizando una pasarela, grupos de seguridad o controles basados en host.

## Ventajas de pasar a un VRF de cliente

**Las ventajas principales de un VRF de cliente son:**

* Tecnología de separación de _aislamiento múltiple_ probada y ampliamente aceptada por el sector. Muchos clientes encuentran el enfoque de VPN de nivel 3 más agradable (que las ACL) a sus auditores y a los responsables de la conformidad.   

* Los clientes pueden ampliar o migrar el alcance de su red de forma significativa, debido a la adición de nuevos sitios o aplicaciones en toda la red de IBM. 

* Las tablas de direccionamiento específicas de arrendatarios acotan la apertura de la superposición de direcciones IP, sin el riesgo de solapamiento con las subredes de otros arrendatarios u otras partes de la red que no son aplicables. 

** Se han producido algunos intercambios menores con el VRF de cliente, en comparación con el modelo de ACL más antiguo: **  

* La conversión a un VRF de cliente requiere una ventana de mantenimiento, lo que provoca una interrupción breve de los flujos de tráfico de la red troncal.

* El acceso remoto por medio de los servicios VPN gestionados (SSL, IPSec) está limitado al centro de datos local; sin embargo, la base de datos de ACL compartida permite el acceso global desde cualquier punto de entrada.

* VLAN que se amplía dentro de la tenencia _de aislamiento múltiple_ de un cliente no disponible.

## Qué sucede durante el proceso de conversión de la cuenta

Muchos clientes están operando actualmente en un modelo de tenencia compartido en la red de IBM Cloud. Durante la conversión, la tenencia se convierte para utilizar un VRF de cliente, más habitualmente con una nueva suscripción de Direct Link, o como se requiere o se solicita de otro modo.  

El proceso de conversión implica una interrupción de la red, mientras que las VLAN y sus subredes se separan de la red troncal ACL y luego se conectan a la VRF del cliente. Este proceso da como resultado algunos momentos de pérdida de paquetes para el tráfico de entrada o salida de las VLAN. Los paquetes dentro de la VLAN siguen fluyendo. En los casos en los que se ha implicado una pasarela de red, como por ejemplo un dispositivo de seguridad FortiGate o un dispositivo de direccionador virtual, no se producen interrupciones entre las VLAN conectadas a dicha pasarela. Los servidores no ven por sí mismos una interrupción de red y la mayoría de las cargas de trabajo se recuperan automáticamente cuando se reanuda el flujo de tráfico. La duración total de la interrupción depende del alcance de la topología del arrendatario, es decir, del número de subredes, de las VLAN y de los pods que incluye la tenencia.

![El proceso de conversión](/images/vrf-on-ibm-cloud.png)

Durante la migración, las VLAN de cliente se desconectan de la red troncal y se reconecta a VRF del cliente.  La duración de la interrupción varía en función de la cantidad de LAN, POD y centros de datos implicados. El tráfico entre las VLAN se ha interrumpido, pero los servidores se mantienen conectados a la red. La aplicación puede o no verse afectada, dependiendo de su sensibilidad a la pérdida de paquetes.

## Cómo puede iniciar la conversión

Nuestros clientes pueden abrir un tíquet de soporte a través de su cuenta de [IBM Cloud Console ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo") ]( https://control.bluemix.net/support/unifiedConsole/tickets/add), solicitando que se migren a un VRF. El tíquet debe indicar: "Pregunta de red privada" e incluye el texto siguiente en el tíquet de soporte: 

"Estamos solicitando que la cuenta _rellene su número de cuenta_ se mueva a su propio VRF. Comprendemos los riesgos y aprobamos el cambio. Vuelva a responder con la ventana (s) planificada (s) de tiempo en la que se realizará este cambio para que podamos prepararnos para la migración." 

La migración la ha completado el equipo de IBM Cloud Network Engineering. No es necesaria ninguna otra información del cliente, excepto una planificación acordada. Por lo general, la pérdida de paquetes puede durar de 15 a 30 minutos, dependiendo de la complejidad de la cuenta. (Puede ser más largo si un cliente tiene conexiones de Direct Link heredadas). El proceso está altamente automatizado. Implica una interacción mínima por parte del equipo de IBM y debe ser transparente para el cliente.
