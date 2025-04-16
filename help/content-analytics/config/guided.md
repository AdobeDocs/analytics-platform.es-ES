---
title: Configuración guiada Analytics contenido
description: Configurar el Analytics de contenido utilizando una configuración guiada de incorporación
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: 6e59b029542b7b4353f03b6dd083e25955aacc7b
workflow-type: tm+mt
source-wordcount: '2571'
ht-degree: 21%

---

# Configuración guiada por Content Analytics

{{release-limited-testing}}


La configuración guiada le ayuda a configurar Content Analytics de forma rápida y sencilla. La configuración guiada utiliza un asistente para configurar los requisitos de Content Analytics automáticamente para su organización. En la **[!UICONTROL pantalla Configuración]** , puede crear una configuración nueva o editar una configuración existente.

>[!IMPORTANT]
>
>Solo puede tener una configuración de Analytics de contenido por entorno de pruebas en su organización.

Para acceder a la configuración del Analytics de contenido

* Seleccione **[!UICONTROL Gestión]** de datos > **[!UICONTROL Configuración de Analytics de]** contenido en el menú principal de Customer Journey Analytics.

En la **[!UICONTROL pantalla Configuraciones de]** Analytics de contenido, verá una tabla con las configuraciones de Analytics de contenido existentes.

![Configuraciones de Analytics de](../assets/aca-configuration-table.png) contenido
Para cada configuración, están disponibles los siguientes detalles:

| Columna | Descripción |
|---|---|
| **[!UICONTROL Nombre]** | El nombre de la configuración. |
| **[!UICONTROL Creado por]** | El cuenta técnico que creó la configuración. |
| **[!UICONTROL Creado el]** | La marca de tiempo cuando se creó la configuración. |
| **[!UICONTROL Modificado el]** | La marca de tiempo de la última modificación de la configuración. |
| **[!UICONTROL Zona protegida]** | El entorno de pruebas dentro de la organización en el cual se configura e implementa el Analytics de contenido. |
| **[!UICONTROL Estado]** | El estado de la configuración. El estado puede ser:<br/>![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Borrador]**: la configuración se guarda para más tarde y no se implementa.<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Failed: The configuration has failed]**. Puede seleccionar **[!UICONTROL Editar]** para obtener información sobre el error. Adobe Systems aborda de manera proactiva cualquier implementación fallida. Puede ponerse en contacto con el Servicio de atención al cliente para obtener más información.<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Completo]**: la configuración se completó e implementó correctamente. |

Puede usar ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para personalizar la tabla. Seleccione qué columnas mostrar en el cuadro de diálogo **[!UICONTROL Personalizar tabla]** y seleccione **[!UICONTROL Aplicar]** para aplicar los cambios.

Desde la pantalla Configuración de Analytics **[!UICONTROL de]** contenido, puede crear una nueva configuración o editar una configuración existente.

Para crear una nueva configuración:

