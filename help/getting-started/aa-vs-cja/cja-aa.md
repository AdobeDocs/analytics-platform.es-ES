---
title: Compatibilidad con funciones de Customer Journey Analytics
description: Customer Journey Analytics en comparación con las funciones de Adobe Analytics establecidas.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: f091dda08391bad3974493e93dce942b8a2fc4d3
workflow-type: ht
source-wordcount: '2287'
ht-degree: 100%

---

# Compatibilidad con funciones de Customer Journey Analytics

Las siguientes tablas indican qué funciones de Adobe Analytics son compatibles, parcialmente o nada compatibles con Customer Journey Analytics, y qué funciones de Customer Journey Analytics no son compatibles o no están disponibles en Adobe Analytics. Estas listas cambiarán con el tiempo a medida que se añadan funciones a Customer Journey Analytics.

## Funciones y componentes totalmente compatibles {#full-support}

| Función Adobe Analytics | Notas sobre asistencia |
| --- | --- |
| Detección de anomalías | Compatibilidad total |
| Attribution IQ | Compatibilidad total |
| Detección de bots | [Compatibilidad total](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=es) |
| Métricas calculadas  | Compatibilidad total. Las métricas calculadas existentes en la versión tradicional de Analysis Workspace no se transfieren a Customer Journey Analytics. |
| Eventos de calendario | Compatibilidad total. Los eventos de calendario se han implementado como [Anotaciones](/help/components/annotations/overview.md) en Workspace. |
| Descarga de CSV | Compatibilidad total |
| Calendarios personalizados | Compatibilidad total |
| Comparaciones de fechas | Compatibilidad total |
| Intervalos de fechas | Se admite toda la funcionalidad de intervalo de fechas. |
| Dimensiones | Compatibilidad total. Customer Journey Analytics utiliza XDM y admite dimensiones ilimitadas. Customer Journey Analytics no está vinculado a las eVars o props personalizadas de Adobe Analytics tradicional. |
| Eliminación de RGPD | Compatibilidad total; tenga en cuenta que RGPD ahora se gestiona en coordinación con [!UICONTROL Adobe Experience Platform]. Customer Journey Analytics hereda los cambios de datos que [!UICONTROL Experience Platform] genera en los conjuntos de datos subyacentes. |
| Creación de informes de alza y confianza | Compatibilidad total a través del [panel Experimentación](/help/analysis-workspace/c-panels/experimentation.md) |
| Variables de lista/Propiedades de lista | Compatibilidad total. Customer Journey Analytics aprovecha XDM y admite matrices de cadenas ilimitadas que pueden utilizarse de manera similar a listVars. |
| eVars de comercialización | Compatibilidad total a través de [dimensiones de enlace y métricas de enlace](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=es#binding-dimension) |
| Métricas | Compatibilidad total; Customer Journey Analytic emplea el Modelo de datos de experiencia (XDM), admite métricas ilimitadas y no está vinculado a los eventos de éxito personalizados de Adobe Analytics. Tenga en cuenta que algunas métricas estándar han cambiado de nombre desde la versión tradicional de Adobe Analytics: Visitantes = Personas, Visitas = Sesiones, Visitas = Eventos. |
| Migración de proyectos, filtros y métricas calculadas de Adobe Analytics a Customer Journey Analytics | Compatibilidad total. |
| Paneles y cuadros de resultados para móviles | Compatibilidad total |
| Paneles | Compatibilidad total con los siguientes paneles: Panel en blanco, Atribución, Forma libre, Información rápida y Elemento siguiente o anterior. |
| Exportación de PDF | Compatibilidad total |
| Revisión del proyecto | Compatibilidad total |
| Vinculación de proyectos | Compatibilidad total |
| Procesamiento de tiempo de los informes | Compatibilidad total; Customer Journey Analytics depende exclusivamente del Procesamiento de tiempo de los informes. |
| Acceso a la API de informes | Compatibilidad total. Disponible a través de la [API de Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/). |
| Informes y proyectos programados | Compatibilidad total |
| Segmentos | Compatibilidad total. Ahora se denominan “Filtros”: tenga en cuenta que los segmentos existentes en la versión tradicional de Analysis Workspace no se transfieren a Customer Journey Analytics. |
| Grupos de informes virtuales | Compatibilidad total. Ahora se denomina [Vistas de datos](/help/data-views/create-dataview.md). |
| Revisión de componentes de grupo de informes virtuales | Compatibilidad total. Ahora forma parte de Vistas de datos. |
| Dimensiones del Dispositivo, Explorador, Referente, Tecnología | Se admite para ambos conjuntos basados en el [conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=es) y para conjuntos de datos generados por WebSDK. Consulta [Documentación sobre las variables de Analytics que se admiten mediante ADC](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=es). Si utilizas la recopilación de datos del SDK web de Experience Platform, actualmente no se admiten dispositivos ni dimensiones basadas en la búsqueda de dispositivos. Está planificada la compatibilidad futura. Para añadir búsquedas de dispositivos y exploradores a la secuencia de datos del SDK web, consulte [esta documentación](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=es) |
| El complemento de Recopilación de medios de streaming | Los datos de medios de streaming están disponibles mediante el conector de datos de Analytics como parte del panel Visualizadores simultáneos de medios y el panel Tiempo invertido en la reproducción de medios de Workspace. |

{style="table-layout:auto"}

## Compatible de una nueva forma {#new-support}

| Función | Notas |
| --- | --- |
| Analytics for Target (A4T) | La [integración entre Adobe Customer Journey Analytics y Target](https://experienceleague.adobe.com/es/docs/target/using/integrate/cja/target-reporting-in-cja) proporciona potentes herramientas de análisis y ahorro de tiempo para su programa de optimización. |
| Publicación del público | Compatible si tiene licencia con la plataforma de datos del cliente o los productos de Journey Optimizer de Adobe. [Publicación de audiencias](/help/components/audiences/audiences-overview.md) envía audiencias al perfil del cliente en tiempo real en Experience Platform. |
| Clasificaciones | Ahora se denomina Conjuntos de datos de búsqueda. Las clasificaciones utilizadas en Analytics se pueden importar a Experience Platform y a Customer Journey Analytics mediante el conector de origen de clasificaciones de Analytics. Los conjuntos de datos de búsqueda también se pueden cargar directamente en Experience Platform y estar disponibles en Customer Journey Analytics. |
| Generador de reglas de clasificación | Admitido mediante [subcadenas](/help/data-views/component-settings/substring.md) en Customer Journey Analytics. Utiliza manipulaciones de cadenas en el tiempo del informe en lugar de conjuntos de datos de búsqueda. |
| Longitud de sesión personalizada | La longitud de sesión se puede configurar mediante las opciones de [Configuración de sesión](../../data-views/create-dataview.md#session-settings) en una Vista de datos. Consulte [Configuración de sesiones](../../data-views/session-settings.md) para obtener más información. <br/>La gestión de eventos móviles en segundo plano se admite mediante el SDK móvil de Adobe Experience Platform. Consulte [Ciclo de vida para Edge Network](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/) para obtener más información. |
| Conversión de moneda | Se admite como parte del [formato de un componente de métrica](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/format.html?lang=es#currency) en una vista de datos. |
| Atributos del cliente | Ahora denominados “conjuntos de datos del perfil”, no se importan de manera automática desde Experience Cloud, pero deben cargarse en Experience Platform antes de que estén disponibles en Customer Journey Analytics. |
| Fuentes de datos | La exportación de datos de primera generación de conjuntos de datos está disponible a través de la [API de acceso a datos de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=es) y mediante [Destinos de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=es). Estas opciones proporcionan una exportación a nivel de evento/fila de todos los datos recopilados o introducidos en el lago de datos de Experience Platform. Las columnas de datos de procesamiento posterior no están disponibles porque las columnas posteriores se calculan en el momento de la consulta. La exportación de columnas de publicación está disponible a través del sistema de creación de informes. |
| Creación de informes de Data Warehouse | La [Exportación de tablas completas de Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md) es la evolución de los informes de Data Warehouse en Adobe Analytics, con muchas funciones nuevas y a menudo solicitadas que no están disponibles en Data Warehouse en la actualidad. |
| Métricas y dimensiones de entradas, salidas y tiempo empleado | Todas estas son ahora compatibles (las entradas y salidas ahora se denominan inicios de sesión y fines de sesión) y se calculan de forma ligeramente distinta. |
| Configuración de persistencia de eVar | Las eVars ya no forman parte de Customer Journey Analytics. Sin embargo, la configuración de persistencia ahora forma parte de las Vistas de datos y está disponible para todas las dimensiones. Tenga en cuenta que la persistencia se basa en el procesamiento de intervalos del informe, no en el procesamiento de la recopilación de datos. Las dimensiones configuradas en las Vistas de datos se limitan a una persistencia máxima de 90 días y no admiten persistencia ilimitada. |
| Dimensiones de segmentación geográfica | [Compatibilidad total](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=es) |
| Identificación basada en gráficos | A través de la [Identificación basada en gráficos](https://experienceleague.adobe.com/es/docs/analytics-platform/using/stitching/overview#graph-based-stitching), puede aprovechar la potencia del gráfico de identidad en [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/es/docs/experience-platform/identity/home) para elevar los conjuntos de datos a su identidad preferida. |
| Confusión de IP | Para clientes de Customer Journey Analytics que utilicen el conector de origen de Analytics para rellenar datos de Adobe Analytics en Customer Journey Analytics: la configuración de ofuscación de la IP aplicada en Adobe Analytics fluye hasta los datos de Customer Journey Analytics. Puede controlar esta configuración en Adobe Analytics según sea necesario.<p>Para clientes de Customer Journey Analytics que utilizan el SDK web de Experience Platform para rellenar datos en Platform y Customer Journey Analytics directamente. Puede utilizar la preparación de datos para la recopilación de datos en Platform con el fin de configurar reglas que ofusquen la dirección IP en función de los requisitos de la compañía. |
| Canales de marketing | Al utilizar el conector de origen de Analytics, los datos de los canales de marketing se incorporan a Customer Journey Analytics a través de ese conector. Las reglas del canal de marketing deben seguir configurándose en la versión tradicional de Adobe Analytics y algunas no son compatibles. Consulte [Canales de marketing de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html?lang=es) para obtener más información. <br/>Para implementaciones de WebSDK, las reglas de procesamiento de los canales de marketing en tiempo de informe son compatibles mediante [Campos derivados](../../data-views/derived-fields/derived-fields.md). |
| Persistencia de la variable de comercialización | Asistencia total a través de [dimensiones de enlace y métricas de enlace](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=es#binding-dimension) |
| Anulación de duplicación métrica | Ahora está configurado en métricas dentro de las vistas de datos. La anulación de duplicación de métricas se produce en el nivel de persona o sesión en lugar de en el nivel de conjunto de datos, vista de datos o conexión. |
| Creación de informes de sesión nueva frente a repetida | Anteriormente, se realizaba mediante la dimensión Número de visita. Se admiten sesiones nuevas y repetidas [con una ventana retrospectiva de 13 meses](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html?lang=es). |
| Reglas de procesamiento, reglas de VISTA, reglas de procesamiento de canales de marketing | Se admite mediante la funcionalidad de preparación de datos de Adobe Experience Platform así como [campos derivados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html?lang=es) tanto para conjuntos de datos basados en WebSDK como para datos del conector de origen de Analytics. |
| Variable Productos | Dentro de Experience Platform, los usuarios pueden utilizar una matriz de objetos dentro de un esquema del conjunto de datos para satisfacer este caso práctico. Dentro de Customer Journey Analytics, los clientes tienen la capacidad de usar cualquier número de variables de producto y no están restringidos a una sola variable como en Adobe Analytics. |
| Uso compartido de proyectos | El uso compartido de proyectos solo es compatible entre los usuarios de Customer Journey Analytics; no existe el uso compartido de proyectos entre Customer Journey Analytics y la versión tradicional de Analysis Workspace. |
| Report Builder | Compatible con un nuevo complemento de Office 365 para Excel. |
| Permisos de usuario/Controles de acceso de datos | Customer Journey Analytics distingue entre administradores de productos, administradores de perfiles de productos y usuarios de [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=es). Solo los administradores de productos pueden crear, actualizar o eliminar conexiones, proyectos, filtros o métricas calculadas creados por otros usuarios, mientras que los administradores de productos y los administradores de perfiles de productos pueden editar las vistas de datos. Hay disponibles permisos de usuario adicionales para tareas como crear métricas calculadas, filtros o anotaciones. |
| Visualizaciones | Todas las visualizaciones son compatibles, excepto la visualización de Mapa. |
| Vinculación entre dispositivos y canales | Compatible con conjuntos de datos que contienen información de identidad directamente (también conocida como vinculación “basada en campos”). La vinculación basada en gráficos aún no es compatible, pero está programada. Consulte [Vinculación](../../stitching/overview.md). |

{style="table-layout:auto"}

## Compatibilidad parcial {#partial}

| Función | Notas |
| --- | --- |
| Paneles | El panel en blanco, el panel de atribución, el panel de forma libre y las perspectivas rápidas son totalmente compatibles. Los paneles Comparación de segmentos y Analytics for Target (A4T) no son compatibles. |

{style="table-layout:auto"}

## Sin soporte, pero planificado {#planned}

| Función | Notas |
| --- | --- |
| Alertas | Se ha planificado lanzar una versión compatible. |
| Análisis de contribución | Se ha planificado lanzar una versión compatible. |
| Vinculación de ID mediante gráfico de dispositivos | Se ha planificado lanzar una versión compatible. |
| Plantillas de proyecto | Se ha planificado lanzar una versión compatible. |
| Creación de informes en tiempo real | Se ha planificado lanzar una versión compatible. |
| IQ de segmento | Se ha planificado lanzar una versión compatible. |
| Fuentes de datos de ID de transacción | Se ha planificado lanzar una versión compatible. |
| Fuentes de datos de nivel de resumen | Se ha planificado lanzar una versión compatible. |

{style="table-layout:auto"}

## Sin compatibilidad, aún no planificada {#not-planned}

| Función | Notas |
| --- | --- |
| Activity Map | Aún no se ha planificado lanzar una versión compatible. |
| Advertising Cloud | Aún no se ha planificado lanzar una versión compatible. |

{style="table-layout:auto"}

## Nunca será compatible {#never}

* Métrica de personas que utiliza la cooperación entre dispositivos

## Funciones de Adobe Customer Journey Analytics no disponibles en Adobe Analytics {#cja-not-aa}

En la tabla siguiente se enumeran las funciones disponibles en Customer Journey Analytics, pero que no son compatibles con Adobe Analytics.

| Funcionalidad | Más detalles |
| --- | --- |
| Capacidad para combinar conjuntos de datos (como grupos de informes de Adobe Analytics) | Customer Journey Analytics le permite [combinar datos](/help/connections/combined-dataset.md) de varios grupos de informes como si fueran un único grupo de informes de Adobe Analytics. |
| Alojamiento para cualquier tipo de datos | Customer Journey Analytics se combina con la capacidad de Experience Platform para albergar todo tipo de esquemas y datos. Con [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es), los datos se pueden representar y organizar de forma uniforme, listos para la combinación y exploración. Adobe Analytics se centra principalmente en los datos de análisis web y móviles con algunas funcionalidades para [importar datos](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=es). |
| Análisis entre dispositivos | Customer Journey Analytics admite la combinación perfecta de conjuntos de datos específicos del dispositivo desde sesiones no autenticadas y autenticadas. Customer Journey Analytics ofrece rellenar los datos históricos en dispositivos conocidos. En Adobe Analytics, esta posibilidad se limita a un único grupo de informes y al uso de un gráfico de dispositivos. |
| Mejoras de dimensión | Customer Journey Analytics proporciona mayor flexibilidad al utilizar las dimensiones: <ul><li>**Dimensiones personalizadas basadas en números**: [cree sus propias dimensiones basadas en números dentro de una vista de datos](/help/data-views/create-dataview.md#components).</li><li>**Ordenar dimensiones basadas en cadenas**: [ordene alfabéticamente las dimensiones basadas en cadenas en una tabla de forma libre.](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#sort-tables) </li></ul><p>En Adobe Analytics, solo había disponibles unas cuantas dimensiones numéricas integradas y no era posible ordenar por dimensiones basadas en cadenas.</p> |
| Campos derivados | Los [Campos derivados](/help/data-views/derived-fields/derived-fields.md) permiten realizar transformaciones durante el tiempo del informe en los datos. Los datos pueden combinarse, corregirse o crearse sobre la marcha y aplicarse de forma retroactiva a todos los informes. |
| Opciones mejoradas de seguridad y privacidad: preparación para HIPAA | Customer Journey Analytics está preparado para la HIPAA y ofrece [opciones de seguridad adicionales](/help/privacy/cmk.md) para el cumplimiento de la normativa. Adobe Analytics no está preparado para la HIPAA. |
| Análisis de experimentación | Customer Journey Analytics puede evaluar [el alza y la confianza de cualquier experimento](/help/analysis-workspace/c-panels/experimentation.md) de cualquier fuente de datos definida como parte de una conexión. Esta evaluación le permite comprender las relaciones de causa y efecto entre las interacciones de los clientes que abarcan cualquier canal. Analytics se limita al análisis de experimentación mediante A4T. |
| Previsión | La [Previsión](/help/analysis-workspace/c-forecast/forecasting.md) es una función de inteligencia artificial/aprendizaje automático que incluye una predicción estadística de datos relacionados con series temporales basada en los datos históricos que ya existen en Customer Journey Analytics. Las previsiones pueden aparecer en tablas de forma libre y visualizaciones de gráficos de líneas. |
| Análisis guiado | El [Análisis guiado](/help/guided-analysis/overview.md) es un formato de informes que permite a los usuarios autoabastecer rápidamente sus necesidades de datos para que puedan obtener perspectivas de alta calidad rápidamente y tomar más decisiones basadas en datos. El análisis guiado forma parte de Adobe Product Analytics, un complemento de análisis de recorrido del cliente. |
| Pies de ilustración inteligentes | Los subtítulos inteligentes utilizan aprendizaje automático avanzado e IA generativa para proporcionar información valiosa en lenguaje natural para las visualizaciones de Workspace. La versión inicial proporciona perspectivas generadas automáticamente para la visualización de [Línea](/help/analysis-workspace/visualizations/line.md). |
| Transformaciones de tiempo del informe | Las [Vistas de datos](/help/data-views/data-views.md) de Customer Journey Analytics le permiten interpretar aún más los datos de una conexión. Puede modificar o quitar datos sin cambiar su implementación, utilizar subcadenas para manipular dimensiones, crear métricas a partir de cualquier valor o filtrar subeventos. Todas estas transformaciones se realizan de manera no destructiva. Adobe Analytics proporciona funciones limitadas a través de grupos de informes virtuales y longitud de sesión personalizada. |
| Extensión de BI | La [Extensión de BI](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-usecases/data-export/bi-extension) le permite conectar CJA directamente a herramientas de visualización de BI populares, como Power BI o Tableau. Con esta extensión, puede hacer que los informes de BI coincidan con precisión con lo que ve en Analysis Workspace y otras interfaces del sistema de informes CJA. Esta es una forma mucho más sencilla de obtener informes de BI para CJA sin necesidad de volver a crear informes/métricas a partir de datos sin procesar. |
| Acceso SQL | Con la opción Data Distiller, Customer Journey Analytics puede eliminar las limitaciones de los datos recopilados en el procesamiento back-end de Adobe. Puede modificar los datos con SQL, crear valores y conjuntos de datos únicos para su empresa y continuar explorando. Analytics no admite ningún tipo de acceso SQL a sus datos. |
| Unión | [Identificación de identidad](/help/stitching/overview.md) (o simplemente, identificación) es una potente función que aumenta la idoneidad de un conjunto de datos de evento para el análisis en canales múltiples. El análisis en canales múltiples es un caso de uso principal que Customer Journey Analytics puede gestionar, lo que le permite combinar y ejecutar informes de varios conjuntos de datos de diferentes canales sin problemas, en función de un identificador común (ID de persona). |
| Métricas y dimensiones de clientes ilimitadas | Las dimensiones de Customer Journey Analytics son ilimitadas; los valores pueden ser numéricos, de texto, de objetos, de listas o de mezclas de todos. Las dimensiones pueden estar anidadas o ser jerárquicas.  <p>Por el contrario, Adobe Analytics admite hasta un máximo de 75 props y 250 eVars.</p> |
| Valores únicos ilimitados | Customer Journey Analytics admite valores únicos ilimitados o elementos de dimensión que se pueden registrar dentro de una sola dimensión. <p>No hay [límites de cardinalidad en una dimensión](/help/components/dimensions/high-cardinality.md), lo que permite que aparezca y se cuente cualquier valor único.</p><p>Este enfoque quita las limitaciones en la creación de informes y los análisis que pueden existir en implementaciones de Adobe Analytics a gran escala, lo que da como resultado etiquetas de [!UICONTROL Poco tráfico].</p><p>En Customer Journey Analytics, es posible ver una etiqueta [!UICONTROL Excesos en la cantidad de valores exclusivos], pero estos se producen con mucha menos frecuencia y se pueden mitigar aplicando un filtro o segmento a los datos.</p> |

{style="table-layout:auto"}
