---
title: Compatibilidad con funciones de Análisis de viajes del cliente
description: Análisis del viaje del cliente en comparación con las funciones de Adobe Analytics establecidas.
translation-type: tm+mt
source-git-commit: 1d65b22ab2323bebf42b2782b2bab2ed52869a02

---


# Compatibilidad con funciones de Análisis de viajes del cliente

Las siguientes tablas muestran qué funciones de Adobe Analytics son compatibles, parcialmente compatibles o no lo son en el análisis de viajes del cliente (CJA). Estas listas cambiarán con el tiempo a medida que se añadan funciones a CJA.

## Funciones y componentes totalmente compatibles

| Función | Notas |
| --- | --- |
| Métricas | CJA aprovecha el modelo de datos de experiencia (XDM) y admite métricas ilimitadas y no está vinculado a los eventos de éxito personalizados de Analytics tradicional. Tenga en cuenta que algunas métricas estándar se han cambiado de nombre desde Analytics tradicional: Visitantes = Personas, Visitas = Sesiones, Visitas = Eventos. |
| Dimensiones | CJA aprovecha XDM y admite dimensiones ilimitadas y no está ligada a los eventos de éxito personalizados de Analytics tradicionales. |
| Variables de lista/Props de lista | CJA aprovecha XDM y admite variables de lista ilimitadas |
| Intervalos de fechas | Se ha planificado la compatibilidad con el calendario personalizado. |
| Métricas calculadas | Tenga en cuenta que las métricas de cálculo existentes en Analysis Workspace tradicional no se transferirán a CJA. |
| Segmentos | Ahora denominados &quot;Filtros&quot;: tenga en cuenta que los segmentos existentes en Analysis Workspace tradicional no se portarán a CJA. |
| Attribution IQ | Asistencia total |
| Revisión del proyecto | Asistencia total |
| Vinculación de proyectos | Asistencia total |
| Comparaciones de fechas | Asistencia total |
| Grupos de informes virtuales | Ahora se denomina Vistas [de datos](/help/data-views/create-dataview.md). |
| Revisión de componentes de VRS | Ahora forma parte de las vistas de datos. |
| Procesamiento de intervalo de tiempo | CJA se basa exclusivamente en Procesamiento de intervalo de tiempo. |
| Eliminación de GDPR | Tenga en cuenta que el RGPD ahora se gestiona en coordinación con Adobe Experience Platform: CJA hereda los cambios que la plataforma de experiencias realice en los conjuntos de datos subyacentes. |

## Admitido con advertencias

| Función | Notas |
| --- | --- |
| Variable de producto | La variable de producto actualmente disponible para la creación de informes de datos que se ajustan al esquema de eventos de experiencia (específicamente mediante el objeto productListItems). |
| Visualizaciones | Todas las visualizaciones son compatibles, excepto la visualización Mapa. |
| Audiencias de AAM | Si los clientes utilizan conjuntos de datos del conector de datos de Analytics, estos datos formarán parte de los datos de ADC. |
| Uso compartido de proyecto | El uso compartido de proyectos solo es compatible entre usuarios de CJA; no existe el uso compartido de proyectos entre CJA y Analysis Workspace tradicional. |
| Sesionización personalizada | Compatibilidad con todas las funciones de sesionización personalizadas que no sean visitas en segundo plano móviles. |
| Configuración de persistencia de eVar | Las eVars ya no forman parte de CJA. Sin embargo, la configuración de persistencia ahora forma parte de las vistas de datos y está disponible para todas las dimensiones. Tenga en cuenta que la persistencia se basa en el procesamiento del tiempo del informe, no en el procesamiento de la recopilación de datos. Esto significa que toda persistencia se basará en el intervalo de fechas del informe en lugar de en la totalidad de los datos. |
| Clasificaciones | Ahora denominados &quot;conjuntos de datos de búsqueda&quot;, no se importan automáticamente desde Analytics tradicional. Tendrán que ser subidos a AEP antes de que estén disponibles en CJA. |
| Atributos del cliente | Ahora denominados &quot;conjuntos de datos de perfil&quot;, no se importan automáticamente desde Experience Cloud, pero deberán cargarse en AEP antes de que estén disponibles en CJA. |

