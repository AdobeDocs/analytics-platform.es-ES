---
description: Factores que afectan el rendimiento y las optimizaciones de Workspace que puede hacer
title: Optimización y factores de rendimiento de Analysis Workspace
uuid: de51d03d-d555-4f0e-b19c-4a8f140770fc
translation-type: tm+mt
source-git-commit: a991dce6abaf90cbca06de75606a2517cb5b6484
workflow-type: tm+mt
source-wordcount: '1839'
ht-degree: 100%

---


# Optimizar [!UICONTROL rendimiento de Analysis Workspace]

>[!NOTE]
>
>Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

Varios factores pueden afectar el rendimiento de un proyecto dentro de Analysis Workspace. Es importante conocer cuáles son antes de comenzar a crear un proyecto, de forma que este se pueda planificar y generar de forma óptima. Esta página incluye una lista de factores que afectarán el rendimiento y las optimizaciones que puede hacer para garantizar un rendimiento máximo en Analysis Workspace.

>[!IMPORTANT]
>
>La página Rendimiento de Analysis Workspace está en versión limitada. [Más información](https://docs.adobe.com/content/help/es-ES/analytics/landing/an-releases.html)

## [!UICONTROL Ayuda] > [!UICONTROL Rendimiento] en Analysis Workspace

En **Analysis Workspace > [!UICONTROL Ayuda] > [!UICONTROL Rendimiento]**, puede ver los factores que afectan el rendimiento del proyecto, incluidos los factores de red, del explorador y del proyecto. Para obtener los resultados más precisos, deje que el proyecto se cargue completamente antes de abrir la página Rendimiento.

* La columna Proyecto actual muestra los resultados del proyecto actual y el entorno del usuario.
* La columna Directriz muestra el umbral recomendado por Adobe para cada factor.

Además, puede **Descargar como CSV** el contenido de rendimiento para compartirlo fácilmente con el Servicio de atención al cliente de Adobe o con sus equipos informáticos internos.

>[!NOTE]
>
>La información de la página Rendimiento varía cada vez que se abre el modal, ya que los factores están sujetos a cambios. Además, el Adobe seguirá perfeccionando las directrices proporcionadas a medida que se disponga de más datos.

![](assets/performance-modal.png)

## Factores de red

[!UICONTROL Ayuda] > Los factores de red de [!UICONTROL Rendimiento] incluyen:

| Factor | Definición | Afectado por | Optimización |
| --- | --- | --- | --- |
| Conexión a Adobe | Adobe envía 10 llamadas de prueba cuando se abre la página de rendimiento. Representa el porcentaje de las llamadas satisfactorias a Adobe. | Los problemas de Adobe o de red local afectarán este factor. | Consulte status.adobe.com para comprobar si hay algún problema de servicio conocido. A continuación, valide la conexión de red local. |
| Ancho de banda de internet | Disponible solo para Google Chrome. El cálculo del ancho de banda del navegador en su ubicación. La guía es de 2 MB/s. | Su conexión de red local afectará este factor. | Valide la conexión de red local. |
| Latencia de internet | Adobe envía 10 llamadas de prueba cuando se abre la página de rendimiento. Esto representa la cantidad de tiempo promedio que se tarda en devolver cada solicitud para ir a Adobe. Dicho de forma más sencilla, es una medida de la velocidad de Internet entre su ubicación y Adobe. La directriz es &lt;1 segundo. | Los problemas de red local, muchas fichas de navegador abiertas o problemas de Adobe afectarán este factor. | Consulte status.adobe.com para comprobar si hay algún problema de servicio conocido. A continuación, valide la conexión de red local y cierre las fichas del explorador que no se utilicen. |

## Factores del explorador

[!UICONTROL Ayuda] > Los factores de navegador de [!UICONTROL Rendimiento] incluyen:

| Factor | Definición | Afectado por | Optimización |
| --- | --- | --- | --- |
| Velocidad de cómputo | La velocidad con la que el equipo hace una prueba de procesamiento. La guía es &lt;750 ms. | Su hardware y sus programas simultáneos afectarán este factor. | Abra el Administrador de Tareas (PC) o el Monitor de Actividad (Mac) del equipo para determinar si se puede cerrar algún programa. A continuación, cierre las fichas del explorador que no se hayan utilizado u otros programas. <br><br>Si estas acciones no ayudan, comente los detalles de hardware con su equipo de TI. |
| Memoria utilizada | Disponible solo para Google Chrome. Cada ficha de Workspace de un navegador Google Chrome comparte 4 GB de memoria en total. Representa el porcentaje de esa asignación de memoria que está consumiendo el proyecto actual. La guía es de 3500 MB, que es el punto en el que Workspace comenzará a mostrar errores de memoria. | Trabajar en varias fichas o descargar 50 000 filas de datos contribuirá a aumentar el uso de la memoria. | Si recibe un error de memoria, cierre otras fichas de Workspace y/o ejecute 50 000 descargas de filas de a una por vez. |
| Almacenamiento local utilizado | Datos almacenados localmente en el equipo para su uso en el explorador. Cada origen (por ejemplo, experience.adobe.com) tiene una asignación de 10 MB. | Analysis Workspace utiliza el almacenamiento local para varias funciones, como almacenar proyectos guardados automáticamente (existentes), ajustes del usuario y indicadores de características. | Para garantizar que las funciones de Analysis Workspace no se interrumpan, borre el almacenamiento local del dominio experience.adobe.com. |
| Velocidad de procesamiento | FPS significa Fotogramas por segundo, que es la cantidad de veces por segundo que el navegador dibuja la página en la pantalla. 24 FPS es comúnmente lo que el ojo humano puede observar; si FPS es menor que eso, observará problemas de procesamiento en Workspace. | FPS se ve afectado por la multitarea en muchos proyectos de Workspace a la vez y por el tamaño del proyecto que se está viendo. Otros programas que se ejecutan en el equipo pueden tener un impacto, como flujo continuo, escáneres de fondo, etc. Además, su hardware afectará este factor. | Abra el Administrador de Tareas (PC) o el Monitor de Actividad (Mac) del equipo para determinar si se puede cerrar algún programa. A continuación, cierre las fichas del explorador que no se hayan utilizado u otros programas. <br><br>Si estas acciones no ayudan, comente los detalles de hardware con su equipo de TI. |

## Factores de proyecto

Los factores del proyecto [!UICONTROL Ayuda] > [!UICONTROL Rendimiento] incluyen:

| Factor | Definición | Optimización |
| --- | --- | --- |
| Cantidad de consultas | La cantidad total de consultas (solicitudes) realizadas a Adobe para recuperar datos que se muestran en el proyecto. Las consultas incluyen solicitudes de clasificación para tablas, detección de anomalías, minigráficos, componentes mostrados en el carril izquierdo, etc. Excluye paneles contraídos y visualizaciones. La directriz es 100. | Simplifique el proyecto siempre que sea posible dividiendo los datos en varios proyectos que cumplan un propósito específico o un grupo de partes interesadas. Utilice las etiquetas para organizar los proyectos en temáticas y utilice la [vinculación directa](/help/analysis-workspace/curate-share/shareable-links.md) para crear una tabla de contenido interna que permita a los interesados encontrar con más facilidad lo que necesitan. |
| Paneles ampliados (de paneles totales) | Cantidad de paneles ampliados del número total de paneles del proyecto. La directriz es 5. | Después de dar los pasos necesarios para simplificar el proyecto, contraiga los paneles del proyecto que no necesitan visualizarse durante la carga. Cuando se abra el proyecto, solo se procesarán los paneles expandidos. Los paneles contraídos no se procesarán hasta que el usuario los expanda. |
| Visualizaciones ampliadas (de visualizaciones totales) | Cantidad de tablas y visualizaciones expandidas del total del proyecto que incluye fuentes de datos ocultas. La directriz es 15. | Después de dar los pasos necesarios para simplificar el proyecto, contraiga las visualizaciones del proyecto que no necesitan visualizarse durante la carga. Priorice los elementos visuales que son más importantes para el consumidor del informe y desglose los elementos visuales de compatibilidad en un proyecto o panel diferente y más detallado, si es necesario. |
| Cantidad de celdas de forma libre | La cantidad total de celdas de tabla improvisada en el proyecto, calculadas mediante filas * columnas en todas las tablas. Excluye las fuentes de datos ocultas. La directriz es 4000. | Reduzca la cantidad de columnas de la tabla a sólo los puntos de datos más relevantes. Reduzca la cantidad de filas de la tabla ajustando el número de filas mostradas, aplicando un filtro de tabla o aplicando un segmento. |
| Componentes disponibles | Cantidad total de componentes recuperados en el carril izquierdo del proyecto, en todos los grupos de informes del proyecto. La directriz es 2000. | Hable con el administrador del producto sobre la creación de un grupo de informes virtuales seleccionado que tenga un conjunto de componentes más personalizado. |
| Componentes utilizados | Cantidad total de componentes utilizados en el proyecto. La directriz es 100. | La cantidad de componentes usados no influye directamente en el rendimiento. Sin embargo, la complejidad de esos componentes contribuirá a la ejecución del proyecto. Consulte las optimizaciones en la sección “Factores adicionales” a continuación. |
| El intervalo de fecha más largo | Este factor muestra el intervalo de fechas más largo utilizado en el proyecto. La directriz es de 1 año. | Siempre que sea posible, no incorpore más datos de los que necesita. Reduzca el calendario del panel a las fechas relevantes para el análisis o use componentes del intervalo de fechas (componentes púrpura) en las tablas improvisadas. Los intervalos de fechas utilizados en una tabla anulan el intervalo de fechas del panel. Por ejemplo, puede agregar el mes pasado, la semana pasada y ayer a las columnas de la tabla para solicitar esos intervalos de datos específicos. Para obtener más información acerca del trabajo con intervalos de fechas en Analysis Workspace, consulte [este vídeo](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/date-ranges-and-calendar-in-analysis-workspace.html). <br><br>Además, minimice el número de comparaciones año tras año utilizadas en el proyecto. Cuando se calcula una comparación año tras año, se analizan los 13 meses completos de datos entre los meses de interés. Esto tiene el mismo impacto que cambiar el intervalo de fechas del panel a los últimos 13 meses. |

## Factores adicionales

Otros factores que no se incluyen en Ayuda > Rendimiento son:

| Factor | Definición | Afectado por | Optimización |
| --- | --- | --- | --- |
| Complejidad de segmento | Los segmentos intrincados pueden tener un impacto significativo en el desempeño del proyecto. | Los factores que añaden complejidad a un segmento (en orden descendente de impacto) son: <ul><li>Los operadores de “contiene”, “contiene algo de”, “coincide con”, “comienza con” o “termina con” </li><li>Segmentación secuencial, sobre todo cuando se utilizan restricciones de dimensión (Dentro/Después) </li><li>Número de elementos de dimensiones únicas dentro de las dimensiones utilizadas en el segmento (por ejemplo, Página = “A” cuando la Página tiene 10 elementos únicos será más rápido que Página = “A” cuando la Página tiene 100000 elementos únicos) </li><li>Número de dimensiones diferentes utilizadas (por ejemplo, Página = “Home” y Página = “Search results” será más rápido que eVar 1 = “red” y eVar 2 = “blue”)</li><li>Muchos operadores OR (en lugar de AND)</li><li>Contenedores anidados que varían en ámbito (por ejemplo, Visita (hit) en el interior de la “Visita” dentro de “Visitante”)</li></ul> | Aunque algunos de los factores de complejidad no se pueden prevenir, busque opciones para reducir la complejidad de sus segmentos. En general, cuanto más específico pueda ser con sus criterios de segmento, mejor. Por ejemplo:<ul><li>Con los contenedores, el uso de un solo contenedor en la parte superior del segmento será más rápido que una serie de contenedores anidados.</li><li>Con los operadores, “es igual que” será más rápido que “contiene” y “es equivalente a” será más rápido que “contiene algo de”.</li><li>Con muchos criterios, los operadores AND serán más rápidos que varios operadores OR.</li></ul> Busque oportunidades para reducir muchas condiciones “OR” en una sola condición “es equivalente a”. <br><br>[Las clasificaciones](https://docs.adobe.com/content/help/es-ES/analytics/components/classifications/c-classifications.html) pueden ayudar a consolidar muchos valores en grupos concisos a partir de los cuales crear segmentos. La segmentación en grupos de clasificación proporciona beneficios de rendimiento sobre los segmentos con muchas condiciones “OR”, o criterios “contiene”. |
| Complejidad de la visualización (segmentos, métricas, filtros) | El tipo de visualización agregado (p. ej., abandonos o tabla improvisada) no tiene demasiada influencia por sí mismo en el rendimiento de un proyecto. Lo que afecta al tiempo de procesamiento es la complejidad de la visualización. | Entre los factores que aumentan la complejidad de una visualización están:<ul><li>Intervalo de datos solicitado</li><li>El número de segmentos aplicados; por ejemplo, los segmentos utilizados como columnas de una tabla improvisada.</li><li>Uso de segmentos complejos</li><li>Filas o columnas de [elementos manuales](/help/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) en tablas improvisada</li><li>Los filtros aplicados a las filas de una tabla improvisada.</li><li>El número de métricas incluidas, en especial las métricas calculadas que utilizan segmentos.</li></ul> | Si ha notado que sus proyectos no se cargan tan rápido como le gustaría, pruebe a sustituir algunos segmentos por eVars y filtros, si es posible.<br><br>Si usa constantemente segmentos y métricas calculadas para puntos de datos que son importantes para su negocio, plantéese mejorar su implementación para capturar estos puntos de datos de forma más directa. El uso de un administrador de etiquetas como Adobe Experience Platform Launch y las reglas de procesamiento de Adobe pueden hacer que los cambios de implementación sean rápidos y sencillos. |
| Tamaño del conjunto de informes | Cantidad de datos recopilados en el grupo de informes. | - | Consulte con su equipo de implementación o con un experto en Adobe para determinar si se pueden realizar mejoras en la implementación para mejorar la experiencia general en Adobe Analytics. |
