---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 4c6578d500ccd86c9e64256aebb65e27de7896be
workflow-type: tm+mt
source-wordcount: '1108'
ht-degree: 47%

---

# Notas de la versión actuales de Adobe Customer Journey Analytics (junio de 2024)

**Última actualización**: miércoles, 18 de junio de 2024

Estas notas de la versión abarcan el periodo de lanzamiento del 6 de junio de 2024 a julio de 2024. Las versiones de Customer Journey Analytics operan en un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Asistente de IA para Customer Journey Analytics** | Permite realizar preguntas en lenguaje natural en la interfaz de usuario de Customer Journey Analytics y obtener respuestas basadas en la documentación de Customer Journey Analytics. [Más información](/help/ai-assistant.md) | | 6 de junio de 2024 |
| **Vinculación basada en gráficos: vinculación mediante la exportación de gráficos de UIS** | Mediante la vinculación basada en gráficos, puede utilizar el gráfico de identidad para obtener una mejor vista del recorrido del cliente mediante:<ul><li>Unir conjuntos de datos con diferentes identificadores sin tener que extraer, transformar ni cargar datos adicionales para reflejar un solo identificador.</li><li>Mejora de la cobertura de la identidad preferida o dorada para un único conjunto de datos compartiendo identidades entre conjuntos de datos.</li><li>Alineación de perfiles creados en Real-time Customer Data Platform y Journey Optimizer con personas de Customer Journey Analytics.</li></ul>(Vínculo a la documentación próximamente) |  | sábado, 28 de junio de 2024 |
| **Transformación de esquemas B2B para persona a cuenta** | Para admitir búsquedas basadas en personas en datos B2B (incluidas cuentas, oportunidades, listas de marketing y campañas), puede transformar los conjuntos de datos de búsqueda B2B. Esta transformación solo está disponible para conjuntos de datos con datos para esquemas de búsqueda B2B, según las siguientes clases:<ul><li>Relación de persona de cuenta empresarial de XDM</li><li>Relación de persona de oportunidad empresarial de XDM</li><li>Miembros de lista de marketing empresarial de XDM</li><li>Miembros de campaña empresarial de XDM</li></ul>[Más información](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/transform-datasets-b2b-lookups) |  | 5 de junio de 2024 |
| **Campos derivados: función matemática** | Permite hacer operadores matemáticos simples dentro de las vistas de datos para responder preguntas sobre los usuarios. Por ejemplo, puede combinar los ingresos de producto, garantía y envío. <p>[Más información](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields#math)</p> | | 5 de junio de 2024 |
| **Campos derivados: función siguiente o anterior** | Permite ver cuál es el valor siguiente o anterior. Por ejemplo, ¿cuáles eran los canales de marketing anteriores con los que interactuó alguien antes del canal de marketing seleccionado? O bien, ¿con qué interactuaban los usuarios antes o después de la página seleccionada? ¿Con qué interactúan los usuarios de canal más populares antes de entrar en la tienda? <p>[Más información](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields#next-or-previous)</p> | | 12 de junio de 2024 |
| **Campos derivados: función de resumen** | Proporciona la capacidad de aplicar funciones de tipo agregación a métricas o dimensiones en los niveles de evento, sesión y usuario. (Vínculo a la documentación próximamente) | | jueves, 26 de junio de 2024 |
| **Campos derivados: función de deduplicación** | Ayuda a evitar el recuento repetido de un valor. Se puede aplicar en el nivel de usuario o de sesión o en función del valor único de una dimensión. (Vínculo a la documentación próximamente) |  | jueves, 26 de junio de 2024 |
| **Priorización y latencia de la ingesta** | Ahora puede introducir los datos de eventos en Customer Journey Analytics en un plazo de 90 minutos (SLT), independientemente de si los datos tienen 24 horas, 48 horas o 7 días. Tenga en cuenta que esta capacidad difiere según el paquete de SKU que haya adquirido su empresa:<ul><li>Ingesta de prioridades de CJA básica: datos de 24 horas dentro del procesamiento SLT de 90 minutos (disponible para CJA Foundation y CJA Select)</li><li>Intermedio de ingesta de prioridades de CJA: datos de 72 horas de antigüedad dentro del procesamiento SLT de 90 minutos (disponible para CJA Prime)</li><li>Ingesta avanzada de prioridades de CJA: datos de una semana de antigüedad dentro del procesamiento SLT de 90 minutos (disponible para CJA Ultimate)</li></ul> |  | 12 de junio de 2024 |
| **Compartir cuentas y ubicaciones que se utilizan para exportar e importar** | Ahora, los usuarios pueden poner las cuentas y ubicaciones que creen a disposición de todos los usuarios de su organización. Solo los propietarios de cuentas y ubicaciones y los administradores del sistema pueden editar y eliminar cuentas y ubicaciones. Anteriormente, las cuentas y ubicaciones solo las podía usar el usuario que las creaba. Esta configuración está disponible cuando los usuarios [configuración de cuentas de exportación de cloud](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts) y [configuración de ubicaciones de exportación de cloud](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-locations). | 12 de junio de 2024 | Mediados de julio de 2024 |
| **Seleccionar varios campos en un filtro desplegable** | Cuando se añaden varios campos a un filtro desplegable, los usuarios ahora pueden seleccionar más de un campo a la vez. El panel se filtra para incluir cualquiera de los campos seleccionados. <p>Anteriormente, los usuarios solo podían seleccionar un campo a la vez en un filtro desplegable.</p><p>La opción para requerir una selección en un filtro desplegable se ha movido al menú al hacer clic con el botón derecho en un filtro desplegable.</p><p>Anteriormente, los usuarios podían hacer clic en la (x) junto a la opción Sin filtro en el menú desplegable.</p><p>Para obtener más información, consulte [Filtros desplegables estáticos](/help/analysis-workspace/c-panels/panels.md#static-drop-down-filters) in [Información general de paneles](/help/analysis-workspace/c-panels/panels.md).</p> |  | 19 de junio de 2024 |
| **Tabla de contenido de los proyectos de Workspace** | Ya está disponible una nueva tabla de contenido para los proyectos. La tabla de contenido proporciona vínculos que permiten a los usuarios moverse rápidamente entre paneles y visualizaciones dentro del proyecto. <p>La tabla de contenido está disponible en el carril izquierdo de todos los proyectos.</p><p>Para obtener más información, consulte [Tabla de contenido del proyecto](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md). |  | 19 de junio de 2024 |
| **Creación de hipervínculos para elementos de dimensión en una tabla de forma libre** | Puede crear hipervínculos para uno o varios elementos de dimensión a fin de que se pueda hacer clic en ellos dentro de una tabla de forma libre en Analysis Workspace. <p>Puede crear hipervínculos para elementos de dimensión que tengan valores de URL o puede crear URL personalizadas para elementos de dimensión que no tengan valores de URL.</p><p>Puede crear URL personalizadas dinámicas para varios elementos de dimensión mediante variables. Las variables pueden hacer referencia al valor de un elemento de dimensión o pueden hacer referencia a la dimensión de desglose.</p><p>Para obtener más información, consulte [Creación de hipervínculos para dimensiones en una tabla de forma libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md).</p> |  | 19 de junio de 2024 |
| **Uso de la vista de datos de Customer Journey Analytics con Adobe Journey Optimizer** | Una nueva opción de configuración en Customer Journey Analytics permite designar una vista de datos del Customer Journey Analytics para utilizarla con Adobe Journey Optimizer, sin necesidad de realizar una configuración manual. <p>Para obtener información sobre cómo habilitar esta opción de configuración, consulte la [Compatibilidad](/help/data-views/create-dataview.md#compatibility) sección en [Creación o edición de una vista de datos](/help/data-views/create-dataview.md).</p><p>Anteriormente, debía configurar manualmente una conexión y vistas de datos al ver datos de Journey Optimizer en Customer Journey Analytics.</p> |  | 19 de junio de 2024 |
| **Los púbicos se publican en una nueva sección “Públicos” en Experience Platform** | Los públicos publicados desde Customer Journey Analytics están ahora disponibles en la nueva sección “Públicos” de Experience Platform.<p>Anteriormente, los públicos publicados desde Customer Journey Analytics estaban disponibles en Experience Platform en la sección “Segmentos”.</p><p>Esta mejora ofrece las siguientes ventajas:</p><ul><li>Los públicos ya no tienen un retraso de 1 hora antes de aparecer en Experience Platform; están disponibles segundos tras su publicación.</li><li>Los públicos se pueden ordenar en Experience Platform mediante la columna “Origen”, que muestra la aplicación desde la que se publicó originalmente el público.</li><li>Las opciones de filtro y ordenación de Experience Platform le permiten encontrar más rápidamente los públicos relevantes.</li></ul> <p>(Vínculo a la documentación próximamente)</p> |  | lunes, 14 de julio de 2024 |

{style="table-layout:auto"}

## Correcciones en Customer Journey Analytics

AN-345454; AN-349816; AN-349905; AN-350617

## Avisos importantes para los administradores de Customer Journey Analytics

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| N/A | | |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de la versión anteriores de Customer Journey Analytics de 2024](/help/release-notes/2024.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
