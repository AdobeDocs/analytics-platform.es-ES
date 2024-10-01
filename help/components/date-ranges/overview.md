---
title: Información general sobre los intervalos de fechas
description: Aprenda qué son los intervalos de fechas y cómo puede utilizarlos en el sistema de informes.
feature: Calendar
exl-id: 99b31bd9-32f1-4da1-9e47-6d90c66282c5
role: User
source-git-commit: 747e77b964006404d70b500b28ec44005d65d944
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 21%

---

# Información general sobre los intervalos de fechas

En un proyecto de Workspace, normalmente se usa el calendario [en un panel](/help/analysis-workspace/c-panels/panels.md#calendar) para especificar el intervalo de fechas para las visualizaciones de ese panel.

Los componentes de intervalo de fechas permiten definir y anular la configuración de calendario del panel.

<!-- Very old video, should we show it?

+++ View a video illustrating use of calendar and date ranges

>[!VIDEO](https://video.tv.adobe.com/v/24136?format=jpeg)

{{videoaa}}
+++

-->

## Usar intervalos de fechas

Puede utilizar un componente de intervalo de fechas para redefinir el calendario del panel.

O bien, puede utilizar un intervalo de fechas en una tabla de forma libre como métrica o dimensión.

![Uso del intervalo de fechas](/help/components/date-ranges/assets/date-ranges-usage.png)

- **Métrica**. Por ejemplo, para comparar una dimensión de dos meses diferentes para una métrica específica.
- **Dimension**. Para comparar una métrica en diferentes elementos de dimensión para la dimensión de intervalo de fechas.

>[!NOTE]
>
>Cuando se utilizan intervalos de fechas en una tabla de forma libre, los intervalos de fechas anulan el calendario especificado para el panel al que pertenece la tabla de forma libre.
>

Usa un intervalo de fecha como lo haría [con cualquier componente](/help/components/overview.md#analysis-workspace-components). Arrastre el intervalo de fechas desde el panel de componente ![Calendario](/help/assets/icons/Calendar.svg) **[!UICONTROL Intervalos de fechas]** y suelte el componente en:

- **[!UICONTROL Calendario]**: Ha ![cambiado](/help/assets/icons/Switch.svg) **[!UICONTROL Reemplaza]** la configuración actual del calendario con el intervalo de fechas.
- **Encabezado de columna de métrica**: Ha ![cambiado](/help/assets/icons/Switch.svg) **[!UICONTROL reemplazado]** la métrica, ha ![agregado](/help/assets/icons/Add.svg)**[!UICONTROL agregado ]**el intervalo de fecha como métrica o ha ![filtrado](/help/assets/icons/Filter.svg)**[!UICONTROL  filtrado ]**la métrica mediante el componente de intervalo de fecha.
- **Encabezado de columna de Dimension**: Usted ![Cambia](/help/assets/icons/Switch.svg) **[!UICONTROL Reemplaza]** las dimensiones actuales. La nueva dimensión ahora es **[!UICONTROL Intervalos de fechas]**. Una vez que la dimensión sea Intervalos de fechas, puede ![Agregar](/help/assets/icons/Add.svg)**[!UICONTROL Agregar ]**intervalos de fechas adicionales como elementos de dimensión.
- **elemento del Dimension**: ha ![Desglose](/help/assets/icons/Breakdown.svg) **[!UICONTROL Desglose]** el elemento de dimensión específico por el intervalo de fechas.

También puede agregar una columna de intervalo de fechas directamente en una visualización de tabla de forma libre:

1. En una columna de métrica, seleccione en el menú contextual:

   - **[!UICONTROL Agregar columna de período de tiempo]**. Puede seleccionar entre las opciones sugeridas que se basan en el calendario actual o crear un [intervalo de fechas personalizado](#custom-date-ranges).
   - **[!UICONTROL Comparar periodos de tiempo]**. Puede seleccionar entre una opción sugerida basada en el calendario actual o crear un [intervalo de fechas personalizado](#custom-date-ranges).

1. En función de su selección, se agregarán columnas de intervalo de fechas adicionales a la tabla de forma libre.

## Intervalos de fechas predeterminados

Analysis Workspace proporciona una serie de intervalos de fechas predeterminados.


| Día | Semana | Mes | Trimestre | Año |
|---|---|---|---|---|
| Hoy | Esta semana | Este mes | Este trimestre | Este año |
| Ayer | Esta semana (sin incluir hoy) | Este mes (sin incluir hoy) | Este trimestre (sin incluir hoy) | Este año (sin incluir hoy) |
| Hace 2 días | Hace 2 semanas | Hace 2 meses |   |  |
| Hace 3 días | Hace 3 semanas | Hace 3 meses |  | |
| Últimos 7 días | Última semana | Mes pasado | Último trimestre | Último año |
| Últimos 14 días | Últimas 2 semanas completas | Los últimos 2 meses completos | Últimos 4 trimestres completos | |
| Últimos 30 días | Últimas 3 semanas completas | Los últimos 3 meses completos | | |
| Últimos 60 días | Últimas 4 semanas completas | Los últimos 6 meses completos | | |
| Últimos 90 días | Últimas 12 semanas completas | Los últimos 12 meses completos | | |
| Últimos 7 días completos | Últimas 52 semanas completas | Los últimos 13 meses completos | | |
| Últimos 14 días completos | | | | |
| Últimos 30 días completos | | | | |
| Últimos 90 días completos | | | | |

<table style="table-layout:fixed">

## Intervalos de fechas personalizados

Puede crear sus propios intervalos de fechas personalizados. Consulte [Crear intervalo de fechas](/help/components/date-ranges/create.md) para ver las distintas opciones disponibles para crear intervalos de fechas. A continuación, genere, modifique y guarde intervalos de fechas en el [Generador de intervalos de fechas](create.md#date-range-builder).

Usa el [administrador de intervalos de fechas](manage.md) para administrar los intervalos de fechas.
