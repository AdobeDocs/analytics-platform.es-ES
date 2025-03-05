---
title: Descripción de las funciones exclusivas de Customer Journey Analytics
description: Obtenga información sobre las funciones exclusivas de Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 4e6cacb9-4eca-4dfb-bce4-e69850507596
source-git-commit: d745e0c3bc75ba6f9d29aedcdbaaae9aa17d6ab8
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 27%

---

# Descripción de las funciones exclusivas de Customer Journey Analytics {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tie-data"
>title="Vincular datos de distintas fuentes"
>abstract="(Recomendado) Asocie datos de varias propiedades web, móviles y sin conexión para crear una única vista consolidada del comportamiento de los clientes. Esta capacidad para combinar datos de análisis de otros canales es el caso de uso principal de Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-datasets"
>title="Unir resultados de varios conjuntos de datos"
>abstract="Si alguno de los conjuntos de datos no comparte un identificador principal (como, por ejemplo, un ID de Experience Cloud), aún puede unir esos datos mediante otra dimensión, como el nombre de usuario de inicio de sesión o la dirección de correo electrónico."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-customer-care"
>title="Póngase en contacto con el Servicio de atención al cliente de Adobe para generar un conjunto de datos vinculado"
>abstract="Si tiene un campo que contiene un identificador que existe en varios conjuntos de datos, pero no es el identificador principal, puede utilizarlo para generar un nuevo conjunto de datos con un identificador coherente."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-rtcdp"
>title="Integración con Real-time CDP"
>abstract="Combine datos de perfil de varias fuentes para generar audiencias y segmentos basados en rasgos de usuario."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-target"
>title="Integración temporal con Adobe Target"
>abstract="Adobe recomienda integrar con Adobe Journey Optimizer para casos de uso de personalización. La integración con Adobe Target es posible, pero una solución a corto plazo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-ajo"
>title="Integración con Journey Optimizer"
>abstract="Ofrezca experiencias conectadas, contextuales y personalizadas a los clientes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-aam"
>title="Integración temporal con Adobe Audience Manager"
>abstract="Adobe recomienda integrar con Adobe Real-time CDP para casos de uso basados en audiencias. La integración con Audience Manager es posible, pero una solución a corto plazo."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

La siguiente lista muestra solo las funciones de Customer Journey Analytics que deben tenerse en cuenta durante el proceso de actualización. Para obtener una lista completa que muestre qué características de Adobe Analytics son totalmente compatibles, parcialmente compatibles o no compatibles con Customer Journey Analytics, consulte [Compatibilidad con características de Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

Tenga en cuenta cuál de las siguientes funciones de Customer Journey Analytics desea adoptar al actualizar a Customer Journey Analytics:

| Función Customer Journey Analytics | Función |
|---------|----------|
| [Asocie datos web con datos de otros canales, como los datos del centro de llamadas](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | Customer Journey Analytics se combina con la capacidad de Experience Platform para albergar todo tipo de esquemas y datos. Con [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es), los datos se pueden representar y organizar de forma uniforme, listos para la combinación y exploración. Adobe Analytics se centra principalmente en los datos de análisis web y móviles con algunas funcionalidades para [importar datos](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=es). |
| [Unir visitas de otros conjuntos de datos usando una dimensión personalizada](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/overview) | Customer Journey Analytics le permite [combinar datos](/help/connections/combined-dataset.md) de varios grupos de informes como si fueran un único grupo de informes de Adobe Analytics. |
| [Integrar con Adobe Real-time CDP](/help/components/audiences/audiences-overview.md) | Puede [crear y publicar audiencias](/help/components/audiences/audiences-overview.md) descubiertas en Customer Journey Analytics para el Perfil del cliente en tiempo real en Adobe Experience Platform para la personalización y segmentación de clientes. |
| [Integrar con Adobe Target (A4T)](/help/integrations/at.md) | Los informes de Target en Customer Journey Analytics le permiten [medir e informar sobre las actividades de Adobe Target](/help/integrations/at.md) directamente en Customer Journey Analytics. Sin embargo, Adobe recomienda integrar con Adobe Journey Optimizer para casos de uso personalizados. |
| [Integrar con Adobe Journey Optimizer](/help/integrations/ajo.md) | Puede configurar los datos generados por Journey Optimizer para [realizar análisis avanzados en Customer Journey Analytics](/help/integrations/ajo.md). |
| [Integrar con Adobe Audience Manager](https://experienceleague.adobe.com/en/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing) | Puede [compartir rasgos y segmentos de Audience Manager con Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing). Sin embargo, Adobe recomienda la integración con CDP en tiempo real de Adobe para casos de uso basados en audiencias. |
