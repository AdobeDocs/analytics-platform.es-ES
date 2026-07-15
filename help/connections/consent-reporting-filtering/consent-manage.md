---
title: Administrar las configuraciones de informes de consentimiento y filtrado
description: Obtenga información sobre cómo ver, editar y eliminar las configuraciones de creación de informes y filtrado de consentimiento, y cómo el conjunto de datos de búsqueda de directivas de consentimiento permanece sincronizado en Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 452
ht-degree: 5%

---

# Administrar las configuraciones de filtrado y creación de informes de consentimiento

Después de [crear una configuración de filtrado y creación de informes de consentimiento](/help/connections/consent-reporting-filtering/consent-configure.md), puede verla, editarla o eliminarla.

Solo los administradores del sistema pueden administrar las configuraciones de filtrado y creación de informes de consentimiento.

Para obtener información general, consulte [Información general sobre la creación de informes y el filtrado de consentimiento](/help/connections/consent-reporting-filtering/consent-overview.md).

## Ver configuraciones existentes

Para ver las configuraciones existentes:

1. En Customer Journey Analytics, seleccione **[!UICONTROL Administración de datos]** > **[!UICONTROL Informes y filtrado de consentimiento]**.

   Las siguientes columnas de información están disponibles para cada configuración:

   * **[!UICONTROL Creado por]**: El usuario que creó la configuración.

   * **[!UICONTROL espacio aislado]**: El espacio aislado de Experience Platform que contiene el conjunto de datos de perfil.

   * **[!UICONTROL Conexión]**: La conexión a la que se aplica la configuración.

   * **[!UICONTROL Filtrado]**: Las acciones de marketing para las que está habilitado el filtrado, si las hay.

   * **[!UICONTROL Fecha de creación]**: La fecha en que se creó la configuración.

   * **[!UICONTROL Última modificación]**: Fecha en la que se modificó la configuración por última vez.

   * **[!UICONTROL Estado]**: El estado de la configuración.

   Puede ocultar cualquier columna seleccionando el icono de columna ![Icono de columna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg), deseleccionando cualquier columna que desee ocultar y, a continuación, seleccionando **[!UICONTROL Aplicar]**.

1. (Opcional) Para filtrar la lista de configuraciones, seleccione el **Filtro** ![Icono de filtro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) y, a continuación, filtre por cualquiera de los siguientes criterios:

   * **[!UICONTROL Conexión]**

   * **[!UICONTROL Creado por]**

   * **[!UICONTROL Zona protegida]**

   * **[!UICONTROL Estado]**

## Editar una configuración

>[!IMPORTANT]
>
>Los cambios en el filtrado afectan únicamente a los datos que se incorporan después de guardar los cambios en la configuración. Al habilitar el filtrado no se eliminan los datos de visitantes que no dieron su consentimiento y que se ingirieron antes del cambio. Al deshabilitar el filtrado, no se recuperan los datos que se excluyeron cuando el filtrado estaba habilitado.

Para editar una configuración existente:

1. En Customer Journey Analytics, seleccione **[!UICONTROL Administración de datos]** > **[!UICONTROL Informes y filtrado de consentimiento]**.

1. Seleccione el nombre de la configuración que desea editar.

   O bien

   Seleccione la casilla que está junto a la configuración que desea editar y, a continuación, seleccione **[!UICONTROL Editar]**.

1. Realice los cambios y seleccione **[!UICONTROL Guardar]**.

## Eliminar una configuración

Para eliminar una configuración existente:

1. En Customer Journey Analytics, seleccione **[!UICONTROL Administración de datos]** > **[!UICONTROL Informes y filtrado de consentimiento]**.

1. Seleccione la casilla de verificación situada junto a la configuración que desee eliminar y, a continuación, seleccione **[!UICONTROL Eliminar]**.

## Cómo permanece sincronizado el conjunto de datos de búsqueda de directivas de consentimiento

Customer Journey Analytics mantiene automáticamente el conjunto de datos de búsqueda de la directiva de consentimiento sincronizado con Experience Platform. Cuando se crea, actualiza, cambia el nombre o elimina una directiva de consentimiento en Experience Platform, se actualizan el nombre y la descripción de la directiva correspondiente en el conjunto de datos de búsqueda.

Tenga en cuenta lo siguiente:

* Existe un máximo de un conjunto de datos de búsqueda de directivas de consentimiento por zona protegida. Varias configuraciones en la misma zona protegida comparten ese conjunto de datos de búsqueda.
* Como los nombres y las descripciones de las directivas provienen de Experience Platform, actualice los metadatos de las directivas en Experience Platform en lugar de editar directamente el conjunto de datos de búsqueda.
