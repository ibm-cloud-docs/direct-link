---

copyright:
  years: 2018, 2019
lastupdated: "2019-03-29"


keywords: Dedicated, Hosting, finalize, questionnaire, Network Engineering, billing, fees, VRF, BGP, ticket, cross-connects, datacenters, data, center, backhaul, single mode, single-mode, fiber, Letter of Authorization, LOA, contract

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Cuestionario de IBM Cloud Direct Link Dedicated Hosting
{: #ibm-cloud-direct-link-dedicated-hosting-questionnaire}

Gracias para abrir una solicitud de {{site.data.keyword.cloud}} Direct Link Dedicated Hosting.  Para finalizar su solicitud, nos gustaría obtener alguna información adicional. Puede ponerse en contacto con un ingeniero en cualquier momento durante el proceso del cuestionario.  Una vez que haya completado el cuestionario, nuestro equipo de ingenieros de diseño de nube lo revisará y lo escalará al equipo de ingenieros de red para su implementación.

## Reconocimientos
{: #dedicated-hosting-acknowledgements}

1. Las tarifas que se muestran en este cuestionario cubren el coste de la terminación del servicio en la infraestructura de red de IBM Cloud. Los costes de coubicación, incluidos archivadores, interconexiones, etc., incluyen tasas mensuales y no recurrentes que se indican por separado como parte de un contrato de coubicación.

2. IBM Cloud Direct Link Dedicated Hosting proporciona interconexiones de fibra de 1 Gbps o de 10 Gbps en la red privada de IBM Cloud. Deberá proporcionar un direccionador o un conmutador de capa 3 que pueda dar soporte a enlaces ascendentes de fibra de modalidad única (SMF). El tiempo de despliegue puede variar en función del proveedor del circuito; el tiempo de despliegue típico para este servicio es de entre 30 y 60 días.

3. Direct Link Dedicated Hosting requiere que se utilice una instancia de VRF (Virtual Routing and Forwarding). Esto permite al cliente definir sus propias direcciones IP remotas para utilizarlas en su red remota; sin embargo, debe ser consciente de que, aunque pueda utilizar la red 10.x.x.x, todavía no puede solapar con sus hosts dentro de IBM Cloud ni con la red de servicios de IBM Cloud (10.0.0.0/14, 10.198.0.0/15 y 10.200.0.0/14). La transición de su cuenta a un VRF requiere una breve interrupción de la red privada, ya que cada VLAN se migra a la nueva configuración.  El equipo de ingeniería de red trabajará con usted para definir una ventana para esta actividad.

4. VRF modifica el comportamiento de IBM Cloud SSL, PPTP e IPsec VPN. Estos suelen funcionar cuando se establece la conexión VPN con la ubicación del centro de datos en el que están los recursos de cálculo a los que se accede, pero no permite el acceso de forma global.  Como alternativa, puede utilizar el propio enlace directo para gestionar los servidores o puede ejecutar su propia solución de VPN (como por ejemplo Vyatta), que se puede configurar con distintos tipos de VPN. 

5. Direct Link Dedicated Hosting necesita BGP para implementar rutas a la red remota de un cliente.  IBM Cloud no implementará filtros en las publicaciones que se realicen en IBM Cloud.  IBM Cloud anunciará todas las subredes privadas asignadas a su cuenta.  Los clientes tendrán que gestionar correctamente las publicaciones recibidas en IBM Cloud.

6. IBM Cloud ofrece enlaces ascendentes duales, uno a cada direccionador de interconexión de IBM Cloud, para permitir que los clientes establezcan conectividad redundante. Esto se consigue en los direccionadores del cliente a través de sesiones BGP mediante el aprovechamiento de las capacidades de ECMP o simplemente mediante la ponderación de las conexiones.

7. No se podrá acceder a la red de servicios IBM Cloud directamente desde sus redes remotas o Dedicated Hosting.

8. IBM Cloud no le permitirá transportar tráfico entre sus sitios remotos a través de la red troncal de IBM Cloud. El servicio Direct Link está diseñado para que las redes remotas puedan comunicarse de forma privada con la infraestructura de IBM Cloud.

9. IBM Cloud ofrece Direct Link con direccionamiento local o global. Confirme el paquete de direccionamiento que necesita y que acepta los planes de ancho de banda asociados con dichos paquetes, que encontrará el enlace siguiente: ibm.biz/DirectLink-Docs.

10. Especifique cuánto tráfico que tiene previsto enviar por push a través de Direct Link y los centros de datos de IBM Cloud a los que tiene previsto enviar este tráfico.

11. Si no adquiere servicios de coubicación a través de IBM Cloud, será responsable de solicitar y de abonar las interconexiones entre su entorno e IBM Cloud.  Una vez conectado, proporcionaremos una Carta de autorización (LOA) en la que se detalla nuestra aprobación de la conexión y de la ubicación a la que se conectará.

12. Confirme que acepta los siguientes precios para Direct Link:
 * 1 Gbps: _PRECIO SEGÚN UBICACIÓN_ 
 * 2 Gbps: _PRECIO SEGÚN UBICACIÓN_
 * 5 Gbps: _PRECIO SEGÚN UBICACIÓN_
 * 10 Gbps: _PRECIO SEGÚN UBICACIÓN_
 * Direccionamiento global opcional
