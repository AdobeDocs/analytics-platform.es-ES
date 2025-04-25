---
title: Selección de un intervalo de fechas en Report Builder en Customer Journey Analytics
description: Describe cómo utilizar el calendario, las fechas móviles y las expresiones personalizadas en Report Builder for Customer Journey Analytics
role: User
feature: Report Builder
type: Documentation
exl-id: 7252214f-a7d6-451b-99c9-d39e8e47120b
solution: Customer Journey Analytics
source-git-commit: 9794779894fbecb433c16d108c555c5f81a4b491
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 49%

---

# Seleccionar un intervalo de fecha

Para cambiar el intervalo de fechas de un bloque de datos existente:

- Seleccione **[!UICONTROL Editar un bloque de datos]** o
- Seleccione el vínculo **[!UICONTROL Intervalo de fecha]** en **[!UICONTROL Edición rápida]**.

Utilice las siguientes opciones para cambiar el intervalo de fechas de un bloque de datos.

## Calendario

La opción **[!UICONTROL Calendario]** le permite crear fechas estáticas o móviles mediante las siguientes opciones:

### Intervalo de fechas

El campo intervalo de fechas muestra el intervalo de fechas actual para la solicitud de bloque de datos. Puede introducir fechas directamente o usar ![Calendario](/help/assets/icons/Calendar.svg) para especificar un intervalo de fechas.

![Calendario de intervalo de fechas](assets/date-range-calendar.png){zoomable="yes"}

### Ajustes preestablecidos

Utilice el menú desplegable de ajustes preestablecidos para seleccionar un ajuste preestablecido. También puede introducir texto para buscar ajustes preestablecidos.

![Ajustes preestablecidos de intervalo de fecha](assets/date-range-presets.png){zoomable="yes"}

El menú desplegable de ajustes preestablecidos incluye un conjunto estándar de intervalos de fechas preestablecidos y componentes de intervalo de fechas para una vista de datos que haya guardado o una vista de datos que se haya compartido con usted.

### Fechas móviles

Para definir fechas móviles:

![Fechas móviles de EE. UU.](assets/date-range-rolling-date.png){zoomable="yes"}

1. Seleccione **[!UICONTROL Usar fechas móviles]** para definir la lógica de una definición de fecha móvil. Puede seleccionar el texto entre corchetes (por ejemplo **[!UICONTROL inicio fijo - desplazamiento diario]**) para ampliar el panel y especificar detalles para **[!UICONTROL Inicio]** y **[!UICONTROL Fin]**.

1. Selecciona **[!UICONTROL Inicio de]**, **[!UICONTROL Fin de]** o **[!UICONTROL Día fijo]**.

   - Cuando hayas seleccionado **[!UICONTROL Inicio de]** o **[!UICONTROL Final de]**, puedes generar una expresión completa. Por ejemplo: **[!UICONTROL Fin de]** **[!UICONTROL año actual]** **[!UICONTROL más]** `1` **[!UICONTROL día]**. Elige el valor apropiado para cada parte individual de la expresión.

      - Selecciona valor para actual. Por ejemplo, **[!UICONTROL año actual]**.
      - Seleccione un valor para un cálculo adicional opcional. Por ejemplo, **[!UICONTROL plus]**.
      - Cuando haya especificado un cálculo adicional, especifique un valor. Por ejemplo, `1`.
      - Cuando haya especificado un cálculo adicional, seleccione el período de tiempo que desea utilizar para el cálculo. Por ejemplo, **[!UICONTROL día]**.

   - Cuando haya seleccionado **[!UICONTROL Día fijo]**, especifique un día fijo o use el selector para seleccionar un día.

1. Seleccione **[!UICONTROL ocultar]** para ocultar los detalles del cálculo de fechas móviles.


### Expresiones personalizadas

La opción de expresión personalizada permite cambiar el intervalo de fechas creando una expresión personalizada o introduciendo una fórmula aritmética.

![Expresión personalizada de intervalo de fecha](assets/date-range-custom-expression.png){zoomable="yes"}

1. Seleccione **[!UICONTROL Usar fechas móviles]**.

1. Seleccione **[!UICONTROL Utilizar expresión personalizada]**.

   Al seleccionar **[!UICONTROL Usar expresión personalizada]**, los controles de intervalo de fechas móviles estándar están deshabilitados.

