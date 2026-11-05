---
description: Obtenga información sobre cómo comparar la funcionalidad de fuentes de datos en Customer Journey Analytics y Adobe Analytics
keywords: flujo de navegación;fuente de datos;fuente de datos;Fuente de datos
title: Comparación de la funcionalidad de las fuentes de datos en Customer Journey Analytics y Adobe Analytics
feature: Components
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 03beb4bd52769a5428ca084beacefd8996d4c810
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 0%
---
# Comprender las discrepancias de datos entre las fuentes de datos y Analysis Workspace

{{release-limited-testing}}

Los datos de una exportación de fuentes de datos no siempre coinciden exactamente con los datos que se ven en Analysis Workspace. La información de esta página explica algunas de las razones principales.

## Ventana Procesamiento (fuentes de datos) frente a ventana Informes (Analysis Workspace) {#processing-window}

Cada entrega de fuente de datos utiliza un periodo de procesamiento móvil de 30 días. La ventana de procesamiento proporciona el contexto histórico necesario para clasificar los eventos en una entrega de fuente de datos. Para obtener detalles acerca de la ventana de procesamiento, incluidos ejemplos, vea [Comprender la ventana de procesamiento](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-window).

En ese sentido, la ventana de procesamiento es similar a la ventana de creación de informes de Analysis Workspace (el intervalo de fechas que elija para un informe). Sin embargo, existen diferencias clave.

| Diferencias clave | Ventana Informes (Analysis Workspace) | Ventana Procesamiento (Fuentes de datos) |
|---------|---------|----------|
| **Límite de datos**<br/> Si los datos se incluyen en un informe o fuente | Flexible<p>Los eventos que no entren en la ventana de creación de informes se pueden incluir en un informe de Workspace si alguno de los siguientes factores influye en los eventos:</p><ul><li>**Persistencia de Dimension**: puede persistir más allá de la ventana de informes al usar la sesión, el tiempo personalizado o la métrica [caducidad](/help/data-views/component-settings/persistence.md#expiration-settings). Igual que la ventana de informes al usar la ventana de informes de personas [expiration](/help/data-views/component-settings/persistence.md#expiration-settings). Se agregan los datos.</li><li>**Calificación de segmentos**: los segmentos pueden extenderse más allá de la ventana de creación de informes de forma predeterminada.<p>Los usuarios pueden optar por limitar el segmento a la ventana de creación de informes cuando creen el segmento.<!--add link to new docs--></p></li><li>**Cálculo de sesión**: las sesiones pueden extenderse más allá de la ventana de informes. </li><li>**Transformaciones de campo derivadas**</li></ul> | Fijo<p>Los eventos que quedan fuera de la ventana de procesamiento generalmente no influyen en la fuente de datos. La ventana de procesamiento se aplica a los siguientes factores:</p><ul><li>**Persistencia de Dimension**: puede persistir más allá del período de procesamiento (hasta 90 días) al usar Tiempo personalizado [caducidad](/help/data-views/component-settings/persistence.md#expiration-settings), igual que en Workspace. No puede persistir más allá de la ventana de procesamiento al usar la ventana de informes de personas [expiration](/help/data-views/component-settings/persistence.md#expiration-settings). Los datos no se acumulan.</li><li>**Calificación de segmentos**: Siempre limitado a la ventana de procesamiento.</li><li>**Cálculo de sesión**: Siempre limitado a la ventana de procesamiento.</li><li>**Transformaciones de campo derivadas**: todas las funciones de campo derivadas que hacen referencia a contenedores utilizan la ventana de procesamiento en las exportaciones de fuentes de datos.</li></ul> |
| **Periodo de tiempo para informar sobre**<br/> Qué eventos se incluyen en un informe o fuente | Igual que la ventana de creación de informes. | No es lo mismo que la ventana de procesamiento. <p>El lapso de tiempo para generar informes es la ventana de frecuencia, que puede ser una sola hora o un solo día al final de la ventana de procesamiento.</p> |

>[!BEGINSHADEBOX]

**Ejemplo**

El ejemplo siguiente ilustra cómo las diferencias entre la ventana de informes y la ventana de procesamiento pueden provocar discrepancias de datos entre los informes de Workspace y las entregas de fuentes de datos.

Un usuario cualificado para un segmento con un contenedor de persona hace 45 días y tiene un evento hoy. Un informe de Workspace con una ventana de informes de 30 días incluye el evento del usuario, ya que los segmentos pueden extenderse más allá de la ventana de informes de forma predeterminada. La entrega de fuentes de datos de hoy no incluye el evento, ya que la calificación de segmentos se limita al periodo de procesamiento de 30 días.

<!-- update the following graphic -->

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

  Es posible que los eventos que llegan después de que se cierre la ventana no se incluyan en la exportación. Esto se ve afectado por el [retraso de procesamiento](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-delay) que elija.

* **Analysis Workspace**: procesa los datos en el momento del informe, por lo que los eventos se incluyen en los informes independientemente del momento en que se recibieron.

## Lote de datos

A veces, los datos se envían en un lote que abarca un período de tiempo prolongado.

Las fuentes de datos y Analysis Workspace funcionan de forma diferente con los datos por lotes, como se indica a continuación:

* **Fuentes de datos**: distribuye los datos por lotes cada día u hora según las marcas de tiempo originales. Por ejemplo, un lote que contiene 30 días de datos se propaga durante 30 días de exportaciones, de modo que solo aparece un pequeño trozo en una sola exportación.

* **Analysis Workspace**: muestra todos los datos en un lote tan pronto como se han procesado por completo, independientemente del intervalo de tiempo incluido en el lote.

