---
description: Hay dos modos de utilizar métricas en Analysis Workspace.
title: Métricas
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: d317f6bb9892d0d13fc7723f7e8c2d9ba2ce4f63
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Métricas

Las métricas permiten cuantificar los puntos de datos en Analysis Workspace. Normalmente se utilizan como columnas en una visualización y están vinculadas a las dimensiones.

## Uso de métricas en Analysis Workspace

Las métricas son flexibles en su uso dentro de Analysis Workspace. Arrastre una métrica a una tabla de forma libre vacía para ver las tendencias de esa métrica durante el período de fecha del proyecto. También puede arrastrar una métrica cuando una dimensión esté presente para verla comparada con cada elemento de dimensión. Al arrastrar una métrica sobre un encabezado de métrica existente, se reemplaza y al arrastrar una métrica junto a un encabezado, puede ver ambas métricas en paralelo.

Para obtener información acerca de cómo agregar métricas y otros tipos de componentes a Analysis Workspace, vea [Usar componentes en Analysis Workspace](/help/components/use-components-in-workspace.md).


## Tipos de métricas

Adobe ofrece varios tipos de métricas para usar en Analysis Workspace:


* **Métricas estándar**: Algunas métricas estándar son Personas, Sesiones y Eventos.

  A diferencia de Adobe Analytics, Customer Journey Analytics permite definir métricas estándar de forma flexible dentro del ámbito de una conexión y una vista de datos.

   * **Personas**: La métrica Personas del Customer Journey Analytics es el recuento distinto de los ID de persona. Según lo que elija como ID de persona al configurar conjuntos de datos en la conexión, la métrica Personas puede significar cosas diferentes.
   * **Sesiones**: La métrica Sesiones de Customer Journey Analytics es lo que define como parte de la configuración de Sesiones en la vista de datos. Consulte [Configuración de la sesión](/help/data-views/session-settings.md).
   * **Eventos**: la métrica Eventos de Customer Journey Analytics está compuesta por los eventos que forman parte de cualquier conjunto de datos de evento que haya configurado como parte de su conexión.

* **Métricas calculadas** ![Calculadora](/help/assets/icons/Calculator.svg): Métricas definidas por el usuario que se basan en métricas estándar, números estáticos o funciones algorítmicas.

* **Plantillas de métricas calculadas** ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) : Métricas definidas por Adobes que se comportan de manera similar a las métricas calculadas. Puede utilizarlos tal cual en los proyectos de Workspace o guardar una copia para personalizar la lógica. Ver [métricas calculadas predeterminadas](calc-metrics/cm-workflow/../default-calcmetrics.md).

Puede ver si una métrica está aprobada ![Icono aprobado](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) o no. Si desea obtener más detalles sobre una métrica, pase el ratón sobre ella y seleccione ![Icono de información](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg). Consulte [Información del componente](use-components-in-workspace.md#component-info) para obtener más información.



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
