---

copyright:
  years: 2018
lastupdated: "2018-06-11"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Cuestionario de IBM Cloud Direct Link Exchange

Gracias para abrir una solicitud de IBM Cloud Direct Link Exchange.  Para finalizar su solicitud, nos gustaría obtener alguna información adicional. Puede ponerse en contacto con un ingeniero en cualquier momento durante el proceso del cuestionario.  Una vez que haya completado el cuestionario, nuestro equipo de ingenieros de diseño de nube lo revisará y lo escalará al equipo de servicios de red especiales para su implementación.

## ¿Está de acuerdo y acepta las siguientes afirmaciones?

1. Cada conexión de Direct Link requiere una solicitud exclusiva. Si necesita varias conexiones, abra una solicitud de Direct Link para cada conexión.

2. Las tarifas del servicio Direct Link Exchange cubren el coste de la terminación del servicio en la infraestructura de IBM Cloud. 

 * Los servicios de la infraestructura se facturan por adelantado y comienzan tras la aceptación del pedido; sin embargo, debido a la naturaleza de IBM Cloud Direct Link, la facturación del servicio Direct Link empieza cuando se establece una sesión BGP (Border Gateway Protocol) con IBM Cloud, o bien 30 días después de que se proporcione la clave de servicio al cliente. 

 * La facturación finaliza después de que:
   * Un cliente solicite que se suprima un circuito, **y** 
   * El proveedor de intercambio o el proveedor de servicios de red haya desaprovisionado el circuito.
  * Para obtener más información, consulte la **Sección 5 - Cargos** del Acuerdo de servicios en la nube en el enlace siguiente: [ibm.biz/service-agreement](ibm.biz/service-agreement)
  * De forma alternativa, la facturación puede detenerse para un cliente si se notifica al mismo que su servicio de Direct Link se ha desactivado y va a dejar de funcionar.

3. Cuando solicita el servicio Direct Link, el cliente es el responsable de los gastos asociados al acceso al PoP (punto de presencia) desde su red remota y de cualquier interconexión necesaria dentro del recurso de PoP para acceder al proveedor de intercambio. El cliente (o su proveedor) también es el responsable de adquirir de IBM Cloud el circuito virtual. Si el proveedor requiere que se instale físicamente un direccionador u otro dispositivo en el PoP, el cliente será el responsable de los costes asociados a la instalación de dicho equipo. Confirme que su proveedor de red o de PoP puede acceder a Direct Link Exchange y puede estimar los costes asociados.

4. IBM Cloud no coubicará ningún equipo del cliente en los POP de nuestra red. Deberá trabajar con su proveedor para determinar si necesita o no ubicar algún equipo en la instalación en la que se encuentra el PoP de IBM Cloud.

5. El servicio Direct Link Exchange se proporciona de forma que el enlace y el direccionador de IBM Cloud en el que puede terminar constituyen puntos únicos de anomalía (SPOF). Si desea conseguir redundancia a través del servicio Direct Link Exchange, tendrá que terminar los enlaces en dos PoP de red de IBM Cloud distintos o solicitar dos conexiones en una ubicación de Direct Link Exchange con un direccionador secundario.

6. No se podrá acceder a la red de servicios IBM Cloud directamente desde sus redes remotas. Se le notificará si esto cambia en el futuro.

7. IBM Cloud no permitirá a los clientes transportar tráfico entre sus sitios remotos a través de la red troncal de IBM Cloud. El producto Direct Link Exchange está pensado para que las redes remotas puedan comunicarse de forma privada con la infraestructura de IBM Cloud.

8. Después de confirmar que el circuito ha accedido al PoP de Direct Link Exchange, tendrá que realizar un pedido con el proveedor de intercambio de nube y proporcionar toda la información pertinente al proveedor de intercambio de nube y a IBM Cloud. Para los proveedores de Equinix, el tiempo de despliegue puede llevar horas. El tiempo de despliegue típico para la oferta IBM Cloud Direct Link Exchange es de entre 5 y 10 días. 

