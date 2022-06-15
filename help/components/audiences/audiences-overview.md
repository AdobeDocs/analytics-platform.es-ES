---
title: Información general sobre la publicación de Audiencias de CJA
description: Obtenga información sobre el concepto de publicación de audiencias en Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
source-git-commit: 1abc116892405772530e8c254299b40167613656
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 3%

---

# Información general sobre la publicación de Audiencias de CJA

Ahora puede crear y publicar audiencias descubiertas en Customer Journey Analytics (CJA) para [Perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=es) (RTCP) en Adobe Experience Platform para personalización y segmentación de clientes.

La publicación de audiencias proporciona una manera clara de activar y realizar acciones en las perspectivas que se encuentran dentro de CJA. Estas acciones pueden incluir:

* Uso de la audiencia para un recorrido en Adobe Journey Optimizer.
* Exportación de la audiencia a un tercero mediante un destino de Experience Platform.
* Enriquecimiento del perfil del cliente en tiempo real con atributos útiles derivados de datos basados en eventos en CJA.
* Hacer todo esto con una latencia mínima después de publicar la audiencia (un par de minutos)
* Publicación de audiencias únicas o recurrentes

## Terminología clave

**Audiencia**: Conjunto o lista de identidades que tienen un área de nombres y un ID específico relacionados con ese área de nombres. Las audiencias se pueden transportar desde Adobe Experience Platform y las aplicaciones que se encuentran encima (como CJA). Las audiencias pueden contener espacios de nombres mixtos.

**Filtro**: Conjunto de reglas que, al evaluarse sobre un conjunto de datos durante un período de tiempo, produce un subconjunto de datos. Se puede utilizar un filtro en el proceso de creación de una audiencia cuando se asocia con otros servicios de soporte. Los filtros se definen y mantienen en CJA.

**Filtros** versus **Segmentos**: CJA no utiliza el concepto de &quot;segmentos&quot;, sino que utiliza &quot;filtros&quot;. Aunque ambas son un conjunto de reglas que pueden contener una lógica similar, producen resultados diferentes. Un filtro se utiliza para reducir un conjunto de datos con fines de análisis. Un segmento se utiliza para producir una lista de identidades que se pueden utilizar para la activación. Los segmentos producen audiencias en el Perfil del cliente en tiempo real, mientras que los filtros (por sí solos) no. La Publicación de audiencias de CJA es el proceso mediante el cual utilizamos un filtro de CJA para crear una audiencia que pueda ser consumida por el Perfil del cliente en tiempo real.

## Permisos

A los administradores se les concede automáticamente el [!UICONTROL Publicación de audiencias] en Adobe Admin Console. Pueden conceder este permiso a usuarios individuales.

## Pasos siguientes

* [Crear y publicar audiencias](/help/components/audiences/publish.md)
* [Administrar audiencias](/help/components/audiences/manage.md)
