---
title: Conjuntos de datos de evento combinados
description: Descubra cómo Customer Journey Analytics crea una conexión combinando conjuntos de datos.
exl-id: 9f678225-a9f3-4134-be38-924b8de8d57f
solution: Customer Journey Analytics
feature: Connections
source-git-commit: cf6da1f126933f17e05fb458f52dff93c1601891
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 61%

---


# Conjuntos de datos de evento combinados

Al crear una conexión, Customer Journey Analytics combina todos los esquemas y conjuntos de datos en un único conjunto de datos. Este &quot;conjunto de datos de evento combinado&quot; es lo que utiliza el Customer Journey Analytics para el sistema de informes. Cuando se incluyen varios esquemas o conjuntos de datos en una conexión:

* Los esquemas están combinados. Se combinan los campos de esquema duplicados.
* La columna &#39;ID de persona&#39; de cada conjunto de datos se combina en una sola columna, independientemente de su nombre. Esta columna es la base de la identificación de personas únicas en Customer Journey Analytics.
* Las filas se procesan según la marca de tiempo.
* Los eventos se resuelven en el nivel de milisegundos.

## Ejemplo

Consideremos el siguiente ejemplo. Tiene dos conjuntos de datos de eventos, cada uno con campos y datos diferentes.

>[!NOTE]
>
>Adobe Experience Platform generalmente almacena la marca de hora en milisegundos de Unix. Para facilitar la lectura en este ejemplo, se utiliza la fecha y la hora.

| `example_id` | `timestamp` | `string_color` | `string_animal` | `metric_a` |
| --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` | |
| `user_310` | `1 Jan 7:04 AM` | | | `2` |
| `user_310` | `1 Jan 7:08 AM` | `Blue` | | `3` |
| `user_847` | `2 Jan 12:31 PM` | | `Turtle` | `4` |
| `user_847` | `2 Jan 12:44 PM` | | | `2` |

| `different_id` | `timestamp` | `string_color` | `string_shape` | `metric_b` |
| --- | --- | --- | --- | --- |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | `Circle` | `8.5` |
| `user_847` | `2 Jan 1:01 PM` | `Red` | | |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | `Square` | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` | | `Triangle` | `3.1` |

Cuando se crea una conexión con estos dos conjuntos de datos de eventos, se utiliza la siguiente tabla para el sistema de informes.

| `id` | `timestamp` | `string_color` | `string_animal` | `string_shape` | `metric_a` | `metric_b` |
| --- | --- | --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` | | | |
| `user_310` | `1 Jan 7:04 AM` | | | | `2` | |
| `user_310` | `1 Jan 7:08 AM` | `Blue` | | | `3` | |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | | `Circle` | | `8.5` |
| `user_847` | `2 Jan 12:31 PM` | | `Turtle` | | `4` | |
| `user_847` | `2 Jan 12:44 PM` | | | | `2` | |
| `user_847` | `2 Jan 1:01 PM` | `Red` | | | | |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | | `Square` | | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` | | | `Triangle` | | `3.1` |

Este conjunto de datos de evento combinado es lo que se usa en el sistema de informes. No importa de qué conjunto de datos proviene una fila; Customer Journey Analytics trata todos los datos como si estuvieran en el mismo conjunto de datos. Si aparece una ID de persona coincidente en ambos conjuntos de datos, se consideran la misma persona única. Si en ambos conjuntos de datos aparece una ID de persona coincidente con una marca de tiempo en un lapso de 30 minutos, se considerarán parte de la misma sesión.

Este concepto también se aplica a la atribución. No importa de qué conjunto de datos proviene una fila; la atribución funciona exactamente como si todos los eventos procedieran de un único conjunto de datos. Ejemplo de uso de las tablas anteriores:

Si la conexión solo incluía la primera tabla y no la segunda, al extraer un informe con la `string_color` dimensión y la métrica `metric_a` mediante atribución de último contacto, se mostraría:

| string_color | metric_a |
| --- | --- |
| No especificado | 6 |
| Azul | 3 |
| Rojo | 2 |

Sin embargo, si ha incluido ambas tablas en la conexión, la atribución cambia porque `user_847` está en ambos conjuntos de datos. Una fila de los atributos del segundo conjunto de datos `metric_a` a &#39;Amarillo&#39; donde no se habían especificado antes:

| string_color | metric_a |
| --- | --- |
| Amarillo | 6 |
| Azul | 3 |
| Rojo | 2 |

## Análisis en canales múltiples

El siguiente nivel de combinación de conjuntos de datos es el análisis en canales múltiples, donde se combinan conjuntos de datos de diferentes canales, en función de un identificador común (ID de persona). El análisis en canales múltiples puede beneficiarse de la funcionalidad de vinculación, que le permite volver a escribir el ID de persona de un conjunto de datos para que el conjunto de datos se actualice correctamente y permita una combinación perfecta de varios conjuntos de datos. La vinculación busca los datos de usuario de las sesiones autenticadas y no autenticadas para generar un ID vinculado.

El análisis en canales múltiples le permite responder preguntas como las siguientes:

* ¿Cuántas personas comienzan su experiencia en un canal y luego la terminan en otro?
* ¿Cuántas personas interactúan con mi marca? ¿Cuántos y qué tipos de dispositivos utilizan? ¿Cómo se superponen?
* ¿Con qué frecuencia comienzan una tarea en un dispositivo móvil y luego se trasladan a un ordenador de escritorio para completarla? ¿Los clics de campaña que llegan a un dispositivo llevan a la conversión en otro dispositivo diferente?
* ¿Cómo cambia mi comprensión de la eficacia de la campaña si tengo en cuenta los recorridos entre dispositivos? ¿Cómo cambia mi análisis de embudo?
* ¿Cuáles son las rutas más comunes que los usuarios realizan de un dispositivo a otro? ¿En qué punto abandonan? ¿Dónde tienen éxito?
* ¿En qué se diferencia el comportamiento de los usuarios con varios dispositivos de los usuarios con un único dispositivo?


Para obtener más información sobre el análisis entre canales, consulte el caso de uso específico:

* [Análisis en canales múltiples](../use-cases/cross-channel/cross-channel.md)

Para obtener una funcionalidad de vinculación de discusión más detallada, vaya a:

* [Información general de vinculación](/help/stitching/overview.md)
* [Cómo funciona la vinculación](../stitching/explained.md)
* [Preguntas frecuentes ](/help/stitching/faq.md)

