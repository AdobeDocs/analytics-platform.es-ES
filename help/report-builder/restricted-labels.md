---
title: Qué son las etiquetas restringidas en Report Builder
description: Describe las etiquetas restringidas en Report Builder
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
source-git-commit: 49a35a256758b259dfb2133658bae617315774e4
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 57%

---

# Etiquetas restringidas en Report Builder

En general, la configuración relacionada con la gobernanza de datos en Customer Journey Analytics se hereda de Adobe Experience Platform. La integración entre Customer Journey Analytics y Gobernanza de datos de Adobe Experience Platform permite el etiquetado de datos confidenciales del Customer Journey Analytics y la aplicación de políticas de privacidad.

Las etiquetas de privacidad y las políticas creadas en conjuntos de datos consumidos por Experience Platform se pueden ver en el flujo de trabajo de vistas de datos del Customer Journey Analytics. Estas etiquetas detienen o advierten a los usuarios que crean métricas o dimensiones a partir de campos confidenciales. Para obtener información acerca de los conjuntos de datos, consulte [Información general sobre conjuntos de datos](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=es)

Además, cuando se exportan datos desde Customer Journey Analytics (mediante creación de informes, exportación, API, etc.), se añaden advertencias o etiquetas para notificar a los usuarios de que un informe contiene información confidencial que debe tratarse de una manera específica.

Esta integración le permite administrar el cumplimiento de normas más fácilmente. Los administradores de datos de su organización pueden establecer políticas para restringir el uso. Como resultado, los usuarios de Customer Journey Analytics pueden utilizar los datos con mayor seguridad, sabiendo que cumplen con las políticas definidas por los administradores de datos.

Para obtener más información, consulte [Customer Journey Analytics y gobernanza de datos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html?lang=es)

## Visualización de datos restringidos en Report Builder

En Customer Journey Analytics aparecen dos directivas definidas por el Adobe que afectan a la creación de informes, a la descarga y al uso compartido:

* Aplicación de la directiva de Analytics
* Aplicación de la directiva de descarga

Los componentes afectados por estas directivas aparecen atenuados. Cuando pasa el ratón sobre un componente que tiene una directiva aplicada, se muestra una nota para indicar lo siguiente: **Se han aplicado directivas a este campo que prohíben el uso de estos datos.** Para obtener más información, consulte [Etiquetas y directivas](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html?lang=es).

![La nota de política que indica el uso prohibido de los datos.](assets/rb-restricted-label.png)

## Actualización de informes que contengan datos restringidos

En los casos en los que un usuario ha creado un informe de Report Builder con elementos de datos que se restrinjan posteriormente, cuando se actualiza el informe, se muestra un mensaje de error.

![El mensaje de error mostrado después de restringir los elementos de datos.](assets/error-restricted-data.png)
