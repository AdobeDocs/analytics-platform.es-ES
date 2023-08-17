---
title: Preguntas frecuentes sobre vinculación
description: Preguntas frecuentes sobre la vinculación
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
source-git-commit: d7dd5f4f0ef53e61755cf02c49c2f7f081ff4b39
workflow-type: tm+mt
source-wordcount: '1299'
ht-degree: 42%

---

# Preguntas frecuentes

Estas son algunas de las preguntas más frecuentes sobre la vinculación:

+++**¿Cómo puedo usar la vinculación para ver cómo se mueve la gente de un canal a otro?**

Puede utilizar una visualización de flujo con la dimensión ID de conjunto de datos.

1. Iniciar sesión en [Customer Journey Analytics](https://analytics.adobe.com) y cree un proyecto de Workspace en blanco.
2. Seleccione el **[!UICONTROL ** Visualizaciones **]** a la izquierda y arrastre una **[!UICONTROL ** Flujo **]** visualización en el lienzo de la derecha.
3. Seleccione el **[!UICONTROL ** Componentes **]** a la izquierda y arrastre la dimensión **[!UICONTROL ** ID de conjunto de datos **]** a la ubicación central con la etiqueta **[!UICONTROL ** Dimension o elemento **]**.
4. Este informe de flujo es interactivo. Para expandir los flujos a páginas posteriores o anteriores, seleccione cualquiera de los valores. Utilice el menú que aparece al hacer clic con el botón derecho para expandir o contraer columnas. También se pueden utilizar distintas dimensiones dentro del mismo informe de flujo.

Puede utilizar un conjunto de datos de búsqueda si desea cambiar el nombre de los elementos de la dimensión de ID de conjunto de datos.

+++

+++**¿Hasta dónde llega la vinculación a los visitantes de repetición?**

La ventana retrospectiva para la regeneración de claves depende de la frecuencia deseada de [reproducción](explained.md) de los datos. Por ejemplo, si configura la vinculación para que reproduzca los datos una vez por semana, la ventana retrospectiva para la regeneración de claves será de siete días. Si configura la vinculación para que reproduzca datos todos los días, la ventana retrospectiva para la regeneración de claves será de un día.

+++

+++**¿Cómo se gestionan los dispositivos compartidos?**

En algunas situaciones, es posible que varias personas inicien sesión desde el mismo dispositivo. Algunos ejemplos son un dispositivo compartido en casa, un equipo compartido en una biblioteca o un quiosco en un punto de venta minorista.

El ID transitorio anula al ID persistente, por lo que los dispositivos compartidos se consideran personas independientes (incluso si se originan en el mismo dispositivo).

+++

+++**¿Cómo gestiona la vinculación las situaciones en las que una sola persona tiene muchos ID persistentes?**

En algunas situaciones, un usuario individual puede asociarse con muchos ID persistentes. Un ejemplo es una persona que borra las cookies del explorador con frecuencia o que utiliza el modo privado/de incógnito del explorador.

El número de ID persistentes es irrelevante en favor del ID transitorio. Un solo usuario puede pertenecer a numerosos dispositivos sin que ello afecte a la capacidad del Customer Journey Analytics para crear vínculos entre los distintos dispositivos.

+++

+++**Tras contactar con el equipo de cuentas de Adobe y proporcionarle la información deseada, ¿cuánto tarda en estar disponible el conjunto de datos cuya clave se ha vuelto a generar?**

La vinculación en tiempo real está disponible aproximadamente una semana después de que el Adobe active la vinculación. La disponibilidad del relleno depende de la cantidad de datos existentes. Los conjuntos de datos pequeños (menos de 1 millón de eventos por día) suelen tardar un par de días, mientras que los grandes conjuntos de datos (1000 millones de eventos por día) pueden tardar una semana o más.

+++

+++**¿Cuál es la diferencia entre el análisis entre dispositivos (una función tradicional de Analytics) y el análisis entre canales?**

[Análisis entre dispositivos](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=es) es una función específica de la versión tradicional de Adobe Analytics que le permite comprender cómo funcionan las personas en distintos dispositivos. Ofrece dos flujos de trabajo para vincular datos de dispositivos: vinculación basada en el campo y el gráfico del dispositivo.

El análisis en canales múltiples es un caso de uso específico de Customer Journey Analytics que le permite comprender cómo funcionan las personas en ambos dispositivos y canales. Vincula el ID de persona de un conjunto de datos, lo que permite que ese conjunto de datos se combine sin problemas con otros conjuntos de datos. Esta función funciona de forma similar al de la vinculación basada en el campo de análisis entre dispositivos, pero la implementación es diferente debido a la diferente arquitectura de datos entre Analytics tradicional y Customer Journey Analytics. Consulte [Vinculación](overview.md) y el [análisis en canales múltiples](../use-cases/cross-channel/cross-channel.md) caso de uso para obtener más información.

+++

+++**¿Cómo gestiona la vinculación las solicitudes del RGPD y CCPA?**

El Adobe gestiona las solicitudes del RGPD y CCPA de conformidad con las leyes locales e internacionales. Adobe ofrece el [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=es) para enviar solicitudes de acceso a datos y de eliminación. Las solicitudes se aplican tanto a los conjuntos de datos originales como a aquellos cuyas claves se volvieron a generar.

+++

+++**¿Qué sucede si está vacío el campo ID persistente de uno o varios eventos?**

Si el campo ID persistente está en blanco en un evento de un conjunto de datos que se está vinculando, el ID vinculado para ese evento se determina de una de las dos maneras siguientes:

* Si el campo ID de transición no está en blanco, el Customer Journey Analytics utiliza el valor de ID de transición como ID con título.
* Si el campo ID de transición está en blanco, el Customer Journey Analytics también deja en blanco el ID vinculado. En este caso, ID persistente, ID transitorio y ID vinculado están todos en blanco en el evento. Estos tipos de eventos se pierden de cualquier conexión de Customer Journey Analytics usando el conjunto de datos que se está vinculando, donde el ID vinculado se eligió como ID de persona.

+++


+++**¿Qué sucede si el campo ID transitorio de uno o varios eventos tiene valores de marcador de posición, como &quot;Indefinido&quot;?**

Tenga cuidado con el &quot;colapso de persona&quot;, que se produce cuando se aplica la vinculación a datos que utilizan valores de marcador de posición para ID transitorios. En la tabla de ejemplo siguiente, los ID de persona no definidos procedentes de un conjunto de datos procedentes de un sistema CRM se rellenan con el valor &quot;No definido&quot;, lo que da como resultado una representación incorrecta de las personas.

| Evento | Marca de tiempo | ID persistente (ID de cookie) | ID transitorio (ID de inicio de sesión) | ID vinculado (después de la reproducción) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 123 | - | **Cory** |
| 2 | 2023-05-12 12:02 | 123 | Cory | **Cory** |
| 3 | 2023-05-12 12:03 | 456 | Indefinido | **Indefinido** |
| 4 | 2023-05-12 12:04 | 456 | - | **Indefinido** |
| 5 | 2023-05-12 12:05 | 789 | Indefinido | **Indefinido** |
| 6 | 2023-05-12 12:06 | 012 | Indefinido | **Indefinido** |
| 7 | 2023-05-12 12:07 | 012 | - | **Indefinido** |
| 8 | 2023-05-12 12:03 | 789 | Indefinido | **Indefinido** |
| 9 | 2023-05-12 12:09 | 456 | - | **Indefinido** |
| 10 | 2023-05-12 12:02 | 123 | - | **Cory** |
| | | **4 dispositivos** | **2 personas**:<br/>Eventos 1, 4, 7, 9, 10 perdidos | **2 personas**:<br/>Cory, no autenticado (contraído a una persona) |

+++

+++**¿En qué se parecen las métricas de los conjuntos de datos enlazados por el Customer Journey Analytics y las de los conjuntos de datos no enlazados por el Customer Journey Analytics y las de Adobe Analytics?**

Ciertas métricas en Customer Journey Analytics son similares a las métricas en la versión tradicional de Analytics, pero otras son diferentes, según lo que esté comparando. La siguiente tabla compara varias métricas comunes:

| **Datos vinculados de Customer Journey Analytics** | **Datos no vinculados de Customer Journey Analytics** | **Adobe Analytics** | **Analytics Ultimate con CDA** |
| ----- | ----- | ----- | ----- |
| **People** = Recuento de ID de persona diferentes donde el ID vinculado se elige como ID de persona. **Las personas** pueden ser superiores o inferiores a los **visitantes únicos** en Adobe Analytics tradicional, según el resultado del proceso de identificación entre dispositivos. | **People** = Recuento de ID de persona distintos en función de la columna seleccionada como ID de persona. **People** en los conjuntos de datos del conector de origen de Analytics es similar a **Visitantes únicos** en Adobe Analytics tradicional si `endUserIDs._experience.aaid.id` se utiliza como ID de persona en Customer Journey Analytics. | **Visitantes únicos** = Recuento de ID de visitantes diferentes. **Visitantes únicos** pueden no ser los mismos que el recuento de **ECID** distintos. | Consulte [Personas](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=es). |
| **Sesiones**: se define en función de la configuración de sesiones en la vista de datos de Customer Journey Analytics. El proceso de identificación entre dispositivos puede combinar sesiones individuales de varios dispositivos en una sola sesión. | **Sesiones**: se define en función de la configuración de sesiones especificada en la vista de datos de Customer Journey Analytics. | **Visitas**: consulte [Visitas](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=es). | **Visitas**: se define en función de la configuración de sesiones especificada en el [grupo de informes virtuales de CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=es). |
| **Eventos** = recuento de filas en los datos enlazados en Customer Journey Analytics. Esta métrica suele estar cerca de **Ocurrencias** en Adobe Analytics tradicional. Sin embargo, tenga en cuenta las preguntas más frecuentes anteriores sobre las filas con un ID persistente en blanco. | **Eventos** = recuento de filas en los datos no enlazados en Customer Journey Analytics. Esta métrica suele estar cerca de **Ocurrencias** en Adobe Analytics tradicional. Sin embargo, tenga en cuenta que si algún evento tiene un ID de persona en blanco en los datos no enlazados en el lago de datos del Experience Platform, estos eventos no se incluyen en el Customer Journey Analytics. | **Ocurrencias**: consulte [Ocurrencias](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=es). | **Ocurrencias**: consulte [Ocurrencias](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=es). |

Otras métricas pueden ser similares en Customer Journey Analytics y Adobe Analytics. Por ejemplo, el recuento total de Adobe Analytics [eventos personalizados](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=es) 1-100 es comparable entre Adobe Analytics tradicional y el Customer Journey Analytics (ya se haya vinculado o no). [Diferencias en las capacidades](/help/getting-started/aa-vs-cja/cja-aa.md)), como la deduplicación de eventos entre Customer Journey Analytics y Adobe Analytics, puede causar discrepancias entre los dos productos.

+++

+++**¿Puede el Customer Journey Analytics utilizar los campos del mapa de identidad?**

No, el Customer Journey Analytics no puede usar actualmente los campos del mapa de identidad para la vinculación.

+++
