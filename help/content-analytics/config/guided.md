---
title: Configuración guiada por Content Analytics
description: Configuración de Content Analytics mediante una configuración guiada de incorporación
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: ceb6ac97686165c2883ad8057730bb09e4d7ad16
workflow-type: tm+mt
source-wordcount: '2428'
ht-degree: 25%

---

# Configuración guiada por Content Analytics

{{release-limited-testing}}

La configuración guiada le ayuda a configurar Content Analytics de forma rápida y sencilla. La configuración guiada utiliza un asistente para configurar los requisitos de Content Analytics automáticamente para su organización. En la pantalla **[!UICONTROL Configuración]**, puede crear una configuración nueva o editar una existente.

>[!IMPORTANT]
>
>Solo puede tener una configuración de Content Analytics por zona protegida en su organización.

Para acceder a la configuración de Content Analytics

* Seleccione **[!UICONTROL Administración de datos]** > **[!UICONTROL Configuración de Content Analytics]** en el menú principal de Customer Journey Analytics.

En la pantalla **[!UICONTROL Configuraciones de Content Analytics]**, verá una tabla de configuraciones de Content Analytics existentes.

![Configuraciones de Content Analytics](../assets/aca-configuration-table.png)
Para cada configuración, están disponibles los siguientes detalles:

| Columna | Descripción |
|---|---|
| **[!UICONTROL Nombre]** | Nombre de la configuración. |
| **[!UICONTROL Creado por]** | Cuenta técnica que creó la configuración. |
| **[!UICONTROL Creado el]** | La marca de tiempo cuando se creó la configuración. |
| **[!UICONTROL Modificado el]** | La marca de tiempo de la última modificación de la configuración. |
| **[!UICONTROL Zona protegida]** | La zona protegida dentro de la organización en la que se ha configurado e implementado Content Analytics (que está previsto). |
| **[!UICONTROL Estado]** | El estado de la configuración. El estado puede ser:<br/>![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Borrador]**: la configuración se guardó para más tarde y no se implementó.<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Error]**: la configuración ha fallado. Puede seleccionar **[!UICONTROL Editar]** para obtener información sobre el error. Adobe aborda de forma proactiva cualquier implementación fallida. Póngase en contacto con el Servicio de atención al cliente para obtener más información.<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Completo]**: la configuración se completó e implementó correctamente. |

Puede usar ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para personalizar la tabla. Seleccione qué columnas mostrar en el cuadro de diálogo **[!UICONTROL Personalizar tabla]** y seleccione **[!UICONTROL Aplicar]** para aplicar los cambios.

Desde la pantalla Content Analytics **[!UICONTROL Configuration]**, puede crear una nueva configuración o editar una configuración existente.

Para crear una nueva configuración:

