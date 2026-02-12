---
title: Notas de la versión de Customer Journey Analytics actuales
description: Visualización de las notas de la última versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 5107f1a3e602afbb1536e7832a060c70aa898966
workflow-type: tm+mt
source-wordcount: '1192'
ht-degree: 32%

---

# Notas de la versión actuales de Customer Journey Analytics (febrero de 2026)

**Última actualización**: viernes, 12 de febrero de 2026

Estas notas de la versión abarcan el período de la versión de febrero de 2026. Las versiones de Adobe Customer Journey Analytics operan en un [modelo de entrega continua](releases.md), que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ------- | ---- |
| **Anulaciones de encabezado** <p>Puede especificar un nombre de encabezado y un valor de encabezado secreto en Content Analytics. Este [encabezado anula la configuración](/help/content-analytics/config/guided.md#header-overrides) y garantiza que Content Analytics enviará encabezados HTTP personalizados para evitar la detección de bots o las tecnologías de tráfico de puerta que haya implementado.</p> |  | martes, 02 de febrero de 2026 |
| **Incluir varias columnas de dimensión en una tabla de forma libre**<p>Ahora puede incluir hasta 5 columnas de dimensión en una tabla de forma libre, lo que le permite ver varios elementos de dimensión en paralelo. Cada fila de elementos de dimensión se comporta como un solo elemento de dimensión concatenado.</p><p>Puede aplicar filtros, clasificaciones, desgloses y mucho más a las tablas de forma libre con varias columnas de dimensión para crear un análisis más profundo y personalizado.</p><p>Anteriormente, solo se podía incluir 1 columna de dimensión en una tabla de forma libre.</p><p>Para obtener más información, vea [Incluir varias columnas de dimensión en una tabla de forma libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md).</p> | jueves, 28 de enero de 2026 | jueves, 18 de febrero de 2026 |
| **Ordenar tablas por varias columnas**<p>Ahora puede ordenar los datos de una tabla de forma libre por varias columnas en Analysis Workspace, ya sean dimensiones o métricas.</p><p>Al ordenar los datos de varias columnas, los datos se ordenan según la prioridad asignada a cada columna. La numeración de prioridad se muestra junto al icono de ordenación.</p><p>Para obtener más información, consulte [Filtrar y ordenar tablas de forma libre](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).</p> | jueves, 28 de enero de 2026 | jueves, 18 de febrero de 2026 |
| **Mejoras en la exportación de tabla completa**<p>La exportación de tabla completa incluye las siguientes mejoras:</p><p>Exportar mejoras de creación y configuración</p><ul><li>Cree una exportación desde la página Exportaciones. Anteriormente, solo se podía crear una exportación desde Analysis Workspace haciendo clic con el botón derecho en la tabla.</li><li>Añada una nueva cuenta o ubicación al crear una exportación.</li><li>Automatice la creación de nombres de archivo y la ubicación de carpetas de archivos exportados. Esto permite que los nombres de archivo sean predecibles y se organicen en carpetas de una manera lógica. Anteriormente, los nombres de archivo eran impredecibles y se agrupaban en una sola carpeta.</li><li>Compatibilidad con la exportación de datos como archivos de Parquet para mejorar la compatibilidad con Data Warehouse. Anteriormente, solo se admitían CSV y JSON.</li></ul><p>Mejoras en la administración de exportaciones</p><ul><li>Renovar o cancelar una o varias exportaciones de la página Exportaciones.</li><li>Vuelva a enviar una o varias exportaciones desde la página Registros.</li><li>Enviar un correo electrónico a usuarios o grupos individuales cuando una exportación falle o esté a punto de caducar.</li><li>Mensajes de error más precisos para exportaciones fallidas.</li></ul><p>Mejoras de métricas, segmentos y dimensiones calculadas</p><ul><li>Compatibilidad con funciones de métricas más calculadas. Anteriormente, solo se admitían funciones matemáticas simples.</li><li>Aplique segmentos al crear una exportación.</li><li>Compatibilidad con dimensiones de tipo de datos dobles para mejorar la precisión.</li></ul><p>Mejoras administrativas</p><ul><li>Los administradores ahora pueden ver todas las exportaciones y registros, independientemente de quién los haya creado.</li></ul><p>(Vínculo a la documentación a continuación).</p> | jueves, 25 de febrero de 2026 | jueves, 11 de marzo de 2026<p>(Originalmente planificado para el 4 de marzo de 2026)</p> |
| **Content Analytics: vistas previas y miniaturas de visualización de dispersión** <p>Cuando se visualiza una visualización de dispersión en Content Analytics, ahora se muestra una miniatura del recurso al pasar el ratón por encima de un punto del gráfico. Esta miniatura le permite ver rápida y fácilmente qué contenido se representa en el gráfico.</p><p>(Vínculo a la documentación a continuación).</p> | miércoles, 17 de febrero de 2026 | martes, 02 de marzo de 2026 |
| **Content Analytics: miniaturas y vistas previas de visualización de barras** <p>Cuando se visualiza una visualización de barras horizontales en Content Analytics, ahora se muestra una miniatura del recurso al pasar el ratón por encima de una barra del gráfico. Esta miniatura le permite ver rápida y fácilmente qué contenido se representa en el gráfico.</p><p>(Vínculo a la documentación a continuación).</p> | martes, 23 de febrero de 2026 | martes, 09 de marzo de 2026 |
| **Actualizar a la función Recuento distinto aproximado**<p>El algoritmo probabilístico HLL utilizado en la función Approximate Distinct se actualizará pronto. La salida resultante para números que utilizan esta función puede cambiar ligeramente con respecto a los números históricos, de la siguiente manera:<ul><li>Al contar cantidades muy pequeñas de valores únicos, los resultados se mejorarán para utilizar recuentos exactos en lugar de utilizar estimaciones.</li><li>Al contar cualquier cosa más grande, las estimaciones de recuento conservarán la misma precisión que antes de esta actualización (las estimaciones son precisas dentro del 5 por ciento del número exacto, el 95 por ciento del tiempo).</li></ul><p>Para obtener más información sobre la función Approximate Count Distinct, vea [Approximate Count Distinct](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct) en [Funciones avanzadas](/help/components/calc-metrics/cm-adv-functions.md)</p> |  | Marzo de 2026 |
| **Compatibilidad con Data Mirror**  <p>Con la compatibilidad con los esquemas basados en modelos y la funcionalidad de captura de datos modificados (CDC) para conectores de origen específicos en Experience Platform, Customer Journey Analytics podrá admitir la funcionalidad de [duplicación de datos](/help/data-mirror/data-mirror.md) de soluciones de almacenamiento de datos como [!DNL Snowflake], [!DNL Azure Databricks] y [!DNL Google BigQuery].</p><p>Póngase en contacto con el equipo de cuentas de Adobe para acceder a Beta.</p> | Lanzamiento de la versión beta: 24 de septiembre de 2025. | Por determinar |
| **Servicios de medios de streaming: compatibilidad con datos de programación** <p>Ahora puede cargar datos de programación del contenido de medios de streaming en directo anterior para rastrear la audiencia de forma más fácil y precisa.</p><p>Los siguientes son ejemplos de contenidos en directo compatibles con la carga de datos de programación:</p><ul><li>Plataformas FAST (Free Ad Supported TV)</li><li>Streams locales</li><li>Deportes en directo</li></ul><p>La carga de datos de programación le permite realizar un seguimiento de los datos del número de espectadores de los programas individuales que se emitieron durante el tiempo designado en el archivo de carga. Incluso puede recopilar datos del número de espectadores de temas específicos o segmentos de programa.</p><p>Estas funciones están disponibles independientemente de cómo haya implementado la recopilación de medios de streaming.</p><p>Anteriormente, era difícil vincular con precisión una sesión determinada a programas específicos cuando se analizaba contenido en directo, y no era posible vincular una sesión determinada a temas o segmentos de programa individuales.</p><p>Para obtener más información, consulte [Cargar datos de programación para realizar un seguimiento del contenido en directo](https://experienceleague.adobe.com/es/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 de octubre de 2025 | Primer semestre de 2026<p>(Originalmente planificado para su lanzamiento el 29 de octubre de 2025)</p> |
| **Combinar grupos de informes de varias organizaciones de IMS**<p>Puede utilizar el conector de Source de Analytics para combinar grupos de informes de varias organizaciones de IMS. Esta característica de asignación de datos de [IMS cruzado](/help/getting-started/aa-vs-cja/mapping-data-ims-orgs.md) permite que las organizaciones tengan una vista combinada de los datos de sus clientes, incluso cuando esos datos de clientes se distribuyen en varias organizaciones IMS. <p>**Nota:** Esta configuración solo está disponible al enviar una solicitud al Servicio de atención al cliente de Adobe.</p> |  | viernes, 12 de febrero de 2026 |

## Correcciones en Customer Journey Analytics

**Analysis Workspace**: AN-421930, AN-424997, AN-424194, AN-425515, AN-425254, AN-423174, AN-428834, AN-306540, AN-426014, AN-427801
**Componentes**:
**Content Analytics**:
**Análisis guiado**:
**Exportaciones**: AN-422041, AN-421599, AN-422112
**Vistas de datos**:
**Implementación**:
**Report Builder**: AN-391415, AN-425125
**Informes**: AN-425817, AN-424362, AN-425752, AN-425278, AN-422249, AN-403446, AN-424727, AN-426791, AN-427985
**Segmentación**: AN-428905, AN-428232
**Informes programados**: AN-425484, AN-425137
**Métricas y dimensiones compartidas**:
**Otros**: AN-428833, AN-425074


## Avisos importantes para los administradores de Customer Journey Analytics

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| **Eliminación de grupos de cifrado TLS 1.2** | jueves, 11 de febrero de 2026 | Aviso a los administradores: Adobe planea eliminar la compatibilidad con los siguientes grupos de cifrados TLS 1.2 de los servidores de recopilación de datos de Adobe el 27 de mayo de 2026.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li></ul><p>No se requiere ninguna acción del cliente para la mayoría de las implementaciones. Este cambio afecta principalmente a los datos de Analytics enviados desde aplicaciones nativas heredadas que utilizan bibliotecas TLS obsoletas, y a un pequeño número de visitantes web en navegadores o sistemas operativos obsoletos. Al eliminar la compatibilidad con estos grupos de cifrado, se mejora la seguridad y se alinea Adobe con los estándares de cifrado modernos. Actualmente, menos del 0,1 % del tráfico de recopilación de datos depende de estos grupos de cifrado.</p> |

## Recursos relacionados

* [Notas de la versión anteriores de Customer Journey Analytics de 2025](/help/release-notes/2025.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión de la colección de medios de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
