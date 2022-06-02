---
title: Información general sobre la publicación de Audiencias de CJA
description: Obtenga información sobre el concepto de publicación de audiencias en Customer Journey Analytics
source-git-commit: 7164c90fe50434a07db8154de173c3c7d8e5cb14
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 3%

---


# Información general sobre la publicación de Audiencias de CJA

Ahora puede publicar audiencias descubiertas en Customer Journey Analytics (CJA) en [Perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=es) en Adobe Experience Platform para personalización y segmentación de clientes. Con Perfil del cliente en tiempo real, puede ver una vista holística de cada cliente combinando datos de varios canales, incluidos en línea, sin conexión, CRM y de terceros. El perfil le permite consolidar los datos de sus clientes en una vista unificada que ofrece una cuenta procesable con marca de tiempo de cada interacción con los clientes.

La publicación de audiencias proporciona una manera clara de realizar acciones con respecto a las perspectivas que se encuentran dentro de CJA. Estas acciones pueden incluir:

* Envío de correos electrónicos a esta audiencia.
* Envío de mensajes push a esta audiencia.
* Uso de la audiencia para un recorrido en Adobe Journey Optimizer.
* Exportación de la audiencia a un tercero mediante un destino de AEP

## Terminología clave

**Audiencia**: Conjunto o lista de identidades que tienen un área de nombres y un ID específico relacionados con ese área de nombres. Las audiencias se pueden transportar desde Adobe Experience Platform y las aplicaciones que se encuentran encima (como CJA). Las audiencias pueden contener espacios de nombres mixtos.

**Filtro**: Conjunto de reglas que, al evaluarse sobre un conjunto de datos durante un período de tiempo, produce un subconjunto de datos. Se puede utilizar un filtro en el proceso de creación de una audiencia cuando se asocia con otros servicios de soporte. Los filtros se definen y mantienen en CJA.

**Filtros** versus **Segmentos**: CJA no utiliza el concepto de &quot;segmentos&quot;, sino que utiliza &quot;filtros&quot;. Aunque ambas son un conjunto de reglas que pueden contener una lógica similar, producen resultados diferentes. Un filtro se utiliza para reducir un conjunto de datos con fines de análisis. Un segmento se utiliza para producir una lista de identidades que se pueden utilizar para la activación. Los segmentos producen audiencias en el Perfil del cliente en tiempo real, mientras que los filtros (por sí solos) no. La Publicación de audiencias de CJA es el proceso mediante el cual utilizamos un filtro de CJA para crear una audiencia que pueda ser consumida por el Perfil del cliente en tiempo real.

## Permisos

A los administradores se les concede automáticamente el [!UICONTROL Publicación de audiencias] en Adobe Admin Console. Pueden conceder este permiso a usuarios individuales.

## Pasos siguientes



