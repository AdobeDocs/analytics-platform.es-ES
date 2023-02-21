---
description: En el calendario, se pueden indicar fechas e intervalos de fechas o seleccionar ajustes preestablecidos.
title: Resumen de calendario e intervalos de fechas
feature: Calendar
solution: Customer Journey Analytics
exl-id: 4afdc68b-97f8-4d8a-9d13-e2f3986873f1
source-git-commit: 524aed20a62b8d8648230be81c63f9c58c84ae87
workflow-type: tm+mt
source-wordcount: '822'
ht-degree: 45%

---

# Resumen de calendario e intervalos de fechas

En el calendario, se pueden indicar fechas e intervalos de fechas o seleccionar ajustes preestablecidos.

Las selecciones de calendario se aplican a nivel de panel, pero tiene la opción de aplicarlas a todos los paneles. Al hacer clic en un intervalo de fechas en Workspace, la interfaz muestra el mes natural actual y el mes natural anterior. Puede ajustar estos dos calendarios haciendo clic en las flechas derecha e izquierda de cada esquina superior respectiva.

![Calendario](assets/aw_calendar2.png){width="60%"}

El primer clic en un calendario inicia una selección de intervalo de fechas. El segundo clic completa una selección de intervalo de fechas, que se resalta. Si la tecla `Shift` se mantiene pulsada (o se utiliza el clic derecho), se anexa al rango seleccionado actualmente.

También puede arrastrar fechas (y dimensiones temporales) a un proyecto de Workspace. Se pueden seleccionar fechas, semanas, meses o años concretos, o bien fechas móviles.

[Uso de intervalos de fechas y calendarios en Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-dates-in-analysis-workspace.html?lang=es) (4:07)

| Configuración | Descripción |
| --- | --- |
| Días seleccionados | Días/semanas/meses/años seleccionados |
| Usar fechas móviles | Las fechas móviles le permiten generar un informe dinámico que observa un periodo de tiempo anterior o posterior basándose en el momento en el que ejecuta el informe. Por ejemplo, si desea un informe sobre todos los pedidos realizados el “último mes” (basándose en el campo Fecha de creación) y se ejecuta dicho informe en diciembre, verá los pedidos realizados en noviembre. Si ejecutara ese mismo informe en enero, vería los pedidos realizados en diciembre.<ul><li>**[!UICONTROL Vista previa de fecha]**: indica qué periodo de tiempo incluye el calendario móvil.</li><li>**[!UICONTROL Inicio]**: puede elegir entre el día, la semana, el mes, el trimestre o el año actuales.</li><li>**[!UICONTROL Fin]**: puede elegir entre el día, la semana, el mes, el trimestre o el año actuales.</li></ul>Por ejemplo, consulte [este enlace](/help/components/date-ranges/custom-date-ranges.md). |
| Intervalo de fechas | Le permite seleccionar un rango de fechas preestablecido. La opción predeterminada es los últimos 30 días. **[!UICONTROL Esta semana, mes, trimestre o año (excluido hoy)]** le permite elegir entre intervalos de fechas que no incluyen datos de día parcial de hoy. |
| Aplicar a todos los paneles | No solo le permite cambiar el intervalo de fechas seleccionado para el panel actual, sino también para todos los demás paneles dentro del proyecto. |
| Aplicar | Aplica el rango de fechas únicamente a este panel. |

## Acerca de los intervalos de fechas del panel relativo {#relative-panel-dates}

Si está trabajando en Workspace, puede hacer que los componentes del intervalo de fechas sean relativos al calendario del panel. Tres casos de uso habituales en los que las fechas relativas del panel surten efecto son los gráficos combinados, el resumen de métricas clave y los intervalos de fechas de la tabla improvisada.

Usar intervalos de fechas del panel relativo

1. Seleccione el **Espacio de trabajo** pestaña .
1. Seleccione **Proyecto en blanco**.
1. Agregue dimensiones, métricas y segmentos desde el carril izquierdo.
1. Haga clic en el campo Intervalo de fechas del panel para alternar el valor del intervalo de fechas del panel relativo.
1. Select **Conversión de componentes de intervalo de fechas en relación con el calendario del panel**.
   * Seleccione la opción para que los componentes del intervalo de fechas sean relativos al calendario del panel.
Si se seleccionan fechas relativas, las fechas móviles se basarán en la fecha de inicio del calendario del panel y no en la fecha actual.
   * Si esta opción no está seleccionada, las fechas móviles se basarán en la fecha actual.

   ![fechas relativas del panel](assets/relative-date-selected.png){width="60%"}

1. Haga clic en **Aplicar**.
Las fechas relativas se muestran en la esquina superior derecha.

   ![fechas relativas en forma libre ](assets/relative-date-range1.png)

## Pautas para intervalos de fechas relativos del panel {#guidelines}

Tenga en cuenta las siguientes directrices cuando utilice intervalos de fechas relativos del panel.

### Fórmulas e intervalos de fechas relativos {#formula-relative-dates}

Si tiene seleccionadas fechas relativas, todas las fórmulas de fecha utilizarán la fecha de inicio del panel como punto de partida.

### Calendarios personalizados e intervalos de fechas relativos {#custom-calendar-formulas}

Cuando se usa un calendario personalizado basado en semanas y se agregan meses o años, la fórmula calcula el desplazamiento del día en un periodo determinado. La fecha real puede ser diferente debido al desplazamiento. La fórmula elige el aterrizaje del día en el mismo lugar del calendario personalizado. Por ejemplo, el tercer viernes de la tercera semana en un calendario personalizado.

### Acerca de los segmentos que utilizan fechas móviles e intervalos de fechas del panel relativo {#segments-relative-dates}

Si genera un segmento o utiliza un segmento con una fecha móvil, por ejemplo, los últimos 7 días o las últimas 2 semanas, y hace clic en la vista previa del segmento, se iniciará la fecha móvil desde *Hoy* en lugar de la fecha de inicio del panel. Como resultado, la vista previa del segmento no coincidirá cuando realmente utilice el segmento en la tabla. La vista previa se ve afectada, no el propio segmento.

## Pautas para intervalos de fechas y vistas previas en el panel {#guidelines-panel-dates}

* A partir de la versión de febrero, las vistas previas de componentes y datos se basarán en el intervalo de fechas del panel y no en los últimos 90 días.
* Todos los componentes enumerados en el carril izquierdo estarán disponibles en función del intervalo de fechas del panel.
* Todas las vistas previas de fechas del segmento y los creadores de métricas calculadas se basarán en el intervalo de fechas del panel (a menos que se acceda desde los administradores de componentes, que no tienen un panel asociado, se basarán en los últimos 90 días).
* Cualquier vista previa de datos mostrará datos o componentes en función del intervalo de fechas del panel.