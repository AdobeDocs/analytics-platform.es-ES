---
description: 'null'
title: Optimizar rendimiento de Analysis Workspace
uuid: de51d03d-d555-4f0e-b19c-4a8f140770fc
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 98%

---


# Optimizar rendimiento de Analysis Workspace

>[!NOTE] Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

Determinados factores pueden influir en el rendimiento de un proyecto dentro de Analysis Workspace. Es importante conocer cuáles son antes de comenzar a crear un proyecto, de forma que este se pueda planificar y generar de forma óptima. Abajo se muestra una lista de factores que afectan al rendimiento y prácticas recomendadas para optimizar los proyectos. El rendimiento de Analysis Workspace es una de las principales prioridades de Adobe y lo mejoramos día a día.

## Complejidad de la lógica de segmentos

Los segmentos intrincados pueden tener un impacto significativo en el desempeño del proyecto. Los factores que añaden complejidad a un segmento (en orden descendente de impacto) son:

* Los operadores de “contiene”, “contiene cualquiera de”, “coincide”, “comienza con” o “termina con”
* Segmentación secuencial, sobre todo cuando se utilizan restricciones de dimensión (Dentro/Después)
* Número de elementos de dimensiones únicas dentro de las dimensiones utilizadas en el segmento (por ejemplo, Página = “A” cuando la Página tiene 10 elementos únicos será más rápido que Página = “A” cuando la Página tiene 100000 elementos únicos)
* Número de dimensiones diferentes utilizadas (por ejemplo, Página = “Inicio” y Página = “Resultados de búsqueda”&#39; será más rápido que eVar 1 = “rojo” y eVar 2 = “azul”&#39;)
* Muchos operadores O (en lugar de Y)
* Contenedores anidados que varían en ámbito (por ejemplo, Visita (hit) en el interior de la “Visita” dentro de “Visitante”)

**Prácticas recomendadas para la complejidad lógica**

Aunque algunos de los factores de complejidad no se pueden prevenir, piense en opciones para reducir la complejidad de sus segmentos. En general, cuanto más específico pueda ser con sus criterios de segmento, mejor. Por ejemplo:

* Con los contenedores, el uso de un solo contenedor en la parte superior del segmento será más rápido que una serie de contenedores anidados.
* Con los operadores, “es igual a” será más rápido que “contiene” y “es igual a cualquiera de” será más rápido que “contiene cualquiera de”.
* Con muchos criterios, los operadores Y serán más rápidos que varios operadores O. Además, busque oportunidades para reducir muchas condiciones “O” en una sola condición “es igual a cualquiera de”.

Además, [las clasificaciones](https://docs.adobe.com/content/help/es-ES/analytics/components/classifications/c-classifications.html) pueden ayudar a consolidar muchos valores en grupos concisos a partir de los cuales crear segmentos. La segmentación en grupos de clasificación proporciona beneficios de rendimiento sobre los segmentos con muchas condiciones “O”, o criterios “contiene”.

## Intervalo de datos solicitado

El intervalo de datos que se solicita en un proyecto influye en el rendimiento de Analysis Workspace.

**Prácticas recomendadas para el rango de datos**

Siempre que sea posible, no incorpore más datos de los que necesita.

Recuerde que los intervalos de fechas (componentes morados) anulan el intervalo de fechas del panel. Como resultado, si está utilizando distintos intervalos de fechas como columnas (p. ej., columnas último mes, última semana o ayer), el intervalo de fechas del panel no tiene por qué abarcar todos los intervalos de fechas de las columnas. Puede establecerse simplemente en “ayer”, ya que los intervalos de fechas empleados en la tabla improvisada anularán los del panel. Para obtener más información acerca del trabajo con intervalos de fechas en Analysis Workspace, consulte [este vídeo](https://www.youtube.com/watch?v=ybmv6EBmhn0).

Utilice [opciones de comparación de fechas](/help/components/date-ranges/time-comparison.md) para incorporar los datos de los periodos de tiempo específicos que quiere comparar. Por ejemplo, si necesita mostrar los datos del último mes comparados con los del mismo mes del año pasado, en vez de establecer el panel en los últimos 13 meses de datos, utilice simplemente la opción de comparación de periodos de tiempo para mostrar el rendimiento año tras año.

## Número de visualizaciones

El número de visualizaciones de gráficos que contiene un proyecto afectará a la respuesta general de Analysis Workspace.

**Práctica recomendada para el número de visualizaciones**

Reduzca el número de visualizaciones en el proyecto. Analysis Workspace realiza una gran cantidad de procesamiento en segundo plano por cada imagen que agrega, así que dé prioridad a las imágenes más importantes para el consumidor del informe y, si es necesario, incluya las imágenes de apoyo en un proyecto separado, más detallado.

## Complejidad de las visualizaciones (segmentos, métricas, filtros)

El tipo de visualización agregado (p. ej., abandonos o tabla improvisada) no tiene demasiada influencia por sí mismo en el rendimiento de un proyecto. Lo que afecta al tiempo de procesamiento es la complejidad de la visualización. Entre los factores que aumentan la complejidad de una visualización están:

* El intervalo de datos solicitado, como se ha mencionado antes.
* El número de segmentos aplicados; por ejemplo, los segmentos utilizados como columnas de una tabla improvisada.
* Uso de segmentos intrincados
* Filas o columnas de elementos manuales en tablas improvisada
* Los filtros aplicados a las filas de una tabla improvisada.
* El número de métricas incluidas, en especial las métricas calculadas que utilizan segmentos.

**Práctica recomendada para la complejidad de la visualización**

Si ha notado que sus proyectos no se cargan tan rápido como le gustaría, pruebe a sustituir algunos segmentos por eVars y filtros, si es posible.

Si se encuentra constantemente empleando segmentos y métricas calculadas para puntos de datos que son importantes para su negocio, plantéese mejorar su implementación para capturar estos puntos de datos de forma más directa. El uso de un administrador de etiquetas como Adobe Experience Platform Launch y las reglas de procesamiento de Adobe pueden hacer que los cambios de implementación sean rápidos y sencillos. Para entender mejor cómo simplificar los segmentos intrincados, vea “Complejidad de la lógica de segmento” más arriba.

## Número de paneles

Un panel puede contener muchas visualizaciones y, como resultado, el número de paneles también puede influir en la respuesta general de Analysis Workspace.

**Práctica recomendada para el número de paneles**

No intente agregar todo en un proyecto: cree proyectos separados que sirvan a un propósito o a un grupo de personas interesadas específico. Utilice etiquetas para organizar los proyectos por temas clave y comparta proyectos relacionados con grupos de personas interesadas.

Si desea una mayor organización de los proyectos, recuerde que existe la opción de realizar [vínculos directos](https://www.youtube.com/watch?v=6IOEewflG2U) a su proyecto. Cree un índice interno de proyectos, de modo que las personas interesadas encuentren más fácilmente lo que necesitan.

Si necesita muchos paneles en un Workspace, contraiga paneles antes de guardar y compartir. Cuando se carga un proyecto, Analysis Workspace solo carga el contenido de los paneles expandidos. Los paneles contraídos no se cargarán hasta que el usuario los expanda. Este enfoque ayuda de dos maneras:

* Los paneles contraídos reducen el tiempo de carga total de un proyecto.
* Los paneles contraídos son un gran modo de organizar sus proyectos de un modo lógico para el consumidor del informe.

## Tamaño del conjunto de informes

El tamaño del conjunto de informes puede parecer un factor importante, pero en realidad tiene una importancia pequeña en el rendimiento del proyecto debido al modo en que Adobe gestiona el procesamiento de datos.

## Número de usuarios que obtienen acceso al mismo tiempo a Analysis Workspace

El número de usuarios que accede a Analysis Workspace o a proyectos específicos al mismo tiempo no tiene un efecto sustancial en el rendimiento de Analysis Workspace, si los usuarios acceden a grupos de informes diferentes. Si los usuarios simultáneos acceden al mismo grupo de informes, el rendimiento se verá afectado.

## Mensajes de error comunes en Analysis Workspace

Puede encontrar errores al interactuar con Analysis Workspace. Los errores pueden producirse por varios motivos. Los que se enumeran a continuación son los más comunes.

| Mensaje de error | ¿Por qué ocurre esto? |
|---|---|
| `The report suite is experiencing unusually heavy reporting. Please try again later.` | Su organización está intentando ejecutar demasiadas solicitudes simultáneas en un grupo de informes específico. Los factores que contribuyen a este error son las solicitudes de API, los proyectos programados, los informes programados, las alertas programadas y los usuarios simultáneos que realizan solicitudes de informes. Le recomendamos que las solicitudes y programaciones del grupo de informes se extiendan de manera más uniforme durante todo el día. |
| `A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.` | Adobe está experimentando un problema que debe resolverse. Le recomendamos que envíe el código de error mediante una solicitud del Servicio de atención al cliente. |
| `The request is too complex.` | La solicitud de informe es demasiado grande y no se puede ejecutar. Los contribuyentes a este error son los tiempos de espera debido al tamaño de la solicitud, demasiados elementos coincidentes en un segmento o filtro de búsqueda, demasiadas métricas incluidas, combinaciones incompatibles de dimensiones y métricas, etc. Le recomendamos que simplifique la solicitud. |
| `One of the segments or the search in this visualization contains a text search that returned too many results.` | Se recomienda reducir los criterios de texto de búsqueda y volver a intentar la solicitud. |
| `This dimension does not currently support non-default attribution models.` | Se recomienda reemplazar la dimensión de la tabla por una que sea compatible con [Attribution IQ](../attribution/overview.md). |
| `Your request failed as a result of too many columns or pre-configured rows.` | Se recomienda eliminar algunas de las columnas o filas, o bien dividirlas en visualizaciones independientes. |
