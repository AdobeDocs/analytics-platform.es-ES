---
title: Adición del conjunto de datos del conector de origen de Analytics a la conexión
description: Obtenga información sobre cómo agregar el conjunto de datos del conector de origen de Analytics a la conexión
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 71b9da74-3597-4536-9e47-f18097dd917b
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 9%

---

# Deshabilitar Adobe Analytics {#disable-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement"
>title="Deshabilitación de la recopilación de datos de AppMeasurement"
>abstract="Con los datos de Web SDK completamente funcionales, colabore con su equipo de desarrolladores para eliminar AppMeasurement.js de su sitio web o propiedad.<br><br>El acto de quitar AppMeasurement de un sitio web tarda unos minutos, pero el equipo de ingeniería debe detenerse para completarlo. Sin embargo, asegúrese de que los usuarios de Analytics usen Customer Journey Analytics y no Adobe Analytics; este proceso de anuncio para mover a todos puede tardar mucho más si aún no lo ha hecho."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Antes de deshabilitar Adobe Analytics, revise la información de [Evalúe cuándo deshabilitar Adobe Analytics después de actualizar a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md).

* **Etiquetas:** Deshabilitar la extensión de Adobe Analytics

* **AppMeasurement:** Reemplace la biblioteca AppMeasurement.js s s=newobject
