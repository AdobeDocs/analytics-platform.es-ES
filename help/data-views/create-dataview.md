---
title: Creación o edición de una vista de datos
description: Todos los ajustes que se pueden ajustar para crear o editar una vista de datos.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 747e77b964006404d70b500b28ec44005d65d944
workflow-type: tm+mt
source-wordcount: '1832'
ht-degree: 96%

---

# Creación o edición de una vista de datos

La creación de una vista de datos implica crear métricas y dimensiones a partir de elementos de esquema o utilizar componentes estándares. La mayoría de los elementos de esquema pueden ser una dimensión o una métrica según los requisitos de la empresa. Una vez arrastrado un elemento de esquema a una vista de datos, las opciones aparecen a la derecha, donde puede ajustar el funcionamiento de la dimensión o métrica en Customer Journey Analytics.

+++ Vea un vídeo para ilustrar las vistas de datos en Customer Journey Analytics

>[!VIDEO](https://video.tv.adobe.com/v/35110/?quality=12&learn=on)

+++

Creación o edición de una vista de datos:

1. Inicie sesión en [Customer Journey Analytics](https://analytics.adobe.com) y vaya a la pestaña **[!UICONTROL Vistas de datos]**.
1. Para crear una vista de datos, seleccione **[!UICONTROL Crear nueva vista de datos]**. También puede seleccionar una vista de datos existente de la lista de vistas de datos para editarla.


## Configuración {#configure}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_externalid"
>title="ID externo"
>abstract="El cambio del ID externo puede afectar a la forma en que el nombre de la vista de datos aparece en fuentes externas, como las herramientas de inteligencia empresarial."

<!-- markdownlint-enable MD034 -->


Para configurar una vista de datos nueva o existente, haga lo siguiente:

1. Seleccione la pestaña **[!UICONTROL Configurar]** (si no está activa).

   ![Configuración de una vista de datos](assets/dataview-configure.png)
1. Especificar datos de [!UICONTROL Configuración], [!UICONTROL Contenedor] y [!UICONTROL Calendario] (consulte más abajo).
1. Seleccionar **[!UICONTROL Guardar y continuar]** para seguir configurando la vista de datos nueva o la existente. Seleccionar **[!UICONTROL Guardar]** para almacenar la configuración para la vista de datos existente.


### Configuración

Proporciona una configuración general para la vista de datos.

| Configuración | Descripción |
| --- | --- |
| [!UICONTROL **Conexión**] | Este campo vincula la vista de datos con la conexión establecida anteriormente, que tiene uno o varios conjuntos de datos de Adobe Experience Platform. |
| [!UICONTROL **Nombre**] | Requerido. Nombre de la vista de datos. Este valor aparece en la lista desplegable superior derecha de Analysis Workspace. |
| [!UICONTROL **ID externo**] | Requerido. El nombre de la vista de datos que se puede utilizar en fuentes externas, como herramientas de inteligencia empresarial. El valor predeterminado es `unspecified`. Si no especifica un ID externo, el nombre se generará a partir del nombre de la vista de datos y reemplazando los espacios por guiones bajos. |
| [!UICONTROL **Descripción**] | Opcional. Adobe recomienda una descripción detallada para que los usuarios entiendan por qué existe la vista de datos y para quién está diseñada. |

{style="table-layout:auto"}

### Compatibilidad {#compatibility}

{{release-limited-testing-section}}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_dataviewsinadobejourneyoptimizer"
>title="Vistas de datos en Journey Optimizer"
>abstract="Journey Optimizer necesita utilizar una vista de datos configurada con Customer Journey Analytics.<br/>Active esta opción para que sea la vista de datos predeterminada que se usa en los informes de Adobe Journey Optimizer."
>additional-url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/integrations/ajo#connection" text="Qué componentes y conjuntos de datos se añaden."

<!-- markdownlint-enable MD034 -->


Proporciona la configuración que se aplica al usar Adobe Journey Optimizer además de Customer Journey Analytics.

Esta sección solo está visible para los administradores que están aprovisionados con Journey Optimizer.

| Configuración | Descripción |
| --- | --- |
| [!UICONTROL **Establecer como vista de datos predeterminada en Adobe Journey Optimizer**] | Esta opción de configuración estandariza los informes en Journey Optimizer y Customer Journey Analytics. También le permite realizar análisis avanzados de los datos de Adobe Journey Optimizer en Customer Journey Analytics (seleccionando ![Abrir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_OpenInLight_18_N.svg) [!UICONTROL **Analizar en CJA**] en Journey Optimizer).<p>Para realizar este tipo de análisis, Journey Optimizer necesita acceder a una vista de datos de Customer Journey Analytics.<p>Habilite esta opción para que sea la vista de datos predeterminada que se utilice en la creación de informes de Journey Optimizer para su zona protegida.</p><p>Esta opción de configuración hace lo siguiente automáticamente:</p><ul><li>Configura todos los conjuntos de datos de Journey Optimizer necesarios en la conexión asociada en Customer Journey Analytics para su uso con Journey Optimizer.</li><li>Crea un conjunto de métricas y dimensiones de Journey Optimizer en la vista de datos (incluidos campos derivados y métricas calculadas). Las etiquetas de contexto se establecen automáticamente en todas estas métricas y dimensiones.</li></ul><p><p>Tenga en cuenta lo siguiente al habilitar esta opción: <ul><li>Puede cambiar la vista de datos predeterminada más adelante, pero al hacerlo se podrían modificar los datos de la creación de informes de Journey Optimizer. Si elige deshabilitar esta opción después de habilitarla, se le pedirá que seleccione una nueva vista de datos predeterminada.</li><li>Si ya ha realizado personalizaciones manuales en los conjuntos de datos, dimensiones o métricas en la vista de datos de Customer Journey Analytics, las personalizaciones manuales permanecen intactas al habilitar esta opción de configuración. Esta opción realiza personalizaciones adicionales que estandarizan aún más la creación de informes en Journey Optimizer y Customer Journey Analytics. También puede realizar personalizaciones manuales después de activar esta opción.</li></ul>Consulte [Integración de Adobe Journey Optimizer con Adobe Customer Journey Analytics](/help/integrations/ajo.md) para obtener más información. |

{style="table-layout:auto"}

### Contenedores

Designa el nombre de los contenedores para la vista de datos. Los nombres de contenedores se utilizan frecuentemente en [Filtros](/help/components/filters/filters-overview.md#Filter-containers).

| Configuración | Descripción |
| --- | --- |
| [!UICONTROL **Nombre de contenedor de persona**] | [!UICONTROL Persona] (valor predeterminado). El contenedor [!UICONTROL Persona] incluye todas las sesiones y eventos de las personas en un lapso de tiempo específico. Si su organización utiliza un término diferente (por ejemplo, visitante o usuario), puede cambiar el nombre del contenedor aquí. |
| [!UICONTROL **Nombre de contenedor de sesión**] | [!UICONTROL Sesión] (valor predeterminado). El contenedor [!UICONTROL Sesión] le permite identificar interacciones de páginas, campañas o conversiones para una sesión específica. Puede cambiar el nombre de este contenedor a Visita o a cualquier otro término que prefiera. |
| [!UICONTROL **Nombre de contenedor de evento**] | [!UICONTROL Evento] (valor predeterminado). El contenedor [!UICONTROL Evento] define eventos individuales en un conjunto de datos. Si su organización utiliza un término diferente (por ejemplo, Visitas individuales o Vistas de página), puede cambiar el nombre del contenedor aquí. |

{style="table-layout:auto"}

### Calendario

Indica el formato de calendario que desea que siga la vista de datos. Puede tener varias vistas de datos basadas en la misma [Conexión](/help/connections/create-connection.md) y proporcionarles diferentes tipos de calendario o zonas horarias. Estas vistas de datos pueden permitir que equipos que utilicen distintos tipos de calendario satisfagan sus necesidades respectivas con los mismos datos subyacentes.

| Configuración | Descripción |
| --- | --- |
| [!UICONTROL **Zona horaria**] | Elija en qué zona horaria desea que se presenten los datos. Si elige una zona horaria que funcione según el horario de verano, los datos se ajustan automáticamente para reflejarlo. En primavera, cuando los relojes se adelantan, hay un espacio de una hora. En otoño, cuando los relojes se atrasan, se repite una hora durante el cambio del horario de verano. |
| [!UICONTROL **Tipo de calendario**] | Determine cómo se agrupan las semanas del mes.<br>**Gregoriano:** formato de calendario estándar. Los trimestres se agrupan por mes.<br>**Venta minorista 4-5-4:** calendario de venta minorista estandarizado 4-5-4. El primer y último mes del trimestre contiene cuatro semanas, mientras que el segundo mes del trimestre consta de cinco semanas.<br>**Personalizado (4-5-4):** similar al calendario 4-5-4 excepto que puede elegir el primer día del año y el año en el que se produce la semana extra.<br>**Personalizado (4-4-5):** el primer y el segundo meses de cada trimestre contienen 4 semanas, mientras que la última semana de cada trimestre constan de 5 semanas.<br>**Personalizado (5-4-4):** el primer mes de cada trimestre consta de 5 semanas, mientras que el segundo y el tercer mes de cada trimestre constan de 4 semanas. |
| [!UICONTROL **Primer mes del año**] y [!UICONTROL **primer día de la semana**] | Visible para el tipo de calendario gregoriano. Especifique en qué mes desea que comience el año del calendario y cada semana. |
| [!UICONTROL **Primer día del año actual**] | Visible para tipos de calendario personalizados. Especifique qué día del año desea que comience el año actual. El calendario aplica automáticamente el formato del primer día de cada semana en función de este valor. |
| [!UICONTROL **Año que incluye la semana “extra”**] | Con la mayoría de los calendarios de 364 días (52 semanas de 7 días cada uno), cada año se acumulan varios días restantes hasta formar una semana extra. Esta semana extra se agrega al último mes de ese año. Especifique a qué año desea agregar la semana adicional. |

{style="table-layout:auto"}

## Componentes

A continuación, puede establecer los componentes de una vista de datos, lo que significa que puede crear métricas y dimensiones a partir de elementos de esquema. También puede utilizar componentes estándares.

>[!IMPORTANT]
>
>Se pueden añadir hasta 5000 métricas y 5000 dimensiones a una sola vista de datos.

1. Seleccione la pestaña **[!UICONTROL Componentes]**.

   ![Pestaña Componentes](assets/dataview-components.png)

   Puede ver la [!UICONTROL Conexión] en la parte superior izquierda, que contiene los conjuntos de datos y sus [!UICONTROL Campos de esquema] a continuación.  Los componentes ya incluidos son estándar (generados por el sistema) necesarios para todas las vistas de datos (como Eventos, Personas, Métricas de sesiones y las dimensiones Minuto, Trimestre y Semana). Adobe también aplica el filtro **[!UICONTROL Contiene datos]** y **[!UICONTROL no está obsoleto]** de forma predeterminada, de modo que solo aparecen los campos de esquema que contienen datos y que no están en desuso.

1. Busque un campo de esquema mediante el ![Icono de búsqueda](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) **[!UICONTROL Buscar campos de esquema]** o busque un campo moviéndose a cualquiera de las colecciones de conjuntos de datos, como ![Icono de carpeta](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg) **[!UICONTROL Conjuntos de datos de evento]**.<br/>Como alternativa, puede crear un campo derivado utilizando ![Icono de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) **Crear campo derivado**. Consulte [Campos derivados](./derived-fields/derived-fields.md) para obtener más información.

1. Cuando haya encontrado el campo de esquema específico o haya definido el campo derivado, arrastre ese campo, como ![Icono de controlador](https://spectrum.adobe.com/static/icons/workflow_22/Smock_DragHandle_22_N.svg) **[!UICONTROL Nombre de página]**, desde el carril izquierdo a la sección Métricas o Dimensión.
Puede arrastrar el mismo campo de esquema a las secciones de dimensiones o métricas varias veces y configurar la misma dimensión o métrica de diferentes maneras. Por ejemplo, desde el campo pageName puede crear dimensiones llamada Páginas de producto y Páginas de error, utilizando diferentes [Configuraciones del componente](component-settings/overview.md) a la derecha.
Si arrastra una carpeta de campo de esquema desde el carril izquierdo, se ordenan automáticamente en secciones típicas. Los campos de cadena terminan en la sección [!UICONTROL Dimensiones] y los tipos de esquema numérico terminan en la sección [!UICONTROL Métricas]. También puede hacer clic en **[!UICONTROL Agregar todo]** y todos los campos de esquema se añaden a sus respectivas ubicaciones.

1. Una vez seleccionado un componente, la configuración aparece a la derecha.

   ![Componente de vista de datos seleccionado](assets/dataview-component-pagename.png)

   Configure el componente con [Configuración del componente](component-settings/overview.md). La configuración de componentes disponible depende de si el componente es una dimensión o métrica y del tipo de datos de esquema. La configuración incluye lo siguiente:

   * [[!UICONTROL Atribución]](component-settings/attribution.md)
   * [[!UICONTROL Comportamiento]](component-settings/behavior.md)
   * [[!UICONTROL Formato]](component-settings/format.md)
   * [[!UICONTROL Incluir/excluir valores]](component-settings/include-exclude-values.md)
   * [[!UICONTROL Anulación de duplicación métrica]](component-settings/metric-deduplication.md)
   * [[!UICONTROL Sin opciones de valor]](component-settings/no-value-options.md)
   * [[!UICONTROL Persistencia]](component-settings/persistence.md)
   * [[!UICONTROL Clasificación de valor]](component-settings/value-bucketing.md)

1. Seleccione **[!UICONTROL Guardar y continuar]** para seguir configurando la vista de datos nueva o la existente. Seleccione **[!UICONTROL Guardar]** para guardar la configuración para la vista de datos existente.

**Duplicado de métricas o dimensiones**

Duplicar métricas o dimensiones y luego modificar configuraciones específicas es una manera sencilla de crear varias métricas o dimensiones a partir de un único campo de esquema. Seleccione la opción [!UICONTROL Duplicado] debajo del nombre de la métrica o dimensión en la parte superior derecha. Modifique la nueva métrica o dimensión, y guárdela con un nombre más descriptivo.

**Filtrado de campos de esquema o conjuntos de datos**

Puede filtrar los campos de esquema ![Icono de filtro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) en el carril izquierdo por [!UICONTROL tipo de datos], [!UICONTROL conjuntos de datos], [!UICONTROL gobernanza de datos] y [!UICONTROL otros] criterios ([!UICONTROL contiene datos], [!UICONTROL es identidad] y [!UICONTROL no está obsoleto]):

![Filtrar campos](assets/dataview-components-filter.png)

>[!TIP]
>
>Si los componentes no se cargan correctamente en la vista de datos y ve un mensaje de error en su lugar, consulte [Falta de permisos](../troubleshooting/lack-of-permissions.md) para resolverlo.



## Configuración

1. Seleccione la pestaña **[!UICONTROL Configuración]**.
1. Configure filtros para aplicarlos a toda la vista de datos. Consulte [Configuración (filtros)](#settings-filters) más abajo.
1. Configure el tiempo de espera de sesión y las métricas. Consulte [Configuración de sesión](#session-settings) más abajo.
1. Seleccione **[!UICONTROL Guardar y continuar]** para seguir configurando la vista de datos nueva o la existente. Seleccione **[!UICONTROL Guardar]** para guardar la configuración para la vista de datos existente.

### Configuración (filtros)

Puede agregar filtros que se apliquen a toda la vista de datos. Este filtro se aplicará a cualquier informe que ejecute el Espacio de trabajo. Arrastre un filtro desde la lista en el carril izquierdo al campo [!UICONTROL Añadir filtros].

### Configuración de sesión

Determine el período de inactividad entre los eventos antes de que caduque una sesión y se inicie una nueva. Se requiere un período de tiempo. Opcionalmente, también puede forzar el inicio de una nueva sesión cuando un evento contenga una métrica determinada. Consulte [Configuración de sesión](session-settings.md) para obtener más información.

Una vez especificada toda la configuración deseada, haga clic en **[!UICONTROL Guardar y finalizar]**.
