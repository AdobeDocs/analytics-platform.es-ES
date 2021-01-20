---
title: Cómo funcionan las reproducciones
description: Comprender el concepto de "repetición" en Análisis de Canales cruzados
translation-type: tm+mt
source-git-commit: dca995fc271b02a26568ed8d4a672b96f10b0a18
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 1%

---


# Cómo funcionan las reproducciones

Análisis de Canales cruzados realiza dos pasadas de datos en una conexión determinada:

* **Cosificación** en vivo: CCA intenta unir cada visita a medida que entra. Los nuevos dispositivos netos del conjunto de datos que nunca han iniciado sesión no suelen vincularse a este nivel. Los dispositivos ya reconocidos se vinculan inmediatamente.
* **Reproducir**: La CCA &quot;reproduce&quot; datos basados en identificadores únicos que ha aprendido. En esta etapa se vinculan nuevos dispositivos a la conexión. Adobe oferta dos intervalos de repetición:
   * Diario: Los datos se reproducen todos los días con una ventana retrospectiva de 24 horas. Esta opción tiene una ventaja que las repeticiones son mucho más frecuentes, pero los visitantes no autenticados deben autenticarse el mismo día que visitan el sitio.
   * Semanal: Los datos se vuelven a reproducir una vez a la semana con una ventana retrospectiva de 7 días. Esta opción ofrece una ventaja que permite que las sesiones no autenticadas tengan un tiempo mucho más indulgente para autenticarse. Sin embargo, los datos de menos de una semana de antigüedad no están enlazados.

## Paso 1: Coherencia en vivo

CCA intenta unir cada evento tras la recopilación a dispositivos y canales conocidos. Considere el siguiente ejemplo, donde Bob usa dos canales diferentes.

*Datos tal como aparecen el día en que se recopilan:*

| Marca de tiempo | ID persistente de conjunto de datos web | ID transitoria del conjunto de datos web | ID de persona del centro de llamadas | ID de persona utilizado | Explicación de la visita | Métrica Personas (acumulativa) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `246` | Bob visita el sitio en su escritorio, sin autenticar | `1` (246) |
| `2` | `246` | `Bob` | - | `Bob` | Bob inicia sesión en el escritorio | `2` (246 y Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob hace una llamada al servicio al cliente | `2` (246 y Bob) |
| `4` | `3579` | - | - | `3579` | Bob accede al sitio desde su dispositivo móvil, sin autenticar | `3` (246, Bob y 3579) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob inicia sesión a través de un dispositivo móvil | `3` (246, Bob y 3579) |
| `6` | - | - | `Bob` | `Bob` | Bob hace otra llamada al servicio al cliente | `3` (246, Bob y 3579) |
| `7` | `246` | - | - | `Bob` | Bob vuelve a visitar el sitio en su escritorio, sin autenticar | `3` (246, Bob y 3579) |

Tanto los eventos no autenticados como los autenticados en los nuevos dispositivos se cuentan como personas independientes (temporalmente). Los eventos no autenticados en dispositivos reconocidos se vinculan en directo.

La atribución funciona tan pronto como la variable personalizada de identificación se vincula a un dispositivo. En el ejemplo anterior, todos los eventos excepto los eventos 1 y 4 están enlazados en directo (todos utilizan el identificador `Bob`). La atribución funciona en los eventos 1 y 4 después de la reproducción del cosido.

## Paso 2: Reproducir la vinculación

A intervalos regulares (una vez a la semana o una vez al día según la ventana retrospectiva seleccionada), CCA vuelve a calcular los datos históricos en función de los dispositivos que ahora reconoce. Si un dispositivo envía inicialmente datos sin autenticar y luego inicia sesión, CCA vincula esos eventos sin autenticar con la persona correcta. La siguiente tabla representa los mismos datos que arriba, pero muestra números diferentes basados en la reproducción de los datos.

*Los mismos datos después de la reproducción:*

| Marca de tiempo | ID persistente de conjunto de datos web | ID transitoria del conjunto de datos web | ID de persona del centro de llamadas | ID de persona utilizado | Explicación de la visita | Métrica Personas (acumulativa) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `Bob` | Bob visita el sitio en su escritorio, sin autenticar | `1` (Bob) |
| `2` | `246` | `Bob` | - | `Bob` | Bob inicia sesión en el escritorio | `1` (Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob hace una llamada al servicio al cliente | `1` (Bob) |
| `4` | `3579` | - | - | `Bob` | Bob accede al sitio desde su dispositivo móvil, sin autenticar | `1` (Bob) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob inicia sesión a través de un dispositivo móvil | `1` (Bob) |
| `6` | - | - | `Bob` | `Bob` | Bob hace otra llamada al servicio al cliente | `1` (Bob) |
| `7` | `246` | - | - | `Bob` | Bob vuelve a visitar el sitio en su escritorio, sin autenticar | `1` (Bob) |

## Volver a poner

* La CCA conecta inmediatamente dispositivos conocidos, pero no establece de forma inmediata dispositivos nuevos o no reconocidos.
* Los datos se reproducen a intervalos regulares y cambian los datos históricos de la conexión en función de los dispositivos que ha aprendido a identificar.
