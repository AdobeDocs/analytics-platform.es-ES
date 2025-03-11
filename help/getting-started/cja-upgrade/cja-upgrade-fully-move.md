---
title: Evalúe durante cuánto tiempo necesita Adobe Analytics después de actualizar a Customer Journey Analytics
description: Obtenga información sobre cómo evaluar cuánto tiempo necesita Adobe Analytics después de actualizar a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 7142ef84-66a6-49eb-938b-b67c9b65bf93
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 18%

---

# Evalúe cuándo deshabilitar Adobe Analytics después de actualizar a Customer Journey Analytics {#evaluate-aa-needs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-fully-move"
>title="Cambio total a Customer Journey Analytics"
>abstract="(Recomendado) Adobe le recomienda realizar la transición completa de Adobe Analytics a Customer Journey Analytics. Durante el período de transición, debe planificar la ejecución de Adobe Analytics junto con Customer Journey Analytics para realizar comparaciones de datos en paralelo. Cuando se sienta cómodo con los datos, puede deshabilitar Adobe Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-keep-aa"
>title="Mantener ambos productos de análisis"
>abstract="(No recomendado) Si selecciona esta opción, el contrato con Adobe incluye tanto Adobe Analytics como Customer Journey Analytics, lo que puede resultar más caro para su organización con el tiempo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-source-connector"
>title="Deshabilite el conector de origen de Analytics para utilizar datos exclusivamente desde Web SDK"
>abstract="El conector de origen de Analytics se utiliza para proporcionar una comparación de datos en paralelo, datos históricos y acceso a algunas funciones que no están totalmente disponibles en Customer Journey Analytics. Cuando ya no necesite Adobe Analytics para estos fines, puede deshabilitar el conector de origen de Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

La mayoría de las organizaciones deshabilitarán Adobe Analytics después de actualizar a Customer Journey Analytics. Esto se debe al coste y a la complejidad de mantener dos entornos de análisis.

Sin embargo, Adobe recomienda mantener el entorno de Adobe Analytics en ejecución durante un periodo de tiempo después de implementar Customer Journey Analytics. En las secciones siguientes se describen los motivos para hacerlo, así como el momento sugerido para deshabilitar Adobe Analytics.

## Usos de Adobe Analytics durante y después de una actualización

A la hora de decidir si su organización debe deshabilitar Adobe Analytics y cuándo, tenga en cuenta los siguientes usos de Adobe Analytics durante y después de una actualización a Customer Journey Analytics:

