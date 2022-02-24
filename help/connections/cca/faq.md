---
title: Preguntas frecuentes sobre Análisis entre canales
description: Preguntas frecuentes sobre Análisis entre canales
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '976'
ht-degree: 100%

---

# Preguntas frecuentes

## ¿Cómo puedo usar AEC para ver cómo se mueve la gente de un canal a otro?

Puede utilizar una visualización de flujo con la dimensión ID de conjunto de datos.

1. Inicie sesión en [analytics.adobe.com](https://analytics.adobe.com) y cree un proyecto del Espacio de trabajo en blanco.
2. Haga clic en la pestaña Visualizaciones de la izquierda y arrastre una visualización de Flujo al lienzo de la derecha.
3. Haga clic en la pestaña Componentes de la izquierda y arrastre la dimensión ID de conjunto de datos a la ubicación central denominada Dimensión o elemento.
4. Este informe de flujo es interactivo. Haga clic en cualquiera de los valores para expandir los flujos a páginas posteriores o anteriores. Utilice el menú que aparece al hacer clic con el botón derecho para expandir o contraer columnas. También se pueden utilizar distintas dimensiones dentro del mismo informe de flujo.

Puede utilizar un conjunto de datos de búsqueda si desea cambiar el nombre de los elementos de la dimensión de ID de conjunto de datos.

## ¿Cuánto tiempo atrás vuelve AEC a generar las claves de los visitantes?

La ventana retrospectiva para la regeneración de claves depende de la frecuencia deseada de [reproducción](replay.md) de los datos. Por ejemplo, si configura AEC para que reproduzca los datos una vez por semana, la ventana retrospectiva para la regeneración de claves será de 7 días. Si configura AEC para que reproduzca datos todos los días, la ventana retrospectiva para la regeneración de claves será de 1 día.

## ¿Cómo se gestionan los dispositivos compartidos?

En algunas situaciones es posible que varias personas inicien sesión desde el mismo dispositivo. Algunos ejemplos son un dispositivo compartido en casa, un equipo compartido en una biblioteca o un quiosco en un punto de venta minorista.

El ID transitorio anula al ID persistente, por lo que los dispositivos compartidos se consideran personas independientes (incluso si se originan en el mismo dispositivo).

## ¿Cómo gestiona AEC las situaciones en las que una sola persona tiene un gran número de ID persistentes?

En algunas situaciones, un usuario individual puede tener asociado un gran número de ID persistentes. Algunos ejemplos de esto son las personas que borran las cookies del explorador con frecuencia o que utilizan el modo privado/de incógnito del explorador.

El número de ID persistentes es irrelevante en favor del ID transitorio. Un solo usuario puede pertenecer a numerosos dispositivos sin que ello afecte a la capacidad de AEC para crear vínculos entre los diferentes dispositivos.

## Tras contactar con el administrador de cuentas y proporcionarle la información deseada, ¿cuánto tarda en estar disponible el conjunto de datos cuya clave se ha vuelto a generar?

La vinculación en tiempo real está disponible aproximadamente 1 semana después de que Adobe active Análisis entre canales. La disponibilidad del relleno depende de la cantidad de datos existentes. Los conjuntos de datos pequeños (menos de 1 millón de eventos por día) suelen tardar un par de días, mientras que los grandes conjuntos de datos (1000 millones de eventos por día) pueden tardar una semana o más.

## ¿Cómo gestiona Análisis entre canales las solicitudes del RGPD y CCPA?

Adobe gestiona las solicitudes del RGPD y CCPA de conformidad con las leyes locales e internacionales. Adobe ofrece el [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=es) para enviar solicitudes de acceso a datos y de eliminación. Las solicitudes se aplican tanto a los conjuntos de datos originales como a aquellos cuyas claves se volvieron a generar.

## ¿Qué sucede si está vacío el campo ID persistente de uno o varios eventos?

Si el campo `Persistent ID` está en blanco en un evento de un conjunto de datos que se está vinculando con la vinculación basada en el campo, CCA rellena el `Stitched ID` para ese evento de una de las dos maneras siguientes:
* Si el campo `Transient ID` no está en blanco, CCA utiliza el valor en `Transient ID` como `Stitched ID`.
* Si el campo `Transient ID` está en blanco, CCA también deja el `Stitched ID` en blanco. En este caso, `Persistent ID`, `Transient ID` y `Stitched ID` estarán en blanco en el evento. Eventos como este se eliminan de CJA en cualquier conexión CJA usando el conjunto de datos que se está vinculando donde `Stitched ID` se eligió como `Person ID`.

## ¿En qué se parecen las métricas de los conjuntos de datos enlazados de CJA y las de los conjuntos de datos no enlazados de CJA y las de la Adobe Analytics tradicional?

Ciertas métricas en CJA son similares a las métricas en la versión tradicional de Analytics, pero otras son bastante diferentes, según lo que esté comparando. La siguiente tabla compara varias métricas comunes:

| **Datos vinculados de CJA** | **Datos no identificados entre dispositivos de CJA** | **Adobe Analytics tradicional** | **Analytics Ultimate con CDA** |
| ----- | ----- | ----- | ----- |
| **Personas** = Recuento de `Person ID` diferentes donde `Stitched ID` se elige como `Person ID`. **Las personas** pueden ser superiores o inferiores a los **visitantes únicos** en Adobe Analytics tradicional, según el resultado del proceso de identificación entre dispositivos. | **Personas** = Recuento de `Person ID` diferentes según la columna seleccionada como `Person ID`. **Las personas** en los conjuntos de datos del conector de Adobe Analytics (ADC) son similares a los **visitantes únicos** en Adobe Analytics tradicional si `endUserIDs. _experience. aaid.id` se elige como `Person ID` en CJA. | **Visitantes únicos** = Recuento de ID de visitantes diferentes. Tenga en cuenta que **Visitantes únicos** pueden no ser los mismos que el recuento de **ECID** distintos. | Consulte [Personas](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=es). |
| **Sesiones**: se define en función de la configuración de sesiones especificada en la vista de datos de CJA. El proceso de identificación entre dispositivos puede combinar sesiones individuales de varios dispositivos en una sola sesión. | **Sesiones**: se define en función de la configuración de sesionización especificada en la vista de datos de CJA. | **Visitas**: consulte [Visitas](https://experienceleague.adobe.com/docs/analytics/components/metrics/visitis.html?lang=es). | **Visitas**: se define en función de la configuración de sesiones especificada en el grupo de informes virtuales de [CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=es). |
| **Eventos** = recuento de filas en los datos enlazados en CJA. Generalmente, esto debería estar cerca de **Ocurrencias** en la versión tradicional de Adobe Analytics. No obstante, tenga en cuenta las preguntas más frecuentes anteriores sobre las filas con un `Persistent ID` en blanco. | **Eventos** = recuento de filas en los datos no enlazados en CJA. Generalmente, esto debería estar cerca de **Ocurrencias** en la versión tradicional de Adobe Analytics. Sin embargo, tenga en cuenta que si algún evento tiene un `Person ID` en blanco en los datos no enlazados en el lago de datos de AEP, estos eventos se perderán (no se incluirán) en CJA. | **Ocurrencias**: consulte [Ocurrencias](https://experienceleague.adobe.com/docs/analytics/components/metrics/ocurrences.html?lang=es). | **Ocurrencias**: consulte [Ocurrencias](https://experienceleague.adobe.com/docs/analytics/components/metrics/ocurrences.html?lang=es). |

Otras métricas pueden ser similares en CJA y en Adobe Analytics tradicional. Por ejemplo, el recuento total de eventos [personalizados](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=es) de Adobe Analytics (eventos 1-100) debería estar muy cerca en la versión tradicional de Adobe Analytics y CJA (ya se haya vinculado o no). Sin embargo, tenga en cuenta que esto puede no ser siempre cierto debido a [diferencias en las capacidades](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-aa.html?lang=es), como la deduplicación de eventos entre CJA y Adobe Analytics tradicional.
