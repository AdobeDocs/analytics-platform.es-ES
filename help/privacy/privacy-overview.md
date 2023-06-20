---
title: Customer Journey Analytics y gobernanza de datos
description: Describe cómo funciona la gobernanza de datos en Customer Journey Analytics.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 68%

---

# Adobe Customer Journey Analytics y gobernanza de datos

En términos generales, cualquier configuración relacionada con la gobernanza de datos en Customer Journey Analytics se hereda de Adobe Experience Platform.

## Gobierno de datos

La integración entre Adobe Customer Journey Analytics y [Gobernanza de datos de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=es) permite el etiquetado de datos confidenciales del Customer Journey Analytics y la aplicación de políticas de privacidad.

Las etiquetas de privacidad y las políticas creadas en conjuntos de datos consumidos por Experience Platform se pueden ver en el flujo de trabajo de vistas de datos del Customer Journey Analytics. Estas etiquetas detienen o advierten a los usuarios que crean métricas o dimensiones a partir de campos confidenciales.

Además, cuando se exportan datos desde Customer Journey Analytics (mediante creación de informes, exportación, API, etc.), se añaden advertencias o etiquetas para notificar a los usuarios de que un informe contiene información confidencial que debe tratarse de una manera específica.

Esta integración le permite administrar el cumplimiento de normas más fácilmente. Los administradores de datos de su organización pueden establecer políticas para restringir el uso. Como resultado, los usuarios de Customer Journey Analytics pueden utilizar los datos con mayor seguridad, sabiendo que cumplen con las políticas definidas por los administradores de datos.

[Más información](/help/data-views/data-governance.md)

## RGPD

Customer Journey Analytics no se suscribirá directamente al servicio central del Reglamento general de protección de datos (RGPD) y, en su lugar, heredará todos los cambios de conjuntos de datos realizados en Experience Platform. Platform Data Lake se encarga de aplicar las solicitudes de eliminación del RGPD y de notificarnos cuando se hayan completado en la canalización. Prestamos atención a la canalización y sincronizamos todos los cambios realizados en lotes afectados en Customer Journey Analytics para los conjuntos de datos implicados en el evento. Los conjuntos de datos de perfil y búsqueda afectados por las solicitudes de eliminación del RGPD se volverán a ingerir completamente después de cada solicitud de eliminación. Garantizamos que las solicitudes de eliminación se ejecutarán en un plazo de 7 días después del evento de eliminación en Data Lake.

## CCPA

La Ley de Privacidad del Consumidor de California (CCPA) mejora los derechos de privacidad y la protección del consumidor para los residentes de California, Estados Unidos. Esta ley entró en vigor el 1 de enero de 2020.
La CCPA otorga nuevos derechos de privacidad de datos a los residentes de California, como el derecho a acceder a sus datos personales y eliminarlos, a saber si sus datos personales se venden o revelan (y a quién) y a rechazar la venta de sus datos personales.
De acuerdo con la CCPA, el Servicio de privacidad aceptará las solicitudes de exclusión de la venta de datos personales.
