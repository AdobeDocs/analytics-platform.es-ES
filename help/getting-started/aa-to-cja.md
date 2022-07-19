---
title: Evolución de Adobe Analytics a Customer Journey Analytics
description: Pasos para transformar datos de Adobe Analytics en datos de Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: 93690a3351f2dca0b3a68e7eea7fb64c581d2d53
workflow-type: ht
source-wordcount: '1333'
ht-degree: 100%

---

# Evolución de Adobe Analytics a Customer Journey Analytics

A medida que su organización evoluciona para utilizar Customer Journey Analytics, explore estos pasos para preparar sus datos y tomar conciencia de las diferencias críticas entre las dos tecnologías. Este artículo está dirigido a administradores.

## Preparación de los datos

La preparación de los datos de Adobe Analytics para pasar sin problemas a Customer Journey Analytics es fundamental para la integridad de los datos y la coherencia del sistema de informes.

### 1. Recopilar identidades {#identities}

Tal vez el componente más crítico para comprender el recorrido del cliente sea saber quién es el cliente en cada paso. Para Customer Journey Analytics, tener un identificador que exista en todos los canales y los datos correspondientes permite unir varias fuentes dentro de CJA.
Algunos ejemplos de identidades pueden ser un ID de cliente, un ID de cuenta o un ID de correo electrónico. Independientemente de la identidad (y puede haber varias), asegúrese de tener en cuenta lo siguiente para cada ID:

* El ID existe o se puede añadir a todas las fuentes de datos que desee introducir en CJA
* El ID se rellena en cada fila de datos
* El ID no contiene PII. Aplique la función resumen a cualquier cosa que pueda ser confidencial.
* El ID utiliza el mismo formato en todas las fuentes (la misma longitud, el mismo método de función resumen, etc.)

En conjuntos de datos como Adobe Analytics, es posible que no exista una identidad en cada fila de datos, pero sí una identidad secundaria. En este caso, se puede utilizar Cross-Channel Analytics (anteriormente conocido como “vinculación basada en campos”) para reducir el espacio entre filas cuando un cliente solo se identifica mediante su ECID y cuando se recopila una identidad (por ejemplo, cuando un cliente se autentica). [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=es)

### 2. Alinee las variables {#variables}

El método de transformación más directa de datos de Adobe Analytics a datos de Customer Journey Analytics es ingerir un [grupo de informes globales](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=es) en Experience Platform mediante el [Conector de origen de Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es). Este conector asigna las variables de Adobe Analytics directamente a un esquema XDM y a un conjunto de datos en Experience Platform, que a su vez pueden conectarse fácilmente a Customer Journey Analytics.

Es posible que no siempre sea factible una implementación de un grupo de informes globales completo. Si planea incluir varios grupos de informes en Customer Journey Analytics, tiene dos opciones:

* Planifique con anticipación para alinear las variables en todos esos grupos de informes. Por ejemplo, eVar1 en el grupo de informes 1 puede apuntar a [!UICONTROL Página]. En el grupo de informes 2, el eVar1 puede señalar a [!UICONTROL Campaña interna]. Cuando se incorporan a CJA, estas variables se mezclan en una sola dimensión de eVar1, lo que conduce a informes potencialmente confusos e inexactos.