* Seleccione **[!UICONTROL Crear configuración]**. Esta acción abre el [asistente de configuración guiada](#guided-configuration-wizard).

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
>title="Limpieza de la vista de datos seleccionada"
>abstract="Ha seleccionado una vista de datos que ya está aprovisionada para el análisis de contenido. Esa configuración del análisis de contenido existente se elimina y la vista de datos se aprovisiona con la nueva configuración."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_prev_cleanup_labels_dialog"
>title="Limpieza de la vista de datos anterior"
>abstract="Ha seleccionado una nueva vista de datos. Se elimina la configuración de análisis de contenido para la vista de datos seleccionada anteriormente."

<!-- markdownlint-enable MD034 -->

Su configuración requiere la selección de una [vista de datos](/help/data-views/data-views.md).

1. Seleccionar una vista de datos

   * Para seleccionar una nueva vista de datos para una configuración, usa ![Datos](/help/assets/icons/Data.svg) **[!UICONTROL Seleccionar vista de datos]**.

     ![Configuración de Content Analytics de una vista de datos](../assets/aca-configuration-dataview.png)

   * Para modificar una vista de datos para una configuración, seleccione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]**.

     ![Configuración de Content Analytics de una vista de datos](../assets/aca-configuration-dataview-edit.png)


   En ambos casos, verá un cuadro de diálogo **[!UICONTROL Vista de datos]**, donde puede seleccionar una Vista de datos para su configuración.

   ![Configuración de Content Analytics de una vista de datos: tabla de vistas de datos](../assets/aca-configuration-dataview-dialog.png)

   Para una configuración nueva, la lista solo muestra las vistas de datos asociadas con zonas protegidas que no tienen una configuración activa. Además, solo verá las vistas de datos asociadas con los entornos limitados a los que tiene acceso y las conexiones para las que tiene derechos de modificación.

   Si edita una configuración existente, la lista solo muestra las vistas de datos disponibles en la zona protegida ya asociada a la configuración existente.

   Puede realizar las siguientes acciones:

   * Para buscar una vista de datos específica, usa el campo ![Buscar](/help/assets/icons/Search.svg).
   * Para filtrar la lista de vistas de datos disponibles, seleccione ![Mostrar filtros](/help/assets/icons/Filter.svg). Puede filtrar la lista en [!UICONTROL Conexión], [!UICONTROL Propietario] y [!UICONTROL Espacio aislado].<br/>Use ![Ocultar](/help/assets/icons/Filter.svg) **[!UICONTROL Ocultar filtros]** para ocultar el panel de filtros.
   * Para definir qué columnas mostrar en la tabla, seleccione ![Configuración de columna](/help/assets/icons/ColumnSetting.svg). Seleccione qué columnas mostrar en el cuadro de diálogo **[!UICONTROL Personalizar tabla]** y seleccione **[!UICONTROL Aplicar]** para aplicar los cambios.

1. Seleccione ![SelectBox](/help/assets/icons/SelectBox.svg) la vista de datos que desee usar.
1. Seleccione **[!UICONTROL Guardar]** para confirmar la vista de datos seleccionada. Seleccione **[!UICONTROL Cancelar]** para cancelar.


En Customer Journey Analytics, una vista de datos está vinculada a una conexión de Customer Journey Analytics [Connection](/help/connections/overview.md). Y una conexión se basa en una zona protegida dentro de su organización. Una vez guardada la configuración, **[!UICONTROL espacio aislado]** se rellena automáticamente con el nombre del espacio aislado, según la vista de datos seleccionada.


### Captura y definición de experiencias {#onboarding-experiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="Captura y definición de experiencias"
>abstract="Puede seleccionar que se incluyan experiencias en los datos que recopila con el análisis de contenido. Cuando se selecciona, debe definir una o más combinaciones de una regex y parámetros de consulta para definir para qué URL desea incluir experiencias."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="Captura y definición de experiencias"
>abstract="Recopilar experiencias en el análisis de contenido"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_parameters_header"
>title="Captura y definición de experiencias"
>abstract="Especifique los parámetros que determinan cómo se procesa el contenido en el sitio web."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="Captura y definición de experiencias"
>abstract="Puede editar la configuración en la extensión de Adobe Content Analytics en la propiedad Etiqueta, asociada a la configuración actual."

<!-- markdownlint-enable MD034 -->

En esta sección, puede seleccionar incluir Experiencias en los datos que recopila con Content Analytics.  Una experiencia es todo el texto de una página web que se puede reproducir con la URL utilizada por el usuario inicial que visitó esa página web.

De manera predeterminada, **[!UICONTROL Incluir experiencias]** está desactivado. Al seleccionarlo, debe definir para qué direcciones URL desea incluir experiencias.

Considere la posibilidad de incluir experiencias únicamente cuando se aplique lo siguiente:

* Solo puede acceder al contenido del sitio mediante direcciones URL públicas. El acceso al sitio no requiere tokens personalizados, cookies u otros mecanismos no disponibles a través de la URL.
* Las páginas del sitio deben poder reproducirse utilizando la dirección URL de la página.

Para incluir experiencias en una configuración nueva o no implementada:

