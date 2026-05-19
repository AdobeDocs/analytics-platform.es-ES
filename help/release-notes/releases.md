---
description: Explica la estrategia de lanzamiento continuo de funciones para Customer Journey Analytics
title: Estrategia de lanzamiento de funcionalidades de Customer Journey Analytics
exl-id: aebe709a-4cc7-4197-86e9-b26ab2874375
feature: Release Notes
autotag-review: '2026-05-19T09:19:46.530Z'
TQID: 'https://experienceleague.adobe.com/nNV-qOa3LVmHUMLf-R2MwNHY0N67hxG2DWbVrpA-ZpI'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: a8e39571-4463-4aa3-8b3f-4e2341ecf3b3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 402
ht-degree: 90%

---

# Estrategia de lanzamiento de funcionalidades de Customer Journey Analytics

Las versiones de Customer Journey Analytics operan en un modelo de entrega continua que permite un enfoque escalable y gradual de la implementación de funciones.

## Estrategia de lanzamiento

[!UICONTROL Analysis Workspace] utiliza indicadores de funcionalidades (también conocidos como “conmutadores”) para controlar la visibilidad de las nuevas funcionalidades, lo que permite realizar pruebas de escala controladas antes del lanzamiento final. Esta estrategia de versión incluye las siguientes fases:

* **Prueba limitada**: una versión por fases comienza con las pruebas realizadas por los usuarios internos de Adobe. A continuación, se pone a disposición de un pequeño grupo de cuentas del cliente para garantizar que la funcionalidad satisfaga sus necesidades y expectativas.

* **Inicio del despliegue**: el despliegue de una versión por fases comienza con la prueba limitada. Después, la versión se escalará con una disponibilidad del 0 % al 100 % en el transcurso de un par de meses. La implementación por fases se produce en el nivel de organización empresarial de CX, por lo que todos los usuarios con derecho de una organización reciben la misma experiencia.

* **Disponibilidad general (GA)**: La funcionalidad está disponible para el 100% de las organizaciones empresariales de CX y la versión de la funcionalidad está completa.

Con cada versión de la funcionalidad, los plazos desde la fase de producción hasta su disponibilidad general pueden variar. El objetivo es reducir el número de versiones, de modo que en los 2 meses posteriores al comienzo de la producción, la funcionalidad esté disponible de forma general.

## Indicadores de características

Los indicadores de características se utilizan para controlar la visibilidad de las nuevas funciones durante el lanzamiento. Adobe recomienda permitir `app.launchdarkly.com` a través del cortafuegos de su organización para disfrutar de una experiencia óptima durante los lanzamientos. Estos indicadores se eliminan después del lanzamiento de una función para todos los usuarios. Consulte [Dominios utilizados por Customer Journey Analytics](../technotes/domains.md) para obtener más información.

Puede realizar la vista de los indicadores de funciones activas en cualquier momento en **Ayuda > Acerca de Espacio de trabajo > Indicadores de funciones activas**.

## Beneficios

Las versiones por fases permiten a Adobe escalar mejor el proceso de implementación de software y garantizar que las funcionalidades se desarrollen completamente antes de estar disponibles de forma general. También permite que las funcionalidades se publiquen tan pronto como estén disponibles, en lugar de seguir una tiempo de versión mensual fijo.

## Preguntas frecuentes

| Pregunta | Respuesta |
| --- | --- |
| ¿Puedo solicitar acceso anticipado a una funcionalidad? | No. No se puede solicitar el acceso anticipado.<br>Si desea probar las versiones iniciales de Analytics, le recomendamos que pruebe [Adobe Analytics Labs](https://experienceleague.adobe.com/docs/analytics/analyze/labs.html?lang=es) para proporcionar comentarios sobre las innovaciones líderes del sector. |
| ¿Esta estrategia de lanzamiento afecta mi acceso a las funcionalidades? | No. Una vez que una funcionalidad haya llegado a su fase de disponibilidad general, tendrá acceso a ella si está incluida en su paquete de Analytics. |
