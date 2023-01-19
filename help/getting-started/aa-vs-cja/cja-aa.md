---
title: Compatibilidad con funciones de Customer Journey Analytics
description: Customer Journey Analytics en comparación con las funciones de Adobe Analytics establecidas.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: a9009c44a8e739add7fbcb9f9c31676d38af0094
workflow-type: tm+mt
source-wordcount: '1537'
ht-degree: 98%

---

# Compatibilidad con funciones de Customer Journey Analytics

Las siguientes tablas detalla qué funciones de Adobe Analytics son compatibles, parcialmente o nada compatibles con Customer Journey Analytics (CJA). Estas listas cambiarán con el tiempo a medida que se añadan funciones a CJA.

## Funciones y componentes totalmente compatibles

| Función Adobe Analytics | Notas sobre asistencia |
| --- | --- |
| Detección de anomalías | Compatibilidad total. |
| Attribution IQ | Compatibilidad total. |
| Métricas calculadas | Compatibilidad total. Tenga en cuenta que las métricas de cálculo existentes en la versión tradicional de Analysis Workspace no se transferirán a CJA. |
| Eventos de calendario | Compatibilidad total. Los eventos de calendario se han implementado como [Anotaciones](/help/components/annotations/overview.md) en Workspace. |
| Descarga de CSV | Compatibilidad total. |
| Calendarios personalizados | Compatibilidad total. |
| Comparaciones de fechas | Compatibilidad total. |
| Intervalos de fechas | Se admite toda la funcionalidad de intervalo de fechas. |
| Dimensiones | Compatibilidad total; CJA aprovecha XDM y admite dimensiones ilimitadas. CJA no está vinculado a las eVars o props personalizadas de Adobe Analytics tradicional. |
| Eliminación de RGPD | Compatibilidad total. Tenga en cuenta que el RGPD ahora se gestiona en coordinación con [!UICONTROL Adobe Experience Platform]. CJA hereda los cambios de datos que [!UICONTROL Experience Platform] hace en los conjuntos de datos subyacentes. |
| Creación de informes de alza y confianza | Asistencia total a través de [Panel de experimentación](/help/analysis-workspace/c-panels/experimentation.md) |
| Variables de lista/Propiedades de lista | Compatibilidad total; CJA aprovecha XDM y admite matrices de cadenas ilimitadas que pueden utilizarse de manera similar a listVars. |
| eVars de comercialización | Asistencia total a través de [dimensiones de enlace y métricas de enlace](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=es#binding-dimension) |
| Métricas | Compatibilidad total. CJA aprovecha Experience Data Model (XDM), admite métricas ilimitadas y no está vinculado a los eventos de éxito personalizados de Analytics tradicional. Tenga en cuenta que algunas métricas estándar han cambiado de nombre desde la versión tradicional de Analytics: Visitantes = Personas, Visitas = Sesiones, Visitas = Eventos. |
| Paneles y cuadros de resultados para móviles | Compatibilidad total. |
| Paneles | El panel en blanco, el panel de atribución, el panel de forma libre y las perspectivas rápidas son totalmente compatibles. |
| Exportación de PDF | Compatibilidad total. |
| Revisión del proyecto | Compatibilidad total. |
| Vinculación de proyectos | Compatibilidad total. |
| Procesamiento de intervalo de tiempo | Compatibilidad total; CJA se basa exclusivamente en el procesamiento de intervalos del informe. |
| Acceso a la API de informes | Compatibilidad total. Disponible a través de la [API de CJA](https://www.adobe.io/cja-apis/docs/). |
| Informes y proyectos programados | Compatibilidad total. |
| Segmentos | Compatibilidad total. Ahora se denomina Filtros. Tenga en cuenta que los segmentos existentes en la versión tradicional de Analysis Workspace no se transferirán a CJA. |
| Grupos de informes virtuales | Compatibilidad total. Ahora se denomina [Vistas de datos](/help/data-views/create-dataview.md). |
| Revisión de componentes de VRS | Compatibilidad total; Ahora forma parte de Vistas de datos. |
| Streaming de medios de Analytics | Los datos de medios están disponibles mediante el conector de datos de Analytics como parte del panel Visualizadores simultáneos de medios y el panel Tiempo invertido en la reproducción de contenido en Workspace. |

{style=&quot;table-layout:auto&quot;}

## Compatible de una nueva forma

| Función | Notas |
| --- | --- |
| Publicación de audiencias (Publicación de segmentos) | Compatible si tiene licencia con la plataforma de datos del cliente o los productos de Journey Optimizer de Adobe. [Publicación de audiencias](/help/components/audiences/audiences-overview.md) envía audiencias al perfil del cliente en tiempo real en Experience Platform. |
| Clasificaciones | Ahora se denomina Conjuntos de datos de búsqueda. Las clasificaciones utilizadas en Analytics se pueden importar a Experience Platform y a CJA mediante el Classifications Source Connector de Analytics. Los conjuntos de datos de búsqueda también se pueden cargar directamente en AEP y estar disponibles en CJA. |
| Generador de reglas de clasificación | Compatible mediante el uso de [subcadenas](/help/data-views/component-settings/substring.md) en CJA. Utiliza manipulaciones de cadenas en el tiempo del informe en lugar de conjuntos de datos de búsqueda. |
| Definición de sesiones personalizada | Compatibilidad con todas las funciones de definición de sesiones personalizada excepto las visitas en segundo plano móviles. |
| Persistencia de la variable de comercialización | Asistencia total a través de [dimensiones de enlace y métricas de enlace](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=es#binding-dimension) |
| Atributos del cliente | Ahora se denomina Conjuntos de datos de perfil. No se importan de manera automática desde Experience Cloud, pero deberán cargarse en AEP antes de que estén disponibles en CJA. |
| Anulación de duplicación métrica | Ahora está configurado en métricas dentro de las vistas de datos. La anulación de duplicación de métricas se produce en el nivel de persona o sesión en lugar de en el nivel de conjunto de datos, vista de datos o conexión. |
| Métricas y dimensiones de entradas, salidas y tiempo empleado | Todas estas son ahora compatibles (las entradas y salidas ahora se denominan inicios de sesión y fines de sesión) y se calculan de forma ligeramente distinta. |
| Configuración de persistencia de eVar | Las eVars ya no forman parte de CJA. Sin embargo, la configuración de persistencia ahora forma parte de las Vistas de datos y está disponible para todas las dimensiones. Tenga en cuenta que la persistencia se basa en el procesamiento de intervalos del informe, no en el procesamiento de la recopilación de datos. Las dimensiones configuradas en Vistas de datos se limitan a una persistencia máxima de 90 días y no admiten persistencia ilimitada. |
| Confusión de IP | Para clientes de CJA que utilicen el conector de origen de Analytics para rellenar datos de Adobe Analytics en CJA: la configuración de confusión de IP aplicada en Adobe Analytics fluye a través de los datos de CJA. Puede controlar esta configuración en Adobe Analytics según sea necesario.<p>Para clientes de CJA que utilizan el SDK web de Adobe Experience Platform para rellenar datos en Platform y CJA directamente: puede usar la preparación de datos para la recopilación de datos en Platform y configurar reglas que ofusquen la dirección IP en función de los requisitos de su compañía. |
| Creación de informes de sesión nueva frente a repetida | Anteriormente, se realizaba mediante la dimensión Número de visita. Se admiten sesiones nuevas y repetidas [con una ventana retrospectiva de 13 meses](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=es#new-repeat). |
| Variable de producto | Dentro de Experience Platform, los usuarios pueden utilizar una matriz de campos de tipo Objeto dentro de un esquema del conjunto de datos para satisfacer este caso práctico. Dentro de CJA, los clientes tienen la capacidad de usar cualquier número de variables de producto y no están restringidos a una sola variable como en Adobe Analytics. |
| Uso compartido de proyecto | El uso compartido de proyectos solo es compatible entre los usuarios de CJA; no existe el uso compartido de proyectos entre CJA y la versión tradicional de Analysis Workspace. |
| Visualizaciones | Todas las visualizaciones son compatibles, excepto la visualización de Mapa. |
| Report Builder (complemento de Excel) | Compatible con un nuevo complemento de Office 365 para Excel. |
| Permisos de usuario/Controles de acceso de datos | CJA distingue entre administradores de productos, administradores de perfiles de productos y usuarios de [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=es). Solo los administradores de productos pueden crear, actualizar o eliminar conexiones, proyectos, filtros o métricas calculadas creados por otros usuarios, mientras que los administradores de productos y los administradores de perfiles de productos pueden editar las vistas de datos. Hay disponibles permisos de usuario adicionales para tareas como crear métricas calculadas, filtros o anotaciones. |
| Reglas de procesamiento, Reglas de VISTA, Reglas de procesamiento de canales de marketing | Se admite mediante la funcionalidad de preparación de datos de Adobe Experience Platform tanto para conjuntos de datos basados en WebSDK como para datos del conector de datos de Analytics. |

{style=&quot;table-layout:auto&quot;}

## Compatibilidad parcial

| Función | Notas |
| --- | --- |
| Canales de marketing | Los datos de los canales de marketing ahora fluyen a CJA a través de Analytics Source Connector. Las reglas del canal de marketing deben seguir configurándose en la versión tradicional de Adobe Analytics y algunas reglas no son compatibles. Para obtener más información, consulte la [documentación sobre canales de marketing de CJA](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=es#cja-usecases). Además, para implementaciones de WebSDK, hay complementos disponibles para definir canales de marketing del lado del cliente. Está planificado que en el futuro se admitan las reglas de procesamiento de tiempo de los canales de marketing. |
| Vinculación entre dispositivos y canales | Compatible con conjuntos de datos que contienen información de identidad directamente (también conocida como vinculación &quot;basada en el campo&quot;). La vinculación basada en gráficos aún no es compatible, pero está planificada. Consulte [Cross-Channel Analytics](/help/cca/overview.md). |
| Filtros de bots | Para conjuntos de datos basados en el [conector de origen de Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=es), se aplica el filtrado de bots. La lógica general de filtrado de bots para otros conjuntos de datos no es realizada por [!UICONTROL Experience Platform] o CJA. |
| Dimensiones del Dispositivo, Explorador, Referente, Tecnología | Admitido para conjuntos de datos basados en [Conector de origen de Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=es). Consulte nuestra [documentación sobre las variables de Analytics que se admiten a través de ADC](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=es).<p>Si no utiliza el conector de origen de Adobe para rellenar datos de Adobe Analytics en CJA, sino que utiliza la recopilación de datos del SDK web de Experience Platform, actualmente no se admiten el dispositivo y las dimensiones basadas en la búsqueda de dispositivos. Está planificada la compatibilidad futura. |
| Dimensiones de segmentación geográfica | Toda la segmentación geográfica/geografía recopilada en Adobe Analytics se transfiere a CJA a través del [conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=es). Las implementaciones que no utilicen Analytics Source Connector, como las que dependen del SDK web de AEP para la recopilación de datos digitales, no tendrán la lista completa de búsquedas geográficas realizadas automáticamente: se admiten países y estados de todo el mundo, ciudades y códigos postales no. |
| Paneles | El panel en blanco, el panel de atribución, el panel de forma libre y las perspectivas rápidas son totalmente compatibles. Los paneles Comparación de segmentos y Analytics for Target (A4T) no son compatibles. |
| Reglas de procesamiento | En los conjuntos de datos basados en Analytics Source Connector, las reglas de procesamiento se aplican igual. Las [Funciones de preparación de datos de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=es) también se pueden usar como reemplazo de las reglas de procesamiento de datos que van directamente a Platform. |
| A4T | Se proporciona soporte parcial mediante campos en el [Conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=es). Se ha planificado la compatibilidad con nombres descriptivos de A4T en Actividades y experiencias de Target. |

{style=&quot;table-layout:auto&quot;}

## No compatible actualmente, pero planificado

| Función | Notas |
| --- | --- |
| Alertas | Se ha planificado lanzar una versión compatible. |
| Análisis de contribución | Se ha planificado lanzar una versión compatible. |
| Creación de informes de Data Warehouse (100 % de exportación de filas) | La compatibilidad está planificada desde la interfaz de Analysis Workspace. [[!UICONTROL El servicio de consulta]](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=es) de Adobe Experience Platform también proporciona una interfaz para estos casos de uso en CJA. |
| Configuración de ID mediante Device Graph | Se ha planificado lanzar una versión compatible. |
| Plantillas de proyecto | Se ha planificado lanzar una versión compatible. |
| Informes en tiempo real | Se ha planificado lanzar una versión compatible. |
| IQ de segmento | Se ha planificado lanzar una versión compatible. |
| Conversión de divisa | Se ha planificado lanzar una versión compatible. |
| Fuentes de datos | La compatibilidad está planificada a través de destinos de AEP. |
| Fuentes de datos de ID de transacción | Se ha planificado lanzar una versión compatible. |
| Migración de proyectos/filtros/métricas calculadas de AA a CJA | Se ha planificado lanzar una versión compatible. |
| Fuentes de nivel de resumen | Se ha planificado lanzar una versión compatible. |

{style=&quot;table-layout:auto&quot;}

## Compatibilidad aún no planificada

| Función | Notas |
| --- | --- |
| Activity Map | Aún no se ha planificado lanzar una versión compatible. |
| Advertising Cloud | Aún no se ha planificado lanzar una versión compatible. |
| Fuentes de datos de resumen | Aún no se ha planificado lanzar una versión compatible. |

{style=&quot;table-layout:auto&quot;}

## Nunca será compatible

* Métrica de personas que utiliza la cooperación entre dispositivos
* Paneles de Reports &amp; Analytics
* Marcadores de Reports &amp; Analytics
* Destinatarios de Reports &amp; Analytics
* Mobile Services
