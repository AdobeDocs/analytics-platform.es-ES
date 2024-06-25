---
title: Control de acceso de Customer Journey Analytics
description: Obtenga información acerca de las formas de implementar el control de acceso en Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 1a470345a6a2748b992263c3ad25e4cd7d3daa9e
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 42%

---

# Control de acceso de Customer Journey Analytics

Hay tres niveles de acceso o funciones que rigen el Customer Journey Analytics: función Administrador de productos, función Administrador de perfil de producto y acceso de nivel de usuario. En este tema se explican estas funciones con más detalle.

Además, este artículo analiza formas más granulares de limitar el acceso, como la depuración de Workspace y nivel de fila, así como el control de acceso de nivel de valor.

## Función Administrador de productos

De forma predeterminada, los usuarios a los que se asigna la función Administrador de productos tienen los permisos necesarios para realizar la mayoría de las tareas dentro de Customer Journey Analytics. Sin embargo, algunas tareas requieren permisos adicionales.

Para agregar un usuario como administrador de productos:

1. Vaya a la [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. Seleccionar [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **Administradores**] pestaña > [!UICONTROL **Añadir administrador**].

   Los usuarios que ha agregado reciben el [Permisos predeterminados del administrador de productos](#product-admin-default-permissions). También puede concederles el derecho de [permisos adicionales](#product-admin-additional-permissions) si es necesario.

### Permisos predeterminados del administrador de productos

Los administradores de productos tienen permisos para completar la mayoría de las tareas de Customer Journey Analytics.

A los administradores de productos se les otorgan los permisos necesarios para realizar las siguientes tareas de forma predeterminada:

* Creación, actualización y eliminación de vistas de datos
* Actualizar y eliminar proyectos, filtros, métricas calculadas, audiencias, anotaciones o filtros creados por otros usuarios
* Compartir proyectos de Workspace con todos los usuarios
* Administrar la actividad de creación de informes en [Administrador de actividades de informes](/help/reporting-activity-manager/reporting-activity-overview.md)
* [Exportar tablas completas](/help/analysis-workspace/export/export-cloud.md) de Analysis Workspace

### Permisos adicionales del administrador de productos

Además de agregarse como Administrador de productos en la **Perfil de producto del Customer Journey Analytics** en el [Admin Console](https://adminconsole.adobe.com/enterprise/)Sin embargo, se requieren permisos adicionales para completar las siguientes tareas dentro de Customer Journey Analytics:

* Creación, actualización y eliminación de datos [Conexiones](/help/connections/overview.md)

  Para realizar esta tarea, los usuarios deben formar parte de un **Perfil de producto del Experience Platform** que proporciona los siguientes permisos:
   * Modelado de datos: Esquemas de vista, Administrar esquemas
   * Administración de datos: Ver conjuntos de datos, Administrar conjuntos de datos
   * Ingesta de datos: Administrar fuentes
   * Ver espacios de nombres de identidad

     Para obtener más información sobre los permisos de Experience Platform, consulte [Control de acceso en Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home).

* Exportar conjuntos de datos a la nube [Destinos](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=es)

  Para realizar esta tarea, los usuarios necesitan los siguientes permisos de Experience Platform:

   * Administrar destinos
   * Activar destinos

     Para obtener más información sobre los permisos de Destinos de Experience Platform, consulte [Resumen de destinos](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/home).

* Utilice el [Extensión de BI](../data-views/bi-extension.md)

  Para que los usuarios utilicen la extensión de BI, un Administrador de productos

   * debe asegurarse de que los permisos de Experience Platform para el usuario incluyan una función que tenga el recurso del servicio de consultas con las opciones Administrar consultas y Administrar integración del servicio de consultas. Consulte [Administración de permisos para un perfil de producto](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions).
   * debe garantizar los permisos de Customer Journey Analytics adecuados para el usuario:
      * permiso para acceder a las vistas de datos relevantes. Consulte Vistas de datos en [Permisos de Customer Journey Analytics en Admin Console](#customer-journey-analytics-permissions-in-admin-console).
      * para acceder a la extensión de CJA BI. Consulte Herramientas de vista de datos en [Permisos de Customer Journey Analytics en Admin Console](#customer-journey-analytics-permissions-in-admin-console).

## Función Administrador de perfil de producto

Un perfil de producto es un conjunto de permisos. Los administradores de perfil de producto pueden hacer lo siguiente:

* Cree y administre perfiles de producto individuales. Como añadir nuevos usuarios o administrar grupos de usuarios y sus perfiles de producto asociados.

* En Customer Journey Analytics, edite las vistas de datos que forman parte de un perfil de producto que administran. No pueden crear vistas de datos nuevas.

## Acceso de nivel de usuario

La siguiente matriz describe los permisos de acceso principales para diferentes funciones de Customer Journey Analytics para administradores que no son administradores de productos y administradores de productos de Customer Journey Analytics. La comprensión de estos permisos ayuda a los usuarios a navegar y utilizar Customer Journey Analytics de forma eficaz en función de su función y responsabilidades dentro de la organización.

| Funcionalidad del producto | No administradores de productos (usuarios) | Administradores de productos |
| --- | --- | --- |
| **Vistas de datos** | No se puede ver, actualizar, crear ni eliminar | Puede crear, actualizar o eliminar |
| **Conexiones** | No se puede ver, actualizar, crear ni eliminar | Puede crear, actualizar o eliminar |
| **Filtros** | Puede crear | Puede crear |
| **Proyectos** | Puede crear | Puede crear, actualizar o eliminar |
| **Públicos** | Puede crear con permisos especiales en Admin Console | Puede crear |
| **Métricas calculadas** | Puede crear con permisos especiales en Admin Console | Puede crear |

{style="table-layout:auto"}

## Depuración del proyecto de Workspace

Se puede utilizar otro nivel de control de acceso en el nivel de creación de informes del Workspace. Puede limitar el acceso a componentes específicos para determinados usuarios. Para obtener más información sobre cómo limitar componentes (dimensiones, métricas, filtros e intervalos de fechas) en el nivel de proyecto de Workspace y cómo se vincula la depuración a las vistas de datos, consulte [Depurar proyectos de](/help/analysis-workspace/curate-share/curate.md).

## Conceder acceso a métricas o dimensiones individuales

No se puede otorgar ni rechazar permisos a métricas o dimensiones individuales en Customer Journey Analytics como se puede hacer en la versión tradicional de Adobe Analytics. Las métricas y dimensiones se pueden modificar en [vistas de datos](/help/data-views/data-views.md) y, por lo tanto, están sujetos a cambios en Customer Journey Analytics. Si se cambian, también de forma retroactiva, la creación de informes se verá modificada.

## Casos prácticos

Estos son algunos casos de uso que ilustran cómo se puede utilizar el control de acceso en escenarios reales.

### Acceso de terceros

Un tercero con el que trabaja su compañía tiene un líder de equipo que se puede convertir en administrador de perfil de producto. Este administrador puede añadir usuarios del equipo de la empresa a este perfil de producto. Este administrador puede proporcionar acceso a vistas de datos específicas y agregar otros usuarios a este perfil de producto. También puede modificar las vistas de datos sobre las que tienen control para adaptarlas a las necesidades de su equipo.

### Control de acceso de nivel de fila

Supongamos que desea que los usuarios tengan acceso a los datos de un solo día. Así se limita el acceso a esas filas específicas:

1. Cree un filtro en Customer Journey Analytics donde **[!UICONTROL Día]** es igual a la fecha en la que desea que tengan acceso a los datos.
1. En [!UICONTROL Vistas de datos] > [!UICONTROL Configuración], agregue ese filtro a la vista de datos.
1. Guarde la vista de datos y aplicará automáticamente el filtro al conjunto de datos. Ahora, las filas que no se ajusten a la definición del filtro se excluyen automáticamente de la vista de datos editada.
1. Cree un nuevo perfil de producto en Admin Console, añada usuarios y limite su acceso a esta vista de datos.

### Control de acceso de nivel de valor

Los usuarios que tienen acceso a una vista de datos solo pueden trabajar con las métricas y dimensiones que el administrador ha incluido en esta vista de datos. Los administradores pueden utilizar la [funcionalidad Incluir/Excluir](/help/data-views/component-settings/include-exclude-values.md) en las vistas de datos para, por ejemplo, excluir ciertos valores de dimensión de una vista de datos.

Este es un ejemplo relacionado con la atención médica: supongamos que crea una métrica denominada “Hipertensión” en una vista de datos a partir de un conjunto de datos que incluya estos datos. El hecho de que sea una métrica le permitiría ver el valor agregado de esta métrica, pero no los pacientes individuales que están dentro de ella.

## Permisos de Customer Journey Analytics en Admin Console

La pestaña **[!UICONTROL Permisos]** forma parte de cada perfil de producto en [Admin Console](https://adminconsole.adobe.com/enterprise/). Puede añadir usuarios a perfiles de producto específicos. A continuación, asigne derechos a vistas de datos específicas y especifique los permisos que tienen los usuarios en un perfil de producto. Estos son los permisos específicos del Customer Journey Analytics:

![permisos de Admin Console](assets/permissions.png)

| Permiso | Definición |
| --- | --- |
| **[!UICONTROL Vistas de datos]** | Si cambia **[!UICONTROL Inclusión automática]** a **[!UICONTROL Activado]**, los usuarios que forman parte de este perfil de producto pueden ver todas las vistas de datos existentes y creadas recientemente. Si esta configuración está **[!UICONTROL Desactivada]**, puede seleccionar las vistas de datos específicas a las que los usuarios tienen acceso. |
| **[!UICONTROL Herramientas de creación de informes]**: |   |
| **[!UICONTROL Acceso a registros de auditoría]** | Este permiso exige la comprobación de permisos en la [API](https://www.adobe.io/cja-apis/docs/endpoints/auditlogs/) y en la interfaz de usuario de registros de auditoría. |
| **[!UICONTROL Acceso a Analysis Workspace]** | Permita que los usuarios accedan a Analysis Workspace en Customer Journey Analytics. |
| [!UICONTROL **Acceso guiado a análisis**] | Permitir que los usuarios creen [Proyectos de análisis guiado](/help/guided-analysis/overview.md). |
| [!UICONTROL **Previsión**] | Permitir que los usuarios accedan a la función Previsión en Analysis Workspace |
| **[!UICONTROL Administración de creación de informes]** | Permite que los usuarios vean y eliminen cualquier informe que se ejecute en su empresa. |
| **[!UICONTROL Vista del uso de creación de informes]** | Permitir que los usuarios vean todas las solicitudes de creación de informes simultáneas. |
| [!UICONTROL **Exportación de tabla completa**] | Permitir a los usuarios [exportar tablas completas a la nube](/help/analysis-workspace/export/export-cloud.md). |
| **[!UICONTROL Creación de métricas calculadas]** | Permitir que los usuarios creen [métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Creación de filtros]** | Permitir que los usuarios creen [filtros](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Acceso a Labs]** | Permitir a los usuarios acceder a [Labs](/help/labs/labs.md) pestaña en el Customer Journey Analytics. |
| **[!UICONTROL Creación de anotaciones]** | Permitir que los usuarios creen [anotaciones](/help/components/annotations/overview.md). |
| **[!UICONTROL Creación de audiencias]** | Permitir que los usuarios creen [audiencias](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Visualización de audiencias]** | Permitir que los usuarios vean [audiencias](/help/components/audiences/audiences-overview.md). |
| [!UICONTROL **Compartir Vínculos Del Proyecto Con Cualquiera**] | Permitir a los usuarios [comparta proyectos con cualquiera.](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| **[!UICONTROL Herramientas de vista de datos]**: |   |
| [!UICONTROL **Exportación de tabla completa**] | Permitir a los usuarios [exportar tablas completas a la nube](/help/analysis-workspace/export/export-cloud.md). |
| **[!UICONTROL [!UICONTROL Extensión de CJA BI]]** | Permitir que los usuarios utilicen [Extensión de BI](../data-views/bi-extension.md). |

{style="table-layout:auto"}
