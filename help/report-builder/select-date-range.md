---
title: Cómo seleccionar un intervalo de fecha en el Report Builder de Customer Journey Analytics
description: Describe cómo utilizar el calendario, las fechas móviles y las expresiones personalizadas en Report Builder for Customer Journey Analytics
role: User
feature: Report Builder
type: Documentation
exl-id: 7252214f-a7d6-451b-99c9-d39e8e47120b
solution: Customer Journey Analytics
source-git-commit: c56c77079aa21fb740fda6bec333731a1f82a48f
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 87%

---

# Selección de un intervalo de fechas

Para cambiar el intervalo de fechas de un bloque de datos existente, seleccione Editar un bloque de datos o utilice el panel EDICIÓN RÁPIDA.

Utilice las siguientes opciones para cambiar el intervalo de fechas de un bloque de datos.

**Calendario**

El calendario le permite crear fechas estáticas o móviles mediante las siguientes opciones:

- Campo de intervalo de fechas
- Calendario
- Menú desplegable de ajustes preestablecidos
- Modo de fecha móvil
- Personalización de expresiones


**Desde celda**

La opción Desde celda permite hacer referencia a las fechas introducidas en las celdas de la hoja de cálculo.

Tiene la opción de excluir hoy en cualquier intervalo de fechas seleccionado.

![Panel de edición rápida del Report Builder con el calendario seleccionado y Excluir hoy seleccionado.](./assets/image17.png)

## Usar el calendario

Al usar la variable **Calendario**, el campo intervalo de fechas muestra el intervalo de fechas actual para la solicitud de bloque de datos. Puede introducir fechas directamente en el campo de intervalo de fechas o utilizar una opción de selección de intervalo de fechas.

### Campo de intervalo de fechas

Introducir fechas directamente en el campo de intervalo de fechas

1. Haga clic en el campo de intervalo de fecha situado junto al icono de calendario.

1. Introduzca las fechas de inicio y finalización del intervalo de fecha.

### Calendario

Para seleccionar fechas utilizando el calendario

1. Haga clic en el icono de calendario para mostrar un calendario mensual.

1. Haga clic en una fecha de inicio.

1. Haga clic en una fecha de finalización.

Para definir un intervalo de fechas al revés, haga clic primero en la fecha de finalización y, a continuación, haga clic en la fecha de inicio.

![panel de intervalo de fechas del Report Builder que muestra el calendario, la fecha de finalización y la fecha de inicio seleccionada.](./assets/image18.png)

### Menú desplegable de ajustes preestablecidos

El menú desplegable de ajustes preestablecidos incluye un conjunto estándar de intervalos de fechas preestablecidos y componentes de intervalo de fechas para una vista de datos que haya guardado o una vista de datos que se haya compartido con usted.

### Fechas móviles

La opción fechas móviles permite seleccionar un intervalo de fechas mediante fechas móviles.

1. Seleccione **Usar fechas móviles**.

1. Seleccione una expresión móvil para la fecha de inicio o de finalización.

   ![Panel de intervalo de fechas del Report Builder que muestra Usar fechas móviles seleccionadas y la expresión móvil.](./assets/image19.png)

   **Inicio de**: permite seleccionar el comienzo de un día, una semana, un mes, un trimestre o un año.

   **Final de**: permite seleccionar el final de un día, una semana, un mes, un trimestre o un año.

   **Día fijo**: permite fijar una fecha de inicio o de finalización mientras la otra fecha es móvil.

1. Elija día, semana, mes, trimestre o año como período móvil.

   ![panel de intervalo de fechas del Report Builder que muestra el día actual seleccionado.](./assets/image20.png)

1. Añada o reste días, semanas, meses, trimestres o años a partir de la fecha móvil.

   ![panel de intervalo de fechas del Report Builder que muestra el día actual más 14 días seleccionados.](./assets/image21.png)

1. Haga clic en Next para definir el intervalo de fechas.

   Utilice la vista previa de fecha para confirmar que el intervalo de fecha resultante es el deseado.

### Expresiones personalizadas

La opción de expresión personalizada permite cambiar el intervalo de fechas creando una expresión personalizada o introduciendo una fórmula aritmética.

1. Seleccione **Usar fechas móviles**.

1. Seleccione **Utilizar expresión personalizada**.

   Al seleccionar la variable **Utilizar expresión personalizada**, los controles de intervalo de fechas móviles estándar están desactivados.

   ![Seleccione Usar expresión personalizada que muestre tm-1m a td-1d.](./assets/custom_expression.png)

1. Introduzca una expresión personalizada.

   Para ver una lista de expresiones personalizadas de ejemplo, consulte **Expresiones de fecha**.

