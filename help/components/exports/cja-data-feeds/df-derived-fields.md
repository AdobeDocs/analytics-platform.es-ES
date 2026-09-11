---
title: Uso de campos derivados en fuentes de datos
description: Aprenda a utilizar campos derivados en fuentes de datos.
hide: true
feature: Components
source-git-commit: a9f53472d57a3a26004bd5ca583a43134bbdba7e
workflow-type: tm+mt
source-wordcount: '1286'
ht-degree: 2%

---

# Uso de campos derivados en fuentes de datos

{{release-limited-testing}}

Puede realizar transformaciones de datos en los datos de fuentes de datos usando [campos derivados](/help/data-views/derived-fields/derived-fields.md).

Muchas funciones de campo derivadas realizan transformaciones que también se pueden aplicar mediante SQL, como reemplazar valores, combinar campos o convertir el tipo de datos de un campo, por lo que el método que elija a veces es una cuestión de preferencia.

## Campos derivados frente a SQL

En la siguiente tabla se comparan las ventajas y desventajas de utilizar campos derivados o SQL.

| Método | Ventajas | Desventajas |
| --- | --- | --- |
| **Campos derivados** | <ul><li>La misma lógica se aplica de forma coherente tanto en Analysis Workspace como en la salida de la fuente de datos, ya que los campos derivados se incluyen como componentes en el esquema de la fuente de datos, junto con las dimensiones y métricas estándar.</li><li>Algunas transformaciones, especialmente las que dependen de una configuración de Ámbito o las que analizan una dirección URL, son difíciles de replicar en SQL.</li></ul> | Agrega la sobrecarga de procesamiento, lo que puede afectar el rendimiento de la entrega de fuentes de datos.<!--Under a future usage-based pricing model, this could also add cost.--> |
| **SQL** | <ul><li>No limitado por los límites de función y operador que se aplican a los campos derivados.</li><li>No afecta al rendimiento de la entrega de fuentes de datos.</li></ul> | <ul><li>La lógica no se aplica en Analysis Workspace, por lo que debería duplicarla allí por separado.</li><li>Algunas transformaciones, especialmente las que dependen de una configuración de Ámbito o las que analizan una dirección URL, son difíciles o poco prácticas de replicar.</li></ul> |

{style="table-layout:auto"}

## Funciones de campo derivadas

En la tabla siguiente se describe cada función de campo derivada, si es más adecuada para un campo derivado o para SQL, y las consideraciones que se deben tener en cuenta antes de utilizarla.

