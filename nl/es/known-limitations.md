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

# Limitaciones conocidas
{: #known-limitations}

En primer lugar, esta sección cubre las limitaciones que se aplican a las tres ofertas de {{site.data.keyword.cloud}} Direct Link, y luego detalla algunas limitaciones de cada oferta individualmente.

## Limitaciones generales de IBM Cloud Direct Link
 * Cada conexión de IBM Cloud Direct Link requiere una solicitud exclusiva. Si necesita varias conexiones, abra una solicitud de IBM Cloud Direct Link para cada conexión.
 * La red de servicios de {{site.data.keyword.BluSoftlayer_notm}} no está accesible directamente desde las redes remotas.
 * {{site.data.keyword.BluSoftlayer_notm}} no permitirá a los clientes transportar tráfico entre sus sitios remotos a través de la red troncal de {{site.data.keyword.BluSoftlayer_notm}}. El producto IBM Cloud Direct Link está pensado para permitir que las redes remotas se comuniquen en privado con su infraestructura de {{site.data.keyword.BluSoftlayer_notm}}.
 * IBM Cloud Direct Link requiere que utilice una instancia de VRF (Virtual Routing and Forwarding).
 * VRF no es totalmente compatible con los servicios de SSL, PPTP, e IPSec VPN de {{site.data.keyword.BluSoftlayer_notm}}.
 * VRF no es compatible con la expansión de VLAN de cuenta a cuenta de {{site.data.keyword.BluSoftlayer_notm}}.
 * IBM Cloud Direct Link requiere BGP para establecer las rutas a una red remota del cliente.
 * Los cambios en la infraestructura de IBM Cloud Direct Link se deben realizar entre las 8:00 y las 17:00, del huso horario de EE. UU. Central.
 
## Limitaciones generales de IBM Cloud Direct Link Exchange y Direct Link Connect
 * Los clientes son responsables de los gastos asociados con alcanzar el POP desde una red remota y cualquier gasto efectuado con el proveedor de Cloud Exchange.
 * {{site.data.keyword.BluSoftlayer_notm}} no coubicará ningún equipo del cliente en los POP de nuestra red. Los clientes deben trabajar con su proveedor para determinar si necesitan coubicar cualquier equipamiento en el centro en el que existe el POP de red de {{site.data.keyword.BluSoftlayer_notm}}.
 * La disponibilidad de Direct Link Cloud Exchange varía entre ubicaciones. Los clientes pueden ponerse en contacto con su gestor de cuentas de IBM Cloud para confirmar la disponibilidad actual o futura.
 
## Limitaciones de IBM Cloud Direct Link Dedicated
 * Las tarifas de {{site.data.keyword.BluSoftlayer_notm}} para IBM Cloud Direct Link Dedicated cubren el coste de la terminación del puerto en la infraestructura de {{site.data.keyword.BluSoftlayer_notm}}. Los clientes son responsables de los gastos asociados con llegar al PoP desde una red remota y cualquier interconexión necesarias dentro del recurso de PoP.  {{site.data.keyword.BluSoftlayer_notm}} no pedirá una interconexión en nombre de ningún cliente.
 * {{site.data.keyword.BluSoftlayer_notm}} no coubicará ningún equipo del cliente en los POP de nuestra red. Los clientes deben trabajar con su proveedor para determinar si necesitan coubicar cualquier equipamiento en el centro en el que existe el POP de red de {{site.data.keyword.BluSoftlayer_notm}}.

## Limitaciones de IBM Cloud Direct Link Dedicated Hosting
 * IBM Cloud Direct Link Dedicated Hosting requiere un contrato específico entre {{site.data.keyword.BluSoftlayer_notm}} y el cliente. Este contrato describe los términos y condiciones para el producto, el precio para el entorno de colocación y el compromiso de términos para los servicios. Es necesario un contrato de 6, 9 o 12 meses.
 * La conectividad del proveedor está limitada a los proveedores en red del centro de datos seleccionado.
