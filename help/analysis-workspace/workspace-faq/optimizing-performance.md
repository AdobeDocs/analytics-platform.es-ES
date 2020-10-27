---
description: Factores que afectan al rendimiento del espacio de trabajo y a las optimizaciones recomendadas
title: Optimización y factores de rendimiento de Analysis Workspace
uuid: de51d03d-d555-4f0e-b19c-4a8f140770fc
translation-type: tm+mt
source-git-commit: 3928307fb51d1bde628773a91d5f4e2d4e5c2a5c
workflow-type: tm+mt
source-wordcount: '2026'
ht-degree: 82%

---


# Optimizar rendimiento de Analysis Workspace

Varios factores pueden afectar el rendimiento de un proyecto dentro de Analysis Workspace. Es importante conocer cuáles son antes de comenzar a crear un proyecto, de forma que este se pueda planificar y generar de forma óptima. Esta página incluye una lista de factores que afectarán al rendimiento y optimizaciones recomendadas que puede realizar para garantizar un rendimiento máximo en Analysis Workspace.

>[!IMPORTANT]
>
>La página Rendimiento de Analysis Workspace está en versión limitada. [Más información](https://docs.adobe.com/content/help/es-ES/analytics/landing/an-releases.html)

## Ayuda > Rendimiento en Analysis Workspace

En **[!UICONTROL Analysis Workspace > Ayuda > Rendimiento]**, puede ver los factores que afectan el rendimiento del proyecto, incluidos los factores de red, el explorador y el proyecto. Para obtener los resultados más precisos, deje que el proyecto se cargue completamente antes de abrir la página Rendimiento. Además, puede **descargar como CSV** el contenido de rendimiento para compartirlo fácilmente con el Servicio de atención al cliente de Adobe o con sus equipos informáticos internos.

>[!NOTE]
>
>La información de la página Rendimiento varía cada vez que se abre el modal, ya que los factores están sujetos a cambios. Además, Adobe seguirá refinando los umbrales recomendados a medida que se disponga de más datos.

![](assets/performance-modal.png)

## Factores de red

**[!UICONTROL Ayuda > Los factores de red de rendimiento incluyen:]**

| Factor | Definición | Afectado por | Optimización |
| --- | --- |--- | --- |
| Conexión a Adobe | Adobe envía 10 llamadas de prueba cuando se abre la página de rendimiento. Representa el porcentaje de las llamadas satisfactorias a Adobe. | Los problemas de Adobe o de red local afectarán este factor. | Consulte status.adobe.com para comprobar si hay algún problema de servicio conocido. A continuación, valide la conexión de red local. |
| Ancho de banda de internet | La estimación del ancho de banda del navegador en su ubicación, probada solo para Google Chrome. El umbral recomendado es de 2,0 MB/s. | Su conexión de red local afectará este factor. | Valide la conexión de red local. |
| Latencia de internet | Adobe envía 10 llamadas de prueba cuando se abre la página de rendimiento. Esto representa la cantidad de tiempo promedio que se tarda en devolver cada solicitud para ir a Adobe. Dicho de forma más sencilla, es una medida de la velocidad de Internet entre su ubicación y Adobe. El umbral recomendado es &lt; 1 segundo. | Los problemas de red local, muchas fichas de navegador abiertas o problemas de Adobe afectarán este factor. | Consulte status.adobe.com para comprobar si hay algún problema de servicio conocido. A continuación, valide la conexión de red local y cierre las fichas del explorador que no se utilicen. |

## Factores del explorador

**[!UICONTROL Ayuda > Los factores del navegador de rendimiento incluyen:]**

| Factor | Definición | Afectado por | Optimización |
| --- | --- | --- | --- |
| Velocidad de cómputo | La velocidad con la que el equipo hace una prueba de procesamiento. El umbral recomendado es &lt; 750 ms. | Su hardware y sus programas simultáneos afectarán este factor. | Abra el Administrador de Tareas (PC) o el Monitor de Actividad (Mac) del equipo para determinar si se puede cerrar algún programa. A continuación, cierre las fichas del explorador que no se hayan utilizado u otros programas. <br><br>Si estas acciones no ayudan, comente los detalles de hardware con su equipo de TI. |
| Memoria utilizada | Cada ficha Espacio de trabajo de un navegador Google Chrome comparte 4 GB de memoria en total (Firefox tiene un umbral más alto). Representa el porcentaje de esa asignación de memoria que está consumiendo el proyecto actual. El umbral recomendado es un límite de 3500 MB, que es el punto en el que Workspace comenzará a mostrar errores de memoria. | Trabajar en varias fichas o descargar 50 000 filas de datos contribuirá a aumentar el uso de la memoria. | Si recibe un error de memoria, se recomienda cerrar otras fichas de Workspace y/o descargar 50000 filas una a la vez. |
| Almacenamiento local utilizado | Datos almacenados localmente en el equipo para su uso en el explorador. Cada origen (por ejemplo, experience.adobe.com) tiene una asignación de 10 MB. | Analysis Workspace utiliza el almacenamiento local para varias funciones, como almacenar proyectos guardados automáticamente (existentes), ajustes del usuario y indicadores de características. | Para garantizar que las funciones de Analysis Workspace no se interrumpan, borre el almacenamiento local del dominio experience.adobe.com. |
| Velocidad de procesamiento | &quot;FPS&quot; significa &quot;Marcos por segundo&quot;, que es la cantidad de veces por segundo que el navegador dibuja la página en la pantalla. 24 FPS es comúnmente lo que el ojo humano puede observar; si FPS es menor que eso, observará problemas de procesamiento en Workspace. | FPS se ve afectado por la multitarea en muchos proyectos de Workspace a la vez y por el tamaño del proyecto que se está viendo. Otros programas que se ejecutan en el equipo pueden tener un impacto, como flujo continuo, escáneres de fondo, etc. Además, su hardware afectará este factor. | Abra el Administrador de Tareas (PC) o el Monitor de Actividad (Mac) del equipo para determinar si se puede cerrar algún programa. A continuación, cierre las fichas del explorador que no se hayan utilizado u otros programas. <br><br>Si estas acciones no ayudan, comente los detalles de hardware con su equipo de TI. |

## Factores de proyecto

**[!UICONTROL Los factores del proyecto Ayuda > Rendimiento incluyen:]**

| Factor | Definición | Optimización |
| --- | --- | --- |
| Cantidad de consultas | La cantidad total de consultas (solicitudes) realizadas a Adobe para recuperar datos que se muestran en el proyecto. Las consultas incluyen solicitudes de clasificación para tablas, detección de anomalías, minigráficos, componentes mostrados en el carril izquierdo, etc. Excluye paneles contraídos y visualizaciones. El umbral recomendado es 100. | Simplifique el proyecto siempre que sea posible dividiendo los datos en varios proyectos que cumplan un propósito específico o un grupo de partes interesadas. Utilice las etiquetas para organizar los proyectos en temáticas y utilice la [vinculación directa](/help/analysis-workspace/curate-share/shareable-links.md) para crear una tabla de contenido interna que permita a los interesados encontrar con más facilidad lo que necesitan. |
| Paneles ampliados (de paneles totales) | Cantidad de paneles ampliados del número total de paneles del proyecto. El umbral recomendado es 5. | Después de dar los pasos necesarios para simplificar el proyecto, contraiga los paneles del proyecto que no necesitan visualizarse durante la carga. Cuando se abra el proyecto, solo se procesarán los paneles expandidos. Los paneles contraídos no se procesarán hasta que el usuario los expanda. |
| Visualizaciones ampliadas (de visualizaciones totales) | Número de tablas y visualizaciones expandidas del total del proyecto. Excluye las fuentes de datos ocultas. El umbral recomendado es 15. | Después de dar los pasos necesarios para simplificar el proyecto, contraiga las visualizaciones del proyecto que no necesitan visualizarse durante la carga. Priorice los elementos visuales que son más importantes para el consumidor del informe y desglose los elementos visuales de compatibilidad en un proyecto o panel diferente y más detallado, si es necesario. |
| Cantidad de celdas de forma libre | La cantidad total de celdas de tabla improvisada en el proyecto, calculadas mediante filas * columnas en todas las tablas. Excluye las fuentes de datos ocultas. El umbral recomendado es 4000. | Reduzca la cantidad de columnas de la tabla a sólo los puntos de datos más relevantes. Reduzca la cantidad de filas de la tabla ajustando el número de filas mostradas, aplicando un filtro de tabla o aplicando un segmento. |
| Componentes disponibles | Cantidad total de componentes recuperados en el carril izquierdo del proyecto, en todos los grupos de informes del proyecto. El umbral recomendado es 2000. | Hable con el administrador del producto sobre la creación de un grupo de informes virtuales seleccionado que tenga un conjunto de componentes más personalizado. |
| Componentes utilizados | Cantidad total de componentes utilizados en el proyecto. El umbral recomendado es 100. | La cantidad de componentes usados no influye directamente en el rendimiento. Sin embargo, la complejidad de esos componentes contribuirá a la ejecución del proyecto. Consulte las optimizaciones recomendadas en la sección &quot;Factores adicionales&quot; a continuación. |
| El intervalo de fecha más largo | Este factor muestra el intervalo de fechas más largo utilizado en el proyecto. El umbral recomendado es 1 año. | Siempre que sea posible, no incorpore más datos de los que necesita. Reduzca el calendario del panel a las fechas relevantes para el análisis o use componentes del intervalo de fechas (componentes púrpura) en las tablas improvisadas. Los intervalos de fechas utilizados en una tabla anulan el intervalo de fechas del panel. Por ejemplo, puede agregar el mes pasado, la semana pasada y ayer a las columnas de la tabla para solicitar esos intervalos de datos específicos. Para obtener más información acerca del trabajo con intervalos de fechas en Analysis Workspace, consulte [este vídeo](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/date-ranges-and-calendar-in-analysis-workspace.html). <br><br>Además, minimice el número de comparaciones año tras año utilizadas en el proyecto. Cuando se calcula una comparación año tras año, se analizan los 13 meses completos de datos entre los meses de interés. Esto tiene el mismo impacto que cambiar el intervalo de fechas del panel a los últimos 13 meses. |

## Factores adicionales

Otros factores que no se incluyen en Ayuda > Rendimiento son:

| Factor | Definición | Afectado por | Optimización |
| --- | --- | --- | --- |
| Complejidad de filtro | Los filtros complejos pueden tener un impacto significativo en el rendimiento del proyecto. | Los factores que agregan complejidad a un filtro (en orden descendente de impacto) incluyen: <ul><li>Los operadores de “contiene”, “contiene cualquiera de”, “coincide”, “comienza con” o “termina con” </li><li>Filtros secuenciales, especialmente cuando se utilizan restricciones de dimensión (En/Después) </li><li>Número de elementos de dimensiones únicas dentro de las dimensiones utilizadas en el segmento (por ejemplo, Página = “A” cuando la Página tiene 10 elementos únicos será más rápido que Página = “A” cuando la Página tiene 100000 elementos únicos) </li><li>Número de dimensiones diferentes utilizadas (por ejemplo, Página = “Inicio” y Página = “Resultados de búsqueda”&#39; será más rápido que eVar 1 = “rojo” y eVar 2 = “azul”&#39;)</li><li>Muchos operadores OR (en lugar de AND)</li><li>Contenedores anidados que varían en ámbito (por ejemplo, Visita (hit) en el interior de la “Visita” dentro de “Visitante”)</li></ul> | Aunque algunos de los factores de complejidad no se pueden evitar, busque oportunidades para reducir la complejidad de los filtros. En general, cuanto más específico pueda ser con sus criterios de filtro, mejor. Por ejemplo:<ul><li>Con los contenedores, el uso de un solo contenedor en la parte superior del segmento será más rápido que una serie de contenedores anidados</li><li>Con los operadores, “es igual a” será más rápido que “contiene” y “es igual a cualquiera de” será más rápido que “contiene cualquiera de”</li><li>Con muchos criterios, los operadores AND serán más rápidos que varios operadores OR.</li><li>Busque oportunidades para reducir muchas condiciones “OR” en una sola condición “es igual a cualquiera de” </li></ul> |
| Complejidad de la visualización (filtros, métricas) | El tipo de visualización (por ejemplo, visitas en el orden previsto vs. tabla improvisada) que se agrega a un proyecto por sí solo no influye demasiado en el rendimiento del proyecto. Lo que aumenta el tiempo de procesamiento es la complejidad de la visualización. | Entre los factores que aumentan la complejidad de una visualización están:<ul><li>Intervalo de datos solicitado</li><li>Número de filtros aplicados; por ejemplo, filtros utilizados como filas de una tabla improvisada</li><li>Uso de filtros complejos</li><li>[Filas o columnas de elementos manuales en tablas improvisada](/help/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md)</li><li>Los filtros aplicados a las filas de una tabla improvisada.</li><li>Número de métricas incluidas, especialmente métricas calculadas que utilizan filtros</li></ul> | Si nota que los proyectos no se cargan lo más rápido posible, intente reemplazar algunos filtros con eVars y filtros, siempre que sea posible.<br><br>Si usa constantemente segmentos y métricas calculadas para puntos de datos que son importantes para su negocio, plantéese mejorar su implementación para capturar estos puntos de datos de forma más directa. El uso de un administrador de etiquetas como Adobe Experience Platform Launch y las reglas de procesamiento de Adobe pueden hacer que los cambios de implementación sean rápidos y sencillos. |

## Mensajes de error frecuentes

Puede encontrar errores al interactuar con Analysis Workspace que también afectarán el rendimiento. A continuación se enumeran los tipos de error más comunes, por qué se producen y las optimizaciones que se pueden realizar.

| Mensaje de error | ¿Por qué ocurre esto? | Optimización |
| --- | --- | --- |
| [!UICONTROL Está grupo de informes está experimentando una creación de informes inusualmente alta. Inténtelo de nuevo más tarde.] | Su organización está intentando ejecutar demasiadas solicitudes simultáneas en un grupo de informes específico. Los factores que contribuyen a este error son las solicitudes de API, los proyectos programados, los informes programados, las alertas programadas y los usuarios simultáneos que realizan solicitudes de informes. | Distribuya las solicitudes y programaciones del grupo de informes de forma más uniforme durante todo el día. |
| [!UICONTROL Se ha producido un error del sistema. Registre una solicitud del Servicio de atención al cliente en Ayuda > Enviar ticket de asistencia técnica e incluya su código de error.] | Adobe está experimentando un problema que debe resolverse. | Envíe el código de error al Servicio de atención al cliente. |
| [!UICONTROL La solicitud es demasiado compleja.] | La solicitud de informe es demasiado grande y no se puede ejecutar. Los contribuyentes a este error son los tiempos de espera debido al tamaño de la solicitud, demasiados elementos coincidentes en un segmento o filtro de búsqueda, demasiadas métricas incluidas, combinaciones incompatibles de dimensiones y métricas, etc. | Simplifique la solicitud eliminando algunas columnas o filas de la tabla, o considere la posibilidad de dividir la tabla en solicitudes independientes. |
| [!UICONTROL Uno de los segmentos o la búsqueda en esta visualización contiene una búsqueda de texto que arrojó demasiados resultados.] | Los criterios del segmento o el filtro del informe son demasiado amplios. | Reduzca los criterios del texto de búsqueda y vuelva solicitar. |
| [!UICONTROL Actualmente, esta dimensión no admite modelos de atribución no predeterminados.] | No se admite la atribución no predeterminada para la dimensión que está utilizando. | Reemplace la dimensión de la tabla por una que sea compatible con [Attribution IQ](/help/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Su solicitud falló como resultado de demasiadas columnas o filas preconfiguradas.] | La tabla tiene demasiadas celdas improvisadas (columnas de fila *). | Elimine columnas o filas de la tabla, o bien considere la posibilidad de dividir la tabla en solicitudes independientes. |
