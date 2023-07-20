---
title: Compatibilidad con funciones de Customer Journey Analytics
description: Customer Journey Analytics en comparación con las funciones de Adobe Analytics establecidas.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
source-git-commit: a49ef8b35b9d5464df2c5409339b33eacb90cd9c
workflow-type: tm+mt
source-wordcount: '2053'
ht-degree: 37%

---

# Compatibilidad con funciones de Adobe Customer Journey Analytics

Las siguientes tablas indican qué funciones de Adobe Analytics son compatibles, parcialmente o nada compatibles con Customer Journey Analytics, y qué funciones de Customer Journey Analytics no son compatibles o no están disponibles en Adobe Analytics. Estas listas cambiarán con el tiempo a medida que se añadan funciones a Customer Journey Analytics.

## Funciones y componentes totalmente compatibles {#full-support}

| Función Adobe Analytics | Notas sobre asistencia |
| --- | --- |
| Detección de anomalías | Compatibilidad total |
| Attribution IQ | Compatibilidad total |
| Métricas calculadas | Compatibilidad total. Las métricas calculadas existentes en la versión tradicional de Analysis Workspace no se transfieren a Customer Journey Analytics. |
| Eventos de calendario | Compatibilidad total. Los eventos de calendario se han implementado como [Anotaciones](/help/components/annotations/overview.md) en Workspace. |
| Descarga de CSV | Compatibilidad total |
| Calendarios personalizados | Compatibilidad total |
| Comparaciones de fechas | Compatibilidad total |
| Intervalos de fechas | Se admite toda la funcionalidad de intervalo de fechas. |
| Dimensiones | Compatibilidad total. Customer Journey Analytics utiliza XDM y admite dimensiones ilimitadas. Customer Journey Analytics no está vinculado a las eVars o props personalizadas del Adobe Analytics tradicional. |
| Eliminación de RGPD | Compatibilidad total. Tenga en cuenta que el RGPD ahora se gestiona en coordinación con [!UICONTROL Adobe Experience Platform]. El Customer Journey Analytics hereda los cambios de datos [!UICONTROL Experience Platform] hace a los conjuntos de datos subyacentes. |
| Creación de informes de alza y confianza | Asistencia total a través de [Panel de experimentación](/help/analysis-workspace/c-panels/experimentation.md) |
| Variables de lista/Propiedades de lista | Compatibilidad total. Customer Journey Analytics utiliza XDM y admite matrices de cadenas ilimitadas que pueden utilizarse de manera similar a listVars. |
| eVars de comercialización | Asistencia total a través de [dimensiones de enlace y métricas de enlace](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=es#binding-dimension) |
| Métricas | Compatibilidad total. Customer Journey Analytics utiliza el Experience Data Model (XDM), admite métricas ilimitadas y no está vinculado a los eventos de éxito personalizados de Adobe Analytics. Algunas métricas estándar han cambiado de nombre desde Adobe Analytics: Visitantes = Personas, Visitas = Sesiones, Visitas = Eventos. |
| Paneles y cuadros de resultados para móviles | Compatibilidad total |
| Paneles | El panel en blanco, el panel de atribución, el panel de forma libre y las perspectivas rápidas son totalmente compatibles. |
| Exportación de PDF | Compatibilidad total |
| Revisión del proyecto | Compatibilidad total |
| Vinculación de proyectos | Compatibilidad total |
| Procesamiento de intervalo de tiempo | Compatibilidad total. El Customer Journey Analytics depende exclusivamente del Procesamiento de intervalo de tiempo. |
| Acceso a la API de informes | Compatibilidad total. Disponible a través del [API de Customer Journey Analytics](https://developer.adobe.com/cja-apis/docs/). |
| Informes y proyectos programados | Compatibilidad total |
| Segmentos | Compatibilidad total. Ahora se denominan &quot;Filtros&quot;: tenga en cuenta que los segmentos existentes en la versión tradicional de Analysis Workspace no se transfieren a Customer Journey Analytics. |
| Grupos de informes virtuales | Compatibilidad total. Ahora se llama [Vistas de datos](/help/data-views/create-dataview.md). |
| Revisión de componentes del grupo de informes virtuales | Compatibilidad total. Ahora forma parte de las Vistas de datos. |
| Streaming de medios de Analytics | Los datos de medios están disponibles mediante el conector de origen de Analytics como parte del panel Visualizadores simultáneos de medios y el panel Tiempo invertido en la reproducción de medios en Workspace. |

{style="table-layout:auto"}

## Compatible de una nueva forma {#new-support}

| Función | Notas |
| --- | --- |
| Publicación de audiencias (Publicación de segmentos) | Compatible si tiene licencia con la plataforma de datos del cliente o los productos de Journey Optimizer de Adobe. [Publicación de audiencias](/help/components/audiences/audiences-overview.md) envía audiencias al perfil del cliente en tiempo real en Experience Platform. |
| Clasificaciones | Ahora se denomina Conjuntos de datos de búsqueda. Las clasificaciones utilizadas en Analytics se pueden importar al Experience Platform y al Customer Journey Analytics mediante el Classifications Source Connector de Analytics. Los conjuntos de datos de búsqueda también se pueden cargar directamente en el Experience Platform y estar disponibles en el Customer Journey Analytics. |
| Generador de reglas de clasificación | Admitido mediante [subcadenas](/help/data-views/component-settings/substring.md) en Customer Journey Analytics. Utiliza manipulaciones de cadenas en el tiempo del informe en lugar de conjuntos de datos de búsqueda. |
| Definición de sesiones personalizada | Compatibilidad con todas las funciones de definición de sesiones personalizada excepto eventos de fondo móviles. |
| Conversión de divisa | Compatible como parte de [formato de un componente de métrica](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/format.html?lang=en#currency) en una vista de datos. |
| Persistencia de la variable de comercialización | Asistencia total a través de [dimensiones de enlace y métricas de enlace](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=es#binding-dimension) |
| Atributos del cliente | Ahora denominados &quot;conjuntos de datos del perfil&quot;, no se importan de manera automática desde Experience Cloud, pero deben cargarse en Experience Platform antes de que estén disponibles en Customer Journey Analytics. |
| Fuentes de datos | La exportación de datos de primera generación de conjuntos de datos está disponible a través del [API de acceso a datos de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=en) y mediante [Destinos del Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en). Estas opciones proporcionan una exportación a nivel de evento/fila de todos los datos recopilados o introducidos en el lago de datos del Experience Platform. Las columnas de datos de procesamiento posterior no están disponibles porque las columnas posteriores se calculan en el momento de la consulta. La exportación de columnas post está disponible a través del sistema de informes. |
| Anulación de duplicación métrica | Ahora está configurado en métricas dentro de las vistas de datos. La anulación de duplicación de métricas se produce en el nivel de persona o sesión en lugar de en el nivel de conjunto de datos, vista de datos o conexión. |
| Métricas y dimensiones de entradas, salidas y tiempo empleado | Todas estas son ahora compatibles (las entradas y salidas ahora se denominan inicios de sesión y fines de sesión) y se calculan de forma ligeramente distinta. |
| Configuración de persistencia de eVar | Las eVars ya no forman parte de Customer Journey Analytics. Sin embargo, la configuración de persistencia ahora forma parte de las Vistas de datos y está disponible para todas las dimensiones. Tenga en cuenta que la persistencia se basa en el procesamiento de intervalos del informe, no en el procesamiento de la recopilación de datos. Los Dimension configurados en Vistas de datos se limitan a una persistencia máxima de 90 días y no admiten persistencia ilimitada. |
| Confusión de IP | Para clientes de Customer Journey Analytics que utilicen el conector de origen de Analytics para rellenar datos de Adobe Analytics en Customer Journey Analytics: la configuración de confusión de IP aplicada en Adobe Analytics fluye a través de los datos de Customer Journey Analytics. Puede controlar esta configuración en Adobe Analytics según sea necesario.<p>Para clientes de Customer Journey Analytics que utilizan el SDK web de Experience Platform para rellenar datos en Platform y Customer Journey Analytics directamente. Puede utilizar la preparación de datos para la recopilación de datos en Platform con el fin de configurar reglas que ofusquen la dirección IP en función de los requisitos de la compañía. |
| Creación de informes de sesión nueva frente a repetida | Anteriormente, se realizaba mediante la dimensión Número de visita. Se admiten sesiones nuevas y repetidas [con una ventana retrospectiva de 13 meses](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html?lang=es). |
| Variable de producto | Dentro de Experience Platform, los usuarios pueden utilizar una matriz de campos de tipo Objeto dentro de un esquema del conjunto de datos para satisfacer este caso práctico. Dentro de Customer Journey Analytics, los clientes pueden utilizar cualquier número de variables de producto y no están restringidos a una sola variable como en Adobe Analytics. |
| Uso compartido de proyecto | El uso compartido de proyectos solo es compatible entre los usuarios de Customer Journey Analytics; no existe el uso compartido de proyectos entre Customer Journey Analytics y la versión tradicional de Analysis Workspace. |
| Visualizaciones | Todas las visualizaciones son compatibles, excepto la visualización de Mapa. |
| Report Builder (complemento de Excel) | Compatible con un nuevo complemento de Office 365 para Excel. |
| Permisos de usuario/Controles de acceso de datos | El Customer Journey Analytics distingue entre [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=es) administradores de productos, administradores de perfiles de productos y usuarios. Solo los administradores de productos pueden crear, actualizar o eliminar conexiones, proyectos, filtros o métricas calculadas creados por otros usuarios, mientras que los administradores de productos y los administradores de perfiles de productos pueden editar las vistas de datos. Hay disponibles permisos de usuario adicionales para tareas como crear métricas calculadas, filtros o anotaciones. |
| Reglas de procesamiento, Reglas de VISTA, Reglas de procesamiento de canales de marketing | Se admite mediante la funcionalidad de preparación de datos de Adobe Experience Platform tanto para conjuntos de datos basados en WebSDK como para datos del conector de origen de Analytics. |
| Canales de marketing | Al utilizar el conector de origen de Analytics, los datos de los canales de marketing fluyen a Customer Journey Analytics a través de ese conector. Las reglas del canal de marketing se configuran en la versión tradicional de Adobe Analytics y algunas reglas no son compatibles. Para obtener más información, consulte [Documentación de canales de marketing de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html). <br/>Para implementaciones de WebSDK, las reglas de procesamiento de los canales de marketing en tiempo de informe son compatibles mediante [Campos derivados](../../data-views/derived-fields/derived-fields.md). |

{style="table-layout:auto"}

## Compatibilidad parcial {#partial}

| Función | Notas |
| --- | --- |
| Vinculación entre dispositivos y canales | Compatible con conjuntos de datos que contienen información de identidad directamente (también conocida como vinculación “basada en campos”). La vinculación basada en gráficos aún no es compatible, pero está programada. Consulte [Vinculación](../../stitching/overview.md). |
| Filtros de bots | Para [Conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=es)Conjuntos de datos basados en, se aplica el filtrado de bots. La lógica general de filtrado de bots para otros conjuntos de datos no es realizada por [!UICONTROL Experience Platform] o Customer Journey Analytics. |
| Dimensiones del Dispositivo, Explorador, Referente, Tecnología | Admitido para [Conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=es)Conjuntos de datos basados en. Consulte [Documentación sobre las variables de Analytics que se admiten mediante ADC](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=es).<p>Si utiliza la recopilación de datos del SDK web de Experience Platform, actualmente no se admiten el dispositivo y las dimensiones basadas en la búsqueda de dispositivos. Está planificada la compatibilidad futura. |
| Dimensiones de segmentación geográfica | Toda la segmentación geográfica/geografía recopilada en Adobe Analytics se transfiere a Customer Journey Analytics a través del [Conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=es). Las implementaciones que no utilizan el conector de origen de Analytics, pero dependen del SDK web de Experience Platform para la recopilación de datos digitales, pueden utilizar el [Servicio de búsqueda geográfica de Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=es). |
| Paneles | El panel en blanco, el panel de atribución, el panel de forma libre y las perspectivas rápidas son totalmente compatibles. Los paneles Comparación de segmentos y Analytics for Target (A4T) no son compatibles. |
| Reglas de procesamiento | En los conjuntos de datos basados en el conector de origen de Analytics, las reglas de procesamiento se aplican igual. Las [Funciones de preparación de datos de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=es) también se pueden usar como reemplazo de las reglas de procesamiento de datos que van directamente a Platform. |
| A4T | Se proporciona soporte parcial mediante campos en la variable [Conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=es). Se ha planificado la compatibilidad con los nombres descriptivos de A4T en las actividades y experiencias de Target. |

{style="table-layout:auto"}

## Sin soporte, pero planificado {#planned}

| Función | Notas |
| --- | --- |
| Alertas | Se ha planificado lanzar una versión compatible. |
| Análisis de contribución | Se ha planificado lanzar una versión compatible. |
| Informes de Data Warehouse | La compatibilidad está planificada desde la interfaz de Analysis Workspace. Adobe Experience Platform [[!UICONTROL Servicio de consultas]](<https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=es>) también proporciona una interfaz para estos casos de uso en Customer Journey Analytics. |
| Configuración de ID mediante Device Graph | Se ha planificado lanzar una versión compatible. |
| Plantillas de proyecto | Se ha planificado lanzar una versión compatible. |
| Informes en tiempo real | Se ha planificado lanzar una versión compatible. |
| IQ de segmento | Se ha planificado lanzar una versión compatible. |
| Fuentes de datos de ID de transacción | Se ha planificado lanzar una versión compatible. |
| Migración de proyectos/filtros/métricas calculadas de Adobe Analytics a Customer Journey Analytics | Se ha planificado lanzar una versión compatible. |
| Fuentes de datos de nivel de resumen | Se ha planificado lanzar una versión compatible. |

{style="table-layout:auto"}

## No hay soporte, aún no se ha planificado {#not-planned}

| Función | Notas |
| --- | --- |
| Activity Map | Aún no se ha planificado lanzar una versión compatible. |
| Advertising Cloud | Aún no se ha planificado lanzar una versión compatible. |

{style="table-layout:auto"}

## Nunca admitido {#never}

* Métrica de personas que utiliza la cooperación entre dispositivos
* Paneles de Reports &amp; Analytics
* Marcadores de Reports &amp; Analytics
* Destinatarios de Reports &amp; Analytics

## Funciones de Adobe Customer Journey Analytics no disponibles en Adobe Analytics {#cja-not-aa}

En la tabla siguiente se enumeran las funciones disponibles en Customer Journey Analytics, pero que no son compatibles con Adobe Analytics.

| Funcionalidad | Más detalles |
| --- | --- |
| Alojamiento para cualquier tipo de datos | Customer Journey Analytics se combina con la capacidad de Experience Platform para albergar todo tipo de esquemas y tipos de datos. Uso de [Modelo de datos de experiencia (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es), los datos se pueden representar y organizar de forma uniforme, listos para la combinación y exploración. Adobe Analytics se centra principalmente en datos de análisis web y móviles con algunas funcionalidades para [importar datos](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=es). |
| Métricas y Dimension de clientes ilimitados | Las dimensiones del Customer Journey Analytics son ilimitadas; los valores pueden ser numéricos, de texto, de objetos, de listas o de mezclas de todos. Los Dimension pueden estar anidados o ser jerárquicos. Analytics admite hasta un máximo de 75 props y 250 eVars. |
| Cardinalidad ilimitada / valores únicos | Customer Journey Analytics admite valores únicos ilimitados o elementos de dimensión que se pueden registrar dentro de una sola dimensión. Adobe Analytics está limitado a 500 000 valores únicos. Los valores o dimensiones únicos ilimitados eliminan las limitaciones de informes y análisis que existen actualmente con la implementación de Analytics a gran escala. |
| Transformaciones de tiempo de informes | Las transformaciones de tiempo de los informes (mejor conocidas como vistas de datos) en Customer Journey Analytics le permiten interpretar aún más los datos de una conexión. Puede modificar o eliminar datos sin volver a implementar; utilizar subcadenas para manipular dimensiones; crear métricas a partir de cualquier valor; filtrar subeventos. Y la transformación se hace de manera no destructiva. Adobe Analytics proporciona funciones limitadas a través de grupos de informes virtuales y sesionización. |
| Análisis de experimentación | El Customer Journey Analytics puede evaluar el alza y la confianza de cualquier experimento desde cualquier fuente de datos definida como parte de una conexión. Esta evaluación le permite comprender las relaciones de causa y efecto entre las interacciones de los clientes que abarcan cualquier canal. Analytics se limita a análisis de experimentación a través de la integración de Analytics para Target (A4T). |
| Análisis entre dispositivos | Customer Journey Analytics admite la combinación perfecta de conjuntos de datos específicos del dispositivo desde sesiones no autenticadas y autenticadas. El Customer Journey Analytics ofrece rellenar los datos históricos en dispositivos conocidos. En Analytics, esta capacidad se limita a un único grupo de informes y al uso de un gráfico de dispositivos. |
| Acceso SQL | Con la opción Data Distiller, Customer Journey Analytics puede eliminar las limitaciones de los datos recopilados en el procesamiento back-end de los Adobes. Puede modificar los datos con SQL, crear valores y conjuntos de datos únicos para su empresa y continuar explorando. Analytics no admite ningún tipo de acceso SQL a sus datos. |
| Opciones mejoradas de seguridad y privacidad: preparación para HIPAA | El Customer Journey Analytics está preparado para la HIPAA y ofrece opciones de seguridad adicionales para el cumplimiento de la normativa. Adobe Analytics no está preparado para HIPAA. |

{style="table-layout:auto"}
