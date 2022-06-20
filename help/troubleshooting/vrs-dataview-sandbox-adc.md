---
source-git-commit: de28f20583457e91aa5136c688a885045606b860
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 8%

---
# Grupos de informes virtuales, vistas de datos, entornos limitados de AEP y el conector de origen de Analytics

Adobe proporciona una variedad de medios para crear entornos de informes virtuales y entornos de entornos limitados. Es útil comprender las similitudes y diferencias entre las siguientes funciones y cómo se relacionan estas con la variable [Conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es):

* Grupos de informes virtuales de Adobe Analytics
* Vistas de datos de CJA
* Entornos limitados de AEP

## Grupos de informes virtuales (VRS) de Adobe Analytics

Para obtener más información, consulte: [Resumen de los grupos de informes virtuales](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=es).

Un VRS:

* Se puede basar en segmentos de Adobe Analytics.
* Se puede aplicar a datos nuevos e históricos de una manera no destructiva.
* Permite crear una o varias vistas virtuales sobre un grupo de informes de Adobe Analytics para su uso por parte de distintos equipos empresariales.
* Puede utilizarse para controlar el acceso a diferentes tipos de datos y depurarlos para diferentes usuarios en Adobe Analytics.
* Proporciona información opcional [procesamiento de tiempo de informes](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en) para Adobe Analytics. En este caso, se puede utilizar un VRS para crear una definición personalizada de &quot;visita&quot;.
* Se aplica durante el tiempo de ejecución del informe, de forma similar a la evaluación de segmentos. Esto es _after_ los datos se han recopilado y almacenado en Adobe Analytics.
* Es necesario para [Análisis entre dispositivos](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=es) en Adobe Analytics.
* Tiene disponible el mismo número de variables para usar que un grupo de informes estándar de Analytics (250 eVars, 250 props y 1000 eventos), aunque la depuración de VRS puede limitar qué variables están expuestas a los usuarios.
* Admite opciones de calendario personalizadas.

Un grupo de informes virtuales no es:

* Proporcionar un medio para combinar grupos de informes.
* Disponible en la Data Warehouse de Adobe Analytics.
* Disponible como fuente para flujos de datos en AEP mediante el conector de origen de Analytics. Solo los grupos de informes completos (no virtuales) están disponibles para su uso con el conector de origen de Analytics.


## Vistas de datos de CJA

Para obtener más información, consulte: [Resumen de las vistas de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=es).

Una vista de datos:

* Se puede basar en filtros de CJA.
* Se puede aplicar a datos nuevos e históricos de una manera no destructiva.
* Permite crear una o varias vistas virtuales sobre una conexión CJA para su uso por parte de diferentes equipos empresariales.
* Puede utilizarse para controlar el acceso a diferentes tipos de datos y depurarlos para diferentes usuarios en CJA.
* Proporciona potentes opciones no destructivas para transformar y mejorar los datos que llegan a CJA a través de una conexión CJA.
* Se basa en las capacidades de procesamiento de tiempo de informes de CJA.
* Permite a los usuarios crear una definición personalizada para &quot;sesión&quot;.
* Se aplica durante el tiempo de ejecución del informe, de forma similar a la evaluación de filtros. Esto es _after_ el conector de origen (Adobe Analytics u otro) ha escrito datos en un conjunto de datos en el lago de datos de AEP, y _after_ los datos se han introducido en CJA a través de una conexión CJA.
* Permite un número ilimitado de variables, aunque la depuración puede limitar qué variables están expuestas a los usuarios
* Permite la asignación de nombres personalizados a los contenedores Evento, Sesión y Persona .
* Admite opciones de calendario personalizadas.

Una vista de datos no:

* Proporcionar directamente un medio para combinar grupos de informes u otros conjuntos de datos. En su lugar, los conjuntos de datos se combinan con en una conexión CJA. Los datos combinados de la conexión CJA están disponibles para su uso en todas las vistas de datos basadas en esa conexión.

## Entornos limitados de AEP

Para obtener más información, consulte: [Información general sobre Sandboxes](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=es).

Un entorno limitado de AEP:

* Proporciona un medio para dividir una sola instancia de AEP en entornos virtuales independientes (desarrollo, prueba, etapa, producción, etc.) para ayudar a desarrollar y desarrollar aplicaciones de experiencia digital.
* Se puede considerar como un contenedor que contiene todos los datos y aplicaciones de un entorno determinado.

Un entorno limitado de AEP no:

* Proporcionar funciones similares a las de grupos de informes virtuales, conexiones CJA o vistas de datos.
* Por sí solo, combine grupos de informes con o sin otros conjuntos de datos. Sin embargo, los conjuntos de datos de un simulador de pruebas se pueden combinar dentro de una conexión CJA.

Además:

* Los datos de diferentes entornos limitados no se pueden combinar dentro de CJA.
* El conector de origen de Analytics envía datos del grupo de informes _into_ un entorno limitado específico. Cada grupo de informes puede configurarse como fuente para un solo simulador de pruebas. Consulte la [Documentación del conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) para obtener más información.