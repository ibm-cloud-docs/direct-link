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

# Visión general de los precios de la competencia
{: #competitive-pricing-overview}

Las empresas eligen utilizar una interconexión de nube privada, como {{site.data.keyword.cloud}} Direct Link, AWS Direct Connect, Google Cloud Interconnect y Microsoft Azure ExpressRoute, por muchas razones, que incluyen el rendimiento de red superior, los requisitos de seguridad y privacidad y la reducción de los costes de ancho de banda. Aunque su empresa puede adoptar una arquitectura de red de interconexión de nube privada debido a las ventajas en cuanto a rendimiento y seguridad, la reducción asociada de los costes de red es una métrica que favorece claramente a IBM Cloud Direct Link en muchos casos de uso. 

## ¿Por qué elegir IBM Direct Link?
{: #why-choose-ibm-cloud-direct-link}

Las tasas estándares de IBM para Direct Link reflejan un valor significativo para los clientes que utilizan los recursos de nube de forma activa. Este hecho se confirma en el cálculo de TCO (coste total de propiedad) correspondiente a Direct Link en comparación con la competencia.

Actualmente, una conexión dedicada de Direct Link de 10 Gbps tiene un coste de 4.999 dólares en América del Norte. Esta oferta garantiza una entrada y salida ilimitadas a los recursos de IBM Cloud a través de la conexión. Direct Link no dispone de opción de medición.

En las siguientes comparaciones se refleja el punto de inflexión frente a los principales competidores. En la tabla del final de este artículo se muestra un resumen detallado de esta comparación de precios, por región geográfica.

## AWS
{: #aws}

AWS (al igual que Google y Microsoft) dispone de una oferta de medición que supone una entrada de bajo coste, pero precios con variaciones significativas en cuanto a salida.
* El precio de AWS a 10 Gbps se compone de un cargo mensual recurrente (MRC) de horas de puerto de 1.620 dólares más una tasa de transferencia de 0,02 dólares/GB para la salida (en América del Norte).
* Para establecer una comparación con IBM Cloud Direct Link Dedicated, una conexión de AWS Direct Connect a 10 Gbps con un 5% de uso (o 170 TB) de salida durante un mes costaría al cliente 5.020 dólares, frente a los 4.999 dólares que costaría una conexión Direct Link a 10 Gbps. En el caso de que la salida de datos superara el 5% (o 170 TB) en un mes, saldría más rentable el modelo de precios de tasa plana de Direct Link.
* Si el cliente de AWS usara un 50% (o 1,7 PB) de salida durante un mes, le costaría 35.620 dólares, frente a los 4.999 dólares que le costaría una conexión Direct Link a 10 Gbps.

## Google
{: #google}

Google (al igual que AWS y Microsoft) dispone de una oferta de medición que supone una entrada de bajo coste, pero precios con variaciones significativas en cuanto a salida.

* El precio de Google a 10 Gbps es de un cargo mensual recurrente (MRC) de 1.750 dólares más una tasa de transferencia de 0,02 dólares/GB para la salida (en América del Norte).
* Para establecer una comparación con IBM Cloud Direct Link Dedicated, un puerto de Google Cloud (GCP) a 10 Gbps con un 5% de uso (170 TB) de salida durante un mes costaría al cliente 5.172 dólares, frente a los 4.999 dólares que costaría una conexión Direct Link a 10 Gbps. 
* En el caso de que la salida de datos superara el 5% (o 170 TB) en un mes, saldría más rentable el modelo de precios de tasa plana de Direct Link.
* Si el cliente de Google usara un 50% (o 1,7 PB) de salida durante un mes, le costaría 35.772 dólares, frente a los 4.999 dólares que le costaría una conexión Direct Link a 10 Gbps.

## Microsoft
{: #microsoft}

Microsoft (al igual que Google y AWS) dispone de una oferta de medición que supone una entrada de bajo coste, pero precios con variaciones significativas en cuanto a salida. Microsoft también ofrece una tabla de precios sin límite. Ambas opciones se comparan en las secciones siguientes.

### Con medición
{: #metered}

* El precio a 10 Gbps de Microsoft Azure consiste en una tarifa de puerto (MRC de 5.000 dólares) más una tasa de transferencia de 0,02 dólares/GB para la salida (en América del Norte). Ya desde el principio, CUALQUIER transferencia de salida sale mucho más cara que con IBM Cloud Direct Link!!!
* Para establecer una comparación con IBM Cloud Direct Link Dedicated, un puerto de Microsoft Azure Express Route a 10 Gbps con un 5% de uso (o 170 TB) de salida durante un mes costaría al cliente 8.400 dólares, frente a los 4.999 dólares que costaría una conexión Direct Link a 10 Gbps. 
* En el caso de que la salida de datos superara 1 TB en un mes, saldría más rentable el modelo de precios de tasa plana de Direct Link.
* Si el cliente de Microsoft Azure usara un 50% (o 1,7 PB) de salida durante un mes, le costaría 47.500 dólares, frente a los 4.999 dólares que le costaría una conexión Direct Link a 10 Gbps.


### Sin medición 
{: #unmetered}

* El precio de Microsoft Azure a 10 Gbps consta de una tasa de puerto con un MRC de 51.000 dólares para disponer de entrada y salida ilimitada.

* Para establecer una comparación con IBM Cloud Direct Link Dedicated, el coste mensual asciende a 51.000 dólares, frente a los 4.999 dólares que cuesta una conexión Direct Link a 10 Gbps. 

## Tabla de resumen
{: #summary-table}

Desplácese horizontalmente según sea necesario para ver las 5 columnas de la comparación.

**Notas:**
* **La información de la tabla siguiente se ha obtenido de sitios web públicos de estas compañías.**
* **Se utiliza un tamaño de conexión de 10 Gbps para comparar los precios.**
* **El uso se basa en 5 Gbps sostenidos o 1,7 PB de transferencia de datos al mes.**


| Región | IBM ilimitado | Azure ilimitado | Azure con medición | AWS con medición (dentro de la región) |
|-----|-----|-----|-----|-----|
| EE. UU. | 4.999 $ | 51.300 $ | 47.500 $ | 35.620 $ |
| TOR/MON/AMS | 5.149 $ | 51.300 $ | 47.500 $ | 35.620 $ |
| LON/OSL/STO/MEX | 5.349 $ | 51.300 $ | 47.500 $ | 35.620 $ |
| PAR/FRA/MIL | 5.499 $ | 51.300 $ | 47.500 $ | 35.620 $ |
| SEO | 5.499 $ | 51.300 $ | 90.000 $ | 73.020 $ |
| SNG/HKG | 5.699 $ | 82.000 $ | 90.000 $ | 73.020 $ |
| TOK | 5.999 $ |82.000 $ | 90.000 $ | 73.020 $ |
| MEL/SYD | 5.999 $ |82.000 $ | 90.000 $ | 73.020 $ |
| CHE | 5.999 $ |82.000 $ | 90.000 $ | 78.120 $ |
| SAO | 5.999 $ |82.000 $ | 242.350 $ | 188.620 $ |