![Captura y definición de la experiencia de configuración de Content Analytics](../assets/aca-configuration-experience.png)

1. Habilitar **[!UICONTROL Incluir experiencias]**.
1. De forma opcional, especifique los parámetros para el modo en que se procesa el contenido en el sitio web. Los parámetros son cero o más combinaciones de una **[!UICONTROL expresión regular de dominio]** y **[!UICONTROL parámetros de consulta]**. Los parámetros de consulta indican qué parámetros afectan al contenido de la página. Esta entrada permite a Content Analytics ignorar cualquier parámetro que no afecte al contenido de la página al definir una experiencia única.
   1. Escriba una **[!UICONTROL expresión regular de dominio]**, por ejemplo `/^(?!.*\b(store|help|admin)\b)/`. Asegúrese de omitir las expresiones regulares usando `/`. La expresión regular de dominio indica a qué direcciones URL se aplican estos parámetros. Por ejemplo, puede tener varios sitios y, para cada sitio, distintos parámetros controlan el contenido. Si los parámetros de consulta se aplican a todas las páginas, puede usar `.*` para indicar todas las páginas.
   1. Especifique una lista separada por comas de **[!UICONTROL parámetros de consulta,]**; por ejemplo, `outdoors, patio, kitchen`.
1. Seleccione **[!UICONTROL Remove]** si desea quitar una combinación de parámetros de consulta y expresión regular de dominio.
1. Seleccione **[!UICONTROL Agregar regex]** si desea agregar otra combinación de una expresión regular y parámetros de consulta.

Para editar experiencias existentes o incluir nuevas en una configuración implementada:

![Captura y definición de la experiencia de configuración de Content Analytics](../assets/aca-configuration-experience-edit.png)

* Alterne **[!UICONTROL Incluir experiencias]** para habilitar o deshabilitar la disponibilidad de componentes, visualizaciones y paneles de experiencia en Analysis Workspace.
* Seleccione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** para editar la configuración de la recopilación de datos para las experiencias en Content Analytics. Se le redirigirá a la [extensión de Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) en la propiedad Tags asociada con la configuración actual.




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

<!-- markdownlint-enable MD034 -->

#### Nueva configuración {#new-configuration}

En una nueva configuración, debe definir si desea utilizar una propiedad de etiquetas existente o crear una nueva propiedad de etiquetas. Además, debe definir las páginas y los recursos que desea incluir o excluir mediante expresiones regulares.

* Para utilizar una propiedad de etiquetas existente:

  ![Etiqueta existente de recopilación de datos de Content Analytics](../assets/aca-configuration-datacollection-existingtag.png)

   1. Seleccione **[!UICONTROL Elegir]** existente.
   2. Seleccione una propiedad existente del menú desplegable **[!UICONTROL Propiedad de etiquetas]**. Puede empezar a escribir para buscar y limitar las opciones disponibles.

* Para crear una nueva propiedad Etiquetas:

  ![Nueva etiqueta de recopilación de datos de Content Analytics](../assets/aca-configuration-datacollection-newtag.png)

   1. Seleccione **[!UICONTROL Crear nuevo]**.
   1. Especifique un **[!UICONTROL nombre de etiqueta]**, por ejemplo `ACA Test for Documentation`.
   1. Especifique **[!UICONTROL dominios]**, por ejemplo, `example.com`.

* Si ha seleccionado incluir experiencias, indique qué páginas deben incluirse o excluirse al recopilar datos para Content Analytics.

   * Especifique una cadena de expresión regular para que **[!UICONTROL Pages incluya/excluya]**. Por ejemplo: `/^(?!.*documentation).*/` para excluir todas las páginas de documentación de Content Analytics. Asegúrese de omitir las expresiones regulares usando `/`.

* Indique qué recursos deben incluirse o excluirse al recopilar datos para Content Analytics.

   * Especifique una cadena de expresión regular para **[!UICONTROL Assets para incluir/excluir]**. Por ejemplo: `/^(?!.*(logo\.jpg|\.svg)).*$/` para excluir todas las imágenes de logotipo de JPEG y SVG de Content Analytics. Asegúrese de omitir las expresiones regulares usando `/`.


