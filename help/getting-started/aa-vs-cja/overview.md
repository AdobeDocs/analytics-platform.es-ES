---
title: Comparación con Adobe Analytics
description: Información general sobre cómo se compara Customer Journey Analytics con Adobe Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: bde36283-86af-4b1a-9cbe-e251676b2951
role: User
autotag-review: '2026-05-19T09:13:47.721Z'
TQID: 'https://experienceleague.adobe.com/MU9ywSyInHtsdzqvxO3yxTSY5bcDvdhnTUkhAgDHmZ4'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
    internal-label: Upgrade
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
    internal-label: Basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 1f480cda20e0b2d54dd42b909bfa8bf8a2bc0c95
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 52%
---
# Comparación con Adobe Analytics

En esta sección de la documentación se explica cómo comparar y comprender las diferencias entre Adobe Customer Journey Analytics y Adobe Analytics.

La diferencia fundamental entre las dos soluciones es la amplitud de datos que se puede tener en cuenta al crear informes y análisis.

En Customer Journey Analytics, *cualquier* fuente de datos puede formar parte de los datos que se utilizan para la creación de informes y el análisis. Adobe Analytics está dirigido principalmente a los datos en línea recopilados de sitios web y aplicaciones móviles. Adobe Analytics ofrece funcionalidades para importar datos de otras fuentes, pero el propósito principal de esta funcionalidad es proporcionar más contexto en torno a los datos en línea mencionados anteriormente.

## Recopilación de datos

Customer Journey Analytics se basa en los datos almacenados en los conjuntos de datos de Experience Platform. Tiene varias opciones para recopilar e introducir datos en estos conjuntos de datos en Experience Platform. Estas opciones se detallan en [Resumen de ingesta de datos](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-data-ingestion/data-ingestion).

