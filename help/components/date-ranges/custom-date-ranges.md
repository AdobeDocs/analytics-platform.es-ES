---
description: Cree intervalos de fechas personalizados en Analysis Workspace y guárdelos como componentes de tiempo.
keywords: Analysis Workspace
title: Crear intervalos de fechas
feature: Calendar
exl-id: 1a7df63a-bf18-4c38-b7e2-e83c2d278544
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 85%

---

# Crear intervalos de fechas

Cree intervalos de fechas personalizados en Analysis Workspace y guárdelos como componentes de tiempo.

**[!UICONTROL Componentes]** > **[!UICONTROL Nuevo intervalo de fechas]**

Se aplica un intervalo de fechas en el panel. Para agregar un intervalo de fechas al proyecto, haga clic en **Paneles** > *`<select panel>`* y especifique el nuevo intervalo.

## Intervalo de fechas para “Dos meses atrás” 

El siguiente intervalo de fechas personalizado muestra un intervalo de fechas para “dos meses atrás”, con una visualización de cambio de resumen que muestra el cambio direccional.

![Generador de intervalos de fechas que muestra las fechas móviles de uso de hace dos meses](assets/date-range-two-months-ago.png)

El intervalo de fechas personalizado se muestra en la parte superior del panel de componente [!UICONTROL Intervalo de fechas] del proyecto:

![Panel de componente Intervalo de fechas con una flecha que señala a Hace dos meses.](assets/date-range-panel-two-months-ago.png)

Puede arrastrar este intervalo de fechas personalizado en un columna a lo largo de un intervalo de fechas móvil mensual mediante el valor preestablecido Último mes para ver una comparación. Agregue una visualización de cambio de resumen y seleccione los totales de cada columna para mostrar un cambio direccional:

![Cambio de resumen que muestra un aumento del 14,45%.](assets/date-range-two-months-table.png)

## Usar un intervalo de fechas móvil de 7 días

Se aplica un intervalo de fechas al nivel de panel. Para agregar un intervalo de fechas al proyecto, haga clic en **Acciones** > **Agregar panel**, y especifique el nuevo intervalo de fechas.

En el Generador de intervalos de fechas, puede crear un intervalo de fechas personalizado que se muestra en el panel Componentes con otros intervalos de fechas.

Por ejemplo, puede crear un intervalo de fechas que especifica una ventana móvil de 7 días y que termina una semana atrás:

![Generador de intervalos de fechas que muestra un intervalo de fechas que especifica una ventana móvil de 7 días.](assets/create_date_range.png)

Uso *`rolling daily`*.

* La configuración de inicio sería *`current day minus 14 days`*.

* La configuración de fin sería *`current day minus 7 days`*.

Este intervalo de fechas puede ser un componente que arrastre en cualquier tabla de forma libre.
