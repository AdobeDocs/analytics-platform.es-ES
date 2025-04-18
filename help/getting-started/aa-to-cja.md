---
title: Evolución desde Adobe Analytics
description: Pasos para transformar datos de Adobe Analytics en datos de Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: 220ebd7dbc3fa75d221690cd6e5828bd94395434
workflow-type: tm+mt
source-wordcount: '1077'
ht-degree: 96%

---

# Evolución desde Adobe Analytics

## Preparación de los datos existentes

La preparación de los datos de Adobe Analytics para pasar sin problemas a Customer Journey Analytics es esencial para la integridad de los datos y la coherencia del sistema de informes.

### Recopilar identidades

Tal vez el componente más crítico para comprender el recorrido del cliente sea saber quién es el cliente en cada paso. Para Customer Journey Analytics, tener un identificador que exista en todos los canales y los datos correspondientes permite unir varias fuentes dentro de Customer Journey Analytics.
Algunos ejemplos de identidades pueden ser un ID de cliente, un ID de cuenta o un ID de correo electrónico. Independientemente de la identidad (y puede haber varias), asegúrese de tener en cuenta lo siguiente para cada ID:

* El ID existe o se puede añadir a todas las fuentes de datos que desee introducir en Customer Journey Analytics
* El ID se rellena en cada fila de datos
* El ID no contiene PII. Aplique la función resumen a cualquier cosa que pueda ser confidencial.
* El ID utiliza el mismo formato en todas las fuentes (la misma longitud, el mismo método de función resumen, etc.)

En conjuntos de datos como Adobe Analytics, es posible que no exista una identidad en cada fila de datos, pero sí una identidad secundaria. En este caso, se puede utilizar [análisis en canales múltiples (también conocido como “vinculación”)](/help/stitching/overview.md) para reducir el espacio entre filas cuando un cliente solo se identifica mediante su ECID y cuando se recopila una identidad (por ejemplo, cuando un cliente se autentica). 

### Alinee las variables

El método de transformación más directa de datos de Adobe Analytics a datos de Customer Journey Analytics es ingestar un [grupo de informes globales](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=es) en Experience Platform mediante el [conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es). Este conector asigna las variables de Adobe Analytics directamente a un esquema XDM y a un conjunto de datos en Experience Platform, que a su vez pueden conectarse fácilmente a Customer Journey Analytics.

Es posible que no siempre sea factible una implementación de un grupo de informes globales completo. Si planea incluir varios grupos de informes en Customer Journey Analytics, tiene dos opciones:

* Planifique con anticipación para alinear las variables en todos esos grupos de informes. Por ejemplo, eVar1 en el grupo de informes 1 puede apuntar a [!UICONTROL Página]. En el grupo de informes 2, el eVar1 puede señalar a [!UICONTROL Campaña interna]. Cuando se incorporan a Customer Journey Analytics, estas variables se mezclan en una sola dimensión de eVar1, lo que conduce a informes potencialmente confusos e inexactos.

