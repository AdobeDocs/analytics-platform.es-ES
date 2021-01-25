---
title: Cómo funcionan las reproducciones
description: Comprender el concepto de "repetición" en Análisis de Canales cruzados
translation-type: tm+mt
source-git-commit: dca995fc271b02a26568ed8d4a672b96f10b0a18
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 96%

---


# Cómo funcionan las reproducciones

Análisis de Canales cruzados realiza dos pasadas de datos en una conexión determinada:

* **Vinculación en tiempo real**: CCA intenta vincular cada visita conforme se va produciendo. Los nuevos dispositivos netos del conjunto de datos que nunca han iniciado sesión no suelen vincularse en este nivel. Los dispositivos ya reconocidos se vinculan inmediatamente.
* **Reproducción**: CCA &quot;reproduce&quot; los datos en función de los identificadores únicos que ha aprendido. En esta fase es en la que se vinculan nuevos dispositivos a la conexión. Adobe ofrece dos intervalos de reproducción:
   * Diario: los datos se reproducen todos los días con una ventana retrospectiva de 24 horas. Esta opción ofrece la ventaja de que las repeticiones son mucho más frecuentes, pero los visitantes no autenticados deben autenticarse el mismo día que visitan el sitio.
   * Semanal: los datos se reproducen una vez a la semana con una ventana retrospectiva de 7 días. Esta opción ofrece la ventaja de que ofrece a las sesiones no autenticadas mucho más tiempo para autenticarse. Sin embargo, los datos de menos de una semana de antigüedad no están vinculados.

## Paso 1: Vinculación en tiempo real

CCA intenta vincular cada evento tras la recopilación con los dispositivos y canales conocidos. Preste atención al siguiente ejemplo, en el que Bob utiliza dos canales diferentes.

*Datos tal como aparecen el día en que se recopilan:*

| Marca de tiempo | ID persistente del conjunto de datos web | ID transitorio del conjunto de datos web | ID de la persona del centro de llamadas | ID de persona utilizado | Explicación de la visita | Métrica de personas (acumulativa) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `246` | Bob visita el sitio en su escritorio, sin autenticarse | `1` (246) |
| `2` | `246` | `Bob` | - | `Bob` | Bob inicia sesión en el escritorio | `2` (246 y Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob hace una llamada al servicio de atención al cliente | `2` (246 y Bob) |
| `4` | `3579` | - | - | `3579` | Bob accede al sitio desde su dispositivo móvil, sin autenticarse | `3` (246, Bob y 3579) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob inicia sesión a través de un dispositivo móvil | `3` (246, Bob y 3579) |
| `6` | - | - | `Bob` | `Bob` | Bob hace otra llamada al servicio de atención al cliente | `3` (246, Bob y 3579) |
| `7` | `246` | - | - | `Bob` | Bob vuelve a visitar el sitio en su escritorio, sin autenticarse | `3` (246, Bob y 3579) |

Tanto los eventos no autenticados como los autenticados en los nuevos dispositivos se cuentan como personas independientes (temporalmente). Los eventos no autenticados en dispositivos reconocidos se vinculan en tiempo real.

La atribución funciona tan pronto como la variable personalizada de identificación se vincula a un dispositivo. En el ejemplo anterior, todos los eventos, excepto los eventos 1 y 4, se vinculan en tiempo real (todos utilizan el identificador `Bob`). La atribución funciona en los eventos 1 y 4 tras la reproducción de la vinculación.

## Paso 2: Reproducción de la vinculación

A intervalos regulares (una vez a la semana o una vez al día, en función de la ventana retrospectiva seleccionada), CCA vuelve a calcular los datos históricos en función de los dispositivos que ahora reconoce. Si un dispositivo envía inicialmente datos sin autenticarse y luego inicia sesión, CCA vincula esos eventos sin autenticar con la persona correcta. La siguiente tabla representa los mismos datos que los que hemos visto anteriormente, pero muestra números diferentes basados en la reproducción de los datos.

*Mismos datos tras la reproducción:*

| Marca de tiempo | ID persistente del conjunto de datos web | ID transitorio del conjunto de datos web | ID de la persona del centro de llamadas | ID de persona utilizado | Explicación de la visita | Métrica de personas (acumulativa) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `Bob` | Bob visita el sitio en su escritorio, sin autenticarse | `1` (Bob) |
| `2` | `246` | `Bob` | - | `Bob` | Bob inicia sesión en el escritorio | `1` (Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob hace una llamada al servicio de atención al cliente | `1` (Bob) |
| `4` | `3579` | - | - | `Bob` | Bob accede al sitio desde su dispositivo móvil, sin autenticarse | `1` (Bob) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob inicia sesión a través de un dispositivo móvil | `1` (Bob) |
| `6` | - | - | `Bob` | `Bob` | Bob hace otra llamada al servicio de atención al cliente | `1` (Bob) |
| `7` | `246` | - | - | `Bob` | Bob vuelve a visitar el sitio en su escritorio, sin autenticarse | `1` (Bob) |

## Recapitulación

* CCA vincula de inmediato los dispositivos conocidos, pero no vincula de forma inmediata los dispositivos nuevos o no reconocidos.
* Los datos se reproducen a intervalos regulares y cambian los datos históricos de la conexión en función de los dispositivos que ha aprendido a identificar.
