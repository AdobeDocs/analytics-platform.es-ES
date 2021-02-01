---
title: Compatibilidad con funciones de Customer Journey Analytics
description: Customer Journey Analytics en comparación con las funciones de Adobe Analytics establecidas.
translation-type: tm+mt
source-git-commit: b77165ee5994ec59e346cf6314a7e051ffa07524
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 76%

---


# Compatibilidad con funciones de Customer Journey Analytics

Las siguientes tablas detalla qué funciones de Adobe Analytics son compatibles, parcialmente o nada compatibles con Customer Journey Analytics (CJA). Estas listas cambiarán con el tiempo a medida que se añadan funciones a CJA.

## Funciones y componentes totalmente compatibles

| Función Adobe Analytics | Notas |
| --- | --- |
| Métricas | CJA aprovecha el Experience Data Model (XDM), admite métricas ilimitadas y no está vinculado a los eventos de éxito personalizados del Analytics tradicional. Tenga en cuenta que algunas métricas estándar han cambiado de nombre desde la versión tradicional de Analytics: Visitantes = Personas, Visitas = Sesiones, Visitas = Eventos. |
| Dimensiones | CJA aprovecha XDM, admite dimensiones ilimitadas y no está vinculado a los eventos de éxito personalizados del Analytics tradicional. |
| Variables de lista/Propiedades de lista | CJA aprovecha XDM y admite variables de lista ilimitadas. |
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
| Eliminación de RGPD | Tenga en cuenta que el RGPD ahora se maneja en coordinación con [!UICONTROL Adobe Experience Platform]: CJA hereda los cambios de datos que [!UICONTROL Experience Platform] realiza en los datasets subyacentes. |
| Permisos de usuario/Controles de acceso de datos | CJA distingue entre administradores de productos y usuarios de Adobe Admin Console. Solo los administradores de productos pueden: 1) crear, actualizar o eliminar conexiones o Vistas de datos, 2) actualizar o eliminar proyectos, filtros o métricas de cálculos creados por otros usuarios, y 3) compartir un proyecto de Workspace con todos los usuarios. |
| Colisión entre dispositivos y canales | Consulte [Análisis de Canales cruzados](/help/connections/cca/overview.md). |
| Dimensiones de Analysis Workspace predeterminadas (por ejemplo: Tipo de explorador, Tipo de Remitente del reenvío, Sistema operativo, etc.) | CJA proporciona estas dimensiones de forma nativa siempre y cuando se rellenen los campos XDM base (como agente de usuario o ID de dispositivo). Para los clientes que utilizan el Conector de datos de Analytics (ADC), algunas de estas dimensiones están disponibles, pero no todas. Consulte nuestra [documentación sobre las variables de Analytics que se admiten a través de ADC](https://docs.adobe.com/content/help/es-ES/experience-platform/ingestion/home.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Acceso a la API de informes | Actualmente disponible mediante la API de Analytics 2.0. |

## Admitido con advertencias

| Función | Notas |
| --- | --- |
| Variable de producto | Dentro del Experience Platform, los usuarios pueden utilizar una matriz de campos de tipo Objeto dentro de un esquema de conjunto de datos para satisfacer este caso de uso. Dentro de CJA, los clientes tienen la capacidad de usar cualquier número de variables de producto y no están restringidos a una sola variable como en Adobe Analytics. |
| Canales de marketing | Los datos de Canales de marketing fluyen a CJA a través del conector de datos de Analytics. Las reglas del canal de marketing aún deben configurarse en Adobe Analytics tradicional. Algunas reglas no son compatibles. Para obtener más información, consulte la [documentación sobre canales de marketing de CJA](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=es-ES#cja-usecases). |
| Visualizaciones | Todas las visualizaciones son compatibles, excepto la visualización de Mapa. |
| Uso compartido de proyecto | El uso compartido de proyectos solo es compatible entre los usuarios de CJA; no existe el uso compartido de proyectos entre CJA y la versión tradicional de Analysis Workspace. |
| Definición de sesiones personalizada | Compatibilidad con todas las funciones de definición de sesiones personalizada que no sean visitas en segundo plano móviles. |
| Configuración de persistencia de eVar | Las eVars ya no forman parte de CJA. Sin embargo, la configuración de persistencia ahora forma parte de las Vistas de datos y está disponible para todas las dimensiones. Tenga en cuenta que la persistencia se basa en el procesamiento de intervalos del informe, no en el procesamiento de la recopilación de datos. Los Dimension configurados en Vistas de datos se limitan a una persistencia máxima de 90 días y no admiten persistencia ilimitada. |
| Clasificaciones | Ahora se denomina &quot;Conjuntos de datos de búsqueda&quot;. Las clasificaciones utilizadas en Analytics se pueden importar al Experience Platform y a CJA mediante el conector de datos de clasificaciones de Analytics. Los conjuntos de datos de búsqueda también se pueden cargar directamente a AEP y estar disponibles en CJA. |
| Atributos del cliente | Ahora denominados &quot;conjuntos de datos del Perfil&quot;, no se importan de manera automática desde Experience Cloud, pero deberán cargarse en AEP antes de que estén disponibles en CJA. |
| Dimensiones de dispositivo, explorador y tecnología | Estas dimensiones se incluyen automáticamente cuando un conjunto de datos de AEP incluye campos de esquema XDM específicos y se ajusta a la clase de evento de Experience XDM. |
| Métricas y dimensiones de entradas, salidas y tiempo transcurrido | Todas estas son ahora compatibles (las entradas y salidas ahora se denominan inicios de sesión y fines de sesión) y se calculan de forma ligeramente distinta. |

## Compatibilidad parcial

| Función | Notas |
| --- | --- |
| Paneles | El panel en blanco, el panel de atribución, el panel improvisado y las perspectivas rápidas son totalmente compatibles. No se admiten los paneles Comparación de segmentos, Analytics para Target (A4T) y Visores simultáneos de medios. |
| eVars de comercialización | El comportamiento de las eVars de comercialización se puede lograr usando dimensiones dentro de una matriz de objetos, dado que un eVar de comercialización no está configurado para utilizar persistencia. Actualmente, la persistencia de la dimensión de comercialización no está disponible. |
| Filtros de bots | Para conjuntos de datos basados en el Conector de datos de Analytics (ADC), se aplica el filtrado de bots. La lógica general de filtrado de bots para otros conjuntos de datos no es realizada por [!UICONTROL Experience Platform] o CJA. |
| Reglas de procesamiento | En los conjuntos de datos basados en el conector de datos de Analytics, las reglas de procesamiento siguen aplicándose. |
| Media Analytics | Los datos de medios están disponibles como parte del conector de datos de Analytics. |

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
| Informes y proyectos programados | Se ha planificado lanzar una versión compatible. |
| Alertas | Se ha planificado lanzar una versión compatible. |
| Exportación de PDF | Se ha planificado lanzar una versión compatible. |
| Configuración de ID mediante Device Graph | Se ha planificado lanzar una versión compatible. |
| Report Builder (complemento de Excel) | Se ha planificado lanzar una versión compatible. |
| Informes en tiempo real | Se ha planificado lanzar una versión compatible. |

## Compatibilidad aún no planificada.

| Función | Notas |
| --- | --- |
| A4T | Aún no se ha planificado lanzar una versión compatible. |
| Advertising Cloud | Aún no se ha planificado lanzar una versión compatible. |
| Activity Map | Aún no se ha planificado lanzar una versión compatible. |
| Clasificación del Generador de reglas | Aún no se ha planificado lanzar una versión compatible. |
| Fuentes de datos de resumen | Aún no se ha planificado lanzar una versión compatible. |

## Nunca será compatible

* Métrica de personas que utiliza la cooperación entre dispositivos
* Paneles de Reports &amp; Analytics
* Marcadores de Reports &amp; Analytics
* Destinatarios de Reports &amp; Analytics
* Eventos del calendario de Reports &amp; Analytics
* Ad Hoc Analysis
* Informes de Data Warehouse - El [!UICONTROL Query Service de Experience Platform] será la nueva interfaz para estos casos de uso en CJA.
* Mobile Services
* Archivo de fuentes de datos
