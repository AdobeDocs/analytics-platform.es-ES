---
title: Configuración guiada por Content Analytics
description: Configuración de Content Analytics mediante una configuración guiada de incorporación
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: cea253d3b1da080e6735989d59cc6eda44afc203
workflow-type: tm+mt
source-wordcount: '1911'
ht-degree: 10%

---

# Configuración guiada por Content Analytics

>[!WARNING]
>
>Este artículo es una versión preliminar no oficial del borrador de una próxima versión final y forma parte de la documentación de Análisis de contenido. Todo el contenido está sujeto a cambios y no se puede derivar ninguna obligación legal de la versión actual de este artículo.
>

{{release-limited-testing}}

La configuración guiada le ayuda a configurar el análisis de contenido de forma rápida y sencilla. La configuración guiada utiliza un asistente para establecer los requisitos para configurar el análisis de contenido automáticamente para su organización. En la pantalla **[!UICONTROL Configuración]**, puede crear una configuración nueva o editar una existente.

>[!IMPORTANT]
>
>Solo puede tener una configuración de análisis de contenido por zona protegida en su organización.


Para acceder a la configuración de Análisis de contenido

* Seleccione **[!UICONTROL Administración de datos]** > **[!UICONTROL Análisis de contenido]** en el menú principal de Customer Journey Analytics.

En la pantalla Configuración de análisis de contenido, verá una tabla de configuraciones de análisis de contenido existentes.

![Configuraciones de análisis de contenido](../assets/aca-configuration-table.png)
Para cada configuración, están disponibles los siguientes detalles:

| Columna | Descripción |
|---|---|
| **[!UICONTROL Nombre]** | Nombre de la configuración. |
| **[!UICONTROL Creado por]** | Cuenta técnica que creó la configuración. |
| **[!UICONTROL Creado el]** | La marca de tiempo cuando se creó la configuración. |
| **[!UICONTROL Modificado el]** | La marca de tiempo de la última modificación de la configuración. |
| **[!UICONTROL Zona protegida]** | La zona protegida dentro de la organización en la que se ha configurado e implementado (y está previsto) el análisis de contenido. |
| **[!UICONTROL Estado]** | El estado de la configuración. El estado puede ser:<br/>![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Borrador]**: la configuración se guardó para más tarde y no se implementó.<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Error]**: la configuración ha fallado. Debe editar la configuración y realizar los cambios necesarios.<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Completo]**: la configuración se completó e implementó correctamente. |

Puede usar ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para personalizar la tabla. Seleccione qué columnas mostrar en el cuadro de diálogo **[!UICONTROL Personalizar tabla]** y seleccione **[!UICONTROL Aplicar]** para aplicar los cambios.

Desde la pantalla **[!UICONTROL Configuración]** de Content Analytics, puede crear una nueva configuración o editar una configuración existente.

Para crear una nueva configuración:

* Seleccione **[!UICONTROL Crear configuración]**. Esta acción abre el asistente de configuración guiada.

Para editar una configuración existente:

* Seleccione ![Más](/help/assets/icons/More.svg) y, a continuación, ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** para una configuración de análisis de contenido existente. Esta acción abre el asistente de configuración guiada.

## Asistente de configuración guiada

