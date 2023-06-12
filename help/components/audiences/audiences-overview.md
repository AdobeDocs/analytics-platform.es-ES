---
title: Información general sobre la publicación de audiencias de CJA
description: Obtenga información sobre el concepto de publicación de audiencias en Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
source-git-commit: 7b86650cd3475a203d597baeec2ec2152e082b10
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 83%

---

# Información general sobre la publicación de audiencias de CJA

Ahora puede crear y publicar audiencias descubiertas en Customer Journey Analytics (CJA) para [Perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=es) (RTCDP) en Adobe Experience Platform para la segmentación y personalización de clientes.

La publicación de audiencias proporciona una manera clara de activar y realizar acciones relacionadas con la información contenida en CJA. Estas acciones pueden incluir:

* Uso de la audiencia para un recorrido en Adobe Journey Optimizer.
* Exportación de la audiencia a un tercero mediante un destino de Experience Platform.
* Enriquecimiento del perfil del cliente en tiempo real con atributos útiles derivados de datos basados en eventos en CJA.
* Haciendo todo esto con una latencia mínima después de la publicación de la audiencia. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=es#latency)
* Publicación de audiencias únicas o recurrentes.

Las audiencias que cree en CJA no tienen por qué basarse en conjuntos de datos habilitados para el perfil. Puede introducir datos históricos en Experience Platform sin habilitar los conjuntos de datos y esquemas asociados para el perfil. A continuación, utilice estos conjuntos de datos para detectar audiencias relevantes en CJA y publicar estas audiencias en RTCDP en Experience Platform para fines de activación.

## Terminología clave

**Audiencia**: conjunto o lista de identidades que tienen un área de nombres y un ID específico relacionado con ese área de nombres. Las audiencias se pueden transportar desde Adobe Experience Platform y las aplicaciones que se basan en la herramienta (como CJA). Las audiencias pueden contener áreas de nombres mixtas.

**Filtro**: conjunto de reglas que, al evaluarse con un conjunto de datos durante un período de tiempo, produce un subconjunto de datos. Se puede utilizar un filtro en el proceso de creación de una audiencia cuando se asocia con otros servicios de respaldo. Los filtros se definen y mantienen en CJA.

**Filtros** en comparación con **Segmentos**: CJA no utiliza el concepto de “segmentos”, sino que utiliza “filtros”. Aunque ambos son un conjunto de reglas que pueden contener una lógica similar, producen resultados diferentes. Un filtro se utiliza para reducir un conjunto de datos con fines de análisis. Un segmento se utiliza para producir una lista de identidades que se puede utilizar para la activación. Los segmentos producen audiencias en el Perfil del cliente en tiempo real, mientras que los filtros (por sí solos) no. La publicación de audiencias de CJA es el proceso mediante el cual utilizamos un filtro de CJA para crear una audiencia que pueda ser consumida por el Perfil del cliente en tiempo real.

## Permisos

* A los administradores se les concede automáticamente el permiso **[!UICONTROL Publicación de audiencias]** en Adobe Admin Console.

* Los administradores pueden conceder este permiso a usuarios individuales.

* También necesitan el permiso **[!UICONTROL Administrar perfiles]** en Adobe Experience Platform.

## Gobernanza de datos y consentimiento

Cuando publica una audiencia en CJA, se registran las etiquetas y políticas de gobernanza de datos adjuntas a los campos utilizados en la audiencia.  Cuando la audiencia se activa en cualquier aplicación de Adobe Experience, todas las etiquetas y políticas de gobernanza de datos asociadas están disponibles para esa audiencia y se puede aplicar la aplicación correspondiente. [Más información sobre el consentimiento](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=es#consent-policy).

## Pasos siguientes

* [Crear y publicar audiencias](/help/components/audiences/publish.md)
* [Administrar audiencias](/help/components/audiences/manage.md)
