---
title: Customer Journey Analytics y gobernanza de datos
description: Describe cómo funciona la gobernanza de datos en Customer Journey Analytics.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
feature: Privacy
role: Admin
hold: true
autotag-review: '2026-05-19T09:18:17.400Z'
TQID: 'https://experienceleague.adobe.com/oDdNRwjtEU2vmeDvQ3DcM8w6XKQTBoTaXAIhmgjSoBk'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 116c169326e98f4e3d649c2fe72dbff44eaa0225
workflow-type: tm+mt
source-wordcount: 560
ht-degree: 88%

---

# Adobe Customer Journey Analytics y la gobernanza de datos

En términos generales, cualquier configuración relacionada con la gobernanza de datos en Customer Journey Analytics se hereda de Adobe Experience Platform.

## Gobernanza de datos

La integración entre Customer Journey Analytics y la [Gobernanza de datos de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=es) permite etiquetar datos confidenciales de Customer Journey Analytics y aplicar directivas de privacidad.

Las etiquetas de privacidad y las políticas creadas en conjuntos de datos consumidos por Experience Platform pueden aparecer en el flujo de trabajo de vistas de datos de Customer Journey Analytics. Estas etiquetas detienen o advierten a los usuarios que crean métricas o dimensiones a partir de campos confidenciales.

Además, cuando se exportan datos desde Customer Journey Analytics (mediante la creación de informes, la exportación, la API, etc.), se añaden advertencias o etiquetas para notificar a los usuarios de que un informe contiene información confidencial que debe tratarse de una manera específica.

Esta integración le permite administrar el cumplimiento de normas más fácilmente. Los administradores de datos de su organización pueden establecer políticas para restringir el uso. Como resultado, los usuarios de Customer Journey Analytics pueden emplear los datos con mayor seguridad, sabiendo que cumplen con las políticas definidas por los administradores de datos.

[Más información](/help/data-views/data-governance.md)

## Informes y filtrado de consentimiento

Customer Journey Analytics puede utilizar los datos de pertenencia a directivas de consentimiento de los conjuntos de datos de perfil de Experience Platform para informar sobre el consentimiento del visitante y, opcionalmente, excluir a los visitantes que no consientan antes de que se incorporen sus datos. La creación de informes de consentimiento hace que las políticas de consentimiento estén disponibles como componentes en Analysis Workspace y el filtrado de consentimiento excluye a los visitantes que no consienten en el momento de la ingesta en función de las acciones de marketing que configure.

[Más información](/help/connections/consent-reporting-filtering/consent-overview.md)

## Solicitudes de privacidad

Adobe gestiona las solicitudes de privacidad de acuerdo con las leyes locales e internacionales aplicables.

Como Customer Journey Analytics usa datos que están disponibles en Adobe Experience Platform, Adobe ofrece [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=es) para enviar solicitudes de acceso y de eliminación de datos. Las solicitudes aplican tanto a los conjuntos de datos originales como a aquellos cuyas claves se volvieron a generar.

## RGPD

Customer Journey Analytics no se suscribirá directamente al servicio central del Reglamento general de protección de datos (RGPD) y, en su lugar, heredará todos los cambios de conjuntos de datos realizados en Experience Platform. Customer Journey Analytics depende del lago de datos de Platform para aplicar las solicitudes de eliminación de RGPD y notificárselo a Customer Journey Analytics cuando se completen las solicitudes. Todos los cambios realizados en los lotes afectados de Customer Journey Analytics para los conjuntos de datos de evento se sincronizan con los datos de Platform. Los conjuntos de datos de perfil y consulta afectados por las solicitudes de eliminación del RGPD se volverán a ingerir completamente después de cada solicitud de eliminación. Las solicitudes de eliminación suelen finalizar en un plazo de 7 días después del evento de eliminación en el lago de datos.

## CCPA

La Ley de Privacidad del Consumidor de California (CCPA) mejora los derechos de privacidad y la protección del consumidor para los residentes de California, Estados Unidos. Esta ley entró en vigor el 1 de enero de 2020.La CCPA otorga nuevos derechos de privacidad de datos a los residentes de California, como el derecho a acceder a sus datos personales y eliminarlos, a saber si sus datos personales se venden o revelan (y a quién) y a rechazar la venta de sus datos personales.De acuerdo con la CCPA, el Servicio de privacidad aceptará las solicitudes de exclusión de la venta de datos personales.

>[!MORELIKETHIS]
>
>* [Blog: Mantenimiento de la gobernanza efectiva en Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/bg-p/adobe-analytics-blogs/page/4?profile.language=es)
