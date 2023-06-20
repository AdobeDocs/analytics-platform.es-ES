---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '1316'
ht-degree: 75%

---

# Notas de la versión actuales de Adobe Customer Journey Analytics (junio de 2023)

**Última actualización**: 19 de junio de 2023

Las versiones de Customer Journey Analytics operan en un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Elementos destacados de la versión {#highlights}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Pies de ilustración inteligentes** | Enriquezca las historias para los usuarios con resúmenes en lenguaje natural de una visualización de [!UICONTROL Línea]. [Más información](/help/analysis-workspace/visualizations/intelligent-captions.md) | 17 de mayo de 2023 | 1 de junio de 2023 |
| **Uso compartido de vínculos para proyectos (no se requiere inicio de sesión)** | Ahora puede compartir vínculos de solo lectura a proyectos de Analysis Workspace con personas que no tienen acceso a Adobe Analytics. Esto incluye compartir con personas fuera de su organización o con personas de su organización que no estén aprovisionadas para Adobe Analytics. [Más información](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=es#share-public-link) <p>Esta funcionalidad está habilitada de forma predeterminada y el administrador del sistema puede inhabilitarla. [Más información](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=es#company-preferences)</p> | 3 de mayo de 2023 | 6 de junio de 2023 |
| **Campos derivados** | Representa la versión inicial de los campos Derivados. Un campo derivado permite definir manipulaciones de datos (a menudo complejas) sobre la marcha, mediante un generador de reglas personalizable. Puede definir aún más el campo derivado como un componente (métrica o dimensión) en las vistas de datos y, a continuación, utilizar el campo derivado como un componente en Workspace.<p>Esta versión es compatible con una plantilla de canales de marketing y las siguientes funciones:</p><ul><li>Concatenar</li><li>Caso de que</li><li>Buscar y reemplazar</li><li>Búsqueda</li><li>Análisis de URL</li></ul> <p>[Más información](/help/data-views/derived-fields/derived-fields.md)</p> | 10 de mayo de 2023 | 14 de junio de 2023 |
| **Acceso de Power BI y Tableau a vistas de datos de Customer Journey Analytics** | Adobe Customer Journey Analytics SQL Connector permite el acceso SQL a las vistas de datos definidas en Customer Journey Analytics. Los ingenieros y analistas de datos que estén más familiarizados con Power BI, Tableau u otras herramientas de inteligencia y visualización empresarial ahora pueden crear informes y paneles basados en las mismas vistas de datos que los usuarios de Customer Journey Analytics utilizan para sus proyectos de Analysis Workspace. [Más información](/help/data-views/sql-connector.md) |  | 30 de junio de 2023 |
| **Búsquedas geográficas de Experience Edge** | Podrá crear informes utilizando los datos de geolocalización en Customer Journey Analytics una vez que las búsquedas geográficas de Experience Edge estén habilitadas para su secuencia de datos. |  | 30 de junio de 2023 |
| **Compatibilidad de búsqueda ampliada para datos de perfil y búsqueda** | Podrá añadir conjuntos de datos de búsqueda no solo a conjuntos de datos de evento, sino también a conjuntos de datos de perfil y búsqueda. | 28 de junio de 2023 | 12 de julio de 2023 |
| **Compatibilidad con conversión de moneda** | La conversión de moneda se admite como parte del formato de un componente de métrica en una vista de datos. [Más información](../data-views/component-settings/format.md#currency) | 7 de junio de 2023 | 21 de junio de 2023 |

{style="table-layout:auto"}

## Otras nuevas funciones o actualizaciones {#other-new}

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Vistas de datos de Adobe Journey Optimizer** | Los administradores de Customer Journey Analytics tienen acceso a algunas vistas de datos adicionales en Customer Journey Analytics, tituladas &quot;Vista de datos de AJO (nombre de zona protegida)&quot;. Estas vistas de datos se utilizan para alimentar los informes en Adobe Journey Optimizer. También pueden utilizarse para realizar análisis más profundos de las actividades de Adobe Journey Optimizer en Customer Journey Analytics. [Más información](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html?lang=es). | | 25 de mayo de 2023 |
| **Relleno para zonas protegidas que no sean de producción** | Al crear un flujo de datos del conector de origen de Analytics en una zona protegida que no sea de producción, el relleno de las zonas protegidas que no sean de producción estará limitado a 3 meses. Permanecerá a los 13 meses para las zonas protegidas de producción. | N/A | 26 de abril de 2023 |
| **Uso compartido de vínculos para proyectos (no se requiere inicio de sesión)** | Ahora puede compartir vínculos de solo lectura a proyectos de Analysis Workspace con personas que no tienen acceso a Adobe Analytics. Esto incluye compartir con personas fuera de su organización o con personas de su organización que no estén aprovisionadas para Adobe Analytics. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=es#share-public-link) <p>Esta funcionalidad está habilitada de forma predeterminada y el administrador del sistema puede inhabilitarla. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=es#ims-organization-preferences)</p> | 3 de mayo de 2023 | 6 de junio de 2023 |
| **Pantalla de inicio actualizada para la aplicación de paneles de Analytics (aplicación móvil)** | La nueva pantalla de inicio actualizada le permite ver todos los cuadros de resultados en una lista consolidada de cuadros de resultados. Si tiene acceso a más de una organización en un inicio de sesión, todos los cuadros de resultados de sus organizaciones estarán disponibles en una sola lista. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html?lang=es#use-dashboards) | N/A | 10 de mayo de 2023 |
| **Report Builder para Customer Journey Analytics: seleccione la vista de datos de la celda** | Esta función permite a los usuarios seleccionar la vista de datos para un bloque de datos de una celda. Esto resulta útil si crea un libro y tiene varias vistas de datos que tienen una construcción de datos similar y desea poder reutilizar un libro varias veces, con diferentes vistas de datos. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=es) | N/A | 24 mayo de 2023 |
| **Página de aprendizaje actualizada para el Customer Journey Analytics** | La pestaña Aprendizaje en la página de aterrizaje del Customer Journey Analytics ahora contiene contenido específico del Customer Journey Analytics, incluido contenido centrado en la transición al Customer Journey Analytics desde Adobe Analytics.<p>Las siguientes mejoras adicionales también están disponibles en la pestaña Aprendizaje:</p><ul><li>Diseño mejorado que muestra más contenido de aprendizaje en una sola página con navegación mejorada</li><li>Capacidad para personalizar el contenido de aprendizaje por nivel de experiencia (principiante, intermedio y avanzado)</li></ul><p>Anteriormente, la pestaña Aprendizaje de Customer Journey Analytics contenía información idéntica a la pestaña Aprendizaje de Adobe Analytics.</p> [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=en#navigate-learning) | N/A | 30 de junio de 2023 |
| **Ordenar componentes en Analysis Workspace** | <p>Ahora hay disponible una nueva opción de ordenación al ver componentes en el carril izquierdo o en el diccionario de datos de Analysis Workspace. Puede ordenar los componentes por Recomendado (los más utilizados), Alfabético o Categórico (tipo).</p><p>Anteriormente, solo se podían buscar o filtrar componentes. [Más información](/help/components/overview.md)</p> | N/A | 7 de junio de 2023 |
| **Eliminación de filas que contienen dimensiones dinámicas de una tabla de forma libre** | En una tabla de forma libre de Analysis Workspace, ahora puede eliminar rápidamente filas específicas que contengan dimensiones dinámicas mediante el icono x. Al hacerlo, se aplica automáticamente una regla de filtro &quot;Excluir artículos siempre&quot;.<p>Anteriormente, la única forma de eliminar filas que contenían dimensiones dinámicas era crear manualmente una regla en el cuadro de diálogo Filtro. [Más información](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | N/A | 17 de mayo de 2023 |
| **Nuevo botón para añadir una visualización dentro de un panel** | Ahora hay disponible un nuevo botón en la parte inferior de cada panel en Analysis Workspace, lo que le permite añadir rápidamente una visualización. <p>Anteriormente, los únicos métodos para añadir una visualización a un panel eran arrastrar una visualización desde el carril izquierdo, duplicar o copiar una visualización existente o crear un panel en blanco. [Más información](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | N/A | 17 de mayo de 2023 |
| **Vinculación profunda (aplicación móvil)** | Permite a los usuarios enviar vínculos a cuadros de resultados que los llevarán directamente al cuadro de resultados de la aplicación. Esto facilita aún más el uso compartido de proyectos e impulsa la participación de una audiencia menos técnica. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=es#share-scorecards-using-a-shareable-link) | N/A | 17 de mayo de 2023 |
| **Pies de ilustración inteligentes** | Enriquezca las historias para los usuarios con resúmenes en lenguaje natural de una visualización de [!UICONTROL Línea]. [Más información](/help/analysis-workspace/visualizations/intelligent-captions.md) | 17 de mayo de 2023 | 1 de junio de 2023 |

{style="table-layout:auto"}

## Correcciones en Customer Journey Analytics

AN-318343; AN-319453

## Avisos importantes para los administradores de Customer Journey Analytics

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| N/A | N/A | N/A |

## Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Migración a las credenciales de servidor a servidor de Adobe I/O OAuth** | 11 de mayo de 2023 | Los clientes de la API de Adobe Analytics, la API de Customer Journey Analytics y Livestream que utilizan las credenciales de JWT de AdobeIO deben migrar a las credenciales de servidor a servidor de OAuth de AdobeIO de **1 de enero de 2025**. Adobe I/O no permitirá que se creen nuevas credenciales de JWT a partir del 1 de mayo de 2024. Los clientes que utilizan JWT deben crear una nueva credencial de servidor a servidor OAuth o migrar su credencial JWT existente a una credencial de servidor a servidor OAuth. Los clientes también deben actualizar sus aplicaciones cliente para utilizar las nuevas credenciales de servidor a servidor de OAuth. <ul><li>[Migración de credenciales de cuenta de servicio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Uso de las nuevas credenciales de servidor a servidor de OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Preguntas frecuentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de la versión anteriores de Customer Journey Analytics de 2023](/help/release-notes/2023.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
