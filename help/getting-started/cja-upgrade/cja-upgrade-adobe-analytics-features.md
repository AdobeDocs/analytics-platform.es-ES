---
title: Comprender la compatibilidad con funciones de Adobe Analytics al actualizar a Customer Journey Analytics
description: Obtenga información acerca de la compatibilidad con funciones de Adobe Analytics al actualizar a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 92053109-f80d-47ab-b011-c28a5411149c
source-git-commit: 7a5414745f065ec29b59172dee4f723c0ce72e68
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 55%

---

# Comprender la compatibilidad con funciones de Adobe Analytics al actualizar a Customer Journey Analytics {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-migrate-projects"
>title="Componentes y proyectos"
>abstract="Los componentes de Adobe Analytics incluyen: proyectos (con sus tablas y visualizaciones de forma libre asociadas), segmentos y métricas calculadas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map"
>title="Superposición de Activity Map y seguimiento de vínculos"
>abstract="Una extensión del explorador que permite ver los datos de seguimiento de vínculos como una superposición en el sitio."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map-support"
>title="La compatibilidad con superposiciones de Activity Map aún no está disponible"
>abstract="La compatibilidad con superposiciones de Activity Map aún no está disponible en Customer Journey Analytics. Está previsto que esté disponible en el futuro."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-classification"
>title="Datos de clasificación"
>abstract="Agrupe o clasfiique los datos como dimensiones independientes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channels"
>title="Canales de marketing"
>abstract="Cree reglas que clasifiquen la forma en que los clientes llegan al sitio."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds"
>title="Fuentes de datos"
>abstract="Exporte datos sin procesar de Adobe Analytics para utilizarlos en herramientas y procesos externos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-warehouse"
>title="Data Warehouse"
>abstract="Exporte datos procesados de Adobe Analytics en formato de hoja de cálculo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-streaming-media"
>title="Datos de medios de streaming"
>abstract="Un complemento de Adobe Analytics y Customer Journey Analytics que está especializado en la recopilación de datos de medios, como audio, vídeo o contenido transmitido."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-component-migration"
>title="Migrar proyectos y componentes"
>abstract="Incluya proyectos de Adobe Analytics y sus componentes asociados a Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

La siguiente lista muestra solo las funciones de Adobe Analytics que deben tenerse en cuenta durante el proceso de actualización a Customer Journey Analytics. Para obtener una lista completa que muestre qué características de Adobe Analytics son totalmente compatibles, parcialmente compatibles o no compatibles con Customer Journey Analytics, consulte [Compatibilidad con características de Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

Tenga en cuenta cuál de las siguientes funciones de Adobe Analytics desea seguir utilizando al actualizar a Customer Journey Analytics:

| Función Adobe Analytics | Función correspondiente en Customer Journey Analytics |
|---------|----------|
| [Componentes y proyectos de Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) | [Migrar proyectos y sus componentes asociados a Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration). |
| [Superposición de Activity Map y seguimiento de vínculos](https://experienceleague.adobe.com/en/docs/analytics/analyze/activity-map/overview) | Aún no está disponible |
| [Datos de clasificación](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/c-classifications) | Los conjuntos de datos de búsqueda son el método para clasificar datos en Customer Journey Analytics.<p>[Cree un conjunto de datos de búsqueda para cada dimensión que contenga datos de clasificación.](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)</p> |
| [Canales de marketing](https://experienceleague.adobe.com/en/docs/analytics/components/marketing-channels/c-getting-started-mchannel) | Los campos derivados se crean dentro de una vista de datos. <p>[Crear un campo derivado de canal de marketing.](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)</p> |
| [Archivos de fuentes de datos](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview) | Experience Platform y Customer Journey Analytics proporcionan una serie de funcionalidades que, independientemente o combinadas, pueden resolver los distintos requisitos de exportación. Estas funcionalidades incluyen [API de acceso a datos de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=es), [Destinos de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=es), [Exportación de tablas completas de Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md) e [integración de herramientas de BI](/help/data-views/bi-extension.md).<p>Para obtener más información sobre las opciones de exportación, consulte [Casos de uso de exportación de datos](/help/use-cases/data-export/overview.md).</p> |
| [Data Warehouse](https://experienceleague.adobe.com/en/docs/analytics/export/data-warehouse/data-warehouse) | La [Exportación de tablas completas de Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md) es la evolución de los informes de Data Warehouse en Adobe Analytics, con muchas funciones nuevas y a menudo solicitadas que no están disponibles en Data Warehouse en la actualidad. |
| [Datos de medios de streaming](https://experienceleague.adobe.com/es/docs/media-analytics/using/media-overview) | Los datos de medios de streaming están disponibles mediante el conector de datos de Analytics como parte del panel Visualizadores simultáneos de medios y el panel Tiempo invertido en la reproducción de medios de Workspace. |
