---
title: Compatibilidad con funciones de Customer Journey Analytics
description: Customer Journey Analytics en comparación con las funciones de Adobe Analytics establecidas.
translation-type: tm+mt
source-git-commit: 9733d6471e6f1c886fd27b702654349d6760870c
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 97%

---


# Compatibilidad con funciones de Customer Journey Analytics

Las siguientes tablas detalla qué funciones de Adobe Analytics son compatibles, parcialmente o nada compatibles con Customer Journey Analytics (CJA). Estas listas cambiarán con el tiempo a medida que se añadan funciones a CJA.

## Funciones y componentes totalmente compatibles

| Función | Notas |
| --- | --- |
| Métricas | CJA aprovecha el Experience Data Model (XDM), admite métricas ilimitadas y no está vinculado a los eventos de éxito personalizados del Analytics tradicional. Tenga en cuenta que algunas métricas estándar han cambiado de nombre desde la versión tradicional de Analytics: Visitantes = Personas, Visitas = Sesiones, Visitas = Eventos. |
| Dimensiones | CJA aprovecha XDM, admite dimensiones ilimitadas y no está vinculado a los eventos de éxito personalizados del Analytics tradicional. |
| Variables de lista/Propiedades de lista | CJA aprovecha XDM y admite variables de lista ilimitadas. |
| Intervalos de fechas | Se ha planificado lanzar una versión compatible con el calendario personalizado. |
| Métricas calculadas | Tenga en cuenta que las métricas de cálculo existentes en la versión tradicional de Analysis Workspace no se transferirán a CJA. |
| Segmentos | Ahora se denominan &quot;Filtros&quot;: tenga en cuenta que los segmentos existentes en la versión tradicional de Analysis Workspace no se transferirán a CJA. |
| Detección de anomalías | Asistencia total a partir de septiembre de 2020 |
| Attribution IQ | Compatibilidad total. |
| Revisión del proyecto | Compatibilidad total. |
| Vinculación de proyectos | Compatibilidad total. |
| Comparaciones de fechas | Compatibilidad total. |
| Grupos de informes virtuales | Ahora se denomina [Vistas de datos](/help/data-views/create-dataview.md). |
| Revisión de componentes de VRS | Ahora forma parte de las Vistas de datos. |
| Procesamiento de intervalo de tiempo | CJA se basa exclusivamente en el procesamiento de intervalos del informe. |
| Eliminación de RGPD | Tenga en cuenta que el RGPD ahora se gestiona en coordinación con [!UICONTROL Experience Platform]: CJA hereda los cambios de datos que [!UICONTROL Experience Platform] haga en los conjuntos de datos subyacentes. |

## Admitido con advertencias

| Función | Notas |
| --- | --- |
| Variable de producto | La variable de producto actualmente disponible para el sistema de informes para los datos que se ajustan al esquema de Experience Event (específicamente mediante el objeto productListItems). |
| Visualizaciones | Todas las visualizaciones son compatibles, excepto la visualización de Mapa. |
| Audiencias de AAM | Si los clientes utilizan conjuntos de datos de [!UICONTROL Analytics Data Connector], estos datos formarán parte de los datos de ADC. |
| Uso compartido de proyecto | El uso compartido de proyectos solo es compatible entre los usuarios de CJA; no existe el uso compartido de proyectos entre CJA y la versión tradicional de Analysis Workspace. |
| Definición de sesiones personalizada | Compatibilidad con todas las funciones de definición de sesiones personalizada que no sean visitas en segundo plano móviles. |
| Configuración de persistencia de eVar | Las eVars ya no forman parte de CJA. Sin embargo, la configuración de persistencia ahora forma parte de las Vistas de datos y está disponible para todas las dimensiones. Tenga en cuenta que la persistencia se basa en el procesamiento de intervalos del informe, no en el procesamiento de la recopilación de datos. Esto significa que toda persistencia se basará en el intervalo de fechas del sistema de informes, no en la totalidad de los datos. |
| Clasificaciones | Ahora denominados &quot;conjuntos de datos de búsqueda&quot;, no se importan de manera automática desde la versión tradicional de Analytics. Tendrán que cargarse en AEP antes de que estén disponibles en CJA. |
| Atributos del cliente | Ahora denominados &quot;conjuntos de datos del Perfil&quot;, no se importan de manera automática desde Experience Cloud, pero deberán cargarse en AEP antes de que estén disponibles en CJA. |