1. Utilice la vista previa de fecha para comprobar que el intervalo de fecha resultante es el deseado.

#### Creación de una expresión personalizada

1. Escriba una **Referencia de fecha**.

1. Añada **Operadores de fecha** para mover la fecha al pasado o al futuro.

Puede introducir una expresión de fecha personalizada que incluya varios operadores, como ```tm-11m-1d```.

#### Referencias de fechas

En la tabla siguiente se muestran ejemplos de referencia de fechas.

| Referencia de fecha | Tipo | Descripción |
|----------------|--------------|----------------------------|
| 1/1/10 | Fecha estática | Introducido en formato de fecha ISO |
| td | Fecha móvil | Inicio del día actual |
| tw | Fecha móvil | Inicio de la semana actual |
| tm | Fecha móvil | Inicio del mes actual |
| tq | Fecha móvil | Inicio del trimestre actual |
| ty | Fecha móvil | Inicio del año actual |

#### Operadores de fechas

En la tabla siguiente se muestran ejemplos de operadores de fecha.

| Operadores de fechas | Unidad | Descripción |
|----------------|---------|--------------------|
| +6d | Día | Añadir 6 días a la referencia de fecha |
| +1w | Semana | Añadir una semana completa a la referencia de fecha |
| -2m | Mes | Restar 2 meses completos a la fecha de referencia |
| -4q | Trimestre | Restar 4 trimestres a la referencia de fecha |
| -1y | Año | Restar un año a la fecha de referencia |

#### Expresiones de fecha

En la tabla siguiente se muestran ejemplos de expresiones de fecha.

| Expresión de fecha | Significado |
|-----------------|--------------------------------------|
| td-1w | Primer día de la semana pasada |
| tm-1d | Último día del mes anterior |
| td-52w | Mismo día hace 52 semanas |
| tm-11m-1d | Último día del mismo mes del año pasado |
| &quot;2020-09-06&quot; | 9 de septiembre de 2020 |

## Intervalo de fechas de la celda

El intervalo de fechas se puede especificar en celdas de hoja de cálculo. Utilice la variable **Intervalo de fechas de la celda** para elegir las fechas de inicio y finalización del bloque de datos de las celdas seleccionadas. Al seleccionar la variable **Desde celda**, se muestran en el panel los campos **De** y **Hasta**, en los que se puede introducir una ubicación de celda.

![Seleccionar de la celda Hoja1!H4 a Hoja1!I4](./assets/image23.png)

## Excluir hoy

Elija la opción **Excluir hoy** para excluir hoy de un intervalo de fechas seleccionado. Si elige incluir hoy, es posible que se estén extrayendo datos incompletos para hoy.

Si se selecciona, la variable **Excluir hoy** excluye el día actual de todos los modos de intervalo de fechas, incluidos el calendario, las fechas móviles o las expresiones personalizadas.

## Intervalos de fechas válidos

La siguiente lista describe formatos de intervalo de fechas válidos.

- Las fechas de inicio y finalización deben tener el siguiente formato: AAAA-MM-DD

- La fecha de inicio debe ser anterior o igual a la fecha de finalización. Ambas fechas se pueden configurar en el futuro.

- Al utilizar fechas móviles, la fecha de inicio debe ser hoy o en el pasado. Debe ser en el pasado si **Excluir hoy** está activado.

- Puede crear un intervalo de fecha estático definido para el futuro. Por ejemplo: es posible que necesite establecer una fecha futura para el inicio de una campaña de marketing la semana que viene. Esta opción crea una monitorización de libro para una campaña con antelación.

## Cambio del intervalo de fechas

Puede editar el intervalo de fechas de un bloque de datos existente seleccionando Editar bloque de datos en el panel COMANDOS o el vínculo Intervalo de fecha en el panel EDICIÓN RÁPIDA.

**Editar bloque de datos**: permite editar varios parámetros de bloque de datos, incluido el intervalo de fechas, para un solo bloque de datos.

**Edición rápida: Intervalo de fechas**: permite editar el intervalo de fechas de uno o más bloques de datos.

Para editar el intervalo de fecha desde el panel EDICIÓN RÁPIDA

1. Seleccionar celdas dentro de uno o más bloques de datos de una hoja de cálculo.

1. Haga clic en el vínculo **Intervalo de fecha** en el panel EDICIÓN RÁPIDA.

1. Seleccione el intervalo de fecha utilizando cualquiera de las opciones de selección de fechas.

1. Haga clic en **Aplicar**.


Report Builder aplica el nuevo intervalo de fechas a todos los bloques de datos de la selección.
