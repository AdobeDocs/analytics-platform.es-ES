---
title: Comparación con Adobe Analytics
description: Información general sobre cómo se compara Customer Journey Analytics con Adobe Analytics.
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 59aabb38ea3e5ba1501ab8da11d14ea2385d8a6b
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 8%

---

# Comparación con Adobe Analytics

En esta sección de la documentación se explica cómo comparar y comprender las diferencias entre Customer Journey Analytics y Adobe Analytics.

La diferencia fundamental entre las dos soluciones es la amplitud de datos que se puede tener en cuenta al crear informes y análisis.

En Customer Journey Analytics, *cualquiera* la fuente de datos puede formar parte de los datos que se utilizan para los informes y análisis. Adobe Analytics está dirigido principalmente a los datos en línea recopilados de sitios web y aplicaciones móviles. Adobe Analytics ofrece funcionalidades para importar datos de otras fuentes, pero el propósito principal de esto es proporcionar más contexto a los datos en línea mencionados anteriormente.

## Recopilación de datos

Customer Journey Analytics se basa en los datos almacenados en los conjuntos de datos de Experience Platform. Tiene varias opciones para recopilar e introducir datos en estos conjuntos de datos en Experience Platform. Estas opciones se describen con más detalle en la sección [Resumen de ingesta de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/data-ingestion.html?lang=en).

En última instancia, Adobe Analytics recopila datos dentro de la propia solución. De nuevo, tiene varias opciones para recopilar esos datos, que se describen con más detalle en la sección [Guía de implementación de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=es).

Puede utilizar los datos del grupo de informes de Adobe Analytics en Customer Journey Analytics mediante el [Conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es). Este conector utiliza los datos recopilados en Adobe Analytics para introducirlos en Experience Platform y, a continuación, utilizarlos en Customer Journey Analytics. Consulte [Uso de datos de grupos de informes de Adobe Analytics en Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=es) para obtener más información.


## Procesamiento de datos

Para poder informar sobre los datos, a menudo debe procesarlos para asegurarse de que se pueden utilizar correctamente. Ese procesamiento de datos puede ocurrir en el momento de la recopilación y en el momento de la creación de informes.

En general, Customer Journey Analytics está diseñado para trabajar con los datos recopilados y almacenados en el conjunto de datos de Experience Platform en el momento del informe. Customer Journey Analytics ofrece una potente funcionalidad de procesamiento de tiempo de los informes para garantizar que los datos estén listos para la creación de informes y el análisis. Si debe asignar, transformar y validar los datos antes de introducirlos en Experience Platform, puede utilizar el [Preparación de datos](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=es) funcionalidad de Experience Platform.

En Adobe Analytics, la mayor parte del procesamiento de datos se produce inmediatamente después de recopilarlos.

Consulte [Comparar el procesamiento de datos entre Adobe Analytics y Customer Journey Analytics.](data-processing-comparisons.md) y [Reglas de procesamiento, VISTA y clasificaciones en comparación con la preparación de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html?lang=es) para obtener más información.


## Terminología

Customer Journey Analytics ofrece flexibilidad para definir dimensiones y métricas, gracias a la flexibilidad que proporcionan los esquemas basados en el Modelo de datos de experiencia (XDM) subyacentes. Por ejemplo, cuando Adobe Analytics utiliza visitantes, visitas y visitas individuales, Customer Journey Analytics utiliza personas, sesiones y eventos como conceptos equivalentes, pero puede cambiar el nombre como crea conveniente.

Consulte [Comparación de terminología para datos de Analytics pasados a través del conector de origen de Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology.html?lang=en) para obtener más información sobre las diferencias terminológicas.


## Entornos de informes virtuales y zonas protegidas

Adobe Analytics tiene el concepto de Grupos de informes virtuales, que le permite segmentar los datos recopilados y controlar el acceso a esos datos segmentados.

Customer Journey Analytics tiene un concepto similar, denominado Vistas de datos. Las vistas de datos son contenedores que le permiten determinar cómo interpretar los datos de una conexión. Ofrece la máxima flexibilidad para especificar y configurar dimensiones y métricas a fin de prepararlas para los informes y análisis.

Experience Platform ofrece zonas protegidas que se pueden considerar como un contenedor que contiene datos y aplicaciones para un entorno determinado. La funcionalidad de una zona protegida no está relacionada con un grupo de informes virtuales de Adobe Analytics o una vista de datos de Customer Journey Analytics. Adobe Analytics en sí no tiene dependencia ni relación alguna con las zonas protegidas de Experience Platform. El Customer Journey Analytics admite entornos limitados del Experience Platform, aunque hay algunas consideraciones importantes.

Consulte [Grupos de informes virtuales, vistas de datos, zonas protegidas de Adobe Experience Platform y el conector de origen de Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html?lang=es) para obtener más información.


## Identidades

Customer Journey Analytics admite las identidades definidas como parte de los esquemas con los que se ajustan los conjuntos de datos que contienen los datos. De este modo, las identidades son un concepto básico Experience Platform que Customer Journey Analytics utiliza al configurar una [conexión](../../connections/overview.md) (definiendo el ID de persona para cada conjunto de datos) y al aplicar [unión](../../stitching/overview.md) para análisis en canales múltiples. Una identidad importante que utilizan los SDK y la API de Experience Platform es el ID del Experience Cloud (ECID).

Adobe Analytics utiliza un conjunto más definitivo de campos de identidad, como el Adobe Analytics ID (AAID). Al utilizar el conector de origen de Analytics, estos campos de identificación de Adobe Analytics reciben un trato especial. Consulte [AAID, ECID, AACUSTOMID y el conector de origen de Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=en) para obtener más información.


## Funciones

Puede encontrar información general sobre las funciones de Adobe Analytics y cómo las admite Customer Journey Analytics en [Compatibilidad con funciones de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa.html?lang=en).





