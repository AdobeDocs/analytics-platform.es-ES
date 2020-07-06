---
description: Ejemplos de casos de uso para análisis de cohorte.
keywords: Analysis Workspace
title: Casos de uso de análisis de cohorte
topic: Reports and analytics
uuid: 5ec46f84-5702-4bc1-a796-874a3abe87c9
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 75%

---


# [!UICONTROL Casos de uso de Análisis] de cohorte

>[!NOTE]
>
>Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

Use case examples for [!UICONTROL Cohort Analysis].

## Caso de uso de interacción con aplicaciones

Imagine que desea analizar de qué manera los usuarios que instalan su aplicación interactúan con ella con el transcurso del tiempo. ¿La instalan y nunca la usan? ¿La usan por un tiempo y luego dejan de hacerlo? ¿O siguen interactuando con la aplicación a lo largo del tiempo?

You can create a six-month [!UICONTROL Cohort Analysis]:

**Granularidad**: mensual, de enero de 2015 a junio de 2015

**Métrica de inclusión**: instalaciones de aplicación

**Métrica de regreso**: sesiones o ejecuciones

Los visitantes no cuentan como *`engaged`* en meses siguientes a menos que tengan una sesión o que, como mínimo, ejecuten la aplicación. [!UICONTROL La Análisis] de cohorte le mostraría los patrones de uso donde *`App Install`* siempre se produce el Mes 0. Podría observar que el uso cae en el Mes 2, independientemente de cuándo instalaron la aplicación los usuarios (para quienes instalaron la aplicación en enero de 2015, el Mes 2 es marzo de 2015; para quienes instalaron la aplicación en febrero de 2015, el Mes 2 es abril de 2015, y así sucesivamente). Este análisis le permite enviar un correo electrónico o un mensaje insertado a todos los usuarios durante el segundo mes después de que instalan la aplicación para recordarles que usen la aplicación.

## Caso de uso de suscripción

Trabaja en Adobe.com y ofrece una suscripción gratuita a Creative Cloud. El objetivo es que los usuarios actualicen de la versión gratuita a la versión de prueba por 30 días o, en definitiva, la versión paga.

**Granularidad**: mensual

**Métrica de inclusión**: vínculo de descarga

**Métrica de regreso**: comprar Creative Cloud pago

Using this [!UICONTROL Cohort Analysis], you could see, for example, that anywhere between 8% and 10% of free Creative Cloud users upgrade in the first month after installation, regardless of when they installed. Del 12 % al 15 % actualizan en el segundo mes de uso. Después, la actualización cae significativamente: del 4 % al 5 % en el mes tres, del 3 % al 4 % en el mes cuatro y del 1 % al 2 % en el mes cinco.

Al reconocer que no necesita perder clientes potenciales en el mes tres, configura una campaña de correo electrónico diseñada para que salga a mediados del mes tres para una muestra de usuarios, ofreciendo un cupón por 50 dólares a los usuarios que aún no actualizaron.

Vuelva a consultar el informe de análisis de cohorte unos meses más tarde. Para cohortes formadas después de la ejecución de la campaña, la conversión a suscripciones a Creative Cloud de pago en el mes tres aumentó de un 4 % y 5 % a un 13 % y 14 %, lo que dio como resultado miles de dólares por cohorte, para cada cohorte mensual que llega al mes tres desde ese punto en adelante.

## Caso de uso de segmentos en una cohorte compleja

Una gran cadena hotelera dirige sus promociones a varios grupos de clientes y realiza un seguimiento del rendimiento. Para identificar los mejores grupos de cohortes de usuarios a los que dirigirse, quieren crear grupos de cohortes muy específicos. Using the augmented [!UICONTROL Inclusion] and [!UICONTROL Return] Criteria within [!UICONTROL Cohort] Tables, they are able to define just the right cohort groupings with multiple metrics and segments to identify underperforming customers groups in order to target them with promotions and deals to increase bookings.

## Caso de uso de adopción de versión de una aplicación

Una gran compañía de seguros obtiene una gran participación de los clientes gracias al uso de su aplicación móvil. Se han añadido nuevas funciones a dicha aplicación y resulta esencial que los clientes se actualicen a la versión más reciente. They can analyze and compare all of their app versions side-by-side using [!UICONTROL Custom Dimension] Cohort to see which customers on which app version to target. Además, puede realizar un seguimiento de la retención y la pérdida para determinar si alguna versión específica de la aplicación aleja a los usuarios de la misma a lo largo del tiempo. Mediante esfuerzos de mensajería móvil pueden reactivar a estos usuarios y animarlos a que se actualicen a la versión más reciente para que aprovechen las nuevas funciones.

## Caso de uso de permanencia en Campaign

Una empresa multimedia internacional utiliza campañas dirigidas para dirigir a los usuarios a sus distintas plataformas y así fomentar la participación. Los ingresos publicitarios por plataforma se basan en la participación de los clientes y la retención; por tanto, el éxito de las campañas es esencial para el éxito del negocio. They use our new [!UICONTROL Custom Dimension] Cohort feature in [!UICONTROL Cohort] Tables to compare various campaigns side-by-side to identify which campaigns are most effective at acquiring and retaining users to increase engagement. De ese modo puede identificar qué aspectos hacen que una campaña tenga éxito y aplicarlos a las demás, y así aumentar la participación en las distintas plataformas.

## Caso de uso de lanzamiento de productos

Un gran minorista de accesorios cuenta con muchos segmentos específicos de clientes que generan gran parte de los ingresos. Se diseñan y crean productos específicos para cada uno de esos segmentos. Cuando se produce un lanzamiento, la empresa quiere saber en qué medida el nuevo producto potencia las ventas en varias cohortes a lo largo del tiempo. Using the new [!UICONTROL Latency Table] setting in [!UICONTROL Cohort Analysis], they are able to analyze a given customer segment&#39;s pre-launch and post-launch behavior and revenue. Esta información permite identificar qué productos producen nuevos ingresos y cuáles no llegan a calar en los clientes.

## Permanencia individual: usuarios más fieles caso de uso

Una gran línea aérea deriva la mayor parte de su éxito e ingresos de los clientes fieles que repiten. En muchos casos, estos viajeros fieles representan la mayoría de los ingresos, por lo que conservarlos es esencial para el éxito a largo plazo. A menudo no es sencillo identificar a los clientes más fieles y consistentes. However, using the new [!UICONTROL Rolling Calculation] setting in [!UICONTROL Cohort Analysis], they were able to analyze loyal customer segments and find out which travelers were repeat purchasers month-over-month. Con estos datos pudo dirigirse a estos viajeros con recompensas y beneficios por su fidelidad. Además, cambiando el tipo de cohorte de retención a pérdida, también pudo identificar qué clientes no repetían reservas un mes tras otro, y así dirigirse a estos segmentos con promociones para reactivarlos y asegurar que, en el futuro, se conviertan en clientes leales.
