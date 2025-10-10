---
title: Obtenga información sobre la información general de publicación de públicos de Customer Journey Analytics
description: Obtenga información sobre el concepto de publicación de públicos en Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
feature: Audiences
role: User, Admin
source-git-commit: be062e350a8c1989be41aeb2774471a3fe1bf524
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 100%

---

# Información general sobre la publicación de públicos

Ahora puede crear y publicar públicos que haya descubierto en Customer Journey Analytics para el [Perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=es) en Adobe Experience Platform para la segmentación y personalización de clientes. 

La publicación de públicos proporciona una manera clara de activar y realizar acciones relacionadas con la información contenida en Customer Journey Analytics. Estas acciones pueden incluir:

* Uso del público para un recorrido en Adobe Journey Optimizer.
Para obtener más información sobre el uso de públicos que se publican en Experience Platform, consulte [Introducción a los públicos](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/audiences-profiles-identities/audiences/about-audiences) en la documentación de Journey Optimizer.
* Exportación del público a un tercero mediante un destino de Experience Platform.
* Enriquecimiento del perfil del cliente en tiempo real con atributos útiles derivados de datos basados en eventos en Customer Journey Analytics.
* Hacer todo esto con una latencia mínima después de la publicación del público.
Para obtener más información, consulte [Consideraciones sobre la latencia](/help/components/audiences/publish.md#latency-considerations) en [Creación y publicación de públicos](/help/components/audiences/publish.md).
* Publicación de públicos únicos o recurrentes

Los públicos que cree en Customer Journey Analytics no tienen por qué basarse en conjuntos de datos habilitados para el perfil. Puede introducir datos históricos en Experience Platform sin habilitar los conjuntos de datos y esquemas asociados para el perfil. A continuación, utilice estos conjuntos de datos para detectar públicos relevantes en Customer Journey Analytics y publicar estos públicos en el Perfil del cliente en tiempo real en Experience Platform para su activación.

## Terminología clave

**Público**: conjunto o lista de identidades que tienen un área de nombres y un ID específico relacionado con ese área de nombres. Los públicos se pueden transportar desde Adobe Experience Platform y las aplicaciones que se basan en la herramienta (como Customer Journey Analytics). Los públicos pueden contener áreas de nombres mixtas.

**Segmento**: Conjunto de reglas que, al evaluarse con un conjunto de datos durante un período de tiempo, produce un subconjunto de datos. Se puede utilizar un segmento en el proceso de creación de un público cuando se asocia con otros servicios de respaldo. Los filtros se definen y mantienen en Customer Journey Analytics.

## Permisos

* A los administradores se les concede automáticamente el permiso **[!UICONTROL Publicación de públicos]** en Adobe Admin Console.

* Los administradores y los administradores de perfil de producto pueden conceder el permiso **[!UICONTROL Creación de públicos]** y **[!UICONTROL Vista de públicos]** a usuarios individuales. Consulta [Control de acceso de nivel de usuario](/help/technotes/access-control.md#user-level-access) para obtener más información.

* También necesitan el permiso **[!UICONTROL Administrar perfiles]** en Adobe Experience Platform.

## Gobernanza de datos y consentimiento

Cuando publica un público en Customer Journey Analytics, se registran las etiquetas y políticas de gobernanza de datos adjuntas a los campos utilizados en el público.  Cuando el público se activa en cualquier aplicación de Adobe Experience, todas las etiquetas y políticas de gobernanza de datos asociadas están disponibles para ese público y se puede aplicar la aplicación correspondiente. [Más información sobre el consentimiento](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=es#consent-policy).

## Pasos siguientes

* [Creación y publicación de públicos](/help/components/audiences/publish.md)
* [Administrar públicos](/help/components/audiences/manage.md)
