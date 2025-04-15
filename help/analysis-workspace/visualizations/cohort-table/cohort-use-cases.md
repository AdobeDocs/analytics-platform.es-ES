---
description: Obtenga información acerca de ejemplos de casos de uso para análisis de cohorte.
keywords: Analysis Workspace
title: Casos de uso de análisis de cohorte
feature: Visualizations
exl-id: f559d4b4-b682-4306-b111-22acb26fe0a0
role: User
source-git-commit: 0101986bb86c49776a044f754d912dc1bcb9422c
workflow-type: tm+mt
source-wordcount: '973'
ht-degree: 52%

---

# Casos de uso de [!UICONTROL análisis de cohorte]

Este artículo describe algunos ejemplos de casos de uso de [!UICONTROL Análisis de cohorte].

## Caso de uso de interacción con aplicaciones

Imagine que desea analizar de qué manera los usuarios que instalan su aplicación interactúan con ella con el transcurso del tiempo. ¿La instalan y nunca la usan? ¿La usan por un tiempo y luego dejan de hacerlo? ¿O siguen interactuando con la aplicación a lo largo del tiempo?

Puede crear un [!UICONTROL análisis de cohorte] de seis meses:

**Granularidad**: mensual, de enero de 2015 a junio de 2015

**Métrica de inclusión**: instalaciones de aplicación

**Métrica de regreso**: sesiones o ejecuciones

Las personas no cuentan como *comprometidos* en los meses siguientes, a menos que tengan una sesión o que, al menos, inicien la aplicación. [!UICONTROL Análisis de cohorte] le mostraría patrones de uso donde *Instalación de aplicación* siempre ocurre en el Mes 0. Podría observar que el uso cae en el Mes 2, independientemente de cuándo instalaron la aplicación los usuarios (Para los usuarios que instalaron la aplicación en enero de 2015, el Mes 2 es marzo de 2015. Para las personas que instalaron la aplicación en febrero de 2015, el Mes 2 es abril de 2015, y así sucesivamente). Este análisis le permite enviar un correo electrónico o un mensaje push a todos los usuarios durante el segundo mes después de que instalan la aplicación para recordarles que usen la aplicación.

## Caso de uso de suscripción

Trabaja en Adobe.com y ofrece una suscripción gratuita a Creative Cloud. El objetivo es que los usuarios actualicen de la versión gratuita a la versión de prueba por 30 días o, en definitiva, la versión paga.

**Granularidad**: mensual

**Métrica de inclusión**: vínculo de descarga

**Métrica de regreso**: comprar Creative Cloud pago

Con [!UICONTROL Análisis de cohorte], podría ver, por ejemplo, que cualquier lugar entre 8% y 10% de usuarios de Creative Cloud gratuito efectúan la actualización en el primer mes después de la instalación. Independientemente de cuándo instalaron los usuarios. Del 12 % al 15 % actualizan en el segundo mes de uso. Después, la actualización cae significativamente: del 4 % al 5 % en el mes tres, del 3 % al 4 % en el mes cuatro y del 1 % al 2 % en el mes cinco.

No quiere perder clientes potenciales en el mes tres. Por lo tanto, se configura una campaña de correo electrónico diseñada para que salga a mediados del tercer mes para una muestra de usuarios. Ofrecer un cupón de 50 $ a los usuarios que aún no hayan actualizado.

Vuelva a consultar los informes de análisis de cohorte unos meses más tarde. Para las cohortes formadas después del lanzamiento de la campaña, la conversión a suscripciones a Creative Cloud de pago en el mes tres aumentó de un 4 % y 5 % a un 13 % y 14 %. Este aumento en la conversión resulta en cientos de miles de dólares por cohorte, para cada cohorte mensual que llega al mes tres a partir de ese momento.

## Caso de uso de segmentos de cohorte complejos

