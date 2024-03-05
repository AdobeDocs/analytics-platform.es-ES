---
title: Protecciones del Customer Journey Analytics
description: Obtenga información acerca de las protecciones para Customer Journey Analytics
solution: Customer Journey Analytics
feature: Administration
role: Admin
exl-id: f093ac54-7d31-449b-a441-a65856a1d535
source-git-commit: b945ae10d9107a760e32f5d111e5c14724898646
workflow-type: tm+mt
source-wordcount: '1519'
ht-degree: 8%

---

# Protecciones del Customer Journey Analytics

Este documento proporciona límites para varios componentes de Customer Journey Analytics. Para obtener protecciones, parámetros de ámbito y derechos, consulte la [Descripción del producto para Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html?lang=es) o el [Descripción del producto para el complemento de Adobe Analytics: Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html?lang=es).

## Tipos de límite

Existen dos tipos de límites predeterminados en este documento:

| Tipo de protección | Descripción |
|----------|---------|
| **Protecciones de rendimiento (límite flexible)** | Las protecciones de rendimiento son límites de uso relacionados con el ámbito de los casos de uso. Al superar las protecciones de rendimiento, puede experimentar una degradación y latencia del rendimiento. El Adobe no es responsable de esta degradación del rendimiento. Los clientes que superen de forma consistente una protección de rendimiento pueden optar por licenciar la capacidad adicional para evitar la degradación del rendimiento. |
| **Protecciones impuestas por el sistema (límite estricto)** | La interfaz de usuario o la API de Customer Journey Analytics aplican las protecciones impuestas por el sistema. Estos son límites que no se pueden superar, ya que la interfaz de usuario y la API le impiden hacerlo o devuelven un error. |

{style="table-layout:auto"}

Algunas de las funciones y su valor asociado para el límite dependen del paquete de Customer Journey Analytics al que esté autorizado.

>[!NOTE]
>
>Los valores descritos en este documento están sujetos a cambios en función de las continuas mejoras realizadas en el producto. Vuelva regularmente para ver las actualizaciones. Si está interesado en conocer los límites personalizados, póngase en contacto con su representante del servicio de atención al cliente.

## Consultas SQL ad hoc

| Nombre | Valor | Tipo de límite | Descripción |
|---|--:|---|---|
| Tiempo de espera para intentarlo de nuevo | 90 | Protección impuesta por el sistema | Número máximo de segundos antes de que el motor de informes responda que la solicitud tarda demasiado en devolver los resultados (posiblemente debido a otras solicitudes simultáneas); es posible solicitar de nuevo. |
| Tiempo de espera para no volver a intentarlo | 600 | Protección impuesta por el sistema | Número máximo de segundos antes de que se agote el tiempo de espera de las consultas Ad Hoc SQL. De lo contrario, se indica que el número máximo de segundos antes de que los motores de informes notifiquen que la solicitud ha tardado demasiado en devolver los resultados y no se debe volver a intentar. Es muy probable que la solicitud nunca devuelva resultados debido a problemas en el proceso en segundo plano. |
| Métricas | 150 | Protección impuesta por el sistema | Número máximo de métricas en una solicitud. |
| Filas de salida de consulta interactiva | 50 000 | Protección impuesta por el sistema | Número predeterminado de filas devueltas a menos que se especifique lo contrario. |

{style="table-layout:auto"}

## Proyectos Analysis Workspace

