---
title: Conjuntos de datos de evento combinados
description: Descubra cómo Customer Journey Analytics crea una conexión combinando conjuntos de datos.
exl-id: 9f678225-a9f3-4134-be38-924b8de8d57f
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: aaf23560b69c90fdbaee3fa401b5fe58e6a4e5d1
workflow-type: tm+mt
source-wordcount: '919'
ht-degree: 33%

---


# Conjuntos de datos de evento combinados

Al crear una conexión, Customer Journey Analytics combina todos los conjuntos de datos de evento en un único conjunto de datos. Este conjunto de datos de evento combinado es lo que utiliza el Customer Journey Analytics para el sistema de informes (junto con los conjuntos de datos de búsqueda y perfil). Cuando se incluyen varios conjuntos de datos de evento en una conexión:

* Los datos de los campos de los conjuntos de datos basados en **la misma ruta de esquema** se combinan en una sola columna del conjunto de datos combinado.
* La columna ID de persona, especificada para cada conjunto de datos, se combina en una sola columna del conjunto de datos combinado, **independientemente de su nombre**. Esta columna es la base de la identificación de personas únicas en Customer Journey Analytics.
* Las filas se procesan según la marca de tiempo.
* Los eventos se resuelven en el nivel de milisegundos.

## Ejemplo

Consideremos el siguiente ejemplo. Tiene dos conjuntos de datos de eventos, cada uno con campos y datos diferentes.

>[!NOTE]
>
>Adobe Experience Platform generalmente almacena una marca de tiempo en milisegundos de UNIX®. Para facilitar la lectura en este ejemplo, se utilizan la fecha y la hora.

| example_id | timestamp | string_color | string_animal | metric_a |
| --- | --- | --- | --- | ---: |
| user_310 | 1 de enero a las 7:02 | Rojo | Zorro | |
| user_310 | 1 de enero a las 7:04 | | | 2 |
| user_310 | 1 de enero a las 7:08 | Azul | | 3 |
| user_847 | 2 de enero, 12:31 p.m. | | Tortuga | 4 |
| user_847 | 2 ene 12:44 p.m. | | | 2 |

| different_id | timestamp | string_color | string_shape | metric_b |
| --- | --- | --- | --- | ---: |
| user_847 | 2 de enero, 12:26 p.m. | Amarillo | Círculo | 8,5 |
| user_847 | 2 de enero, 1:01 p.m. | Rojo | | |
| alternateid_656 | 2 de enero a las 8:58 p.m. | Rojo | Cuadrado | 4.2 |
| alternateid_656 | 2 de enero, 9:03 p. m. | | Triángulo | 3,1 |

Cuando crea una conexión con estos dos conjuntos de datos de eventos, y ha identificado

* `example_id` como ID de persona para el primer conjunto de datos y
* `different_id` como ID de persona para el segundo conjunto de datos,

el siguiente conjunto de datos combinado se utiliza para el sistema de informes.

| id | timestamp | string_color | string_animal | string_shape | metric_a | metric_b |
| --- | --- | --- | --- | --- | ---: | ---: |
| user_310 | 1 de enero a las 7:02 | Rojo | Zorro | | | |
| user_310 | 1 de enero a las 7:04 | | | | 2 | |
| user_310 | 1 de enero a las 7:08 | Azul | | | 3 | |
| user_847 | 2 de enero, 12:26 p.m. | Amarillo | | Círculo | | 8,5 |
| user_847 | 2 de enero, 12:31 p.m. | | Tortuga | | 4 | |
| user_847 | 2 ene 12:44 p.m. | | | | 2 | |
| user_847 | 2 de enero, 1:01 p.m. | Rojo | | | | |
| alternateid_656 | 2 de enero a las 8:58 p.m. | Rojo | | Cuadrado | | 4.2 |
| alternateid_656 | 2 de enero, 9:03 p. m. | | | Triángulo | | 3,1 |

Para ilustrar la importancia de las rutas de esquema, considere este escenario. En el primer conjunto de datos, `string_color` se basa en la ruta de esquema `_experience.whatever.string_color` y en el segundo conjunto de datos en la ruta de esquema `_experience.somethingelse.string_color`. En este escenario, los datos **no** se combinaron en una columna en el conjunto de datos combinado resultante. En su lugar, el resultado son dos columnas `string_color` en el conjunto de datos combinado:

