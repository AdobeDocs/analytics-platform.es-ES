---
description: Hay dos modos de utilizar métricas en Analysis Workspace.
title: Métricas
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 20%

---

# Métricas

Las métricas permiten cuantificar los puntos de datos en Analysis Workspace. Normalmente se utilizan como columnas en una visualización y están vinculadas a las dimensiones.

## Tipos de métricas

Adobe ofrece varios tipos de métricas para usar en Analysis Workspace:


* **Métricas estándar**: Algunas métricas estándar son Personas, Sesiones y Eventos.

* **Métricas calculadas** ![Calculadora](/help/assets/icons/Calculator.svg): Métricas definidas por el usuario que se basan en métricas estándar, números estáticos o funciones algorítmicas.

* **Plantillas de métricas calculadas** ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) : Métricas definidas por Adobes que se comportan de manera similar a las métricas calculadas. Puede utilizarlos tal cual en los proyectos de Workspace o guardar una copia para personalizar la lógica.

Puede ver si una métrica está aprobada ![Icono aprobado](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) o no. Si desea obtener más detalles sobre una métrica, pase el ratón sobre ella y seleccione ![Icono de información](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg). Consulte [Información del componente](use-components-in-workspace.md#component-info) para obtener más información.



## Uso de métricas en Analysis Workspace

Las métricas son flexibles en su uso dentro de Analysis Workspace. Arrastre una métrica a una tabla de forma libre vacía para ver las tendencias de esa métrica durante el período de fecha del proyecto. También puede arrastrar una métrica cuando una dimensión esté presente para verla comparada con cada elemento de dimensión. Al arrastrar una métrica sobre un encabezado de métrica existente, se reemplaza y al arrastrar una métrica junto a un encabezado, puede ver ambas métricas en paralelo.

Para obtener información acerca de cómo agregar métricas y otros tipos de componentes a Analysis Workspace, vea [Usar componentes en Analysis Workspace](/help/components/use-components-in-workspace.md).

## Métricas calculadas 

Las métricas calculadas permiten configurar fácilmente cómo se relacionan entre sí las métricas mediante operadores simples o funciones estadísticas. Consulte [Resumen de métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md) para obtener más información.

<!--

There are several ways to create calculated metrics. See [Create calculated metrics]()

### Create calculated metrics for all projects

You can use the calculated metric builder to create calculated metrics. When created in this way, calculated metrics are available in the component list and can then be used in projects throughout your organization. 

For information about how to access the calculated metrics builder, see [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

### Create calculated metrics for a single project

You can create quick calculated metrics that are available only for the project where they were created.

To create a calculated metric for a single project:

1. In Analysis Workspace, open the project where you want to create the calculated metric.

1. In a freeform table, select **[!UICONTROL Create metric from selection]** from the context menu in a column header.

   ![Workspace panel highlighting Create from selection](assets/create-metric-from-selection.png)

1. To create a calculated metric for this project only, choose from the following options:

   * [!UICONTROL **Divide**]
   
   * [!UICONTROL **Subtract**]

   * [!UICONTROL **Add**]

   * [!UICONTROL **Multiply**]

   Or, to open the calculated metric builder and create the calculated metric for all projects, select [!UICONTROL **Open in Calculated Metric Builder**], then continue with [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).


<!-- This video really shows an AA example using hits, etc.  Not suitable for CJA... >
+++ See the following video on how to create an implementation-less calculated metric from within Analysis Workspace.

[Calculated Metrics: Implementation-less metrics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html) (3:42)


>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12)

+++

-->

## Comparar métricas con diferentes modelos de atribución

Si quiere comparar rápida y fácilmente un modelo de atribución con otro para una métrica, seleccione **[!UICONTROL Comparar modelos de atribución]** en el menú contextual de una métrica.

![Resaltar el panel de Workspace Comparar modelos de atribución](assets/compare-attribution.png)

Este método abreviado permite comparar rápida y fácilmente modelos de atribución.
