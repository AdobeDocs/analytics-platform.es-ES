---
title: Configurar análisis de contenido
description: Información general sobre la configuración del análisis de contenido
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: ec0ea74df83bbd07b7e026d7b9d7114c7dc595ab
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 2%

---

# Configurar análisis de contenido

>[!WARNING]
>
>Este artículo es una versión preliminar no oficial del borrador de una próxima versión final y forma parte de la documentación de Análisis de contenido. Todo el contenido está sujeto a cambios y no se puede derivar ninguna obligación legal de la versión actual de este artículo.
>

{{release-limited-testing}}


Para configurar el análisis de contenido para su organización, use la [configuración guiada](guided.md) de Análisis de contenido. El asistente de configuración le guiará por todos los pasos necesarios para configurar los requisitos previos para una configuración automática de Content Analytics.

Después de una implementación correcta, puede realizar algunos cambios mediante el asistente de configuración guiada. Sin embargo, es posible que se requieran [cambios manuales](manual.md) además de eso.

## Requisitos previos

Antes de configurar Análisis de contenido, asegúrese de que se cumplen los siguientes requisitos previos:

* Ha incluido en la lista de permitidos el agente de usuario y la dirección IP para el servicio de funcionalidad que se utiliza en el análisis de contenido. La cadena del agente de usuario es `AdobeFeaturization/1.0`.
* Tiene una función de administrador de productos de Customer Journey Analytics, con los permisos adicionales para administrar conexiones y colecciones de datos. Los permisos de Experience Platform necesarios son:

  | Categoría | Permiso | Descripción |
  |---|---|---|
  | [!UICONTROL Recopilación de datos] | Ver flujos de datos | Acceso de solo lectura a flujos de datos. |
  | [!UICONTROL Recopilación de datos] | Administrar flujos de datos | Acceso para leer, crear, editar y eliminar flujos de datos. |
  | [!UICONTROL Modelado de datos] | [!UICONTROL Esquemas de vista] | Acceso de solo lectura a esquemas y recursos relacionados. |
  | [!UICONTROL Modelado de datos] | [!UICONTROL Administrar esquemas] | Acceso para leer, crear, editar y eliminar esquemas y recursos relacionados. |
  | [!UICONTROL Administración de datos] | [!UICONTROL Ver conjuntos de datos] | Acceso de solo lectura para conjuntos de datos y esquemas. |
  | [!UICONTROL Administración de datos] | [!UICONTROL Administrar conjuntos de datos] | Acceso para leer, crear, editar y eliminar conjuntos de datos. Acceso de solo lectura para esquemas. |
  | [!UICONTROL Ingesta de datos] | [!UICONTROL Administrar orígenes] | Acceso para leer, crear, editar y deshabilitar orígenes. |
  | [!UICONTROL Identity Management] | [!UICONTROL Ver áreas de nombres de identidad] | Acceso de solo lectura para áreas de nombres de identidad. |

* Ha considerado detenidamente las siguientes opciones de configuración importantes:

   * ¿Su sitio es adecuado para el sistema de informes de experiencias? Un informe de experiencia adecuado solo es posible cuando se cumplen las siguientes condiciones:
      * El contenido del sitio solo se administra mediante direcciones URL.
      * Las páginas del sitio se pueden reproducir con la dirección URL de la página y se comprende qué parámetros de URL opcionales impulsan las experiencias.
   * Tiene una comprensión clara de qué páginas desea capturar el análisis de participación del contenido y las perspectivas.
   * Tiene una comprensión clara de qué recursos (tipo de) desea capturar el análisis y las perspectivas de participación en el contenido.


>>
[!MORELIKETHIS]
>>
* [Configuración guiada](guided.md)
* [Configuración manual](manual.md)
* [Control de acceso](/help/technotes/access-control.md)
>


