---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-02"

keywords: Dedicated, finalize, questionnaire, Special Network Services, billing, fees, VRF, BGP, ticket, cross-connect, link speed, VPN, data, center, PoP, ECMP

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Cuestionario de IBM Cloud Direct Link Dedicated
{: #ibm-cloud-direct-link-dedicated-questionnaire}

Gracias para abrir una solicitud de {{site.data.keyword.cloud}} Direct Link Dedicated. Para finalizar su solicitud, nos gustaría obtener alguna información adicional. Puede ponerse en contacto con un ingeniero en cualquier momento durante el proceso del cuestionario.  Una vez que haya completado el cuestionario, nuestro equipo de ingenieros de diseño de nube lo revisará y lo escalará al equipo de servicios de red especiales para su implementación.

## ¿Está de acuerdo y acepta las siguientes afirmaciones?
{: #dedicated-do-you-agree}

1. Cada conexión de Direct Link requiere una solicitud exclusiva.  Si necesita varias conexiones, abra una solicitud de Direct Link para cada conexión.

2. Las tarifas del servicio Direct Link Connect cubren el coste de la terminación del servicio en la infraestructura de IBM Cloud. 

 * Los servicios de la infraestructura se facturan por adelantado y comienzan tras la aceptación del pedido; sin embargo, debido a la naturaleza de IBM Cloud Direct Link, la facturación del servicio Direct Link empieza cuando se establece una sesión BGP (Border Gateway Protocol) con IBM Cloud, o bien 30 días después de que se proporcione la clave de servicio al cliente. 

 * La facturación finaliza después de que:
   * Un cliente solicite que se suprima un circuito, **y** 
   * El proveedor de intercambio o el proveedor de servicios de red haya desaprovisionado el circuito.
  * Para obtener más información, consulte la **Sección 5 - Cargos** del Acuerdo de servicios en la nube en el siguiente enlace: [https://www.ibm.com/support/customer/zz/en/selectcountrylang.html](https://www.ibm.com/support/customer/zz/en/selectcountrylang.html). Por ejemplo, los clientes de Estados Unidos visualizarían [este documento de contrato de servicios en la nube](https://www.ibm.com/support/customer/csol/contractexplorer/cloud/csa/us-en).

3. Cuando solicita el servicio Direct Link, el cliente es el responsable de los gastos asociados al acceso al PoP (punto de presencia) desde su red remota y de cualquier interconexión necesaria dentro del recurso de PoP. Si el proveedor requiere que se instale físicamente un direccionador u otro dispositivo en el PoP, el cliente será el responsable de los costes asociados a la instalación de dicho equipo.

4. IBM Cloud no solicitará una interconexión en nombre de ningún cliente.

5. IBM Cloud no coubicará ningún equipo del cliente en los POP de nuestra red. Solo aceptamos 'interconexiones' que sean Ethernet de fibra (solo fibra de modalidad única, ya sea 1Gig-LX o 10Gig-LR 1310nm) procedentes de su caja o de su proveedor. No aceptamos T1s, DS3s, ISDN, línea POTs, etc.  Deberá trabajar con su proveedor para determinar si necesita o no ubicar algún equipo en la instalación en la que se encuentra el PoP de IBM Cloud.

6. El servicio Direct Link se proporciona de forma que el enlace y el direccionador de IBM Cloud en el que termina constituyen puntos únicos de anomalía (SPOF). Si desea conseguir redundancia a través del servicio Direct Link, tendrá que solicitar dos conexiones con una ubicación de Direct Link con un direccionador secundario o bien terminar los enlaces en dos PoP de IBM Cloud diferentes.

7. No se podrá acceder a la red de servicios IBM Cloud directamente desde sus redes remotas. Se le notificará si esto cambia en el futuro.

8. IBM Cloud no permitirá a los clientes transportar tráfico entre sus sitios remotos a través de la red troncal de IBM Cloud. El producto Direct Link está pensado para que las redes remotas puedan comunicarse de forma privada con la infraestructura de IBM Cloud.

9. Una vez que haya confirmado que el circuito ha accedido al PoP y que lo ha completado el operador, deberá solicitar la interconexión con XCR (direccionador de conexión cruzada) de IBM Cloud, lo que suele tardar entre 2 y 10 días laborables en completarse. Esto incluye el parche en el puerto de terminación de SoftLayer.  Una vez completado, deberá proporcionar a IBM Cloud el aviso de finalización de interconexión desde el proveedor de la instalación. El proceso de IP en la infraestructura de red de IBM Cloud se completará en un plazo de 3 días hábiles una vez que se complete la interconexión.

10. IBM Cloud Direct Link requiere que se utilice una instancia de VRF (Virtual Routing and Forwarding). Esta función permite a los clientes definir sus propias direcciones IP remotas para utilizarlas en su red remota; sin embargo, debe ser consciente de que, aunque pueda utilizar la red 10.x.x.x, todavía no puede solapar con sus hosts dentro de IBM Cloud ni con la red de servicios de IBM Cloud (10.0.0.0/14, 10.198.0.0/15 y 10.200.0.0/14). La transición de su cuenta a un VRF requiere una breve interrupción de la red privada, ya que cada VLAN se migra a la nueva configuración. El equipo de servicios de red especiales trabajará con usted para definir una ventana para esta actividad. El equipo de servicios está disponible de lunes a viernes de 8 a 5 CST (huso horario de EE. UU. Central Estándar). Cualquier actividad de activación fuera de este periodo debe solicitarse mediante incidencia y aprobarse por adelantado si hay ingenieros disponibles.

11. VRF no es compatible con los servicios de IBM Cloud (antiguo SoftLayer) SSL, PPTP e IPSEC VPN.  Una alternativa consiste en utilizar el propio enlace directo para gestionar los servidores o en ejecutar su propia solución de VPN (como por ejemplo Vyatta), que se puede configurar con distintos tipos de VPN. Tras la migración a VRF, la VPN de SSL normalmente funciona cuando se realiza una conexión VPN con la ubicación del centro de datos en el que está el equipo al que se está accediendo, pero no permite el acceso de forma global.

12. IBM Cloud Direct Link Dedicated necesita BGP para implementar rutas a la red remota de un cliente.  Cuando se haya desplegado el servicio de Direct Link, IBM Cloud anunciará todas las subredes privadas asignadas a su cuenta. IBM Cloud no implementará filtros personalizados, prefijos AS-Path ni preferencias locales personalizadas en las publicaciones en el igual de BGP remoto del cliente. IBM Cloud no implementará filtros en las publicaciones recibidas en IBM Cloud. Los clientes tendrán que gestionar correctamente las publicaciones a/desde IBM Cloud desde el direccionador del extremo del cliente. 

## Otras preguntas
{: #dedicated-other-questions}

* **¿En qué PoP desea terminar el servicio Direct Link?**

* **¿Qué velocidad de enlace necesita (1, 2, 5 o 10 Gbps)?**

* **¿Necesita que se configure BGP MultiPath con ECMP para configurar una conexión redundante con IBM Cloud?**  

    _Si es así, incluya el ID de incidencia para la otra conexión. Número de incidencia ____________  (tenga en cuenta que ECMP solo se puede suministrar en dos sesiones en el mismo XCR de IBM Cloud.  Si desea utilizar ECMP, tenga en cuenta que ambos Direct Links deben acabar en el mismo direccionador.)_

* **¿Necesita acceso de direccionamiento local o global?**

    _Los clientes que seleccionen direccionamiento local solo podrán pasar tráfico entre los centros de datos que reciben servicio desde el PoP en el que se ha solicitado Direct Link.  Los clientes que deseen pasar tráfico fuera del PoP en el que se ha solicitado Direct Link deberán añadir la opción de direccionamiento global._

* **¿Está de acuerdo con la tarifa de direccionamiento global, incluido el cargo mensual de _SU UBICACIÓN_ y los cargos por excedente que se describen a continuación?**

    _El direccionamiento local incluye acceso a todos los centros de datos conectados directamente al PoP y proporciona un tráfico ilimitado de entrada/salida. El direccionamiento global amplía el acceso para incluir todos los centros de datos de IBM Cloud de forma global.  El ancho de banda se calcula cuando el servicio puede medir el tráfico. Cuando se calcule el ancho de banda, se le facturará mensualmente según el precio de mercado, tal como se muestra en la tabla siguiente._


### Precios de direccionamiento global
{: #dedicated-global-routing-pricing}

| Entrada de direccionamiento global | Salida de direccionamiento global |
|---|---|
| Gratuito | Circuito de 1, 2 o 5 Gbps - 10 TB de ancho de banda gratuitos |
| Gratuito | Circuito de 10 Gbps - 50 TB de ancho de banda gratuitos |


| Cargos por excedente de ancho de banda |
|---|
| Mercado 1: 0,05 $ por GB |
| Mercado 2: 0,10 $ por GB |
| Mercado 3: 0,15 $ por GB |
