---

copyright:
  years: 2017, 2018
lastupdated: "2018-05-22"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Utilización de IBM Cloud Direct Link para conectar con IBM Cloud Object Storage

En este documento se describe cómo configurar IBM Cloud Direct Link de forma que tenga acceso a IBM Cloud Object Storage (COS). Aunque los métodos aquí descritos se han diseñado y probado con COS, pueden funcionar para algunos otros servicios de IBM Cloud.

De acuerdo con la política actual, IBM Cloud Direct Link deniega el acceso a los puntos finales de servicio privado de IBM Cloud, incluidos los que utiliza IBM Cloud Object Storage (COS). La técnica que se describe en este documento se basa en el acceso indirecto a COS a través de servidores alojados en la cuenta de IBM Cloud del cliente. Después de la configuración, el servidor de cada cliente puede reenviar el tráfico bidireccionalmente entre los puntos finales de servicio privados de IBM Cloud y sus redes remotas conectadas por Direct Link.

## ¿Qué es IBM Cloud Object Storage (COS)?

IBM Cloud Object Storage (COS) es una plataforma de escala web que almacena datos no estructurados. Proporciona fiabilidad, seguridad, disponibilidad y recuperación tras desastre sin réplica manual.

La información almacenada en IBM Cloud Object Storage está cifrada y distribuida entre varias ubicaciones geográficas. Se puede acceder a esta información a través de una implementación de la API S3. Este servicio utiliza las tecnologías de almacenamiento distribuido que proporciona el servicio IBM Cloud Object Storage.

IBM COS está disponible en tres configuraciones: **Cross Region (varias regiones)**, **Regional** y **Single Site (un solo sitio)**.

 * El servicio Cross Region proporciona una mayor durabilidad y disponibilidad que el uso de una sola región, pero a costa de una latencia ligeramente superior. Este servicio está disponible actualmente en Estados Unidos y en la UE.
 
 * El servicio Regional proporciona lo contrario: distribuye los objetos en varias zonas de disponibilidad dentro de una sola región. Si no se puede acceder a una determinada región o zona de disponibilidad, el almacén de objetos continúa funcionando correctamente. Los cambios que falten se aplicarán cuando el centro de datos inaccesible vuelva a estar en línea.
  
 * El servicio Single Site ofrece un acceso asequible a Cloud Object Storage en un centro de datos seleccionado.

### Puntos finales privados y públicos de COS
Los puntos finales son URL que las aplicaciones utilizan para emitir mandatos de COS y para intercambiar datos con COS. Cada punto final utiliza la misma interfaz de programación de aplicaciones (API) para interactuar con COS.

Los servidores suministrados en IBM Cloud utilizan puntos finales de API para servicios, incluido COS. Los puntos finales privados proporcionan a los servidores IBM Cloud de los clientes conexiones directas de alta velocidad a servicios sin costes adicionales de ancho de banda.

Los puntos finales públicos de COS proporcionan a los clientes de IBM Cloud acceso a los mismos datos de COS a los que se puede acceder desde dentro de IBM Cloud, pero los puntos finales públicos permiten el acceso desde cualquier ubicación equipada con Internet.

Hay que tener en cuenta estos dos puntos en cuanto a los puntos finales públicos de COS:
 * El uso de puntos finales públicos puede incurrir en costes de ancho de banda además de los cargos de uso impuestos por el servicio COS. 
 * Aunque todos los datos se cifran durante la transferencia, es posible que los clientes tengan restricciones o dudas en cuanto a privacidad relacionadas con los datos que se aplican a través de Internet.

## ¿Qué es IBM Cloud Direct Link?
IBM Cloud Direct Link es una suite de productos que proporciona a los clientes la posibilidad de crear conexiones seguras y privadas entre sus entornos de red remota y sus despliegues de IBM Cloud. Los datos que se intercambian mediante Direct Link nunca se exponen a Internet.