9. IBM Cloud Direct Link Exchange requiere que se utilice una instancia de VRF (Virtual Routing and Forwarding) en el lado de IBM Cloud Network.   Esto permite al cliente definir sus propias direcciones IP remotas para utilizarlas en su red remota; sin embargo, debe ser consciente de que, aunque pueda utilizar la red 10.x.x.x, todavía no puede solapar con sus hosts dentro de IBM Cloud ni con la red de servicios de IBM Cloud (10.0.0.0/14, 10.198.0.0/15 y 10.200.0.0/14). La transición de su cuenta a un VRF requiere una breve interrupción de la red privada, ya que cada VLAN se migra a la nueva configuración.   El equipo de servicios de red especiales trabajará con usted para definir una ventana para esta actividad. El equipo de servicios normalmente está disponible de lunes a viernes de 8 a 5 CST (huso horario de EE.UU. Central Estándar). Cualquier actividad de activación fuera de este periodo deberá solicitarse mediante incidencia y aprobarse por adelantado si hay ingenieros disponibles. 

10. VRF no es compatible con los servicios de IBM Cloud SSL, PPTP e IPSEC VPN.  Una alternativa consiste en utilizar el propio enlace directo para gestionar los servidores o en ejecutar su propia solución de VPN (como por ejemplo Vyatta), que se puede configurar con distintos tipos de VPN. Tras la migración a VRF, la VPN de SSL normalmente funciona cuando se realiza una conexión VPN con la ubicación del centro de datos en el que está el equipo al que se está accediendo, pero no permite el acceso de forma global.

11. IBM Cloud Direct Link Exchange necesita BGP para implementar rutas a la red remota de un cliente. Cuando se haya desplegado el servicio de Direct Link, IBM Cloud anunciará todas las subredes privadas asignadas a su cuenta. IBM Cloud no implementará filtros personalizados, prefijos AS-Path ni preferencias locales personalizadas en las publicaciones en el igual de BGP remoto del cliente. IBM Cloud no implementará filtros en las publicaciones recibidas en IBM Cloud. Los clientes tendrán que gestionar correctamente las publicaciones a/desde IBM Cloud desde el direccionador del extremo del cliente. 

## Otras preguntas

* **¿Reconoce y acepta los precios de _SU UBICACIÓN_ para la conexión de IBM Cloud Direct Link Exchange?**

* ** IBM Cloud le asignará un ASN privado a fin de configurar BGP para anunciar sus redes remotas en su red privada de IBM Cloud.  ¿Le parece aceptable o preferiría utilizar su propio ASN público?**

* **¿Necesita que se configure BGP MultiPath con ECMP para configurar una conexión redundante con IBM Cloud?**  

    _Si es así, incluya el ID de incidencia para la otra conexión. Número de incidencia ____________  (tenga en cuenta que ECMP solo se puede suministrar en dos sesiones en el mismo XCR de IBM Cloud.  Si desea utilizar ECMP, tenga en cuenta que ambos Direct Links deben acabar en el mismo direccionador.)_

* **¿Necesita acceso de direccionamiento local o global?**

    _Los clientes que seleccionen direccionamiento local solo podrán pasar tráfico entre los centros de datos que reciben servicio desde el PoP en el que se ha solicitado Direct Link.  Los clientes que deseen pasar tráfico fuera del PoP en el que se ha solicitado Direct Link deberán añadir la opción de direccionamiento global._

* **¿Está de acuerdo con la tarifa de direccionamiento global, incluido el cargo mensual de _SU UBICACIÓN_ y los cargos por excedente que se describen a continuación?**

    _El direccionamiento local incluye acceso a todos los centros de datos conectados directamente al PoP y proporciona un tráfico ilimitado de entrada/salida. El direccionamiento global amplía el acceso para incluir todos los centros de datos de IBM Cloud de forma global.  El ancho de banda se calcula cuando el servicio puede medir el tráfico. Cuando se calcule el ancho de banda, se le facturará mensualmente según el precio de mercado, tal como se muestra en la tabla siguiente. _


### Precios de direccionamiento global

| Entrada de direccionamiento global | Salida de direccionamiento global |
|---|---|
| Gratuito | Circuito de 1, 2 o 5 Gbps - 10 TB de ancho de banda gratuitos |
| Gratuito | Circuito de 10 Gbps - 50 TB de ancho de banda gratuitos |


| Cargos por excedente de ancho de banda |
|---|
| Mercado 1: 0,05 $ por GB |
| Mercado 2: 0,10 $ por GB |
| Mercado 3: 0,15 $ por GB |
