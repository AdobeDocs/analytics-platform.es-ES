---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 86b411ac28aaa78914c6f105af2716e1b3a4150c
workflow-type: tm+mt
source-wordcount: '1065'
ht-degree: 67%

---

# Notas de la versión de Customer Journey Analytics (CJA) actuales (junio de 2023)

**Última actualización**: 6 de junio de 2023

Las versiones de Customer Journey Analytics operan en un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Elementos destacados de la versión {#highlights}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Pies de ilustración inteligentes** | Enriquezca la narración para los usuarios con resúmenes de un lenguaje natural [!UICONTROL Línea] visualización. [Más información](/help/analysis-workspace/visualizations/intelligent-captions.md) | 17 de mayo de 2023 | 1 de junio de 2023 |
| **Uso compartido de vínculos para proyectos (no se requiere inicio de sesión)** | Ahora puede compartir vínculos de solo lectura a proyectos de Analysis Workspace con personas que no tienen acceso a Adobe Analytics. Esto incluye compartir con personas fuera de su organización o con personas de su organización que no estén aprovisionadas para Adobe Analytics. [Más información](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=es#share-public-link) <p>Esta funcionalidad está habilitada de forma predeterminada y el administrador del sistema puede inhabilitarla. [Más información](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=es#company-preferences)</p> | 3 de mayo de 2023 | 6 de junio de 2023 |
| **Campos derivados** | Representa la versión inicial de los campos Derivados. Un campo derivado permite definir manipulaciones de datos (a menudo complejas) sobre la marcha, mediante un generador de reglas personalizable. Puede definir el campo derivado como componente (métrica o dimensión) en las vistas de datos y, a continuación, utilizar el campo derivado como componente en Workspace.<p>Esta versión es compatible con una plantilla de canales de marketing y las siguientes funciones:</p><ul><li>Concatenar</li><li>Caso de que</li><li>Buscar y reemplazar</li><li>Búsqueda</li><li>Análisis de URL</li></ul> <p>[Más información](/help/data-views/derived-fields/derived-fields.md)</p> | 10 de mayo de 2023 | 21 de junio de 2023 |
| **Acceso de PowerBI y Tableau a las vistas de datos de CJA** | El conector SQL del Customer Journey Analytics (CJA) habilita el acceso SQL a las vistas de datos que ha definido en CJA. Los ingenieros y analistas de datos más familiarizados con Power BI, Tableau u otras herramientas de inteligencia y visualización empresarial ahora pueden crear informes y paneles basados en las mismas vistas de datos que los usuarios de CJA utilizan para sus proyectos de Analysis Workspace. [Más información](/help/data-views/sql-connector.md) |  | 30 de junio de 2023 |
| **Búsquedas geográficas de Experience Edge** | Podrá crear informes utilizando los datos de geolocalización en CJA una vez que las búsquedas geográficas de Experience Edge estén habilitadas para su conjunto de datos. |  | 30 de junio de 2023 |
| **Compatibilidad de búsqueda ampliada para datos de perfil y búsqueda** | Podrá agregar conjuntos de datos de búsqueda no solo a conjuntos de datos de evento, sino también a conjuntos de datos de perfil y búsqueda. | 21 de junio de 2023 | 12 de julio de 2023 |
| **Compatibilidad con la conversión de moneda** | CJA admitirá la conversión de moneda como parte del formato de un componente de métrica en una vista de datos. | 21 de junio de 2023 | 19 de julio de 2023 |

{style="table-layout:auto"}

## Otras nuevas funciones o actualizaciones {#other-new}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Vistas de datos de Adobe Journey Optimizer** | Los administradores de CJA tienen acceso a algunas vistas de datos adicionales en CJA, tituladas &quot;Vista de datos de AJO (nombre de zona protegida)&quot;. Estas vistas de datos se utilizan para activar los informes en Adobe Journey Optimizer (AJO). También pueden utilizarse para realizar un análisis más profundo de las actividades de AJO en CJA. [Más información](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html). |  | 25 de mayo de 2023 |
| **Relleno para zonas protegidas que no sean de producción** | Al crear un flujo de datos del conector de origen de Analytics en una zona protegida que no sea de producción, el relleno de las zonas protegidas que no sean de producción estará limitado a 3 meses. Permanecerá a los 13 meses para las zonas protegidas de producción. | N/A | 26 de abril de 2023 |
| **Uso compartido de vínculos para proyectos (no se requiere inicio de sesión)** | Ahora puede compartir vínculos de solo lectura a proyectos de Analysis Workspace con personas que no tienen acceso a Adobe Analytics. Esto incluye compartir con personas fuera de su organización o con personas de su organización que no estén aprovisionadas para Adobe Analytics. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=es#share-public-link) <p>Esta funcionalidad está habilitada de forma predeterminada y el administrador del sistema puede inhabilitarla. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#ims-organization-preferences)</p> | 3 de mayo de 2023 | 6 de junio de 2023 |
| **Pantalla de inicio actualizada para la aplicación de paneles de Analytics (aplicación móvil)** | La nueva pantalla de inicio actualizada le permite ver todos los cuadros de resultados en una lista consolidada de cuadros de resultados. Si tiene acceso a más de una organización en un inicio de sesión, todos los cuadros de resultados de sus organizaciones estarán disponibles en una sola lista. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html#use-dashboards) | N/A | 10 de mayo de 2023 |
| **Campos derivados** | Representa la versión inicial de los campos Derivados. Un campo derivado permite definir manipulaciones de datos (a menudo complejas) sobre la marcha, mediante un generador de reglas personalizable. Puede definir el campo derivado como componente (métrica o dimensión) en las vistas de datos y, a continuación, utilizar el campo derivado como componente en Workspace.<p>Esta versión es compatible con una plantilla de canales de marketing y las siguientes funciones:</p><ul><li>Concatenar</li><li>Caso de que</li><li>Buscar y reemplazar</li><li>Búsqueda</li><li>Análisis de URL</li></ul> <p>[Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html?lang=es)</p> | 10 de mayo de 2023 | 2 de agosto de 2023 |
| **Report Builder para CJA: seleccionar la vista de datos de la celda** | Esta función permite a los usuarios seleccionar la vista de datos para un bloque de datos de una celda. Esto resulta útil si crea un libro y tiene varias vistas de datos que tienen una construcción de datos similar y desea poder reutilizar un libro varias veces, con diferentes vistas de datos. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=es) | N/A | 24 mayo de 2023 |
| **Ordenar componentes en Analysis Workspace** | <p>Ahora hay disponible una nueva opción de ordenación al ver componentes en el carril izquierdo o en el diccionario de datos de Analysis Workspace. Puede ordenar los componentes por Recomendado (los más utilizados), Alfabético o Categórico (tipo).</p><p>Anteriormente, solo se podían buscar o filtrar componentes. [Más información](/help/components/overview.md)</p> | N/A | Por determinar |

{style="table-layout:auto"}

## Correcciones en Customer Journey Analytics

AN-318343; AN-319453

## Avisos importantes para los administradores de CJA

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| N/A | N/A | N/A |

## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Migración a las credenciales de servidor a servidor de AdobeIO OAuth** | 11 de mayo de 2023 | Los clientes de la API de Adobe Analytics, la API de CJA y Livestream que utilizan las credenciales de JWT de AdobeIO deben migrar a las credenciales de servidor a servidor de OAuth de AdobeIO de **1 de enero de 2025**. AdobeIO no permitirá que se creen nuevas credenciales de JWT a partir del 1 de mayo de 2024. Los clientes que utilizan JWT deben crear una nueva credencial de servidor a servidor OAuth o migrar su credencial JWT existente a una credencial de servidor a servidor OAuth. Los clientes también deben actualizar sus aplicaciones cliente para utilizar las nuevas credenciales de servidor a servidor de OAuth. <ul><li>[Migración de credenciales de cuenta de servicio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Uso de las nuevas credenciales de servidor a servidor de OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Preguntas frecuentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de la versión de CJA anteriores de 2023](/help/release-notes/2023.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
