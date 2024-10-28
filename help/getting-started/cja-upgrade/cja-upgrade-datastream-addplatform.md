---
title: Crear un esquema para el Customer Journey Analytics
description: Obtenga información acerca de la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 29%

---

# Añadir Platform como servicio al conjunto de datos

>[!NOTE]
>
>Esta documentación se debe usar después de completar el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
> 
>Siga los pasos de esta página solo después de completar todos los pasos anteriores generados dinámicamente para su organización.
>
>Después de completar los pasos de esta página, continúe siguiendo los pasos de actualización que se generaron dinámicamente para su organización desde el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Debe existir una secuencia de datos antes de completar los pasos de esta sección. El momento y el modo en que se creó el conjunto de datos dependen de la implementación de Adobe Analytics, de la siguiente manera:

* Si la implementación de Adobe Analytics utiliza el SDK web o la extensión del SDK web, el conjunto de datos estaba disponible para el entorno de Adobe Analytics antes del proceso de actualización.

* Para otras implementaciones de Adobe Analytics, la creación de un conjunto de datos forma parte del proceso de actualización, tal como se describe en [Crear un conjunto de datos para utilizarlo con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

Con la secuencia de datos disponible, debe agregar Platform como servicio:

1. En la interfaz de usuario de Adobe Experience Platform, seleccione **[!UICONTROL Secuencias de datos]** desde [!UICONTROL RECOPILACIÓN DE DATOS] en el carril izquierdo.

1. Seleccione la secuencia de datos configurada anteriormente. <!--true?-->

1. Seleccione **[!UICONTROL Agregar servicio]**.

1. En la pantalla [!UICONTROL Agregar servicio], debe hacer lo siguiente:

   1. Seleccione **[!UICONTROL Adobe Experience Platform]** en la lista [!UICONTROL Servicio].

   1. Asegúrese de que **[!UICONTROL Habilitado]** esté seleccionado.

   1. Seleccione su conjunto de datos en la lista [!UICONTROL Conjunto de datos de evento].

      ![Servicio AEP de secuencia de datos](./assets/datastream-aep-service.png)

   1. Deje los demás ajustes y seleccione **[!UICONTROL Guardar]** para guardar la secuencia de datos.

   La secuencia de datos ya está configurada para reenviar los datos recopilados de su sitio web a su conjunto de datos en Adobe Experience Platform.

   Consulte la [Información general sobre secuencias de datos](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html) para obtener más información sobre cómo configurar una secuencia de datos y cómo gestionar datos confidenciales.

1. Continúe siguiendo los pasos de actualización generados dinámicamente para su organización desde el [cuestionario de actualización de Adobe Analytics a Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
