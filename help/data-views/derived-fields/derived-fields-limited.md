---
title: Campos derivados
description: Un campo derivado especifica la manipulación durante el tiempo del informe de los campos de esquema y/o los componentes estándar a través de un conjunto de funciones disponibles y plantillas de funciones.
solution: Customer Journey Analytics
feature: Derived Fields
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 1b81b0fb81119132b6568726761e9897c2b4e47c
workflow-type: tm+mt
source-wordcount: '1178'
ht-degree: 24%

---


# Campos derivados (pruebas limitadas){#derived-fields}

{{release-limited-testing}}

>[!IMPORTANT]
>
>Esta es la documentación preliminar de las nuevas funciones de campo derivadas que aún no están disponibles de forma general. Utilice esta información para obtener información sobre las nuevas funciones de campo derivadas. Esta documentación sigue estando sujeta a cambios y no se puede derivar ninguna obligación legal de la versión actual de este artículo.
>&#x200B;><br/>Consulte [Campos derivados](derived-fields.md) para obtener información sobre la funcionalidad de campos derivados en general y las funciones liberadas y plantillas de funciones disponibles actualmente.
>

## Referencia de función

{{select-package}}

Para cada función admitida, busque los detalles siguientes sobre:

- especificaciones:
   - tipo de datos de entrada: tipo de datos admitidos,
   - entrada: posibles valores para la entrada,
   - operadores incluidos: operadores admitidos para esta función (si existen),
   - limitaciones: limitaciones que se aplican a esta función específica,
   - salida.

- casos de uso, incluidos:
   - (opcional) datos antes de definir el campo derivado,
   - cómo definir el campo derivado,
   - (opcional) después de definir el campo derivado.

- restricciones (si procede).



<!-- DATE MATH -->

### Aritmética de fechas {#datemath}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_datemath"
>title="Aritmética de fechas"
>abstract="Esta función proporciona la capacidad de devolver la diferencia entre dos campos de fecha y hora."

Devuelve la diferencia entre dos fechas o dos campos de fecha y hora.

+++ Detalles

## Especificaciones {#datemath-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Limitaciones | Salida |
|---|---|---|---|---|
| <ul><li>Fecha</li><li>Fecha-hora</li></ul> | <ul><li>[!UICONTROL Ámbito]<ul><li>Evento</li><li>Sesión</li><li>Persona</li></ul></li><li>[!UICONTROL Valor]<ul><li>Fecha</li><li>Fecha-hora</li><li>Fecha estática (ha introducido el usuario)</li><li>Fecha y hora estáticas (ingresó el usuario)</li><li>Fecha dinámica<ul><li>Hoy</li></ul></li><li>Fecha-hora dinámica<ul><li>Ahora</li></ul></li></ul></li><li>[!UICONTROL Granularidad]:<ul><li>Seconds</li><li>Minutes</li><li>Horas</li><li>Days</li><li>Weeks</li><li>Months</li><li>Trimestres</li><li>Años</li></ul></li><li>Para cada devolución de fecha y hora:<ul><li>Primero (dentro de la sesión o la persona)</li><li>Último (en sesión o persona)</li></ul></li></ul> | <p>N/A</p> | <p>2 funciones por campo derivado</p> | <p>Nuevo campo derivado</p> |

{style="table-layout:auto"}


## Caso de uso 1 {#datemath-uc1}

Como analista de marketing de una empresa hotelera, le gustaría comprender la diferencia del número de días entre las fechas de llegada de los clientes y las fechas de reserva a lo largo de la última semana.


### Campo derivado {#datemath-uc1-derivedfield}

Defina un campo derivado `Days between booking and check-in`. Utiliza la función [!UICONTROL DATE MATH] para definir una regla que calcule los días del [!UICONTROL ámbito] [!DNL Person] entre la [!UICONTROL fecha de reserva] y la [!UICONTROL fecha de llegada]. Selecciona [!UICONTROL Día] como [!UICONTROL Granularidad de salida]. Y selecciona [!UICONTROL Devolver el último] tanto para la [!UICONTROL Fecha de reserva] como para la [!UICONTROL Fecha de registro] para garantizar que se use el valor de ámbito de la última persona en el cálculo.

![Captura de pantalla de la regla Date Math](assets/datemath-1.png)


## Caso de uso 2 {#datemath-uc2}

Como analista de marketing de una tienda, quiere saber cuántos días atrás fue la última visita de un cliente a la tienda. La funcionalidad de geolocalización se utiliza en una aplicación móvil y las señalizaciones de la tienda para capturar las visitas físicas de los clientes.

### Campo derivado {#datemath-uc2-derivedfield}

