---
title: Grupos de informes virtuales, vistas de datos, zonas protegidas de Adobe Experience Platform y el conector de origen de Analytics
description: Obtenga información sobre los entornos de informes virtuales y los entornos de zonas protegidas.
exl-id: 8f0358d1-85fe-4e1e-8724-8a7caa16328c
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 62%

---

# Grupos de informes virtuales, vistas de datos, zonas protegidas de Adobe Experience Platform y el conector de origen de Analytics

Adobe proporciona una variedad de medios para crear entornos de informes virtuales y entornos de zonas protegidas. Es útil comprender las similitudes y diferencias entre las siguientes funciones y cómo se relacionan con el [conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es):

* Grupos de informes virtuales de Adobe Analytics
* Vistas de datos de Customer Journey Analytics
* Zonas protegidas de Adobe Experience Platform

## Grupos de informes virtuales (VRS) de Adobe Analytics

Para obtener más información, consulte: [Resumen de los grupos de informes virtuales](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=es).

Un grupo de informes virtuales:

* Se puede basar en segmentos de Adobe Analytics.
* Se puede aplicar a datos nuevos e históricos de una manera no destructiva.
* Permite crear una o varias vistas virtuales sobre un grupo de informes de Adobe Analytics para que las utilicen distintos equipos empresariales.
* Puede utilizarse para controlar el acceso a diferentes tipos de datos y depurarlos para diferentes usuarios en Adobe Analytics.
* Proporciona capacidades opcionales de [procesamiento en tiempo de informe](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=es) para Adobe Analytics. En este caso, se puede utilizar un VRS para crear una definición personalizada de «visita».
* Se aplica durante el tiempo de ejecución del informe, de forma similar a la evaluación de segmentos. Esto es _después_ de que los datos se hayan recopilado y almacenado en Adobe Analytics.
* Es necesario para el [análisis entre dispositivos](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=es) en Adobe Analytics.
* Tiene disponible el mismo número de variables que un grupo de informes estándar de Analytics (250 eVars, 250 props y 1000 eventos), aunque la depuración de VRS puede limitar qué variables están expuestas a los usuarios.
* Admite opciones de calendario personalizadas.

Un grupo de informes virtuales no es:

* Un medio para combinar grupos de informes.
* Algo que esté disponible en Adobe Analytics Data Warehouse.
* Disponible como fuente para flujos de datos en Adobe Experience Platform mediante el conector de origen de Analytics. Solo los grupos de informes completos (no virtuales) están disponibles para su uso con el conector de origen de Analytics.


## Vistas de datos de Customer Journey Analytics

Para obtener más información, consulte: [Resumen de las vistas de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=es).

Una vista de datos:

* Se puede basar en filtros de Customer Journey Analytics.
* Se puede aplicar a datos nuevos e históricos de una manera no destructiva.
* Permite crear una o varias vistas virtuales sobre una conexión de Customer Journey Analytics para que las utilicen distintos equipos empresariales.
* Puede utilizarse para controlar el acceso a diferentes tipos de datos y depurarlos para diferentes usuarios en Customer Journey Analytics.
* Proporciona potentes opciones no destructivas para transformar y mejorar los datos que llegan a Customer Journey Analytics a través de una conexión de Customer Journey Analytics.
* Se basa en las capacidades de procesamiento de tiempo de informes de Customer Journey Analytics.
* Permite a los usuarios crear una definición personalizada para «sesión».
* Se aplica durante el tiempo de ejecución del informe, de forma similar a una evaluación de filtro. Esto es _después_ el conector de origen (Adobe Analytics u otro) ha escrito datos en un conjunto de datos en el lago de datos de Adobe Experience Platform, y _después_ los datos se han introducido en Customer Journey Analytics mediante una conexión de Customer Journey Analytics.
* Permite un número ilimitado de variables, aunque la depuración puede limitar qué variables están expuestas a los usuarios
* Permite la asignación de nombres personalizados a los contenedores Evento, Sesión y Persona.
* Admite opciones de calendario personalizadas.

Una vista de datos no:

* Proporciona directamente un medio para combinar grupos de informes u otros conjuntos de datos. En su lugar, los conjuntos de datos se combinan con en una conexión de Customer Journey Analytics. Los datos combinados de la conexión de Customer Journey Analytics están disponibles para su uso en todas las vistas de datos basadas en esa conexión.

## Zonas protegidas de Adobe Experience Platform

Para obtener más información, consulte: [Resumen de las vistas de zona protegida](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=es).

Una zona protegida de Adobe Experience Platform:

* Proporciona un medio para dividir una sola instancia de Adobe Experience Platform en entornos virtuales independientes (desarrollo, prueba, fase, producción, etc.) para ayudar a desarrollar y evolucionar aplicaciones de experiencia digital.
* Se puede considerar como un contenedor de todos los datos y aplicaciones de un entorno determinado.

Una zona protegida de Adobe Experience Platform no:

* Proporciona funciones similares a las de grupos de informes virtuales, conexiones de Customer Journey Analytics o vistas de datos.
* Combina por sí sola grupos de informes con o sin otros conjuntos de datos. Sin embargo, los conjuntos de datos de una zona protegida se pueden combinar dentro de una conexión de Customer Journey Analytics.

Tenga en cuenta lo siguiente:

* Los datos de diferentes zonas protegidas no se pueden combinar dentro del Customer Journey Analytics.
* El conector de origen de Analytics envía datos del grupo de informes _hacia_ una zona protegida específica. Cada grupo de informes puede configurarse como fuente para una sola zona protegida. Consulte la [Documentación del conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es) para obtener más información.
