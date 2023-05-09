---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 1c00f3974293c9022365e69d6c1b38d79f52d872
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 27%

---

# Notas de la versión de Customer Journey Analytics (CJA) actuales (mayo de 2023)

**Última actualización:** 8 de mayo de 2023

Las versiones de Customer Journey Analytics operan en un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones principales y actualizaciones

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Relleno para entornos limitados que no sean de producción** | Al crear un flujo de datos del conector de origen de Analytics en un simulador para pruebas que no sean de producción, el relleno de los entornos limitados que no sean de producción estará limitado a 3 meses. Permanecerá a los 13 meses para los entornos limitados de producción. | N/A | 26 de abril de 2023 |
| **Uso compartido de vínculos para proyectos (no se requiere inicio de sesión)** | Ahora puede compartir vínculos de solo lectura a proyectos de Analysis Workspace con personas que no tienen acceso a Adobe Analytics. Esto incluye el uso compartido con personas ajenas a su organización o con personas pertenecientes a su organización que no estén aprovisionadas para Adobe Analytics. [Más información](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>Esta funcionalidad está habilitada de forma predeterminada y el administrador del sistema puede desactivarla. [Más información](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=en#company-preferences)</p> | 3 de mayo de 2023 | Junio de 2023 |
| **Pantalla principal actualizada para la aplicación de paneles de Analytics (aplicación móvil)** | La nueva pantalla de inicio actualizada le permite ver todos los informes de valoración en una lista consolidada de informes de valoración.  Si tiene acceso a más de una organización en un inicio de sesión, todos los informes de valoración de sus organizaciones estarán disponibles en una sola lista. | N/A | 10 de mayo de 2023 |
| **Campos derivados** | Representa la versión inicial de los campos Derivados. Un campo derivado permite definir manipulaciones de datos (a menudo complejas) sobre la marcha, mediante un generador de reglas personalizable. Puede definir el campo derivado como componente (métrica o dimensión) en las vistas de datos y, a continuación, utilizar el campo derivado como componente en Workspace.<p>Esta versión es compatible con una plantilla de canales de marketing y las siguientes funciones:</p><ul><li>Concatenar</li><li>Caso de que</li><li>Buscar y reemplazar</li><li>Búsqueda</li><li>Análisis de URL</li></ul> <p>[Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html)</p> | 10 de mayo de 2023 | Por determinar |
| **Report Builder para CJA: seleccione la vista de datos de la celda** | Esta función permite a los usuarios seleccionar la vista de datos para un bloque de datos de una celda. Esto resulta útil si crea un libro y tiene varias vistas de datos que tienen una construcción de datos similar y desea poder reutilizar un libro varias veces, con diferentes vistas de datos. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) | N/A | 24 de mayo de 2023 |
| **Ordenar componentes en Analysis Workspace** | <p>Ahora hay disponible una nueva opción de ordenación al ver componentes en el carril izquierdo o en el diccionario de datos de Analysis Workspace. Puede ordenar los componentes por Recomendado (los más utilizados), Alfabético o Categórico (tipo).</p><p>Anteriormente, solo se podían buscar o filtrar componentes. [Más información](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=en)</p> | N/A | 10 de mayo de 2023 |
| **Eliminar filas que contienen dimensiones dinámicas de una tabla improvisada** | En una tabla improvisada de Analysis Workspace, ahora puede eliminar rápidamente filas específicas que contengan dimensiones dinámicas mediante el icono x . Al hacerlo, se aplica automáticamente una regla de filtro &quot;No es igual que&quot;.<p>Anteriormente, la única forma de eliminar filas que contenían dimensiones dinámicas era crear manualmente una regla en el cuadro de diálogo Filtro. [Más información](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.html?lang=en)</p> | N/A | 10 de mayo de 2023 |
| **Nuevo botón para añadir una visualización dentro de un panel** | Ahora hay disponible un nuevo botón en la parte inferior de cada panel en Analysis Workspace, lo que le permite añadir rápidamente una visualización. <p>Anteriormente, los únicos métodos para añadir una visualización a un panel eran arrastrar una visualización desde el carril izquierdo, duplicar o copiar una visualización existente o crear un panel en blanco. [Más información](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=en#quick-viz)</p> | N/A | 10 de mayo de 2023 |
| **Vinculación profunda (aplicación móvil)** | Permite a los usuarios enviar vínculos a informes de valoración que los llevarán directamente al proyecto de informe de valoración de la aplicación. Esto facilita aún más el uso compartido de proyectos y aumenta la participación de una audiencia menos técnica. | N/A | 17 de mayo de 2023 |
| **Subtítulos inteligentes** | Enriquezca la narración para los usuarios con resúmenes en lenguaje natural de una visualización de Línea. | 17 de mayo de 2023 | 1 de junio de 2023 |

{style="table-layout:auto"}

## Correcciones en Customer Journey Analytics

AN-316412; AN-317105; AN-318122; AN-317353

## Avisos importantes para los administradores de CJA

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| N/A | N/A | N/A |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de la versión de CJA anteriores de 2023](/help/release-notes/2023.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