* Seleccione **[!UICONTROL Crear configuración]**. Esta acción abre el [asistente](#guided-configuration-wizard) de configuración guiada.

Para editar una configuración existente:

* Seleccione ![Más](/help/assets/icons/More.svg) y luego ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** para una configuración de Content Analytics existente. Esta acción abre el [asistente de configuración guiada](#guided-configuration-wizard).

## Asistente de configuración guiada

El asistente de configuración guiada consta de cuatro secciones ([Detalles](#details), [Vista de datos](#data-view), [Captura y definición de experiencias](#experience-capture-and-definition) y [Recopilación de datos](#data-collection)), cada una de las cuales le solicita los detalles necesarios para configurar Content Analytics correctamente. Complete cada sección antes de pasar a la siguiente, ya que algunos ajustes de una sección pueden depender de los valores de configuración de secciones anteriores.

### Detalles {#onboarding-details}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="Detalles"
>abstract="Introduzca un nombre para la conexión. En las secciones **[!UICONTROL Vista de datos]**, **[!UICONTROL Captura y definición de experiencias]** y **[!UICONTROL Recopilación de datos]**, proporcione más detalles para garantizar que el análisis de contenido se pueda configurar correctamente."

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="Detalles"
>abstract="Esta guía establece los requisitos necesarios para configurar el análisis de contenido. Proporcione un nombre para esta configuración"

<!-- markdownlint-enable MD034 -->

Cada configuración requiere un nombre único. Por ejemplo, `Example Content Analytics configuration`. El nombre es necesario para guardar o implementar una configuración.

![Detalles de configuración de Content Analytics](../assets/aca-configuration-details.png)


### Vista de datos {#onboarding-data-view}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="Vista de datos"
>abstract="Para la configuración del análisis de contenido, debe seleccionar una vista de datos existente. Por lo tanto, puede combinar los datos de análisis de contenido con otros datos."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="Vista de datos"
>abstract="Seleccione una vista de datos existente de Customer Journey Analytics con la que desee combinar sus datos de análisis de contenido."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="Vista de datos"
>abstract="Seleccione una vista de datos existente de Customer Journey Analytics con la que desee combinar sus datos de análisis de contenido.<br/> "

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_change_dialog"
>title="Nueva vista de datos"
>abstract="Al seleccionar una nueva vista de datos se obtiene una actualización de dicha vista de datos para incluir las métricas y dimensiones de análisis de contenido. Si es necesario, la conexión asociada también se actualiza para incluir conjuntos de datos de Content Analytics. La conexión y la vista de datos configuradas actualmente para Análisis de contenido no se modifican."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_current_cleanup_labels_dialog"
>title="Limpiar vista de datos seleccionada"
>abstract="Ha seleccionado una vista de datos que ya está aprovisionada para Content Analytics. Esa configuración de Analytics de contenido existente se elimina y el vista de datos se aprovisiona con la nueva configuración."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_prev_cleanup_labels_dialog"
>title="Limpiar datos anteriores vista"
>abstract="Ha seleccionado una nueva vista de datos. Se quita la configuración del Analytics de contenido para el vista de datos seleccionado anteriormente."

<!-- markdownlint-enable MD034 -->

Su configuración requiere la selección de un [vista](/help/data-views/data-views.md) de datos.

1. Seleccione una vista de datos

   * Para seleccionar una nueva vista de datos para una configuración, usa ![Datos](/help/assets/icons/Data.svg) **[!UICONTROL Seleccionar vista de datos]**.

     ![Contenido Analytics configuración de un vista de datos](../assets/aca-configuration-dataview.png)

   * Para modificar un vista de datos para una configuración, seleccione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]**.

     ![Contenido Analytics configuración de un vista de datos](../assets/aca-configuration-dataview-edit.png)


   En ambos escenarios, verá un **[!UICONTROL cuadro de diálogo vista]** datos, donde puede seleccionar un vista de datos para su configuración.

   ![Contenido Analytics configuración de un vista de datos: tabla de vistas de datos](../assets/aca-configuration-dataview-dialog.png)

   Para una configuración nueva, el lista solo muestra vistas de datos asociadas con entornos aislados que no tienen una configuración activa. Además, solo verá vistas de datos asociadas con entornos limitados a los que tiene acceso y conexiones que tiene derechos para modificar.

   Si edita una configuración existente, la lista solo muestra las vistas de datos disponibles dentro del espacio aislado ya asociado con la configuración existente.

   Puede realizar las siguientes acciones:

   * Para búsqueda un vista de datos específico, utilice el campo Search![](/help/assets/icons/Search.svg).
   * Para filtrar el lista de vistas de datos disponibles, seleccione ![Mostrar filtros](/help/assets/icons/Filter.svg). Puede filtrar las lista en [!UICONTROL Conexión], [!UICONTROL Propietario] y [!UICONTROL Sandbox].<br/>Use ![la filtros ]**Ocultar ocultar para ocultar el panel de](/help/assets/icons/Filter.svg)**[!UICONTROL  filtro.
   * Para definir qué columnas se mostrarán en la tabla, seleccione ![Columna Configuración](/help/assets/icons/ColumnSetting.svg). Seleccione qué columnas desea mostrar en el **[!UICONTROL cuadro de diálogo Personalizar tabla]** y seleccione **[!UICONTROL Aplicar]** para aplicar los cambios.

1. Seleccione ![SelectBox](/help/assets/icons/SelectBox.svg) la vista de datos que desee utilizar.
1. Seleccione **[!UICONTROL Guardar]** para confirmar la vista de datos seleccionada. Seleccione **[!UICONTROL Cancelar]** para cancelar.


En Customer Journey Analytics, una [vista de datos](/help/data-views/data-views.md) está vinculada a una [conexión](/help/connections/overview.md) de Customer Journey Analytics. Y una conexión se basa en una zona protegida dentro de su organización. Una vez guardada la configuración, **[!UICONTROL Sandbox]** se rellena automáticamente con el nombre del sandbox, en función de los vista de datos seleccionados.


### Captura y definición de experiencias {#onboarding-experiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="Captura y definición de experiencias"
>abstract="Puede seleccionar incluir experiencias en los datos recopilados con Content Analytics. Cuando se selecciona, debe definir una o más combinaciones de una regex y parámetros de consulta para definir para qué URL desea incluir experiencias."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="Captura y definición de experiencias"
>abstract="Recopilar experiencias en el análisis de contenido"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_parameters_header"
>title="Captura y definición de experiencias"
>abstract="Especifique los parámetros que determinan cómo se procesa el contenido en el sitio web."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_new_include_experiences"
>title="Captura y definición de experiencias"
>abstract="Cuando está habilitado, se recopilan experiencia datos, se generan experiencia atributos y experiencia sistema de informes está disponible."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_include_experiences"
>title="Captura y definición de experiencias"
>abstract="Cuando se habilita, se recopilan los datos de la experiencia, se generan los atributos de la experiencia y está disponible la creación de informes de experiencia. <br><br/>Utilice ![Editar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Editar]** para modificar la configuración recopilación de datos de experiencias en el Propiedad Tags asociado a la configuración actual."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="Captura y definición de experiencias"
>abstract="Debe editar la configuración de la recopilación de datos de experiencia en la extensión de Adobe Content Analytics en la propiedad Etiquetas asociada a la configuración actual."

<!-- markdownlint-enable MD034 -->

En esta sección, puede seleccionar incluir experiencias en los datos que recopila con Content Analytics.  Una experiencia es todo el texto de una página web que se puede reproducir con la URL utilizada por el usuario inicial que visitó esa página web.

De manera predeterminada, **[!UICONTROL Incluir experiencias]** está desactivado. Al seleccionar esta opción, tendrá que definir las direcciones URL en las que desea incluir experiencias.

Solo considere incluir experiencias cuando lo siguiente sea aplicable:

* Las páginas del sitio deben ser reproducibles utilizando el Página URL.
* El texto contenido visto por cualquier usuario puede reproducirse utilizando el URL Página y no depende de cookies u otros mecanismos personalización.

Para incluir experiencias en una configuración nueva o no implementada:

![Captura y definición de la experiencia de configuración de Content Analytics](../assets/aca-configuration-experience.png)

1. Habilitar **[!UICONTROL Incluir experiencias]**. El cambio para habilitar experiencias afecta a lo siguiente:

   * colección de datos en la extensión de Analytics de contenido
   * Proceso que genera atributos de experiencia a partir de la datos de evento de Analytics de contenido
   * El sistema de informes plantilla en Customer Journey Analytics.

1. Especifique los parámetros para la representación del contenido en el sitio web. Los parámetros son cero o más combinaciones de una **[!UICONTROL expresión regular de dominio]** y **[!UICONTROL parámetros de consulta]**. Los parámetros de consulta indican qué parámetros afectan al contenido de la página. Esta entrada permite a Content Analytics ignorar cualquier parámetro que no afecte al contenido de la página al definir una experiencia única.
   1. Escriba una **[!UICONTROL expresión regular de dominio]**, por ejemplo `/^(?!.*\b(store|help|admin)\b)/`. Asegúrese de omitir las expresiones regulares usando `/`. La expresión regular de dominio indica a qué direcciones URL se aplican estos parámetros. Por ejemplo, puede tener varios sitios y, para cada sitio, distintos parámetros controlan el contenido. Si los parámetros de consulta se aplican a todas las páginas, puede usar `.*` para indicar todas las páginas.
   1. Especifique una lista separada por comas de **[!UICONTROL parámetros de consulta,]**; por ejemplo, `outdoors, patio, kitchen`.
1. Seleccione **[!UICONTROL Remove]** si desea quitar una combinación de parámetros de consulta y expresión regular de dominio.
1. Seleccione **[!UICONTROL Agregar regex]** si desea agregar otra combinación de una expresión regular y parámetros de consulta.

Para editar experiencias existentes o incluir nuevas en una configuración implementada:

![Captura y definición de la experiencia de configuración de Content Analytics](../assets/aca-configuration-experience-edit.png)

* Alternar **[!UICONTROL Incluir experiencias]**  para habilitar o deshabilitar:

   * Proceso que genera atributos de experiencia a partir de la datos de evento de Analytics de contenido
   * El sistema de informes plantilla en Customer Journey Analytics.

* Seleccione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** para seguir editando la configuración de recopilación de datos para experiencias en Content Analytics. Se le redirigirá a la [extensión de Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) en la propiedad Tags asociada con la configuración actual.


### Recopilación de datos {#onboarding-data-collection}

En esta sección, puede configurar cómo recopilar los datos de análisis de contenido.

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="Recopilación de datos"
>abstract="Defina qué propiedad Etiquetas desea utilizar o cree una nueva. Y defina las páginas y los recursos que desea incluir o excluir utilizando expresiones regulares."

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
>abstract="Indique qué páginas deben **incluirse** o **excluirse** al recopilar datos para el análisis de contenido"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_boldheader"
>title="Recopilación de datos"
>abstract="**Recursos para incluir/excluir**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_header"
>title="Recopilación de datos"
>abstract="Indique qué recursos deben **incluirse** o **excluirse** al recopilar datos para el análisis de contenido"

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

<!-- markdownlint-enable MD034 -->

#### Nuevo configuración {#new-configuration}

En una nueva configuración, debe definir si desea usar un Propiedad de etiquetas existente o crear un nuevo Propiedad de etiquetas. Además, debe definir las páginas y los activos desea incluir o excluir mediante expresiones regulares.

* Para utilizar un Propiedad de etiquetas existente:

  ![Recopilación de contenido Analytics datos Etiqueta existente](../assets/aca-configuration-datacollection-existingtag.png)

   1. Seleccione Elegir **[!UICONTROL existente]**.
   2. Seleccione una Propiedad existente en el **[!UICONTROL menú desplegable Etiquetas Propiedad]** . Puede inicio escribir para búsqueda y limitar las opciones disponibles. No puede seleccionar un Propiedad de etiquetas que ya esté utilizando otra configuración de Analytics de contenido implementada.


* Para crear un nuevo Propiedad de etiquetas:

  ![Etiqueta de recopilación Nuevo de contenido Analytics datos](../assets/aca-configuration-datacollection-newtag.png)

   1. Seleccione **[!UICONTROL Crear nuevo]**.
   1. Especifique un **[!UICONTROL nombre de etiqueta]**, por ejemplo `ACA Test for Documentation`.
   1. Especifique **[!UICONTROL dominios]**, por ejemplo, `example.com`.

* Indique qué páginas deben incluirse o excluirse al recopilar datos para Content Analytics.

  Especifique una cadena de expresión regular para que **[!UICONTROL Pages incluya/excluya]**. <br/>Por ejemplo: `^(?!.*documentation).*` para excluir todas las páginas de documentación de Content Analytics.

* Indique qué activos deben incluirse o excluirse al recopilar datos para Content Analytics.

  Especifique una cadena de expresión regular para **[!UICONTROL que Assets incluya o excluya]**. <br/>Por ejemplo, `^(?!.*(logo\.jpg|\.svg)).*$` para excluir todas las imágenes de logotipos JPEG y SVG de Content Analytics.

>[!IMPORTANT]
>
>En caso de que tenga un implementación de SDK web existente que use el [biblioteca](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) JavaScript y no use la [extensión](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) Tags, debe quitar manualmente la extensión de SDK web incluida automáticamente del Propiedad Tags recién creado.



#### Configuración existente {#existing-configuration}

Para una configuración existente, no se puede editar la propiedad Etiquetas. Sin embargo, puede editar las páginas y los recursos que desea incluir o excluir.

* Para editar qué páginas se deben incluir o excluir al recopilar datos para Content Analytics, seleccione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** debajo de **[!UICONTROL Experiencia]**. Se le redirige a la [extensión](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) Analytics de contenido de Adobe Systems asociada al Propiedad de etiquetas para la configuración actual del Analytics de contenido. Puede editar los expresión regular para incluir o excluir páginas. [Asegúrese de publicar](#publish) los cambios.

* Para editar qué activos deben incluirse o excluirse al recopilar datos para Content Analytics, seleccione Editar ![](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** debajo **[!UICONTROL de Asset]**. Se le redirige a la [extensión](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) Analytics de contenido de Adobe Systems asociada al Propiedad de etiquetas para la configuración actual del Analytics de contenido. Puede editar los expresión regular para incluir o excluir activos. Asegúrese de [publicar](#publish) sus cambios.

### Resumen {#summary}

Una vez que haya proporcionado todos los detalles necesarios, un resumen proporciona detalles sobre los artefactos que se crean o modifican.

* Verá un **[!UICONTROL Está casi listo para implementar _nombre de configuración_ para el resumen de Content Analytics]** al implementar una nueva configuración.

* Para las configuraciones implementadas existentes, verá **[!UICONTROL Ha implementado _nombre de configuración_ para el resumen de Content Analytics]**.

![Resumen de configuración de Content Analytics](../assets/aca-configuration-summary.png)

### Acciones {#actions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_dialog"
>title="Confirmación de la implementación"
>abstract="Si selecciona **[!UICONTROL Implementar]**, se configura el Análisis de contenido en función de la entrada proporcionada en este flujo de trabajo. Varias configuraciones se eligen de forma predeterminada en función de lo que generalmente resulta útil para el análisis de contenido, pero usted (como responsable del tratamiento de datos) debe revisar la configuración de cada artefacto para confirmar que la configuración se implemente de acuerdo con su política de privacidad, sus derechos y obligaciones contractuales y los requisitos de consentimiento según la legislación aplicable.<br/><br/>Tenga en cuenta que no se recopilarán datos hasta que la biblioteca de etiquetas asociada con esta configuración se publique manualmente.<br/><br/>Para poder derivar atributos de imágenes y texto, Adobe recuperará los atributos mediante:<ol><li>La dirección URL capturada en el momento de la visita al sitio del usuario, según la configuración de recopilación de datos que tenga y la</li><li>Dirección URL donde se aloja la imagen.</li></ol>No debe etiquetar imágenes alojadas en sitios de terceros."

<!-- markdownlint-enable MD034 -->

Cuando cree o edite una configuración, dispone de las siguientes opciones:

* **[!UICONTROL Descartar]**: todos los cambios realizados como parte de la configuración se descartarán.
* **[!UICONTROL Guardar para más tarde]**: los cambios realizados en una configuración se guardarán. Puede volver a consultar la configuración en una fase posterior para realizar más cambios o implementar la configuración. Para guardar una configuración solo se necesita un valor de [!UICONTROL Nombre] .
* **[!UICONTROL Implementar]**: se guardan e implementan Configuración o los cambios realizados en una configuración. Todos los campos marcados como ![obligatorios](/help/assets/icons/Required.svg) deben tener valores adecuados. El implementación consta de:

   * **** Customer Journey Analytics configuración:
      * La vista de datos seleccionada se actualiza para incluir el contenido Analytics dimensión y las métricas.
      * La conexión vinculada a la vista de datos seleccionada se modifica para incluir eventos de contenido Analytics y conjuntos de datos de atributos.
      * Se agrega una plantilla de sistema de informes de contenido Analytics a Espacio de trabajo.


   * **** Adobe Experience Platform configuración:
      * La creación de esquemas para modelar eventos de Content Analytics, atributos de recursos y atributos de experiencia (si están configurados).
      * La creación de conjuntos de datos para recopilar eventos de Content Analytics, atributos de recursos y atributos de experiencia (si están configurados).
      * Creación de un flujo de datos que utilice el servicio de personalización para generar y actualizar atributos de contenido a partir de eventos de Content Analytics.


   * Configuración de **[!UICONTROL recopilación de datos]**:
      * La propiedad de etiquetas nueva o existente está configurada para admitir la recopilación de datos de Content Analytics. Esta configuración implica la inclusión de la extensión Analytics de contenido de Adobe Systems para etiquetas.
      * Se crea un flujo de datos para los eventos de Analytics de contenido.
      * La extensión de Adobe Content Analytics está configurada para garantizar que los eventos de Content Analytics se envíen al conjunto de datos para Content Analytics.
      * Si Web SDK no está configurado para la propiedad Tags, se crea una nueva configuración de Web SDK para enviar sólo eventos de Content Analytics.
      * Si Web SDK está configurado para esta propiedad Tags, no se realizan cambios en la configuración existente de Web SDK.


* **[!UICONTROL Guardar]**: Los cambios realizados en una configuración implementada se guardan y el implementación se actualiza.
* **[!UICONTROL Salir]**. Sale de la configuración guiada. Se descartan todos los cambios realizados en una configuración implementada.


## Publicación {#publish}

Para inicio recopilar datos para la configuración del Analytics de contenido, debe [publicar manualmente](manual.md) el Propiedad de etiquetas que se crea después de seleccionar **[!UICONTROL Implementar]**.


>[!MORELIKETHIS]
>
>[Configuración manual](manual.md)
>
