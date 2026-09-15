---
title: Aplicar transformaciones de datos a las fuentes de datos
description: Obtenga información sobre las distintas formas de transformar los datos de fuentes de datos mediante la configuración de componentes, campos derivados o SQL.
hide: true
feature: Components
source-git-commit: 082927c1d511ba0831beba08aaaac0e2d0d9fbf6
workflow-type: tm+mt
source-wordcount: '1556'
ht-degree: 5%
---
# Aplicar transformaciones de datos a las fuentes de datos

{{release-limited-testing}}

Puede transformar los datos de las fuentes de datos mediante cualquiera de los métodos siguientes:

* [Configuración del componente de vista de datos](/help/data-views/component-settings/overview.md), usando

* [Campos derivados](/help/data-views/derived-fields/derived-fields.md)

* SQL

El método que elija a veces es una cuestión de preferencia. La siguiente tabla compara las compensaciones.

## Comparar métodos de transformación de datos

En la tabla siguiente se comparan las ventajas y desventajas de cada método en general.

| Método | Ventajas | Desventajas |
| --- | --- | --- |
| **Configuración de componentes** | <ul><li>Se aplican en el momento del informe, antes de que se envíe la fuente de datos.</li><li>La misma lógica se aplica de forma coherente en Analysis Workspace y en la salida de la fuente de datos.</li><li>No utiliza uno de los campos derivados limitados de la cuenta.</li><li>Algunas transformaciones, como la persistencia y la anulación de duplicación de métricas, son difíciles de replicar en SQL y la persistencia tampoco es posible actualmente con un campo derivado.</li></ul> | <ul><li>Solo está disponible para el conjunto de configuraciones específico que admite cada componente, no es tan flexible como crear lógica personalizada con un campo derivado.</li><li>Aún se está confirmando si una configuración afecta a la salida de la fuente de datos en algunos ajustes. Consulte la tabla siguiente.</li></ul> |
| **Campos derivados** | <ul><li>Se aplican en el momento del informe, antes de que se envíe la fuente de datos.</li><li>La misma lógica se aplica de forma coherente en Analysis Workspace y en la salida de la fuente de datos.</li><li>Admite una lógica personalizada más flexible que cualquier configuración de componente individual, como reglas condicionales encadenadas.</li><li>Algunas transformaciones, especialmente las que dependen de una configuración de Ámbito o las que analizan una dirección URL, son difíciles de replicar en SQL.</li></ul> | <ul><li>Agrega la sobrecarga de procesamiento, lo que puede afectar el rendimiento de la entrega de fuentes de datos.<!--Under a future usage-based pricing model, this could also add cost.--></li><li>Utiliza uno de los campos derivados limitados de la cuenta. Si una configuración de componente puede hacer el mismo trabajo, prefiera eso en su lugar.</li></ul> |
| **SQL** | <ul><li>No limitado por los límites de función y operador que se aplican a los campos derivados.</li><li>No afecta al rendimiento de la entrega de fuentes de datos.</li></ul> | <ul><li>Se aplica después de que la fuente de datos ya se haya entregado.</li><li>La lógica no se aplica en Analysis Workspace, por lo que debería duplicarla allí por separado.</li><li>Algunas transformaciones, especialmente aquellas que dependen de una configuración de Ámbito, que analizan una dirección URL o que deduplican o conservan un valor en un ámbito, son difíciles o poco prácticas de replicar.</li></ul> |

{style="table-layout:auto"}

## Transformaciones de datos

En la tabla siguiente se enumeran las transformaciones de datos específicas, mostrando qué método (o métodos) puede realizar cada uno, lo difícil que sería replicar en SQL y qué método utilizar. <!--A few transformations are still being confirmed with the engineering team and are marked as open questions — don't treat those as confirmed to affect data feed output until that's resolved.-->

