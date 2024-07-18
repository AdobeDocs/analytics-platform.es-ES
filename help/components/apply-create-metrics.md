---
description: Hay dos modos de utilizar métricas en Analysis Workspace.
title: Métricas
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: 53d367e51f739ebf324390ba4114ddb58138fac8
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 40%

---

# Métricas

Las métricas permiten cuantificar los puntos de datos en Analysis Workspace. Normalmente se utilizan como columnas en una visualización y están vinculadas a las dimensiones.

## Tipos de métricas

Adobe ofrece varios tipos de métricas para usar en Analysis Workspace:

* **Métricas estándar**: Algunas métricas estándar son Personas, Sesiones y Eventos.

* **Métricas calculadas** ![Icono de métrica calculada](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg): Métricas definidas por el usuario que se basan en métricas estándar, números estáticos o funciones algorítmicas.

* **Plantillas de métricas calculadas**  <img src="./assets/adobe-logo.svg" width="18"> : métricas definidas por el Adobe que se comportan de manera similar a las métricas calculadas. Puede utilizarlos tal cual en los proyectos de Workspace o guardar una copia para personalizar su lógica.


![Panel de Workspace que resalta las métricas en el panel izquierdo.](assets/cja-metrics.png)

Puede ver si una métrica está aprobada ![Icono aprobado](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) o no. Si desea obtener más detalles sobre una métrica, pase el ratón sobre ella y seleccione ![Icono de información](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg).


Las métricas son flexibles en su uso dentro de Analysis Workspace. Arrastre una métrica a una tabla de forma libre vacía para ver las tendencias de esa métrica durante el período de fecha del proyecto. También puede arrastrar una métrica cuando una dimensión esté presente para verla comparada con cada elemento de dimensión. Al arrastrar una métrica sobre un encabezado de métrica existente, se reemplaza y al arrastrar una métrica junto a un encabezado, puede ver ambas métricas en paralelo.

## Uso de métricas en Analysis Workspace

Las métricas se pueden utilizar de varias formas dentro de Analysis Workspace. Para obtener información acerca de cómo agregar métricas y otros tipos de componentes a Analysis Workspace, vea [Usar componentes en Analysis Workspace](/help/components/use-components-in-workspace.md).

## Métricas calculadas 

Las métricas calculadas permiten ver fácilmente cómo se relacionan entre sí las métricas mediante operadores simples o funciones estadísticas. Existen varias formas de crear métricas calculadas:

Puede seleccionar **[!UICONTROL Componentes]** > **[!UICONTROL Métricas calculadas]**. Esto lo lleva al [Creador de métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md), donde puede generar métricas personalizadas a partir de las ya existentes.

Con el fin de facilitar la creación rápida de métricas calculadas, se ha añadido la opción **[!UICONTROL Crear métrica a partir de la selección]** al menú de columna que se abre al hacer clic con el botón secundario en las tablas improvisadas. Esta opción se muestra cuando se selecciona al menos una celda de columna de encabezado.

![Panel de Workspace resaltando Crear a partir de la selección](assets/create-metric-from-selection.png)

[Métricas calculadas: métricas sin implementación](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=es) (3:42)

## Comparar métricas con diferentes modelos de atribución

Si quiere comparar rápida y fácilmente un modelo de atribución con otro, haga clic con el botón secundario en una métrica y seleccione **[!UICONTROL Comparar modelos de atribución]**:

![Resaltar el panel de Workspace Comparar modelos de atribución](assets/compare-attribution.png)

Este método abreviado permite comparar rápida y fácilmente un modelo de atribución con otro sin tener que arrastrar una métrica y configurarla dos veces.
