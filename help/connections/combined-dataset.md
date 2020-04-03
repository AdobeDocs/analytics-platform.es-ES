---
title: Conjunto de datos combinados
description: Descubra cómo CJA crea una conexión combinando conjuntos de datos.
translation-type: tm+mt
source-git-commit: f9cdcb8a6efe688d553929c3081f3239e0691cd9

---


# Conjunto de datos combinados

Al crear una conexión, CJA combina todos los esquemas y conjuntos de datos en un único conjunto de datos. Este &quot;conjunto de datos combinado&quot; es lo que utiliza CJA para el sistema de informes. Cuando se incluyen varios esquemas o conjuntos de datos en una conexión:

* Esquemas combinados. Se combinan los campos de esquema de Duplicado.
* La columna &#39;ID de persona&#39; de cada conjunto de datos se combina en una sola columna, independientemente de su nombre. Esta columna es la base de la identificación de visitantes únicos en la lista de usuarios.
* Las filas se procesan según la marca de tiempo.

## Ejemplo

Consideremos el siguiente ejemplo. Tiene dos conjuntos de datos, cada uno con campos diferentes que contienen datos diferentes.

> [!NOTE] Adobe Experience Platform generalmente almacena la marca de hora en milisegundos de Unix. Para facilitar la lectura en este ejemplo, se utiliza la fecha y la hora.

| `example_id` | `timestamp` | `string_color` | `string_animal` | `metric_a` |
| --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` |  |
| `user_310` | `1 Jan 7:04 AM` |  |  | `2` |
| `user_310` | `1 Jan 7:08 AM` | `Blue` |  | `3` |
| `user_847` | `2 Jan 12:31 PM` |  | `Turtle` | `4` |
| `user_847` | `2 Jan 12:44 PM` |  |  | `2` |

| `different_id` | `timestamp` | `string_color` | `string_shape` | `metric_b` |
| --- | --- | --- | --- | --- |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | `Circle` | `8.5` |
| `user_847` | `2 Jan 1:01 PM` | `Red` |  |  |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | `Square` | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` |  | `Triangle` | `3.1` |

Cuando se crea una conexión con estos dos conjuntos de datos, se utiliza la siguiente tabla para el sistema de informes.

| `id` | `timestamp` | `string_color` | `string_animal` | `string_shape` | `metric_a` | `metric_b` |
| --- | --- | --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` |  |  |  |
| `user_310` | `1 Jan 7:04 AM` |  |  |  | `2` |  |
| `user_310` | `1 Jan 7:08 AM` | `Blue` |  |  | `3` |  |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` |  | `Circle` |  | `8.5` |
| `user_847` | `2 Jan 12:31 PM` |  | `Turtle` |  | `4` |  |
| `user_847` | `2 Jan 12:44 PM` |  |  |  | `2` |  |
| `user_847` | `2 Jan 1:01 PM` | `Red` |  |  |  |  |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` |  | `Square` |  | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` |  |  | `Triangle` |  | `3.1` |

Este conjunto de datos combinado es lo que se utiliza en sistema de informes. No importa de qué conjunto de datos proviene una fila; CJA trata todos los datos como si estuvieran en el mismo conjunto de datos. Si aparece una ID de persona coincidente en ambos conjuntos de datos, se consideran el mismo visitante único. Si en ambos conjuntos de datos aparece una ID de persona coincidente con una marca de tiempo en un lapso de 30 minutos, se considerarán parte de la misma sesión.

Este concepto también se aplica a la atribución. No importa de qué conjunto de datos proviene una fila; la atribución funciona exactamente como si todos los eventos procedieran de un único conjunto de datos. Ejemplo de uso de las tablas anteriores:

Si la conexión solo incluía la primera tabla y no la segunda, al extraer un informe con la `string_color` dimensión y la métrica `metric_a` mediante atribución de último toque se mostraría:

| string_color | metric_a |
| --- | --- |
| Azul | 5 |
| No especificado | 6 |
| Rojo | 2 |

Sin embargo, si ha incluido ambas tablas en la conexión, la atribución cambia porque `user_847` está en ambos conjuntos de datos. Una fila de los atributos del segundo conjunto de datos `metric_a` a &#39;Amarillo&#39; donde anteriormente no se habían especificado:

| string_color | metric_a |
| --- | --- |
| Amarillo | 6 |
| Rojo | 2 |
| Azul | 3 |
