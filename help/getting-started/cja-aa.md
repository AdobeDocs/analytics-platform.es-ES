---
title: Compatibilidad con funciones de Customer Journey Analytics
description: Customer Journey Analytics en comparación con las funciones de Adobe Analytics establecidas.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
source-git-commit: c23b172fd4dc5d0303723c4e8ccfeaa251257bfd
workflow-type: tm+mt
source-wordcount: '1188'
ht-degree: 73%

---

# Compatibilidad con funciones de Customer Journey Analytics

Las siguientes tablas detalla qué funciones de Adobe Analytics son compatibles, parcialmente o nada compatibles con Customer Journey Analytics (CJA). Estas listas cambiarán con el tiempo a medida que se añadan funciones a CJA.

## Funciones y componentes totalmente compatibles

| Función Adobe Analytics | Notas sobre asistencia |
| --- | --- |
| Detección de anomalías | Compatibilidad total. |
| Attribution IQ | Compatibilidad total. |
| Métricas calculadas | Asistencia total; Tenga en cuenta que las métricas calculadas existentes en la versión tradicional de Analysis Workspace no se transferirán a CJA. |
| Vinculación entre dispositivos y canales | Asistencia total; Consulte [Análisis en canales múltiples](/help/connections/cca/overview.md). |
| Comparaciones de fechas | Compatibilidad total. |
| Dimensiones | Asistencia total; CJA aprovecha XDM y admite dimensiones ilimitadas. CJA no está vinculado a las eVars o props personalizadas de la Adobe Analytics tradicional. |
| Dimensiones de Analysis Workspace predeterminadas (por ejemplo: Tipo de explorador, Tipo de referente, Sistema operativo, etc.) | CJA proporciona estas dimensiones de forma nativa siempre y cuando se rellenen los campos XDM base (como agente de usuario o ID de dispositivo). Para los clientes que utilizan el Conector de datos de Analytics (ADC), algunas de estas dimensiones están disponibles, pero no todas. Consulte nuestra [documentación sobre las variables de Analytics que se admiten a través de ADC](https://docs.adobe.com/content/help/es-ES/experience-platform/ingestion/home.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Eliminación de RGPD | Asistencia total; tenga en cuenta que el RGPD ahora se gestiona en coordinación con [!UICONTROL Adobe Experience Platform]. CJA hereda los cambios de datos que [!UICONTROL Experience Platform] haga en los conjuntos de datos subyacentes. |
| Variables de lista/Propiedades de lista | Asistencia total; CJA aprovecha XDM y admite matrices de cadenas ilimitadas que pueden utilizarse de manera similar a listVars. |
| Métricas | Asistencia total; CJA aprovecha el Experience Data Model (XDM), admite métricas ilimitadas y no está vinculado a los eventos de éxito personalizados del Analytics tradicional. Tenga en cuenta que algunas métricas estándar han cambiado de nombre desde la versión tradicional de Analytics: Visitantes = Personas, Visitas = Sesiones, Visitas = Eventos. |
| Exportación de PDF | Compatibilidad total. |
| Revisión del proyecto | Compatibilidad total. |
| Vinculación de proyectos | Compatibilidad total. |
| Procesamiento de intervalo de tiempo | Asistencia total; CJA se basa exclusivamente en el procesamiento de intervalo de tiempo. |
| Acceso a la API de informes | Asistencia total; Disponible a través de la [API de CJA](https://www.adobe.io/cja-apis/docs/). |
| Informes y proyectos programados | Compatibilidad total. |
| Segmentos | Asistencia total; Ahora se denomina &quot;Filtros&quot;: tenga en cuenta que los segmentos existentes en la Analysis Workspace tradicional no se transferirán a CJA. |
| Permisos de usuario/Controles de acceso de datos | Asistencia total; CJA distingue entre [administradores de producto de Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=en) y usuarios. Solo los administradores de productos pueden <ul><li>Crear/actualizar/eliminar conexiones o Vistas de datos</li><li>Actualizar o eliminar proyectos, filtros o métricas de cálculo creados por otros usuarios, y</li><li>Compartir un proyecto de Workspace con todos los usuarios.</li></ul> |
| Grupos de informes virtuales | Asistencia total; Ahora se denomina [Vistas de datos](/help/data-views/create-dataview.md). |
| Revisión de componentes de VRS | Asistencia total; Ahora forma parte de las vistas de datos. |

## Admitido con advertencias

| Función | Notas |
| --- | --- |
| A4T | Se proporciona compatibilidad mediante los campos del [Conector de origen de Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=es). |
| Clasificaciones | Ahora se denomina Conjuntos de datos de búsqueda. Las clasificaciones utilizadas en Analytics se pueden importar a Experience Platform y a CJA mediante el Classifications Data Connector de Analytics. Los conjuntos de datos de búsqueda también se pueden cargar directamente en AEP y estar disponibles en CJA. |
| Definición de sesiones personalizada | Compatibilidad con todas las funciones de definición de sesiones personalizada que no sean visitas en segundo plano móviles. |
| Atributos del cliente | Ahora denominados &quot;conjuntos de datos de perfil&quot;, no se importan automáticamente desde el Experience Cloud, pero deberán cargarse en AEP antes de que estén disponibles en CJA. |
| Intervalos de fechas | Se admite toda la funcionalidad de intervalo de fechas, excepto la compatibilidad con calendarios personalizados, que está planificada. |
| Dimensiones de dispositivo, explorador y tecnología | Estas dimensiones se incluyen automáticamente cuando un conjunto de datos de AEP incluye campos de esquema XDM específicos y se ajusta a la clase de evento de Experience XDM. |
| Métricas y dimensiones de entradas, salidas y tiempo empleado | Todas estas son ahora compatibles (las entradas y salidas ahora se denominan inicios de sesión y fines de sesión) y se calculan de forma ligeramente distinta. |
| Configuración de persistencia de eVar | Las eVars ya no forman parte de CJA. Sin embargo, la configuración de persistencia ahora forma parte de las Vistas de datos y está disponible para todas las dimensiones. Tenga en cuenta que la persistencia se basa en el procesamiento de intervalos del informe, no en el procesamiento de la recopilación de datos. Las dimensiones configuradas en Vistas de datos se limitan a una persistencia máxima de 90 días y no admiten persistencia ilimitada. |
| Dimensiones de segmentación geográfica | Toda la segmentación geográfica/geografía recopilada en Adobe Analytics se transfiere a CJA a través del conector de datos de Analytics. Las implementaciones que no utilicen el conector de datos de Analytics, como las que dependen del SDK web de AEP para la recopilación de datos digitales, no tendrán la pizarra completa de búsquedas geográficas realizadas automáticamente (se admiten países y estados, ciudad y código postal no). |
| Canales de marketing | Los datos de los canales de marketing ahora fluyen a CJA a través de Analytics Data Connector. Las reglas del canal de marketing aún deben configurarse en Adobe Analytics tradicional. Algunas reglas no son compatibles. Para obtener más información, consulte la [documentación sobre canales de marketing de CJA](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=es#cja-usecases). |
| Variable de producto | Dentro de Experience Platform, los usuarios pueden utilizar una matriz de campos de tipo Objeto dentro de un esquema del conjunto de datos para satisfacer este caso práctico. Dentro de CJA, los clientes tienen la capacidad de usar cualquier número de variables de producto y no están restringidos a una sola variable como en Adobe Analytics. |
| Uso compartido de proyecto | El uso compartido de proyectos solo es compatible entre los usuarios de CJA; no existe el uso compartido de proyectos entre CJA y la versión tradicional de Analysis Workspace. |
| Visualizaciones | Todas las visualizaciones son compatibles, excepto la visualización de Mapa. |

## Compatibilidad parcial

| Función | Notas |
| --- | --- |
| Filtros de bots | Para conjuntos de datos basados en el Conector de datos de Analytics (ADC), se aplica el filtrado de bots. La lógica general de filtrado de bots para otros conjuntos de datos no es realizada por [!UICONTROL Experience Platform] o CJA. |
| Media Analytics | Los datos de medios están disponibles como parte de Analytics Data Connector. |
| eVars de comercialización | El comportamiento de los eVars de comercialización se puede lograr usando dimensiones dentro de una matriz de objetos, dado que un eVar de comercialización no está configurado para utilizar persistencia. Actualmente, la persistencia de la dimensión de comercialización no está disponible. |
| Paneles | El panel en blanco, el panel de atribución, el panel improvisado y las perspectivas rápidas son totalmente compatibles. No se admiten los paneles Comparación de segmentos, Analytics for Target (A4T) y Visores simultáneos de medios. |
| Reglas de procesamiento | En los conjuntos de datos basados en Analytics Data Connector, las reglas de procesamiento se aplican igual. Las [Funciones de preparación de datos de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=es) también se pueden usar como reemplazo de las reglas de procesamiento de datos que van directamente a Platform. |

## No compatible actualmente, pero planificado

| Función | Notas |
| --- | --- |
| Alertas | Se ha planificado lanzar una versión compatible. |
| Análisis de contribución | Se ha planificado lanzar una versión compatible. |
| Descarga de CSV | Se ha planificado lanzar una versión compatible. |
| Calendarios personalizados | Se ha planificado lanzar una versión compatible. |
| Creación de informes de Data Warehouse (100 % de exportación de filas) | La compatibilidad está planificada desde la interfaz de Analysis Workspace. El [!UICONTROL servicio de consulta de Experience Platform] también proporciona una interfaz para estos casos de uso en CJA. |
| Configuración de ID mediante Device Graph | Se ha planificado lanzar una versión compatible. |
| Anulación de duplicación métrica | Se ha planificado lanzar una versión compatible. |
| Persistencia de la variable de comercialización | Se ha planificado lanzar una versión compatible. |
| Informes en tiempo real | Se ha planificado lanzar una versión compatible. |
| Report Builder (complemento de Excel) | Se ha planificado lanzar una versión compatible. |
| IQ de segmento | Se ha planificado lanzar una versión compatible. |
| Publicación de segmentos (envío de segmentos de Workspace a Experience Cloud) | Se ha planificado lanzar una versión compatible. |

## Compatibilidad aún no planificada

| Función | Notas |
| --- | --- |
| Activity Map | Aún no se ha planificado lanzar una versión compatible. |
| Advertising Cloud | Aún no se ha planificado lanzar una versión compatible. |
| Clasificación del Generador de reglas | Aún no se ha planificado lanzar una versión compatible. |
| Archivo de fuentes de datos | Aún no se ha planificado lanzar una versión compatible. |
| Fuentes de datos de resumen | Aún no se ha planificado lanzar una versión compatible. |

## Nunca será compatible

* Métrica de personas que utiliza la cooperación entre dispositivos
* Paneles de Reports &amp; Analytics
* Marcadores de Reports &amp; Analytics
* Destinatarios de Reports &amp; Analytics
* Eventos del calendario de Reports &amp; Analytics
* Mobile Services