## Utilización de Cloud Object Storage (COS) sobre IBM Cloud Direct Link
Los ingenieros de IBM han desarrollado un método que permite a un cliente de IBM Cloud que adquiere COS y Direct Link establecer conexiones remotas con puntos finales privados de COS. Este tipo de conexión amplía las ventajas de los puntos finales de servicio privados, ya que pueden ser utilizados por sistemas cliente externos a las instalaciones de IBM Cloud.
 
Encontrará diagramas y descripciones de esta solución en las siguientes secciones.

### Proxy inverso

**Premisa básica: los clientes remotos pasan solicitudes a COS, incluidas credenciales seguras, a través de un servidor privado**

![reverse=proxy](images/reverse-proxy.png)

Las solicitudes de COS HTTPS (HTTP seguro) se inician desde un cliente en un sitio remoto. Se transmiten de forma segura a través de IBM Cloud Direct Link, y se destinan a uno de los _servidores proxy inversos_ de un clúster desplegados en una cuenta de IBM Cloud del cliente. Desde ahí, las solicitudes se pasan a un punto final privado de COS, se procesan y, a continuación, se devuelven los resultados al cliente remoto que ha realizado la llamada.

Cualquier código de cliente de ejemplo que funcione con COS también debería funcionar a través de un servidor _proxy inverso_. El único ajuste necesario es que, en lugar de utilizar como destino uno de los URL de punto final privados de COS publicados por IBM, el destino del cliente es la dirección IP o el URL del servidor proxy inverso.

#### Instalación del proxy inverso Nginx
**NginX** es un servidor web de código abierto rápido, compacto y maduro que destaca en tareas especializadas, que incluyen el rol de servidor _proxy inverso_ mencionado anteriormente.

