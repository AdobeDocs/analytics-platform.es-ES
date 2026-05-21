---
title: Etiquetas Restringidas En Report Builder
description: Obtenga información sobre las etiquetas restringidas en Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
TQID: https://experienceleague.adobe.com/MeHO7A9KWAjG8TyiOn9taPbtPhD47JGl88KSCoQwdMI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: f2ef16dc-055a-4bb7-baa5-7039653f3966
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 345
ht-degree: 36%

---

# Etiquetas restringidas en Report Builder

En general, la configuración relacionada con la gobernanza de datos en Customer Journey Analytics se hereda de Experience Platform. La integración entre Customer Journey Analytics y Gobernanza de datos de Experience Platform permite el etiquetado de datos confidenciales de Customer Journey Analytics y la aplicación de políticas de privacidad.

Las etiquetas de privacidad y las políticas creadas en conjuntos de datos consumidos por Experience Platform se pueden ver en el flujo de trabajo de vistas de datos de Customer Journey Analytics. Estas etiquetas detienen o advierten a los usuarios que crean métricas y dimensiones a partir de campos confidenciales. Para obtener información acerca de los conjuntos de datos, consulte [Información general sobre conjuntos de datos](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview)

Además, cuando se exportan datos desde Customer Journey Analytics (mediante la creación de informes, la exportación, la API, etc.), se añaden advertencias o etiquetas para notificar a los usuarios de que un informe contiene información confidencial que debe tratarse de una manera específica.

Esta integración le permite administrar el cumplimiento de normas. Los administradores de datos de su organización pueden establecer políticas para restringir el uso. Como resultado, los usuarios de Customer Journey Analytics pueden emplear los datos con mayor seguridad, sabiendo que cumplen con las políticas definidas por los administradores de datos.

Para obtener más información, consulte [Customer Journey Analytics y gobernanza de datos](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-privacy/privacy-overview)

## Ver datos restringidos

En Customer Journey Analytics aparecen dos políticas definidas por Adobe que afectan a la creación de informes, a la descarga y al uso compartido:

* Aplicación de la directiva de Analytics
* Aplicación de la directiva de descarga

Los componentes sujetos a estas directivas aparecen atenuados y no tienen un icono ![InfoOutline](/help/assets/icons/InfoOutline.svg). Cuando pasa el ratón sobre el icono de información, se muestra una nota para indicar lo siguiente: **[!UICONTROL Se han aplicado directivas a este campo que prohíben el uso de estos datos]**.

Para obtener más información, consulte [Etiquetas y directivas](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-governance).


![La nota de directiva que indica el uso prohibido de los datos.](assets/restricted-label.png){zoomable="yes"}


## Actualizar informes que contienen datos restringidos

En los casos en los que un usuario ha creado un informe de Report Builder con elementos de datos que se restrinjan posteriormente, cuando se actualiza el informe, se muestra un mensaje de error.

![El mensaje de error que se muestra después de restringir los elementos de datos.](assets/error-restricted-data.png){width="100%" zoomable="yes"}
