---
description: Comprenda las funcionalidades de creación de informes en tiempo real en Customer Journey Analytics.
title: Información general de informes en tiempo real
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
exl-id: 12fbb760-936d-4e30-958f-764febca5ae7
source-git-commit: b833914e7066fa660f856737d6b8a6392aae2feb
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 3%

---

# Resumen de informes en tiempo real

La creación de informes en tiempo real en Customer Journey Analytics muestra y actualiza datos y visualizaciones en uno o varios paneles de Analysis Workspace en tiempo real.

{{release-limited-testing}}

{{ultimate-package}}

## Casos de uso

Esta sección proporciona información general sobre los casos de uso habituales y menos valiosos. Y también información sobre cuándo no considerar la creación de informes en tiempo real.

* Los casos de uso más valiosos para los informes en tiempo real son las principales ventas, promociones o lanzamientos de productos.
Como parte de ese lanzamiento, desea saber lo siguiente:

   * ¿Cómo se comparan las ventas con su última venta?
   * ¿En qué se diferencia este lanzamiento de producto del último?
   * ¿Funcionan realmente tus promociones para este importante día o evento?

* Los casos de uso relevantes, pero menos valiosos, para la creación de informes en tiempo real son los casos de uso de validación.
Desea validar, por ejemplo:

   * ¿Funciona realmente el recorrido de campaña que ha iniciado recientemente?
   * Cuando se lanzó la nueva página de productos, ¿está recopilando datos de clientes de la página?
   * ¿Funciona correctamente su evento de medios en directo?

No considere la creación de informes en tiempo real para las operaciones que supervisan casos de uso. Por ejemplo, para responder a la pregunta de si un sitio funciona correctamente. Dado que [cambio de actualización en tiempo real](use-real-time.md) se deshabilita automáticamente después de 30 minutos y el informe en tiempo real deja de actualizarse, no debería usar un informe en tiempo real como una fuente confiable para estos casos de uso.


## Definición

El aspecto en tiempo real de los informes en tiempo real para Customer Journey Analytics se define como los datos y las visualizaciones que se actualizan en un plazo aproximado de 6,5 minutos desde el momento en que se incorporan los datos subyacentes a través de la conexión asociada.

Varios componentes de la configuración de la recopilación de datos determinan la latencia de la creación de informes en tiempo real.

![Creación de informes en tiempo real](assets/real-time-reporting-latencies.svg){zoomable="yes"}

| | Descripción | Latencia |
|:---:|---|--:|
| 1 | Datos recopilados mediante SDK/API de Edge Network en Edge Network. | &lt; 500 milisegundos |
| 2 | Datos duplicados de Edge Network en el servicio de recopilación y validación de datos de Experience Platform Hub. | &lt; 5 minutos |
| 3 | Datos recopilados mediante conectores de flujo continuo en el servicio de recopilación y validación de datos en Experience Platform Hub. | &lt; 15 minutos |
| 4 | Datos recopilados mediante Adobe Analytics y reenviados por el conector de origen de Analytics al procesador de conectores de origen en Experience Platform Hub. | &lt; 15 minutos |
| 5 | Datos recopilados a través de otros conectores de origen en el procesador de conectores de origen en Experience Platform Hub. | &lt; 24 horas |
| 6 | Datos procesados por el procesador en tiempo real para un conjunto de datos consolidado para informes en tiempo real. | &lt; 90 segundos |

## Limitaciones

Tenga en cuenta la siguiente limitación para los informes en tiempo real:

* Los informes en tiempo real solo incluyen datos disponibles en un periodo móvil de 24 horas. Los datos que cruzan este periodo móvil de 24 horas se ocultan para la creación de informes en tiempo real. Una vez que la [actualización en tiempo real](use-real-time.md) de un informe esté deshabilitada o desactivada automáticamente, todos los datos relevantes de un informe volverán a estar disponibles.
* La atribución, la segmentación, las métricas calculadas y mucho más solo funcionan en los datos disponibles dentro del período móvil de 24 horas.
* La creación de informes en tiempo real funciona mejor con datos de nivel de evento y sesión, y debe tener cuidado al utilizar la creación de informes en tiempo real con datos de nivel de persona. <!--Need to explain this a bit better --> Dado que solo los eventos del período móvil de 24 horas están disponibles para los informes en tiempo real, el historial de eventos de una persona también se limita a esta ventana. Tenga en cuenta la preferencia por los datos de nivel de evento y de sesión al seleccionar una dimensión y métricas (calculadas). Y cuando utiliza funcionalidades como desgloses, siguiente o anterior, y más en el panel habilitado para la actualización en tiempo real.
* No se puede combinar la vinculación con los informes en tiempo real. <!-- Do we need to explain this in more detail, why? --> Los informes en tiempo real se refieren a los datos de nivel de evento y de sesión, y son menos relevantes para los datos basados en personas.
* No hay métricas de medios recopilados de Heartbeat disponibles, excepto métricas de inicio y cierre de medios. Por lo tanto, puede seguir utilizando los informes en tiempo real para habilitar un caso de uso de medios.
* Cuando use las [opciones de descarga o exportación](/help/analysis-workspace/export/download-send.md) para descargar un proyecto o exportar datos desde una tabla de forma libre, tenga en cuenta lo siguiente:
   * Un proyecto CSV descargado o un archivo CSV exportado contiene los datos en tiempo real disponibles en el momento de la descarga o exportación.
   * Un proyecto de PDF descargado contiene datos no en tiempo real, similares a los datos que se muestran cuando la actualización en tiempo real está desactivada.
