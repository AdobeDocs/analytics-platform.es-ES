---
title: Compatibilidad con funciones de Customer Journey Analytics
description: Customer Journey Analytics en comparación con las funciones de Adobe Analytics establecidas.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
translation-type: tm+mt
source-git-commit: 4b543a1566580a8f3060c2387928148d55be70f2
workflow-type: tm+mt
source-wordcount: '1037'
ht-degree: 99%

---

# Compatibilidad con funciones de Customer Journey Analytics

Las siguientes tablas detalla qué funciones de Adobe Analytics son compatibles, parcialmente o nada compatibles con Customer Journey Analytics (CJA). Estas listas cambiarán con el tiempo a medida que se añadan funciones a CJA.

## Funciones y componentes totalmente compatibles

| Función Adobe Analytics | Notas sobre asistencia |
| --- | --- |
| Métricas | CJA aprovecha el Experience Data Model (XDM), admite métricas ilimitadas y no está vinculado a los eventos de éxito personalizados del Analytics tradicional. Tenga en cuenta que algunas métricas estándar han cambiado de nombre desde la versión tradicional de Analytics: Visitantes = Personas, Visitas = Sesiones, Visitas = Eventos. |
| Dimensiones | CJA aprovecha XDM, admite dimensiones ilimitadas, y no se vincula con las variables de conversión y de tráfico personalizadas del software de Analytics tradicional. |
| Variables de lista/Propiedades de lista | CJA aprovecha XDM y admite matrices de cadenas ilimitadas que pueden utilizarse de manera similar a listVars. |
| Intervalos de fechas | Se ha planificado lanzar una versión compatible con el calendario personalizado. |
| Métricas calculadas | Tenga en cuenta que las métricas de cálculo existentes en la versión tradicional de Analysis Workspace no se transferirán a CJA. |
| Segmentos | Ahora se denominan &quot;Filtros&quot;: tenga en cuenta que los segmentos existentes en la versión tradicional de Analysis Workspace no se transferirán a CJA. |
| Detección de anomalías | Compatibilidad total. |
| Attribution IQ | Compatibilidad total. |
| Revisión del proyecto | Compatibilidad total. |
| Vinculación de proyectos | Compatibilidad total. |
| Comparaciones de fechas | Compatibilidad total. |
| Grupos de informes virtuales | Ahora se denomina [Vistas de datos](/help/data-views/create-dataview.md). |
| Revisión de componentes de VRS | Ahora forma parte de las Vistas de datos. |
| Procesamiento de intervalo de tiempo | CJA se basa exclusivamente en el procesamiento de intervalos del informe. |
| Eliminación de RGPD | Tenga en cuenta que el RGPD ahora se gestiona en coordinación con [!UICONTROL Adobe Experience Platform]: CJA hereda los cambios de datos que [!UICONTROL Experience Platform] haga en los conjuntos de datos subyacentes. |
| Permisos de usuario/Controles de acceso de datos | CJA distingue entre administradores de productos y usuarios de Adobe Admin Console. Solo los administradores de productos pueden: 1) crear, actualizar o eliminar conexiones o Vistas de datos, 2) actualizar o eliminar proyectos, filtros o métricas de cálculos creados por otros usuarios, y 3) compartir un proyecto de Workspace con todos los usuarios. |
| Vinculación entre dispositivos y canales | Consulte [Análisis entre canales](/help/connections/cca/overview.md). |
| Dimensiones de Analysis Workspace predeterminadas (por ejemplo: Tipo de explorador, Tipo de referente, Sistema operativo, etc.) | CJA proporciona estas dimensiones de forma nativa siempre y cuando se rellenen los campos XDM base (como agente de usuario o ID de dispositivo). Para los clientes que utilizan el Conector de datos de Analytics (ADC), algunas de estas dimensiones están disponibles, pero no todas. Consulte nuestra [documentación sobre las variables de Analytics que se admiten a través de ADC](https://docs.adobe.com/content/help/es-ES/experience-platform/ingestion/home.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Acceso a la API de informes | Ahora disponible mediante la [API de CJA](https://www.adobe.io/cja-apis/docs/). |
| Informes y proyectos programados | Compatibilidad total. |
| Exportación de PDF | Compatibilidad total. |

## Admitido con advertencias

| Función | Notas |
| --- | --- |
| Variable de producto | Dentro de Experience Platform, los usuarios pueden utilizar una matriz de campos de tipo Objeto dentro de un esquema del conjunto de datos para satisfacer este caso práctico. Dentro de CJA, los clientes tienen la capacidad de usar cualquier número de variables de producto y no están restringidos a una sola variable como en Adobe Analytics. |
| Canales de marketing | Los datos de los canales de marketing ahora fluyen a CJA a través de Analytics Data Connector. Las reglas del canal de marketing aún deben configurarse en Adobe Analytics tradicional. Algunas reglas no son compatibles. Para obtener más información, consulte la [documentación sobre canales de marketing de CJA](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=es#cja-usecases). |
| Visualizaciones | Todas las visualizaciones son compatibles, excepto la visualización de Mapa. |
| Uso compartido de proyecto | El uso compartido de proyectos solo es compatible entre los usuarios de CJA; no existe el uso compartido de proyectos entre CJA y la versión tradicional de Analysis Workspace. |
| Definición de sesiones personalizada | Compatibilidad con todas las funciones de definición de sesiones personalizada que no sean visitas en segundo plano móviles. |
| Configuración de persistencia de eVar | Las eVars ya no forman parte de CJA. Sin embargo, la configuración de persistencia ahora forma parte de las Vistas de datos y está disponible para todas las dimensiones. Tenga en cuenta que la persistencia se basa en el procesamiento de intervalos del informe, no en el procesamiento de la recopilación de datos. Las dimensiones configuradas en Vistas de datos se limitan a una persistencia máxima de 90 días y no admiten persistencia ilimitada. |
| Clasificaciones | Ahora se denomina Conjuntos de datos de búsqueda. Las clasificaciones utilizadas en Analytics se pueden importar a Experience Platform y a CJA mediante el Classifications Data Connector de Analytics. Los conjuntos de datos de búsqueda también se pueden cargar directamente en AEP y estar disponibles en CJA. |
| Atributos del cliente | Ahora denominados &quot;conjuntos de datos del Perfil&quot;, no se importan de manera automática desde Experience Cloud, pero deberán cargarse en AEP antes de que estén disponibles en CJA. |
| Dimensiones de dispositivo, explorador y tecnología | Estas dimensiones se incluyen automáticamente cuando un conjunto de datos de AEP incluye campos de esquema XDM específicos y se ajusta a la clase de evento de Experience XDM. |
| Métricas y dimensiones de entradas, salidas y tiempo transcurrido | Todas estas son ahora compatibles (las entradas y salidas ahora se denominan inicios de sesión y fines de sesión) y se calculan de forma ligeramente distinta. |

## Compatibilidad parcial

| Función | Notas |
| --- | --- |
| Paneles | El panel en blanco, el panel de atribución, el panel improvisado y las perspectivas rápidas son totalmente compatibles. No se admiten los paneles Comparación de segmentos, Analytics for Target (A4T) y Visores simultáneos de medios. |
| eVars de comercialización | El comportamiento de los eVars de comercialización se puede lograr usando dimensiones dentro de una matriz de objetos, dado que un eVar de comercialización no está configurado para utilizar persistencia. Actualmente, la persistencia de la dimensión de comercialización no está disponible. |
| Filtros de bots | Para conjuntos de datos basados en el Conector de datos de Analytics (ADC), se aplica el filtrado de bots. La lógica general de filtrado de bots para otros conjuntos de datos no es realizada por [!UICONTROL Experience Platform] o CJA. |
| Reglas de procesamiento | En los conjuntos de datos basados en Analytics Data Connector, las reglas de procesamiento se aplican igual. |
| Media Analytics | Los datos de medios están disponibles como parte de Analytics Data Connector. |

## No compatible actualmente, pero planificado

| Función | Notas |
| --- | --- |
| Análisis de contribución | Se ha planificado lanzar una versión compatible. |
| IQ de segmento | Se ha planificado lanzar una versión compatible. |
| Publicación de segmentos (envío de segmentos de Workspace a Experience Cloud) | Se ha planificado lanzar una versión compatible. |
| Descarga de CSV | Se ha planificado lanzar una versión compatible. |
| Calendarios personalizados | Se ha planificado lanzar una versión compatible. |
| Anulación de duplicación métrica | Se ha planificado lanzar una versión compatible. |
| Persistencia de la variable de comercialización | Se ha planificado lanzar una versión compatible. |
| Alertas | Se ha planificado lanzar una versión compatible. |
| Configuración de ID mediante Device Graph | Se ha planificado lanzar una versión compatible. |
| Report Builder (complemento de Excel) | Se ha planificado lanzar una versión compatible. |
| Informes en tiempo real | Se ha planificado lanzar una versión compatible. |
| Creación de informes de Data Warehouse (100 % de exportación de filas) | La compatibilidad está planificada desde la interfaz de Analysis Workspace. El [!UICONTROL servicio de consulta de Experience Platform] también proporciona una interfaz para estos casos de uso en CJA. |

## Compatibilidad aún no planificada

| Función | Notas |
| --- | --- |
| A4T | Aún no se ha planificado lanzar una versión compatible. |
| Advertising Cloud | Aún no se ha planificado lanzar una versión compatible. |
| Activity Map | Aún no se ha planificado lanzar una versión compatible. |
| Clasificación del Generador de reglas | Aún no se ha planificado lanzar una versión compatible. |
| Fuentes de datos de resumen | Aún no se ha planificado lanzar una versión compatible. |
| Archivo de fuentes de datos | Aún no se ha planificado lanzar una versión compatible. |

## Nunca será compatible

* Métrica de personas que utiliza la cooperación entre dispositivos
* Paneles de Reports &amp; Analytics
* Marcadores de Reports &amp; Analytics
* Destinatarios de Reports &amp; Analytics
* Eventos del calendario de Reports &amp; Analytics
* Mobile Services
