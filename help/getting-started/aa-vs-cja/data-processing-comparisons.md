---
title: Comparar el procesamiento de datos entre las funciones de creación de informes de Adobe Analytics y Customer Journey Analytics
description: Comprender las diferencias en el procesamiento de datos para las distintas funciones de creación de informes
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
feature: Basics
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 64%

---

# Compare el procesamiento de datos entre Adobe Analytics y Customer Journey Analytics

A menudo necesita la capacidad de procesar datos antes de que sean útiles para la creación de informes. Puede procesar esos datos en varias etapas del recorrido, desde la recopilación de datos hasta la generación del informe o la visualización.

En Adobe Analytics, la mayor parte de ese procesamiento de datos se produce inmediatamente después de recopilarlos. Funcionalidades como reglas de VISTA, reglas de procesamiento y reglas de procesamiento de canales de marketing están disponibles para admitir este **procesamiento de tiempo de colección**.
A continuación, los datos se almacenan y, en el momento del informe, se puede aplicar un procesamiento adicional. Por ejemplo, desglose de dimensiones, aplicar la segmentación o seleccionar un modelo de atribución diferente. Este **procesamiento de tiempo del informe** sucede sobre la marcha.

En Adobe Analytics, el procesamiento de tiempo de los informes suele representar una cantidad de procesamiento menor que lo que sucede en el momento de la recopilación.

![Procesamiento de tiempo de colección de Adobe Analytics](../assets/aa-processing.png)

Por el contrario, Customer Journey Analytics está diseñado para requerir un procesamiento mínimo del tiempo de recopilación inicial antes de que los datos se organicen y almacenen. La arquitectura subyacente de Customer Journey Analytics está diseñada para trabajar con los datos almacenados en el momento del informe. Customer Journey Analytics ofrece su potente funcionalidad de procesamiento de tiempo de los informes no solo en Analysis Workspace. Funcionalidad de procesamiento de tiempo del informe adicional está disponible a través de la definición de [componentes](/help/data-views/component-settings/overview.md) y [campos derivados](/help/data-views/derived-fields/derived-fields.md) en sus vistas de datos.

![Customer Journey Analytics del procesamiento de tiempo del informe](../assets/cja-processing.png)

Comprender las diferencias en el procesamiento de datos para las distintas funciones de creación de informes puede ser útil para comprender qué métricas están disponibles, dónde y por qué pueden diferir.

Por ejemplo, *visitas* se define como una métrica en Adobe Analytics en el momento del procesamiento de datos. Y *sesiones* se calcula como una métrica en Customer Journey Analytics en el momento del informe. Como resultado, las dos métricas pueden diferir en función de las reglas para la definición de sesión en una vista de datos de Customer Journey Analytics.

Además, las visitas y sesiones como métrica no están disponibles en conjuntos de datos creados por el conector de origen de Analytics. Y, por lo tanto, requeriría que defina la sesión en la lógica de consulta para hacer comparaciones.

## Terminología {#terms}

La siguiente tabla define la terminología para los diferentes tipos de lógica de procesamiento que se aplican a Adobe Analytics y Customer Journey Analytics:

| Término | Definición | Notas |
| --- | --- | --- |
| Procesamiento de tiempo de colección | Lógica que se realiza cuando se procesan los datos, antes de almacenarse para fines de creación de informes y análisis. | Esta lógica está “incorporada” a los datos históricos y, por lo general, no se puede cambiar fácilmente. |
| Procesamiento de tiempo de informe | Lógica que se realiza en el momento de ejecutar un informe. | Esta lógica se puede aplicar a datos futuros e históricos durante el tiempo de ejecución del informe de forma no destructiva. |
| Lógica de nivel de éxito individual | Lógica aplicada en un nivel fila a fila. | Ejemplos: Reglas de procesamiento, VISTA, ciertas reglas de canal de marketing. |
| Lógica de nivel de visita | Lógica que se aplica en el nivel de visita. | Ejemplos: Visita y definición de sesión. |
| Lógica a nivel de visitante | Lógica que se aplica en el nivel de persona. | Ejemplo: Vinculación de personas entre dispositivos y canales. |
| Lógica del segmento | Evaluación de las reglas del segmento evento/visita/persona (evento/sesión/persona). | Ejemplo: Personas que compraron zapatos rojos. |
| Métricas calculadas | Evaluación de métricas personalizadas creadas por el cliente. Las métricas calculadas se pueden basar en fórmulas complejas, incluidos segmentos. | Por ejemplo, el número de personas que compraron zapatos rojos. |
| Lógica de atribución | Lógica para calcular la atribución. | Ejemplo: Persistencia del eVar. |
| Configuración de componentes | Aplicación de personalizaciones a métricas o dimensiones, como atribución, comportamiento, formato, etc | Ejemplo: agrupación de valores para combinar valores numéricos basados en un rango |
| Campos derivados | Lógica que se aplica a los campos de esquema o estándar como parte de la definición de componentes en una vista de datos. | Ejemplo: creación de una nueva dimensión de canal de marketing |

