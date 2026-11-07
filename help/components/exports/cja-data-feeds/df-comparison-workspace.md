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
source-git-commit: 7f3fb46b9c1928f8b02ce2108b4e98b5cc8da766
workflow-type: tm+mt
source-wordcount: '1140'
ht-degree: 0%
---
# Comprender las discrepancias de datos entre las fuentes de datos y Analysis Workspace

{{release-limited-testing}}

Los datos de una exportación de fuentes de datos no siempre coinciden exactamente con los datos que se ven en Analysis Workspace. La información de esta página explica algunas de las razones principales.

Algunas de estas diferencias provienen de comportamientos de Workspace difíciles de ver solo en los informes de Workspace, porque se agregan datos de Workspace. Las fuentes de datos proporcionan datos en el nivel de evento, por lo que estos comportamientos se hacen evidentes al comparar los resultados de las fuentes de datos con los informes de Workspace.

## Ventana Procesamiento (fuentes de datos) frente a ventana Informes (Analysis Workspace) {#processing-window}

Cada entrega de fuente de datos utiliza un periodo de procesamiento móvil de 30 días. La ventana de procesamiento proporciona el contexto histórico necesario para clasificar los eventos en una entrega de fuente de datos. Para obtener detalles acerca de la ventana de procesamiento, incluidos ejemplos, vea [Comprender la ventana de procesamiento](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-window).

En ese sentido, la ventana de procesamiento es similar a la ventana de creación de informes de Analysis Workspace (el intervalo de fechas que elija para un informe). Sin embargo, existen diferencias clave.