Las instrucciones y la información de configuración que se muestran a continuación para configurar un servidor proxy inverso NginX pueden funcionar una vez que las haya adaptado a su entorno. Si se atasca o necesita más información, consulte la parte sobre proxy inverso de la [documentación de Nginx](https://docs.nginx.com/nginx/admin-guide/web-server/reverse-proxy/) o busque [stackoverflow](http://stackoverflow.com) para ver ejemplos.

1. Suministre sus servidores VSI o nativos con una compilación mínima **RHEL** o **CentOS** Linux (recomendado)
2. Para cada VSI, habilite las siguientes reglas de grupo de seguridad en la interfaz pública: `allow_http`, `allow_https`, `allow_outbound`, `allow_ssh`
3. Para cada VSI, habilite las reglas `allow_all` y `allow_outbound` en la interfaz privada; seleccione **Guardar**
4. Mediante **PuTTY** en Windows o el programa de terminal de su escritorio, ejecute `ssh` en el nuevo servidor como root
5. Actualice el SO del sistema operativo (`yum update`)
6. Instale el repositorio de EPEL (`yum install epel-release`)
7. Instale NginX (`yum install nginx`)
8. Inicie NginX (`nginx`) y abra la dirección IP del servidor en un navegador.
9. La ubicación predeterminada de `nginx.conf` es `/etc/nginx`. Cree una copia segura.
10. Mueva el archivo de configuración `nginx.conf` de ejemplo, que se muestra a continuación, a `/etc/nginx`
11. Adquiera certificados SSL a través del portal de IBM Cloud o ejecute el mandato `yum install easy-rsa` y consulte sus documentos en línea favoritos para obtener consejos sobre la creación de certificados autofirmados.
12. Añada la información de certificado al archivo de configuración, `nginx.conf`
13. Pruebe la configuración de NginX modificada mediante el mandato `nginx -t`
14. Si pasa la prueba, reinicie `nginx` con el mandato `nginx -s quit; sleep 3; nginx`
15. Ahora el cliente debería poder enviar solicitudes COS a las direcciones IP o los URL del servidor NginX (proxy)

#### Notas:

* En la solución se presupone que Direct Link se ha solicitado y desplegado correctamente, aunque se puede probar sin el mismo.
* Se puede utilizar memoria o memoria caché de disco opcional con `proxy_cache`
* Es posible que se necesite un valor de `proxy_read_timeout` superior para transferencias de archivos grandes.
* Utilice `keepalive` o Pacemaker para conseguir alta disponibilidad (migración tras error automática)

#### Archivo de configuración: `nginx.conf`

El archivo de configuración de ejemplo se muestra en la siguiente sección. Puede copiarlo y pegarlo.

```
user nginx;
worker_processes auto;
error_log /var/log/nginx/error.log;
pid /run/nginx.pid;

events {
    worker_connections 1024;
}

http {
    log_format  main  '$remote_addr - $remote_user [$time_local] "$request" '
                      '$status $body_bytes_sent "$http_referer" '
                      '"$http_user_agent" "$http_x_forwarded_for"';

    access_log  /var/log/nginx/access.log  main;

    sendfile            on;
    tcp_nopush          on;
    tcp_nodelay         on;
    keepalive_timeout   5;
    types_hash_max_size 2048;

    include             /etc/nginx/mime.types;
    default_type        application/octet-stream;
    ssl_session_cache shared:SSL:1m;
    ssl_session_timeout  10m;
    ssl_ciphers HIGH:!aNULL:!MD5;
    ssl_prefer_server_ciphers on;
    proxy_http_version 1.1;
    proxy_buffering off;
    proxy_intercept_errors on;

    # IBM COS Endpoints
    # https://console.bluemix.net/docs/infrastructure/cloud-object-storage-infrastructure/endpoints.html#select-regions-and-endpoints
    # US
    server {
        listen       443 ssl http2;
        server_name  us-cos.myibmcloud.com;
        ssl_certificate "/etc/pki/tls/certs/star.myibmcloud.com.pem";
        ssl_certificate_key "/etc/pki/tls/private/star.myibmcloud.com.key";
        location / {
            proxy_set_header Host $server_name;
            proxy_pass https://s3-api.us-geo.objectstorage.service.networklayer.com;
        }
    }

    # Dallas
    server {
        listen       443 ssl http2;
        server_name  dal-cos.myibmcloud.com;
        ssl_certificate "/etc/pki/tls/certs/star.myibmcloud.com.pem";
        ssl_certificate_key "/etc/pki/tls/private/star.myibmcloud.com.key";
        location / {
            proxy_set_header Host $server_name;
            proxy_pass https://s3-api.dal-us-geo.objectstorage.service.networklayer.com;
        }
    }
}
```

Consulte [Puntos finales de COS](https://console.bluemix.net/docs/infrastructure/cloud-object-storage-infrastructure/endpoints.html#select-regions-and-endpoints) para ver una lista de puntos finales privados que puede utilizar en las entradas `proxy_pass` anteriores.

#### Sugerencias:

 * Para aumentar el escalado y la capacidad de recuperación, despliegue varios servidores proxy asociados a distintos puntos finales.
 * Utilice DNS en rueda en la parte del cliente para conseguir funciones rudimentarias de migración tras error y equilibrio de carga.
 * Los servidores proxy se pueden colocar detrás de un dispositivo direccionador virtual (VRA) por motivos de protección y registro centralizado.

## Gestión y suministro de prestaciones de IBM Cloud

Esta sección contiene enlaces rápidos a la documentación de algunas ofertas de IBM Cloud PaaS y SaaS con las que puede conectar mediante IBM Cloud Direct Link.

### Cómo suministrar servidores nativos

Para obtener instrucciones detalladas sobre cómo suministrar servidores nativos, consulte la publicación [Guide to Bare Metal Servers](https://console.bluemix.net/docs/bare-metal/about.html#getting-started-with-bare-metal-servers).

### Cómo suministrar un dispositivo direccionador virtual (VRA)

Para obtener instrucciones detalladas sobre cómo suministrar un VRA, consulte la publicación [VRA Getting Started Guide](https://console.bluemix.net/docs/infrastructure/virtual-router-appliance/getting-started.html#getting-started).

### Cómo suministrar IBM Cloud Object Storage (COS)

 * Para obtener instrucciones detalladas sobre cómo suministrar COS, consulte la publicación [Cloud Object Storage Guide](https://console.bluemix.net/catalog/services/cloud-object-storage).

 * Utilice uno de los puntos finales privados (mostrados anteriormente) para crear una interfaz con el contenedor o cualquier objeto de su cuenta de COS suministrada.
