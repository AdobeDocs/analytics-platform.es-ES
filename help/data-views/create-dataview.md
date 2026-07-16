---
title: Creación O Edición De Una Vista De Datos
description: Obtenga información sobre todas las opciones que se pueden configurar al crear o editar una vista de datos.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78
solution: Customer Journey Analytics
feature: Data Views
role: Admin
TQID: https://experienceleague.adobe.com/EXiKrWVfmMRgZ4GF0OR410Mr2-P5IEjPy3Hf0FmRDJ8
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 28959f1ea858dee686e6d13025621c4a6164c319
workflow-type: tm+mt
source-wordcount: 3152
ht-degree: 74%

---

# Creación o edición de una vista de datos

La creación de una vista de datos implica crear métricas y dimensiones a partir de elementos de esquema o utilizar componentes estándares. La mayoría de los elementos de esquema pueden ser una dimensión o una métrica según los requisitos de la empresa. Una vez arrastrado un elemento de esquema a una vista de datos, las opciones aparecen a la derecha, donde puede ajustar el funcionamiento de la dimensión o métrica en Customer Journey Analytics.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Crear o editar una vista de datos](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/data-views/overview-of-configuring-data-views-for-cja){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


Creación o edición de una vista de datos:

1. Inicie sesión en [Customer Journey Analytics](https://analytics.adobe.com) y seleccione **[!UICONTROL Vistas de datos]**, opcionalmente desde **[!UICONTROL Administración de datos]**, en el menú superior.
1. Para crear una vista de datos, seleccione **[!UICONTROL Crear nueva vista de datos]**. También puede seleccionar una vista de datos existente de la lista de vistas de datos para editarla.


## Configuración {#configure}

Para configurar una vista de datos nueva o existente, haga lo siguiente:

![Configurar vista de datos con la ficha de contenedores independiente](assets/data-view-configure-containers.png)



1. Seleccione la pestaña **[!UICONTROL Configurar]** (si no está activa).
1. Especifique los detalles de **[!UICONTROL Configuración]**, **[!UICONTROL Compatibilidad]**, **[!UICONTROL Configuración de IA]** y **[!UICONTROL Calendario]** (ver a continuación).
1. Seleccionar **[!UICONTROL Guardar y continuar]** para seguir configurando la vista de datos nueva o la existente. Seleccionar **[!UICONTROL Guardar]** para almacenar la configuración para la vista de datos existente.


### Configuración {#configure-settings}

>[!CONTEXTUALHELP]
>id="dataview_externalid"
>title="ID externo"
>abstract="Cambiar el ID externo afecta al modo en que el nombre de la vista de datos aparece en las fuentes externas, como las herramientas de inteligencia empresarial."


Proporciona una configuración general para la vista de datos.

| Configuración | Descripción |
| --- | --- |
| **[!UICONTROL Conexión]** | Este campo vincula la vista de datos con la conexión establecida anteriormente, que tiene uno o varios conjuntos de datos de Adobe Experience Platform. |
| **[!UICONTROL Nombre]** | Requerido. Nombre de la vista de datos. Este valor aparece en el menú desplegable superior derecho de Analysis Workspace. |
| **[!UICONTROL ID externo]** | Requerido. El nombre de la vista de datos que se puede utilizar en fuentes externas, como herramientas de inteligencia empresarial. El valor predeterminado es `unspecified`. Si no especifica un ID externo, el nombre se generará a partir del nombre de la vista de datos y reemplazando los espacios por guiones bajos. |
| **[!UICONTROL Descripción]** | Opcional. Adobe recomienda una descripción detallada para que los usuarios entiendan por qué existe la vista de datos y para quién está diseñada. |

{style="table-layout:auto"}

### Compatibilidad {#compatibility}


>[!CONTEXTUALHELP]
>id="dataview_dataviewsinadobejourneyoptimizer"
>title="Vistas de datos en Adobe Journey Optimizer"
>abstract="Customer Journey Analytics requiere una conexión y una vista de datos compatibles con Adobe Journey Optimizer. El sistema crea una conexión y una vista de datos de forma predeterminada. También puede habilitar esta opción para establecerla como la vista de datos predeterminada para los informes de Adobe Journey Optimizer, que agrega los componentes necesarios a la vista de datos y a los conjuntos de datos de la conexión."
>additional-url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/integrations/ajo#connection" text="Qué componentes y conjuntos de datos se añaden."


Proporciona la configuración que se aplica al usar Adobe Journey Optimizer además de Customer Journey Analytics.

Esta sección solo está visible para los administradores que están aprovisionados con Journey Optimizer.

| Configuración | Descripción |
| --- | --- |
| [!UICONTROL **Establecer como vista de datos predeterminada en Adobe Journey Optimizer**] | Esta opción de configuración estandariza los informes en Journey Optimizer y Customer Journey Analytics. También le permite realizar análisis avanzados de los datos de Adobe Journey Optimizer en Customer Journey Analytics (seleccionando ![Abrir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_OpenInLight_18_N.svg) [!UICONTROL **Analizar en CJA**] en Journey Optimizer).<p>Para realizar este tipo de análisis, Journey Optimizer necesita acceder a una vista de datos de Customer Journey Analytics.<p>Habilite esta opción para que sea la vista de datos predeterminada que se utilice en la creación de informes de Journey Optimizer para su zona protegida.</p><p>Esta opción de configuración hace lo siguiente automáticamente:</p><ul><li>Configura todos los conjuntos de datos de Journey Optimizer necesarios en la conexión asociada en Customer Journey Analytics para su uso con Journey Optimizer.</li><li>Crea un conjunto de métricas y dimensiones de Journey Optimizer en la vista de datos (incluidos campos derivados y métricas calculadas). Las etiquetas de contexto se establecen automáticamente en todas estas métricas y dimensiones.</li><li>Habilita automáticamente la opción **[!UICONTROL Usar en CJA]** en la conexión asociada con esta vista de datos. (Para obtener más información sobre esta opción, consulte [Usar una conexión de Journey Optimizer en Customer Journey Analytics](/help/connections/manage-connections.md)).<p>Si deshabilita manualmente esta opción una vez habilitada, la conexión y las vistas de datos asociadas se restablecerán a su estado predeterminado. Esto puede provocar cambios en los informes.</p></li></ul><p><p>Ten en cuenta lo siguiente al habilitar esta opción: <ul><li>Puede cambiar la vista de datos predeterminada más adelante, pero al hacerlo se podrían modificar los datos de la creación de informes de Journey Optimizer. Si elige deshabilitar esta opción después de habilitarla, se le pedirá que seleccione una nueva vista de datos predeterminada.</li><li>Si ya ha realizado personalizaciones manuales en los conjuntos de datos, dimensiones o métricas en la vista de datos de Customer Journey Analytics, las personalizaciones manuales permanecen intactas al habilitar esta opción de configuración. Esta opción realiza personalizaciones adicionales que estandarizan aún más la creación de informes en Journey Optimizer y Customer Journey Analytics. También puede realizar personalizaciones manuales después de habilitar esta opción.</li><li>Cuando esta opción está seleccionada, la conexión asociada con la vista de datos no se puede eliminar.</li></ul>Consulte [Integración de Adobe Journey Optimizer con Adobe Customer Journey Analytics](/help/integrations/ajo.md) para obtener más información. |

{style="table-layout:auto"}


### Configuración de IA

Seleccione **[!UICONTROL Habilitar para Data Insights Agent]** para habilitar la vista de datos para [Data Insights Agent](/help/data-analysis-ai.md). Data Insights Agent es un agente de conversación de IA generativa al que se puede acceder desde el asistente de IA de Customer Journey Analytics. Le ayuda a analizar rápidamente los datos con indicaciones de texto. El agente crea visualizaciones relevantes en Analysis Workspace utilizando componentes de la vista de datos y utilizando los datos reales.


### Calendario

Indica el formato de calendario que desea que siga la vista de datos. Puede tener varias vistas de datos basadas en la misma [Conexión](/help/connections/create-connection.md) y proporcionarles diferentes tipos de calendario o zonas horarias. Estas vistas de datos pueden permitir que equipos que utilicen distintos tipos de calendario satisfagan sus necesidades respectivas con los mismos datos subyacentes.

| Configuración | Descripción |
| --- | --- |
| [!UICONTROL **Zona horaria**] | Elija en qué zona horaria desea que se presenten los datos. Si elige una zona horaria que funcione según el horario de verano, los datos se ajustan automáticamente para reflejarlo. En primavera, cuando los relojes se adelantan, hay un espacio de una hora. En otoño, cuando los relojes se atrasan, se repite una hora durante el cambio del horario de verano. |
| [!UICONTROL **Tipo de calendario**] | Determine cómo se agrupan las semanas del mes.<br>**Gregoriano:** Formato de calendario estándar. Los trimestres se agrupan por mes.<br>**4-5-4 Ventas minoristas:** Calendario comercial estandarizado 4-5-4. El primer y último mes del trimestre contiene cuatro semanas, mientras que el segundo mes del trimestre consta de cinco semanas.<br>**Personalizado (4-5-4):** similar al calendario 4-5-4 excepto que puede elegir el primer día del año y el año en el que se produce la semana extra.<br>**Personalizado (4-4-5):** el primer y el segundo meses de cada trimestre contienen 4 semanas, mientras que la última semana de cada trimestre constan de 5 semanas.<br>**Personalizado (5-4-4):** el primer mes de cada trimestre consta de 5 semanas, mientras que el segundo y el tercer mes de cada trimestre constan de 4 semanas. |
| [!UICONTROL **Primer mes del año**] y [!UICONTROL **primer día de la semana**] | Visible para el tipo de calendario gregoriano. Especifique en qué mes desea que comience el año del calendario y cada semana. |
| [!UICONTROL **Primer día del año actual**] | Visible para tipos de calendario personalizados. Especifique qué día del año desea que comience el año actual. El calendario aplica automáticamente el formato del primer día de cada semana en función de este valor. |
| [!UICONTROL **Año que incluye la semana “extra”**] | Con la mayoría de los calendarios de 364 días (52 semanas de 7 días cada uno), cada año se acumulan varios días restantes hasta formar una semana extra. Esta semana extra se agrega al último mes de ese año. Especifique a qué año desea agregar la semana adicional.<br><br/>**Semanas adicionales y años bisiestos**<br/> Al seleccionar un **[!UICONTROL Tipo de calendario]** personalizado (**[!UICONTROL Personalizado (4-5-4)]**, **[!UICONTROL Personalizado (4-4-5)]** o **[!UICONTROL Personalizado (5-4-4)]**), los días restantes se acumulan cada año hasta que sumen una semana adicional completa (siete días). Esa semana adicional se añade al año que seleccione en **[!UICONTROL Año que incluye la semana “extra”]**.<br/><br/>Los años bisiestos no se muestran de forma intencionada en el **[!UICONTROL Año que incluye la semana “extra”]**. Sin embargo, un año bisiesto puede contener 53 semanas. Para que un año bisiesto contenga 53 semanas, seleccione un año no bisiesto en **[!UICONTROL Año que incluye la semana “extra”]** para garantizar que la desviación acumulada de la fecha sume hasta siete días para el año bisiesto de destino. Por ejemplo: para tener 53 semanas en 2024, seleccione **[!UICONTROL 2019]**. De 2019 a 2024, la deriva de fecha total es de 7 días (2020 (+2), 2021 (+1), 2022 (+1), 2023 (+1) y 2024 (+2)), lo que resulta en una semana 53 en 2024.<br/><br/>La selección de **[!UICONTROL Primer día del año actual]** afecta dónde aterriza la semana extra. Confirme la configuración con la vista previa del calendario. |

{style="table-layout:auto"}

## Contenedores

{{release-limited-testing-section}}


>[!BEGINTABS]

>[!TAB Estándar]

![Configuración de una vista de datos](assets/data-view-containers-b2c.png)

>[!TAB B2B Edition]

![Configuración de una vista de datos B2B](assets/data-view-containers-b2b.png)

>[!ENDTABS]

En la ficha **[!UICONTROL Contenedores]** puede cambiar el nombre de los contenedores del sistema y agregar contenedores personalizados.

### Contenedores del sistema

Designa el nombre de los contenedores para la vista de datos. Los nombres de contenedores se utilizan frecuentemente en [segmentos](/help/components/segments/seg-overview.md#containers).

| Nombre del contenedor | Nombre para mostrar (predeterminado) | Descripción |
| --- | --- | --- |
| globalAccount | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Cuenta global &#x200B;]** | El contenedor [!UICONTROL Cuenta global] incluye todas las sesiones y eventos de las cuentas globales dentro del lapso de tiempo especificado. Si su organización utiliza un término diferente, puede cambiar el nombre del contenedor aquí. |
| persona | **[!UICONTROL Persona]** | El contenedor [!UICONTROL Persona] incluye todas las sesiones y eventos de las personas en un lapso de tiempo específico. Si su organización utiliza un término diferente (por ejemplo, visitante o usuario), puede cambiar el nombre del contenedor aquí. |
| sesión | **[!UICONTROL Sesión]** | El contenedor [!UICONTROL Sesión] le permite identificar interacciones de páginas, campañas o conversiones para una sesión específica. Puede cambiar el nombre de este contenedor a Visita o a cualquier otro término que prefiera. |
| oportunidad | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Oportunidad &#x200B;]** | El contenedor [!UICONTROL Oportunidad] incluye todas las visitas y vistas de página de los visitantes en un lapso de tiempo específico. Si su organización utiliza un término diferente, puede cambiar el nombre del contenedor aquí. |
| purchaseGroup | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Grupo de compra &#x200B;]** | El contenedor [!UICONTROL Grupo de compras] incluye todas las visitas y vistas de página de los visitantes en un lapso de tiempo específico. Si su organización utiliza un término diferente, puede cambiar el nombre del contenedor aquí. |
| evento | **[!UICONTROL Evento]** | El contenedor [!UICONTROL Evento] define eventos individuales en un conjunto de datos. Si su organización utiliza un término diferente (por ejemplo, Visitas individuales o Vistas de página), puede cambiar el nombre del contenedor aquí. |
| account | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Cuenta &#x200B;]** | El contenedor [!UICONTROL Cuenta] incluye todas las sesiones y eventos de las cuentas dentro del lapso de tiempo especificado. Si su organización utiliza un término diferente, puede cambiar el nombre del contenedor aquí. |

Para cambiar el nombre de los contenedores del sistema:

1. Seleccione ![Editar](/help/assets/icons/Edit.svg) para editar el **[!UICONTROL nombre para mostrar]** del contenedor.
1. Defina un nuevo nombre para el contenedor.
1. Seleccione **[!UICONTROL Guardar]**.


### Contenedores personalizados

Agrega contenedores personalizados a su vista de datos para que pueda usar estos contenedores para [análisis de subeventos](/help/components/segments/sub-event.md). Los contenedores personalizados se pueden definir desde:

* objetos o matrices disponibles dentro de los conjuntos de datos que forman parte de la conexión. Por ejemplo, **[!UICONTROL productListItems]**, **[!UICONTROL content_assets]** o **[!UICONTROL placeContext.activePOIs]**.
* campos derivados que devuelven una matriz mediante el uso de la función [Split](/help/data-views/derived-fields/derived-fields.md#split).
* componentes de vista de datos configurados para devolver una matriz usando la configuración del componente [Substring](/help/data-views/component-settings/substring.md) con la opción [Delimitador](/help/data-views/component-settings/substring.md#delimiter).

Para agregar un contenedor personalizado:

1. Seleccione **[!UICONTROL Agregar contenedor personalizado]**.
1. En el diálogo **[!UICONTROL Agregar contenedor]**:
   1. Seleccione un contenedor del menú desplegable **[!UICONTROL Contenedor]**. Por ejemplo: **[!UICONTROL productListItems.productCategories]**. Tras la selección, verá valores actualizados para **[!UICONTROL Ruta de esquema]** y **[!UICONTROL Tipo de esquema]**.

   1. Escriba un **[!UICONTROL nombre para mostrar]** para el contenedor. Por ejemplo: `Product Categories`.
   1. Seleccione **[!UICONTROL Guardar]**.

Para editar un contenedor personalizado:

1. Seleccione ![Más](/help/assets/icons/More.svg) para el contenedor personalizado en la columna **[!UICONTROL Nombre para mostrar]**.
1. Seleccione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** en el menú contextual.
1. En el diálogo **[!UICONTROL Editar contenedor]**:
   1. Modifique **[!UICONTROL Contenedor]**, **[!UICONTROL Nombre para mostrar]** o ambos.
   1. Seleccione **[!UICONTROL Guardar]**.

Para eliminar un contenedor personalizado:

1. Seleccione ![Más](/help/assets/icons/More.svg) para el contenedor personalizado en la columna Nombre para mostrar.
1. Seleccione ![Eliminar](/help/assets/icons/Delete.svg) **[!UICONTROL Eliminar]** del menú contextual.

   >[!NOTE]
   >
   >El contenedor personalizado se elimina sin confirmación.
   >

Para cambiar la lista de contenedores personalizados:

1. Seleccione ![ColumnSetting](/help/assets/icons/ColumnSetting.svg).
1. En **[!UICONTROL Personalizar tabla]**:
   1. Seleccione las columnas que desea mostrar.
   1. Seleccione **[!UICONTROL Guardar]**.


## Componentes

A continuación, puede establecer los componentes de una vista de datos, lo que significa que puede crear métricas y dimensiones a partir de elementos de esquema. También puede utilizar componentes estándares.

>[!IMPORTANT]
>
>Se pueden añadir hasta 5000 métricas y 5000 dimensiones a una sola vista de datos.

1. Seleccione la pestaña **[!UICONTROL Componentes]**.

   ![Pestaña Componentes](assets/dataview-components.png)

   Puede ver la [!UICONTROL Conexión] en la parte superior izquierda, que contiene los conjuntos de datos y sus [!UICONTROL Campos de esquema] a continuación.  Todas las vistas de datos incluyen componentes estándar como Eventos, Personas, Métricas de sesión y dimensiones temporales.<ul><li>Cuando define [contenedores personalizados](#containers-1), las métricas se agregan automáticamente como ![ShowAllLayer](/help/assets/icons/ShowAllLayer.svg) **[!UICONTROL _nombre de contenedor personalizado _Ocurrencias]**.</li><li>El sistema aplica el filtro **[!UICONTROL no está obsoleto]** de forma predeterminada, de modo que solo aparecen los campos de esquema no obsoletos.</li></ul>

1. Busque un campo de esquema mediante ![icono de búsqueda](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) **[!UICONTROL Buscar campos de esquema]** o busque un campo accediendo a cualquiera de las colecciones de conjuntos de datos, como ![Carpeta](/help/assets/icons/Folder.svg) **[!UICONTROL Conjuntos de datos de eventos]** o ![Carpeta](/help/assets/icons/Folder.svg) **[!UICONTROL Conjuntos de datos de búsqueda]**. Para los conjuntos de datos de evento, hay disponibles colecciones independientes para ![Folder](/help/assets/icons/Folder.svg) **[!UICONTROL campos XDM]** y ![Folder](/help/assets/icons/Folder.svg) **[!UICONTROL Campos adhoc y relacionales]**.<br/>También puede crear un campo derivado mediante ![Icono de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) **Crear campo derivado**. Consulte [Campos derivados](./derived-fields/derived-fields.md) para obtener más información.

1. Cuando haya encontrado el campo de esquema específico o definido el campo derivado, arrastre ese campo, como ![Icono de identificador](https://spectrum.adobe.com/static/icons/workflow_22/Smock_DragHandle_22_N.svg) **[!UICONTROL Nombre de página]**, desde el carril izquierdo a la sección **[!UICONTROL Métricas]** o **[!UICONTROL Dimensiones]** debajo de **[!UICONTROL Componentes incluidos]**.
Puede arrastrar el mismo campo de esquema a las secciones de dimensiones o métricas varias veces y configurar la misma dimensión o métrica de diferentes maneras. Por ejemplo, en el campo pageName, cree las dimensiones `Product Pages` y `Error pages` con diferentes [configuraciones del componente](component-settings/overview.md) a la derecha.
Si arrastra una carpeta de campos del esquema desde el carril izquierdo, los campos de la carpeta se ordenarán automáticamente en la sección correspondiente. Los campos de cadena terminan en la sección [!UICONTROL Dimensiones] y los tipos de esquema numérico terminan en la sección [!UICONTROL Métricas]. También puede hacer clic en **[!UICONTROL Añadir todo]** y todos los campos del esquema se añadirán a su sección respectiva.

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

1. Seleccionar **[!UICONTROL Guardar y continuar]** para seguir configurando la vista de datos nueva o la existente. Seleccionar **[!UICONTROL Guardar]** para almacenar la configuración para la vista de datos existente.

### Duplicado de métricas o dimensiones

Duplicar métricas o dimensiones y luego modificar configuraciones específicas es una manera eficaz de crear varias métricas o dimensiones a partir de un único campo de esquema. Seleccione la configuración [!UICONTROL Duplicate] debajo del nombre de la métrica o dimensión en la parte superior derecha. Modifique la nueva métrica o dimensión, y guárdela con un nombre más descriptivo.

### Filtrado de campos de esquema o conjuntos de datos

Puede filtrar los campos de esquema ![Icono de filtro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) en el carril izquierdo por [!UICONTROL tipo de datos], [!UICONTROL conjuntos de datos], [!UICONTROL gobernanza de datos] y [!UICONTROL otros] criterios ([!UICONTROL contiene datos], [!UICONTROL es identidad] y [!UICONTROL no está obsoleto]):

![Filtrar campos](assets/dataview-components-filter.png)

>[!TIP]
>
>Si los componentes no se cargan correctamente en la vista de datos y ve un mensaje de error, consulte [Falta de permisos](../troubleshooting/lack-of-permissions.md) para obtener una solución.


### Componentes incluidos {#included-components}

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_custom"
>title="Etiquetas personalizadas"
>abstract="Además de las etiquetas proporcionadas por Adobe, también puede definir sus propias etiquetas personalizadas para su organización."
>additional-url="https://experienceleague.adobe.com/es/docs/experience-platform/data-governance/labels/overview" text="Información general sobre las etiquetas de uso de datos"

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_contract"
>title="Etiquetas de contrato"
>abstract="Las etiquetas de contrato (C) se utilizan para categorizar los datos que tienen obligaciones contractuales o están relacionados con las políticas de gobernanza de datos de su organización."
>additional-url="https://experienceleague.adobe.com/es/docs/experience-platform/data-governance/labels/overview" text="Información general sobre las etiquetas de uso de datos"

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_identity"
>title="Etiquetas de identidad"
>abstract="Las etiquetas de identidad (I) se utilizan para categorizar los datos que permiten identificar a una persona específica o ponerse en contacto con ella."
>additional-url="https://experienceleague.adobe.com/es/docs/experience-platform/data-governance/labels/overview" text="Información general sobre las etiquetas de uso de datos"

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_sensitive"
>title="Etiquetas confidenciales"
>abstract="Las etiquetas confidenciales (S) se utilizan para categorizar los datos que usted y su organización consideran confidenciales."
>additional-url="https://experienceleague.adobe.com/es/docs/experience-platform/data-governance/labels/overview" text="Información general sobre las etiquetas de uso de datos"


>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_partnerecosystem"
>title="Ecosistema de socios"
>abstract="Las etiquetas de ecosistema de socios (P) se utilizan para categorizar los datos que se comparten con socios de terceros."
>additional-url="https://experienceleague.adobe.com/es/docs/experience-platform/data-governance/labels/overview" text="Información general sobre las etiquetas de uso de datos"

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_policies"
>title="Políticas"
>abstract="Para cumplir con la normativa de datos, implemente políticas de uso de datos. Estas políticas describen acciones de marketing permitidas o restringidas en los datos de Experience Platform. Los filtros de las políticas se aplican a la política habilitada a la Vista de datos."
>additional-url="https://experienceleague.adobe.com/es/docs/experience-platform/data-governance/labels/overview" text="Información general sobre las etiquetas de uso de datos"


>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_responsibleengagement"
>title="Etiquetas de participación responsable"
>abstract="Las etiquetas de participación responsable se utilizan para apoyar una participación responsable."
>additional-url="https://experienceleague.adobe.com/es/docs/experience-platform/data-governance/labels/overview" text="Información general sobre las etiquetas de uso de datos"


La sección **[!UICONTROL Componentes incluidos]** contiene la lista de **[!UICONTROL Métricas]** y **[!UICONTROL Dimensiones]** que configuró para la vista de datos.

* Para buscar componentes, utilice ![Búsqueda](/help/assets/icons/Search.svg) **[!UICONTROL _Buscar componentes_]**.
* Para filtrar los componentes incluidos en la lista, seleccione ![Filtro](/help/assets/icons/Filter.svg).

  ![Cuadro de diálogo Filtro de componentes incluidos](assets/dataview_includedcomponents_filter.png)

  En el cuadro de diálogo **[!UICONTROL Filtrar campo por]**, puede filtrar según las siguientes categorías:

   * **[!UICONTROL Tipo de datos]**: puede seleccionar uno o más de los siguientes tipos de datos: [!UICONTROL Cadena], [!UICONTROL Entero], [!UICONTROL Corto], [!UICONTROL Booleano], [!UICONTROL Doble], [!UICONTROL Byte], [!UICONTROL Largo], [!UICONTROL Fecha] o [!UICONTROL Fecha-hora].
   * **[!UICONTROL Conjuntos de datos]**: seleccione uno o más conjuntos de datos.
   * **[!UICONTROL Control de datos]**: seleccione una o más etiquetas de las [!UICONTROL etiquetas personalizadas], [!UICONTROL etiquetas de contrato], [!UICONTROL etiquetas de identidad], [!UICONTROL etiquetas de confidencialidad], [!UICONTROL ecosistema de socios] o subcategorías de [!UICONTROL directivas].
   * **[!UICONTROL Otros]**: seleccione una o más de las opciones [!UICONTROL Contiene datos], [!UICONTROL Es identidad] o [!UICONTROL No está obsoleto].

  Seleccione **[!UICONTROL Aplicar]** para aplicar los filtros.



## Configuración {#dataview-settings}

1. Seleccione la pestaña **[!UICONTROL Configuración]**.

   Configuración de la ![vista de datos](assets/dataview-settings.png)

1. Configure los segmentos para aplicarlos a toda la vista de datos. Consulte [Configuración (segmentos)](#settings-filters) más abajo.
1. Configure el tiempo de espera de sesión y las métricas. Consulte [Configuración de sesión](#session-settings) más abajo.

1. Seleccionar **[!UICONTROL Guardar y continuar]** para seguir configurando la vista de datos nueva o la existente. Seleccionar **[!UICONTROL Guardar]** para almacenar la configuración para la vista de datos existente.

### Configuración (segmentos) {#segment-settings}

Puede añadir segmentos que se apliquen a una vista de datos entera. Este filtro se aplica a cualquier informe que se ejecute en Worskpace. Arrastre un filtro desde la lista en el carril izquierdo hasta el campo **[!UICONTROL Añadir segmentos]**.

### Configuración de sesión

Determine el período de inactividad entre los eventos antes de que caduque una sesión y se inicie una nueva. Se requiere un período de tiempo. Si lo desea, puede forzar el inicio de una nueva sesión cuando un evento contenga una métrica determinada. Consulte [Configuración de sesión](session-settings.md) para obtener más información.

### Previsualización de datos

La vista previa de datos compara (para los distintos contenedores) los datos de esta vista de datos con los datos de la conexión. El porcentaje de vista previa se basa en el número total de la conexión de los últimos 90 días.

Si la previsualización no se carga, la conexión se sigue llenando.

Una vez especificada toda la configuración deseada, haga clic en **[!UICONTROL Guardar y finalizar]**.
