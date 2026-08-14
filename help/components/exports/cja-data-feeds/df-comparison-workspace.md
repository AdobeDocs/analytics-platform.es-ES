---
description: Obtenga información sobre cómo comparar la funcionalidad de fuentes de datos en Customer Journey Analytics y Adobe Analytics
keywords: flujo de navegación;fuente de datos;fuente de datos;Fuente de datos
title: Comparación de la funcionalidad de las fuentes de datos en Customer Journey Analytics y Adobe Analytics
feature: Components
hide: true
source-git-commit: a72ed21bdea40e2441443d7218d9fd7c906adc3e
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 0%

---

# Comprender las discrepancias de datos entre las fuentes de datos y Analysis Workspace

{{release-limited-testing}}

Los datos de una exportación de fuentes de datos no siempre coinciden exactamente con los datos que se ven en Analysis Workspace. La información de esta página explica algunas de las razones principales.

## Intervalo de fechas de retrospectiva (fuentes de datos) frente al intervalo de fechas de creación de informes (Analysis Workspace)

El intervalo de fechas de retrospectiva en las fuentes de datos determina hasta dónde se remonta Customer Journey Analytics al encontrar eventos que cumplen los requisitos para una entrega de fuente de datos. En ese sentido, el intervalo de fechas de retrospectiva es similar al intervalo de fechas de creación de informes en Analysis Workspace. Sin embargo, existen diferencias clave.

| Diferencias clave | Intervalo de fechas de creación de informes (Analysis Workspace) | Intervalo de fecha de retrospectiva (fuentes de datos) |
|---------|---------|----------|
| **Límite de datos**<br/> Si los datos se incluyen en un informe o fuente | Flexible<p>Los eventos que no entren dentro del intervalo de fechas del informe se pueden incluir en un informe de Workspace si alguno de los siguientes factores influye en los eventos:</p><ul><li>**Persistencia de Dimension**: puede persistir más allá del intervalo de fechas del informe. Se agregan los datos.</li><li>**Calificación de segmentos**: los segmentos pueden extenderse más allá del intervalo de fechas del informe de forma predeterminada.<p>Los usuarios pueden optar por limitar el segmento al intervalo de fechas del informe cuando creen el segmento.<!--add link to new docs--></p></li><li>**Cálculo de sesión**: las sesiones pueden extenderse más allá del intervalo de fechas del informe. </li><li>**Transformaciones de campo derivadas**</li></ul> | Fijo<p>Los eventos que se encuentran fuera del intervalo de fechas de retrospectiva nunca se incluyen en una fuente de datos, independientemente de si se ven influidos por los siguientes factores:</p></p><ul><li>**Persistencia de Dimension**: no puede persistir más allá del intervalo de fechas retrospectivo. Los datos no se acumulan.</li><li>**Calificación de segmentos**: siempre limitada al intervalo de fechas de retroactividad.</li><li>**Cálculo de sesión**: siempre limitado al intervalo de fechas retrospectivas.</li><li>**Transformaciones de campo derivadas**: todas las funciones de campo derivadas que hacen referencia a contenedores utilizan el intervalo de fecha retrospectiva en las exportaciones de fuentes de datos.</li></ul><p>Para obtener más información sobre la configuración del intervalo de fechas de retrospectiva, consulte [Crear una fuente de datos](/help/components/exports/cja-data-feeds/create-feed.md#create-and-configure-a-data-feed).</p> |
| **Ventana de informes**<br/> El lapso de tiempo para informar | Igual que la ventana de creación de informes (el lapso de tiempo sobre el que desea crear el informe). | No es lo mismo que el lapso de tiempo sobre el que desea informar. <p>El lapso de tiempo para generar informes es la ventana Frecuencia, que puede ser una hora o un día.</p> |

>[!BEGINSHADEBOX]

**Ejemplo**

El ejemplo siguiente ilustra cómo las diferencias entre el intervalo de fechas del sistema de informes y el intervalo de fechas de retrospectiva pueden provocar discrepancias de datos entre los informes de Workspace y las entregas de fuentes de datos.

El evento A se produjo hace 85 días y se encuentra en una dimensión con una configuración de persistencia de 90 días (por ejemplo, una ventana de atribución de clic en una campaña). El evento se incluye en el informe de Analysis Workspace y no en la entrega de fuentes de datos.

![Diferencias de datos entre el espacio de trabajo y las fuentes de datos](assets/data-feed-data-differences.png)


>[!ENDSHADEBOX]

## Vinculación de reproducciones

Cada vez que se ejecuta una reproducción de vinculación, los datos de identidad históricos se actualizan de forma retroactiva.

Las fuentes de datos y Analysis Workspace tratan la vinculación de reproducciones de forma diferente, de la siguiente manera:

* **Fuentes de datos**: solo refleja la identidad enlazada en el momento de la exportación. Los resultados de la reproducción no se aplican de forma retroactiva a los archivos exportados.

* **Analysis Workspace**: muestra los datos enlazados más actuales, actualizados de forma retroactiva cada vez que se ejecuta una reproducción. Los datos históricos cambian después de cada reproducción, por lo que Workspace siempre refleja la resolución de identidad más reciente.

## Eventos que llegan tarde

En una fuente de datos, los eventos pueden llegar después de que se cierre la ventana de exportación de fuentes de datos.

Las fuentes de datos y Analysis Workspace funcionan de forma diferente en relación con los eventos anteriores, como se indica a continuación:

* **Fuentes de datos**: exporta datos en un período de tiempo fijo en función del momento en que se reciben los eventos.

  Es posible que los eventos que llegan después de que se cierre la ventana no se incluyan en la exportación. Esto se ve influido por el [intervalo de fechas retrospectivas](#lookback-date-range-data-feeds-vs-reporting-date-range-analysis-workspace) que elija.

* **Analysis Workspace**: procesa los datos en el momento del informe, por lo que los eventos se incluyen en los informes independientemente del momento en que se recibieron.

## Lote de datos

A veces, los datos se envían en un lote que abarca un período de tiempo prolongado.

Las fuentes de datos y Analysis Workspace funcionan de forma diferente con los datos por lotes, como se indica a continuación:

* **Fuentes de datos**: distribuye los datos por lotes cada día u hora según las marcas de tiempo originales. Por ejemplo, un lote que contiene 30 días de datos se propaga durante 30 días de exportaciones, de modo que solo aparece un pequeño trozo en una sola exportación.

* **Analysis Workspace**: muestra todos los datos en un lote tan pronto como se han procesado por completo, independientemente del intervalo de tiempo incluido en el lote.