## Compatibilidad parcial

| Función | Notas |
| --- | --- |
| Dimensiones predeterminadas del Analysis Workspace (por ejemplo: tipo de explorador, tipo de remitente del reenvío, canales de marketing, cantidad de visitas, etc.) | CJA no proporciona estas dimensiones de forma nativa. Para los clientes que utilizan el Analytics Data Connector (ADC), algunas de estas dimensiones están disponibles, pero no todas. Consulte nuestra [documentación sobre las variables de Analytics que se admiten a través de ADC](https://docs.adobe.com/content/help/es-ES/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Paneles | El panel en blanco, el panel de atribución, el panel improvisado y las perspectivas rápidas son totalmente compatibles. Los paneles Comparación de segmentos y Analytics para Target (A4T) no son compatibles. |
| eVars de comercialización | Las eVars de comercialización solo funcionarán con conjuntos de datos basados en ADC a menos que se ajusten estrictamente al mismo esquema de XDM (similar a las limitaciones de lista de productos anteriores). |
| Filtros de bots | Para conjuntos de datos basados en el Analytics Data Connector (ADC), se aplica el filtrado de bots. La lógica general de filtrado de bots para otros conjuntos de datos no es realizada por [!UICONTROL Experience Platform] o CJA. |
| Reglas de procesamiento | Para los conjuntos de datos basados en ADC, las reglas de procesamiento siguen aplicándose. |
| Configuración de identidad entre dispositivos | Los clientes se limitan a puntos &quot;únicos&quot; de datos a través del servicio de Consulta o deben aplicar esta lógica a los datos antes del ingreso de datos de [!UICONTROL Experience Platform]. |

## No compatible actualmente, pero planificado

| Función | Notas |
| --- | --- |
| Análisis de contribución | Se ha planificado lanzar una versión compatible. |
| IQ de segmento | Se ha planificado lanzar una versión compatible. |
| Publicación de segmentos (envío de segmentos de Workspace a Experience Cloud) | Se ha planificado lanzar una versión compatible. |
| Permisos de usuario/Controles de acceso de datos | Todos los usuarios de CJA tienen los mismos controles de acceso: esto significa que todos los usuarios tienen acceso a todas las conexiones, vistas de datos, etc. Básicamente, todos los usuarios son usuarios de nivel de administrador en CJA. Se prevé compatibilidad para 2020. |
| Descarga de CSV | Se ha planificado lanzar una versión compatible. |
| Informes y proyectos programados | Se ha planificado lanzar una versión compatible. |
| Alertas | Se ha planificado lanzar una versión compatible. |
| Calendarios personalizados | Se ha planificado lanzar una versión compatible. |
| Canales de marketing | Se ha planificado lanzar una versión compatible. |
| Exportación de PDF | Se ha planificado lanzar una versión compatible. |
| Acceso a la API de informes | Se ha planificado lanzar una versión compatible: solo estará disponible con la API 2.0. |
| Configuración de ID mediante Device Graph | Se ha planificado lanzar una versión compatible. |

## Compatibilidad aún no planificada

| Función | Notas |
| --- | --- |
| A4T | Aún no se ha planificado lanzar una versión compatible. |
| Media Analytics | Aún no se ha planificado lanzar una versión compatible. |
| Advertising Cloud | Aún no se ha planificado lanzar una versión compatible. |
| Report Builder (complemento de Excel) | Aún no se ha planificado lanzar una versión compatible. |
| Activity Map | Aún no se ha planificado lanzar una versión compatible. |
| Clasificación del Generador de reglas | Aún no se ha planificado lanzar una versión compatible. |
| Fuentes de datos de resumen | Aún no se ha planificado lanzar una versión compatible. |
| Informes en tiempo real | Aún no se ha planificado lanzar una versión compatible. |

## Nunca será compatible

* Métrica de personas que utiliza la cooperación entre dispositivos
* Paneles de Reports &amp; Analytics
* Marcadores de Reports &amp; Analytics
* Destinatarios de Reports &amp; Analytics
* Eventos del calendario de Reports &amp; Analytics
* Ad Hoc Analysis
* sistema de informes de Data Warehouse: [!UICONTROL Servicio de Consulta de Experience Platform] será la nueva interfaz para estos casos de uso en CJA.
* Mobile Services
* Archivo de fuentes de datos
