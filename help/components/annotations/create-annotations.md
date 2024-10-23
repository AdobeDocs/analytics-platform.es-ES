---
title: Creación de anotaciones
description: Cómo crear anotaciones en Espacio de trabajo.
feature: Components
exl-id: 68fef9b3-dc47-4e56-bea6-d1c4c39fb51b
role: User, Admin
source-git-commit: c56c77079aa21fb740fda6bec333731a1f82a48f
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 24%

---

# Creación de anotaciones

De forma predeterminada, solo los administradores pueden crear anotaciones. Los usuarios tienen derechos para ver anotaciones, de forma similar a como ven otros componentes (como filtros, métricas calculadas, etc.).

Sin embargo, los administradores pueden dar permiso a **[!UICONTROL Creación de anotaciones]** para **[!UICONTROL Herramientas de informes]** en **[!UICONTROL Editar permisos para el acceso de CJA Workspace]** a los usuarios a través del Admin Console. Consulte [Control de acceso de nivel de usuario](/help/technotes/access-control.md#user-level-access) para obtener más información.

Puede crear una anotación de las siguientes maneras:

![Crear una anotación](assets/create-annotation.png)

* ?? En la interfaz principal, seleccione **[!UICONTROL Componentes]** y seleccione **[!UICONTROL Anotaciones]**. Seleccione ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**] del administrador de [[!UICONTROL Anotaciones]](/help/components/annotations/manage-annotations.md).
* ?? En un proyecto de Workspace, en el menú contextual de una visualización, seleccione **[!UICONTROL Crear anotación a partir de la selección]**.
* ?? En un proyecto de Workspace, en el menú contextual de un gráfico de líneas, seleccione **[!UICONTROL Anotar selección]**.
* ??En un proyecto de Workspace, seleccione **[!UICONTROL Componentes]** en el menú y seleccione **[!UICONTROL Crear anotación]**.
* ?? En un proyecto de Workspace, use el acceso directo **[!UICONTROL ctrl+mayús+o]** (Windows) o **[!UICONTROL mayús+comando+o]** (macOS)

