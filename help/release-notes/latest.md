---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: ed5b1a233dc0e4cbfe223fe71e6e1960efba0592
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 45%

---

# Notas de la versión de Customer Journey Analytics (CJA) (octubre de 2022)

**Última actualización**: 13 de octubre de 2022

Las versiones de Customer Journey Analytics operan en un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Recursos relacionados

* [Notas de la versión de CJA anteriores de 2022](/help/release-notes/2022.md)

* [Notas de la versión de Adobe Analytics ](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)

* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)

* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)

## Funciones principales y actualizaciones

| Función | Descripción | [Fecha objetivo](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Panel de experimentación** | Este nuevo panel de espacio de trabajo permite a los usuarios de CJA evaluar el alza y la confianza de cualquier experimento A/B desde cualquier fuente: en línea, sin conexión, desde soluciones de Adobe, Adobe Journey Optimizer e incluso datos propios.  [Más información](/help/analysis-workspace/c-panels/experimentation.md) | 5 de octubre de 2022 |
| **[!UICONTROL Resumen de métricas clave] visualización** | La variable [!UICONTROL Resumen de métricas clave] la visualización le permite ver las tendencias de una métrica importante dentro de un solo intervalo de tiempo. También le permite comparar el rendimiento de las métricas en dos intervalos de tiempo. Más información | Lanzamiento gradual a partir del 5 de octubre de 2022 |
| **Compatibilidad con campos de fecha en CJA** | Permite que CJA informe sobre los campos de fecha y hora.  [Más información](/help/data-views/data-views-usecases.md#date) | 5 de octubre de 2022 |
| **Aplicación móvil: Vistas de detalles personalizadas** | Las vistas de detalles personalizadas le permiten centrarse aún más en la información que comparte con su audiencia, ya que permiten centrarse en lo que es más importante. Puede modificar el diseño de la vista de detalles asociada a cada mosaico del informe de valoración y agregar texto para explicar mejor lo que el usuario final puede ver en los datos.  [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=es) | 5 de octubre de 2022 |
| **Variables de varios valores que no distinguen entre mayúsculas y minúsculas** | Para variables de varios valores que no distinguen entre mayúsculas y minúsculas, los valores se almacenan en `mvvar1` - `mvvar3` ya no se convertirá en minúsculas automáticamente. En su lugar, los datos pasados a través del Conector de origen de Analytics a Adobe Experience Platform y CJA reflejarán el caso original que se pasó desde la página. | 24 de octubre de 2022 |

{style=&quot;table-layout:auto&quot;}

## Avisos importantes para los administradores de CJA

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| **Página de aterrizaje predeterminada** | 29 de septiembre de 2023 | La variable [nueva página de aterrizaje](/help/getting-started/landing.md) que se introdujo a principios de este año se convertirá en la experiencia predeterminada para todos los usuarios de **Enero de 2023**. La página actual quedará obsoleta y todos tendrán que utilizar la nueva experiencia. |
| **Asignación de IP a geolocalización mejorada** | 29 de septiembre de 2022 | El proveedor de Adobe para búsquedas de IP, Digital Element, está actualizando a un nuevo conjunto de datos mejorado (NetAcuity Pulse) para la asignación de IP a geolocalización. Adobe Analytics ha pospuesto la adopción de este nuevo conjunto de datos a **Enero de 2023**. La nueva base de datos será más precisa que las versiones anteriores. Algunas asignaciones de IP a regiones cambiarán o mejorarán cuando se adopte la nueva base de datos.<p> Los datos de CJA proporcionados a través de la variable [!UICONTROL Conector de origen de Analytics] también aprovechará automáticamente las nuevas asignaciones. |
| **[!UICONTROL Detección de anomalías] condiciones de ejecución automática** | 29 de septiembre de 2022 | Hoy, [!UICONTROL Detección de anomalías] se ejecuta automáticamente en todas las columnas de tablas de forma libre de series temporales. Para garantizar que los datos estén disponibles para análisis y que los proyectos se carguen más rápido, el Adobe cambiará la forma en que [!UICONTROL Detección de anomalías] se ejecuta automáticamente. Inicio **26 de octubre de 2022**, la detección de anomalías se ejecutará automáticamente solo en la primera columna de métrica de una tabla. Puede configurar la configuración de columna para que se ejecute [!UICONTROL Detección de anomalías] en otras columnas, si es necesario. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
