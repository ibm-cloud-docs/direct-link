---
copyright:
  years: 2018, 2019
lastupdated: "2019-04-02"

keywords: Intercloud, Frankfurt, PoPs, Connect, Exchange, Chennai, Equinix, Megaport, Kinx, diversity, Bluefringe, CenturyLink, BT, Sao Paulo, Tokyo, Japan, PCCW, Colt, blog, service provider, partner, Telia, Internexion, Packet Fabric, Global Routing, expanded, market

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:important: .important}

# Anuncio: el cambio en la política del servicio Global Routing comienza el 1 de julio

A partir del 1 de julio de 2019, cambia la política del servicio IBM Direct Link Global Routing
{: important}

Para mejorar la experiencia del cliente y aumentar su valor, estamos mejorando el servicio IBM Direct Link Global Routing. Las principales mejoras incluyen:

* **Ampliación de mercados locales:** estamos implementando alineando los sitios a los que se pueden conectar los clientes con sus mercados locales. Estamos alineando cada sitio de PoP en la red de IBM Cloud para permitir que los clientes que se conectan a IBM Cloud en nuestros sitios de PoP se conecten a los recursos de uno o varios de nuestros centros de datos ubicados en todo el mundo.

* **Nuevo modelo de precios:** para ajustar mejor los precios a las velocidades de conexión seleccionadas, estamos cambiando el modelo de precios de nuestro servicio IBM Direct Link Global Routing.

* **Tráfico ilimitado de Direct Link:** estamos eliminando los cargos por excedente de tráfico de red para los clientes que tienen direccionamiento local o global para el tráfico de red privada de Direct Link entre los PoP de IBM Cloud y los centros de datos a nivel global.

## Visión general del servicio IBM Cloud Direct Link Global Routing
{: #ibm-cloud-direct-link-global-routing-overview}

Todas las ofertas actuales de Direct Link incluyen direccionamiento local sin tasas adicionales. Este servicio incluye el acceso a los centros de datos del mercado local en el que se encuentra la conexión de Direct Link. Ofrece tráfico ilimitado de entrada y de salida entre las conexiones privadas de Direct Link y los recursos de IBM Cloud de la cuenta del cliente. Con esta opción de direccionamiento local, el tráfico de Direct Link se restringe a los servicios que suministra este mercado local.

Para direccionar el tráfico de red fuera del mercado local al que está conectado Direct Link (PoP o centro de datos), debe añadir la opción Global Routing, que amplía el acceso para incluir todos los centros de datos de IBM Cloud de todo el mundo.

Global Routing se aplica a servicios individuales de Direct Link. Global Routing no se aplica mediante agregación. Se debe especificar en cada servicio de Direct Link que desee conectar fuera de un mercado determinado.

## Mercados locales ampliados de IBM Direct Link
{: #announce-expanded-ibm-direct-link-local-markets}

Estamos ampliando los mercados locales de Direct Link para proporcionar más opciones de direccionamiento local a nuestros clientes en todo el mundo. A continuación encontrará las nuevas asignaciones de mercados locales:

* El mercado local de Dallas ahora incluirá PoP en Denver, Houston y Chicago.
* El mercado local de Washington DC ahora incluirá PoP de Nueva York, Atlanta y Miami.
* El mercado local de San José ahora incluirá el PoP de Los Ángeles.
* El mercado local de Oslo ahora incluirá el PoP de Estocolmo.
* El mercado local de Sídney ahora incluirá el PoP de Perth.
* El mercado local de Hong Kong incluirá el PoP de Taipei cuando esté listo.
* El mercado local de Tokio incluirá el PoP de Osaka cuando esté listo.
* El mercado local de Chennai incluirá el PoP de Mumbai cuando esté listo.

Estos cambios se detallan en las tablas que encontrará en: https://cloud.ibm.com/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#expanded-ibm-direct-link-local-markets

## Modelo de precios de IBM Cloud Direct Link Global Routing
{: #announce-ibm-cloud-direct-link-global-routing-pricing-model}

Con todas las ofertas de IBM Cloud Direct Link, el direccionamiento de red dentro de un mercado local se ofrece de forma estándar. A partir del 1 de julio de 2019, los precios de la opción Global Routing se está alineando con la velocidad de conexión de la conexión de Direct Link. Esta alineación beneficiará a los clientes con cualquier velocidad de conexión disponible para las ofertas de Direct Link.

Encontrará los precios en https://cloud.ibm.com/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-global-routing-add-on

## Cargos por excedente de tráfico de red de IBM Cloud Direct Link Global Routing
{: #announce-ibm-cloud-direct-link-global-routing-network-transit-overage-charges}

Junto con este anuncio, retiramos los límites de tráfico de red y los cargos por excedente para los clientes con la opción Global Routing. Los precios anteriores incluían concesiones y cargos por excedente de tráfico en la red para el tráfico de salida procedente del mercado local del cliente. Los nuevos precios eliminan estos cargos de tráfico de red. A partir de este anuncio, el tráfico de entrada y de salida a través de las conexiones de Direct Link no incurrirá en cargos por excedente.

## Fecha de aplicación
{: #announce-effective-date}

Estos cambios entrarán en vigor el lunes, 1 de julio de 2019, y se aplicarán a todos los nuevos pedidos en el siguiente ciclo de facturación tras esta fecha.

Es importante tener en cuenta que con esta automatización actualizada, los circuitos de Direct Link que necesitan Global Routing deben actualizarse adecuadamente antes de esta fecha. Cualquier actualización o degradación de un servicio de Direct Link dará lugar a una automatización que verificará si está presente Global Routing. Si Global Routing no está presente, el tráfico a través de circuitos de Direct Link se restringirá a los mercados locales.

Se recomienda encarecidamente a los clientes que revisen su direccionamiento de IBM Cloud en los servicios de Direct Link y que abran incidencias para resolver el direccionamiento en los servicios de Direct Link existentes.