Para definir la anotación, utilice el [[!UICONTROL Generador de anotaciones]](#annotation-builder):

<!-- Should we really mention API here. If so, we can do it all over the place in the docs...
| **Use the [Customer Journey Analytics Annotations API](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | The Customer Journey Analytics Annotations APIs allow you to create, update, or retrieve annotations programmatically through Adobe Developer. These APIs use the same data and methods that Adobe uses inside the product UI. |
-->


## Generador de anotaciones {#annotation-builder}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_annotations_details"
>title="Detalles de anotación"
>abstract="Las anotaciones le permiten comunicar de forma eficaz los matices y perspectivas de datos contextuales a su organización. Permiten enlazar eventos de calendario con dimensiones/métricas específicas. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_annotations_scope"
>title="Ámbito"
>abstract="El ámbito le permite personalizar qué datos se van a anotar. Las métricas y los segmentos calculados no heredarán de forma automática las anotaciones aplicadas a los componentes utilizados en sus definiciones. Puede añadir nuevas métricas calculadas a la sección de ámbito de una anotación existente. Los nuevos segmentos requieren una nueva anotación."

<!-- markdownlint-enable MD034 -->


El cuadro de diálogo **[!UICONTROL Generador de anotaciones]** se usa para crear anotaciones nuevas o editar las existentes. El cuadro de diálogo se titula **[!UICONTROL Nueva anotación]** o **[!UICONTROL Editar anotación]** para las anotaciones que cree o administre desde el administrador de [[!UICONTROL Anotaciones]](/help/components/annotations/manage-annotations.md).


>[!BEGINTABS]

>[!TAB Creador de anotaciones]

![Ventana de detalles de anotación que muestra los campos y las opciones descritas en la sección siguiente.](assets/annotation-builder.png)

>[!TAB Crear/editar anotación]

![Ventana de detalles de anotación que muestra los campos y las opciones descritas en la sección siguiente.](assets/create-edit-annotation.png)

>[!ENDTABS]

1. Especifique los siguientes detalles (![Necesario](/help/assets/icons/Required.svg) es obligatorio):

   | Elemento | Descripción |
   | --- | --- |
   | **[!UICONTROL Vista de datos]** | Puede seleccionar la vista de datos para la anotación. La anotación que defina estará disponible como anotación en los proyectos de Workspace en función de la vista de datos seleccionada. Se anula esta selección cuando se habilita [!UICONTROL Aplicar a todas las vistas de datos]. |
   | **[!UICONTROL Anotación solo de proyecto]** | Un cuadro de información para explicar que la anotación que cree solo está visible en el proyecto de Workspace en el que está trabajando. Habilite **[!UICONTROL Hacer que esta anotación esté disponible para todos sus proyectos]**, para que la anotación sea visible para todos sus proyectos. Este cuadro de información solo está visible cuando se crea una anotación desde un proyecto de Workspace. |
   | **[!UICONTROL Título]** ![Requerido](/help/assets/icons/Required.svg) | Asigne un nombre a la anotación, por ejemplo, `Needs further investigation`. |
   | **[!UICONTROL Descripción]** | Proporcione una descripción para la anotación, por ejemplo, `We never expected such a fluctuation in numbers.`. |
   | **[!UICONTROL Etiquetas]** | Organice la anotación creando o aplicando una o varias etiquetas. Empiece a escribir para buscar las etiquetas existentes que puede seleccionar. O presione **[!UICONTROL Entrar]** para agregar una etiqueta nueva. Seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para quitar una etiqueta. |
   | **[!UICONTROL Fecha de aplicación]** ![Requerida](/help/assets/icons/Required.svg) | Seleccione la fecha o el intervalo de fechas que debe estar presente para que la anotación sea visible. Cuando se crea una anotación mediante el método abreviado, la anotación toma el valor predeterminado de un intervalo de fechas solo para el día. Cuando crea una anotación utilizando una selección en una visualización, la anotación toma el valor predeterminado del intervalo de fechas en función del intervalo de fechas del panel al que pertenece la visualización. |
   | **[!UICONTROL Color]** | Aplique un color a la anotación. La anotación aparece en el proyecto con el color seleccionado. El color se puede utilizar para categorizar anotaciones, como festivos, eventos externos, problemas de seguimiento, etc. |
   | **[!UICONTROL Ámbito]** | Arrastre y suelte las métricas del panel de componentes que almacena en déclencheur la anotación. Por ejemplo, Personas, Sesiones y Eventos. A continuación, arrastre y suelte las dimensiones o filtros del panel de componentes que actúen como filtros para determinar si desea mostrar o no la anotación. Si no especifica un ámbito, la anotación se aplica a todos los datos. <br/>Tiene dos opciones:<ul><li>**[!UICONTROL Cualquiera de estas métricas está presente]**: Arrastre y suelte hasta 10 métricas que almacenen en déclencheur la anotación que desea mostrar.<br/>Por ejemplo, la métrica Ingresos ha dejado de recopilar datos para un intervalo de fechas específico. Arrastre la métrica Ingresos a este cuadro.</li><li>**[!UICONTROL Con todos estos filtros]**: arrastre y suelte hasta 10 dimensiones o filtros que filtran si se muestra la anotación.</li></ul><p><p>**Nota:** Cualquier anotación aplicada a un componente que luego se usa como parte de una métrica calculada o definición de filtro NO hereda automáticamente la anotación. La métrica calculada deseada también debe agregarse a la sección de ámbito para mostrar la anotación. Sin embargo, se debe crear una nueva anotación para cualquier filtro que desee anotar con la misma información. Por ejemplo, aplica una anotación a [!UICONTROL Pedidos] en un día específico. A continuación, utilice [!UICONTROL Pedidos] en una métrica calculada para el mismo intervalo de fechas. La nueva métrica calculada no muestra automáticamente la anotación de los pedidos. Agregue también la métrica calculada a la sección ámbito para que se muestre la anotación. |
   | **[!UICONTROL Aplicar a todas las vistas de datos]** | De forma predeterminada, la anotación se aplica a la vista de datos de origen. Al marcar esta casilla, puede hacer que la anotación se aplique a todas las vistas de datos de la compañía. |

   {style="table-layout:auto"}

1. Select
   * **[!UICONTROL Guardar]** para guardar la anotación.
   * **[!UICONTROL Guardar como]** para guardar una copia de la anotación.
   * **[!UICONTROL Eliminar]** para eliminar una anotación.
   * **[!UICONTROL Cancelar]** para cancelar los cambios realizados en una anotación o cancelar la creación de una nueva anotación.
