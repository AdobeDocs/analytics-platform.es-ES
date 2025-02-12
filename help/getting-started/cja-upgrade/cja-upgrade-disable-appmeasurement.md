---
title: Adición del conjunto de datos del conector de origen de Analytics a la conexión
description: Obtenga información sobre cómo agregar el conjunto de datos del conector de origen de Analytics a la conexión
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 71b9da74-3597-4536-9e47-f18097dd917b
source-git-commit: 3b1012a302200192fd31fd6a9ed94f96323eb595
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 9%

---

# Deshabilitación de la recopilación de datos de AppMeasurement {#disable-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement"
>title="Deshabilitación de la recopilación de datos de AppMeasurement"
>abstract="Con los datos de Web SDK completamente funcionales, colabore con su equipo de desarrolladores para eliminar AppMeasurement.js de su sitio web o propiedad.<br><br>El acto de quitar AppMeasurement de un sitio web tarda unos minutos, pero el equipo de ingeniería debe detenerse para completarlo. Sin embargo, asegúrese de que los usuarios de Analytics usen Customer Journey Analytics y no Adobe Analytics; este proceso de anuncio para mover a todos puede tardar mucho más si aún no lo ha hecho."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Siga los pasos de esta página solo después de completar todos los pasos de actualización anteriores. Puede seguir los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), o puede seguir los pasos de actualización que se generaron dinámicamente para su organización con el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>Después de completar los pasos de esta página, siga los pasos de actualización recomendados o los pasos de actualización generados dinámicamente.

<!-- need to work on this -->

* **Etiquetas:** Deshabilitar la extensión de Adobe Analytics

* **AppMeasurement:** Reemplace la biblioteca AppMeasurement.js s s=newobject