En última instancia, Adobe Analytics recopila datos dentro de la propia solución. Una vez más, tiene varias opciones para recopilar esos datos, que se detallan en la [Guía de implementación de Adobe Analytics](https://experienceleague.adobe.com/es/docs/analytics/implementation/home).

Puede utilizar los datos del grupo de informes de Adobe Analytics en Customer Journey Analytics mediante el [Conector de origen de Analytics](https://experienceleague.adobe.com/es/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics). Este conector incorpora los datos recopilados en Adobe Analytics en Experience Platform. A continuación, puede crear una conexión con este conjunto de datos en Customer Journey Analytics. Consulte [Uso de datos de grupos de informes de Adobe Analytics en Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja) para obtener más información.

Los datos del grupo de informes de Adobe Analytics son independientes de los datos almacenados en los conjuntos de datos de Adobe Experience Platform que constituyen la conexión de Customer Journey Analytics. Por lo tanto, Adobe recomienda evaluar los datos en cada plataforma por separado en lugar de esperar que ambas plataformas reflejen los mismos valores.

## Procesamiento de datos

Antes de poder elaborar un informe sobre los datos, a menudo es necesario procesarlos para garantizar que se pueden utilizar adecuadamente para ese fin. Ese procesamiento de datos puede ocurrir en el momento de la recopilación y en el momento de la creación de informes.

En general, Customer Journey Analytics está diseñado para trabajar con los datos recopilados y almacenados en los conjuntos de datos de Experience Platform en el momento del informe. Customer Journey Analytics ofrece una potente funcionalidad de procesamiento de tiempo de los informes para garantizar que los datos estén listos para la creación de informes y el análisis. Los [campos derivados](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-dataviews/derived-fields) y la [configuración de componentes](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/overview) se pueden modificar y aplicar de forma retroactiva a los datos históricos. Si debe asignar, transformar y validar datos antes de ingerirlos en Experience Platform, puede usar la funcionalidad [Preparación de datos](https://experienceleague.adobe.com/es/docs/experience-platform/data-prep/home) de Experience Platform.

En Adobe Analytics, la mayor parte de ese procesamiento de datos se produce inmediatamente después de recopilarlos. Las reglas de canal de marketing, las reglas de procesamiento, la persistencia de eVar y otras lógicas posteriores al procesamiento se aplican en este momento y son permanentes en el grupo de informes. Los cambios realizados en cualquiera de estas configuraciones solo afectan a los nuevos datos entrantes a partir de ese momento.

Consulte [Comparar el procesamiento de datos entre Adobe Analytics y Customer Journey Analytics.](data-processing-comparisons.md) y [Reglas de procesamiento, VISTA y clasificaciones en comparación con la preparación de datos](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep) para obtener más información.


## Terminología

Customer Journey Analytics ofrece flexibilidad para definir dimensiones y métricas, gracias a la flexibilidad que proporcionan los esquemas basados en el Modelo de datos de experiencia (XDM) subyacente. Por ejemplo, donde Adobe Analytics utiliza visitantes, visitas y visitas individuales, Customer Journey Analytics utiliza personas, sesiones y eventos (puede cambiar el nombre como crea conveniente).

Consulte [Comparación de terminología para datos de Analytics pasados a través del conector de origen de Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology) para obtener más información sobre las diferencias terminológicas.


## Entornos virtuales de creación de informes y zonas protegidas

Adobe Analytics tiene el concepto de grupos de informes virtuales, que le permite segmentar los datos recopilados y controlar el acceso a esos datos segmentados.

Customer Journey Analytics tiene un concepto similar, denominado Vistas de datos. Las vistas de datos son contenedores que le permiten determinar cómo interpretar los datos de una conexión. Ofrece la máxima flexibilidad para especificar y configurar dimensiones y métricas a fin de prepararlas para la creación de informes y el análisis.

Experience Platform ofrece zonas protegidas que funcionan como un contenedor que contiene datos y aplicaciones para un entorno determinado. La funcionalidad de una zona protegida no está relacionada con un grupo de informes virtuales de Adobe Analytics o una vista de datos de Customer Journey Analytics. Adobe Analytics en sí no tiene dependencia ni relación con las zonas protegidas de Experience Platform. Customer Journey Analytics admite zonas protegidas de Experience Platform, aunque hay algunas consideraciones importantes.

Para más información, consulte [Grupos de informes virtuales, vistas de datos, zonas protegidas de Adobe Experience Platform y el conector de origen de Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc).


## Identidades

Customer Journey Analytics admite las identidades definidas como parte de los esquemas con los que se ajustan los conjuntos de datos que contienen los datos. De este modo, las identidades son un concepto básico de Experience Platform que Customer Journey Analytics utiliza al configurar una [conexión](../../connections/overview.md) (definiendo el ID de persona para cada conjunto de datos) y al aplicar la [vinculación](../../stitching/overview.md) para el análisis en canales múltiples. Una identidad importante que utilizan los SDK y la API de Experience Platform es el ECID.

Adobe Analytics utiliza un conjunto más definitivo de campos de identidad, como el ID de Adobe Analytics (AAID). Al utilizar el conector de origen de Analytics, estos campos de identidad de Adobe Analytics reciben un trato especial. Consulte [AAID, ECID, AACUSTOMID y el conector de origen de Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc) para obtener más información.


## Dimensiones de alta cardinalidad

Customer Journey Analytics almacena valores de dimensión completos y no hay límite para la cantidad de valores únicos que puede abarcar una dimensión. Por el contrario, Adobe Analytics utiliza hashes de 32 bits para asignar valores de dimensión y optimizar la creación de informes y el almacenamiento. Este comportamiento puede provocar [conflictos de hash](https://experienceleague.adobe.com/en/docs/analytics/implementation/validate/hash-collisions) en los informes. Adobe Analytics también agrupa los valores en el elemento de línea [Poco tráfico](https://experienceleague.adobe.com/en/docs/analytics/technotes/low-traffic) una vez que se alcanza el umbral de límite único. Los segmentos que utilizan estas dimensiones pueden mostrar discrepancias entre los informes de Adobe Analytics y Customer Journey Analytics.

## Funciones compatibles

Puede encontrar información general sobre las características de Adobe Analytics y cómo Customer Journey Analytics las admite en [Compatibilidad con características de Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa).
