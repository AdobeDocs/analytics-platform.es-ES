---
title: Reglas de procesamiento, VISTA y clasificaciones frente a la preparación de datos para el conector de origen de Analytics
description: Obtenga información sobre la transformación de datos mediante reglas de procesamiento y VISTA en comparación con el uso de la preparación de datos
exl-id: 049ad97e-0b4f-4163-a022-32661e48bf13
feature: Basics
role: User
TQID: https://experienceleague.adobe.com/MuJbtTwSbGbKBifnyWz6SNybYX9JsMpIL9QwVJv031Y
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 632
ht-degree: 92%

---

# Reglas de procesamiento, VISTA y clasificaciones en comparación con la preparación de datos

Las [reglas de procesamiento de Adobe Analytics y las reglas de VISTA](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=es) proporcionan un medio para transformar y manipular los datos que se pasan a la [recopilación de datos](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=es) de Adobe Analytics. Estas transformaciones se producen como parte del procesamiento de datos de Adobe antes de que los datos se almacenen para fines de informes y análisis en Adobe Analytics.

La [preparación de datos](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=es) es una herramienta que le permite aplicar asignaciones y transformaciones basadas en filas a los datos introducidos en [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=es). Posteriormente, los datos se ponen a disposición de las aplicaciones Experience Platform, incluidas Customer Journey Analytics y otras. La preparación de datos está integrada con muchos de los [conectores de origen](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=es) de Platform, así como con el [conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es). Este conector proporciona una forma de introducir datos de grupos de informes de Adobe Analytics en Platform.

## Transformación adicional mediante la preparación de datos {#data-prep}

Los datos que recopila y almacena Adobe Analytics se pueden transformar mediante reglas de procesamiento, reglas de VISTA o ambas. Sin embargo, los grupos de informes que luego se reenvían a Platform a través del conector de origen de Analytics pueden transformarse una vez más a través de la preparación de datos. Esto puede ser deseable para varios fines:

* **Solución de diferencias de esquema entre grupos de informes para su uso en Customer Journey Analytics o RTCDP**. Por ejemplo, supongamos que el grupo de informes A se define `eVar1` como “Término de búsqueda” y el grupo de informes B se define `eVar2` como “Término de búsqueda”. Puede utilizar la preparación de datos para asignar las dos eVars diferentes a un campo común que contenga datos de ambas eVars. Esto permite [combinar grupos de informes con distintos esquemas](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=es) en una [conexión Customer Journey Analytics](/help/connections/overview.md) o para usar en [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html?lang=es).
* **Asignación `eVars` de campos a nombres con sentido semántico**. `eVars` y `props` que llegan a través del conector de origen de Analytics están asignados a campos como _\_ experience.analytics.customDimensions.eVars.eVar1_. La preparación de datos se puede utilizar para asignar `eVar` y `prop` a campos nuevos que tengan nombres más significativos para los usuarios o que coincidan con nombres procedentes de otras fuentes de datos. (Esto también se puede realizar por otros medios, como cambiar el nombre de los campos de una [vista de datos de Customer Journey Analytics](/help/data-views/create-dataview.md)).
* **Transformación general de datos**. La preparación de datos tiene cientos de funciones de asignación que pueden usarse para computar y calcular nuevos campos basados en los datos que llegan a través del conector de origen de Analytics. Puede dividir los campos delimitados en campos independientes. Puede combinar campos. Puede manipular cadenas. Puede extraer información de un campo basándose en expresiones regulares y mucho más.

## Preparación y clasificación de datos {#classifications}

La preparación de datos tiene una transición con [clasificaciones](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=es) en algunas situaciones.

Por ejemplo, en un campo delimitado puede utilizar la preparación de datos para dividir ese campo en varios campos individuales sin el uso de clasificaciones. Por lo general, las clasificaciones permiten agregar metadatos a un campo cargando un archivo de búsqueda que se proporciona fuera del flujo de visitas entrantes de Analytics.

Por ejemplo, puede cargar un archivo de clasificación que agrupe las SKU en &quot;tamaño&quot;, &quot;marca&quot;, &quot;color&quot;, etc. Otra diferencia entre las clasificaciones y la preparación de datos es que las clasificaciones se aplican a los datos _tanto históricamente como en el futuro_. Las asignaciones de preparación de datos, por otro lado, se aplican _hacia adelante_ a los datos desde el momento en que se crea la asignación.
