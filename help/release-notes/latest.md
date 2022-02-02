---
title: Ver las notas de la versión del Customer Journey Analytics actual
description: Últimas notas de la versión de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 73%

---

# Notas de la versión del Customer Journey Analytics actual

## Actualizaciones clave

|[!UICONTROL Persistencia] opciones para enlazar dimensiones y métricas de enlace| Al crear o editar una vista de datos, puede enlazar la persistencia de una dimensión a otra dimensión o métrica. Este concepto se conoce como _comercialización_ en Reports &amp; Analytics, y ahora es compatible con CJA. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=es#binding-dimension)| 19 de enero de 2022 |

## Otras actualizaciones

| Función | Descripción | Fecha objetivo |
| ----------- | ---------- | ----- |
| Modelos de asignación [!UICONTROL Conocida por primera vez] y [!UICONTROL Última conocida] | Estos dos nuevos modelos de asignación toman el primer o último valor observado para una dimensión dentro de un ámbito de persistencia especificado (sesión, persona o período de tiempo personalizado con retrospectiva). A continuación, aplican el modelo de asignación a todos los eventos dentro del ámbito especificado. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=es#allocation-settings) | 19 de enero de 2022 |
| [!UICONTROL PersonID] y [!UICONTROL Área de nombres de PersonID] como dimensiones | Expone el `personID` (o `customerID`, o el ID que utilice para combinar conjuntos de datos en una conexión) como dimensión en vistas de datos. Esta mejora facilita la inclusión de la variable `personID` como dimensión en la vista de datos al extraerla de la conexión. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=es#optional-standard-components) | 19 de enero de 2022 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Actualizaciones de documentación de Customer Journey Analytics](/help/doc-changes.md)
