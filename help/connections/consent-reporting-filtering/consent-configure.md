---
title: Configuración de informes y filtros de consentimiento
description: Aprenda a utilizar el asistente de aprovisionamiento para habilitar los informes de consentimiento y el filtrado opcional en tiempo de ingesta para una conexión en Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 759
ht-degree: 2%

---

# Configuración de informes y filtros de consentimiento

Los administradores del sistema pueden activar los informes de consentimiento y, opcionalmente, el filtrado de consentimiento para una o más conexiones. Para obtener información general, consulte [Información general sobre la creación de informes y el filtrado de consentimiento](/help/connections/consent-reporting-filtering/consent-overview.md).

>[!IMPORTANT]
>
>El filtrado de consentimiento excluye los datos de visitantes sin consentimiento en el momento de la ingesta. Los datos que se excluyen mediante el filtrado no se almacenan en Customer Journey Analytics y no se pueden recuperar para fechas pasadas. Revise atentamente las selecciones de acciones de marketing antes de habilitar el filtrado.

## Requisitos previos

Antes de configurar la creación de informes y el filtrado de consentimiento, asegúrese de lo siguiente:

* Tiene permisos de administrador del sistema en Customer Journey Analytics.
* La zona protegida que desea utilizar contiene un conjunto de datos de perfil con datos de pertenencia a directivas de consentimiento en el campo `consentPoliciesIDMap`.
* La conexión que desea configurar ya existe. Para obtener más información, consulte [Crear o editar una conexión](/help/connections/create-connection.md).

## Crear una configuración

Al crear una configuración para los informes y el filtrado de consentimiento, se selecciona la zona protegida y el conjunto de datos de perfil que contienen los datos de pertenencia a la directiva de consentimiento, se elige la conexión o conexiones que se van a configurar y se elige si se filtran los datos de cada acción de marketing. A continuación, Customer Journey Analytics crea automáticamente el conjunto de datos de búsqueda de la política de consentimiento y los componentes de la política de consentimiento.

Para crear una configuración de filtrado y creación de informes de consentimiento:

1. En Customer Journey Analytics, seleccione **[!UICONTROL Administración de datos]** > **[!UICONTROL Informes y filtrado de consentimiento]**.

1. Seleccione **[!UICONTROL Crear configuración]**.

1. En la sección **[!UICONTROL Detalles]**, especifique la siguiente información:

   | Campo | Descripción |
   |---------|----------|
   | **[!UICONTROL Nombre]** | Especifique un nombre para la configuración. |
   | **[!UICONTROL Zona protegida]** | Seleccione el simulador para pruebas de Experience Platform que contiene el conjunto de datos de perfil con los datos de pertenencia a directivas de consentimiento. <p>Existe un máximo de un conjunto de datos de búsqueda de directivas de consentimiento por zona protegida. Varias configuraciones en la misma zona protegida comparten el mismo conjunto de datos de búsqueda.</p> |

1. En la sección **[!UICONTROL Conjunto de datos de perfil]**, seleccione el conjunto de datos de perfil que contiene los datos de pertenencia a directivas de consentimiento (el campo `consentPoliciesIDMap`) sobre los que desea informar. Este conjunto de datos de perfil se agrega a la conexión que seleccione.

1. En la sección **[!UICONTROL Conexión]**, seleccione **[!UICONTROL Seleccionar una conexión]**, marque la casilla de verificación que hay junto a una o más conexiones que configurar y, a continuación, seleccione **[!UICONTROL Usar conexión]**.

   La creación de informes y el filtrado de consentimiento se aplican al nivel de conexión. Todas las vistas de datos de una conexión configurada heredan el mismo comportamiento.

1. (Opcional) En la sección **[!UICONTROL Filtrado]**, puede habilitar el filtrado para las siguientes acciones de marketing:

   >[!NOTE]
   >
   >Deje ambos alternadores sin seleccionar para habilitar la creación de informes de consentimiento sin filtrar.
   >
   >Cuando el filtrado para una acción de marketing está habilitado, Customer Journey Analytics ingiere los datos de un visitante solo si este coincide con **todas** las directivas de consentimiento que se aplican a esa acción de marketing. Para obtener más información, consulte [Filtrado de consentimiento](/help/connections/consent-reporting-filtering/consent-overview.md#consent-filtering) en [Resumen de filtrado e informes de consentimiento](/help/connections/consent-reporting-filtering/consent-overview.md).

   | Acción de marketing | Descripción |
   |---------|----------|
   | **[!UICONTROL Analytics]** | Filtrar datos utilizados para los informes estándar de Customer Journey Analytics en Analysis Workspace. |
   | **[!UICONTROL Ciencia de datos]** | Filtrar datos utilizados para casos de uso de análisis avanzados, aprendizaje automático y ciencia de datos. |

1. Seleccione **[!UICONTROL Crear]** para crear la configuración.

   Customer Journey Analytics automáticamente:

   * Agrega el conjunto de datos de perfil seleccionado a la conexión.
   * Crea un conjunto de datos de búsqueda de directivas de consentimiento para la zona protegida (si aún no existe) y sincroniza los nombres y las descripciones de las directivas de Experience Platform.
   * Agrega los componentes de la directiva de consentimiento (dimensiones, métricas y un campo derivado) a las vistas de datos dentro de la conexión configurada.
   * Aplica la etiqueta interna **consent** a los nuevos componentes para que pueda filtrarlos en la vista de datos. Para obtener más información acerca de las etiquetas internas, vea [Etiquetas y directivas](/help/data-views/data-governance.md).

1. Una vez completada la configuración, [vea los componentes de la directiva de consentimiento en la vista de datos](#view-consent-policy-components-in-the-data-view) para comprobar que están disponibles.

## Ver componentes de política de consentimiento en la vista de datos

Después de [crear una configuración](#create-a-configuration), puede comprobar que los componentes de la directiva de consentimiento se agregaron a las vistas de datos en la conexión configurada.

Para ver los componentes de directiva de consentimiento en la vista de datos, debe ser administrador de perfil de producto para el perfil de producto al que está asignada la vista de datos. Para obtener más información, consulte [Control de acceso](/help/technotes/access-control.md).

Para ver los componentes de la política de consentimiento en la vista de datos:

1. En Customer Journey Analytics, seleccione **[!UICONTROL Administración de datos]** > **[!UICONTROL Vistas de datos]**.

1. Abra una vista de datos asociada a la conexión configurada.

1. En la sección **[!UICONTROL Dimensiones]**, deberían estar disponibles las siguientes dimensiones:

   * **[!UICONTROL Id. de directiva de consentimiento]**

   * **[!UICONTROL Nombre de directiva]**

   * **[!UICONTROL Descripción de directiva]**

1. En la sección **[!UICONTROL Métricas]**, deberían estar disponibles las siguientes métricas:

   * **[!UICONTROL Visitantes con consentimiento]**

   * **[!UICONTROL Eventos con consentimiento]**

   * **[!UICONTROL Políticas de consentimiento único]**

   <!-- TODO: Add a screenshot of the consent policy components in the data view (assets/consent-components-dataview.png). -->

1. Utilice los componentes de política de consentimiento en Analysis Workspace.

   Los usuarios que tienen acceso a la vista de datos en Analysis Workspace ahora pueden ver los nuevos componentes y utilizarlos en sus análisis. Para obtener información sobre cómo usar los componentes de la directiva de consentimiento en Analysis Workspace, consulte [Analizar datos de la directiva de consentimiento](/help/connections/consent-reporting-filtering/consent-analyze.md).
