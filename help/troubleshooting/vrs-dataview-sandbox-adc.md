---
source-git-commit: 7c3bbe2829c83406b2e6824e509c34459ae00f94
workflow-type: ht
source-wordcount: '698'
ht-degree: 100%

---
# Grupos de informes virtuales, vistas de datos, zonas protegidas de AEP y el conector de origen de Analytics

Adobe proporciona una variedad de medios para crear entornos de informes virtuales y entornos de zonas protegidas. Es útil comprender las similitudes y diferencias entre las siguientes funciones y cómo se relacionan con el [conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es):

* Grupos de informes virtuales de Adobe Analytics
* Vistas de datos de CJA
* Zonas protegidas de AEP

## Grupos de informes virtuales (VRS) de Adobe Analytics

Para obtener más información, consulte: [Resumen de los grupos de informes virtuales](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=es).

Un VRS:

* Se puede basar en segmentos de Adobe Analytics.
* Se puede aplicar a datos nuevos e históricos de una manera no destructiva.
* Permite crear una o varias vistas virtuales sobre un grupo de informes de Adobe Analytics para que las utilicen distintos equipos empresariales.
* Puede utilizarse para controlar el acceso a diferentes tipos de datos y depurarlos para diferentes usuarios en Adobe Analytics.
* Proporciona capacidades opcionales de [procesamiento en tiempo de informe](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=es) para Adobe Analytics. En este caso, se puede utilizar un VRS para crear una definición personalizada de «visita».
* Se aplica durante el tiempo de ejecución del informe, de forma similar a la evaluación de segmentos. Esto es _después_ de que los datos se hayan recopilado y almacenado en Adobe Analytics.
* Es necesario para el [análisis entre dispositivos](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=es) en Adobe Analytics.
* Tiene disponible el mismo número de variables que un grupo de informes estándar de Analytics (250 eVars, 250 props y 1000 eventos), aunque la depuración de VRS puede limitar qué variables están expuestas a los usuarios.
* Admite opciones de calendario personalizadas.

Un grupo de informes virtuales no:

* Proporciona un medio para combinar grupos de informes.
* Algo que esté disponible en Adobe Analytics Data Warehouse.
* Algo que esté disponible como fuente para flujos de datos en AEP mediante el conector de origen de Analytics. Solo los grupos de informes completos (no virtuales) están disponibles para su uso con el conector de origen de Analytics.


## Vistas de datos de CJA

Para obtener más información, consulte: [Resumen de las vistas de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=es).

Una vista de datos:

* Se puede basar en filtros de CJA.
* Se puede aplicar a datos nuevos e históricos de una manera no destructiva.
* Permite crear una o varias vistas virtuales sobre una conexión CJA para que las utilicen distintos equipos empresariales.
* Puede utilizarse para controlar el acceso a diferentes tipos de datos y depurarlos para diferentes usuarios en CJA.
* Proporciona potentes opciones no destructivas para transformar y mejorar los datos que llegan a CJA a través de una conexión CJA.
* Se basa en las capacidades de procesamiento de tiempo de informes de CJA.
* Permite a los usuarios crear una definición personalizada para «sesión».
* Se aplica durante el tiempo de ejecución del informe, de forma similar a una evaluación de filtro. Esto es _después_ de que el conector de origen (Adobe Analytics u otro) haya escrito datos en un conjunto de datos en el lago de datos de AEP, y _después_ de que los datos se hayan introducido en CJA a través de una conexión CJA.
* Permite un número ilimitado de variables, aunque la depuración puede limitar qué variables están expuestas a los usuarios
* Permite la asignación de nombres personalizados a los contenedores Evento, Sesión y Persona.
* Admite opciones de calendario personalizadas.

Una vista de datos no:

* Proporciona directamente un medio para combinar grupos de informes u otros conjuntos de datos. En su lugar, los conjuntos de datos se combinan con en una conexión CJA. Los datos combinados de la conexión CJA están disponibles para su uso en todas las vistas de datos basadas en esa conexión.

## Zonas protegidas de AEP

Para obtener más información, consulte: [Resumen de las vistas de zona protegida](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=es).

Una zona protegida de AEP:

* Proporciona un medio para dividir una sola instancia de AEP en entornos virtuales independientes (desarrollo, prueba, etapa, producción, etc.) para ayudar a desarrollar y evolucionar aplicaciones de experiencia digital.
* Se puede considerar como un contenedor de todos los datos y aplicaciones de un entorno determinado.

Una zona protegida de AEP no:

* Proporciona funciones similares a las de grupos de informes virtuales, conexiones CJA o vistas de datos.
* Combina por sí sola grupos de informes con o sin otros conjuntos de datos. Sin embargo, los conjuntos de datos de una zona protegida se pueden combinar dentro de una conexión CJA.

Más información:

* Los datos de diferentes zonas protegidas no se pueden combinar dentro de CJA.
* El conector de origen de Analytics envía datos del grupo de informes _hacia_ una zona protegida específica. Cada grupo de informes puede configurarse como fuente para una sola zona protegida. Consulte la [Documentación del conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es) para obtener más información.