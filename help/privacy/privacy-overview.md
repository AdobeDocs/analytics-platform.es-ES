---
title: Información general sobre la privacidad de Customer Journey Analytics
description: Describe cómo funciona la configuración de privacidad en Customer Journey Analytics.
translation-type: tm+mt
source-git-commit: 415a4a7f7d540a0329f973042d1c6a6a285d5b1b
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 100%

---


# Información general sobre la privacidad de Customer Journey Analytics

En términos generales, cualquier configuración relacionada con la privacidad en Customer Journey Analytics se hereda de Adobe Experience Platform.

## RGPD

Customer Journey Analytics no se suscribirá directamente al servicio central del Reglamento general de protección de datos (RGPD) y, en su lugar, heredará todos los cambios de conjuntos de datos realizados en Experience Platform. Platform Data Lake se encarga de aplicar las solicitudes de eliminación del RGPD y de notificarnos cuando se hayan completado en la canalización. Prestamos atención a la canalización y sincronizamos todos los cambios realizados en lotes afectados en Customer Journey Analytics para los conjuntos de datos implicados en el evento. Los conjuntos de datos de perfil y búsqueda afectados por las solicitudes de eliminación del RGPD se volverán a ingerir completamente después de cada solicitud de eliminación. Garantizamos que las solicitudes de eliminación se ejecutarán en un plazo de 7 días después del evento de eliminación en Data Lake.

## CCPA

La Ley de Privacidad del Consumidor de California (CCPA) mejora los derechos de privacidad y la protección del consumidor para los residentes de California, Estados Unidos. Esta ley entrará en vigor el 1 de enero de 2020.
La CCPA otorga nuevos derechos de privacidad de datos a los residentes de California, como el derecho a acceder y eliminar sus datos personales, a saber si sus datos personales se venden o revelan (y a quién) y a rechazar la venta de sus datos personales.
En previsión de la CCPA, el Servicio de privacidad aceptará las solicitudes de exclusión de la venta de datos personales.
