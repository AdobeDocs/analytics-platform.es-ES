---
title: Reemplazar fuentes de datos y Data Warehouse al migrar a Customer Journey Analytics
description: Planifique la migración de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 3a99aed3-26b9-494f-aaf9-f8eaa2c2d88f
source-git-commit: 8b7fedb9625ba60af1fea0b1580d32d2366081b8
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 1%

---

# Paso 8: Reemplazar fuentes de datos y Data Warehouse al migrar a Customer Journey Analytics

+++Expanda esta sección para ver dónde encaja la información de esta página en el proceso de migración más amplio. Asegúrese de que se han completado todos los pasos de migración anteriores.

Antes de continuar con esta sección, primero asegúrese de haber completado todas las tareas de migración anteriores.

La información de esta página cubre el paso 8, como se indica en la tabla siguiente:

| Tarea de migración | Detalles |
|---------|----------|
| **Paso 1: [Introducción a la migración](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Conozca las ventajas de migrar a Adobe Analytics y el proceso de migración básico. |
| **Paso 2: [Elija la ruta de migración](/help/getting-started/cja-migration/cja-migration-path.md)** | Hay varios métodos disponibles para migrar a Customer Journey Analytics. Elija el método que mejor se adapte a su organización, según el entorno de Adobe Analytics actual de su organización y los objetivos a largo plazo. |
| **Paso 3: [Asignación de datos al esquema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Esquemas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) se utilizan en Adobe Experience Platform para describir la estructura de los datos de una manera uniforme y reutilizable. Al definir los datos de forma coherente en todos los sistemas, resulta más fácil conservar el significado y, por lo tanto, obtener valor de los datos.<p>La mayoría de las rutas de migración requieren que cree un nuevo esquema XDM o que asigne el esquema de Adobe Analytics existente a XDM mediante la asignación de flujos de datos.</p> |
| **Paso 4: [Envío de datos a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | El proceso de envío de datos a Adobe Experience Platform difiere según la ruta de migración elegida en el paso 2. |
| **Paso 5: [Conservar datos históricos](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La mayoría de las organizaciones necesitan conservar sus datos históricos de Adobe Analytics durante un periodo de tiempo determinado. Hay varias opciones disponibles para hacerlo. |
| **Paso 6: [Planificar la incorporación del usuario](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Debe dar a los usuarios tiempo suficiente (de 3 a 6 meses) para familiarizarse con las diferencias clave de Analysis Workspace en Customer Journey Analytics. |
| **Paso 7: [Puerto del uso de API de informes](/help/getting-started/cja-migration/cja-migration-api.md)** | La API de informes de Customer Journey Analytics tiene el mismo formato, pero utiliza un punto de conexión diferente. Publique el uso de la API de informes desde la API de informes de Adobe Analytics a la API de informes de Customer Journey Analytics. |
| <span class="preview">**Paso 8: [Reemplazar fuentes de datos y Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)**</span> | <span class="preview">Decida cómo utilizará las opciones de exportación disponibles en Customer Journey Analytics para reemplazar las fuentes de datos y las funciones de Data Warehouse que utilizaba en Adobe Analytics.</span> |
| **Paso 9: [Migrar proyectos y componentes](/help/getting-started/cja-migration/cja-migration-projects.md)** | El área Migración de componentes en Adobe Analytics le permite migrar proyectos y sus componentes asociados de Adobe Analytics a Customer Journey Analytics. |
| **Paso 10: [Realizar tareas posteriores a la migración](/help/getting-started/cja-getting-started.md)** | Una vez completada la migración, debe realizar varias tareas, como introducir otros datos en Experience Platform, crear conexiones entre conjuntos de datos de Platform y Customer Journey Analytics, crear vistas de datos y aprender a informar sobre datos de canales cruzados en Analysis Workspace. |

{style="table-layout:auto"}

+++

Si actualmente utiliza Fuentes de datos o Data Warehouse en Adobe Analytics, utilice la siguiente tabla para obtener más información acerca de las distintas opciones de exportación disponibles en Customer Journey Analytics:

| Adobe Analytics | Customer Journey Analytics |
|---------|----------|
| Fuentes de datos | Evalúe los casos de uso de las fuentes de datos y, a continuación, utilice cualquier combinación de métodos de exportación alternativos disponibles en Customer Journey Analytics: <ul><li>Para exportar conjuntos de datos sin procesar, [exportar conjuntos de datos a destinos de almacenamiento en la nube](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets).&#x200B;</li><li>Para exportaciones de nivel de audiencia o evento mediante ID de persona o Marca de tiempo, utilice [Exportación de tabla completa](/help/analysis-workspace/export/export-cloud.md).&#x200B;</li><li>Para la integración directa con Power BI y Tableau, utilice el [Extensión de Customer Journey Analytics BI](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension).&#x200B;</li><li>Para acceder directamente a los datos de SQL en Adobe Experience Platform, utilice el [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/home).</li></ul> |
| Data Warehouse | Cambiar exportaciones de Data Warehouse de Adobe Analytics para usar [Exportación de tabla completa](/help/analysis-workspace/export/export-cloud.md) en Customer Journey Analytics.<p>Customer Journey Analytics La exportación de tablas completas es la evolución de los informes de Data Warehouse en Adobe Analytics, con muchas funciones nuevas y solicitadas que no están disponibles en Data Warehouse en la actualidad.</p> |

{style="table-layout:auto"}

## A continuación, migre proyectos y componentes

Utilice el área Migración de componentes en Adobe Analytics para lo siguiente [migrar proyectos y sus componentes asociados](/help/getting-started/cja-migration/cja-migration-projects.md) de Adobe Analytics a Customer Journey Analytics.