| Diferencias clave | Ventana Informes (Analysis Workspace) | Ventana Procesamiento (Fuentes de datos) |
|---------|---------|----------|
| **Periodo de tiempo para informar sobre**<br/> Qué eventos se incluyen en un informe o fuente | Comienza el primer día del mes del calendario en el que comienza la ventana de creación de informes y finaliza al final de dicha ventana.<p>Por ejemplo, un informe con una ventana de informes del 6 de octubre al 5 de noviembre también incluye eventos del 1 de octubre al 5 de octubre. Debido a que los datos de Workspace se acumulan, estos eventos adicionales pueden ser difíciles de notar.</p><!--SME CHECK: Confirm that every Workspace report includes events from the first day of the calendar month in which the reporting window starts (per Luke, Nov 5, 2026), including segment qualification for segments limited to the reporting window. Other docs (persistence.md Person Reporting Window row, analysis-workspace/attribution/models.md lookback window) don't describe this yet.--> | No es lo mismo que la ventana de procesamiento. <p>El lapso de tiempo para generar informes es la ventana de frecuencia, que puede ser una sola hora o un solo día al final de la ventana de procesamiento.</p> |
| **Límite de datos**<br/> Indica si los datos que están fuera de la ventana se incluyen en un informe o una fuente o si influyen en ellos | Flexible<p>Los eventos del primer día del mes natural en el que se inicia la ventana de creación de informes se incluyen en un informe de Workspace, incluso si caen antes de la ventana de creación de informes. Para obtener más información, consulte **Plazo para informar sobre** más arriba.</p><p>Los eventos que no entran dentro de la ventana de creación de informes también pueden influir en los datos de los informes de Workspace por cualquiera de los siguientes factores:</p><ul><li>**Persistencia de Dimension**: puede persistir más allá de la ventana de informes al usar la sesión, el tiempo personalizado o la métrica [caducidad](/help/data-views/component-settings/persistence.md#expiration-settings).</li><li>**Calificación de segmentos**: los segmentos pueden extenderse más allá de la ventana de creación de informes de forma predeterminada.<p>Los usuarios pueden optar por limitar el segmento a la ventana de creación de informes cuando lo creen. Incluso entonces, la calificación de segmentos considera eventos desde el primer día del mes natural en el que se inicia la ventana de creación de informes.</p></li><li>**Cálculo de sesión**: las sesiones pueden extenderse más allá de la ventana de informes. </li><li>**Transformaciones de campos derivadas**: Cualquier función de campo derivada que haga referencia a contenedores utiliza la ventana de informes.<!--SME CHECK: Confirm that Session- and Person-scoped derived field functions (Deduplicate, Next or Previous, Summarize, Date Math) are limited to the reporting window in Workspace, or whether Session scope can extend beyond it like session calculation. ALSO: In the Segment qualification bullet, add a link to the new docs about limiting a segment to the reporting window.--></li></ul> | Fijo<p>En una fuente de datos solo se incluyen los eventos de la ventana de frecuencia. Para obtener más información, consulte **Plazo para informar sobre** más arriba.</p><p>Los eventos que se producen fuera de la ventana de frecuencia pero dentro de la ventana de procesamiento pueden influir en los datos de una fuente de datos. Los eventos que se producen antes de la ventana de procesamiento generalmente no pueden hacerlo. La ventana de procesamiento limita los siguientes factores:</p><ul><li>**Persistencia de Dimension**: no se puede mantener más allá de la ventana de procesamiento al usar la sesión, la ventana de informes de personas o la métrica [caducidad](/help/data-views/component-settings/persistence.md#expiration-settings). A diferencia de Workspace, la retrospectiva no se extiende hasta el primer día del mes. Puede persistir más allá del período de procesamiento (hasta 90 días) al usar Tiempo personalizado [caducidad](/help/data-views/component-settings/persistence.md#expiration-settings), igual que en Workspace. Tanto en Workspace como en las fuentes de datos, la ventana retrospectiva de tiempo personalizado no se extiende hasta el primer día del mes.<p>**Nota:** Actualmente, la caducidad de Tiempo personalizado también está limitada a la ventana de procesamiento. La compatibilidad con tiempos personalizados que se extienden más allá de la ventana de procesamiento estará disponible próximamente.</p></li><li>**Calificación de segmentos**: Siempre limitado a la ventana de procesamiento. A diferencia de Workspace, no se extiende hasta el primer día del mes.</li><li>**Cálculo de sesión**: Siempre limitado a la ventana de procesamiento.</li><li>**Transformaciones de campo derivadas**: todas las funciones de campo derivadas que hacen referencia a contenedores utilizan la ventana de procesamiento en las exportaciones de fuentes de datos.</li></ul> |

>[!BEGINSHADEBOX]

**Ejemplo**

Los ejemplos siguientes ilustran cómo las diferencias entre la ventana de informes y la ventana de procesamiento pueden provocar discrepancias de datos entre los informes de Workspace y las entregas de fuentes de datos.

* **Lapso de tiempo para informar sobre**: Un usuario tiene un evento el 1 de octubre que establece un valor de dimensión y más eventos más adelante en octubre. Un informe de Workspace con una ventana de creación de informes que comienza el 6 de octubre incluye el evento del 1 de octubre, ya que Workspace incluye eventos desde el primer día del mes. El valor establecido el 1 de octubre también puede persistir en los eventos del usuario en la ventana de creación de informes. Una entrega de fuentes de datos con una ventana de procesamiento que comienza el 6 de octubre no tiene en cuenta el evento del 1 de octubre, por lo que el valor que establece no persiste en los eventos del usuario en la entrega.

* **Calificación de segmentos**: Un usuario calificado para un segmento con un contenedor de persona hace 45 días y tiene un evento hoy. Un informe de Workspace con una ventana de informes de 30 días incluye el evento del usuario, ya que los segmentos pueden extenderse más allá de la ventana de informes de forma predeterminada. La entrega de fuentes de datos de hoy no incluye el evento, ya que la calificación de segmentos se limita al periodo de procesamiento de 30 días.

<!-- update the following graphic: ![Data differences between workspace and data feeds](assets/data-feed-data-differences.png) -->

>[!ENDSHADEBOX]

## Vinculación de reproducciones

Cada vez que se ejecuta una reproducción de vinculación, los datos de identidad históricos se actualizan de forma retroactiva.

Las fuentes de datos y Analysis Workspace tratan la vinculación de reproducciones de forma diferente, de la siguiente manera:

* **Fuentes de datos**: solo refleja la identidad enlazada en el momento de la exportación. Los resultados de la reproducción no se aplican de forma retroactiva a los archivos exportados.

* **Analysis Workspace**: muestra los datos enlazados más actuales, actualizados de forma retroactiva cada vez que se ejecuta una reproducción. Los datos históricos cambian después de cada reproducción, por lo que Workspace siempre refleja la resolución de identidad más reciente.

## Eventos que llegan tarde

En una fuente de datos, los eventos pueden llegar después de que se cierre la ventana de exportación de fuentes de datos.

Las fuentes de datos y Analysis Workspace funcionan de forma diferente en relación con los eventos anteriores, como se indica a continuación:

* **Fuentes de datos**: exporta datos en un período de tiempo fijo (la hora o el día de cada envío), según las marcas de tiempo del evento.

  Antes de procesar cada envío, Customer Journey Analytics espera el [retraso de procesamiento](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-delay) que usted elija. Los eventos que llegan durante el retraso del procesamiento se incluyen en la entrega. Los eventos que llegan después de que comience el procesamiento no se incluyen en el archivo de fuente de datos.

* **Analysis Workspace**: procesa los datos en el momento del informe, por lo que los eventos se incluyen en los informes independientemente del momento en que se recibieron.

## Lote de datos

A veces, los datos se envían en un lote que abarca un período de tiempo prolongado.

Las fuentes de datos y Analysis Workspace funcionan de forma diferente con los datos por lotes, como se indica a continuación:

* **Fuentes de datos**: distribuye los datos por lotes cada día u hora según las marcas de tiempo originales. Por ejemplo, un lote que contiene 30 días de datos se propaga durante 30 días de exportaciones, de modo que solo aparece un pequeño trozo en una sola exportación.

* **Analysis Workspace**: muestra todos los datos en un lote tan pronto como se han procesado por completo, independientemente del intervalo de tiempo incluido en el lote.