| Nombre | Valor | Tipo de límite | Descripción |
|---|--:|---|---|
| Filas visibles por tabla | 400 | Protección impuesta por el sistema | Número máximo de filas visibles en cualquier tabla de forma libre de un proyecto de Analysis Workspace. |
| Filas exportables por tabla | 50 000 | Protección impuesta por el sistema | Número máximo de filas que se pueden exportar por dimensión única. |
| Paneles por proyecto | 15 | Protección impuesta por el sistema | Número máximo de [paneles](../analysis-workspace/home.md#panels) por proyecto. |
| Visualizaciones por panel | 25 | Protección impuesta por el sistema | Número máximo de [visualizaciones](../analysis-workspace/home.md#visualizations) por panel. |
| Campos derivados por tabla de forma libre | 5 | Protección impuesta por el sistema | Número máximo de campos derivados diferentes en una sola tabla de forma libre. |

{style="table-layout:auto"}

<!--
## Attribution AI

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Attribution AI models | 35 | Maximum number of Attribution AI Model per year to analyze the impact of up to an average of 60 independent touchpoints on a specified conversion event.  | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Region based iterations | 10 | Maximum number of region-based iterations of each Attribution AI model. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Export Insights batches | 12 | Maximum number of export batches times the number of authorized Attribution AI Insights per year. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 

{style="table-layout:auto"}
-->

## Audiencias

| Nombre | Valor | Tipo de límite | Descripción |
|---|--:|---|---|
| Filtros de audiencia | 20 | Protección impuesta por el sistema | Número máximo de [filtros](../components/filters/filters-overview.md) por audiencia. |
| Número de identidades de la audiencia | 20 millones | Protección impuesta por el sistema | Número máximo de identidades por audiencia. |
| Frecuencia de actualización de audiencia | 4 | Protección impuesta por el sistema | Frecuencia máxima en horas y [audiencia](../components/audiences/audiences-overview.md) se puede actualizar. |
| Ventana retrospectiva de actualización de audiencia | 90 | Protección impuesta por el sistema | Número máximo de días para actualizar la ventana retrospectiva. |
| Actualizando fecha de caducidad de audiencia | 13 | Protección impuesta por el sistema | La audiencia deja de actualizarse durante un número máximo de meses a partir de la fecha de creación. Los clientes pueden prolongar esta duración otros 13 meses. |
| Número de audiencias actualizadas | 75, 100 | Protección impuesta por el sistema | Número máximo de audiencias de actualización, el valor varía según el paquete (consulte la Descripción del producto). |

{style="table-layout:auto"}

Consulte también Experience Platform [Protecciones de Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/Guardrails.html?lang=en).


## Caducidad automatizada del conjunto de datos

| Nombre | Valor | Tipo de límite | Descripción |
|---|--:|---|:---:|
| Órdenes de trabajo | 20 | Protección impuesta por el sistema | Número máximo de órdenes de trabajo de caducidad automatizada de conjuntos de datos por mes. |

{style="table-layout:auto"}



## Conexiones, vistas de datos, proyectos

| Nombre | Valor | Tipo de límite | Descripción |
|---|--:|---|---|
| Proyectos | 2.000 | Protección impuesta por el sistema | Número máximo de proyectos para una organización. |
| Vistas de datos | 2.000 | Protección impuesta por el sistema | Número máximo de [vistas de datos](../data-views/data-views.md) para una organización. |
| Vistas de datos | 50 | Protección impuesta por el sistema | Número máximo de vistas de datos para una conexión |
| Conjuntos de datos | 100 | Protección impuesta por el sistema | Número máximo de [conjuntos de datos](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=en) por conexión. |
| Conexiones | 1000 | Protección impuesta por el sistema | Número máximo de [conexiones](../connections/overview.md) para una organización. |
| Título de conexión | 500 | Protección impuesta por el sistema | Número máximo de caracteres para un título de conexión. |
| Métricas | 5.000 | Protección impuesta por el sistema | Número máximo de métricas en una vista de datos. |
| Dimensiones | 5.000 | Protección impuesta por el sistema | Número máximo de dimensiones en una vista de datos. |
| Título de anotación | 100 | Protección impuesta por el sistema | Número máximo de caracteres para un título de anotación. |
| Descripción de anotación | 250 | Protección impuesta por el sistema | Número máximo de caracteres para una descripción de anotación. |
| Campos de esquema | 10 | Protección impuesta por el sistema | Número máximo de campos de esquema (sin incluir los campos estándar) al definir reglas para una [campo derivado](../data-views/derived-fields/derived-fields.md). |
| Campos de búsqueda/perfil | 3 | Protección impuesta por el sistema | Número máximo de campos de esquema de búsqueda o perfil dentro del número máximo de campos de esquema (sin incluir los campos estándar) al definir reglas para un campo derivado. |
| Campos derivados | 100 | Protección impuesta por el sistema | Número máximo de campos derivados por conexión. |

{style="table-layout:auto"}


## Límites de transferencia de datos

| Nombre | Valor | Tipo de límite | Descripción |
|---|--:|---|---|
| Campos | 10.000 | Protección impuesta por el sistema | Número máximo de propiedades o campos por fila en un conjunto de datos. |
| Cadenas únicas | 10 millones | Protección impuesta por el sistema | Número máximo de claves únicas por conjunto de datos de búsqueda. |
| Filas | 1 millón | Protección impuesta por el sistema | Número máximo de filas por ID único de persona dentro de una conexión. |
| Tamaño de fila | 2 | Protección de rendimiento / Protección impuesta por el sistema | Tamaño medio en kilobytes por fila de datos introducidos en el Customer Journey Analytics (límite flexible). Las protecciones determinan un límite estático para el tamaño de fila para la ingesta de datos en Experience Platform. |

{style="table-layout:auto"}

Consulte también Experience Platform [Protecciones para la ingesta de datos](https://experienceleague.adobe.com/docs/experience-platform/ingestion/Guardrails.html?lang=en).


## Zona de aterrizaje de datos

| Nombre | Valor | Tipo de límite | Descripción |
|---|--:|---|---|
| Zona de aterrizaje de datos por zona protegida | 1 | Protección impuesta por el sistema | Número máximo de zonas de aterrizaje de datos por zona protegida. |
| Almacenamiento de datos | 7 | Protección impuesta por el sistema | La cantidad máxima de días que los datos se almacenan en la zona de aterrizaje de datos antes de eliminarse. |

{style="table-layout:auto"}


## Vinculación basada en el campo

| Nombre | Valor | Tipo de límite | Descripción |
|---|--:|---|---|
| Conjuntos de datos vinculados | 10 | Protección impuesta por el sistema | Número máximo de conjuntos de datos enlazados por cliente; el valor varía según el paquete de Customer Journey Analytics aplicable (consulte la descripción del producto aplicable). |
| Datos de relleno | 60 | Protección impuesta por el sistema | Número máximo de días de datos de relleno. |

{style="table-layout:auto"}


## Filtros y métricas calculadas

| Nombre | Valor | Tipo de límite | Descripción |
|---|--:|---|---|
| Contenedores por filtro | 50 | Protección impuesta por el sistema | Número máximo de contenedores por filtro. |
| Métricas por métrica calculada | 25 | Protección impuesta por el sistema | Número máximo de métricas por métrica calculada. |
| Métricas y Dimension por filtro | 25 | Protección impuesta por el sistema | Número máximo de métricas y dimensiones únicas por filtro. |
| Contenedores anidados por filtro | 10 | Protección impuesta por el sistema | Número máximo de contenedores anidados por filtro. |
| Reglas por filtro | 100 | Protección impuesta por el sistema | Número máximo de reglas por filtro. |
| Comparaciones de cadenas por Dimension y por filtro | 100 | Protección impuesta por el sistema | Número máximo de comparaciones de cadenas por dimensión por filtro. |
| Métricas calculadas  | 6.000 | Protección impuesta por el sistema | Número máximo de métricas calculadas para una organización. |
| Filtros | 50 000 | Protección impuesta por el sistema | Número máximo de filtros que puede definir para una organización. |
| Llamadas de API | 120 | Protección impuesta por el sistema | Solicitudes de API por minuto (12 solicitudes cada 6 segundos). |

{style="table-layout:auto"}


## aplicación móvil

| Nombre | Valor | Tipo de límite | Descripción |
|---|--:|---|---|
| Mosaicos | 16 | Protección impuesta por el sistema | Número máximo de mosaicos por cuadro de resultados. |
| Filtros | 10 | Protección impuesta por el sistema | Número máximo de filtros por cuadro de resultados. |
| Dimensiones | 10 | Protección impuesta por el sistema | Número máximo de dimensiones por cuadro de resultados. |

{style="table-layout:auto"}

## Report Builder

| Nombre | Valor | Tipo de límite | Descripción |
|---|--:|---|---|
| Tamaño del archivo del libro | 5 | Protección impuesta por el sistema | Tamaño máximo de archivo en MB de un libro programado. |
| Bloques de datos | 1000 | Protección impuesta por el sistema | Número máximo de [bloques de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=en) por libro. |
| Métricas | 20 | Protección impuesta por el sistema | Número máximo de métricas por bloque de datos. |
| Intervalo de intervalo de fecha | 13 | Protección impuesta por el sistema | Número máximo de meses que puede abarcar un intervalo de fecha por bloque de datos. |
| Filas | 50 000 | Protección impuesta por el sistema | Número máximo de filas por bloque de datos. |

{style="table-layout:auto"}


## Exportación de tablas completas

| Nombre | Valor | Tipo de límite | Descripción |
|---|--:|---|---|
| Filas por informe | 3 millones - 300 millones | Protección impuesta por el sistema | Número máximo de filas de informes por informe; el valor varía según el paquete de Customer Journey Analytics aplicable (consulte la descripción del producto aplicable). |
| Desgloses por tabla | 5 | Protección impuesta por el sistema | Número máximo de desgloses por tabla. |
| Métricas por tabla | 5 | Protección impuesta por el sistema | Número máximo de métricas por tabla. |
| Frecuencia de programación | 1 | Protección impuesta por el sistema | Las exportaciones se pueden programar una vez (1) al día o en un horario más largo (por ejemplo: una vez cada 2 días o semanalmente). |

{style="table-layout:auto"}

## Latencias

>[!NOTE]
>
>Los tiempos de procesamiento a continuación son protecciones, no acuerdos contractuales de nivel de servicio (SLA). La latencia varía según la configuración del cliente, los volúmenes de datos y las aplicaciones de los consumidores. Los tiempos de procesamiento reales suelen ser más rápidos. Consulte el contrato de Customer Journey Analytics para conocer las condiciones contractuales y los SLA específicos. Consulte el Experience Platform [Protecciones para la ingesta de datos](https://experienceleague.adobe.com/docs/experience-platform/ingestion/Guardrails.html?lang=en) para obtener más información.

| Flujo de datos | Latencia esperada |
|---|---|
| Conector de origen de Adobe Analytics a Adobe Analytics (A4T habilitado) | &lt; 30 minutos |
| Conector de origen de Adobe Analytics al perfil del cliente en tiempo real (A4T no habilitado) | &lt; 2 minutos |
| Conector de origen de Adobe Analytics al perfil del cliente en tiempo real (A4T activado) | &lt; 30 minutos |
| Ingesta de datos en el lago de datos desde la red perimetral o la ingesta de streaming | &lt; 60 minutos |
| Ingesta de datos en el lago de datos desde el conector de origen de Adobe Analytics | &lt; 2,25 horas |
| Ingesta de datos en el Customer Journey Analytics desde Data Lake | &lt; 90 minutos |
| Vinculación (función opcional; consulte [Información general de vinculación](../stitching/overview.md) para obtener más información) | &lt; 3,25 horas |
| Relleno del conector de origen de Adobe Analytics de menos de 10 000 millones de eventos (un máximo de 13 meses de datos históricos) | &lt; 4 semanas |
| Publicación de audiencias en el Perfil del cliente en tiempo real, lo que incluye la creación automática del segmento de flujo continuo y permite que el segmento esté listo para recibir los datos. | ≈ 60 minutos |
| Actualizar la frecuencia de las audiencias | Actualización única: latencia inferior a 5 minutos.<br/>Actualice cada 4 horas, diariamente, semanalmente o mensualmente (la latencia va acompañada de la frecuencia de actualización). |

{style="table-layout:auto"}
