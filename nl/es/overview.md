---

copyright:
  years: 2017, 2018
lastupdated: "2018-03-14"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Visión general de Características

Las ofertas de IBM Cloud Direct Link proporcionan conectividad desde un origen externo a una red privada de IBM Cloud del cliente. Direct Link puede considerarse como una alternativa a una solución VPN de sitio a sitio tradicional, diseñado para clientes que necesitan una conectividad más coherente y de mayor rendimiento entre una red remota y sus entornos de IBM Cloud. Hay disponibles cuatro tipos de conexiones:
 
 * **IBM Cloud Direct Link Exchange** permite a los clientes aprovechar un proveedor de Exchange para ofrecer conectividad a su IBM Cloud. Un proveedor de Exchange es un transportista o proveedor de red que ya está conectado a la red de IBM Cloud, utilizando enlaces multiarrendatario de alta capacidad. Los clientes pueden comprar normalmente un circuito virtual en este proveedor, proporcionando conectividad a un coste reducido, porque la conectividad física de {{site.data.keyword.BluSoftlayer_notm}} al proveedor de Exchange ya está en marcha, compartida entre otros clientes.
 
 * **IBM Cloud Direct Link Connect** permite a los proveedores optimizar una conexión mediante socios que poseen y operan una red basada en recursos. Con IBM Cloud Direct Link Connect, IBM y el socio se conectan con los clientes en las capas 2 y 3 mediante NNI duales de 10G de 2 capas.
 
 * **IBM Cloud Direct Link Dedicated** permite a los clientes terminar una conexión dedicada, individual y de fibra en su propia red privada de IBM Cloud.
 
 * **IBM Cloud Direct Link Dedicated Hosting** proporciona conectividad similar a IBM Cloud Direct Link Dedicated, pero el punto de conexión es adyacente a un centro de datos de {{site.data.keyword.BluSoftlayer_notm}}, que mejora la latencia para casos de uso de mayor rendimiento. IBM Cloud ofrece una variedad de servicios de coubicación personalizables con esta solución.
  
El servicio de IBM Cloud Direct Link es un servicio direccionado de 3 capas de OSI. Ofrece una conexión directa a la red troncal privada de {{site.data.keyword.BluSoftlayer_notm}}, con baja latencia y velocidades de hasta 10 Gbps.
Para una mayor flexibilidad para crear esta conectividad de 3 capas, IBM Cloud Direct Link permite a los clientes utilizar:
 * IP dual para los hosts remotos
 * NAT
 * Tunelado para BYOIP