* Utilice la función [Preparación de fecha](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=es) para asignar variables. Aunque facilita que todos los grupos de informes utilicen el mismo diseño común de variables, no es necesario si utiliza la nueva función [Preparación de datos](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es#mapping) de Experience Platform. Permite hacer referencia a una variable según su valor asignado, que es del nivel de conjunto de datos (o propiedad).

Si ha evitado pasarse a un grupo de informes globales debido a problemas de [!UICONTROL excesos en la cantidad de valores exclusivos] o [!UICONTROL bajo tráfico], debe saber que Customer Journey Analytics no tiene [límites de cardinalidad en una dimensión](/help/components/dimensions/high-cardinality.md). Permite que aparezca y se cuente cualquier valor único.

Este es un caso de uso en [combinación de grupos de informes con diferentes esquemas](/help/use-cases/aa-data/combine-report-suites.md).

### (Re)Configuración de los canales de marketing

La configuración tradicional del canal de marketing de Adobe Analytics no funciona igual en Customer Journey Analytics. Esto se debe a dos razones:

* El nivel de procesamiento de los datos de Adobe Analytics introducidos en Adobe Experience Platform y

* El carácter de tiempo del informe de Customer Journey Analytics

Adobe ha publicado [prácticas recomendadas actualizadas para la implementación de canales de marketing](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=es). Estas recomendaciones actualizadas le ayudan a sacar el máximo partido a las funciones que ya están disponibles en Adobe Analytics con Attribution IQ. También le prepararán para tener éxito al realizar la transición a Customer Journey Analytics.

Con la introducción de los [Campos derivados](../data-views/derived-fields/derived-fields.md) como parte de las vistas de datos de Customer Journey Analytics, los canales de marketing también son compatibles de forma inofensiva y retroactiva mediante la [plantilla de función de canal de marketing](../data-views/derived-fields/derived-fields.md#function-templates).

## Preparación para diferencias críticas al migrar a Customer Journey Analytics

A medida que su organización evoluciona para utilizar Customer Journey Analytics, explore estos pasos para preparar sus datos y tomar conciencia de las diferencias críticas entre las dos tecnologías. Este artículo está dirigido a administradores.

### Familiarícese con el procesamiento de tiempo de los informes {#report-time}

Los informes de Adobe Analytics dependen de una cantidad significativa de datos preprocesados para generar resultados como la persistencia que se ve en [!UICONTROL eVars]. Por el contrario, Customer Journey Analytics ejecuta esos cálculos en el tiempo de ejecución del informe.

[!UICONTROL Procesamiento de intervalo de tiempo] abre la capacidad de aplicar configuraciones retroactivas y crear varias versiones de persistencia de variables sin necesidad de cambiar la forma en que se recopilan los datos subyacentes.

Este cambio producirá algunas diferencias en la forma en que se crean los informes de los datos, especialmente para cualquier variable que pueda tener un período de caducidad largo. Puede empezar evaluando cómo puede afectar el procesamiento del tiempo de los informes a su creación con un [grupo de informes virtuales](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=es).

### Identificación de segmentos críticos y métricas calculadas {#segments-calcmetrics}

Los segmentos de Adobe Analytics y las métricas calculadas no son compatibles con Customer Journey Analytics. En muchos casos, estos componentes se pueden reconstruir en Customer Journey Analytics utilizando los nuevos esquemas y datos disponibles.

Para que el cambio sea lo más fluido posible para los usuarios cuando realicen la transición entre sistemas, planifíquelo con antelación de la siguiente manera:

1. Identifique los componentes más críticos.

2. Documente sus definiciones, e

3. Identifique los campos que se requerirán en los datos para replicarlos en Customer Journey Analytics como [Segmentos](/help/components/filters/filters-overview.md) y [Métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md).

Aquí hay un par de vídeos para guiarle:

* [Paso de segmentos de Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=es)

* [Paso de métricas calculadas de Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/calc-metrics/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=es)

### Otras consideraciones

* Con el poder de las vistas de datos de Customer Journey Analytics, tiene mucha más flexibilidad en la definición de métricas y dimensiones dentro de Customer Journey Analytics. Por ejemplo, puede utilizar el valor de una dimensión para convertirlo en la definición de una métrica. [Más información](/help/use-cases/data-views/data-views-usecases.md)

* Si ha definido un calendario personalizado en Adobe Analytics, tendrá [funciones de calendario personalizadas](/help/components/date-ranges/overview.md) similares dentro de Customer Journey Analytics. Debe asegurarse de que el calendario esté definido correctamente.

* En Customer Journey Analytics, puede definir un tiempo de espera de visita/sesión personalizado, así como una métrica que iniciará una nueva sesión. Puede crear vistas de datos con distintas definiciones de sesión para obtener perspectivas que vayan más allá de las posibles en Adobe Analytics. Esta capacidad puede ser especialmente beneficiosa para los conjuntos de datos móviles.

* Considere la posibilidad de proporcionar un diccionario de datos para los usuarios o ampliar el SDR para incluir el nombre del campo Experience Platform para los elementos de esquema.

### Pasos siguientes

Después de pasar a Customer Journey Analytics, si observa discrepancias en los datos, puede comparar los datos originales de Adobe Analytics con los de Adobe Analytics que ahora están en Customer Journey Analytics. [Más información](/help/troubleshooting/compare.md)
