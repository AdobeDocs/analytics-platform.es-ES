---
title: Reglas de procesamiento, VISTA y clasificaciones vs. Preparación de datos para el conector de origen de Analytics
description: Obtenga información sobre la transformación de datos mediante reglas de procesamiento y VISTA en comparación con el uso de la preparación de datos
source-git-commit: f6b8c5f1e8e82d0eb856b5cfed63b72c7ecfe3db
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 6%

---


# Reglas de procesamiento, VISTA y clasificaciones en comparación con la preparación de datos

Adobe Analytics [reglas de procesamiento y reglas de VISTA](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=en) proporcionar un medio para transformar y manipular los datos que se pasan a Adobe Analytics [recopilación de datos](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=en). Estas transformaciones se producen como parte del procesamiento de datos de Adobe antes de que los datos se almacenen para fines de informes y análisis en Adobe Analytics.

[Preparación de datos](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=es) es una herramienta que le permite aplicar asignaciones y transformaciones basadas en filas a los datos introducidos en [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=en). Posteriormente, los datos se ponen a disposición de las aplicaciones Experience Platform, incluidas CJA y otras. La preparación de datos está integrada con muchas de las plataformas [conectores de origen](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en), así como con el [Conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es). Este conector proporciona una forma de introducir datos de grupos de informes de Adobe Analytics en Platform.

## Transformación adicional mediante la preparación de datos {#data-prep}

Los datos que recopila y almacena Adobe Analytics se pueden transformar mediante reglas de procesamiento, reglas de VISTA o ambas. Sin embargo, los grupos de informes que luego se reenvíen a Platform a través del conector de origen de Analytics pueden transformarse una vez más a través de la preparación de datos. Esto puede ser deseable para varios fines:

* **Solución de diferencias de esquema entre grupos de informes para su uso en CJA o RTCDP**. Por ejemplo, supongamos que el grupo de informes A define `eVar1` como &quot;Término de búsqueda&quot; y grupo de informes B define `eVar2` como &quot;Término de búsqueda&quot;. Puede utilizar la preparación de datos para asignar las dos eVars diferentes a un campo común que contenga datos de ambas eVars. Esto permite [combinar grupos de informes con distintos esquemas](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=en) en un [Conexión CJA](/help/connections/overview.md) o para usar en [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html?lang=es).
* **Asignación `eVars` campos a nombres con sentido semántico**. `eVars` y `props` Los que llegan a través del conector de origen de Analytics están asignados a campos como _\_experience.analytics.customDimensions.eVars.eVar1_. La preparación de datos se puede utilizar para asignar `eVar` y `prop` a campos nuevos que tengan nombres más significativos para los usuarios o que coincidan con nombres procedentes de otras fuentes de datos. (Esto también se puede realizar por otros medios, como cambiar el nombre de los campos de una [Vista de datos de CJA](/help/data-views/create-dataview.md).)
* **Transformación general de datos**. La preparación de datos tiene cientos de funciones de asignación que se pueden utilizar para calcular y calcular nuevos campos en función de los datos que pasan a través del conector de origen de Analytics. Puede dividir los campos delimitados en campos independientes. Puede combinar campos. Puede manipular cadenas. Puede extraer información de un campo basándose en expresiones regulares y mucho más.

## Preparación y clasificación de datos {#classifications}

La preparación de datos tiene una transición con [clasificaciones](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=es) en algunas situaciones.

Por ejemplo, en un campo delimitado puede utilizar la preparación de datos para dividir ese campo en varios campos individuales sin el uso de clasificaciones. Por lo general, las clasificaciones permiten agregar metadatos a un campo cargando un archivo de búsqueda que se proporciona fuera del flujo de visitas entrantes de Analytics.

Por ejemplo, puede cargar un archivo de clasificación que agrupe las SKU en &quot;tamaño&quot;, &quot;marca&quot;, &quot;color&quot;, etc. Otra diferencia entre las clasificaciones y la Preparación de datos es que las clasificaciones se aplican a los datos _históricamente y en el futuro_. Por otro lado, se aplican las asignaciones de preparación de datos _forward_ a los datos desde el momento en que se crea la asignación.

