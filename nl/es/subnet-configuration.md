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
{:download: .download}

# Configurar IBM Cloud Direct Link
{ #configure-ibm-cloud-direct-link}

Una vez se haya establecido la conectividad de IBM Cloud Direct Link, puede seguir los pasos descritos en este documento para configurar la subred e interactuar con IBM Cloud.

En general, para hacer que funcione la conexión de IBM Cloud Direct Link, tiene que realizar algunos pasos de configuración de red básicos, y luego establecer el protocolo BGP (Border Gateway Protocol). Durante el proceso de configuración, un ingeniero de IBM trabajará con usted para habilitar su red para utilizar la función de VRF (Virtual Routing Function), que es obligatoria.

## Configuración de red básica

1. Defina su red remota utilizando el espacio de direcciones privado de RFC1918 estándar. 
 * Para entornos nuevos, se recomienda **no** utilizar el espacio 10.0.0.0/8. 
 * Para los entornos existentes que utilizan 10.0.0.0/8, recomendamos obtener una evaluación más detallada, para asegurarse de que no haya ningún conflicto con la red de servicios de {{site.data.keyword.BluSoftlayer_notm}}, ni con las redes ya asignadas a su cuenta.

2. Nuestro personal de {{site.data.keyword.BluSoftlayer_notm}} asignará un /31 o /30 para cada conexión y configurará una dirección IP de la interfaz en la infraestructura del direccionador de conexión (XCR) de {{site.data.keyword.BluSoftlayer_notm}}.  

3. Configure la interfaz en el direccionador de extremo del cliente (CER), utilizando la dirección IP que le hemos proporcionado: tan sólo utilice la IP de XCR de {{site.data.keyword.BluSoftlayer_notm}} como el próximo paso para cualquier tráfico destinado a {{site.data.keyword.BluSoftlayer_notm}}. 

4. Para el tráfico de retorno, {{site.data.keyword.BluSoftlayer_notm}} utilizará la IP de CER asignada como el próximo paso para cualquier tráfico destinado a la red remota, como se anuncia a través de BGP.

## Configuración de BGP

Para intercambiar información de ruta con el entorno, {{site.data.keyword.BluSoftlayer_notm}} requiere que se configure BGP.  

1. **ASN**: {{site.data.keyword.BluSoftlayer_notm}} asigna un ASN privado para el uso de cada cliente. Como alternativa, puede utilizar su propio ASN público. Su preferencia se solicita en el momento de realizar el pedido. El ASN privado asignado se proporciona durante el proceso de implementación.

2. **VRF**: Al utilizar VRF, {{site.data.keyword.BluSoftlayer_notm}} anuncia las subredes privadas específicas asignadas a su cuenta de cliente.  Debe anunciar las redes remotas a las que desea que se pueda llegar desde la red privada de {{site.data.keyword.BluSoftlayer_notm}}. Las redes siguientes están filtradas y no se pueden aceptar: 0.0.0.0, 10.0.0.0/14, 10.198.0.0/15, 10.200.0.0/14, 169.254.0.0/16, 224.0.0.0/4. Es su responsabilidad como cliente gestionar los anuncios hacia y desde la red de IBM Cloud. (Se incluyen más detalles sobre VRF en la siguiente sección).

3. **ECMP**: Para los clientes que eligen crear redundancia en una ubicación soportada, {{site.data.keyword.BluSoftlayer_notm}} soporta la implementación de ECMP (equal-cost multipath) para proporcionar equilibrio de carga y redundancia entre los dos enlaces. Esta configuración de ECMP se debe solicitar en el momento del pedido.

## Especificaciones de BGP para IBM Cloud Direct Link 

Las especificaciones de BGP son las siguientes:

Como se ha comentado en la sección anterior, BGP es obligatorio para gestionar el direccionamiento a través de Direct Link. Una cuenta que solicite Direct Link se migrará al entorno VRF.

**Advertencias para VLANS y VRF:**
 * No se permite la expansión de VLAN entre cuentas en el entorno VRF. 
 * El servicio VPN de IPSEC está limitado. 
 
**Nota:** VRF no impide el acceso VPN de PPTP o SSL, pero su comportamiento cambia. Sin VRF, una conexión VPN es suficiente para ver todos los servidores de la cuenta. Con VRF, solo puede acceder a los recursos del mercado asociados a su VPN. Así, si se conecta al VPN DAL, solo puede conectarse a servidores DAL.

ASN de IBM Cloud es **13884**, para los servicios públicos y privados. 
 * El ASN predeterminado para un cliente cuando realiza el pedido es **64999**, pero el valor predeterminado se puede modificar mediante una solicitud del cliente. 
 * Opcionalmente, se puede utilizar un ASN privado de 4 bytes comprendido entre 4201000000 y 4201064511.
 * Si utiliza Direct Link Connect con un servicio de 3 capas, como IP VPN, IBM Cloud establecerá BGP con el ASN del proveedor de Direct Link Connect.
   
**Limitaciones estrictas en las asignaciones de IP:**
 * Si utiliza la red 10.x.x.x, todavía no puede crear solapamientos con los hosts dentro de IBM Cloud ni con la red de servicios de IBM Cloud, que ocupa `10.0.0.0/14`, `10.198.0.0/15` y `10.200.0.0/14`.  

 * No se permiten los siguientes rangos en el sistema Federal y los servidores IBM los rechazarán: `169.254.0.0/16`, `224.0.0.0/4`.

**Recomendaciones, valores predeterminados y límites:**

 * Se da soporte al tunelado (es decir, GRE) y se recomienda si el solapamiento de IP se convierte en un problema.
 * Los valores predeterminados del temporizador BGP son `Keepalive:30`, `Holdtime:60.`
 * La autenticación no está habilitada de forma predeterminada.
 * BGP BFD no está habilitado de forma predeterminada.
 * El límite en el máximo de prefijos recibidos (del cliente o del proveedor) es de 200 por VRF.

## Redundancia y diversidad

IBM Cloud Direct Link proporciona diversidad y los clientes son responsables de aplicar la redundancia mediante esquemas BGP.

Si selecciona ECMP para la redundancia, ambas sesiones BGP deberán existir en el mismo XCR, lo que significa que renuncia a la diversidad del direccionador y se expone a riesgos en caso de que el direccionador fallara. Gana una redundancia de 3 capas pero pierde diversidad de direccionador.

## Más información sobre el uso de VRF

Todas las cuentas que utilizan la solución IBM Cloud Direct Link deben migrar a un VRF. Al utilizar VRF, los clientes anuncian las rutas disponibles a sus redes remotas autodefinidas. Tenga en cuenta que esta configuración no permite utilizar las direcciones de IP autodefinidas en la red de {{site.data.keyword.BluSoftlayer_notm}}.

La migración a un VRF se realiza durante el proceso de configuración. Requiere una ventana de parada corta (hasta 30 minutos para cuentas grandes con varias VLAN/ubicaciones), durante la cual las VLAN de red de fondo perderán la conectividad mutua mientras se mueven al VRF. La migración de VRF está planificada con el ingeniero de implementación.

Tenga en cuenta que VRF elimina la opción "VLAN Spanning" para su cuenta, incluidas las capacidades de expansión de VLAN de cuenta a cuenta, porque todas las VLAN pueden comunicarse, a menos que se introduzca un Dispositivo de pasarela para gestionar el tráfico. VRF también limita la posibilidad de utilizar servicios VPN de {{site.data.keyword.BluSoftlayer_notm}}, porque no es compatible con los servicios de SSL, PPTP, e IPSec VPN de {{site.data.keyword.BluSoftlayer_notm}}.   

Una alternativa es utilizar la oferta IBM Cloud Direct Link para gestionar los servidores o ejecutar su propia solución de VPN (por ejemplo, Vyatta), que puede configurarse con distintos tipos de VPN. Después de migrar a un VRF, SSL VPN normalmente funciona cuando se realiza una conexión VPN en la ubicación del mismo centro de datos en la que se ejecuta una máquina virtual de cálculo, pero no permite el acceso global.

## Uso de BYOIP y NAT con Direct Link
IBM Cloud Direct Link no ofrece BYOIP en la red privada. Por lo tanto, el tráfico con una dirección IP de destino que no haya asignado {{site.data.keyword.BluSoftlayer_notm}} se descartará. Sin embargo, los clientes pueden encapsular tráfico entre la red remota y su red de {{site.data.keyword.BluSoftlayer_notm}} utilizando GRE, IPSec, o VXLAN.  

Generalmente, el entorno BYOIP se implementa en el ámbito de una Pasarela de red (Vyatta) o un despliegue de VMWare NSX. Esta configuración permite a los clientes utilizar cualquier espacio de IP deseable en el lado de {{site.data.keyword.BluSoftlayer_notm}}, y direccionar de nuevo a través del túnel a la red remota. Tenga en cuenta que esta configuración debe estar gestionada y soportada por el cliente, independiente de {{site.data.keyword.BluSoftlayer_notm}}. Además, esta configuración puede romper la conectividad a la red de servicios de {{site.data.keyword.BluSoftlayer_notm}} si el cliente asigna un bloque 10.x.x.x que {{site.data.keyword.BluSoftlayer_notm}} tenga en uso para los servicios. 

Esta solución también requiere que cada host que necesite conectividad a la red de servicios de {{site.data.keyword.BluSoftlayer_notm}} y a la red remota debe tener 2 direcciones IP asignadas: una debe estar asignada desde el bloque de IBM 10.x.x.x y otra desde el bloque de red remota. Las rutas estáticas deben establecerse en el host, para asegurarse de que el tráfico se direcciona adecuadamente. No se podrá asignar espacio de IP directamente en los hosts de {{site.data.keyword.BluSoftlayer_notm}} (BYOIP) y tenerlo direccionable en la red de {{site.data.keyword.BluSoftlayer_notm}} de forma inherente. La única forma de implementar esta capacidad es como se resaltó anteriormente, pero no está soportado por {{site.data.keyword.BluSoftlayer_notm}}.

Como alternativa, los clientes suelen asignar un bloque de red remoto para su uso en una tabla NAT configurada en su direccionador de extremo remoto. Esta configuración permite a los clientes limitar los cambios necesarios para ambas redes, mientras que sigue convirtiendo tráfico a un espacio de direcciones de red compatible con las dos redes.