| Transformación | Configuración de componentes | Campo derivado | Dificultad en SQL | Mejor ajuste | Consideraciones |
| --- | --- | --- | --- | --- | --- |
| **Aplicar lógica condicional o filtrar valores por criterios** | [Incluir/excluir valores](/help/data-views/component-settings/include-exclude-values.md) | [Caso Cuándo](/help/data-views/derived-fields/derived-fields.md#casewhen) | Fácil para cadenas; de moderado a difícil para métricas | Para cadenas; configuración de componentes para métricas | Para valores de cadena, comparables entre los tres, se trata en gran medida de una cuestión de preferencia. Para las métricas, SQL requiere una instrucción `CASE` combinada con una `COUNT`, lo cual es factible pero más complejo, por lo que la configuración del componente es la ruta más fácil. |
| **Crédito de atributo para un evento de éxito** | [Atribución](/help/data-views/component-settings/attribution.md) | No disponible | No aplicable | No aplicable | No se aplica a métricas de fuentes de datos. No es necesario replicar ningún comportamiento de fuente de datos, ya sea en SQL o en cualquier otro lugar. |
| **Agrupe valores numéricos en intervalos** | [Clasificación de valor](/help/data-views/component-settings/value-bucketing.md) | Case When (manual) | Difícil | Configuración de componentes | La complejidad aumenta desde la configuración del componente (más fácil) hasta el campo derivado (moderado, con un uso manual de Case When) y SQL (más complejo). |
| **Clasificar valores mediante una asignación de estilo de búsqueda** | No disponible | [Clasificar](/help/data-views/derived-fields/derived-fields.md#classify) | Fácil de moderar | O | Reproducible en SQL, pero el uso de un campo derivado mantiene la misma lógica aplicada de forma coherente en Analysis Workspace y en la salida de la fuente de datos. |
| **Combinar valores de campo con un delimitador** | No disponible | [Concatenar](/help/data-views/derived-fields/derived-fields.md#concatenate) | Fácil de moderar | O | Refleja la funcionalidad de agregar varias columnas de dimensión a una tabla de forma libre, que se limita a la exportación de tabla completa. Un campo derivado hace que un resultado similar esté disponible en una fuente de datos. |
| **Convertir el tipo de datos de un campo** | No disponible | [Tipografía](/help/data-views/derived-fields/derived-fields.md#typecast) | Fácil de moderar | O | Reproducible en SQL, pero el uso de un campo derivado mantiene la misma lógica aplicada de forma coherente en Analysis Workspace y en la salida de la fuente de datos. |
| **Contar ocurrencias de métricas (valores vs. instancias)** | [Comportamiento](/help/data-views/component-settings/behavior.md) | Solución alternativa personalizada basada en matemáticas | Fácil de moderar | O | Los tres enfoques funcionan; si puede hacerlo de forma nativa en Customer Journey Analytics, hay pocas razones para no hacerlo. |
| **Deduplicar un valor dentro de un ámbito** | [Anulación de duplicación métrica](/help/data-views/component-settings/metric-deduplication.md) | [Deduplicar](/help/data-views/derived-fields/derived-fields.md#dedup) | Difícil | Configuración de componentes o campo derivado | Depende de la configuración del ámbito. Consulte [Cómo afecta la configuración del ámbito a las fuentes de datos](#scope-settings). La configuración del componente y el campo derivado son aproximadamente equivalentes, pero prefiera la configuración del componente, ya que no utiliza uno de los campos derivados limitados. |
| **Determinar la profundidad de un campo dentro de una sesión** | No disponible | [Profundidad](/help/data-views/derived-fields/derived-fields.md#depth) | Difícil | Campo derivado | Utiliza la sesión como ámbito y no se puede configurar. <!-- Open question as of 2026-09-09: does the Depth counter carry over across an hourly/daily feed boundary using lookback-window context, or does it restart? Pending confirmation from engineering (Ron Fulkerson / Nate Purser). --> El comportamiento del contador cuando una sesión abarca un límite de entrega de fuente aún se está confirmando con ingeniería. Depende de la configuración del ámbito. Consulte [Cómo afecta la configuración del ámbito a las fuentes de datos](#scope-settings). |
| **Buscar y reemplazar un valor literal** | No disponible | [Buscar y reemplazar](/help/data-views/derived-fields/derived-fields.md#find-and-replace) | Fácil de moderar | O | Reproducible en SQL, pero el uso de un campo derivado mantiene la misma lógica aplicada de forma coherente en Analysis Workspace y en la salida de la fuente de datos. |
| **Dar formato a un valor para su visualización** | [Formato](/help/data-views/component-settings/format.md) | No disponible | Difícil | Configuración de componentes | El formato de fecha y hora aún no se refleja en la salida de la fuente de datos: las fuentes muestran actualmente la marca de tiempo estándar independientemente de esta configuración, aunque Adobe planea admitirlo para garantizar la disponibilidad general. El equipo aún está confirmando si los formatos numéricos (decimal, monetario, porcentual) de las métricas afectan a la salida de la fuente de datos. |
| **Agrupar dimensiones de conjuntos de datos de resumen** | [Grupo de datos de resumen](/help/data-views/component-settings/summary-data-group.md) | No disponible | Abrir pregunta | Abrir pregunta | Aún no se ha hablado con el equipo. No dé por hecho que esto afecta a la salida de fuentes de datos hasta que se confirme. |
| **Controlar un campo vacío (&quot;sin valor&quot;)** | [Sin opciones de valor](/help/data-views/component-settings/no-value-options.md) | No disponible | Abrir pregunta | Abrir pregunta | Si esto afecta a la salida de la fuente de datos (incluido si un valor en blanco se envía como nulo y si &quot;Tratar como valor&quot; cambia los datos subyacentes) aún se está revisando con el equipo. |
| **Buscar un valor de un conjunto de datos de búsqueda** | No disponible | [Búsqueda](/help/data-views/derived-fields/derived-fields.md#lookup) | Fácil de moderar | O | SQL funciona si ya existe una tabla de búsqueda. |
| **Minúsculas en una cadena** | [Comportamiento](/help/data-views/component-settings/behavior.md) | [Minúsculas](/help/data-views/derived-fields/derived-fields.md#lowercase) | Fácil de moderar | Configuración de componentes o campo derivado | Ambos son equivalentes, pero prefiere la configuración del componente, ya que no utiliza uno de los campos derivados limitados. |
| **Combinar varios campos en uno** | No disponible | [Combinar campos](/help/data-views/derived-fields/derived-fields.md#merge) | Fácil de moderar | O | — |
| **Analizar una dirección URL en sus componentes** | [Subcadena](/help/data-views/component-settings/substring.md) (método de análisis de URL) | [Análisis de URL](/help/data-views/derived-fields/derived-fields.md#urlparse) | Difícil | Configuración de componentes o campo derivado | SQL requiere un análisis de cadena personalizado para extraer los mismos componentes. <!-- Possible discrepancy: in the component settings meeting, Matt and Derek described all Substring methods, including URL parse, as roughly interchangeable across component setting, derived field, and SQL ("either one would work... maybe a preference"), which is a looser SQL-difficulty read than "Difficult." Flagged for Luke to reconcile; not changed without confirmation. --> |
| **Realizar cálculos básicos en campos numéricos** | No disponible | [Matemáticas](/help/data-views/derived-fields/derived-fields.md#math) | Fácil de moderar | O | Reproducible en SQL, pero el uso de un campo derivado mantiene la misma lógica aplicada de forma coherente en Analysis Workspace y en la salida de la fuente de datos. |
| **Conservar un valor de dimensión en todos los eventos** | [Persistencia](/help/data-views/component-settings/persistence.md) | No disponible actualmente <!-- Derek: considering adding this to FDL and surfacing it in derived fields; not currently possible. --> | Difícil | Configuración de componentes | Es mucho más fácil utilizar la configuración del componente que replicar esta lógica en SQL. Ya se ha confirmado que interactúa con el intervalo de fechas de retrospectiva del mismo modo que lo hacen las funciones de campo derivadas dependientes del ámbito. Ver [Comprender el intervalo de fechas de retrospectiva](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-lookback-date-range). |
| **Reemplazar un valor mediante una expresión regular** | [Subcadena](/help/data-views/component-settings/substring.md) (método Regex) | [Reemplazar regex](/help/data-views/derived-fields/derived-fields.md#regex-replace) | Fácil de moderar | O | Los tres enfoques producen el mismo resultado; es una cuestión de preferencia. |
| **Resolver el valor anterior o siguiente de una sesión** | No disponible | [Siguiente o Anterior](/help/data-views/derived-fields/derived-fields.md#next-previous) | Difícil | Campo derivado | Depende de la configuración del ámbito. Consulte [Cómo afecta la configuración del ámbito a las fuentes de datos](#scope-settings). |
| **Devuelve la diferencia entre dos fechas** | No disponible | [Matemáticas de fecha](/help/data-views/derived-fields/derived-fields.md#datemath) | Difícil | Campo derivado | Complejo para replicar en SQL. Depende de la configuración del ámbito. Consulte [Cómo afecta la configuración del ámbito a las fuentes de datos](#scope-settings). |
| **Alcance de una métrica como basada en eventos, perfiles o totales** | [Ámbito](/help/data-views/component-settings/scope.md) | No disponible | Abrir pregunta | Abrir pregunta | Aún no se ha hablado con el equipo. No dé por hecho que esto afecta a la salida de fuentes de datos hasta que se confirme. |
| **Dividir un valor delimitado** | [Subcadena](/help/data-views/component-settings/substring.md) (delimitador o método desde la izquierda/derecha) | [División](/help/data-views/derived-fields/derived-fields.md#split) | Fácil de moderar | O | Los tres enfoques producen el mismo resultado; es una cuestión de preferencia. |
| **Resumir o agregar un valor en un ámbito** | No disponible | [Resumir](/help/data-views/derived-fields/derived-fields.md#summarize) | Difícil | Campo derivado | Depende de la configuración del ámbito. Consulte [Cómo afecta la configuración del ámbito a las fuentes de datos](#scope-settings). |
| **Recortar caracteres de una cadena** | [Subcadena](/help/data-views/component-settings/substring.md) (método Trim) | [Recortar](/help/data-views/derived-fields/derived-fields.md#trim) | Fácil de moderar | O | Los tres enfoques producen el mismo resultado; es una cuestión de preferencia. |

{style="table-layout:auto"}

### Cómo afecta la configuración del ámbito a las fuentes de datos {#scope-settings}

La coincidencia de fecha, la anulación de duplicación, la siguiente o la anterior y el resumen dependen de una configuración de [!UICONTROL **ámbito**] de evento, sesión o persona (las opciones disponibles varían según la función). La profundidad no tiene un campo de ámbito configurable, pero está intrínsecamente vinculada a la sesión, de forma similar a la dimensión de profundidad del evento estándar. Cualquier campo con un ámbito escribe el mismo valor en cada fila dentro de ese ámbito y ese valor depende de los datos dentro del intervalo de fecha retrospectiva.
<!-- Open question as of 2026-09-09: is the lookback date range boundary anchored to a fixed point (e.g., midnight), or does it float with the feed run time, and is this configurable? Pending confirmation from Ron Fulkerson. -->

Dado que el [intervalo de fechas retrospectivo](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-lookback-date-range) se desliza hacia adelante con cada entrega de fuente de datos, el mismo campo puede devolver un valor diferente en una entrega posterior, incluso para los eventos que ya se han producido.

El riesgo aumenta con el tamaño del ámbito: el ámbito de la persona conlleva más riesgo que el de la sesión, ya que el historial de una persona no tiene un límite de tiempo natural dentro de una ejecución de fuente.

## Plantillas de funciones de campo derivadas

[Las plantillas de función de campo derivado](/help/data-views/derived-fields/derived-fields.md#templates) le permiten crear rápidamente un campo derivado para un caso de uso específico, como crear canales de marketing, detectar bots o extraer un parámetro de UTM de una dirección URL. Dado que una plantilla se crea a partir de una cadena de reglas creadas previamente, es casi siempre preferible utilizar una en lugar de reproducir la misma lógica en SQL desde cero.

Si una plantilla incluye una función que depende de una configuración de ámbito, la plantilla hereda la precaución de ámbito de esa función. Consulte [Cómo afecta la configuración del ámbito a las fuentes de datos](#scope-settings).