## Compatibilidad parcial

| Función | Notas |
| --- | --- |
| Dimensiones predeterminadas de Analysis Workspace (por ejemplo: Tipo de explorador, Tipo de referente, Canales de mercadotecnia, Número de visita, etc.) | CJA no proporciona estas dimensiones de forma nativa. Para los clientes que utilizan el conector de datos de Analytics (ADC), algunas de estas dimensiones están disponibles, pero no todas. Consulte nuestra [documentación sobre las variables de Analytics que se admiten a través de ADC](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Paneles | El panel en blanco, el panel de atribución y el panel improvisado son totalmente compatibles. No se admite la comparación de segmentos. |
| eVars de comercialización | Las eVars de comercialización solo funcionarán con conjuntos de datos basados en ADC a menos que se ajusten estrictamente al mismo esquema XDM (similar a las limitaciones de la lista de productos anteriores). |
| Filtro de bots | Para conjuntos de datos basados en el conector de datos de Analytics (ADC), se aplica el filtrado de bots. La lógica general de filtrado de bots para otros conjuntos de datos no la realiza la Plataforma de experiencia o CJA. |
| Reglas de procesamiento | Para los conjuntos de datos basados en ADC, las reglas de procesamiento siguen aplicándose. |
| Configuración de identidad entre dispositivos | Los clientes están limitados a puntos de datos &quot;únicos&quot; a través del servicio de consultas o deben aplicar esta lógica a los datos antes de la ingestión de datos de la plataforma de experiencias. |

## No compatible actualmente, pero planificado

| Función | Notas |
| --- | --- |
| Detección de anomalías | Se ha planificado la asistencia. |
| Análisis de contribución | Se ha planificado la asistencia. |
| IQ de segmento | Se ha planificado la asistencia. |
| Publicación de segmentos (envío de segmentos desde Workspace a Experience Cloud) | Se ha planificado la asistencia. |
| Permisos de usuario/Controles de acceso a datos | Todos los usuarios de CJA tienen los mismos controles de acceso, lo que significa que todos los usuarios tienen acceso a todas las conexiones, vistas de datos, etc. Básicamente, todos los usuarios son usuarios de nivel de administrador en CJA. Se prevé prestar apoyo para 2020. |
| Descarga de CSV | Se ha planificado la asistencia. |
| Informes y proyectos programados | Se ha planificado la asistencia. |
| Alertas | Se ha planificado la asistencia. |
| Calendarios personalizados | Se ha planificado la asistencia. |
| Canales de marketing | Se ha planificado la asistencia. |
| Exportación de PDF | Se ha planificado la asistencia. |
| Acceso a la API de informes | Se ha planificado la asistencia técnica: solo estará disponible con la API 2.0. |
| Configuración de ID mediante Device Graph | Se ha planificado la asistencia. |

## Asistencia aún no planificada

| Función | Notas |
| --- | --- |
| A4T | Aún no se ha planificado la asistencia. |
| Análisis de vídeo | Aún no se ha planificado la asistencia. |
| Advertising Cloud | Aún no se ha planificado la asistencia. |
| Creador de informes (complemento de Excel) | Aún no se ha planificado la asistencia. |
| Activity Map  | Aún no se ha planificado la asistencia. |
| Clasificación del Generador de reglas | Aún no se ha planificado la asistencia. |
| Fuentes de datos de resumen | Aún no se ha planificado la asistencia. |
| Informes en tiempo real | Aún no se ha planificado la asistencia. |

## Nunca se admitirá

| Función | Notas |
| --- | --- |
| Métrica Personas que utiliza la cooperación entre dispositivos |  |
| Tableros de informes y análisis |  |
| Marcadores de informes y análisis |  |
| Objetivos de informes y análisis |  |
| Eventos de calendario de informes y análisis |  |
| Ad Hoc Analysis |  |
| Data Warehouse Creación de informes | El servicio de consulta de la plataforma de experiencia de Adobe será la nueva interfaz para estos casos de uso en CJA. |
| Mobile Services |  |
| Archivo de fuentes de datos |  |
