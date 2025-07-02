---
description: Comprenda cuáles son las métricas y cómo utilizarlas en Adobe Analytics.
title: Métricas
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: f3c9a000ae5baa19cb5a6cf0e0343de3a9685b56
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 8%

---

# Métricas

Las métricas permiten cuantificar los puntos de datos en Analysis Workspace. Normalmente se utilizan como columnas en una visualización y están vinculadas a las dimensiones.

## Uso de métricas en Analysis Workspace

Las métricas son flexibles en su uso dentro de Analysis Workspace. Arrastre una métrica a una tabla de forma libre vacía para ver las tendencias de esa métrica durante el período de fecha del proyecto. También puede arrastrar una métrica cuando una dimensión esté presente para ver cómo se compara esa métrica con cada elemento de dimensión. Si arrastra una métrica sobre un encabezado de métrica existente, reemplazará la métrica existente y, si arrastra una métrica junto a un encabezado, podrá ver ambas métricas una al lado de la otra.

Para obtener información acerca de cómo agregar métricas y otros tipos de componentes a Analysis Workspace, vea [Usar componentes en Analysis Workspace](/help/components/use-components-in-workspace.md).


## Tipos de métricas

Adobe ofrece varios tipos de métricas para usar en Analysis Workspace:


* **Métricas estándar**: Algunos ejemplos de métricas estándar son Personas, Sesiones, Eventos y Cuentas de [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}.

  Al contrario que Adobe Analytics, Customer Journey Analytics permite definir métricas estándar de forma flexible dentro del ámbito de una conexión y una vista de datos.  Consulte [Métricas estándar](#standard-metrics) para obtener una lista completa de las métricas estándar.

* **Métricas calculadas** ![Calculadora](/help/assets/icons/Calculator.svg): [Métricas definidas por el usuario](/help/components/calc-metrics/calc-metr-overview.md) basadas en métricas estándar, números estáticos o funciones algorítmicas.

* **Plantillas de métricas calculadas** ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) : Métricas definidas por Adobe que se comportan de manera similar a las métricas calculadas. Puede utilizarlos tal cual en los proyectos de Workspace o guardar una copia para personalizar la lógica. Ver [métricas calculadas predeterminadas](calc-metrics/cm-workflow/../default-calcmetrics.md).

Puede ver si una métrica está aprobada ![Icono aprobado](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) o no. Si desea obtener más detalles sobre una métrica, pase el ratón sobre ella y seleccione ![Icono de información](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg). Consulte [Información del componente](use-components-in-workspace.md#component-info) para obtener más información.


## Métricas estándar

La lista completa de métricas estándar en Customer Journey Analytics:
{{standard-metrics}}


## Crear métricas calculadas

Las métricas calculadas permiten configurar cómo se relacionan entre sí las métricas, mediante operadores simples o funciones estadísticas. Consulte [Resumen de métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md) para obtener más información.

Existen varias formas de crear métricas calculadas. El método que elija determina si la métrica calculada está disponible en la lista de componentes de todos los proyectos o solo en el proyecto en el que se creó.

### Crear métricas calculadas para todos los proyectos

Puede usar el [generador de métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) para [crear métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-workflow.md). Cuando se crean de esta manera, las métricas calculadas están disponibles en la lista de componentes y, a continuación, se pueden utilizar en proyectos de toda la organización.

### Crear métricas calculadas para un solo proyecto

Puede crear rápidamente una métrica calculada que solo esté disponible para el proyecto en el que se creó.

Para crear una métrica calculada para un solo proyecto:

1. En Analysis Workspace, abra el proyecto en el que desea crear la métrica calculada.

1. En una tabla de forma libre, haga clic con el botón secundario en el encabezado de columna de una sola columna.

   O bien

   Seleccione dos columnas mientras mantiene pulsada la tecla Mayús y, a continuación, haga clic con el botón derecho en una de las columnas seleccionadas.

1. Seleccionar **[!UICONTROL Crear métrica a partir de la selección]**

   ![Panel de Workspace resaltando Crear a partir de la selección](assets/create-metric-from-selection.png)

1. Para crear una métrica calculada solo para este proyecto, elija entre las opciones disponibles.

   Cuando se selecciona una sola columna, están disponibles las siguientes opciones:

   * [!UICONTROL **Media**]: crea una nueva columna que muestra el valor medio en el conjunto de elementos de dimensión de la columna. Este valor de columna utiliza la función [Media](/help/components/calc-metrics/cm-functions.md#mean).

   * [!UICONTROL **Mediana**]: crea una nueva columna que muestra el valor de mediana en el conjunto de elementos de dimensión de la columna. Este valor de columna utiliza la función [Median](/help/components/calc-metrics/cm-functions.md#median).

   * [!UICONTROL **Máximo de columna**]: Crea una nueva columna que muestra el valor más alto del conjunto de elementos de dimensión de la columna. Este valor de columna utiliza la función [Máximo de columna](/help/components/calc-metrics/cm-functions.md#column-maximum).

   * [!UICONTROL **Columna mín.**]: crea una nueva columna que muestra el valor más pequeño del conjunto de elementos de dimensión para la columna. Este valor de columna utiliza la función [Mínimo de columna](/help/components/calc-metrics/cm-functions.md#column-minimum).

   * [!UICONTROL **Suma de columna**]: Crea una nueva columna que agrega todos los valores numéricos de una métrica dentro de una columna (en los elementos de una dimensión). Este valor de columna utiliza la función [Suma de columna](/help/components/calc-metrics/cm-functions.md#column-sum).

   Cuando se seleccionan dos columnas, están disponibles las siguientes opciones:

   * [!UICONTROL **Dividir**]: crea una nueva columna que divide los valores de las dos columnas seleccionadas.

   * [!UICONTROL **Restar**]: crea una nueva columna que resta los valores de las dos columnas seleccionadas.

   * [!UICONTROL **Agregar**]: crea una nueva columna que agrega los valores de las dos columnas seleccionadas.

   * [!UICONTROL **Multiplicar**]: crea una nueva columna que multiplica los valores de las dos columnas seleccionadas.

   * [!UICONTROL **Cambio porcentual**]: crea una nueva columna que muestra el cambio porcentual entre las dos columnas seleccionadas.


## Comparar métricas con diferentes modelos de atribución

Para comparar rápidamente un modelo de atribución con otro para una métrica, seleccione **[!UICONTROL Comparar modelos de atribución]** en el menú contextual de una métrica.

![Resaltar el panel de Workspace Comparar modelos de atribución](assets/compare-attribution.png)

Este método abreviado permite comparar un modelo de atribución con otro sin tener que arrastrar una métrica y configurarla dos veces.