Una gran cadena hotelera dirige sus promociones a varios grupos de clientes y realiza un seguimiento del rendimiento. Para identificar los mejores grupos de cohortes de usuarios a los que dirigirse, quieren crear grupos de cohortes muy específicos. Con los criterios aumentados de [!UICONTROL Inclusión] y [!UICONTROL Regreso] en las tablas de [!UICONTROL cohorte], la cadena de hoteles puede definir las agrupaciones de cohortes exactas, con múltiples métricas y segmentos. Por lo tanto, la cadena hotelera puede identificar grupos de clientes de bajo rendimiento para dirigirse a los clientes con promociones y ofertas para aumentar las reservas.

## Caso de uso de adopción de versión de una aplicación

Una gran compañía de seguros aumenta la participación de los clientes mediante el uso de su aplicación móvil. Se han añadido nuevas funciones a dicha aplicación y resulta esencial que los clientes se actualicen a la versión más reciente. La empresa puede analizar y comparar todas las versiones de la aplicación mediante una cohorte de [!UICONTROL dimensión personalizada], y así determinar a qué clientes debe dirigirse, en función de la versión de la aplicación que tengan. Además, puede realizar un seguimiento de la retención y la pérdida para determinar si alguna versión específica de la aplicación aleja a los usuarios de la misma a lo largo del tiempo. Mediante esfuerzos de mensajería móvil pueden reactivar a estos usuarios y animarlos a que se actualicen a la versión más reciente para que aprovechen las nuevas funciones.

## Caso de uso de permanencia en Campaign

Una empresa multimedia internacional utiliza campañas dirigidas para dirigir a los usuarios a sus distintas plataformas y así fomentar la participación. Los ingresos publicitarios por plataforma se basan en la participación de los clientes y la retención; por tanto, el éxito de las campañas es esencial para el éxito del negocio. Usan la nueva característica de cohorte [!UICONTROL Dimension] personalizada en las tablas [!UICONTROL Cohorte] para comparar varias campañas e identificar cuáles son las más efectivas a la hora de obtener y retener usuarios para aumentar la participación. De ese modo puede identificar qué aspectos hacen que una campaña tenga éxito y aplicarlos a las demás, y así aumentar la participación en las distintas plataformas.

## Caso de uso de lanzamiento de productos

Un gran minorista de accesorios cuenta con muchos segmentos específicos de clientes que generan gran parte de los ingresos. Se diseñan y crean productos específicos para cada uno de esos segmentos. Cuando se produce un lanzamiento, la empresa quiere saber en qué medida el nuevo producto potencia las ventas en varias cohortes a lo largo del tiempo. Mediante la nueva configuración de [!UICONTROL tablas de latencia] de los [!UICONTROL análisis de cohortes], se puede analizar el comportamiento y los ingresos de un segmento de clientes dados antes y después del lanzamiento. Esta información permite identificar qué productos producen nuevos ingresos y cuáles no llegan a calar en los clientes.

## Permanencia individual: caso de uso de los usuarios más fieles

Una gran línea aérea deriva la mayor parte de su éxito e ingresos de los clientes fieles que repiten. En muchos casos, estos viajeros fieles representan la mayoría de los ingresos, por lo que conservarlos es esencial para el éxito a largo plazo. A menudo no es sencillo identificar a los clientes más fieles y consistentes. Sin embargo, gracias a la nueva configuración de [!UICONTROL Cálculo móvil] en el [!UICONTROL Análisis de cohorte], la aerolínea puede analizar los segmentos de clientes fieles y averiguar cuáles repiten reservas un mes tras otro. La aerolínea también puede dirigirse a estos viajeros con recompensas y beneficios por su fidelidad. Además, cambiando el tipo de cohorte de retención a pérdida, la aerolínea puede identificar qué clientes no repiten reservas un mes tras otro, y así dirigirse a esos clientes con promociones. Por lo tanto, la aerolínea puede volver a interactuar con estos clientes y asegurarse de que sigan siendo clientes leales en el futuro.
