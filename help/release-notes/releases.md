---
description: Explica la estrategia de lanzamiento continuo de funciones para Customer Journey Analytics
title: Lanzamiento de funciones de Customer Journey Analytics
exl-id: aebe709a-4cc7-4197-86e9-b26ab2874375
source-git-commit: 44a140fdd5069cbe806f694377802215bcf50b31
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 90%

---

# Lanzamiento de funciones de Customer Journey Analytics

Las versiones de Customer Journey Analytics operan en un modelo de entrega continua que permite un enfoque escalable y gradual de la implementación de funciones.

## Estrategia de lanzamiento

[!UICONTROL Analysis Workspace] utiliza indicadores de funcionalidades (también conocidos como “alternadores”) para controlar la visibilidad de las nuevas funcionalidades, lo que permite realizar pruebas de escala controladas antes del lanzamiento final. Esta estrategia de versión incluye las siguientes fases:

* **Inicio de la implementación**: La implementación de una versión por fases comienza con las pruebas limitadas realizadas por los usuarios de Adobe internos. A continuación, la versión se escalará de 0% a 100% de disponibilidad para los clientes en un par de meses. La implementación por fases se produce en el nivel de organización de Experience Cloud, por lo que todos los usuarios con derecho de una organización reciben la misma experiencia.

* **Disponibilidad general (GA)**: La funcionalidad está disponible para el 100% de las organizaciones de Experience Cloud y la versión de la funcionalidad está completa.

Con cada versión de la funcionalidad, los plazos desde la fase de producción hasta su disponibilidad general pueden variar. El objetivo es reducir el número de versiones, de modo que en los 2 meses posteriores al comienzo de la producción, la funcionalidad esté disponible de forma general.

## Indicadores de características

Los indicadores de características se utilizan para controlar la visibilidad de las nuevas funciones durante el lanzamiento. Adobe recomienda añadir `app.launchdarkly.com` a la [lista de permitidos](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=es) del cortafuegos para disfrutar de una experiencia óptima durante el lanzamiento. Poco después de que se llegue a GA, se elimina el indicador.

Puede realizar la vista de los indicadores de funciones activas en cualquier momento en **Ayuda > Acerca de Espacio de trabajo > Indicadores de funciones activas**.

## Beneficios

Las versiones por fases permiten a Adobe escalar mejor el proceso de implementación de software y garantizar que las funcionalidades se desarrollen completamente antes de estar disponibles de forma general. También permite que las funcionalidades se publiquen tan pronto como estén disponibles, en lugar de seguir una tiempo de versión mensual fijo.

## Preguntas frecuentes

| Pregunta | Respuesta |
| --- | --- |
| ¿Puedo solicitar acceso anticipado a una funcionalidad? | No. No se puede solicitar el acceso anticipado.<br>Si desea probar las versiones iniciales de Analytics, le recomendamos que pruebe [Adobe Analytics Labs](https://experienceleague.adobe.com/docs/analytics/analyze/labs.html?lang=es) para proporcionar comentarios sobre las innovaciones líderes del sector. |
| ¿Esta estrategia de lanzamiento afecta mi acceso a las funcionalidades? | No. Una vez que una funcionalidad haya llegado a su fase de disponibilidad general, tendrá acceso a ella si está incluida en su paquete de Analytics. |
