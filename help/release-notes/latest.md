---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: f95aadbaa9cff775f51ed3d1f8bf9fe54adfd795
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 52%

---

# Notas de la versión del Customer Journey Analytics actual (CJA) (julio de 2022)

**Última actualización**: 19 de julio de 2022

>[!NOTE]
>
>Esta página contiene información previa al lanzamiento y está sujeta a cambios.

## Funciones principales

| Función | Descripción | [Fecha objetivo](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| Compatibilidad con campos numéricos como claves de búsqueda y valores de búsqueda | Resulta útil si desea clasificar valores de cadena con un campo numérico como, por ejemplo, COGS o margen en un SKU de producto. Al permitir métricas de búsquedas, puede obtener estos puntos de datos en los informes. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=es#numeric) | 20 de julio de 2022 |
| Panel de visualizadores simultáneos de medios | Comprenda dónde se produjo el pico de concurrencia o dónde se produjeron las disminuciones. Obtenga valiosos conocimientos de la calidad del contenido y de la participación del visualizador, y ayude a solucionar problemas o a planificar el volumen o la escala. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html) | 30 de julio de 2022 |
| Panel Tiempo invertido en la reproducción de contenido | El tiempo de reproducción de contenido multimedia empleado proporciona una valiosa perspectiva de la participación del visor y permite a las organizaciones de medios obtener perspectivas más detalladas gracias a la participación del usuario minuto a minuto a través del análisis avanzado del tiempo invertido con funciones de partición de día. Puede observar la cantidad de tiempo que se dedica a ver sus flujos de contenido en un momento determinado. Puede dividir la duración de la reproducción por diferentes granularidades, incluyendo las nuevas granularidades de 5, 15 y 30 minutos.  [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html) | 30 de julio de 2022 |
| Informes de primera sesión frente a repetida | Ahora puede descubrir si una sesión en particular fue la primera sesión de un usuario. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) | 17 de agosto de 2022 |


## Correcciones

AN-288455; AN-288828; AN-289323

## Avisos importantes para los administradores de CJA

| Aviso | Añadido o actualizado | Descripción |
| --- | --- | --- |
| Asignación de IP a geolocalización mejorada | 11 de julio de 2022 | El proveedor de Adobes para búsquedas de IP, Digital Element, está actualizando a un nuevo conjunto de datos mejorado (NetAcuity Pulse) para la asignación de IP a geolocalización. Adobe Analytics adoptará este nuevo conjunto de datos en el intervalo de tiempo de octubre de 2022. La nueva base de datos será más precisa que las versiones anteriores. Algunas asignaciones de IP a regiones cambiarán o mejorarán cuando se adopte la nueva base de datos.<p> Los datos de CJA proporcionados a través del conector de origen de Analytics también aprovecharán automáticamente las nuevas asignaciones. |

>[!MORELIKETHIS]
>[Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
