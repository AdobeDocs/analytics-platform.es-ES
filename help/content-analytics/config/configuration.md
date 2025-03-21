---
title: Configuración de Content Analytics
description: Información general sobre la configuración de Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: 01459765d84a46d170c1619ffeae184957bbf839
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 2%

---

# Configuración de Content Analytics

{{draft-aca}}

{{release-limited-testing}}

La configuración de Content Analytics consta de los siguientes pasos:

![Configuración de Content Analytics](../assets/aca-configuration.svg){zoomable="yes"}

1. Utilice el asistente de Content Analytics [configuración guiada](guided.md) para guiarle por todos los pasos necesarios para establecer los requisitos previos de una configuración de Content Analytics. Puede guardar las configuraciones en cualquier momento y volver más tarde.
1. Una vez que se sienta cómodo con los valores de configuración, puede implementar la configuración. Esta implementación crea todos los artefactos necesarios en función de lo que haya configurado en el asistente.
1. Solo cuando [publique](manual.md) manualmente la propiedad Etiquetas, la configuración de Content Analytics se implementará y activará de manera efectiva.

1. Solo puede realizar algunos cambios menores en una configuración implementada mediante el asistente de [configuración guiada](guided.md). Por ejemplo, cambie la [Vista de datos](/help/data-views/data-views.md).
1. Puede realizar otros cambios en una configuración implementada usando la [extensión de Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) en la propiedad Tags asociada.
1. Solo cuando [vuelva a publicar](manual.md) manualmente la propiedad Etiquetas, las modificaciones de configuración se implementarán y activarán de manera efectiva.


## Requisitos previos

Antes de configurar Content Analytics, asegúrese de que se cumplen los siguientes requisitos previos:

* Ha incluido en la lista de permitidos el agente de usuario y la dirección IP para el servicio de funcionalidad que se utiliza en Content Analytics. La cadena del agente de usuario que se va a configurar es: <code>AdobeFeaturization/1.0</code>.
* Tiene una función de administrador de productos de Customer Journey Analytics, con los permisos adicionales para administrar conexiones y vistas de datos.
* Tiene los permisos de Experience Platform necesarios:

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

   * Su sitio es adecuado para los informes de experiencias. Un sistema de informes de experiencia adecuado solo es posible cuando se cumplen las siguientes condiciones:
      * Puede acceder al contenido del sitio solo mediante direcciones URL públicas. El acceso al sitio no requiere tokens personalizados, cookies u otros mecanismos no disponibles a través de la URL.
      * Las páginas del sitio se pueden reproducir con la dirección URL de la página y se comprende qué parámetros de URL opcionales impulsan las experiencias.
   * Tiene una comprensión clara de qué páginas desea capturar el análisis de participación del contenido y las perspectivas.
   * Tiene una comprensión clara de qué recursos (tipo de) desea capturar el análisis y las perspectivas de participación en el contenido.


## Control de acceso

>[!IMPORTANT]
>
>No hay permisos de Content Analytics que se puedan configurar para habilitar o deshabilitar el acceso de Content Analytics para usuarios individuales o grupos de usuarios.
>

Para que un usuario o grupo de usuarios tenga acceso a Content Analytics, debe proporcionarle acceso a una o más [vistas de datos configuradas para Content Analytics](guided.md#data-view).

Este acceso implica:

1. La vista de datos habilitada para Content Analytics se incluye como parte de los permisos de vista de datos para un perfil de producto de Customer Journey Analytics específico.
1. Ese perfil de producto de Customer Journey Analytics específico es uno de los perfiles de producto asignados al usuario o grupo de usuarios.

>[!MORELIKETHIS]
>
>* [Configuración guiada](guided.md)
>* [Configuración manual](manual.md)
>* [Control de acceso](/help/technotes/access-control.md)
>