| Función de campo derivada | Dificultad para replicar con SQL | Mejor ajuste (campo derivado o SQL) | Consideraciones |
| --- | --- | --- | --- |
| [**Caso cuando**](/help/data-views/derived-fields/derived-fields.md#casewhen)<br/> Aplica condicionales basados en criterios de uno o más campos y, a continuación, establece el valor de salida en función de qué condición coincida. | Fácil de moderar | O | Reproducible en SQL, pero el uso de un campo derivado mantiene la misma lógica aplicada de forma coherente en Analysis Workspace y en la salida de la fuente de datos. Esto resulta especialmente útil cuando se aplica un gran número de reglas, como una clasificación de canal de marketing. |
| [**Clasificar**](/help/data-views/derived-fields/derived-fields.md#classify)<br/> Define un conjunto de valores que se reemplazan por los valores correspondientes en un nuevo campo derivado. | Fácil de moderar | O | Reproducible en SQL, pero el uso de un campo derivado mantiene la misma lógica aplicada de forma coherente en Analysis Workspace y en la salida de la fuente de datos. |
| [**Concatenar**](/help/data-views/derived-fields/derived-fields.md#concatenate)<br/> Combina valores de campo en un único campo derivado nuevo utilizando delimitadores definidos (por ejemplo, nombre de página y canal de marketing). | Fácil de moderar | O | Refleja la funcionalidad de agregar varias columnas de dimensión a una tabla de forma libre, que se limita a la exportación de tabla completa. Un campo derivado hace que un resultado similar esté disponible en una fuente de datos. |
| [**Matemática de fecha**](/help/data-views/derived-fields/derived-fields.md#datemath)<br/> Devuelve la diferencia entre dos campos de fecha y hora (por ejemplo, días entre una fecha de reserva y una fecha de llegada), con un ámbito de evento, sesión o persona. | Difícil | Campo derivado | Complejo para replicar en SQL. Esta función depende de una configuración de ámbito. Para obtener más información, vea [Cómo afecta la configuración de ámbito de las funciones a las fuentes de datos](#scope-settings). |
| [**Deduplicar**](/help/data-views/derived-fields/derived-fields.md#dedup)<br/> Evita contar un valor varias veces, con un ámbito de persona o sesión (por ejemplo, deduplicar un ID de confirmación de reserva). | Difícil | Campo derivado | Esta función depende de una configuración de ámbito. Para obtener más información, vea [Cómo afecta la configuración de ámbito de las funciones a las fuentes de datos](#scope-settings). |
| [**Profundidad**](/help/data-views/derived-fields/derived-fields.md#depth)<br/> Devuelve la profundidad de un campo, similar a la dimensión Profundidad de evento estándar (por ejemplo, profundidad de búsqueda interna). | Difícil | Campo derivado | Utiliza la sesión como ámbito y no se puede configurar. <!-- Open question as of 2026-09-09: does the Depth counter carry over across an hourly/daily feed boundary using lookback-window context, or does it restart? Pending confirmation from engineering (Ron Fulkerson / Nate Purser). --> El comportamiento del contador cuando una sesión abarca un límite de entrega de fuente aún se está confirmando con ingeniería. Esta función depende de una configuración de ámbito. Para obtener más información, vea [Cómo afecta la configuración de ámbito de las funciones a las fuentes de datos](#scope-settings). |
| [**Buscar y reemplazar**](/help/data-views/derived-fields/derived-fields.md#find-and-replace)<br/> Busca todos los valores de un campo seleccionado y los reemplaza por un valor diferente. | Fácil de moderar | O | Reproducible en SQL, pero el uso de un campo derivado mantiene la misma lógica aplicada de forma coherente en Analysis Workspace y en la salida de la fuente de datos. |
| [**Consulta**](/help/data-views/derived-fields/derived-fields.md#lookup)<br/> Busca un valor de un conjunto de datos de consulta utilizando una clave coincidente y lo devuelve en un nuevo campo derivado. | Fácil de moderar | O | SQL funciona si ya existe una tabla de búsqueda. |
| [**Minúsculas**](/help/data-views/derived-fields/derived-fields.md#lowercase)<br/> Convierte los valores de un campo a minúsculas. | Fácil de moderar | O | Reproducible en SQL, pero el uso de un campo derivado mantiene la misma lógica aplicada de forma coherente en Analysis Workspace y en la salida de la fuente de datos. |
| [**Matemáticas**](/help/data-views/derived-fields/derived-fields.md#math)<br/> Aplica operadores matemáticos básicos (sumar, restar, multiplicar, dividir o aumentar a una potencia) a campos numéricos, evaluados visita a visita. | Fácil de moderar | O | Reproducible en SQL, pero el uso de un campo derivado mantiene la misma lógica aplicada de forma coherente en Analysis Workspace y en la salida de la fuente de datos. |
| [**Combinar campos**](/help/data-views/derived-fields/derived-fields.md#merge)<br/> Comprueba si el primero de dos o más campos tiene un valor; en caso contrario, utiliza el siguiente campo, y así sucesivamente. | Fácil de moderar | O | Ninguno |
| [**Siguiente o anterior**](/help/data-views/derived-fields/derived-fields.md#next-previous)<br/> Resuelve el valor siguiente o anterior de un campo de tabla de visitas o eventos, con un ámbito de persona o sesión. | Difícil | Campo derivado | Esta función depende de una configuración de ámbito. Para obtener más información, vea [Cómo afecta la configuración de ámbito de las funciones a las fuentes de datos](#scope-settings). |
| [**Reemplazo de regex**](/help/data-views/derived-fields/derived-fields.md#regex-replace)<br/> Reemplaza un valor de un campo mediante una expresión regular. | Fácil de moderar | O | Reproducible en SQL, pero el uso de un campo derivado mantiene la misma lógica aplicada de forma coherente en Analysis Workspace y en la salida de la fuente de datos. |
| [**Split**](/help/data-views/derived-fields/derived-fields.md#split)<br/> Divide un valor de un campo en un nuevo campo derivado (por ejemplo, convertir una lista delimitada en una matriz). | Fácil de moderar | O | Reproducible en SQL, pero el uso de un campo derivado mantiene la misma lógica aplicada de forma coherente en Analysis Workspace y en la salida de la fuente de datos. |
| [**Resumir**](/help/data-views/derived-fields/derived-fields.md#summarize)<br/> Aplica funciones de agregación (como suma, recuento o más común) a un campo, con un ámbito de evento, sesión o persona. | Difícil | Campo derivado | Esta función depende de una configuración de ámbito. Para obtener más información, vea [Cómo afecta la configuración de ámbito de las funciones a las fuentes de datos](#scope-settings). |
| [**Recortar**](/help/data-views/derived-fields/derived-fields.md#trim)<br/> Recorta espacios en blanco, caracteres especiales o un número determinado de caracteres desde el principio o el final de los valores de un campo. | Fácil de moderar | O | Reproducible en SQL, pero el uso de un campo derivado mantiene la misma lógica aplicada de forma coherente en Analysis Workspace y en la salida de la fuente de datos. |
| [**Typecast**](/help/data-views/derived-fields/derived-fields.md#typecast)<br/> Cambia el tipo de datos de un campo para que esté disponible para transformaciones adicionales. | Fácil de moderar | O | Reproducible en SQL, pero el uso de un campo derivado mantiene la misma lógica aplicada de forma coherente en Analysis Workspace y en la salida de la fuente de datos. |
| [**Análisis de URL**](/help/data-views/derived-fields/derived-fields.md#urlparse)<br/> Analiza partes de una dirección URL, incluido el protocolo, el host, la ruta de acceso, el parámetro de cadena de consulta o el valor hash. | Difícil | Campo derivado | SQL requiere un análisis de cadena personalizado para extraer los mismos componentes. |

{style="table-layout:auto"}

### Efecto de la configuración de ámbito en las funciones en las fuentes de datos {#scope-settings}

[!UICONTROL **Matemáticas de fecha**], [!UICONTROL **Deduplicar**], [!UICONTROL **Siguiente o Anterior**] y [!UICONTROL **Resumir**] dependen de una configuración de [!UICONTROL **Ámbito**] de evento, Sesión o Persona (las opciones disponibles varían según la función). [!UICONTROL **Profundidad**] no tiene un campo de ámbito configurable, pero está inherentemente vinculado a la sesión, de forma similar a la dimensión Profundidad de evento estándar. Cualquier campo con un ámbito escribe el mismo valor en cada fila dentro de ese ámbito y ese valor depende de los datos dentro del intervalo de fecha retrospectiva.
<!-- Open question as of 2026-09-09: is the lookback date range boundary anchored to a fixed point (e.g., midnight), or does it float with the feed run time, and is this configurable? Pending confirmation from Ron Fulkerson. -->

Dado que el intervalo de fechas retroactivo se desliza hacia adelante con cada entrega de fuente de datos, el mismo campo puede devolver un valor diferente en una entrega posterior, incluso para los eventos que ya se han producido.

El riesgo aumenta con el tamaño del ámbito: el ámbito de la persona conlleva más riesgo que el de la sesión, ya que el historial de una persona no tiene un límite de tiempo natural dentro de una ejecución de fuente.

## Plantillas de funciones de campo derivadas

[Las plantillas de función de campo derivado](/help/data-views/derived-fields/derived-fields.md#templates) le permiten crear rápidamente un campo derivado para un caso de uso específico, como crear canales de marketing, detectar bots o extraer un parámetro de UTM de una dirección URL. Dado que una plantilla se crea a partir de una cadena de reglas creadas previamente, es casi siempre preferible utilizar una en lugar de reproducir la misma lógica en SQL desde cero.

Si una plantilla incluye una función que depende de una configuración de ámbito, la plantilla hereda la precaución de ámbito de esa función. Consulte [Cómo afecta la configuración de ámbito de las funciones a las fuentes de datos](#scope-settings).