{style="table-layout:auto"}

Con el tiempo, Adobe Analytics y ahora Customer Journey Analytics han mejorado su flexibilidad al permitir que la lógica de datos de nivel de visita y persona se realice durante el tiempo de ejecución del informe.

## Tipos de procesamiento de datos {#types}

Los pasos de procesamiento de datos que realizan Adobe Analytics y Customer Journey Analytics y el tiempo que se debe pasar por estos pasos varían de una función a otra. La siguiente tabla proporciona un resumen de los tipos de procesamiento de datos para cada función y cuándo se aplica el procesamiento de datos.

| Funcionalidad | Se aplica en el tiempo del procesamiento | Se aplica en el tiempo del informe | No disponible | Notas |
| --- | --- | --- | --- | --- |
| [Informes de Adobe Analytics](https://experienceleague.adobe.com/es/docs/analytics)<br/>(sin incluir las funciones de atribución avanzadas ni los grupos de informes virtuales con procesamiento de tiempo de los informes) | <ul><li>[Reglas de procesamiento](https://experienceleague.adobe.com/es/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/c-processing-rules/processing-rules)</li><li>[Reglas de VISTA](https://experienceleague.adobe.com/es/docs/analytics/technotes/terms)</li><li>[Reglas de canal de marketing](https://experienceleague.adobe.com/es/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules) de nivel de éxito</li><li>Reglas de canal de marketing de nivel de visita (consulte la nota)</li><li>Definición de la visita</li><li>Lógica de atribución</li></ul> | <ul><li>Lógica del segmento</li><li>Métricas calculadas</li></ul> | <ul><li>Análisis entre dispositivos (consulte la nota)</li></ul> | <ul><li>Cross-Device Analytics requiere el uso de grupos de informes virtuales con procesamiento de tiempo de informes.</li><li>Las “reglas de canal de marketing de nivel de visita” incluyen: **Es la primera página de la visita**, **Anular canal de último toque** y **Caducidad del canal de marketing**. (Consulte la [documentación](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels).)</li></ul> |
| [Data Warehouse](https://experienceleague.adobe.com/es/docs/analytics/export/data-warehouse/data-warehouse) de Adobe Analytics | <ul><li>Reglas de procesamiento</li><li>Reglas de VISTA</li><li>Reglas de canal de marketing de nivel de éxito</li><li>Reglas de canal de marketing de nivel de visita</li><li>Definición de la visita</li><li>Lógica de atribución</li></ul> | <ul><li>Lógica del segmento</li></ul> | <ul><li>Métricas calculadas</li><li>Análisis entre dispositivos</li></ul> |     |
| [Fuentes de datos](https://experienceleague.adobe.com/es/docs/analytics/export/analytics-data-feed/data-feed-overview) de Adobe Analytics | <ul><li>Reglas de procesamiento</li><li>Reglas de VISTA</li><li>Reglas de canal de marketing de nivel de éxito</li><li>Reglas de canal de marketing de nivel de visita</li><li>Definición de visita (campo visitnum)</li><li>Lógica de atribución (en columnas posteriores)</li></ul> |   | <ul><li>Lógica del segmento</li><li>Métricas calculadas</li><li>Análisis entre dispositivos</li></ul> | <ul><li>Las asignaciones de ID para determinadas columnas relacionadas con los canales de marketing en fuentes de datos no se incluyen en las fuentes de datos. (Consulte la [documentación de fuentes de datos](https://experienceleague.adobe.com/es/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference)).</li></ul> |
| [Livestream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) de Adobe Analytics | <ul><li> Reglas de procesamiento</li><li>Reglas de VISTA</li><ul> |   | <ul><li>Reglas de canal de marketing de nivel de éxito</li><li>Reglas de canal de marketing de nivel de visita</li><li>Lógica de visita</li><li>Lógica de atribución</li><li>Lógica del segmento</li><li>Métricas calculadas</li><li>Análisis entre dispositivos</li></ul> |  |
| Adobe Analytics [Funciones de atribución avanzadas](https://experienceleague.adobe.com/es/docs/analytics/analyze/analysis-workspace/attribution/overview) | <ul><li>Reglas de procesamiento</li><li>Reglas de VISTA</li><li>Definición de la visita (consulte la nota)</li><li>Análisis entre dispositivos (consulte la nota)</li></ul> | <ul><li>Reglas de canal de marketing de nivel de éxito (consulte la nota)</li><li>Reglas de canal de marketing de visita (consulte la nota) Lógica de atribución</li><li>Lógica del segmento</li><li>Métricas calculadas</li></ul> |  | <ul><li>Cross-Device Analytics requiere el uso de grupos de informes virtuales con procesamiento de tiempo de informes.</li><li>Las funciones de atribución avanzadas de Core Analytics utilizan canales de marketing que se derivan completamente en el tiempo del informe (es decir, valores medios derivados).</li><li>Las funciones de atribución avanzadas utilizan una definición de visita en el tiempo del procesamiento excepto cuando se utilizan en un grupo de informes virtuales de procesamiento de tiempo de informes.</li></ul> |
| Grupos de informes virtuales de Adobe Analytics con [procesamiento de tiempo del informe](https://experienceleague.adobe.com/es/docs/analytics/components/virtual-report-suites/vrs-report-time-processing) | <ul><li>Reglas de procesamiento</li><li>Reglas de VISTA</li><li>[Análisis entre dispositivos](https://experienceleague.adobe.com/es/docs/analytics/components/cda/overview)</li></ul> | <ul><li>Definición de la visita</li><li>Lógica de atribución</li><li>Lógica del segmento</li><li>Métricas calculadas</li><li>Otra configuración de procesamiento de tiempo de informes de grupos de informes virtuales</li></ul> | <ul><li>Reglas de canal de marketing de nivel de éxito</li><li>Reglas de canal de marketing de nivel de visita</li></ul> | <ul><li>Consulte la [documentación](https://experienceleague.adobe.com/es/docs/analytics/components/virtual-report-suites/vrs-report-time-processing) acerca del procesamiento de tiempo de los informes de grupos de informes virtuales.</li></ul> |
| Conjunto de datos basado en el [conector de origen de Analytics](https://experienceleague.adobe.com/es/docs/experience-platform/sources/connectors/adobe-applications/analytics) en el lago de datos Adobe Experience Platform | <ul><li>Reglas de procesamiento</li><li>Reglas de VISTA</li><li>Reglas de canal de marketing de nivel de éxito</li><li>Vinculación basada en el campo (véase la nota)</li></ul> |   | <ul><li>[Reglas de canal de marketing de nivel de visita](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels)</li><li>Lógica de visita</li><li>Lógica de atribución</li><li>Lógica del segmento</li></ul> | <ul><li>Aplicar su propia lógica de segmento y métricas calculadas</li><li>La vinculación basada en campos crea un conjunto de datos vinculado independiente, además del creado por el conector de origen de Analytics.</li></ul> |
| Creación de informes de [Customer Journey Analytics](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-landing) | <ul><li>Se implementa como parte de la recopilación de datos de Adobe Experience Platform</li></ul> | <ul><li>Definición de sesión</li><li>Configuración de [vista de datos](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-dataviews/data-views)<li>Lógica de atribución</li><li>Métricas calculadas</li><li>Lógica del segmento</li></ul> | <ul><li>Reglas de canal de marketing de nivel de visita</li></ul> | <ul><li>Utilice conjuntos de datos enlazados para aprovechar el análisis entre canales.</li></ul> |

{style="table-layout:auto"}
