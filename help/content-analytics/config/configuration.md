---
title: Configurar análisis de contenido
description: Información general sobre la configuración del análisis de contenido
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: 596e54a559bac69214e1de3ea37da6177f110b7a
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 2%

---

# Configurar análisis de contenido

>[!WARNING]
>
>Este artículo es una versión preliminar no oficial del borrador de una próxima versión final y forma parte de la documentación de Análisis de contenido. Todo el contenido está sujeto a cambios y no se puede derivar ninguna obligación legal de la versión actual de este artículo.
>

{{release-limited-testing}}

La configuración de Análisis de contenido consiste en los siguientes pasos:

![Configuración de análisis de contenido](../assets/aca-configuration.svg)

1. Utilice el asistente de [configuración guiada](guided.md) de Content Analytics para guiarle por todos los pasos necesarios para establecer los requisitos previos de una configuración de Content Analytics. Puede guardar las configuraciones y volver más tarde.
1. Una vez que se sienta cómodo con los valores de configuración, puede implementar la configuración. Esta implementación crea todos los artefactos necesarios en función de lo que haya configurado en el asistente. Se crean, actualizan o seleccionan los siguientes artefactos:
   * Análisis de Recorrido personalizado
      * Se ha seleccionado [una vista de datos](/help/data-views/data-views.md).
      * Se seleccionó una [conexión](/help/connections/overview.md), que se deriva automáticamente de la vista de datos seleccionada.
   * Experience Platform
      * La zona protegida está seleccionada, derivada automáticamente de la conexión. Los flujos de trabajo y servicios necesarios están habilitados en la zona protegida.
      * Los esquemas de análisis de contenido están seleccionados en la zona protegida. Si no está disponible, se crean los esquemas necesarios.
      * Conjuntos de datos de análisis de contenido seleccionados en la zona protegida. Si no está disponible, se crean los conjuntos de datos necesarios.
   * Recopilación de datos
      * Se crea un conjunto de datos y se configura un servicio de Experience Platform dentro del conjunto de datos para transmitir datos al conjunto de datos de evento de experiencia de Content Analytics.
      * Se crea una propiedad Tag con la extensión de Adobe Content Analytics configurada para la zona protegida, la secuencia de datos y otras opciones de configuración correctas del asistente de configuración.
1. Solo cuando publica manualmente la propiedad Etiqueta, el Análisis de contenido se implementa y activa de forma eficaz.
1. Solo puede realizar algunos cambios limitados en una configuración implementada mediante el asistente de [configuración guiada](guided.md). Por ejemplo, cambie la [vista de datos](/help/data-views/data-views.md).
1. Puede realizar otros cambios en una configuración implementada mediante la [extensión de Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) en la propiedad de etiquetas asociada.
1. Solo cuando vuelve a publicar manualmente la propiedad Tag, las modificaciones de configuración de los pasos 4 y 5 se implementan y activan de forma eficaz.


Antes de configurar Análisis de contenido, asegúrese de que se cumplen los siguientes requisitos previos:


>[!PREREQUISITES]
>
>* Ha incluido en la lista de permitidos el agente de usuario y la dirección IP para el servicio de funcionalidad que se utiliza en el análisis de contenido. La cadena del agente de usuario es `AdobeFeaturization/1.0`.
>* Tiene una función de administrador de productos de Customer Journey Analytics, con los permisos adicionales para administrar conexiones y colecciones de datos. Los permisos de Experience Platform necesarios son:
>  
>   | Categoría | Permiso | Descripción |
>   |---|---|---|
>   | [!UICONTROL Recopilación de datos] | Ver flujos de datos | Acceso de solo lectura a flujos de datos. |
>   | [!UICONTROL Recopilación de datos] | Administrar flujos de datos | Acceso para leer, crear, editar y eliminar flujos de datos. |
>   | [!UICONTROL Modelado de datos] | [!UICONTROL Esquemas de vista] | Acceso de solo lectura a esquemas y recursos relacionados. |
>   | [!UICONTROL Modelado de datos] | [!UICONTROL Administrar esquemas] | Acceso para leer, crear, editar y eliminar esquemas y recursos relacionados. |
>   | [!UICONTROL Administración de datos] | [!UICONTROL Ver conjuntos de datos] | Acceso de solo lectura para conjuntos de datos y esquemas. |
>   | [!UICONTROL Administración de datos] | [!UICONTROL Administrar conjuntos de datos] | Acceso para leer, crear, editar y eliminar conjuntos de datos. Acceso de solo lectura para esquemas. |
>   | [!UICONTROL Ingesta de datos] | [!UICONTROL Administrar orígenes] | Acceso para leer, crear, editar y deshabilitar orígenes. |
>   | [!UICONTROL Identity Management] | [!UICONTROL Ver áreas de nombres de identidad] | Acceso de solo lectura para áreas de nombres de identidad. |
>
>* Ha considerado detenidamente las siguientes opciones de configuración importantes:
>
>   * ¿Su sitio es adecuado para el sistema de informes de experiencias? Un informe de experiencia adecuado solo es posible cuando se cumplen las siguientes condiciones:
>   * El contenido del sitio solo se administra mediante direcciones URL.
>   * Las páginas del sitio se pueden reproducir con la dirección URL de la página y se comprende qué parámetros de URL opcionales impulsan las experiencias.
>* Tiene una comprensión clara de qué páginas desea capturar el análisis de participación del contenido y las perspectivas.
>* Tiene una comprensión clara de qué recursos (tipo de) desea capturar el análisis y las perspectivas de participación en el contenido.
>


>[!MORELIKETHIS]
>
>* [Configuración guiada](guided.md)
>* [Configuración manual](manual.md)
>* [Control de acceso](/help/technotes/access-control.md)
>


