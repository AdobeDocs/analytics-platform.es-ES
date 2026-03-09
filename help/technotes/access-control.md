---
title: Control de acceso de Customer Journey Analytics
description: Obtenga información acerca de las formas de implementar el control de acceso en Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 81e08ecb593b6ba789c479d0e648cbe7ba0a82d6
workflow-type: tm+mt
source-wordcount: '1554'
ht-degree: 96%

---

# Control de acceso

Hay tres niveles de acceso o tres funciones que rigen a Customer Journey Analytics: la función de administrador de productos, la función de administrador de perfiles de productos y el acceso a nivel de usuario. En este tema se explican estas funciones con más detalle.

Además, este artículo analiza formas más detalladas de limitar el acceso, como la curación de Workspace y nivel de fila, así como el control de acceso de nivel de valor.

## Control de acceso basado en funciones

Están disponibles los siguientes niveles de control de acceso basados en funciones.

### Función de administrador de productos

De forma predeterminada, los usuarios a los que se asigna la función de administrador de productos tienen los permisos necesarios para realizar la mayoría de las tareas en Customer Journey Analytics. Sin embargo, algunas tareas requieren permisos adicionales.

Para añadir un usuario como administrador de productos, haga lo siguiente:

1. Vaya a [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. Seleccione la pestaña [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **Administradores**] > [!UICONTROL **Añadir administrador**].

   A los usuarios que añadió se les han concedido los [permisos predeterminados de administrador de productos](#product-admin-default-permissions). También puede concederles [permisos adicionales](#product-admin-additional-permissions) si es necesario.

#### Permisos predeterminados de administrador de productos

Los administradores de productos tienen permisos para completar la mayoría de las tareas de Customer Journey Analytics.

A los administradores de productos se les otorgan los permisos necesarios para realizar las siguientes tareas de forma predeterminada:

* Actualizar y eliminar proyectos, segmentos, métricas calculadas, públicos, anotaciones o segmentos creados por otros usuarios
* Compartir proyectos de Workspace con todos los usuarios
* Administrar la actividad de creación de informes en el [Administrador de actividades de creación de informes](/help/reporting-activity-manager/reporting-activity-overview.md)
* [Exportar tablas completas](/help/analysis-workspace/export/export-cloud.md) desde Analysis Workspace

#### Permisos adicionales del administrador de productos

Además de añadirse como administrador de productos en el **Perfil de productos de Customer Journey Analytics** en [Admin Console](https://adminconsole.adobe.com/enterprise/), se necesitan permisos adicionales para completar las siguientes tareas en Customer Journey Analytics:

* Crear, actualizar y eliminar [vistas de datos](/help/data-views/data-views.md).
* Crear, actualizar y eliminar [conexiones](/help/connections/overview.md)

  Para realizar esta tarea, los usuarios deben formar parte de un **Perfil del producto de Experience Platform** que proporcione los siguientes permisos:

  | Categoría | Permiso | Descripción |
  |---|---|---|
  | [!UICONTROL Zonas protegidas] | [!UICONTROL Al menos uno] | Acceso a zonas protegidas relevantes para conexiones. |
  | [!UICONTROL Modelado de datos] | [!UICONTROL Ver esquemas] | Acceso de solo lectura a esquemas y recursos relacionados. |
  | [!UICONTROL Modelado de datos] | [!UICONTROL Administrar esquemas] | Acceso para leer, crear, editar y eliminar esquemas y recursos relacionados. |
  | [!UICONTROL Administración de datos] | [!UICONTROL Ver conjuntos de datos de vistas] | Acceso de solo lectura para conjuntos de datos y esquemas. |
  | [!UICONTROL Identity Management] | [!UICONTROL Ver espacios de nombres de identidad] | Acceso de solo lectura para espacios de nombres de identidad. |

  Para obtener más información sobre los permisos de Experience Platform, consulte [Administrar permisos para un perfil del producto](https://experienceleague.adobe.com/es/docs/experience-platform/access-control/ui/permissions).


* Si Journey Optimizer está integrado con Customer Journey Analytics donde existen conexiones de Journey Optimizer, también deben añadirse permisos de recorridos para acceder a Conexiones:

  | Categoría | Permiso | Descripción |
  |---|---|---|
  | [!UICONTROL Recorridos] | [!UICONTROL Ver eventos de recorridos, fuentes de datos y acciones] | Acceso de solo lectura a eventos de recorrido, acciones personalizadas de recorrido y fuentes de datos de recorrido. |
  | [!UICONTROL Recorridos] | [!UICONTROL Administrar eventos de recorridos, fuentes de datos y acciones] | Leer, crear, editar y eliminar eventos, fuentes o acciones. |
  | [!UICONTROL Recorridos] | [!UICONTROL Ver recorridos] | Acceso de solo lectura a recorridos. |
  | [!UICONTROL Recorridos] | [!UICONTROL Administrar recorridos] | Leer, crear, editar y eliminar recorridos. |

* Exportar conjuntos de datos a [destinos](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/ui/activate/export-datasets)

  Para realizar esta tarea, los usuarios deben formar parte de un **Perfil del producto de Experience Platform** que proporcione los siguientes permisos:

  | Categoría | Permiso | Descripción |
  |---|---|---|
  | [!UICONTROL Destinos] | [!UICONTROL Administrar destinos] | Acceso para leer, crear y eliminar conexiones y cuentas de destino. |
  | [!UICONTROL Destinos] | [!UICONTROL Activar destinos] | Permite a los usuarios activar segmentos en destinos existentes. Habilita el paso de asignación en el flujo de trabajo de activación. Este permiso también requiere que se conceda el permiso Ver destinos al usuario que desea activar los datos en los destinos. |

  Para obtener más información sobre los permisos de Experience Platform, consulte [Administrar permisos para un perfil del producto](https://experienceleague.adobe.com/es/docs/experience-platform/access-control/ui/permissions).

* Usar la [extensión de BI](../data-views/bi-extension.md)

  Para que los usuarios utilicen la extensión de BI, un administrador de productos

   * debe asegurarse de que los permisos de Experience Platform para el usuario incluyan una función que tenga el recurso del Servicio de consultas con las opciones de Administrar consultas y Administrar integración del servicio de consultas. Para obtener más información sobre los permisos de Experience Platform, consulte [Administrar permisos para un perfil del producto](https://experienceleague.adobe.com/es/docs/experience-platform/access-control/ui/permissions).

     | Categoría | Permiso | Descripción |
     |---|---|---|
     | [!UICONTROL Servicio de consultas] | [!UICONTROL Administrar consultas] | Acceso para leer, crear, editar y eliminar consultas SQL estructuradas para datos de Platform. |
     | [!UICONTROL Servicio de consultas] | [!UICONTROL Administrar integración del servicio de consultas] | Acceso para crear, actualizar y eliminar credenciales que no caducan para el acceso al Servicio de consultas. |

   * debe garantizar los permisos de Customer Journey Analytics adecuados para el usuario:
      * permiso para acceder a las vistas de datos relevantes. Consulte [!UICONTROL Vistas de datos] en [Acceso de nivel de usuario](#user-level-access).
      * permiso para acceder a la extensión de BI de Customer Journey Analytics. Consulte [!UICONTROL Herramientas de vista de datos] en [Acceso de nivel de usuario](#user-level-access).

### Función de administrador de perfiles de producto

Un perfil de producto es un conjunto de permisos. Los administradores de productos crean perfiles de producto y pueden asignar administradores de perfiles de producto para administrar uno o varios perfiles de producto. Un administrador de perfiles de producto puede hacer lo siguiente:

* Administrar los perfiles de producto asignados. Tales como añadir o eliminar usuarios o grupos de usuarios y modificar los permisos de los perfiles de producto.

* En Customer Journey Analytics, edite las vistas de datos que forman parte de un perfil de producto asignado. Los administradores de perfiles de producto no pueden crear nuevas vistas de datos.

### Acceso de nivel de usuario

En la tabla siguiente se describen los principales permisos de acceso para las distintas funciones de Customer Journey Analytics que puede configurar para los usuarios relevantes. Puede administrar diferentes niveles de acceso de usuarios a través de perfiles de producto. Un perfil del producto combina una serie de permisos que puede asignar a usuarios individuales o grupos de usuarios.

La pestaña **[!UICONTROL Permisos]** forma parte de cada perfil del producto en [Admin Console](https://adminconsole.adobe.com/enterprise/).

![permisos de Admin Console](assets/permissions.png)

| Categoría | Permiso | Descripción |
| --- | --- | ---|
| [!UICONTROL Vistas de datos] | *nombre de la vista de datos* | Si cambia **[!UICONTROL Inclusión automática]** a **[!UICONTROL Activado]**, los usuarios que forman parte de este perfil de producto pueden ver todas las vistas de datos existentes y creadas recientemente. Si esta configuración está **[!UICONTROL Desactivada]**, puede seleccionar las vistas de datos específicas a las que los usuarios tienen acceso. |
| [!UICONTROL Herramientas de creación de informes] | [!UICONTROL Acceso guiado a análisis] | Permite que los usuarios accedan a [Análisis guiado](/help/guided-analysis/overview.md). |
| [!UICONTROL Herramientas de creación de informes] | [!UICONTROL Creación de métricas calculadas] | Permite que los usuarios creen [métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md). Los usuarios solo pueden etiquetar, compartir, eliminar y cambiar el nombre de las métricas calculadas que crean o de las métricas calculadas compartidas con ellos. |
| [!UICONTROL Herramientas de creación de informes] | [!UICONTROL Creación de segmentos] | Permite que los usuarios creen [segmentos](/help/components/segments/seg-overview.md). Los usuarios pueden etiquetar, compartir, eliminar y cambiar el nombre solo de los segmentos que crean o de los que han compartido con ellos. |
| [!UICONTROL Herramientas de creación de informes] | [!UICONTROL Acceso a Labs] | Permite que los usuarios tengan acceso a la pestaña [Labs](/help/labs/labs.md) en Customer Journey Analytics. |
| [!UICONTROL Herramientas de creación de informes] | [!UICONTROL Creación de anotaciones] | Permite que los usuarios creen [anotaciones](/help/components/annotations/overview.md). Los usuarios solo pueden etiquetar, compartir, eliminar y cambiar el nombre de las anotaciones que creen o de las anotaciones compartidas con ellos. |
| [!UICONTROL Herramientas de creación de informes] | [!UICONTROL Visualización de públicos] | Permite que los usuarios vean [públicos](/help/components/audiences/audiences-overview.md). |
| [!UICONTROL Herramientas de creación de informes] | [!UICONTROL Creación de públicos] | Permitir que los usuarios creen [audiencias](/help/components/audiences/audiences-overview.md). Requiere [Administrar segmentos](https://experienceleague.adobe.com/es/docs/experience-platform/access-control/home) en Adobe Experience Platform. |
| [!UICONTROL Herramientas de creación de informes] | [!UICONTROL Narración de datos] | Permite que los usuarios [generen presentaciones de diapositivas basadas en proyectos de Workspace.](/help/analysis-workspace/curate-share/generate-slides.md) |
| [!UICONTROL Herramientas de creación de informes] | [!UICONTROL Acceso a registros de auditoría] | Este permiso aplica la comprobación de permisos en la [API](https://developer.adobe.com/cja-apis/docs/endpoints/auditlogs/) y en la interfaz de usuario de registros de auditoría. |
| [!UICONTROL Herramientas de creación de informes] | [!UICONTROL Uso compartido de vínculos del proyecto con cualquier persona] | Permite que los usuarios [compartan proyectos con cualquiera.](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| [!UICONTROL Herramientas de creación de informes] | [!UICONTROL Previsión] | Permite que los usuarios accedan a la función [Previsión](../analysis-workspace/c-forecast/forecasting.md) en Analysis Workspace |
| [!UICONTROL Herramientas de creación de informes] | [!UICONTROL Asistente de IA: conocimiento del producto] | Permite que los usuarios tengan acceso al [Asistente de IA](../ai-assistant.md) para obtener conocimiento del producto. |
| [!UICONTROL Herramientas de creación de informes] | [!UICONTROL Data Insights Agent] | Permita que los usuarios tengan acceso a [Data Insights Agent](../data-analysis-ai.md) para obtener información de datos generados por IA. |
| [!UICONTROL Herramientas de creación de informes] | [!UICONTROL Pies de ilustración inteligentes] | Permite que los usuarios tengan acceso a [subtítulos inteligentes](/help/analysis-workspace/visualizations/intelligent-captions.md). |
| [!UICONTROL Herramientas de vista de datos] | [!UICONTROL Exportación de tablas completas] | Permite a los usuarioss[Exportar tablas completas a la nube](/help/analysis-workspace/export/export-cloud.md) |
| [!UICONTROL Herramientas de vista de datos] | [!UICONTROL Extensión de CJA BI] | Permite que los usuarios usen la [extensión BI](../data-views/bi-extension.md). |

{style="table-layout:auto"}

## Curación del proyecto de Workspace

Se puede utilizar otro nivel de control de acceso en el nivel de creación de informes del Workspace. Puede limitar el acceso a componentes específicos para determinados usuarios. Para obtener más información sobre cómo limitar componentes (dimensiones, métricas, segmentos e intervalos de fechas) en el nivel de proyecto de Workspace y cómo se vincula la depuración a las vistas de datos, consulte [Depuración de proyectos](/help/analysis-workspace/curate-share/curate.md).

## Conceder acceso a métricas o dimensiones individuales

No se puede otorgar ni rechazar permisos a métricas o dimensiones individuales en Customer Journey Analytics como se puede hacer en la versión tradicional de Adobe Analytics. Las métricas y dimensiones se pueden modificar en las [vistas de datos](/help/data-views/data-views.md) y, por lo tanto, están sujetas a cambios en Customer Journey Analytics. Si se cambian, también de forma retroactiva, la creación de informes se verá modificada.

## Casos prácticos

Estos son algunos casos de uso que ilustran cómo se puede utilizar el control de acceso en escenarios reales.

### Acceso de terceros

Puede proporcionar acceso de administración de perfiles de producto a un líder de equipo de un tercero con el que trabaje su compañía. A continuación, este administrador puede añadir usuarios de su equipo a este perfil de producto. Este administrador puede proporcionar acceso a vistas de datos específicas y añadir otros usuarios a este perfil de producto. El administrador de perfiles de producto puede modificar las vistas de datos para adaptarlas a los requisitos del equipo de terceros.

### Control de acceso de nivel de fila

Supongamos que desea que los usuarios tengan acceso a los datos de un solo día. Así se limita el acceso a esas filas específicas:

1. Cree un segmento en [!UICONTROL Configuración] de una vista de datos específica, donde [!UICONTROL Día] es igual a la fecha en la que desea que tengan acceso a los datos. Consulte [Crear vista de datos](/help/data-views/create-dataview.md#settings-filters) para obtener más información.
1. Guarde la vista de datos, que aplica el segmento a la parte de datos de los conjuntos de datos de la conexión subyacente. Las filas que no se ajusten a la definición del segmento se excluyen automáticamente de la vista de datos y no están disponibles para Analysis Workspace al utilizar esta vista de datos.
1. Cree un nuevo [Perfil del producto](#product-profile-admin-role) en Admin Console, añada usuarios al perfil del producto e incluya solamente esta vista de datos específica en el perfil del producto.

### Control de acceso de nivel de valor

Los usuarios que tienen acceso a una vista de datos solo pueden trabajar con las métricas y dimensiones que el administrador ha incluido en esta vista de datos. Los administradores pueden usar la configuración del componente [Incluir/Excluir funcionalidad](/help/data-views/component-settings/include-exclude-values.md) o [Creación de depósitos de valor](../data-views/component-settings/value-bucketing.md) en vistas de datos para excluir o añadir ciertos valores de dimensión de una vista de datos.

Por ejemplo: crea una métrica llamada *Hipertensión* en una vista de datos a partir de un componente que contiene datos de pacientes individuales del conjunto de datos. La creación de depósitos de valor se utiliza para proporcionar acceso únicamente a los valores agrupados, de modo que los usuarios de los datos no vean los datos de pacientes individuales.
