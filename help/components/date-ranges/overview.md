---
description: Utilice el calendario y los intervalos de fechas para especificar intervalos de fechas en Analysis Workspace.
title: Información general sobre los intervalos de fechas
feature: Calendar
exl-id: 99b31bd9-32f1-4da1-9e47-6d90c66282c5
role: User
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 100%

---

# Información general sobre los intervalos de fechas

En un proyecto de Workspace, normalmente se usa el [calendario de un panel](/help/analysis-workspace/c-panels/panels.md#calendar) para especificar el intervalo de fechas para las visualizaciones de ese panel.

Los componentes de intervalo de fechas le permiten definir y anular la configuración de calendario del panel.

## Usar intervalos de fechas

Puede utilizar un componente de intervalo de fechas para redefinir el calendario del panel.

O bien, puede utilizar un intervalo de fechas en una tabla de forma libre como una métrica o dimensión.

![Uso del intervalo de fechas](/help/components/date-ranges/assets/date-ranges-usage.png)

- **Métrica**.  Por ejemplo, para comparar una dimensión durante dos meses diferentes para una métrica específica.
- **Dimensión**.  Para comparar una métrica en diferentes elementos de dimensión para la dimensión de intervalo de fechas.

>[!NOTE]
>
>Cuando se utilizan intervalos de fechas en una tabla de forma libre, los intervalos de fechas anulan el calendario especificado para el panel al que pertenece la tabla de forma libre.
>

Use un intervalo de fechas como lo [haría con cualquier componente](/help/components/overview.md#analysis-workspace-components). Arrastre el intervalo de fechas desde el panel de componente ![Calendario](/help/assets/icons/Calendar.svg) **[!UICONTROL Intervalos de fechas]** y suelte el componente en:

- **[!UICONTROL Calendario]**: ![Cambiar](/help/assets/icons/Switch.svg) **[!UICONTROL Sustituya]** la configuración actual del calendario por el intervalo de fechas.
- **Encabezado de la columna de métrica**:![Cambiar](/help/assets/icons/Switch.svg) **[!UICONTROL Sustituya]** la métrica, ![Añadir](/help/assets/icons/Add.svg)**[!UICONTROL Añada ]**el intervalo de fechas como métrica o ![Filtrar](/help/assets/icons/Filter.svg)**[!UICONTROL  Filtre ]**la métrica mediante el componente de intervalo de fechas.
- **Encabezado de la columna de Dimension**: ![Cambiar](/help/assets/icons/Switch.svg) **[!UICONTROL Reemplace]** las dimensiones actuales. La nueva dimensión ahora es **[!UICONTROL Intervalos de fechas]**. Cuando la dimensión sea Intervalos de fechas, podrá ![Añadir](/help/assets/icons/Add.svg)**[!UICONTROL Añadir ]**intervalos de fechas adicionales como elementos de dimensión.
- **Elemento de dimensión**: Realice un ![Desglose](/help/assets/icons/Breakdown.svg) **[!UICONTROL Desglose]** del elemento de dimensión específico por el intervalo de fechas.

También puede añadir una columna de intervalo de fechas directamente en una visualización de tabla de forma libre:

1. En una columna de métrica, seleccione en el menú contextual:

   - **[!UICONTROL Añadir columna de período de tiempo]**. Puede seleccionar entre las opciones sugeridas que se basan en el calendario actual o crear un [intervalo de fechas personalizado](#custom-date-ranges).
   - **[!UICONTROL Comparar períodos de tiempo]** Puede seleccionar entre una opción sugerida basada en el calendario actual o crear un [intervalo de fechas personalizado](#custom-date-ranges).

1. En función de su selección, se añadirán columnas de intervalo de fechas adicionales a la tabla de forma libre.

## Intervalos de fechas no compatibles

Analysis Workspace proporciona una serie de intervalos de fechas predeterminados.


| Día | Semana | Mes | Trimestre | Año |
|---|---|---|---|---|
| Hoy | Esta semana | Este mes | Este trimestre | Este año |
| Ayer | Esta semana (sin incluir hoy) | Este mes (sin incluir hoy) | Este trimestre (sin incluir hoy) | Este año (sin incluir hoy) |
| Hace 2 días | Hace 2 semanas | Hace 2 meses |   |  |
| Hace 3 días | Hace 3 semanas | Hace 3 meses  |  | |
| Últimos 7 días | Semana pasada | Mes pasado | Último trimestre | Año pasado |
| Últimos 14 días | Últimas 2 semanas completas | 2 últimos meses completos | Últimos 4 trimestres completos | |
| Últimos 30 días | Últimas 3 semanas completas | 3 últimos meses completos | | |
| Últimos 60 días | Últimas 4 semanas completas | 6 últimos meses completos | | |
| Últimos 90 días | Últimas 12 semanas completas | 12 últimos meses completos | | |
| Últimos 7 días completos | Últimas 52 semanas completas | 13 últimos meses completos | | |
| Últimos 14 días completos | | | | |
| Últimos 30 días completos | | | | |
| Últimos 90 días completos | | | | |

<table style="table-layout:fixed">

## Intervalos de fechas personalizados

Puede crear sus propios intervalos de fechas personalizados. Consulte [Crear intervalo de fechas](/help/components/date-ranges/create.md) para ver las distintas opciones disponibles para crear intervalos de fechas. A continuación, puede generar, modificar y guardar intervalos de fechas en el [Generador de intervalos de fechas](create.md#date-range-builder).

Utilice el [administrador de intervalos de fechas](manage.md) para administrar los intervalos de fechas.
