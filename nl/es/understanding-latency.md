---
copyright:
  years: 1994, 2017, 2018, 2019
lastupdated: "2019-02-19"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Visión general de la latencia
{: #understanding-latency}

_Solución híbrida con {{site.data.keyword.cloud}} Direct Link: sus cargas de trabajo se ejecutarán más rápidamente y en todo el mundo_

IBM Cloud ofrece centros de datos con prestaciones de Direct Link en todo el mundo. Por lo tanto, puede contar con una latencia mínima cuando utilice Direct Link para crear su solución de nube híbrida enlazando su IBM Cloud a su infraestructura existente.

Tanto si tiene una tienda en línea, como si ejecuta soluciones de "big data" o tiene empleados distribuidos en una red con acceso a archivos en todo el mundo lo último que deseará oír es que una página tarda en cargarse en la web o que la transferencia de datos desde una base de datos es lenta, lo que podría quitarle una venta o reducir la productividad de sus empleados. Una velocidad baja puede deberse a la latencia de red, que es la medida de la velocidad con la que viajan los datos entre dos puntos conectados en Internet. Puede considerarlo como el intervalo de tiempo que se tarda en transportar un paquete de datos de un sitio a otro.

A nivel global, la latencia general de Internet puede variar significativamente en función de la distancia que deben viajar los datos físicamente, del número de veces que deben saltar los datos entre proveedores de servicio, del ancho de banda disponible durante el trayecto y de los otros datos que hacen el mismo recorrido, además de otras variables. IBM Cloud Direct Link ofrece una latencia determinista con mayor seguridad, relativa a Internet, para un conseguir un rendimiento predecible.


## Visión general de la latencia de red

Como práctica recomendada, cada proveedor de red desea ofrecer la latencia de red más baja al mayor número de clientes, y todos los clientes desean obtener la latencia más baja posible. Esta es la solución que todos desean.

En teoría, los datos pueden viajar a la velocidad de la luz a través de cables de red de fibra óptica, pero, por todas las razones mencionadas anteriormente, los datos suelen viajar más lentamente. Por ejemplo, si una determinada conexión de red ha alcanzado su capacidad de ancho de banda, los paquetes de datos se pueden colocar en cola temporalmente a la espera de que les llegue el turno de viajar por el trayecto elegido. Por poner otro ejemplo, si la red de un determinado proveedor de servicio selecciona una ruta de red que no es la óptima, los paquetes de datos pueden alejarse cientos o miles de kilómetros de su destino en el proceso de alcanzar su destino. Este tipo de retrasos son la causa de una latencia de red superior y de transferencias de datos más lentas.

Expresamos la latencia de red en milisegundos (es decir, en 1000 milisegundos por segundo). Unas pocas milésimas de segundo pueden no significar mucho en nuestro día a día, pero los milisegundos suelen convertirse en un factor decisivo cuando queremos navegar por la web o en nuestras transacciones comerciales. Por ejemplo, en el sector financiero, unos milisegundos pueden significar miles de millones de dólares de diferencia en las ganancias o la pérdida de transacciones comerciales diariamente.

## Enfoques comunes que minimizan la latencia de red

Dado que nuestro objetivo compartido consiste en minimizar la latencia, tiene sentido limitar el número de variables potenciales que pueden afectar a la velocidad de transferencia de los datos. Ningún proveedor puede conseguir un control completo sobre cómo viajan los datos a través de Internet, pero aquí exponemos algunas prácticas recomendadas para minimizar la latencia de red:

 * Distribuya los datos por todo el mundo: los clientes de distintas ubicaciones pueden extraer datos de la ubicación que esté geográficamente más cerca. Puesto que los datos están más cerca de los clientes, se manipulan menos veces. Cuando los datos tienen que viajar una distancia más corta, es menos probable que el direccionamiento cause un impacto significativo en el rendimiento.

 * Suministre servidores con puertos de red de alta capacidad: pueden transferirse volúmenes de datos enormes a través de un servidor cada segundo. Si los paquetes se retrasan debido a puertos saturados, transcurren milisegundos de tiempo, las páginas se cargan más lentamente, descienden las velocidades de descarga y aumenta la insatisfacción de los usuarios.

 * Comprenda cómo los proveedores redireccionan el tráfico: si tiene más información sobre cómo se transfieren los datos a clientes de todo el mundo, puede tomar mejores decisiones sobre dónde alojar sus datos.

## Cómo IBM Cloud minimiza la latencia de red

Para minimizar la latencia, IBM Cloud ha adoptado un enfoque único para crear su red. Todos nuestros centros de datos están conectados a puntos de presencia (PoP) en la red y todos nuestros puntos de presencia en la red están conectados entre sí a través de nuestra red troncal global. Puesto que mantenemos nuestra propia red troncal global, nuestro equipo de operaciones de red puede controlar las vías de acceso de red y las transferencias de datos de forma más precisa que si dependiéramos de otros proveedores para mover datos entre geografías.
 
Por ejemplo, si un cliente de IBM Cloud en Berlín desea ver un vídeo de gatos alojado en un servidor de IBM Cloud en Dallas, los paquetes de datos que conforman el vídeo de gatos se desplazarán a través de nuestra red troncal (que únicamente se utiliza para el tráfico de IBM Cloud) a Frankfurt, donde los paquetes se enviarán a uno de nuestros proveedores de servicios de red públicos de transporte o de servicio público, para llegar finalmente al usuario en Berlín. Y, lo que es aún mejor, si el cliente utiliza la función CDN de IBM Cloud, los paquetes se enviarán desde un servidor de extremo ubicado cerca del cliente, con lo que no hará falta enviarlos desde Dallas.

Sin una red troncal global, los paquetes de vídeo se envían a un proveedor de red pública de transición o de tránsito en Dallas, luego dicho proveedor direcciona los paquetes a través de su red o los envía a otro proveedor en un salto de red, y los paquetes finalmente retoman su camino a Alemania. Es muy posible que los paquetes puedan pasar de Dallas a Berlín con la misma latencia de red sin utilizar la red troncal global, pero sin esta existen más variables; la latencia total es mucho más difícil de garantizar o de predecir.

Además de utilizar nuestra propia red troncal global, IBM Cloud también segmenta el tráfico público, privado y de gestión en distintos puertos de red. Esto significa que los distintos tipos de tráfico se transfieren sin interferencias entre sí.

## Resumen: latencia de red

Los clientes desean sus datos tan rápido como los pueda entregar. El tiempo que tardan los datos en llegar a ellos a través de Internet se denomina latencia de red. Cuanto más control tenga sobre la vía de acceso de red de los datos, más coherente y baja puede ser la latencia de red.

* Con Direct Link, le ofrecemos el control sobre la vía de acceso por la que viajan sus datos, de modo que el trayecto de sus datos no se vea interrumpido ni bloqueado por otro tráfico.

* IBM Cloud ofrece proveedores de servicio líderes del sector, que proporcionan alto rendimiento, seguridad y capacidad de recuperación.

* En IBM Cloud, añadimos continuamente puntos de presencia (PoP) en la red en todo el mundo para acercar los datos de sus clientes a sus clientes, mejorando así la latencia y el rendimiento global para satisfacer las necesidades de sus cargas de trabajo de nube híbridas.

