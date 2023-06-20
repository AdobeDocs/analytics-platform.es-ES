---
title: Preguntas frecuentes sobre Cross-Channel Analytics
description: Preguntas frecuentes sobre Cross-Channel Analytics
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '1101'
ht-degree: 66%

---

# Preguntas frecuentes

## ¿Cómo puedo usar CCA para ver cómo se mueve la gente de un canal a otro?

Puede utilizar una visualización de flujo con la dimensión ID de conjunto de datos.

1. Inicie sesión en [analytics.adobe.com](https://analytics.adobe.com) y cree un proyecto del Espacio de trabajo en blanco.
2. Haga clic en la pestaña Visualizaciones de la izquierda y arrastre una visualización de Flujo al lienzo de la derecha.
3. Haga clic en la pestaña Componentes de la izquierda y arrastre la dimensión ID de conjunto de datos a la ubicación central denominada Dimensión o elemento.
4. Este informe de flujo es interactivo. Haga clic en cualquiera de los valores para expandir los flujos a páginas posteriores o anteriores. Utilice el menú que aparece al hacer clic con el botón derecho para expandir o contraer columnas. También se pueden utilizar distintas dimensiones dentro del mismo informe de flujo.

Puede utilizar un conjunto de datos de búsqueda si desea cambiar el nombre de los elementos de la dimensión de ID de conjunto de datos.

## ¿Hasta dónde regresa CCA a las personas?

La ventana retrospectiva para la regeneración de claves depende de la frecuencia deseada de [reproducción](replay.md) de los datos. Por ejemplo, si configura CCA para que reproduzca los datos una vez por semana, la ventana retrospectiva para la regeneración de claves será de siete días. Si configura CCA para que reproduzca datos todos los días, la ventana retrospectiva para la regeneración de claves será de un día.

## ¿Cómo se gestionan los dispositivos compartidos?

En algunas situaciones, es posible que varias personas inicien sesión desde el mismo dispositivo. Algunos ejemplos son un dispositivo compartido en casa, un equipo compartido en una biblioteca o un quiosco en un punto de venta minorista.

El ID transitorio anula al ID persistente, por lo que los dispositivos compartidos se consideran personas independientes (incluso si se originan en el mismo dispositivo).

## ¿Cómo gestiona el CCA las situaciones en las que una sola persona tiene muchos ID persistentes?

En algunas situaciones, un usuario individual puede asociarse con muchos ID persistentes. Algunos ejemplos de esto son las personas que borran las cookies del explorador con frecuencia o que utilizan el modo privado/de incógnito del explorador.

El número de ID persistentes es irrelevante en favor del ID transitorio. Un solo usuario puede pertenecer a numerosos dispositivos sin que ello afecte a la capacidad de CCA para crear vínculos entre los diferentes dispositivos.

## Una vez que contacto con mi equipo de cuenta de Adobe y le proporciono la información deseada, ¿cuánto tiempo tarda en estar disponible el conjunto de datos cuya clave se ha vuelto a generar?

La vinculación en tiempo real está disponible aproximadamente una semana después de que Adobe active Cross-Channel Analytics. La disponibilidad del relleno depende de la cantidad de datos existentes. Los conjuntos de datos pequeños (menos de 1 millón de eventos por día) suelen tardar un par de días, mientras que los grandes conjuntos de datos (1000 millones de eventos por día) pueden tardar una semana o más.

## ¿Cuál es la diferencia entre Cross-Device Analytics (una función de Adobe Analytics) y Cross-Channel Analytics?

[Análisis entre dispositivos](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=es) es una función específica de la versión tradicional de Adobe Analytics que le permite comprender cómo funcionan las personas en distintos dispositivos. Ofrece dos flujos de trabajo para vincular datos de dispositivos: vinculación basada en el campo y el gráfico del dispositivo.

[Análisis entre canales](/help/cca/overview.md) es una función específica de Customer Journey Analytics que le permite comprender cómo funcionan las personas en ambos dispositivos y canales. Vuelve a codificar el ID de persona de un conjunto de datos, lo que permite que ese conjunto de datos se combine sin problemas con otros conjuntos de datos. Esta función funciona de forma similar al de la vinculación basada en el campo de CDA, pero la implementación es diferente debido a la diferente arquitectura de datos entre Adobe Analytics y Customer Journey Analytics.

## ¿Cómo gestiona Cross-Channel Analytics las solicitudes del RGPD y CCPA?

Adobe gestiona las solicitudes del RGPD y CCPA de conformidad con las leyes locales e internacionales. Adobe ofrece el [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=es) para enviar solicitudes de acceso a datos y de eliminación. Las solicitudes se aplican tanto a los conjuntos de datos originales como a aquellos cuyas claves se volvieron a generar.

## ¿Qué sucede si está vacío el campo ID persistente de uno o varios eventos?

Si el campo `Persistent ID` está en blanco en un evento de un conjunto de datos que se está vinculando con la vinculación basada en el campo, CCA rellena el `Stitched ID` para ese evento de una de las dos maneras siguientes:

* Si el campo `Transient ID` no está en blanco, CCA utiliza el valor en `Transient ID` como `Stitched ID`.
* Si el campo `Transient ID` está en blanco, CCA también deja el `Stitched ID` en blanco. En este caso, `Persistent ID`, `Transient ID` y `Stitched ID` están en blanco en el evento. Estos tipos de eventos se pierden de cualquier conexión de Customer Journey Analytics usando el conjunto de datos que se está vinculando donde `Stitched ID` se eligió como el `Person ID`.

## ¿En qué se parecen las métricas de los conjuntos de datos enlazados por el Customer Journey Analytics y las de los conjuntos de datos no enlazados por el Customer Journey Analytics y las de la Adobe Analytics tradicional?

Ciertas métricas en Customer Journey Analytics son similares a las métricas en Adobe Analytics, pero otras son bastante diferentes, según lo que esté comparando. La siguiente tabla compara varias métricas comunes:

| **datos vinculados del Customer Journey Analytics** | **datos no enlazados del Customer Journey Analytics** | **Adobe Analytics tradicional** | **Analytics Ultimate con CDA** |
| ----- | ----- | ----- | ----- |
| **Personas** = Recuento de `Person ID` diferentes donde `Stitched ID` se elige como `Person ID`. **Las personas** pueden ser superiores o inferiores a los **visitantes únicos** en Adobe Analytics tradicional, según el resultado del proceso de identificación entre dispositivos. | **Personas** = Recuento de `Person ID` diferentes según la columna seleccionada como `Person ID`. **People** en los conjuntos de datos del conector de origen de Adobe es similar a **Visitantes únicos** en Adobe Analytics tradicional si `endUserIDs._experience.aaid.id` se elige como `Person ID` en Customer Journey Analytics. | **Visitantes únicos** = Recuento de ID de persona diferentes. **Visitantes únicos** pueden no ser los mismos que el recuento de **ECID** distintos. | Consulte [Personas](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=es). |
| **Sesiones**: se define en función de la configuración de sesión en la vista de datos del Customer Journey Analytics. El proceso de identificación entre dispositivos puede combinar sesiones individuales de varios dispositivos en una sola sesión. | **Sesiones**: se define en función de la configuración de sesión especificada en la vista de datos del Customer Journey Analytics. | **Visitas**: consulte [Visitas](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=es). | **Visitas**: se define en función de la configuración de sesiones especificada en el [grupo de informes virtuales de CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=es). |
| **Eventos** = recuento de filas en los datos enlazados en Customer Journey Analytics. Esta métrica suele estar cerca de **Ocurrencias** en Adobe Analytics tradicional. No obstante, tenga en cuenta las preguntas más frecuentes anteriores sobre las filas con un `Persistent ID` en blanco. | **Eventos** = recuento de filas en los datos no enlazados en Customer Journey Analytics. Esta métrica suele estar cerca de **Ocurrencias** en Adobe Analytics tradicional. Sin embargo, tenga en cuenta que si algún evento tiene un en blanco `Person ID` en los datos no enlazados del lago de datos de Experience Platform, estos eventos no se incluyen en Customer Journey Analytics. | **Ocurrencias**: consulte [Ocurrencias](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=es). | **Ocurrencias**: consulte [Ocurrencias](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=es). |

Otras métricas pueden ser similares en Adobe Analytics tradicional y Customer Journey Analytics. Por ejemplo, el recuento total de Adobe Analytics [eventos personalizados](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=es) 1-100 suele ser comparable entre Adobe Analytics tradicional y el Customer Journey Analytics (ya se haya vinculado o no). [Diferencias en las capacidades](/help/getting-started/aa-vs-cja/cja-aa.md)), como la deduplicación de eventos entre Customer Journey Analytics y Adobe Analytics tradicional, puede causar discrepancias entre los dos productos.

## ¿Puede CCA utilizar los campos del mapa de identidad?

No, actualmente CCA no puede utilizar los campos del mapa de identidad.
