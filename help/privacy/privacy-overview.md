---
title: Información general sobre la privacidad de Análisis de viajes del cliente
description: Describe cómo funciona la configuración de privacidad en el análisis de viajes del cliente.
translation-type: tm+mt
source-git-commit: 415a4a7f7d540a0329f973042d1c6a6a285d5b1b

---


# Información general sobre la privacidad de Análisis de viajes del cliente

En términos generales, cualquier configuración relacionada con la privacidad en el análisis de viajes del cliente se hereda de Adobe Experience Platform.

## GDPR

Customer Journey Analytics no se suscribirá directamente al servicio central del Reglamento general de protección de datos (RGPD) y, en su lugar, heredará todos los cambios de conjuntos de datos realizados en la plataforma de experiencia. Dependemos del lago de datos de plataforma para aplicar las solicitudes de eliminación del RGPD y notificarnos cuando se hayan completado con Pipeline. Escuchamos Pipeline y sincronizamos todos los cambios realizados en lotes afectados en el análisis del viaje del cliente para conjuntos de datos de evento. Los conjuntos de datos de Perfil y búsqueda afectados por las solicitudes de eliminación del RGPD se volverán a ingerir completamente después de cada solicitud de eliminación. Podemos garantizar que las solicitudes de eliminación se ejecuten dentro de los 7 días posteriores a un evento de eliminación en Data Lake.

## CCPA

La Ley de Privacidad del Consumidor de California (CCPA) mejora los derechos de privacidad y la protección del consumidor para los residentes de California, Estados Unidos. Esta ley entrará en vigor el 1 de enero de 2020.
La CCPA otorga nuevos derechos de privacidad de datos a los residentes de California, como el derecho a acceder y eliminar sus datos personales, a saber si sus datos personales se venden o revelan (y a quién) y a rechazar la venta de sus datos personales.
En previsión de la CCPA, el Servicio de privacidad aceptará las solicitudes de exclusión de la venta de datos personales.