#### Configuración existente {#existing-configuration}

Para una configuración existente, no se puede editar la propiedad Etiquetas. Sin embargo, puede editar las páginas y los recursos que desea incluir o excluir.

* Para editar qué páginas se deben incluir o excluir al recopilar datos para Content Analytics, seleccione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** debajo de **[!UICONTROL Experiencia]**. Se le redirigirá a la [extensión de Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) asociada a la propiedad Tags para la configuración actual de Content Analytics. Puede editar la expresión regular para incluir o excluir páginas. Asegúrese de [publicar](#publish) sus cambios.

* Para editar qué recursos deben incluirse o excluirse al recopilar datos para Content Analytics, seleccione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** debajo de **[!UICONTROL Recurso]**. Se le redirigirá a la [extensión de Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) asociada a la propiedad Tags para la configuración actual de Content Analytics. Puede editar la expresión regular para incluir o excluir recursos. Asegúrese de [publicar](#publish) sus cambios.

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

Cuando ha creado o editado una configuración, están disponibles las siguientes acciones.

* **[!UICONTROL Descartar]**: se descartarán todos los cambios realizados al crear una configuración nueva o al editar una existente.
* **[!UICONTROL Guardar para más tarde]**: se guardan los cambios realizados en una configuración nueva o en una configuración existente que aún no se ha implementado. Puede volver a consultar la configuración en una fase posterior para realizar más cambios o implementar la configuración.
* **[!UICONTROL Implementar]**: La configuración o los cambios realizados en una configuración nueva o en una configuración existente que aún no se ha implementado se guardarán e implementarán. La implementación consiste en:

   * Configuración de **[!UICONTROL Customer Journey Analytics]**:
      * La vista de datos seleccionada se actualiza para incluir la dimensión y las métricas de Content Analytics.
      * La Conexión asociada a la vista de datos seleccionada se modifica para incluir eventos de Content Analytics y conjuntos de datos de atributos.
      * Se agrega una plantilla de informes de Content Analytics a Workspace.


   * Configuración de **[!UICONTROL Adobe Experience Platform]**:
      * La creación de esquemas para modelar eventos de Content Analytics, atributos de recursos y atributos de experiencia (si están configurados).
      * La creación de conjuntos de datos para recopilar eventos de Content Analytics, atributos de recursos y atributos de experiencia (si están configurados).
      * Creación de un flujo de datos que utilice el servicio de personalización para generar y actualizar atributos de contenido a partir de eventos de Content Analytics.


   * Configuración de **[!UICONTROL recopilación de datos]**:
      * La propiedad de etiquetas nueva o existente está configurada para admitir la recopilación de datos de Content Analytics. Esta configuración implica la inclusión de la extensión de Adobe Content Analytics para etiquetas.
      * Se crea una secuencia de datos para los eventos de Content Analytics.
      * La extensión de Adobe Content Analytics está configurada para garantizar que los eventos de Content Analytics se envíen al conjunto de datos para Content Analytics.
      * Si Web SDK no está configurado para la propiedad Tags, se crea una nueva configuración de Web SDK para enviar sólo eventos de Content Analytics.
      * Si Web SDK está configurado para esta propiedad Tags, no se realizan cambios en la configuración existente de Web SDK.


* **[!UICONTROL Guardar]**: los cambios realizados en una configuración implementada se guardan y la implementación se actualiza.
* **[!UICONTROL Salir]**. Sale de la configuración guiada. Todos los cambios realizados en una configuración implementada se descartan.


## Publicación {#publish}

Para empezar a recopilar datos para la configuración de Content Analytics, debes [publicar manualmente](manual.md) la propiedad Etiquetas que se creó después de seleccionar **[!UICONTROL Implementar]**.


>[!MORELIKETHIS]
>
>[Configuración manual](manual.md)
>
