---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-02"

keywords: diversity, redundancy, schematics, deployment, configuration, global routing, ECMP, Dual XCRs, model

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Modelos de diversidad y redundancia en Direct Link
{: #models-for-diversity-and-redundancy-in-direct-link}

Este documento contiene una serie de esquemas relacionados con los problemas de redundancia y diversidad, que pueden ayudarle a encontrar un modelo para crear el despliegue de {{site.data.keyword.cloud}} Direct Link más adecuado que pueda satisfacer sus necesidades. Los esquemas están organizados por niveles ascendentes de complejidad y también de acuerdo a la oferta de Direct Link que ilustra cada uno. Direct Link no es un servicio inherentemente redundante en el direccionador de conexión cruzada (XCR); los clientes son los responsables de crear redundancia a través de sus esquemas de BGP (Border Gateway Protocol). 

## Sección 1: Configuraciones relativamente sencillas que consiguen diversidad
{: #section-1-diversity-models}

Las configuraciones que se muestran en este grupo se basan en el hecho de que todos los activos están ubicados en el mismo PoP y en el mismo mercado global.

**Figura 1: Direct Link Exchange con diversidad en el mismo PoP (no AZ)**

![Exchange con diversidad en el mismo PoP](/images/exchange-diversity-same-pop.png)

**Figura 2: Direct Link Connect con diversidad en el mismo PoP (no AZ)**

![Connect con diversidad en el mismo PoP](/images/connect-diversity-same-pop.png)

**Figura 3: Direct Link Dedicated con diversidad en el mismo PoP (no AZ)**

![Dedicated con diversidad en el mismo PoP](/images/dedicated-diversity-same-pop.png)

## Sección 2: Diversidad que incluye las opciones AZ y direccionamiento global
{: #section-2-diversity-models}

Las configuraciones que se muestran en este grupo ofrecen opciones para conectarse a través de zonas de disponibilidad y mercados locales.

### Parte A: Diversidad en una zona de disponibilidad local (AZ)
{: #section-2-part-a}

**Figura 4: Direct Link Exchange con diversidad en un AZ local (WDC, DAL, FRA, LON)**

![Exchange con diversidad en el AZ local](/images/exchange-diversity-local-az.png)

**Figura 5: Direct Link Connect con diversidad en un AZ local (WDC, DAL, FRA, LON)**

![Connect con diversidad en el AZ local](/images/connect-diversity-local-az.png)

**Figura 6: Direct Link Dedicated con diversidad en un AZ local (WDC, DAL, FRA, LON)**

![Dedicated con diversidad en el AZ local](/images/dedicated-diversity-local-az.png)

### Parte B: Diversidad en diferentes mercados locales, con direccionamiento global
{: #section-2-part-b}

**Figura 7: Direct Link Connect con diversidad y direccionamiento global**

![Connect con diversidad y direccionamiento global](/images/connect-diversity-global.png)

**Figura 8: Direct Link Exchange con diversidad y direccionamiento global**

![Exchange con diversidad y direccionamiento global](/images/exchange-diversity-global.png)

**Figura 9: Direct Link Dedicated con diversidad y direccionamiento global**

![Dedicated con diversidad y direccionamiento global](/images/dedicated-diversity-global.png)

## Más sobre ECMP
{: #more-about-ecmp}

ECMP es una característica de BGP. Algunos clientes nos han preguntado sobre el uso de ECMP como método para conseguir redundancia. Sin embargo, ECMP por sí solo no es suficiente. En esta sección se explica por qué.

**P: ¿Es ECMP el método adecuado para conseguir conexiones redundantes? ¿Qué alternativas existen?**

ECMP no está diseñado para crear conexiones redundantes, sino para equilibrar la carga sobre dos enlaces. Con ECMP en {{site.data.keyword.cloud_notm}}, ambas conexiones deben terminar en el mismo direccionador de interconexión (XCR) de IBM Cloud, lo que lo convierte en un punto único de anomalía. (Es decir, ECMP solo se puede suministrar como dos sesiones en el mismo XCR de {{site.data.keyword.cloud_notm}}.)

**Figura 10: Suministro de ECMP**

![Modelo de ECMP dedicado](/images/ecmp-without-diversity.png)

### Cómo lograr diversidad y redundancia
{: #how-to-achieve-diversity-and-redundancy}

Si busca alta disponibilidad (HA) o redundancia completa: configure dos enlaces en diferentes XCR en el mismo centro de datos (por ejemplo, DAL03). A continuación, realice la migración tras error según sea necesario utilizando configuraciones BGP.

**Figura 11: ECMP con XCR duales**

![Modelo de XCR dual de ECMP](/images/ecmp-with-diversity.png)
