---
title: Notas de la versión de Customer Journey Analytics actuales
description: Visualización de las notas de la última versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: fc22f2c83340bacb99fd08095c48585be9e5f1fe
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 19%

---

# Notas actuales de la versión de Adobe Customer Journey Analytics (agosto de 2025)

**Última actualización**: viernes, 14 de agosto de 2025


Estas notas de la versión abarcan el periodo de lanzamiento del 13 de agosto al 16 de septiembre de 2025. Las versiones de Adobe Customer Journey Analytics operan en un [modelo de entrega continua](releases.md), que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Visualización de mapas** | La visualización de mapas es una visualización en Analysis Workspace que le permite crear un mapa visual de cualquier métrica (incluidas las métricas calculadas). Resulta útil para identificar y comparar datos de métricas entre diferentes regiones geográficas.<p>Anteriormente, la visualización de mapas solo estaba disponible en Adobe Analytics.</p><p>La visualización de mapas en Customer Journey Analytics presenta las siguientes mejoras con respecto a la visualización de mapas en Adobe Analytics:</p><ul><li>Utilice cualquier segmento de la vista de datos como fuente de datos.</li><li>Precisión de hasta un solo medidor configurando la dimensión en la vista de datos.</li><li>Una nueva herramienta de selección le permite crear un segmento, una audiencia, una tendencia o un desglose a partir de cualquier área que seleccione en la visualización.</li></ul><p>Para obtener más información, consulte [Mapa](/help/analysis-workspace/visualizations/map.md).</p> | jueves, 13 de agosto de 2025 | martes, 25 de agosto de 2025 |
| **Plantillas B2B** | Si obtiene la licencia de Customer Journey Analytics B2B edition, las siguientes plantillas B2B adicionales ya están disponibles en la interfaz de usuario de Adobe templates: <ul><li>información general sobre la participación de la cuenta B2B</li><li>Información general sobre la participación de oportunidad B2B</li><li>Actividad de los grupos de compra B2B</li></ul><p>Para obtener más información, consulte [Plantillas B2B](/help/analysis-workspace/templates/use-templates.md#b2b-templates) en [Usar plantillas](/help/analysis-workspace/templates/use-templates.md).</p> |  | sábado, 15 de agosto de 2025 |
| **Los proyectos descargados en formato PDF se descargan en su estación de trabajo** | Al descargar un proyecto as a PDF, PDF se descarga en la carpeta de descargas de la estación de trabajo. <p>Anteriormente, al descargar un proyecto as a PDF, se iniciaba PDF en una nueva pestaña del explorador con una dirección URL única.</p><p>Para obtener más información, vea [Descargar proyectos y datos](/help/analysis-workspace/export/download-send.md).</p> |  | martes, 25 de agosto de 2025 |
| **Compatibilidad con esquemas ad hoc** | [Los esquemas específicos](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/tutorials/ad-hoc) se utilizan en varios flujos de trabajo de ingesta de datos para Experience Platform, incluida la ingesta de archivos CSV y la creación de ciertos tipos de conexiones de origen. <p>Esta función habilita la compatibilidad para utilizar esquemas ad hoc en Customer Journey Analytics. Como parte de la definición de una conexión, ahora puede seleccionar un conjunto de datos basado en un esquema ad-hoc y utilizar los datos en la vista de datos y los proyectos de Workspace.</p> <p>(Vínculo a la documentación a continuación).</p> |  | viernes, 28 de agosto de 2025 |
| **Ampliación del límite de claves de búsqueda** | Según el paquete de Customer Journey Analytics, ahora puede tener hasta un máximo de 1000 millones de claves únicas en un conjunto de datos de consulta. <p>Para obtener más información, consulte [Límites de transferencia de datos](/help/technotes/guardrails.md#data-transfer-limits) en la documentación de [Protecciones](/help/technotes/guardrails.md) de Customer Journey Analytics.</p> |  | sábado, 29 de agosto de 2025 |
| **Cree métricas y dimensiones basadas en campos de asignación definidos por el usuario a partir del esquema de Platform** | Los campos de asignación definidos por el usuario que defina en el esquema de Experience Platform ya están disponibles para su uso en Customer Journey Analytics.<p>Puede utilizar los siguientes campos de asignación al crear métricas y dimensiones en Customer Journey Analytics:</p><ul><li>Cadena a cadena</li><li>Cadena a entero</li></ul><p>(Vínculo a la documentación a continuación).</p><p>Para obtener más información sobre los campos de asignación en Experience Platform, consulte [Definir campos de asignación en la interfaz de usuario](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/ui/fields/map).</p> |  | Finales de agosto de 2025 |
| **La dirección URL no tiene disponibles de inmediato los proyectos eliminados y estos se eliminan de las entregas programadas** | Los proyectos que se eliminan se eliminan inmediatamente de las entregas programadas y ya no son accesibles mediante su dirección URL.<p>Anteriormente, los proyectos se incluían en envíos programados y se podía acceder a ellos con su dirección URL durante 60 días después de eliminarse.</p><p>Para obtener más información sobre cómo eliminar proyectos, consulte [Resumen de proyectos](/help/analysis-workspace/build-workspace-project/freeform-overview.md).</p> | | Finales de agosto de 2025 |
| **Creación de informes en tiempo real** | La creación de informes en tiempo real en Customer Journey Analytics muestra y actualiza datos y visualizaciones en uno o varios paneles de Analysis Workspace en tiempo real. | | 17 de septiembre de 2025 (originalmente programado para su lanzamiento el 15 de agosto de 2025) |
| **Medios de streaming: se han actualizado los campos XDM para recopilar datos de medios de streaming en Adobe Experience Platform** | Al recopilar datos de medios de streaming en Adobe Experience Platform, ya no se deben utilizar las rutas de campo XDM que se muestran en el encabezado de &quot;Ruta de campo XDM&quot; de la documentación de parámetros de medios de streaming. En su lugar, los clientes que implementaron el conector de origen de Analytics para recopilar datos de medios de streaming en Platform antes del 9 de mayo de 2025 deben migrar sus configuraciones existentes a las rutas de campo de creación de informes de medios, como se muestra en el encabezado de &quot;Ruta del campo XDM de creación de informes&quot; de la documentación de parámetros de medios de streaming.<p> Estas rutas de campo se encuentran en las páginas siguientes y están marcadas como &quot;Obsoletas&quot;: [Parámetros de audio y vídeo](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/audio-video-parameters), [Parámetros de publicidad](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/ad-parameters), [Parámetros de capítulo](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/chapter-parameters), [Parámetros de estado del reproductor](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/player-state-parameters) y [Parámetros de calidad](https://experienceleague.adobe.com/es/docs/media-analytics/using/implementation/variables/quality-parameters). (No se requiere ninguna acción para los clientes que implementan el conector de origen de Analytics después del 9 de mayo de 2025 y que ya solo utilizan rutas XDM de creación de informes de medios).</p><p>La ingesta de datos en las rutas de campo XDM obsoletas seguirá hasta finales de octubre de 2025. Después de este tiempo, las rutas de campo obsoletas se eliminarán por completo y ya no serán visibles en la interfaz de usuario del esquema de Adobe Experience Platform, y los datos se enviarán únicamente mediante las rutas de campo de mediaReporting.</p><p>Para obtener más información, consulte [Migrar una implementación del conector Source de Analytics a campos actualizados de medios de streaming XDM](https://experienceleague.adobe.com/es/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields).</p><p>Póngase en contacto con los servicios de Adobe Consulting o con el equipo de la cuenta para obtener ayuda sobre la migración. </p> |  | Octubre de 2025 |
| **Vinculación en conexiones** | Simplifica la vinculación de Customer Journey Analytics. En lugar de duplicar un conjunto de datos y aplicar la vinculación en el conjunto de datos duplicado, la vinculación ahora se realiza al ingerir datos en Customer Journey Analytics, lo que elimina el requisito de conjuntos de datos y esquemas duplicados. <p>Además, en lugar de tener que solicitar la vinculación a través del servicio de atención al cliente, ahora puede iniciar la vinculación desde una interfaz de usuario de Conexiones actualizada.</p><p> *Las fechas de versiones comunicadas anteriormente se retrasan debido a los esfuerzos adicionales necesarios. Las nuevas fechas de lanzamiento se superponen con la temporada de vacaciones, lo que introduce restricciones de lanzamiento adicionales. Ahora se planea un despliegue gradual para garantizar la estabilidad y minimizar las interrupciones durante el período de vacaciones.*</p> | Finales de octubre de 2025 | Finales de enero de 2026 |

## Correcciones en Customer Journey Analytics

**Analysis Workspace**: AN-389683; AN-389534; AN-389207; AN-389066; AN-388687; AN-388478; AN-387089; AN-384865; AN-384560; AN-383486; AN-365768; AN-351639
**Componentes**:
**Content Analytics**:
**Análisis guiado**: AN-384426
**Plataforma**: AN-384410
**Report Builder**: AN-389336; AN-382775
**Informes**:
**Segmentación**:
**Métricas y dimensiones compartidas**:
**Otros**: AN-388222; AN-384898; AN-387169


## Avisos importantes para los administradores de Customer Journey Analytics

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| N/A | | |

## Recursos relacionados

* [Notas de la versión anteriores de Customer Journey Analytics de 2025](/help/release-notes/2025.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión de la colección de medios de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
