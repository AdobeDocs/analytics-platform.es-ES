---
title: Migración de Adobe Analytics a Customer Journey Analytics
description: Pasos para migrar de Adobe Analytics a Customer Journey Analytics
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: 2a330a430b48eb753d269e1165e95b61cb5fb483
workflow-type: tm+mt
source-wordcount: '1060'
ht-degree: 5%

---

# Preparación para migrar de Adobe Analytics a Customer Journey Analytics

Antes de migrar los datos de Adobe Analytics a Customer Journey Analytics, explore estas consideraciones para preparar los datos y conocer las diferencias críticas entre las dos tecnologías.

## Preparar los datos

La preparación de los datos de Adobe Analytics para un paso sin problemas al Customer Journey Analytics es fundamental para la integridad de los datos y la coherencia de los informes.

### 1. Recopilar identidades

Tal vez el componente más crítico para comprender el recorrido de un cliente sea saber quién es el cliente en cada paso. Para Customer Journey Analytics, tener un identificador que exista en todos los canales y los datos correspondientes permite unir varias fuentes dentro de CJA.
Algunos ejemplos de identidades pueden ser un ID de cliente, un ID de cuenta o un ID de correo electrónico. Independientemente de la identidad (y puede haber varios), asegúrese de tener en cuenta lo siguiente para cada ID:

* La ID existe o se puede agregar a todas las fuentes de datos que desee introducir en CJA
* El ID se rellena en cada fila de datos
* El ID no contiene PII. Aplique hash a cualquier cosa que pueda ser delicada.
* El ID utiliza el mismo formato en todas las fuentes (la misma longitud, el mismo método hash, etc.)

En conjuntos de datos como Adobe Analytics, es posible que no exista una identidad en cada fila de datos, pero sí una identidad secundaria. En este caso, se puede utilizar Cross-channel Analytics (anteriormente conocido como &quot;Configuración basada en el campo&quot;) para reducir el espacio entre filas cuando un cliente solo se identifica mediante su ECID y cuando se recopila una identidad (por ejemplo, cuando un cliente se autentica). [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=es)

### 2. Alinee las variables

La migración más directa de los datos de Adobe Analytics a Customer Journey Analytics es la ingesta de un grupo de informes globales en Experience Platform mediante el [Conector de origen de Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es). Este conector asigna las variables de Adobe Analytics directamente a un esquema XDM y a un conjunto de datos en AEP, que a su vez pueden conectarse fácilmente a CJA.

Es posible que no siempre sea factible una implementación de un grupo de informes globales completo. Si planea incluir varios grupos de informes en Customer Journey Analytics, debe planificarlos con anticipación para alinear las variables entre esos grupos de informes.

Por ejemplo, eVar1 en el grupo de informes 1 puede apuntar a [!UICONTROL Página]. En el grupo de informes 2, el eVar 1 puede señalar a [!UICONTROL Campaña interna]. Cuando se incorporan a CJA, estas variables se mezclan en una sola dimensión de eVar1, lo que conduce a informes potencialmente confusos e inexactos.

Si ha evitado pasar a un grupo de informes globales debido a problemas con [!UICONTROL Se excedió la cantidad de valores exclusivos] o [!UICONTROL Poco tráfico], sepa que CJA no tiene [límites de cardinalidad en una dimensión](/help/components/dimensions/high-cardinality.md). Permite que aparezca y se cuente cualquier valor único.

### 3. (Re)Configurar los canales de marketing

La configuración tradicional del canal de marketing de Adobe Analytics no funciona igual en CJA. Esto se debe a dos razones:

* El nivel de procesamiento de los datos de Adobe Analytics introducidos en Adobe Experience Platform y

* El carácter de tiempo del informe del Customer Journey Analytics

Adobe publicado [prácticas recomendadas actualizadas para la implementación de canales de marketing](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=en). Estas recomendaciones actualizadas le ayudan a sacar el máximo partido a las funciones que ya están disponibles en Adobe Analytics con Attribution IQ. También le configurarán para que tenga éxito al realizar la transición a Customer Journey Analytics.

### 4. Decida utilizar el conector de origen de Analytics y los SDK de Experience Platform

Como [Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=es) la recopilación de datos evoluciona, probablemente migrará a [SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/web-sdk.html?lang=en) o [SDK de Adobe Experience Platform Mobile](https://experienceleague.adobe.com/docs/mobile.html?lang=en) con Adobe Experience Platform Edge Network. Aunque una implementación típica de los SDK enviará datos a Adobe Analytics, se presenta una nueva oportunidad para enviar datos directamente a Adobe Experience Platform. A continuación, se puede ingerir en Customer Journey Analytics, manteniendo al mismo tiempo los datos enviados a Adobe Analytics.

Este método amplía considerablemente las posibilidades de recopilación de datos: Ya no existe una limitación en el número de campos o la necesidad de asignar elementos de datos a props, eVars y eventos como en Analytics. Puede utilizar elementos de esquema ilimitados de diferentes tipos y representarlos de varias formas mediante CJA [Vistas de datos](/help/data-views/data-views.md). La velocidad de disponibilidad de los datos aumenta cuando se envían directamente a Adobe Experience Platform, a medida que se elimina el tiempo de procesamiento de los datos mediante Adobe Analytics.

**Ventajas del uso de SDK de Experience Platform**

* Esquema flexible para definir cualquier campo que necesite
* No depende de la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)
* No existen limitaciones de caracteres (100 caracteres para props)
* Disponibilidad de datos más rápida en Adobe Experience Platform

**Inconvenientes para utilizar SDK de Experience Platform**

No se admiten los siguientes componentes de Adobe Analytics:

* Canales de marketing
* Filtros de bots
* Búsqueda geográfica, de dominio y de dispositivo
*  de Analytics for Target (A4T)

## Preparación para diferencias críticas

### Familiarícese con el procesamiento de tiempo de los informes

Los informes de Adobe Analytics dependen de una cantidad significativa de datos preprocesados para generar resultados como la persistencia que se ve en las eVars. El Customer Journey Analytics ejecuta esos cálculos en el tiempo de ejecución del informe.

El procesamiento del tiempo de los informes permite aplicar configuraciones retroactivas y crear varias versiones de la persistencia de las variables sin necesidad de cambiar la forma en que se recopilan los datos subyacentes.

Este cambio producirá algunas diferencias en la forma en que se crean los informes de los datos, especialmente para cualquier variable que pueda tener un período de caducidad largo. Puede empezar evaluando cómo puede afectar el procesamiento del tiempo de los informes a sus informes con un [grupo de informes virtuales](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html).

### Identificar segmentos críticos y métricas calculadas

Los segmentos de Adobe Analytics (llamados filtros en CJA) y las métricas calculadas no son compatibles con Customer Journey Analytics. En muchos casos, estos componentes se pueden reconstruir en CJA utilizando los nuevos esquemas y datos disponibles.

Para que la transición sea lo más fluida posible para los usuarios cuando realicen la transición entre sistemas, planifique con antelación

1. Identificación de los componentes más críticos.

1. Documentando sus definiciones, y

1. Identificación de los campos que se requerirán en los datos para replicarlos en CJA como [Filtros](/help/components/filters/filters-overview.md) y [Métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md).

Aquí hay un par de vídeos para guiarle:

* [Mover segmentos de Adobe Analytics al Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=en)

* [Paso de métricas calculadas de Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=en)
