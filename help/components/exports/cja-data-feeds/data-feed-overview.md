---
description: Obtenga información sobre cómo utilizar fuentes de datos para exportar datos sin procesar en el nivel de evento desde Customer Journey Analytics, revisar los requisitos previos y encontrar los artículos que necesita para empezar.
keywords: flujo de navegación;fuente de datos;fuente de datos;Fuente de datos
title: Información general sobre fuentes de datos Customer Journey Analytics
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
autotag-review: '2026-05-19T08:45:11.428Z'
TQID: 'https://experienceleague.adobe.com/TO8lEW8-GE-sIGj3vmm0X1zCgpg-0VpS1wjs0-HQjg8'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 34959e37a7040bcd861a506968895ad6f051b686
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 1%
---
# Resumen de fuentes de datos

{{release-limited-testing}}

Las fuentes de datos exportan datos sin procesar en el nivel de evento desde Customer Journey Analytics a un destino de nube. Puede utilizar estos datos en otras plataformas fuera de Adobe, como un almacén de datos.

Las fuentes de datos se crean a partir de los componentes de una vista de datos. Cada dimensión y métrica que incluya se convertirá en una columna de la fuente de datos y se aplicará a los datos la configuración de la vista de datos, como la persistencia, los campos derivados y los segmentos. Los archivos se entregan en formato parquet.

Puede crear los siguientes tipos de fuentes de datos:

* **Fuentes activas**: exporte datos actuales y futuros por hora o por día. Cada entrega se realiza después de que finalice la hora o el día y de que haya transcurrido el tiempo de procesamiento.

* **Fuentes de relleno**: exporte datos históricos para un intervalo de fechas anterior.

Para ver una comparación de las fuentes de datos con otros métodos de exportación de Customer Journey Analytics, como Exportación de tabla completa, consulte [Comparación de productos de Analytics](/help/getting-started/analytics-product-comparison.md).

## Requisitos previos

Asegúrese de cumplir todos los requisitos antes de utilizar fuentes de datos:

* Se están ingiriendo datos en Customer Journey Analytics y se han configurado una conexión y [vista de datos](/help/data-views/create-dataview.md). <!-- For more information, see Data ingestion overview - add link -->

* Su cuenta es un administrador de productos de Customer Journey Analytics o pertenece a un perfil de producto con el permiso [!UICONTROL **Fuentes de datos**] (en la categoría [!UICONTROL **Herramientas de vista de datos**]) para la vista de datos que desea utilizar. Para obtener más información, vea [Control de acceso](/help/technotes/access-control.md). <!--Add a Data Feeds row to the Data View Tools permissions table in access-control.md.-->

* Se han configurado una cuenta y una ubicación de exportación de nube para [!DNL Amazon S3], [!DNL Google Cloud Platform], [!DNL Azure RBAC] o [!DNL Azure SAS]. Para obtener más información, consulte [Configurar cuentas de exportación en la nube](/help/components/exports/cloud-export-accounts.md) y [Configurar ubicaciones de exportación en la nube](/help/components/exports/cloud-export-locations.md).

>[!TIP]
>
>Dado que los cambios en los componentes de una vista de datos afectan a cada fuente de datos que la utilice, considere la posibilidad de crear una vista de datos que solo se utilice para las fuentes de datos.
>
>* **Ventaja**: reduce el riesgo de que los cambios realizados en los informes de Analysis Workspace cambien inesperadamente el resultado de la fuente de datos.
>
>* **Desventaja**: debe mantener la vista de datos adicional junto con las demás vistas de datos.

## Introducción

Utilice los siguientes artículos para planificar, migrar y crear sus fuentes de datos.

### Planifique sus fuentes de datos

* [Comparar fuentes de datos en Customer Journey Analytics y Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md): comprenda las diferencias en funciones y conceptos si antes utilizaba fuentes de datos de Adobe Analytics.

* [Comprenda las discrepancias de datos entre las fuentes de datos y Analysis Workspace](/help/components/exports/cja-data-feeds/df-comparison-workspace.md): Descubra por qué la salida de las fuentes de datos podría no coincidir con los informes de Analysis Workspace.

* [Disponibilidad de componentes en fuentes de datos](/help/components/exports/cja-data-feeds/df-components.md): Descubra qué dimensiones y métricas son necesarias, no son compatibles o están restringidas en las fuentes de datos.

### Migración desde fuentes de datos de Adobe Analytics

1. [Prepárese para asignar columnas de fuentes de datos](/help/components/exports/cja-data-feeds/df-column-mapping-prep.md): comprenda los factores que afectan a cómo se asignan las columnas de Adobe Analytics a Customer Journey Analytics.

1. [Asignar columnas de fuentes de datos de Adobe Analytics a Customer Journey Analytics](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md): busque el equivalente de Customer Journey Analytics de cada columna de Adobe Analytics que desee conservar.

### Creación y configuración de fuentes de datos

* [Crear una fuente de datos](/help/components/exports/cja-data-feeds/create-feed.md): elija componentes, configure la programación y configure la entrega.

* [Segmentación en fuentes de datos](/help/components/exports/cja-data-feeds/df-segmentation.md): aplique segmentos para filtrar los datos en una fuente de datos.

* [Aplicar transformaciones de datos](/help/components/exports/cja-data-feeds/df-data-transformations.md): Transforme datos mediante la configuración de componentes, campos derivados o SQL.

* [Componentes de subevento en fuentes de datos](/help/components/exports/cja-data-feeds/df-sub-event.md): Descubra cómo se exportan los componentes de matrices y asignaciones y cómo consultarlos.

