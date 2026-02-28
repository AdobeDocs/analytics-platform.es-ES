---
title: Comprender las funciones exclusivas de Customer Journey Analytics
description: Obtenga información sobre las funciones exclusivas de Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4e6cacb9-4eca-4dfb-bce4-e69850507596
source-git-commit: 153828839bbed493ae12c4969c69195b4beeaab1
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 91%

---

# Comprender las funciones exclusivas de Customer Journey Analytics {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tie-data"
>title="Vinculación de datos de distintas fuentes"
>abstract="(Recomendado) Vincule datos de varias propiedades web, móviles y sin conexión para crear una única vista consolidada del comportamiento de los clientes. La posibilidad de combinar datos de análisis de otros canales es el caso de uso principal de Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-datasets"
>title="Unión de visitas de varios conjuntos de datos"
>abstract="Si alguno de los conjuntos de datos no comparte un identificador principal (como un ID de Experience Cloud), aún puede unir esos datos mediante otra dimensión, como el nombre de usuario de inicio de sesión o la dirección de correo electrónico."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-customer-care"
>title="Habilitar la vinculación para uno o varios conjuntos de datos"
>abstract="Si tiene un campo que contiene un identificador que existe en varios conjuntos de datos, pero no es el identificador principal, puede utilizar la vinculación para elevar los datos a uno o más de estos conjuntos de datos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-rtcdp"
>title="Integración con Real-time CDP"
>abstract="Combine datos de perfil de varias fuentes para generar públicos y segmentos basados en rasgos de usuario."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-target"
>title="Integrar temporalmente con Adobe Target"
>abstract="Adobe recomienda integrar con Adobe Journey Optimizer para casos de uso de personalización. La integración con Adobe Target es posible, pero es una solución temporal."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-ajo"
>title="Integrar con Journey Optimizer"
>abstract="Ofrezca a sus clientes experiencias conectadas, contextuales y personalizadas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-aam"
>title="Integrar temporalmente con Adobe Audience Manager"
>abstract="Adobe recomienda integrar con Adobe Real-time CDP para casos de uso basados en públicos. La integración con Audience Manager es posible, pero es una solución temporal."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

La siguiente lista muestra solo las funciones de Customer Journey Analytics que deben tenerse en cuenta durante el proceso de actualización. Para obtener una lista completa que muestre qué características de Adobe Analytics son totalmente compatibles, parcialmente compatibles o no compatibles con Customer Journey Analytics, consulte [Compatibilidad con funcionalidades de Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

Tenga en cuenta cuál de las siguientes funciones de Customer Journey Analytics desea adoptar al actualizar a Customer Journey Analytics:

| Funcionalidad de Customer Journey Analytics | Función |
|---------|----------|
| [Vinculación de datos web con datos de otras fuentes, como datos de centros de llamadas](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | Customer Journey Analytics se combina con la capacidad de Experience Platform para albergar todo tipo de esquemas y datos. Con [Modelo de datos de experiencia (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es), los datos se pueden representar y organizar de forma uniforme, listos para la combinación y exploración. Adobe Analytics se centra principalmente en los datos de análisis web y móviles con algunas funcionalidades para [importar datos](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=es). |
| [Una los resultados de otros conjuntos de datos mediante una dimensión personalizada](https://experienceleague.adobe.com/es/docs/analytics-platform/using/stitching/overview) | Customer Journey Analytics le permite [combinar datos](/help/connections/combined-dataset.md) de varios grupos de informes como si fueran un único grupo de informes de Adobe Analytics. |
| [Integración con Adobe Real-Time CDP](/help/components/audiences/audiences-overview.md) | Ahora puede [crear y publicar los públicos](/help/components/audiences/audiences-overview.md) que haya identificado en Customer Journey Analytics (CJA) en el Perfil del cliente en tiempo real (RTCP) de Adobe Experience Platform para la segmentación y personalización de clientes.  |
| [Integrar con Adobe Target (A4T)](/help/integrations/at.md) | Los informes de Target en Customer Journey Analytics le permiten [medir e informar sobre las actividades de Adobe Target](/help/integrations/at.md) directamente en Customer Journey Analytics. Adobe recomienda integrar con Adobe Journey Optimizer para casos de uso de personalización.  |
| [Integración con Adobe Journey Optimizer](/help/integrations/ajo.md) | Puede configurar los datos generados por Journey Optimizer para [realizar análisis avanzados en Customer Journey Analytics](/help/integrations/ajo.md).  |
| [Integrar con Adobe Audience Manager](https://experienceleague.adobe.com/es/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing) | Puede [compartir rasgos y segmentos de Audience Manager con Adobe Experience Platform](https://experienceleague.adobe.com/es/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing). No obstante, Adobe recomienda integrar con Adobe Real-time CDP para casos de uso basados en públicos.  |
