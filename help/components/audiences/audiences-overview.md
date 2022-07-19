---
title: Información general sobre la publicación de audiencias de CJA
description: Obtenga información sobre el concepto de publicación de audiencias en Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
source-git-commit: 86998458bd79f1fc17c17e58932b2b8434abf041
workflow-type: ht
source-wordcount: '355'
ht-degree: 100%

---

# Información general sobre la publicación de audiencias de CJA

>[!NOTE]
>
>Actualmente, esta función está en [prueba limitada](/help/release-notes/releases.md).

Ahora puede crear y publicar audiencias que haya descubierto en Customer Journey Analytics (CJA) para el [Perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=es) (RTCP) en Adobe Experience Platform para la segmentación y personalización de clientes.

La publicación de audiencias proporciona una manera clara de activar y realizar acciones relacionadas con la información contenida en CJA. Estas acciones pueden incluir:

* Uso de la audiencia para un recorrido en Adobe Journey Optimizer.
* Exportación de la audiencia a un tercero mediante un destino de Experience Platform.
* Enriquecimiento del perfil del cliente en tiempo real con atributos útiles derivados de datos basados en eventos en CJA.
* Hacer todo esto con una latencia mínima después de publicar la audiencia (un par de minutos)
* Publicación de audiencias únicas o recurrentes

## Terminología clave

**Audiencia**: conjunto o lista de identidades que tienen un área de nombres y un ID específico relacionado con ese área de nombres. Las audiencias se pueden transportar desde Adobe Experience Platform y las aplicaciones que se basan en la herramienta (como CJA). Las audiencias pueden contener áreas de nombres mixtas.

**Filtro**: conjunto de reglas que, al evaluarse con un conjunto de datos durante un período de tiempo, produce un subconjunto de datos. Se puede utilizar un filtro en el proceso de creación de una audiencia cuando se asocia con otros servicios de respaldo. Los filtros se definen y mantienen en CJA.

**Filtros** en comparación con **Segmentos**: CJA no utiliza el concepto de «segmentos», sino que utiliza «filtros». Aunque ambos son un conjunto de reglas que pueden contener una lógica similar, producen resultados diferentes. Un filtro se utiliza para reducir un conjunto de datos con fines de análisis. Un segmento se utiliza para producir una lista de identidades que se puede utilizar para la activación. Los segmentos producen audiencias en el Perfil del cliente en tiempo real, mientras que los filtros (por sí solos) no. La publicación de audiencias de CJA es el proceso mediante el cual utilizamos un filtro de CJA para crear una audiencia que pueda ser consumida por el Perfil del cliente en tiempo real.

## Permisos

A los administradores se les concede automáticamente el permiso [!UICONTROL Publicación de audiencias] en Adobe Admin Console. Pueden conceder este permiso a usuarios individuales.

## Pasos siguientes

* [Crear y publicar audiencias](/help/components/audiences/publish.md)
* [Administrar audiencias](/help/components/audiences/manage.md)