* Utilice la función [Preparación de fecha](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=es) para asignar variables. Aunque facilita que todos los grupos de informes utilicen el mismo diseño común de variables, no es necesario si utiliza la nueva función [Preparación de datos](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es#mapping) de Experience Platform. Permite hacer referencia a una variable según su valor asignado, que es del nivel de conjunto de datos (o propiedad).

Si ha evitado pasarse a un grupo de informes globales debido a problemas de [!UICONTROL excesos en la cantidad de valores exclusivos] o [!UICONTROL bajo tráfico], debe saber que CJA no tiene [límites de cardinalidad en una dimensión](/help/components/dimensions/high-cardinality.md). Permite que aparezca y se cuente cualquier valor único.

Este es un caso de uso en [combinación de grupos de informes con diferentes esquemas](/help/use-cases/combine-report-suites.md).

### 3. (Re)Configuración de los canales de marketing {#marketing-channels}

La configuración tradicional del canal de marketing de Adobe Analytics no funciona igual en CJA. Esto se debe a dos razones:

* El nivel de procesamiento de los datos de Adobe Analytics introducidos en Adobe Experience Platform y

* El carácter de tiempo del informe de Customer Journey Analytics

Adobe ha publicado [prácticas recomendadas actualizadas para la implementación de canales de marketing](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=es). Estas recomendaciones actualizadas le ayudan a sacar el máximo partido a las funciones que ya están disponibles en Adobe Analytics con Attribution IQ. También le prepararán para tener éxito al realizar la transición a Customer Journey Analytics.

### 4. Decida si utilizar el conector de origen de Analytics o los SDK de Experience Platform {#connector-vs-sdk}

Como la recopilación de datos [Edge de Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=es) evoluciona, probablemente migrará al [SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/web-sdk.html?lang=es) o al [SDK móvil de Adobe Experience Platform](https://experienceleague.adobe.com/docs/mobile.html?lang=es) con la red Edge de Adobe Experience Platform. Aunque una implementación típica de los SDK enviará datos a Adobe Analytics, se presenta una nueva oportunidad para enviar datos directamente a Adobe Experience Platform. A continuación, se puede ingerir en Customer Journey Analytics, y mantenerse al mismo tiempo los datos enviados a Adobe Analytics.

Este método amplía considerablemente las posibilidades de recopilación de datos: ya no existe una limitación en el número de campos o la necesidad de asignar elementos de datos a props, eVars y eventos como en Analytics. Puede utilizar elementos de esquema ilimitados de diferentes tipos y representarlos de varias formas mediante [Vistas de datos](/help/data-views/data-views.md) de CJA. La velocidad de disponibilidad de los datos aumenta cuando se envían directamente a Adobe Experience Platform, a medida que se elimina el tiempo de procesamiento de datos mediante Adobe Analytics.

**Ventajas de utilizar el SDK de Experience Platform:**

* Esquema flexible para definir cualquier campo que necesite
* No depende de la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)
* No existen limitaciones de caracteres (100 caracteres para props)
* Disponibilidad de datos más rápida en Adobe Experience Platform

**Inconvenientes de utilizar el SDK de Experience Platform**

No se admiten las siguientes funciones o componentes de Adobe Analytics:

* Canales de marketing
* Filtros de bots
* Búsqueda geográfica, de dominio y de dispositivo
* Analytics for Target (A4T)

## Preparación para diferencias críticas

### Familiarícese con el procesamiento de tiempo de los informes {#report-time}

Los informes de Adobe Analytics dependen de una cantidad significativa de datos preprocesados para generar resultados como la persistencia que se ve en [!UICONTROL eVars]. Por el contrario, Customer Journey Analytics ejecuta esos cálculos en el tiempo de ejecución del informe.

[!UICONTROL Procesamiento de intervalo de tiempo] abre la capacidad de aplicar configuraciones retroactivas y crear varias versiones de persistencia de variables sin necesidad de cambiar la forma en que se recopilan los datos subyacentes.

Este cambio producirá algunas diferencias en la forma en que se crean los informes de los datos, especialmente para cualquier variable que pueda tener un período de caducidad largo. Puede empezar evaluando cómo puede afectar el procesamiento del tiempo de los informes a su creación con un [grupo de informes virtuales](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=es).

### Identificación de segmentos críticos y métricas calculadas {#segments-calcmetrics}

Los segmentos de Adobe Analytics (llamados [!UICONTROL filtros] en CJA) y las métricas calculadas no son compatibles con Customer Journey Analytics. En muchos casos, estos componentes se pueden reconstruir en CJA utilizando los nuevos esquemas y datos disponibles.

Para que el cambio sea lo más fluido posible para los usuarios cuando realicen la transición entre sistemas, planifíquelo con antelación de la siguiente manera:

1. Identifique los componentes más críticos.

1. Documente sus definiciones, e

1. Identifique los campos que se requerirán en los datos para replicarlos en CJA como [Filtros](/help/components/filters/filters-overview.md) y [Métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md).

Aquí hay un par de vídeos para guiarle:

* [Paso de segmentos de Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=es)

* [Paso de métricas calculadas de Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/calc-metrics/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=es)

### Otras consideraciones

* Con el poder de las vistas de datos de CJA, tiene mucha más flexibilidad en la definición de métricas y dimensiones dentro de Customer Journey Analytics. Por ejemplo, puede utilizar el valor de una dimensión para convertirlo en la definición de una métrica. [Más información](/help/data-views/data-views-usecases.md)

* Si ha definido un calendario personalizado en Adobe Analytics, tendrá [funciones de calendario personalizadas](/help/components/date-ranges/custom-date-ranges.md) similares dentro de CJA. Debe asegurarse de que el calendario esté definido correctamente.

* En Customer Journey Analytics, puede definir un tiempo de espera de visita/sesión personalizado, así como una métrica que iniciará una nueva sesión. Puede crear vistas de datos con distintas definiciones de sesión para obtener perspectivas que vayan más allá de las posibles en Adobe Analytics. Esta capacidad puede ser especialmente beneficiosa para los conjuntos de datos móviles.

* Considere la posibilidad de proporcionar un diccionario de datos para los usuarios o ampliar el SDR para incluir el nombre del campo Experience Platform para los elementos de esquema.

## Pasos siguientes

Después de pasar a CJA, si observa discrepancias en los datos, puede comparar los datos originales de Adobe Analytics con los de Adobe Analytics que ahora están en Customer Journey Analytics. [Más información](/help/troubleshooting/compare.md)
