---
title: Resumen de publicación de audiencias de Customer Journey Analytics
description: Obtenga información sobre el concepto de publicación de audiencias en Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 54%

---

# Resumen de publicación de audiencia de Customer Journey Analytics

Ahora puede crear y publicar audiencias descubiertas en Customer Journey Analytics a [Perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=es) (RTCDP) en Adobe Experience Platform para la segmentación y personalización de clientes.

Las audiencias de publicación proporcionan una forma clara de activar y actuar en función de las perspectivas que se encuentran en Customer Journey Analytics. Estas acciones pueden incluir:

* Uso de la audiencia para un recorrido en Adobe Journey Optimizer.
* Exportación de la audiencia a un tercero mediante un destino de Experience Platform.
* Enriquecimiento del perfil del cliente en tiempo real con atributos útiles derivados de datos basados en eventos en Customer Journey Analytics.
* Haciendo todo esto con una latencia mínima después de la publicación de la audiencia. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=es#latency)
* Publicación de audiencias únicas o recurrentes.

Las audiencias que cree en Customer Journey Analytics no tienen por qué basarse en conjuntos de datos habilitados para el perfil. Puede introducir datos históricos en Experience Platform sin habilitar los conjuntos de datos y esquemas asociados para el perfil. A continuación, utilice estos conjuntos de datos para detectar audiencias relevantes en Customer Journey Analytics y publique estas audiencias en RTCDP en Experience Platform para fines de activación.

## Terminología clave

**Audiencia**: conjunto o lista de identidades que tienen un área de nombres y un ID específico relacionado con ese área de nombres. Las audiencias se pueden transportar desde Adobe Experience Platform y las aplicaciones que se basan en la herramienta (como Customer Journey Analytics). Las audiencias pueden contener áreas de nombres mixtas.

**Filtro**: conjunto de reglas que, al evaluarse con un conjunto de datos durante un período de tiempo, produce un subconjunto de datos. Se puede utilizar un filtro en el proceso de creación de una audiencia cuando se asocia con otros servicios de respaldo. Los filtros se definen y mantienen en el Customer Journey Analytics.

**Filtros** frente **Segmentos**: El Customer Journey Analytics no utiliza el concepto de &quot;segmentos&quot;, sino que utiliza &quot;filtros&quot;. Aunque ambos son un conjunto de reglas que pueden contener una lógica similar, producen resultados diferentes. Un filtro se utiliza para reducir un conjunto de datos con fines de análisis. Un segmento se utiliza para producir una lista de identidades que se puede utilizar para la activación. Los segmentos producen audiencias en el Perfil del cliente en tiempo real, mientras que los filtros (por sí solos) no. La publicación de audiencias de Customer Journey Analytics es el proceso mediante el cual utilizamos un filtro de Customer Journey Analytics para crear una audiencia que pueda ser consumida por el Perfil del cliente en tiempo real.

## Permisos

* A los administradores se les concede automáticamente el permiso **[!UICONTROL Publicación de audiencias]** en Adobe Admin Console.

* Los administradores pueden conceder este permiso a usuarios individuales.

* También necesitan el permiso **[!UICONTROL Administrar perfiles]** en Adobe Experience Platform.

## Gobernanza de datos y consentimiento

Cuando publica una audiencia en Customer Journey Analytics, se registran las etiquetas y políticas de control de datos adjuntas a los campos utilizados en la audiencia.  Cuando la audiencia se activa en cualquier aplicación de Adobe Experience, todas las etiquetas y políticas de gobernanza de datos asociadas están disponibles para esa audiencia y se puede aplicar la aplicación correspondiente. [Más información sobre el consentimiento](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=es#consent-policy).

## Pasos siguientes

* [Crear y publicar audiencias](/help/components/audiences/publish.md)
* [Administrar audiencias](/help/components/audiences/manage.md)