El asistente de configuración guiada consta de cuatro secciones ([Detalles](#details), [Vista de datos](#data-view), [Captura y definición de experiencias](#experience-capture-and-definition) y [Recopilación de datos](#data-collection)), cada una de las cuales le solicita los detalles necesarios para configurar correctamente el Análisis de contenido. Complete cada sección antes de pasar a la siguiente, ya que algunos ajustes de una sección pueden depender de los valores de configuración de secciones anteriores.

### Detalles {#onboarding-details}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="Detalles"
>abstract="Introduzca un nombre para la conexión. En las secciones **[!UICONTROL Vista de datos]**, **[!UICONTROL Captura y definición de experiencias]** y **[!UICONTROL Recopilación de datos]**, proporciona más detalles para garantizar que Análisis de contenido se pueda configurar correctamente."

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="Detalles"
>abstract="Esta guía establece los requisitos necesarios para configurar el análisis de contenido. Proporcione un nombre para esta configuración"

<!-- markdownlint-enable MD034 -->

Cada configuración requiere un nombre único. Por ejemplo, `Example Content Analytics configuration`.

![Detalles de configuración de análisis de contenido](../assets/aca-configuration-details.png)


### Vista de datos {#onboarding-data-view}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="Vista de datos"
>abstract="Para la configuración de Content Analytics, debe seleccionar una vista de datos existente. Por lo tanto, puede combinar los datos de análisis de contenido con otros datos."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="Vista de datos"
>abstract="Seleccione una vista de datos existente de Customer Journey Analytics con la que desee combinar los datos de análisis de contenido."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="Vista de datos"
>abstract="Seleccione una vista de datos existente de Customer Journey Analytics con la que desee combinar los datos de análisis de contenido.<br/>"

<!-- markdownlint-enable MD034 -->

Su configuración requiere la selección de una [vista de datos](/help/data-views/data-views.md).

![Configuración de análisis de contenido de una vista de datos](../assets/aca-configuration-dataview.png)

Para seleccionar una vista de datos:

1. Usar ![datos](/help/assets/icons/Data.svg) **[!UICONTROL Seleccionar vista de datos]**. Verá un cuadro de diálogo **[!UICONTROL Vista de datos]**, donde podrá seleccionar una Vista de datos para su configuración.

   Si crea una configuración nueva, la lista solo muestra las vistas de datos asociadas con zonas protegidas que no tienen una configuración activa.
Si edita una configuración existente, la lista solo muestra las vistas de datos disponibles en la zona protegida ya asociada a la configuración existente.

   * Para filtrar la lista de vistas de datos disponibles, seleccione ![Mostrar filtros](/help/assets/icons/Filter.svg). Puede filtrar la lista por Conexión, Propietario y Zona protegida.<br/>Use ![Ocultar](/help/assets/icons/Filter.svg) **[!UICONTROL Ocultar filtros]** para ocultar el panel de filtros.
   * Para definir qué columnas mostrar en la tabla, seleccione ![Configuración de columna](/help/assets/icons/ColumnSetting.svg). Seleccione qué columnas mostrar en el cuadro de diálogo **[!UICONTROL Personalizar tabla]** y seleccione **[!UICONTROL Aplicar]** para aplicar los cambios.
1. Seleccione **[!UICONTROL Guardar]** para confirmar la vista de datos seleccionada. Seleccione **[!UICONTROL Cancelar]** para cancelar.

Una vista de datos está vinculada a una conexión [Connection](/help/connections/overview.md) de Customer Journey Analytics. Y una conexión se basa en una zona protegida dentro de su organización. Una vez guardada la configuración, **[!UICONTROL espacio aislado]** se rellena automáticamente con el nombre correcto del espacio aislado, según la vista de datos seleccionada.


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
>id="aca_onboarding_experiences_url_header"
>title="Captura y definición de experiencias"
>abstract="Especifique las direcciones URL a las que se aplican los parámetros siguientes"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_edit_button"
>title="Captura y definición de experiencias"
>abstract="Puede editar la configuración en la extensión de Adobe Content Analytics en la propiedad Etiqueta, asociada a la configuración seleccionada."

<!-- markdownlint-enable MD034 -->

En esta sección, puede seleccionar incluir Experiencias en los datos que recopila con Análisis de contenido.  Una experiencia es todo el texto de una página web que se puede reproducir con la URL utilizada por el usuario inicial que visitó esa página web.

De manera predeterminada, **[!UICONTROL Incluir experiencias]** está desactivado. Al seleccionarlo, debe definir para qué direcciones URL desea incluir experiencias.

Considere la posibilidad de incluir experiencias únicamente cuando se aplique lo siguiente:

* El contenido del sitio se administra únicamente mediante una dirección URL.
* Las páginas del sitio deben poder reproducirse utilizando la dirección URL de la página.

Para incluir experiencias en una configuración nueva o no implementada:

![Captura y definición de la experiencia de configuración de Content Analytics](../assets/aca-configuration-experience.png)

1. Habilitar **[!UICONTROL Incluir experiencias]**.
1. Especifique los parámetros que determinan cómo se procesa el contenido en el sitio web. Los parámetros son cero o más combinaciones de una **[!UICONTROL expresión regular de dominio]** y **[!UICONTROL parámetros de consulta]**.
   1. Escriba una **[!UICONTROL expresión regular de dominio]**, por ejemplo `(?!.*\b(store|help|admin)\b)`.
   1. Especifique una lista separada por comas de **[!UICONTROL parámetros de consulta,]**; por ejemplo, `outdoors, patio, kitchen`.
1. Seleccione **[!UICONTROL Remove]** si desea quitar una combinación de parámetros de consulta y expresión regular de dominio.
1. Seleccione **[!UICONTROL Agregar otro]** si desea agregar otra combinación de una expresión regular y parámetros de consulta.

Para editar experiencias existentes o incluir nuevas en una configuración implementada:

![Captura y definición de la experiencia de configuración de Content Analytics](../assets/aca-configuration-experience-edit.png)

* Seleccione ![Editar](/help/assets/icons/Edit.svg) Editar para editar los parámetros de la extensión de Adobe Content Analytics en la propiedad Etiqueta, asociada a la configuración seleccionada.


### Recopilación de datos {#onboarding-data-collection}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="Recopilación de datos"
>abstract="Defina qué propiedad de etiqueta desea utilizar o cree una nueva. Y defina las páginas y los recursos que desea incluir o excluir mediante expresiones regulares."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tag_header"
>title="Recopilación de datos"
>abstract="Proporcionar una propiedad de etiqueta"

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

#### Nueva configuración

En una nueva configuración, debe definir qué propiedad de etiqueta desea utilizar o crear una nueva propiedad de etiqueta. Además, debe definir las páginas y los recursos que desea incluir o excluir mediante expresiones regulares.

* Para utilizar una propiedad Tag existente:

  ![Etiqueta existente de recopilación de datos de análisis de contenido](../assets/aca-configuration-datacollection-existingtag.png)

   * Seleccione **[!UICONTROL Existente]**.
   * Seleccione una propiedad existente del menú desplegable **[!UICONTROL Propiedad de etiqueta]**.

* Para crear una nueva propiedad Tag:

  ![Nueva etiqueta de recopilación de datos de análisis de contenido](../assets/aca-configuration-datacollection-newtag.png)

   1. Seleccione **[!UICONTROL Crear nuevo]**.
   2. Especifique un **[!UICONTROL nombre de etiqueta]**, por ejemplo `ACA Test`.
   3. Especifique **[!UICONTROL dominios]**, por ejemplo, `example.com`.

* Si ha seleccionado incluir experiencias, indique qué páginas deben incluirse o excluirse al recopilar datos para el análisis de contenido.

   * Especifique una expresión regular para **[!UICONTROL Experience]**. Por ejemplo: `(?!.*\b(store|help|admin)\b)`.

* Indique qué recursos deben incluirse o excluirse al recopilar datos para el análisis de contenido.

   * Especifique una expresión regular para **[!UICONTROL Asset]**. Por ejemplo: `(?!.*\b(store|help|admin)\b)`.


#### Configuración existente

Para una configuración existente, no se puede editar la propiedad Etiqueta. Sin embargo, puede editar las páginas y los recursos que desea incluir o excluir.

* Para editar qué páginas se deben incluir o excluir al recopilar datos para el análisis de contenido, seleccione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** debajo de **[!UICONTROL Experiencia]**.

* Para editar qué recursos deben incluirse o excluirse al recopilar datos para el análisis de contenido, seleccione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** debajo de **[!UICONTROL Recurso]**.

### Resumen {#summary}

Una vez que haya proporcionado todos los detalles necesarios, un resumen proporciona detalles sobre los artefactos que se crean o modifican.

* Verá un **[!UICONTROL Está casi listo para implementar _nombre de configuración_ para el resumen de Análisis de contenido]** al implementar una nueva configuración.

* Para las configuraciones implementadas existentes, verá **[!UICONTROL Ha implementado _nombre de configuración_ para el resumen de Análisis de contenido]**.

![Resumen de configuración de análisis de contenido](../assets/aca-configuration-summary.png)

### Acciones {#actions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning"
>title="Advertencia de implementación de incorporación"
>abstract="Esto configurará el análisis de contenido en función parcialmente de la entrada proporcionada en este flujo de trabajo. Otras configuraciones se eligen automáticamente en función de lo que suele resultar útil para el análisis de contenido. Se le recomienda revisar la configuración de cada artefacto para confirmar que cumpla con sus requisitos y directrices. <br/><br/>Tenga en cuenta que no se recopilarán datos hasta que la biblioteca de etiquetas asociada con esta configuración se publique manualmente.<br/><br/>Tenga en cuenta también que, para derivar atributos de imágenes y texto, Adobe recuperará estos atributos mediante la dirección URL capturada en el momento de la visita de los usuarios según la configuración de recopilación de datos implementada."

<!-- markdownlint-enable MD034 -->


Cuando ha creado o editado una configuración, están disponibles las siguientes acciones.

* **[!UICONTROL Descartar]**: se descartarán todos los cambios realizados al crear una configuración nueva o al editar una existente.
* **[!UICONTROL Guardar para más tarde]**: se guardan los cambios realizados en una configuración nueva o en una configuración existente que aún no se ha implementado. Puede volver a consultar la configuración en una fase posterior para realizar más cambios o implementar la configuración.
* **[!UICONTROL Implementar]**: Los cambios realizados en una configuración nueva o en una configuración existente que aún no se ha implementado se guardan e implementan. La implementación consiste en:
   * Configuración de **[!UICONTROL Adobe Experience Platform]**:
      1. La creación de esquemas para modelar eventos de Content Analytics, atributos de recursos y atributos de experiencia (si están configurados).
      1. La creación de conjuntos de datos para recopilar eventos de Content Analytics, atributos de recursos y atributos de experiencia (si están configurados).
      1. Creación de un flujo de datos que utiliza el servicio de personalización para generar y actualizar atributos de contenido a partir de eventos de Content Analytics.
   * Configuración de **[!UICONTROL análisis de contenido]**:
      * Configuración de un proceso de ensamblador de funciones basado en la configuración.
   * Configuración de **[!UICONTROL Customer Journey Analytics]**:
      1. La vista de datos seleccionada se actualiza para incluir la dimensión y las métricas de Análisis de contenido.
      1. La Conexión asociada a la vista de datos seleccionada se modifica para incluir los conjuntos de datos de atributos y eventos de Content Analytics.
      1. Las plantillas de informes de Análisis de contenido se añaden a Workspace.
   * Configuración de **[!UICONTROL recopilación de datos]**:
      1. La propiedad de etiquetas nueva o existente está configurada para admitir la recopilación de datos de Content Analytics. Esta configuración implica la inclusión de la extensión de Adobe Content Analytics para etiquetas.
      1. Se crea una secuencia de datos para los eventos de análisis de contenido.
      1. La extensión de Adobe Content Analytics está configurada para garantizar que los eventos de Content Analytics se envíen al conjunto de datos de Content Analytics.
      1. Si Web SDK no está configurado para la propiedad Tags, se crea una nueva configuración de Web SDK para enviar únicamente eventos de Content Analytics.
      1. Si Web SDK está configurado para esta propiedad Tag, no se realizan cambios en la configuración existente de Web SDK.
* **[!UICONTROL Guardar]**: los cambios realizados en una configuración implementada se guardan y la implementación se actualiza.
* **[!UICONTROL Salir]**. Sale de la configuración guiada. Todos los cambios realizados en una configuración implementada se descartan.

>[!MORELIKETHIS]
>
>[Configuración manual de análisis de contenido](manual.md)
>
