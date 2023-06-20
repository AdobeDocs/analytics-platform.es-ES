---
title: Uso de los datos de grupos de informes de Adobe Analytics en Customer Journey Analytics
description: Configuración de grupos de informes de Adobe Analytics para su incorporación a Adobe Experience Platform y Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: ca329bd551990c1fefeda2fe272ed17551cfaac8
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 30%

---

# Uso de los datos de grupos de informes de Adobe Analytics en Customer Journey Analytics

Los clientes de Adobe Analytics pueden aprovechar fácilmente sus grupos de informes en Adobe Experience Platform y el Customer Journey Analytics mediante el [Conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=es). La siguiente discusión explica cómo hacerlo.

## Preparación

A medida que se prepara para empezar a usar grupos de informes de Adobe Analytics en Adobe Experience Platform y Customer Journey Analytics, debe considerar la posibilidad de hacer varias cosas para preparar sus datos para un paso perfecto a Customer Journey Analytics. Consulte la siguiente página para obtener más información:

* [Evolución de Adobe Analytics a Customer Journey Analytics](/help/getting-started/aa-to-cja.md)

## Configurar grupos de informes para su incorporación al Customer Journey Analytics de Adobe Experience Platform y

Una vez que haya preparado los datos, estará listo para empezar a configurar grupos de informes para su uso en Adobe Experience Platform y Customer Journey Analytics.

1. **Cree un flujo de datos para cada grupo de informes que desee utilizar en Adobe Experience Platform y Customer Journey Analytics.** El [Conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=es) es la herramienta que le permite [crear una conexión](/help/connections/create-connection.md) (también conocido como flujo de datos) entre Adobe Analytics y Adobe Experience Platform. Utilizará el conector de origen para crear un flujo de datos para cada grupo de informes que desee utilizar en Adobe Experience Platform. El flujo de datos crea una copia de los datos del grupo de informes en el que el esquema se ha convertido a  [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=es) para el consumo por aplicaciones de Adobe Experience Platform, incluido Customer Journey Analytics.<p>Cada grupo de informes configurado con un flujo de datos mediante el conector de origen se almacena como un conjunto de datos independiente en el lago de datos de Adobe Experience Platform. Con cada flujo de datos se incluirán automáticamente 13 meses de datos históricos de grupos de informes, y los nuevos datos fluirán a Adobe Experience Platform de forma continua. (Tenga en cuenta que a partir del 26 de abril de 2023, el relleno en zonas protegidas que no sean de producción estará limitado a 3 meses). Con el conector de origen de Analytics no es necesario preocuparse por crear el esquema con antelación. Se crea automáticamente un esquema estandarizado específico de Adobe Analytics. Sin embargo, Adobe Experience Platform [Preparación de datos](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=es) se puede utilizar para mejorar este esquema antes de que los datos se almacenen en Data Lake y se pongan a disposición del Customer Journey Analytics. Tenga en cuenta que ciertos tipos de datos se filtran por el conector de origen y no estarán presentes en el conjunto de datos en Adobe Experience Platform Data Lake. Otras filas pueden filtrarse entre el lago de datos y el Customer Journey Analytics. Consulte [Comparación de los datos de Adobe Analytics con los de Customer Journey Analytics](/help/troubleshooting/compare.md) para obtener más información.
1. **Utilice la preparación de datos para ayudarle a combinar grupos de informes en Customer Journey Analytics.** La preparación de datos se puede utilizar para muchos tipos de transformación de datos, y un uso común de los datos de Adobe Analytics es resolver las diferencias en las asignaciones de prop o eVar en varios grupos de informes, de modo que los grupos de informes se puedan combinar fácilmente dentro del Customer Journey Analytics. Consulte [combinar grupos de informes con distintos esquemas](/help/use-cases/aa-data/combine-report-suites.md) para obtener más información.
1. **Habilitar Cross-Channel Analytics** según sea necesario. Al combinar varios conjuntos de datos en Customer Journey Analytics, las capacidades de vinculación de identidad de Cross-Channel Analytics pueden ayudar a resolver diferentes áreas de nombres de ID en un único ID identificado para una única vista del cliente entre dispositivos y canales. Consulte [Resumen de Cross-Channel Analytics](/help/cca/overview.md) para obtener más información.
1. **Cree una o más conexiones de Customer Journey Analytics.** Una vez que los conjuntos de datos de sus grupos de informes estén disponibles en el lago de datos de Adobe Experience Platform, puede crear uno o más [conexiones de Customer Journey Analytics](/help/connections/overview.md) para llevar esos conjuntos de datos a Customer Journey Analytics. Dentro de una conexión, los datos del grupo de informes se pueden combinar con otros tipos de datos, lo que le permite crear una verdadera vista multicanal de las experiencias de los clientes.
1. **Cree una o varias vistas de datos de Customer Journey Analytics.** A [vista de datos](/help/data-views/data-views.md) es un contenedor específico de Customer Journey Analytics que le permite determinar cómo interpretar los datos de una conexión de Customer Journey Analytics. Las vistas de datos tienen muchas [opciones de configuración](/help/data-views/create-dataview.md) potentes para personalizar los datos que se presentan a los usuarios en [Analysis Workspace](/help/analysis-workspace/home.md).

## Comparación entre Customer Journey Analytics y Adobe Analytics

Customer Journey Analytics y Adobe Analytics tienen varias similitudes. Por ejemplo, tanto Customer Journey Analytics como Adobe Analytics ofrecen la potencia de Analysis Workspace para un análisis de forma libre de la velocidad de pensamiento. Sin embargo, como Customer Journey Analytics es una aplicación dentro de Adobe Experience Platform y utiliza Adobe Experience Platform para la ingesta de datos, Customer Journey Analytics y Adobe Analytics difieren en una serie de formas importantes. Los siguientes artículos son útiles para comprender estas diferencias:

* [Comparación de los datos de Adobe Analytics con los de Customer Journey Analytics](/help/troubleshooting/compare.md)
* [Compatibilidad con funciones de Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Comparación de terminología para datos de Analytics pasados a través del conector de origen de Analytics](/help/getting-started/aa-vs-cja/terminology.md)
* [Comparar el procesamiento de datos entre las funciones de informes de Adobe Analytics y de Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [Grupos de informes virtuales, vistas de datos, zonas protegidas de Adobe Experience Platform y el conector de origen de Analytics](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [Reglas de procesamiento, VISTA y clasificaciones en comparación con la preparación de datos](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID, ECID, AACUSTOMID y el conector de origen de Analytics](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
