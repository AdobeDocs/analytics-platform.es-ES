---
title: Notas de la versión de Customer Journey Analytics actuales
description: Ver las notas de la versión más recientes de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 806bcaa72479c3e871e12fd1c4802bac97eda439
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 29%

---

# Notas actuales de la versión de Adobe Customer Journey Analytics (enero de 2025)

**Última actualización**: jueves, 22 de enero de 2025

Estas notas de la versión abarcan el periodo de lanzamiento del 23 de octubre de 2024 al 30 de enero de 2025. Las versiones de Adobe Customer Journey Analytics operan en un [modelo de entrega continua](releases.md), que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Experiencia de uso de conexiones actualizada** | La ficha **[!UICONTROL Uso]** de Connection ahora proporciona visualizaciones mejoradas para estos tipos de filas de informes: datos principales, ingeridos e históricos. También puede ver y desglosar los datos de uso por conexión, conjunto de datos, zona protegida o etiqueta. [Más información](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/manage-connections#connections-usage) |  | jueves, 15 de enero de 2025 |
| **API para migrar proyectos de Adobe Analytics y cualquier componente incluido al Customer Journey Analytics** | Ahora hay disponible una API para migrar sus proyectos de Adobe Analytics y los componentes incluidos a Customer Journey Analytics. Anteriormente, la migración de proyectos y componentes solo estaba disponible a través de la interfaz de usuario de. [Más información](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=CJA%20Migration%20APIs). Seleccione **API de migración de CJA** de la lista desplegable. |  | jueves, 15 de enero de 2025 |
| **Usar plantillas personalizadas del Customer Journey Analytics en la página Informes de Journey Optimizer** | Ahora puede personalizar la nueva interfaz de informes en Adobe Journey Optimizer creando o editando una plantilla en Customer Journey Analytics y guardando a continuación la plantilla que desea utilizar en la página Informes de Journey Optimizer. Anteriormente, la nueva interfaz de informes de Adobe Journey Optimizer no se podía personalizar. <p>Para obtener más información, consulte &quot;Crear una plantilla&quot; o &quot;Editar o eliminar una plantilla&quot; en [Crear y administrar plantillas](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/templates/create-templates).  |  | jueves, 15 de enero de 2025 |
| **Plantillas en Analysis Workspace** | Las plantillas ya están disponibles en Customer Journey Analytics.<ul><li>**Plantillas generadas previamente**: Hay disponible una gran selección de plantillas generadas previamente. Puede utilizar estas plantillas para obtener información rápida sobre los escenarios de sistema de informes más comunes. Las plantillas creadas previamente se pueden usar tal cual. O bien, pueden utilizarse como punto de partida para un proyecto, que luego se puede personalizar para adaptarse mejor a un propósito específico. [Más información](/help/analysis-workspace/templates/use-templates.md)</li><li>**Plantillas de empresa**: los administradores pueden crear plantillas de empresa para satisfacer las necesidades de los casos de uso específicos de su organización. Las plantillas de empresa que crean los administradores están disponibles para los usuarios de su organización. [Más información](/help/analysis-workspace/templates/create-templates.md)</li></ul> | Enero de 15 | viernes, 30 de enero de 2025 |
| **Uso del producto** | Consulte cómo utiliza su organización Customer Journey Analytics. Al habilitar esta función, se crea un conjunto de datos en Adobe Experience Platform que recopila datos cuando cualquier persona de su organización utiliza Analysis Workspace. También se crean automáticamente una conexión y una vista de datos, lo que le permite acceder a dimensiones como los tipos de proyecto principales, los usuarios más activos y los componentes más populares que se utilizan en los proyectos. [Más información](/help/tools/product-usage/usage-overview.md) | 23 de octubre de 2024 | 22 de enero de 2025 |
| **Subtítulos inteligentes v2** | Los subtítulos inteligentes ahora son compatibles con las siguientes visualizaciones: Multilínea, Barra, Barra horizontal, Anillo, Área, Flujo y Visitas en el orden previsto. Puede seleccionar mostrar todos los subtítulos inteligentes a la vez en una vista expandida o puede mostrar subtítulos inteligentes individuales en una vista uno a uno. [Más información](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/intelligent-captions) |  | 22 de enero de 2025 |
| **Agregar análisis guiados a proyectos desde el análisis guiado** | Permite agregar análisis guiados a proyectos de Workspace desde un análisis guiado. También puede añadir análisis guiados directamente en Analysis Workspace. [Más información](https://experienceleague.adobe.com/es/docs/analytics-platform/using/guided-analysis/overview) |  | 22 de enero de 2025 |
| **Recopilación de medios: actualizaciones del conector Source de Adobe para el nuevo XDM de creación de informes de medios** | El Conector de Source de Analytics asignará automáticamente los datos de medios de streaming en Adobe Analytics a los mismos campos utilizados por el SDK web. Actualmente, los datos se asignan a las ubicaciones antigua y nueva, pero solo se utilizará la nueva en el futuro. (Vínculo a la documentación próximamente) |  | viernes, 30 de enero de 2025 |

## Correcciones en Customer Journey Analytics

Alertas: AN-363263; AN-364880; AN-365029; AN-365960
Audiencias: AN-362564; AN-363254;
Ingesta de datos: AN-362359; AN-362751
Vistas de datos: AN-362089; AN-365213; AN-365770; AN-366171; AN-366681
Campos derivados: AN-359711; AN-362496
Ubicaciones de exportación: AN-363999
Exportación de tabla completa: AN-363055
Report Builder: AN-362937
Workspace: AN-359012; AN-359145; AN-359914; AN-361455; AN-361934; AN-362469; AN-363460; AN-364714; AN-364918; AN-366277;


## Avisos importantes para los administradores de Customer Journey Analytics

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| N/A | | |

## Recursos relacionados

* [Notas de la versión anteriores de Customer Journey Analytics de 2024](/help/release-notes/2024.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión de la colección de medios de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
