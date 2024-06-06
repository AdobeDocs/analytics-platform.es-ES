---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 6ac57240b9c74b83cadcb26a5fd55913bc28c01f
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 91%

---

# Notas actuales de la versión de Adobe Customer Journey Analytics (mayo de 2024)

**Última actualización**: viernes, 06 de junio de 2024

Estas notas de la versión abarcan el periodo de lanzamiento del 15 de mayo de 2024 a junio de 2024. Las versiones de Customer Journey Analytics operan en un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Asistente de IA para Customer Journey Analytics** | Permite realizar preguntas en lenguaje natural en la interfaz de usuario de Customer Journey Analytics y obtener respuestas basadas en la documentación de Customer Journey Analytics. [Más información](/help/ai-assistant.md) | | viernes, 06 de junio de 2024 |
| **Transformación de los conjuntos de datos de búsqueda B2B** | Ahora puede [transformar conjuntos de datos de búsqueda B2B](/help/connections/transform-datasets-b2b-lookups.md) al definir una conexión. Esta transformación permite admitir búsquedas basadas en personas en datos B2B. | | viernes, 06 de junio de 2024 |
| **Extensión de BI** | La extensión de BI habilita el acceso SQL a las vistas de datos que ha definido en Customer Journey Analytics. [Más información](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-dataviews/bi-extension) | | 15 de mayo de 2024 |
| **Los púbicos se publican en una nueva sección “Públicos” en Experience Platform** | Los públicos publicados desde Customer Journey Analytics están ahora disponibles en la nueva sección “Públicos” de Experience Platform.<p>Anteriormente, los públicos publicados desde Customer Journey Analytics estaban disponibles en Experience Platform en la sección “Segmentos”.</p><p>Esta mejora ofrece las siguientes ventajas:</p><ul><li>Los públicos ya no tienen un retraso de 1 hora antes de aparecer en Experience Platform; están disponibles segundos tras su publicación.</li><li>Los públicos se pueden ordenar en Experience Platform mediante la columna “Origen”, que muestra la aplicación desde la que se publicó originalmente el público.</li><li>Las opciones de filtro y ordenación de Experience Platform le permiten encontrar más rápidamente los públicos relevantes.</li></ul> <p>(Vínculo a la documentación actualizada a continuación)</p> |  | De finales de mayo a principios de junio de 2024 |
| **Medios de streaming: envíe datos web a Edge Network de Adobe Experience Platform con SDK web** | Ahora puede utilizar SDK web de Adobe Experience Platform para enviar datos web de medios de streaming a Edge Network de Adobe Experience Platform, lo que le permite generar campañas más personalizadas y proporcionar contenido más personalizado, lo que proporciona más datos de seguimiento sobre los que informar.<p>Esta mejora proporciona un método de colección unificado para implementaciones web en todas las soluciones de Platform, como Customer Journey Analytics, RT-CDP, AJO y reenvío de eventos. Anteriormente, la única manera de enviar datos web de medios de streaming a Edge Network era mediante la API de Media Edge. <p>[Más información](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/edge-web-sdk)</p> | | 29 de mayo de 2024 |
| **Campos derivados: nuevas funciones y plantillas de funciones** | Funciones de campo derivadas adicionales ([Matemáticas](/help/data-views/derived-fields/derived-fields.md#math), [Siguiente o Anterior](/help/data-views/derived-fields/derived-fields.md#next-or-previous)) y [plantillas de función](/help/data-views/derived-fields/derived-fields.md#function-templates). | | 5 de junio de 2024 |
| **Compartir cuentas y ubicaciones que se utilizan para exportar e importar** | Ahora, los usuarios pueden poner las cuentas y ubicaciones que creen a disposición de todos los usuarios de su organización. Los propietarios de cuentas y ubicaciones y los administradores del sistema son los únicos que pueden editar y eliminar cuentas y ubicaciones.<p>Anteriormente, las cuentas y ubicaciones solo las podía usar el usuario que las creaba.</p><p>Esta configuración está disponible cuando los usuarios configuran cuentas de exportación en la nube y configuran ubicaciones de exportación en la nube.</p> <p>(Vínculo a la documentación actualizada a continuación)</p> | 12 de junio de 2024 | 30 de junio de 2024 |
| **Nueva documentación para actualizar de Adobe Analytics a Customer Journey Analytics** | Para las organizaciones que actualizan de Adobe Analytics a Customer Journey Analytics, existen varias opciones de actualización y muchas consideraciones que se deben tener en cuenta según la implementación de Adobe Analytics actual y los objetivos a largo plazo de una organización. Ya hay disponibles nuevos recursos de documentación para ayudarle a comprender mejor:<ul><li>Las distintas rutas de actualización existentes</li><li>Qué rutas de actualización están disponibles según la implementación de Adobe Analytics actual de una organización</li><li>Las ventajas y desventajas de cada ruta de actualización</li><li>Guía paso a paso para cada ruta de actualización</li><li>Consideraciones para administrar datos históricos</li></ul>[Introducción a la actualización a Customer Journey Analytics](https://experienceleague.adobe.com/es/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | Ya disponible |
| **Nueva documentación sobre Casos de uso de exportación de datos** | Esta nueva sección describe [casos de uso de exportación de datos](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-usecases/data-export/overview) como<ul><li>Copia de seguridad de datos</li><li>Validación de datos</li><li>Herramientas de lago de datos, almacén de datos o BI</li><li>Preparación para IA/AA</li></ul> y cómo implementarlos mediante las funcionalidades de Experience Platform y Customer Journey Analytics. | | Ya disponible |

{style="table-layout:auto"}

## Correcciones en Customer Journey Analytics

AN-342309; AN-342312; AN-345267; AN-345909; AN-346016; AN-346049; AN-346052; AN-346287; AN-346624; AN-347919

## Avisos importantes para los administradores de Customer Journey Analytics

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| N/A | | |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de la versión anteriores de Customer Journey Analytics de 2024](/help/release-notes/2024.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
