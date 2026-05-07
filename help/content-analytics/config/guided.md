---
title: Configuración guiada de Content Analytics
description: Cómo configurar Content Analytics mediante una configuración guiada de incorporación
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: 21bf687f3cff101ee1b3e4be3d870de270f82e89
workflow-type: tm+mt
source-wordcount: '3991'
ht-degree: 48%

---

# Configuración guiada de Content Analytics

La configuración guiada le ayuda a configurar Content Analytics de una forma rápida y sencilla. La configuración guiada utiliza un asistente para establecer los requisitos para configurar Content Analytics automáticamente para su organización. En la pantalla **[!UICONTROL Configuración]**, puede crear una configuración nueva o editar una existente.

>[!IMPORTANT]
>
>Solo puede tener una configuración de Content Analytics por cada zona protegida de su organización.

>[!NOTE]
>
>El asistente de configuración admite varias vistas de datos y canales, y es diferente de la versión anterior, que solo admitía una vista de datos y solo el canal web. Debe seleccionar una zona protegida y una conexión para poder seleccionar una o más vistas de datos en la sección [Vistas de datos](#data-views). Las configuraciones de **[!UICONTROL Experience Capture]**, **[!UICONTROL Recopilación de datos]** y **[!UICONTROL invalidaciones de encabezados]** dependen del canal y forman parte de cada uno de los canales que configuras en la sección [Canales](#channels).

Para acceder a la configuración de Content Analytics

* Seleccione **[!UICONTROL Administración de datos]** > **[!UICONTROL configuración de Content Analytics]** en el menú principal de Customer Journey Analytics.

En la pantalla **[!UICONTROL Configuración de Content Analytics]**, verá una tabla de configuraciones de Content Analytics existentes.

![configuraciones de Content Analytics](../assets/aca-configuration-table.png)
Para cada configuración, están disponibles los siguientes detalles:

| Columna | Descripción |
|---|---|
| **[!UICONTROL Nombre]** | El nombre de la configuración. |
| **[!UICONTROL Creado por]** | La cuenta técnica que ha creado la configuración. |
| **[!UICONTROL Creado el]** | La marca de tiempo de creación de la configuración. |
| **[!UICONTROL Modificado el]** | La marca de tiempo de la última modificación de la configuración. |
| **[!UICONTROL Zona protegida]** | La zona protegida dentro de la organización en la que se configura y se implementa (o se planea implementar) Content Analytics. |
| **[!UICONTROL Estado]** | El estado de la configuración. El estado indica en cuántos canales habilitados se completó la configuración. Use ![InfoOutline](/help/assets/icons/InfoOutline.svg) para abrir una ventana emergente con más detalles. |

Puede utilizar ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para personalizar la tabla. Seleccione qué columnas desea mostrar en el cuadro de diálogo **[!UICONTROL Personalizar tabla]** y seleccione **[!UICONTROL Aplicar]** para aplicar los cambios.

En la pantalla **[!UICONTROL Configuración]** de Content Analytics, puede crear una nueva configuración o editar una configuración existente.

Para crear una nueva configuración:

* Seleccione **[!UICONTROL Crear configuración]**. Esta acción abre el [asistente de configuración guiada](#guided-configuration-wizard).

Para editar una configuración existente:

* Seleccione ![Más](/help/assets/icons/More.svg) y, a continuación, ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** para una configuración de análisis de contenido existente. Esta acción abre el [asistente de configuración guiada](#guided-configuration-wizard).

## Asistente de la configuración guiada

El asistente de configuración guiada consta de cuatro secciones ([Detalles](#details), [Conexión](#connection), [Vista de datos](#data-view) y [Canales](#channels)), cada una de las cuales solicita detalles necesarios para configurar Content Analytics correctamente. Complete cada sección antes de pasar a la siguiente, ya que algunos ajustes de una sección pueden depender de los valores de configuración de secciones anteriores.

### Detalles {#onboarding-details}

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="Detalles"
>abstract="Introduzca un nombre para la conexión. En las secciones **[!UICONTROL Vista de datos]**, **[!UICONTROL Captura y definición de experiencias]** y **[!UICONTROL Recopilación de datos]**, proporcione más detalles para garantizar que Content Analytics se pueda configurar correctamente."

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="Detalles"
>abstract="Esta guía establece los requisitos necesarios para configurar el análisis de contenido. Proporcione un nombre para esta configuración"

>[!CONTEXTUALHELP]
>id="aca_onboarding_connection_boldheader"
>title="Conexión"
>abstract="**Conexión**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_connection_header"
>title="Conexión"
>abstract="Seleccione una conexión existente de Customer Journey Analytics con la que desee combinar los datos de Content Analytics."

Cada configuración requiere un nombre único. Por ejemplo, `Example Content Analytics configuration`. El nombre es necesario para guardar o implementar una configuración.

Para cada configuración, también debe seleccionar la zona protegida para la que desea configurar Content Analytics.

![Detalles de la configuración de Content Analytics](../assets/aca-configuration-details.png)

* **[!UICONTROL Nombre]**: cada configuración requiere un nombre único. Por ejemplo, `Example Content Analytics configuration`. El nombre es necesario para guardar o implementar una configuración.

* **[!UICONTROL espacio aislado]**: La configuración requiere un espacio aislado. Seleccione una zona protegida de la lista de zonas protegidas a las que tenga acceso y en las que se recopilen los datos que desee utilizar para Content Analytics.

  Si cambia un simulador para pruebas configurado para el que ha definido una conexión y, opcionalmente, vistas de datos, se le notificará que es necesario volver a configurar la conexión y las vistas de datos.

### Conexión

Debe seleccionar una conexión a la que desee agregar la recopilación de datos de Content Analytics.

Si no ha seleccionado ninguna conexión para la configuración:

1. Use ![Datos](/help/assets/icons/Data.svg) **[!UICONTROL Seleccione una conexión]** para abrir el cuadro de diálogo **[!UICONTROL Seleccionar una conexión]** que enumera todas las conexiones disponibles en la zona protegida.
1. En el cuadro de diálogo **[!UICONTROL Seleccionar una conexión]**, seleccione ![SeleccionarCuadro](/help/assets/icons/SelectBox.svg) una conexión que desee utilizar. Solo puede seleccionar una conexión.
1. Seleccione **[!UICONTROL Usar conexión]**.

Si ya ha seleccionado una conexión, pero desea cambiar esa conexión:

1. Seleccione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]**.
1. En el cuadro de diálogo **[!UICONTROL Seleccionar una conexión]**, modifique la conexión que desea utilizar.
1. Seleccione **[!UICONTROL Usar conexión]**.


### Vistas de datos {#onboarding-data-view}

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="Vista de datos"
>abstract="Para la configuración de Content Analytics, debe seleccionar una vista de datos existente. Por lo tanto, puede combinar los datos de Content Analytics con otros datos."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="Vista de datos"
>abstract="Seleccione una vista de datos existente de Customer Journey Analytics con la que desee combinar sus datos de Content Analytics."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="Vista de datos"
>abstract="Seleccione una vista de datos existente de Customer Journey Analytics con la que desee combinar sus datos de Content Analytics con<br/>."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_change_dialog"
>title="Nueva vista de datos"
>abstract="Ha seleccionado una nueva vista de datos para esta configuración. La nueva vista de datos se actualizará para incluir las métricas y dimensiones de análisis de contenido. Se eliminarán estas métricas y dimensiones de la vista de datos seleccionada originalmente.<br/><br/>Si hay una conexión diferente asociada con la nueva vista de datos, la conexión se actualizará para incluir conjuntos de datos del análisis de contenido. Los conjuntos de datos de análisis de contenido no se eliminan de la conexión seleccionada originalmente."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_current_cleanup_labels_dialog"
>title="Limpieza de la vista de datos seleccionada"
>abstract="Ha seleccionado una vista de datos que ya está aprovisionada para el Content Analytics. Esa configuración de Content Analytics existente se elimina y la vista de datos se aprovisiona con la nueva configuración."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_prev_cleanup_labels_dialog"
>title="Limpieza de la vista de datos anterior"
>abstract="Ha seleccionado una nueva vista de datos. Se elimina la configuración de Content Analytics para la vista de datos seleccionada anteriormente."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_new_dialog"
>title="Nueva vista de datos"
>abstract="Ha seleccionado una nueva vista de datos para esta configuración. La nueva vista de datos se actualizará para incluir las métricas y dimensiones de análisis de contenido. Se eliminarán las métricas y dimensiones similares de la vista de datos existente.<br/>Si hay una conexión diferente asociada con la nueva vista de datos, la conexión se actualizará para incluir conjuntos de datos del análisis de contenido. Tenga en cuenta que los conjuntos de datos del análisis de contenido no se eliminan de la configuración existente."


>[!CONTEXTUALHELP]
>id="ac_onboarding_dataviews_button"
>title="Vista de datos"
>abstract="Para la configuración de Content Analytics, debe seleccionar una o más vistas de datos. Por lo tanto, puede combinar los datos de Content Analytics con otros datos."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_header"
>title="Vistas de datos"
>abstract="Seleccione una o varias vistas de datos existentes de Customer Journey Analytics con las que desee combinar los datos de Content Analytics."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_header_alt"
>title="Vistas de datos"
>abstract="Seleccione una o más vistas de datos existentes de Customer Journey Analytics con las que desee combinar los datos de Content Analytics.<br/>"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_new_dialog"
>title="Vistas de datos seleccionadas"
>abstract="Ha modificado las vistas de datos seleccionadas para esta configuración. Las vistas de datos seleccionadas se actualizarán para incluir las métricas y dimensiones de Content Analytics. Estas métricas y dimensiones se eliminarán de las vistas de datos seleccionadas anteriormente que ya no estén seleccionadas.<br/><br/>Si hay una conexión diferente asociada con las vistas de datos seleccionadas, la conexión se actualizará para incluir los conjuntos de datos de Content Analytics. Los conjuntos de datos de análisis de contenido no se eliminan de la conexión seleccionada originalmente.<br/><br/>Todas las vistas de datos seleccionadas heredan los canales que forman parte de esta configuración."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_change_dialog"
>title="Vistas de datos seleccionadas"
>abstract="Ha modificado las vistas de datos seleccionadas para esta configuración. Las vistas de datos seleccionadas se actualizarán para incluir las métricas y dimensiones de Content Analytics. Estas métricas y dimensiones se eliminarán de las vistas de datos seleccionadas anteriormente que ya no estén seleccionadas.<br/><br/>Si hay una conexión diferente asociada con las vistas de datos seleccionadas, la conexión se actualizará para incluir los conjuntos de datos de Content Analytics. Los conjuntos de datos de análisis de contenido no se eliminan de la conexión seleccionada originalmente.<br/><br/>Todas las vistas de datos seleccionadas heredan los canales que forman parte de esta configuración."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_current_cleanup_labels_dialog"
>title="Vistas de datos seleccionadas"
>abstract="Ha modificado las vistas de datos seleccionadas para esta configuración. Las vistas de datos seleccionadas se actualizarán para incluir las métricas y dimensiones de Content Analytics. Estas métricas y dimensiones se eliminarán de las vistas de datos seleccionadas anteriormente que ya no estén seleccionadas.<br/><br/>Si hay una conexión diferente asociada con las vistas de datos seleccionadas, la conexión se actualizará para incluir los conjuntos de datos de Content Analytics. Los conjuntos de datos de análisis de contenido no se eliminan de la conexión seleccionada originalmente.<br/><br/>Todas las vistas de datos seleccionadas heredan los canales que forman parte de esta configuración."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataviews_prev_cleanup_labels_dialog"
>title="Vistas de datos seleccionadas"
>abstract="Ha modificado las vistas de datos seleccionadas para esta configuración. Las vistas de datos seleccionadas se actualizarán para incluir las métricas y dimensiones de Content Analytics. Estas métricas y dimensiones se eliminarán de las vistas de datos seleccionadas anteriormente que ya no estén seleccionadas.<br/><br/>Si hay una conexión diferente asociada con las vistas de datos seleccionadas, la conexión se actualizará para incluir los conjuntos de datos de Content Analytics. Los conjuntos de datos de análisis de contenido no se eliminan de la conexión seleccionada originalmente.<br/><br/>Todas las vistas de datos seleccionadas heredan los canales que forman parte de esta configuración."

>[!CONTEXTUALHELP]
>id="aca_onboarding_channels_button"
>title="Canales"
>abstract="Habilite y configure uno o varios canales para la configuración."

>[!CONTEXTUALHELP]
>id="aca_onboarding_channels_header"
>title="Canales"
>abstract="Habilite y configure uno o varios canales para la configuración. Todas las vistas de datos que forman parte de la configuración heredan los canales habilitados."


Su configuración requiere la selección de una o más [vistas de datos](/help/data-views/data-views.md).

Si no ha seleccionado vistas de datos para su configuración:

1. Use ![Datos](/help/assets/icons/Data.svg) **[!UICONTROL Seleccionar vista de datos]** para abrir el cuadro de diálogo **[!UICONTROL Vista de datos]** que enumera todas las vistas de datos disponibles para la conexión que ha configurado para Content Analytics.
1. En el cuadro de diálogo **[!UICONTROL Vista de datos]**, seleccione ![SeleccionarCuadro](/help/assets/icons/SelectBox.svg) una o más vistas de datos que desee usar.
1. Seleccione **[!UICONTROL Guardar]**.

Si ya ha seleccionado una o más vistas de datos, pero desea cambiar esa selección:

1. Seleccione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar selección de vista de datos]**.
1. En el cuadro de diálogo **[!UICONTROL Vista de datos]**, modifique la selección ![SelectBox](/help/assets/icons/SelectBox.svg) de las vistas de datos que desea utilizar.
1. Seleccione **[!UICONTROL Guardar]**.

Una vez que seleccione **[!UICONTROL Guardar]**, verá un cuadro de diálogo de **[!UICONTROL Vistas de datos seleccionadas]** que le informa sobre las implicaciones de incluir Content Analytics para las vistas de datos seleccionadas. Seleccione **[!UICONTROL Continuar]** para continuar o **[!UICONTROL Cancelar]** para cancelar.

Las siguientes acciones están disponibles en el cuadro de diálogo **[!UICONTROL Vista de datos]**:

* Para buscar un conjunto de datos específico, utilice el campo ![Buscar](/help/assets/icons/Search.svg).
* Para filtrar la lista de vistas de datos disponibles, seleccione ![Mostrar filtro](/help/assets/icons/Filter.svg). Puede filtrar la lista por [!UICONTROL Propietario].<br/>Use ![Ocultar](/help/assets/icons/Filter.svg) **[!UICONTROL Ocultar filtros]** para ocultar el panel del segmento.
* Para definir qué columnas desea mostrar en la tabla, seleccione ![Configuración de columna](/help/assets/icons/ColumnSetting.svg). Seleccione qué columnas desea mostrar en el cuadro de diálogo **[!UICONTROL Personalizar tabla]** y seleccione **[!UICONTROL Aplicar]** para aplicar los cambios.

### Canales

En la sección **[!UICONTROL Canales]**, seleccione los canales que desea habilitar para Content Analytics. Puede seleccionar entre **[!UICONTROL Móvil]** y **[!UICONTROL Web]**.

* Para seleccionar un canal que aún no haya configurado, seleccione **[!UICONTROL Habilitar]**.
* Para seleccionar un canal que ya está configurado pero cuya configuración desea cambiar, seleccione **[!UICONTROL Editar configuración]**.

A continuación, puede configurar el canal con más detalle. Esa configuración es diferente dependiendo de si habilita y configura o edita una configuración para el canal [mobile](#mobile) o [web](#web).

#### Móvil {#mobile}

<!-- For updated ACA -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_experience_locations_boldheader"
>title="Recopilación de datos de ubicaciones de experiencias móviles"
>abstract="**Ubicaciones de experiencia para excluir**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_experience_locations_header"
>title="Recopilación de datos de ubicaciones de experiencias móviles"
>abstract="Indique qué ubicaciones de experiencia deben **excluirse** al recopilar datos para Content Analytics. Asegúrese de excluir las ubicaciones de experiencias que puedan identificar personalmente."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_asset_locations_boldheader"
>title="Recopilación de datos de ubicaciones de recursos móviles"
>abstract="**Ubicaciones de recursos que excluir**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_asset_locations_header"
>title="Recopilación de datos de ubicaciones de recursos móviles"
>abstract="Indique qué ubicaciones de recursos deben **excluirse** al recopilar datos para Content Analytics. Asegúrese de excluir las ubicaciones de recursos que identifique personalmente."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_asset_urls_boldheader"
>title="Recopilación de datos de URL de recursos móviles"
>abstract="**URL de recursos que excluir**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_mobile_asset_urls_header"
>title="Recopilación de datos de URL de recursos móviles"
>abstract="Indique qué direcciones URL de recursos deben **excluirse** al recopilar datos para Content Analytics. Asegúrese de excluir las direcciones URL de recursos que lo identifiquen personalmente."

En el canal móvil, puede configurar [captura y definición de la experiencia](#experience-capture-and-definition), [recopilación de datos](#data-collection) y [invalidaciones del encabezado](#header-overrides).

##### Captura y definición de experiencias {#mobile-experience-capture-and-definition}

En esta sección, puede seleccionar incluir experiencias en los datos móviles que recopila con Content Analytics.  En el caso del canal móvil, una experiencia es lo que se ha registrado como experiencia con Adobe Experience Platform SDK para Content Analytics.

De manera predeterminada, **[!UICONTROL Incluir experiencias]** está deshabilitado.

Considere la posibilidad de incluir experiencias únicamente cuando haya instrumentado su aplicación móvil para registrar experiencias, rastrear vistas de experiencias y clics en experiencias.

##### Recopilación de datos {#mobile-data-collection}

La configuración de recopilación de datos permite definir qué datos (ubicaciones de experiencias, ubicaciones de recursos y URL de recursos) desea recopilar para Content Analytics. Asegúrese de que no recopila información de identificación personal como parte de esa recopilación de datos.

Para configurar la recopilación de datos:

* Utilice una propiedad de etiquetas móviles existente o cree una nueva propiedad de etiquetas móviles.

   * Para utilizar una propiedad de etiquetas móviles existente:

      1. Seleccione **[!UICONTROL Elegir existente]**.
      2. Seleccione una propiedad existente en el menú desplegable **[!UICONTROL Propiedad Etiquetas]**. Puede empezar a escribir para buscar y limitar las opciones disponibles. No puede seleccionar una propiedad Etiquetas que ya utilice otra configuración de Content Analytics implementada.


   * Para crear una nueva propiedad de etiquetas móviles:

      1. Seleccione **[!UICONTROL Crear nueva clase]**.
      1. Especifique un **[!UICONTROL Nombre de Etiquetas]**, por ejemplo `ACA Test for Documentation`.
      1. Especifique **[!UICONTROL dominios]**, por ejemplo, `example.com`.

* Indique qué ubicaciones de experiencia deben excluirse al recopilar datos para Content Analytics. Asegúrese de excluir las ubicaciones de experiencias que puedan identificar personalmente.

  Especifique una **[!UICONTROL cadena de expresión regular]** para **[!UICONTROL ubicaciones de experiencia que excluir]**. <br/>Por ejemplo: `^(?!.*documentation).*` para excluir todas las ubicaciones de experiencia de documentación de Content Analytics.

* Indique qué ubicaciones de recursos deben excluirse al recopilar datos para Content Analytics. Asegúrese de excluir las ubicaciones de recursos que identifique personalmente.

  Especifique una **[!UICONTROL cadena de expresión regular]** para **[!UICONTROL ubicaciones de recursos que excluir]**. <br/>Por ejemplo: `^(?!.*(logo\.jpg)).*$` para excluir todas las ubicaciones de recursos con imágenes de logotipo de JPEG de Content Analytics.

* Indique qué direcciones URL de recursos deben excluirse al recopilar datos para Content Analytics. Asegúrese de excluir las direcciones URL de recursos que lo identifiquen personalmente.

  Especifique una **[!UICONTROL cadena de expresión regular]** para **[!UICONTROL URL de recursos que excluir]**. <br/>Por ejemplo: `^(?!.*(logo\.jpg)).*$` para excluir todas las URL de recursos que hagan referencia a imágenes de logotipo de JPEG de Content Analytics.


##### Anulaciones de encabezado {#mobile-header-overrides}

<!-- needs modification for mobile channel -->

Opcionalmente, puede especificar en la sección **[!UICONTROL Anulaciones de encabezado]** un nombre de encabezado y un valor de encabezado secreto.  Este encabezado anula la configuración y garantiza que Content Analytics envíe un encabezado HTTP personalizado para recuperar los recursos de la aplicación móvil, evitando la detección de bots o las tecnologías de acceso al tráfico.

![Sección de invalidaciones de encabezado](/help/content-analytics/assets/aca-configuration-header-overrides.png)

1. Habilitar **[!UICONTROL Configurar invalidaciones de encabezado]**.
1. Escriba el **[!UICONTROL nombre del encabezado]**. Por ejemplo, `x-asset-service`.
1. Escriba el **[!UICONTROL valor del encabezado]**. Lo que especifique es secreto y no está visible en la interfaz de usuario (a menos que seleccione explícitamente revelar ![Visibilidad](/help/assets/icons/Visibility.svg) del valor durante la entrada).

##### Guardar {#mobile-save}

Una vez que haya configurado el canal móvil, seleccione **[!UICONTROL Guardar]** para guardar la configuración. Seleccione **[!UICONTROL Cancelar]** para cancelar la configuración.


#### Web {#web}

En el canal web, puedes configurar [captura y definición de la experiencia](#experience-capture-and-definition-1), [recopilación de datos](#data-collection-1) y [invalidaciones del encabezado](#header-overrides-1).

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="Captura y definición de experiencias"
>abstract="Puede seleccionar que se incluyan experiencias en los datos que recopila con Content Analytics. Cuando se selecciona, debe definir una o más combinaciones de una regex y parámetros de consulta para definir para qué URL desea incluir experiencias."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="Captura y definición de experiencias"
>abstract="Recopilar experiencias en el Content Analytics"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_parameters_header"
>title="Captura y definición de experiencias"
>abstract="Especifique los parámetros que determinan cómo se procesa el contenido en el sitio web."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_new_include_experiences"
>title="Captura y definición de experiencias"
>abstract="Cuando se habilita, se recopilan los datos de la experiencia, se generan los atributos de la experiencia y está disponible la creación de informes de experiencia."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_include_experiences"
>title="Captura y definición de experiencias"
>abstract="Cuando se habilita, se recopilan los datos de la experiencia, se generan los atributos de la experiencia y está disponible la creación de informes de experiencia. <br><br/>Use ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar]** para modificar la configuración de recopilación de datos para las experiencias en la propiedad Etiquetas asociada con la configuración actual."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="Captura y definición de experiencias"
>abstract="Debe editar la configuración de la recopilación de datos de experiencia en la extensión de Adobe Content Analytics."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="Recopilación de datos"
>abstract="Defina qué propiedad Etiquetas desea utilizar o cree una nueva. Y defina las páginas y los recursos que desea incluir o excluir mediante expresiones regulares."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tag_header"
>title="Recopilación de datos"
>abstract="**Proporcionar una propiedad Etiquetas**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_boldheader"
>title="Recopilación de datos"
>abstract="**Páginas para incluir/excluir**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_header"
>title="Recopilación de datos"
>abstract="Indique qué páginas deben **incluirse** o **excluirse** al recopilar datos para Content Analytics. Asegúrese de excluir las páginas de identificación personal."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_boldheader"
>title="Recopilación de datos"
>abstract="**Recursos para incluir/excluir**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_header"
>title="Recopilación de datos"
>abstract="Indique qué recursos deben **incluirse** o **excluirse** al recopilar datos para Content Analytics. Asegúrese de excluir los activos que le identifiquen personalmente."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_experiences_edit_button"
>title="Recopilación de datos"
>abstract="Puede editar la configuración de las páginas en la extensión de Adobe Content Analytics en la propiedad Etiqueta, asociada a la configuración seleccionada."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="Recopilación de datos"
>abstract="Puede editar la configuración de los recursos en la extensión de Adobe Content Analytics en la propiedad Etiqueta, asociada a la configuración seleccionada."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tags_disabled_description "
>title="Propiedad de etiquetas deshabilitada"
>abstract="La extensión de Content Analytics ya está activa."


<!-- For updated ACA -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_web_pages_boldheader"
>title="Recopilación de datos de páginas web"
>abstract="**Páginas para incluir/excluir**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_web_pages_header"
>title="Recopilación de datos de páginas web"
>abstract="Indique qué páginas deben **incluirse** o **excluirse** al recopilar datos para Content Analytics."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_web_assets_boldheader"
>title="Recopilación de datos de recursos web"
>abstract="**Recursos para incluir/excluir**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_web_assets_header"
>title="Recopilación de datos de recursos web"
>abstract="Indique qué recursos deben **incluirse** o **excluirse** al recopilar datos para Content Analytics. Asegúrese de excluir los activos que le identifiquen personalmente."


##### Captura y definición de experiencias {#web-experience-capture-and-definition}

En esta sección, puede seleccionar incluir experiencias en los datos web que recopila con Content Analytics.  Una experiencia consiste en todo el texto de una página web que se puede reproducir con la dirección URL de la visita inicial del usuario.

De manera predeterminada, **[!UICONTROL Incluir experiencias]** está desactivado. Cuando esté seleccionado, defina las direcciones URL para las que desea incluir experiencias.

Considere la posibilidad de incluir experiencias únicamente cuando se aplique lo siguiente:

* Las páginas del sitio deben poder reproducirse utilizando la dirección URL de la página.
* El contenido de texto que vea un usuario determinado se puede reproducir mediante la dirección URL de la página y no depende de las cookies u otros mecanismos de personalización.

>[!IMPORTANT]
>
>Implemente [versiones de Content Analytics](manual.md#versioning) para recopilar los cambios que realice en las experiencias (páginas) sujetas a Content Analytics.



###### Nueva configuración {#new-experiences-configuration}

Para incluir experiencias en una configuración nueva o no implementada:

![Captura y definición de experiencias de configuración de Content Analytics](../assets/aca-configuration-experience.png)

1. Habilite **[!UICONTROL Incluir experiencias]**. El cambio para habilitar experiencias afecta a lo siguiente:

   * Recopilación de datos en la extensión de Content Analytics
   * Proceso que genera atributos de experiencia a partir de datos de evento de Content Analytics
   * La plantilla de informes de Customer Journey Analytics.

1. Seleccione **[!UICONTROL Agregar regex]** para agregar una combinación de una expresión regular de dominio y parámetros de consulta.
1. Especifique cómo se representa el contenido en su sitio web definiendo combinaciones de una **[!UICONTROL expresión regular de dominio]** y **[!UICONTROL parámetros de consulta]** que afectan el contenido de la página.
   1. Introduzca una **[!UICONTROL Expresión regular de dominio]**, por ejemplo `/^(?!.*\b(store|help|admin)\b)/`. Asegúrese de omitir las expresiones regulares usando `/`. La expresión regular de dominio indica a qué direcciones URL se aplican estos parámetros. Por ejemplo, puede tener varios sitios y, para cada sitio, distintos parámetros controlan el contenido. Si los parámetros de consulta se aplican a todas las páginas, puede usar `.*` para indicar todas las páginas.
   1. Especifique una lista separada por comas de **[!UICONTROL parámetros de consulta]**, por ejemplo `outdoors, patio, kitchen`.
1. Seleccione **[!UICONTROL Quitar]** si desea quitar una combinación de expresión regular de dominio y parámetros de consulta.
1. Seleccione **[!UICONTROL Añadir Regex]** si desea añadir otra combinación de una expresión regular y parámetros de consulta.


###### Configuración implementada {#implemented-experiences-configuration}

Para editar experiencias existentes o incluir unas nuevas en una configuración implementada:

![Captura y definición de experiencias de configuración de Content Analytics](../assets/aca-configuration-experience-edit.png)

* Alternar **[!UICONTROL Incluir experiencias]** para habilitar o deshabilitar:

   * Proceso que genera atributos de experiencia a partir de datos de evento de Content Analytics
   * La plantilla de informes de Customer Journey Analytics.

* Seleccione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** para editar aún más la configuración de la recopilación de datos para experiencias en Content Analytics. Se le redirige a la extensión [Adobe Content Analytics](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting) en la propiedad Etiquetas que está asociada a la configuración actual.

##### Recopilación de datos {#web-data-collection}

La configuración de recopilación de datos permite definir qué datos (páginas, recursos) desea recopilar para Content Analytics. No recopile información personal identificable como parte de esa recopilación de datos.

Para configurar la recopilación de datos:

* Utilice una propiedad de etiquetas web existente o cree una nueva propiedad de etiquetas web.

   * Para utilizar una propiedad de etiquetas web existente:

      1. Seleccione **[!UICONTROL Elegir existente]**.
      2. Seleccione una propiedad existente en el menú desplegable **[!UICONTROL Propiedad Etiquetas]**. Puede empezar a escribir para buscar y limitar las opciones disponibles. No puede seleccionar una propiedad Etiquetas que ya utilice otra configuración de Content Analytics implementada.


   * Para crear una nueva propiedad de etiquetas web:

      1. Seleccione **[!UICONTROL Crear nueva clase]**.
      1. Especifique un **[!UICONTROL Nombre de Etiquetas]**, por ejemplo `ACA Test for Documentation`.
      1. Especifique **[!UICONTROL dominios]**, por ejemplo, `example.com`.

* Indique qué páginas deben incluirse o excluirse al recopilar datos para Content Analytics. Asegúrese de excluir las páginas de identificación personal.

  Especifique una **[!UICONTROL cadena de expresión regular]** para que **[!UICONTROL las páginas incluyan/excluyan]**. <br/>Por ejemplo: `^(?!.*documentation).*` para excluir todas las páginas de documentación de Content Analytics.

* Indique qué recursos deben incluirse o excluirse al recopilar datos para Content Analytics. Asegúrese de excluir los activos que le identifiquen personalmente.

  Especifique una **[!UICONTROL cadena de expresión regular]** para **[!UICONTROL Asset que se va a incluir/excluir]**. <br/>Por ejemplo: `^(?!.*(logo\.jpg)).*$` para excluir todas las imágenes de logotipo de JPEG de Content Analytics.


##### Anulaciones de encabezado {#web-header-overrides}

<!-- needs modification for mobile channel -->

Opcionalmente, puede especificar en la sección **[!UICONTROL Anulaciones de encabezado]** un nombre de encabezado y un valor de encabezado secreto.  Esta configuración de anulación de encabezados garantiza que Content Analytics envíe encabezados HTTP personalizados para evitar la detección de bots o las tecnologías de acceso al tráfico que haya implementado.

![Sección de invalidaciones de encabezado](/help/content-analytics/assets/aca-configuration-header-overrides.png)

1. Habilitar **[!UICONTROL Configurar invalidaciones de encabezado]**.
1. Escriba el **[!UICONTROL nombre del encabezado]**. Por ejemplo, `x-asset-service`.
1. Escriba el **[!UICONTROL valor del encabezado]**. Lo que especifique es secreto y no está visible en la interfaz de usuario (a menos que seleccione explícitamente revelar ![Visibilidad](/help/assets/icons/Visibility.svg) del valor durante la entrada).

#### Guardar {#web-save}

Una vez que haya especificado los detalles del canal web, seleccione **[!UICONTROL Guardar]** para guardar la configuración. Seleccione **[!UICONTROL Cancelar]** para cancelar la configuración.


### Resumen {#summary}

Cuando haya proporcionado todos los detalles necesarios, un resumen proporcionará los detalles sobre los artefactos que se crean o modifican.

* Aparecerá un mensaje **[!UICONTROL Ya está casi listo para implementar _nombre de configuración_ para el resumen de Content Analytics]** cuando implemente una nueva configuración.

* En el caso de las configuraciones implementadas existentes, aparecerá un mensaje **[!UICONTROL Ha implementado _nombre de configuración_ para el resumen de Content Analytics]**.

![Resumen de la configuración de Content Analytics](../assets/aca-configuration-summary.png)

### Acciones {#actions}

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_dialog"
>title="Confirmación de la implementación"
>abstract="Si selecciona **[!UICONTROL Implementar]**, configurará Content Analytics en función de la entrada proporcionada en este flujo de trabajo. Varias configuraciones se eligen de forma predeterminada en función de lo que generalmente resulta útil para el análisis de contenido, pero usted (como responsable del tratamiento de datos) debe revisar la configuración de cada artefacto para confirmar que la configuración se implemente de acuerdo con su política de privacidad, sus derechos y obligaciones contractuales y los requisitos de consentimiento según la legislación aplicable.<br/><br/>Tenga en cuenta que no se recopilarán datos hasta que la biblioteca de etiquetas asociada a esta configuración se publique manualmente.<br/><br/>Para poder derivar atributos de imágenes y texto, Adobe recuperará los atributos mediante:<ol><li>La dirección URL de la página capturada en el momento de la visita al sitio del usuario, según la configuración de recopilación de datos que tenga y</li><li>La dirección URL donde se aloja la imagen.</li></ol>No debe etiquetar imágenes que estén alojadas en sitios de terceros."

Al crear o editar una configuración, tiene estas opciones:

* **[!UICONTROL Descartar]**: todos los cambios realizados como parte de la configuración se descartarán.
* **[!UICONTROL Guardar para más tarde]**: los cambios realizados en una configuración se guardarán. Puede volver a consultar la configuración en una fase posterior para realizar más cambios o implementar la configuración. Solo se requiere un valor para [!UICONTROL Nombre] para guardar una configuración.
* **[!UICONTROL Implementar]**: La configuración o los cambios realizados en una configuración se han guardado e implementado. Todos los campos marcados como ![Obligatorio](/help/assets/icons/Required.svg) deben tener los valores adecuados. La implementación consiste en lo siguiente:

   * Configuración de **[!UICONTROL Customer Journey Analytics]**:
      * La vista de datos seleccionada se actualiza para incluir dimensiones y métricas de Content Analytics.
      * La Conexión asociada a la vista de datos seleccionada se modifica para incluir los conjuntos de datos de eventos y atributos de Content Analytics.
      * Se añade una plantilla de informes de Content Analytics a Workspace.


   * Configuración de **[!UICONTROL Adobe Experience Platform]**:
      * La creación de esquemas para modelar eventos de Content Analytics, atributos de recursos y atributos de experiencia (si están configurados).
      * La creación de conjuntos de datos para recopilar eventos de Content Analytics, atributos de recursos y atributos de experiencia (si están configurados).
      * La creación de un flujo de datos que utiliza el servicio de caracterización para generar y actualizar atributos de contenido a partir de eventos de Content Analytics.


   * Configuración de la **[!UICONTROL recopilación de datos]**:
      * La propiedad de Etiquetas nueva o existente está configurada para admitir la recopilación de datos de Content Analytics. Esta configuración implica la inclusión de la extensión de Content Analytics de Adobe para las etiquetas.
      * Se crea una secuencia de datos para los eventos de Content Analytics.
      * La extensión de Content Analytics de Adobe está configurada para garantizar que los eventos de Content Analytics se envíen a la secuencia de datos de Content Analytics.
      * Si Web SDK o Mobile SDK no están configurados para la propiedad Tags, se crea una nueva configuración de Web SDK o Mobile SDK para enviar únicamente eventos de Content Analytics.
      * Si Web SDK o Mobile SDK están configurados para la propiedad Tags, no se realizan cambios en la configuración existente de Web SDK o Mobile SDK.


* **[!UICONTROL Guardar]**: los cambios realizados en una configuración implementada se guardan y la implementación se actualiza.
* **[!UICONTROL Salir]** Realiza la salida de la configuración guiada. Todos los cambios realizados en una configuración implementada se descartan.


## Publicar {#publish}

Para empezar a recopilar datos para la configuración de Content Analytics, debes [publicar manualmente](manual.md) las propiedades de etiquetas creadas para los canales que habilitaste.


>[!MORELIKETHIS]
>
>[Configuración manual](manual.md)
>