Defina un campo derivado `Days Since Visit To Shop`. Utiliza la función [!UICONTROL DATE MATH] para definir una regla que calcule los días entre una fecha y hora personalizada (que especifica en [!UICONTROL Fecha]) y la [!UICONTROL hora local] (de su grupo de campos [!UICONTROL placeContext] del conjunto de datos de evento) con un [!UICONTROL ámbito de deduplicación] de [!UICONTROL Persona]. Selecciona [!UICONTROL Devolver el último] para garantizar que se use el último valor de ámbito de persona de [!UICONTROL Hora local] en el cálculo. Selecciona Día como [!UICONTROL granularidad de salida].

![Captura de pantalla de la regla Date Math 2](assets/datemath-2.png)


## Caso de uso 3 {#datemath-uc3}

Desea comprender el tiempo de búsqueda en minutos antes de que un cliente, dentro de una sesión, realice un pedido.

Usted define un nuevo campo derivado de `Time Between Search And Order In Minutes` que es el resultado de dos funciones [[!UICONTROL CASE WHEN]](#case-when) para definir valores de [!UICONTROL Tiempo de búsqueda] y [!UICONTROL Tiempo de pedido].
A continuación, utilice estos dos valores para calcular la diferencia con una función [!UICONTROL DATE MATH] con [!UICONTROL Ámbito] establecido en [!UICONTROL Sesión], valores establecidos en [!UICONTROL Tiempo de búsqueda] y [!UICONTROL Tiempo de pedido] y [!UICONTROL Granularidad de salida] establecido en [!UICONTROL Minuto]. Para ambos valores, selecciona [!UICONTROL Devolver el primer] para garantizar que se devuelvan el primer [!UICONTROL Tiempo de búsqueda] y el [!UICONTROL Tiempo de pedido].

![Captura de pantalla de la regla Date Math 3](assets/datemath-3.png)



<!--
| Visitor ID | Marketing Channel | Events |
|----|---|---:|
| ABC123 | paid search | 1 |
| DEF123 | email | 1 |
| JKL123 | natural search | 1 |

{style="table-layout:auto"}

-->

+++



<!-- DEPTH -->

### Profundidad {#depth}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_depth"
>title="Profundidad"
>abstract="Esta función ofrece la posibilidad de devolver la profundidad de cualquier campo, de forma similar a la funcionalidad del componente estándar de profundidad del evento."

Devuelve la profundidad de un campo, similar a lo que es posible con la [dimensión de profundidad de evento estándar](/help/components/dimensions/overview.md#standard-dimensions).

+++ Detalles

## Especificaciones {#depth-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Limitaciones | Salida |
|---|---|---|---|---|
| Cualquiera | Cualquier campo | N/A | 3 funciones por campo derivado | Nuevo campo derivado |

{style="table-layout:auto"}


<!--
## Example Data {#depth-example}

| event# | page name | search | product view | cart add  | order |
|:---:|---|:---:|:---:|:---:|:---:|
| 1 |  home page        |  0  | 0  | 0  | 0 |
| 2 |  search page      |  1  | 0  | 0  | 0 |
| 3 |  product page     |  0  | 0  | 0  | 0 |
| 4 |  cart page        |  0  | 0  | 1  | 0 |
| 5 |  confirmation     |  0  | 0  | 0  | 1 |

-->

## Caso de uso {#depth-uc1}

Desea comprender la profundidad de la búsqueda (que también puede interpretar como el número de búsquedas). Por lo tanto, puede utilizar esa profundidad de búsqueda más adelante para buscar el término de búsqueda asociado con una profundidad de búsqueda específica.


### Campo derivado {#depth-uc1-derivedfield}

Defina un campo derivado `Search Depth`. La función [!UICONTROL DEPTH] se usa para definir una regla con el fin de recuperar la profundidad de [!UICONTROL Search] y almacenarla en un nuevo campo derivado.

![Captura de pantalla de la regla de profundidad](assets/depth-1.png)

+++


<!-- TYPECASE -->

### Cambiar tipo de campo {#typecast}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_typecast"
>title="Cambiar tipo de campo"
>abstract="Esta función ofrece la posibilidad de cambiar el tipo de campo sobre la marcha para que esté disponible para transformaciones adicionales en Customer Journey Analytics."

Cambie el tipo de campo de un campo para que esté disponible para transformaciones adicionales en Customer Journey Analytics.

+++ Detalles

## Especificaciones {#typecast-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Límite | Salida |
|---|---|---|---|---|
| <ul><li>Numéricos</li><li>Fecha</li><li>Fecha-hora</li><li>Cadena</li></ul> | <ul><li>[!UICONTROL Campo] | <p><ul><li>Número entero<ul><li>Para la cadena <strong>(Debe)</strong></li></ul></li><li>Doble<ul><li>Para la cadena <strong>(Debe)</strong><ul><li>Incluir el número de decimales que heredar (máximo de 5?)</li></ul></li><li>Al entero <strong>(Debería)</strong></li></ul></li><li>Byte<ul><li>Para la cadena <strong>(Debe)</strong></li></ul></li><li>Largo<ul><li>Para la cadena <strong>(Debe)</strong></li></ul></li><li>Fecha<ul><li>Para la cadena <strong>(Debe)</strong><ul><li>Proporcionar la capacidad de definir el formato de salida</li></ul></li><li>Ejemplos<ul><li>Fecha (ejemplo del 7 de enero de 2025)<ul><li data-stringify-indent="1" data-stringify-border="0">DD/MM/YY<ul><li data-stringify-indent="2" data-stringify-border="0">Ejemplo: 01-07-25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD/MM/AAAA<ul><li data-stringify-indent="2" data-stringify-border="0">Ejemplo: 07-01-2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD/MM/AA<ul><li data-stringify-indent="2" data-stringify-border="0">Ejemplo: 07-01-25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD/MM/AAAA<ul><li data-stringify-indent="2" data-stringify-border="0">Ejemplo: 01-07-2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD/MM/YY<ul><li data-stringify-indent="2" data-stringify-border="0">Ejemplo: 25-01-07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD/MM/YYYY<ul><li data-stringify-indent="2" data-stringify-border="0">Ejemplo: 07-01-2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD/MM/AA<ul><li data-stringify-indent="2" data-stringify-border="0">Ejemplo: 01/07/25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">MM/DD/AAAA<ul><li data-stringify-indent="2" data-stringify-border="0">Ejemplo: 07/01/2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">AAAA/MM/DD<ul><li data-stringify-indent="2" data-stringify-border="0">Ejemplo: 2025/01/07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">AA/MM/DD<ul><li data-stringify-indent="2" data-stringify-border="0">Ejemplo: 25/01/07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD/MM/YYYY<ul><li data-stringify-indent="2" data-stringify-border="0">Ejemplo: miércoles, 07 de enero de 2025</li></ul></li></ul></li></ul></li></ul></li><li>Fecha-hora<ul><li>Para la cadena <strong>(Debe)</strong><ul><li>Proporcionar la capacidad de definir el formato de salida</li></ul></li><li>Ejemplos<ul><li data-stringify-indent="0" data-stringify-border="0">Fecha-hora (ejemplo del 7 de enero de 2025 a las 1:30pm, 52 segundos)<ul><li data-stringify-indent="2" data-stringify-border="0">DD/MM/YY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ejemplo: 01-07-25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD/MM/YYYY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ejemplo: 01-07-2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD/MM/YY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ejemplo: 07-01-25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD/MM/YYYY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ejemplo: 07-01-2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD/MM/YY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ejemplo: 25-01-07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD/MM/YYYY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ejemplo: 07-01-2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">Hhmmss MM/DD/AA<ul><li data-stringify-indent="3" data-stringify-border="0">Ejemplo: 01/07/25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">Hhmmss MM/DD/AAAA<ul><li data-stringify-indent="3" data-stringify-border="0">Ejemplo: 07/01/2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD/MM/YYYY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ejemplo: 01/2025/07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">AA/MM/DD hh:mm :ss<ul><li data-stringify-indent="3" data-stringify-border="0">Ejemplo: 25/01/07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD de MMM de YYYY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ejemplo: 07 de enero de 2025 13:30:52</li></ul></li></ul></li></ul></li><li>Cadena<ul><li>A Numérico <strong>(Debería)</strong><ul><li>Si tenemos valores que no son numéricos, devolverán un valor nulo.</li><li>Necesitaremos que el usuario introduzca la precisión y la configuración regional que desea utilizar. </li></ul></li></ul></li></ul></li></ul></p> | <p>3 funciones por campo derivado</p> | <p>Nuevo campo derivado</p> |

{style="table-layout:auto"}


## Caso de uso 1 {#typecast-uc1}

Tiene un campo entero, altura de pantalla (por ejemplo, device.screenHeight del conjunto de datos de evento), que desea utilizar como dimensión basada en cadenas.


### Campo derivado {#typecast-uc1-derivedfield}

Usted define un campo derivado de `Screen Height`. La función [!UICONTROL TYPECAST] se usa para definir una regla para [!UICONTROL Typecast para] [!UICONTROL String] el campo [!UICONTROL Screen height] y almacenarla en el nuevo campo derivado.

![Captura de pantalla de la regla Typecast 1](assets/typecast-1.png)



## Caso de uso 2 {#typecast-uc2}

Desea utilizar Revenue en una tabla de cohorte (que sólo admite números enteros), pero el campo Revenue tiene un tipo Double.

![Captura de pantalla de la regla Typecast 2](assets/typecast-2.png)


### Campo derivado {#typecast-uc2-derivedfield}

Usted define un campo derivado de `Revenue (integer)`. La función [!UICONTROL TYPECAST] se usa para definir una regla para [!UICONTROL Typecast para] [!UICONTROL Integer] el campo [!UICONTROL Revenue] y almacenarla en el nuevo campo derivado.


+++
