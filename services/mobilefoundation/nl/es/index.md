---

copyright:
  years: 2016
lastupdated:  "2016-11-16"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Iniciación a {{site.data.keyword.mobilefoundation_short}}
{: #gettingstartedtemplate}

{{site.data.keyword.mobilefoundation_long}} acelera la configuración de un entorno de {{site.data.keyword.mfp_full}} desde el cual puede desarrollar, probar y operar aplicaciones móviles de empresa. {{site.data.keyword.mobilefoundation_short}} está disponible bajo dos de servicio distintos: Developer y Professional 1 Application.
{:shortdesc}

<!-- The Professional 1 Application plan allows the {{site.data.keyword.mobilefoundation_short}} server to be deployed on a scalable container group.--> Utilizando el plan Professional 1 Application se puede gestionar una sola aplicación incorporada en una o todas las plataformas operativas soportadas como Android, iOS, Windows o Mobile Web. El plan Developer <!-- does not support {{site.data.keyword.mobilefoundation_short}} deployment on a container group with more than 1 node. This plan --> está pensado para entornos de desarrollo y pruebas.

## Iniciación al plan {{site.data.keyword.mobilefoundation_short}}: Developer

Después de crear una instancia de {{site.data.keyword.mobilefoundation_short}}: Developer, puede empezar a crear el canal móvil en tan solo unas pulsaciones.

*	Para crear una instancia de servidor de {{site.data.keyword.mobilefirst_notm}} con la configuración predeterminada, pulse **Iniciar servidor básico**.

  `La instancia de servidor básico incluye un nodo y 1 GB de memoria.`

* Para crear una instancia de servidor de {{site.data.keyword.mobilefirst_notm}} con configuración avanzada para la topología, seguridad y otros tipos de configuración del servidor, pulse **Iniciar servidor con configuración avanzada**. Consulte [Ajuste de la configuración avanzada](c_using_mfs_p1.html#using_mfs_advanced_p1), para obtener más información.

## Iniciación al plan {{site.data.keyword.mobilefoundation_short}}: Professional 1 Application

Después de crear una instancia del servicio {{site.data.keyword.mobilefoundation_short}}: Professional 1 Application, puede empezar a crear el canal móvil realizando los pasos siguientes.

1.  Conéctese a un servicio {{site.data.keyword.dashdbshort}}: Enterprise Transactional en {{site.data.keyword.Bluemix_notm}}.

    1.  Seleccione la `Organización` de {{site.data.keyword.Bluemix_notm}} donde existe la instancia del servicio {{site.data.keyword.dashdbshort_notm}}.

    + Seleccione el `Espacio` de {{site.data.keyword.Bluemix_notm}} donde existe la instancia del servicio {{site.data.keyword.dashdbshort_notm}}, en la lista de espacios disponible en la `Organización` seleccionada.

    + Seleccione el `Nombre de servicio` y las `Credenciales` de {{site.data.keyword.dashdbshort_notm}} para conectarse con la instancia de servicio {{site.data.keyword.dashdbshort_notm}} existente.

    + Pruebe la conexión con la instancia del servicio {{site.data.keyword.dashdbshort_notm}}: Enterprise Transactional seleccionada pulsando **Probar conexión**.

    + Pulse **Añadir**, seguido de **Continuar** en la ventana emergente que le solicita información sobre el servicio de {{site.data.keyword.dashdbshort_notm}} seleccionado. Esta acción crea las tablas necesarias en la instancia de servicio de base de datos de {{site.data.keyword.dashdbshort_notm}} configurada.

    **Nota:** Después de añadir una conexión {{site.data.keyword.dashdbshort_notm}} a la instancia {{site.data.keyword.mobilefoundation_short}} no podrá cambiarla.

2.  Cree e inicie el servidor.

    * Para crear una instancia de servidor de {{site.data.keyword.mobilefirst_notm}} con la configuración predeterminada, pulse **Iniciar servidor básico**.

      `La instancia de servidor básico incluye un nodo y 1 GB de memoria.`

    * Para crear una instancia de servidor de {{site.data.keyword.mobilefirst_notm}} con configuración avanzada para la topología, seguridad y otros tipos de configuración del servidor, pulse **Iniciar servidor con configuración avanzada**. Consulte [Ajuste de la configuración avanzada](c_using_mfs_p2.html#using_mfs_advanced_p2), para obtener más información.

Vaya a [Utilización del servicio Mobile Foundation para configurar el servidor de MobileFirst<!-- on IBM Containers-->](https://mobilefirstplatform.ibmcloud.com/tutorials/en/foundation/8.0/bluemix/using-mobile-foundation/) para obtener más información sobre la iniciación a {{site.data.keyword.mobilefoundation_short}}.

##  Limitaciones conocidas

* La IU del servicio {{site.data.keyword.mobilefoundation_short}} no utiliza el patrón específico del entorno local seleccionado por el usuario para mostrar números.


# Enlaces relacionados
{: #rellinks}

## Enlaces relacionados
{: #general}

*	[Documentación del producto de IBM MobileFirst Platform Foundation V8.0.0](https://www.ibm.com/support/knowledgecenter/SSHS8R_8.0.0/wl_welcome.html){: new_window}
*	[IBM MobileFirst Platform Developer Center](https://mobilefirstplatform.ibmcloud.com){: new_window}