1. Escriba una [expresión personalizada](#create-a-custom-expression).

1. Use **[!UICONTROL Vista previa de fecha]** para comprobar el intervalo de fecha resultante.

#### Creación de una expresión personalizada

1. Escriba una [referencia de fecha](#date-references).

1. Agregue un [operador de fecha](#date-operators) opcional para mover la fecha al pasado o al futuro.

Puede escribir una expresión personalizada que incluya varios operadores, como `tm-11m-1d`.

#### Referencias de fechas

En la tabla siguiente se muestran ejemplos de referencia de fechas.

| Referencia de fecha | Tipo | Descripción |
|----------------|--------------|----------------------------|
| `1/1/10` | Fecha estática | Introducido en formato de fecha ISO |
| `td` | Fecha móvil | Inicio del día actual |
| `tw` | Fecha móvil | Inicio de la semana actual |
| `tm` | Fecha móvil | Inicio del mes actual |
| `tq` | Fecha móvil | Inicio del trimestre actual |
| `ty` | Fecha móvil | Inicio del año actual |

#### Operadores de fechas

En la tabla siguiente se muestran ejemplos de operadores de fecha.

| Operador de fecha | Unidad | Descripción |
|----------------|---------|--------------------|
| `+6d` | Día | Añadir 6 días a la referencia de fecha |
| `+1w` | Semana | Añadir una semana completa a la referencia de fecha |
| `-2m` | Mes | Restar 2 meses completos a la fecha de referencia |
| `-4q` | Trimestre | Restar 4 trimestres a la referencia de fecha |
| -`1y` | Año | Restar un año a la fecha de referencia |

#### Expresiones de fecha

En la tabla siguiente se muestran ejemplos de expresiones de fecha.

| Expresión de fecha | Significado |
|-----------------|--------------------------------------|
| `td` | Hoy |
| `td-1w` | Primer día de la semana pasada |
| `tm-1d` | Último día del mes anterior |
| `td-52w` | Mismo día hace 52 semanas |
| `tm-11m-1d` | Último día del mismo mes del año pasado |
| `"2020-09-06"` | Fecha específica, 9 de septiembre de 2020 |



## Intervalo de fechas de la celda

El intervalo de fechas se puede especificar en celdas de hoja de cálculo. Utilice la opción **[!UICONTROL Intervalo de fechas de la celda]** para elegir las fechas de inicio y finalización del bloque de datos de las celdas seleccionadas. Al seleccionar la opción **[!UICONTROL Desde la celda]**, el panel muestra los campos **[!UICONTROL Desde]** y **[!UICONTROL Hasta]**, en los que puede especificar la ubicación de una celda o usar ![SelectorDeBloquesDeDatos](/help/assets/icons/DataBlockSelector.svg) para elegir la celda seleccionada actualmente.

![Seleccionar de la celda Hoja1!H4 a Hoja1!I4](./assets/date-range-from-cell.png){zoomable="yes"}


## Excluir hoy

Seleccione **[!UICONTROL Excluir hoy]** para excluir hoy de un intervalo de fechas seleccionado. El día actual se excluye de todos los modos utilizados para definir un intervalo de fechas: calendario, fechas móviles o expresiones personalizadas.


## Intervalos de fechas válidos

La siguiente lista describe formatos de intervalo de fechas válidos.

- Las fechas de inicio y finalización deben tener el siguiente formato: AAAA-MM-DD

- La fecha de inicio debe ser anterior o igual a la fecha de finalización. Ambas fechas se pueden configurar en el futuro.

- Al utilizar fechas móviles, la fecha de inicio debe ser hoy o en el pasado. El día de inicio debe ser anterior si se selecciona **[!UICONTROL Excluir hoy]**.

- Puede crear un intervalo de fecha estático definido para el futuro. Por ejemplo: es posible que necesite establecer una fecha futura para el inicio de una campaña de marketing la semana que viene. Esta opción crea una monitorización de libro para una campaña con antelación.

## Cambio del intervalo de fechas

Puede editar el intervalo de fechas de un bloque de datos existente.

1. Seleccione una celda del bloque de datos.

- Seleccione **[!UICONTROL Editar bloque de datos]** en el panel **[!UICONTROL Comandos]** o
- Seleccione el vínculo **[!UICONTROL Intervalo de fecha]** en el panel **[!UICONTROL Edición rápida]**.

1. Modifique el intervalo de fechas utilizando cualquiera de las opciones de selección de fechas disponibles.

1. Seleccione **[!UICONTROL Aplicar]**.

Report Builder aplica el nuevo intervalo de fechas a todos los bloques de datos de la selección.
