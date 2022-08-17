---
title: ¿Qué son las etiquetas restringidas en el Report Builder?
description: Describe las etiquetas restringidas en el Report Builder
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
source-git-commit: 72e6c568ccad4c5f74612a1f19758a7b41746836
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%

---

# Etiquetas restringidas en el Report Builder

Por lo general, la configuración relacionada con el control de datos en Customer Journey Analytics se hereda de Adobe Experience Platform. La integración entre CJA y la Administración de datos de Adobe Experience Platform permite el etiquetado de datos de CJA confidenciales y la aplicación de políticas de privacidad.

Las etiquetas de privacidad y las políticas creadas en conjuntos de datos consumidos por el Experience Platform se pueden ver en el flujo de trabajo de vistas de datos de CJA. Estas etiquetas detienen o advierten a los usuarios que crean métricas y/o dimensiones a partir de campos confidenciales. Para obtener información sobre conjuntos de datos, consulte [Información general sobre conjuntos de datos](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html)

Además, cuando se exportan datos desde CJA (mediante informes, exportación, API, etc.), se añaden advertencias o etiquetas para notificar a los usuarios que un informe contiene información confidencial que debe tratarse de una manera específica.

Esta integración le permite administrar el cumplimiento de normas más fácilmente. Los administradores de datos de su organización pueden establecer políticas para restringir el uso. Como resultado, los usuarios de CJA pueden usar los datos con mayor seguridad, sabiendo que cumplen con las políticas definidas por los administradores de datos.

Para obtener más información, consulte [Customer Journey Analytics y administración de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html)

## Ver datos restringidos en el Report Builder

En CJA aparecen dos políticas definidas por Adobe que afectan a los informes, las descargas y el uso compartido:

* Aplicar directiva de Analytics
* Aplicar directiva de descarga

Los componentes afectados por estas políticas aparecen atenuados. Cuando pasa el ratón sobre un componente que tiene una política aplicada, se muestra una nota para indicar lo siguiente: **Se han aplicado políticas a este campo que prohíben el uso de estos datos.** Para obtener más información, consulte [Etiquetas y políticas](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html).

![](assets/rb-restricted-label.png)

## Actualizar informes que contengan datos restringidos

En los casos en los que un usuario ha creado un informe de Report Builder con elementos de datos que se restrinjan posteriormente, cuando se actualiza el informe, se muestra un mensaje de error.

![](assets/error-restricted-data.png)
