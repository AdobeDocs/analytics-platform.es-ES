---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: f961bf0a615199de931a98f14d8b640890df7a2b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Notas de la versión del Customer Journey Analytics actual (CJA) (septiembre de 2022)

**Última actualización**: 9 de septiembre de 2022

>[!NOTE]
>
>Esta página incluye contenido previo al lanzamiento de la nueva versión y está sujeta a cambios.

## Recursos relacionados

* [Notas de la versión anteriores de CJA para 2022](/help/release-notes/2022.md)

* [Notas de la versión de Adobe Analytics de ](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)

* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)

* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)

## Funciones principales

| Función | Descripción | [Fecha objetivo](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Compatibilidad entre regiones para el conector de origen de Analytics** | Ahora puede ingerir grupos de informes de cualquier región (Estados Unidos, Reino Unido o Singapur). Sin embargo, estos deben asignarse a la misma organización que la instancia de zona protegida de Experience Platform en la que se está creando la conexión de origen.  [Más información](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es) | 24 de agosto de 2022 |
| **Informes de primera sesión** | Descubra si una sesión en particular fue la primera sesión del usuario.  [Más información](/help/data-views/data-views-usecases.md) | 24 de agosto de 2022 |
| **Panel de experimentación para CJA** | Este nuevo panel de espacio de trabajo permite a los usuarios de CJA evaluar el alza y la confianza de cualquier experimento A/B desde cualquier fuente: en línea, sin conexión, desde soluciones de Adobe, Adobe Journey Optimizer e incluso datos de BYO (por su cuenta).  [Más información](/help/analysis-workspace/c-panels/experimentation.md) | [Versión limitada](/help/release-notes/releases.md) a partir del 14 de septiembre de 2022 |
| **Visualización de gráficos combinados en Workspace** | Los gráficos combinados le permiten comparar métricas de forma más fácil e intuitiva dentro de Workspace.  [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/visualizations/combo-charts.html?lang=en) | 14 de septiembre de 2022 |

{style=&quot;table-layout:auto&quot;}

## Correcciones

AN-298412

## Avisos importantes para los administradores de CJA

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| **Asignación de IP a geolocalización mejorada** | 9 de septiembre de 2022 | El proveedor de Adobe para búsquedas de IP, Digital Element, está actualizando a un nuevo conjunto de datos mejorado (NetAcuity Pulse) para la asignación de IP a geolocalización. Adobe Analytics adoptará este nuevo conjunto de datos en **5 de octubre de 2022**. La nueva base de datos será más precisa que las versiones anteriores. Algunas asignaciones de IP a regiones cambiarán o mejorarán cuando se adopte la nueva base de datos.<p> Los datos de CJA proporcionados a través del conector de origen de Analytics también aprovecharán automáticamente las nuevas asignaciones. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