| Usos de Adobe Analytics durante y después de la actualización | Explicación |
|---------|----------|
| Realizar comparación de datos en paralelo | Adobe recomienda mantener el entorno de Adobe Analytics en ejecución durante un periodo de tiempo después de que el nuevo entorno de Customer Journey Analytics se esté ejecutando y recopilando datos. Esta es la mejor manera de comparar los datos de Customer Journey Analytics en paralelo con los de Adobe Analytics.<p>No desactive Adobe Analytics hasta que se sienta cómodo con los datos de su entorno de Customer Journey Analytics.</p><p>**Nota:** Adobe recomienda una nueva implementación de Web SDK para su entorno de Customer Journey Analytics, junto con el conector de origen de Analytics para los datos históricos. [Más información](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| Conservar datos históricos de Adobe Analytics | Adobe recomienda mantener el entorno de Adobe Analytics en su lugar con el conector de origen de Analytics durante un período de tiempo después de que el nuevo entorno de Customer Journey Analytics se esté ejecutando y recopilando datos. Esta es la mejor manera de incluir datos históricos de Adobe Analytics en Customer Journey Analytics.<p>Después de haber recopilado suficientes datos históricos en Customer Journey Analytics con la nueva implementación de Web SDK, puede quitar el conector de origen de Analytics por completo. Haga esto cuando pueda confiar únicamente en los datos históricos que ha recopilado con la nueva implementación de Customer Journey Analytics Web SDK.</p><p>**Nota:** Adobe recomienda una nueva implementación de Web SDK para su entorno de Customer Journey Analytics, junto con el conector de origen de Analytics para los datos históricos. [Más información](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| Usar fuentes de datos u otras funciones de Adobe Analytics | Un pequeño conjunto de funciones aún no está disponible en Customer Journey Analytics. Si necesita acceder a estas funciones, puede que sea necesario utilizar Adobe Analytics junto con Customer Journey Analytics hasta que estas funciones estén disponibles. <p>Las funciones que no están disponibles por completo en Customer Journey Analytics incluyen Fuentes de datos y Análisis de contribución. Para obtener una lista completa de las características que aún no están disponibles, consulte [Compatibilidad con características de Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).</p> |

## Proceso y cronología de desactivación de Adobe Analytics {#disable-adobe-analytics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement-third-pary"
>title="Deshabilitación de un sistema de administración de etiquetas de terceros"
>abstract="Con los datos del SDK web completamente funcionales, colabore con su administrador de etiquetas para quitar la biblioteca de AppMeasurement de su sistema de administración de etiquetas de terceros.<br><br>El tiempo estimado para realizar este paso depende de la facilidad con que se deshabilite AppMeasurement del producto de administración de etiquetas, así como del ciclo de lanzamiento que emplee su organización para implementar y administrar el código de etiquetas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-tags"
>title="Desactivación de la extensión de Analytics en etiquetas"
>abstract="Con los datos de Web SDK completamente funcionales, colabore con su administrador de etiquetas para eliminar la extensión de Adobe Analytics de la propiedad de etiquetas. Antes de hacerlo, asegúrese de que los usuarios hayan realizado la transición del uso de Adobe Analytics a Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-api"
>title="Desactivar la recopilación de datos de API para Adobe Analytics"
>abstract="Con los datos de Web SDK completamente funcionales, colabore con el equipo de ingeniería correspondiente para eliminar el código Adobe Analytics del proyecto. Antes de hacerlo, asegúrese de que los usuarios hayan realizado la transición del uso de Adobe Analytics a Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

La implementación de Adobe Analytics existente es una parte clave para una actualización correcta a Customer Journey Analytics, como se describe en la sección anterior, [Usos de Adobe Analytics durante y después de una actualización](#uses-of-adobe-analytics-during-and-after-an-upgrade).

Cuando ya no necesite Adobe Analytics para los fines descritos en la sección anterior, utilice la siguiente información para eliminar Adobe Analytics:

1. Deje de recopilar datos con Adobe Analytics.

   Una vez que esté satisfecho con las comparaciones paralelas de los datos de Adobe Analytics y de Customer Journey Analytics, puede dejar de recopilar datos con la implementación de Adobe Analytics. Los nuevos datos de Adobe Analytics ya no fluirán a Customer Journey Analytics a través del conector de origen de Analytics.

   Sin embargo, los datos que recopiló en su entorno de Adobe Analytics antes de este punto aún están disponibles como datos históricos en Customer Journey Analytics a través del conector de origen de Analytics.

   Este proceso difiere según el método de recopilación de datos que se haya utilizado para implementar Adobe Analytics:

+++ AppMeasurement

   [Deshabilitar la recopilación de datos de AppMeasurement](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md).

+++

+++ Extensión de Analytics (etiquetas)

   Deshabilite la extensión de Analytics en las etiquetas.

+++

+++ API

   Deshabilite la recopilación de datos API.

+++

+++ Terceros

   Póngase en contacto con el administrador de etiquetas para eliminar la biblioteca de AppMeasurement de su sistema de administración de etiquetas de terceros.

+++

1. Elimine Adobe Analytics como servicio del conjunto de datos.

   Con los datos de Web SDK completamente funcionales, colabore con el administrador de la plataforma para quitar Adobe Analytics como servicio del conjunto de datos.

   Antes de eliminar Adobe Analytics as a service, asegúrese de que los usuarios de Analytics utilicen Customer Journey Analytics y no Adobe Analytics.

1. Elimine completamente el conector de origen de Analytics.

   Después de haber recopilado suficientes datos históricos en Customer Journey Analytics con la nueva implementación de Web SDK, puede quitar el conector de origen de Analytics por completo.

   Haga esto cuando ya no necesite los datos históricos de su entorno de Adobe Analytics a través del conector de origen de Analytics y pueda confiar únicamente en los datos históricos que recopiló con la nueva implementación de Web SDK.

{{upgrade-final-step}}