| id | timestamp | _experience.<br/>lo que sea.<br/>color_cadena | _experience.<br/>algo más.<br/>color_cadena | string_animal | string_shape | metric_a | metric_b |
|---|---|---|---|---|---|---:|---:|
| user_310 | 1 de enero a las 7:02 | Rojo | | Zorro | | | |
| user_310 | 1 de enero a las 7:04 | | | | | 2 | |
| user_310 | 1 de enero a las 7:08 | Azul | | | | 3 | |
| user_847 | 2 de enero, 12:26 p.m. | | Amarillo | | Círculo | | 8,5 |
| user_847 | 2 de enero, 12:31 p.m. | | | Tortuga |  | 4 | |
| user_847 | 2 ene 12:44 p.m. | | | | | 2 | |
| user_847 | 2 de enero, 1:01 p.m. | | Rojo | | | | |
| alternateid_656 | 2 de enero a las 8:58 p.m. | | Rojo | | Cuadrado | | 4.2 |
| alternateid_656 | 2 de enero, 9:03 p. m. | | | | Triángulo | | 3,1 |

Este conjunto de datos de evento combinado es lo que se usa en el sistema de informes. No importa de qué conjunto de datos proviene una fila. Customer Journey Analytics trata todos los datos como si estuvieran en el mismo conjunto de datos. Si aparece una ID de persona coincidente en ambos conjuntos de datos, se consideran la misma persona única. Si en ambos conjuntos de datos aparece una ID de persona coincidente con una marca de tiempo en un plazo de 30 minutos, se considerarán parte de la misma sesión. Se combinan campos con rutas de esquema idénticas.

Este concepto también se aplica a la atribución. No importa de qué conjunto de datos proviene una fila; la atribución funciona exactamente como si todos los eventos procedieran de un único conjunto de datos. Ejemplo de uso de las tablas anteriores:

Si la conexión solo incluía la primera tabla y no la segunda, al extraer un informe con la `string_color` dimensión y la métrica `metric_a` mediante atribución de último contacto, se mostraría:

| string_color | metric_a |
| --- | ---: |
| No especificado | 6 |
| Azul | 3 |
| Rojo | 2 |

Sin embargo, si ha incluido ambas tablas en la conexión, la atribución cambia porque `user_847` está en ambos conjuntos de datos. Una fila de los atributos del segundo conjunto de datos `metric_a` a &#39;Amarillo&#39; donde no se habían especificado antes:

| string_color | metric_a |
| --- | ---: |
| Amarillo | 6 |
| Azul | 3 |
| Rojo | 2 |

>[!NOTE]
>
>Si un campo combinado es una clave de búsqueda para un conjunto de datos de evento de la conexión, el conjunto de datos de búsqueda asociado enriquecerá **todos** los valores de ese campo. No importa de qué conjunto de datos de evento proviene una fila, ya que la relación de búsqueda está asociada a la ruta de esquema compartida.

## Análisis en canales múltiples

El siguiente nivel de combinación de conjuntos de datos es el análisis en canales múltiples, donde se combinan conjuntos de datos de diferentes canales, en función de un identificador común (ID de persona). El análisis en canales múltiples puede beneficiarse de la funcionalidad de vinculación, que le permite volver a escribir el ID de persona de un conjunto de datos para que el conjunto de datos se actualice correctamente y se habilite una combinación perfecta de varios conjuntos de datos. La vinculación busca los datos de usuario de las sesiones autenticadas y no autenticadas para generar un ID vinculado.

El análisis en canales múltiples le permite responder preguntas como las siguientes:

* ¿Cuántas personas comienzan su experiencia en un canal y luego la terminan en otro?
* ¿Cuántas personas interactúan con mi marca? ¿Cuántos y qué tipos de dispositivos utilizan? ¿Cómo se superponen?
* ¿Con qué frecuencia comienzan una tarea en un dispositivo móvil y luego se trasladan a un ordenador de escritorio para completarla? ¿Los clics de campaña que llegan a un dispositivo llevan a la conversión en otro dispositivo diferente?
* ¿Cómo cambia mi comprensión de la eficacia de la campaña si tengo en cuenta los recorridos entre dispositivos? ¿Cómo cambia mi análisis de embudo?
* ¿Cuáles son las rutas más comunes que los usuarios realizan de un dispositivo a otro? ¿En qué punto abandonan? ¿Dónde tienen éxito?
* ¿En qué se diferencia el comportamiento de los usuarios con varios dispositivos de los usuarios con un único dispositivo?


Para obtener más información sobre el análisis en canales múltiples, consulte el caso de uso específico:

* [Análisis en canales múltiples](../use-cases/cross-channel/cross-channel.md)

Para un análisis más detallado de la funcionalidad de la vinculación, vaya a:

* [Información general de vinculación](/help/stitching/overview.md)
* [Preguntas frecuentes ](/help/stitching/faq.md)

