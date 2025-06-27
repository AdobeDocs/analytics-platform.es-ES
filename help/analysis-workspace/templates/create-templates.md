---
description: Obtenga información sobre cómo crear y administrar plantillas en Analysis Workspace.
title: Creación Y Administración De Plantillas
feature: Workspace Basics
role: User, Admin
exl-id: 23cdf02f-56a1-4465-ae7f-b3a1bcad28af
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '1851'
ht-degree: 99%

---

# Creación y administración de plantillas

Los administradores pueden crear plantillas y guardarlas para que otros usuarios las utilicen en su compañía al iniciar sesión.

Las personas de la compañía que inician sesión pueden usar estas plantillas de compañía tal como se describe en [Uso de plantillas](/help/analysis-workspace/templates/use-templates.md).

## Creación de una plantilla {#create-templates}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="use-case-ajo-template"
>title="Uso de plantillas en Journey Optimizer"
>abstract="Cuando se utiliza esta plantilla en Journey Optimizer, se utiliza la vista de datos establecida como vista de datos predeterminada de Adobe Journey Optimizer, independientemente de la vista de datos que se haya seleccionado con esta plantilla en Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

Para crear una nueva plantilla que pueden utilizar las personas de su compañía para iniciar sesión:

1. En Analysis Workspace, genere un proyecto con el estado que desee.

1. Seleccione [!UICONTROL **Proyecto**] > **[!UICONTROL Guardar como plantilla...]**.

   ![Plantilla de la compañía](assets/company-template-save.png)

1. Especifique la siguiente información en el cuadro de diálogo [!UICONTROL Guardar como plantilla]:

   | Campo | Descripción |
   |---------|----------|
   | **[!UICONTROL Nombre]** | Escriba un nombre descriptivo para la plantilla. |
   | **[!UICONTROL Descripción]** | Suministre una breve descripción de la plantilla que describa los usos previstos. |
   | **[!UICONTROL Por qué utilizar esta plantilla]** | Ofrezca una breve explicación para informar a los miembros de la organización sobre cómo se podría utilizar esta plantilla. Esta explicación se muestra en la página Vista previa de la plantilla. |
   | **[!UICONTROL Canales]** | Seleccione los canales aplicables correspondientes a esta plantilla. Puede seleccionar varios canales: **[!UICONTROL web]**, **[!UICONTROL móvil]**, **[!UICONTROL canales múltiples]**, **[!UICONTROL centro de llamadas]** y **[!UICONTROL En la tienda]**.<p>Las selecciones que realice determinarán dónde se mostrará la plantilla y qué segmentos se aplicarán a los usuarios que acceden a ella desde la página Plantillas de la organización.</p> |
   | **[!UICONTROL Casos de uso]** | Seleccione los casos de uso aplicables a esta plantilla. Puede seleccionar varios casos de uso: **[!UICONTROL Participación]**, **[!UICONTROL Conversión]**, **[!UICONTROL Público]**, **[!UICONTROL Adquisición]** y **[!UICONTROL Journey Optimizer]**. <p>Las selecciones que realice determinarán la ubicación de la plantilla en la página Plantillas de la organización. Los usuarios pueden navegar hasta la plantilla o pueden filtrar la lista por caso de uso. </p><p>**Nota:** Cuando selecciona la opción **[!UICONTROL Journey Optimizer]**, la plantilla está disponible para su uso en Adobe Journey Optimizer. En Journey Optimizer, hay disponible un menú desplegable en la página **[!UICONTROL Informes]**, que permite a los usuarios seleccionar esta plantilla o la plantilla predeterminada. Consulte [Introducción a la experiencia de creación de informes actualizada](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja) en la documentación de Journey Optimizer.</p><p>Tenga en cuenta lo siguiente al seleccionar la opción Journey Optimizer:</p><ul><li>Esta opción solo está disponible si los datos de Journey Optimizer existen en la vista de datos que está utilizando en Customer Journey Analytics. </li><li>Cuando se utiliza esta plantilla en Journey Optimizer, se utiliza la vista de datos establecida como vista de datos predeterminada en Adobe Journey Optimizer, independientemente de la vista de datos que se haya seleccionado con esta plantilla en Customer Journey Analytics. <br/>Para obtener más información sobre cómo establecer una vista de datos como vista de datos predeterminada en Journey Optimizer, consulte [Compatibilidad](/help/data-views/create-dataview.md#compatibility) en [Creación o edición de una vista de datos](/help/data-views/create-dataview.md).</li></ul> |
   | **[!UICONTROL Tipo de actividad de Journey Optimizer]** | Elija el tipo de actividad de Journey Optimizer que desea asociar a esta plantilla: **[!UICONTROL Campañas]**, **[!UICONTROL Recorridos]**, **[!UICONTROL Páginas de destino]**, **[!UICONTROL Informes]** o **[!UICONTROL Suscripciones]**. <p>Deje este campo en blanco si desea que esta plantilla esté asociada a todos los tipos de actividad.</p><p>Este campo solo se muestra si **[!UICONTROL Journey Optimizer]** está seleccionado en el campo **[!UICONTROL Casos de uso]**.</p> |
   | **[!UICONTROL Actividad de Journey Optimizer]** | Elija la actividad de Journey Optimizer que desee asociar a esta plantilla. <p>Deje este campo en blanco si desea que esta plantilla se asocie a todas las actividades del tipo de actividad seleccionada.</p><p>Este campo solo se muestra si **[!UICONTROL Journey Optimizer]** está seleccionado en el campo **[!UICONTROL Casos de uso]**.</p> |
   | **[!UICONTROL Etiquetas]** | Especifique las etiquetas que desea aplicar a la plantilla. Las personas pueden filtrar la lista de plantillas por las etiquetas que añada. |

1. Seleccione [!UICONTROL **Guardar como plantilla**]

Para obtener información sobre cómo los usuarios pueden crear un proyecto basado en una plantilla, consulte [Creación de un proyecto basado en una plantilla](/help/analysis-workspace/templates/use-templates.md#create-a-project-based-on-a-template) en [Uso de plantillas](/help/analysis-workspace/templates/use-templates.md).

## Edición o eliminación de una plantilla

Los administradores pueden editar o eliminar las plantillas de la compañía.

1. En Analysis Workspace, seleccione la pestaña [!UICONTROL **Workspace**] y, a continuación, en **[!UICONTROL Plantillas]**, en el carril izquierdo, seleccione las plantillas **[!UICONTROL _nombre_compañía_inicio_sesión _]**.

1. Si está viendo plantillas en una vista de columna ![icono de vista de columna](assets/column-view-icon.png):

   1. Vaya a la plantilla que desea editar o eliminar y seleccione el icono de información junto al nombre de la plantilla.

      ![Información de plantilla de la compañía](assets/company-template-info.png)

   1. Seleccione **[!UICONTROL Vista previa]**.

   1. Seleccione el icono Más y luego seleccione **[!UICONTROL Editar]** o **[!UICONTROL Eliminar]**.

      ![Edición o eliminación de una plantilla](assets/company-template-edit-delete.png)

1. Si está viendo plantillas en una vista de tarjeta ![icono de vista de tarjeta](assets/card-view-icon.png):

   1. Busque la plantilla que desea editar o eliminar.

      ![Vista de tarjeta de plantilla de la compañía](assets/company-template-cards.png)

   1. Pase el puntero por encima de la plantilla y seleccione **[!UICONTROL Vista previa]**.

   1. Seleccione el icono Más y luego **[!UICONTROL Editar]** o **[!UICONTROL Eliminar]**.

      ![Edición o eliminación de la tarjeta de plantilla de la compañía](assets/company-template-card-edit-delete.png)

1. Si está editando una plantilla, realice las ediciones que desee y, a continuación, seleccione [!UICONTROL **Proyecto**] > **[!UICONTROL Guardar como plantilla...]**.

   ![Plantilla de la compañía](assets/company-template-save.png)

1. Especifique la siguiente información en el cuadro de diálogo [!UICONTROL Guardar como plantilla]:

   | Campo | Descripción |
   |---------|----------|
   | **[!UICONTROL Nombre]** | Escriba un nombre descriptivo para la plantilla. |
   | **[!UICONTROL Descripción]** | Suministre una breve descripción de la plantilla que describa los usos previstos. |
   | **[!UICONTROL Por qué utilizar esta plantilla]** | Ofrezca una breve explicación para informar a los miembros de la organización sobre cómo se podría utilizar esta plantilla. Esta explicación se muestra en la página Vista previa de la plantilla. |
   | **[!UICONTROL Canales]** | Seleccione los canales aplicables correspondientes a esta plantilla. Puede seleccionar varios canales: **[!UICONTROL web]**, **[!UICONTROL móvil]**, **[!UICONTROL canales múltiples]**, **[!UICONTROL centro de llamadas]** y **[!UICONTROL En la tienda]**. Si no se selecciona ningún canal, la plantilla se incluye con todos los canales.<p>Las selecciones que realice determinarán dónde se mostrará la plantilla y qué filtros se aplicarán a los usuarios que acceden a ella desde la página Plantillas de la organización.</p> |
   | **[!UICONTROL Casos de uso]** | Seleccione los casos de uso aplicables a esta plantilla. Puede seleccionar varios casos de uso: **[!UICONTROL Participación]**, **[!UICONTROL Conversión]**, **[!UICONTROL Público]**, **[!UICONTROL Adquisición]** y **[!UICONTROL Journey Optimizer]**. <p>Las selecciones que realice determinarán la ubicación de la plantilla en la página Plantillas de la organización. Los usuarios pueden navegar hasta la plantilla o pueden filtrar la lista por caso de uso. </p><p>**Nota:** Cuando selecciona la opción **[!UICONTROL Journey Optimizer]**, la plantilla está disponible para su uso en Adobe Journey Optimizer. En Journey Optimizer, hay disponible un menú desplegable en la página **[!UICONTROL Informes]**, que permite a los usuarios seleccionar esta plantilla o la plantilla predeterminada. Consulte [Introducción a la experiencia de creación de informes actualizada](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja) en la documentación de Journey Optimizer.</p><p>Tenga en cuenta lo siguiente al seleccionar la opción Journey Optimizer:</p><ul><li>Esta opción solo está disponible si los datos de Journey Optimizer existen en la vista de datos que está utilizando en Customer Journey Analytics. </li><li>Cuando se utiliza esta plantilla en Journey Optimizer, se utiliza la vista de datos establecida como vista de datos predeterminada en Adobe Journey Optimizer, independientemente de la vista de datos que se haya seleccionado con esta plantilla en Customer Journey Analytics. <br/>Para obtener más información sobre cómo establecer una vista de datos como vista de datos predeterminada en Journey Optimizer, consulte [Compatibilidad](/help/data-views/create-dataview.md#compatibility) en [Creación o edición de una vista de datos](/help/data-views/create-dataview.md).</li></ul> |
   | **[!UICONTROL Tipo de actividad de Journey Optimizer]** | Elija el tipo de actividad de Journey Optimizer que desea asociar a esta plantilla: **[!UICONTROL Campañas]**, **[!UICONTROL Recorridos]**, **[!UICONTROL Páginas de destino]**, **[!UICONTROL Informes]** o **[!UICONTROL Suscripciones]**. <p>Deje este campo en blanco si desea que esta plantilla esté asociada a todos los tipos de actividad.</p><p>Este campo solo se muestra si **[!UICONTROL Journey Optimizer]** está seleccionado en el campo **[!UICONTROL Casos de uso]**.</p> |
   | **[!UICONTROL Actividad de Journey Optimizer]** | Elija la actividad de Journey Optimizer que desee asociar a esta plantilla. <p>Deje este campo en blanco si desea que esta plantilla se asocie a todas las actividades del tipo de actividad seleccionada.</p><p>Este campo solo se muestra si **[!UICONTROL Journey Optimizer]** está seleccionado en el campo **[!UICONTROL Casos de uso]**.</p> |
   | **[!UICONTROL Etiquetas]** | Especifique las etiquetas que desea aplicar a la plantilla. Las personas pueden filtrar la lista de plantillas por las etiquetas que añada. |

1. Seleccione [!UICONTROL **Guardar como plantilla**].

## Cambiar el nombre, etiquetar o aprobar plantillas

Los administradores pueden cambiar el nombre, etiquetar y aprobar plantillas de la empresa.

1. En Analysis Workspace, seleccione la pestaña [!UICONTROL **Workspace**] y, a continuación, la **[!UICONTROL pestaña Proyectos]** en el carril izquierdo.

1. Seleccione el icono de filtro para filtrar la lista de proyectos.

1. En el carril de filtro, seleccione **[!UICONTROL Otros filtros]** y, a continuación, seleccione **[!UICONTROL Plantillas de la compañía]**.

   Se muestra una lista de las plantillas de la compañía. No se muestran todos los proyectos normales, a menos que estén anclados.

   Las plantillas de la compañía se pueden identificar mediante el ![icono de plantillas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileTemplate_18_N.svg) que precede al nombre de la plantilla.

   ![Mostrar los filtros de plantillas de la compañía](assets/company-templates-filter.png)

1. Haga clic en el icono de puntos suspensivos **...** situado junto a una plantilla para ver las opciones disponibles.

   ![Acciones de las plantillas de la compañía](assets/company-templates-actions.png)

1. Seleccione **[!UICONTROL Cambiar nombre]**, **[!UICONTROL Etiqueta]** o **[!UICONTROL Aprobar]**.

   También puede eliminar una plantilla, o puede eliminar una plantilla como se describe en [Editar o eliminar plantillas](#edit-or-delete-templates).

1. (Opcional) Para volver a la vista normal, en el carril de filtro, anule la selección de **[!UICONTROL Plantillas de empresa]**.

## Agregar los componentes que faltan a la vista de datos de una plantilla determinada

De forma predeterminada, algunas plantillas que proporciona Adobe no se pueden usar porque contienen componentes que no están en la vista de datos.

Para cada componente que falta, existe una etiqueta de contexto coincidente disponible en la vista de datos. Debe añadir la etiqueta de contexto coincidente a un componente que ya está en la vista de datos o añadir uno nuevo a la vista de datos y añadirle la etiqueta de contexto.

Para agregar los componentes que faltan a una plantilla:

1. En Analysis Workspace, seleccione la pestaña [!UICONTROL **Workspace**] y, a continuación, en **[!UICONTROL Plantillas]** en el carril izquierdo, seleccione **[!UICONTROL Plantillas de Adobe]**.

1. Seleccione el icono de filtro para filtrar la lista de plantillas.

1. Seleccione **[!UICONTROL No está listo para su uso]** para mostrar las plantillas que requieren componentes que no están en la vista de datos.

   ![Usar una plantilla a la que le faltan componentes](assets/template-not-ready.png)

1. Busque una plantilla que aún no esté lista para usar con la vista de datos.

1. Realice cualquiera de los siguientes pasos:

   * **Si está viendo plantillas en una vista de columna** ![icono de vista de columna](assets/column-view-icon.png):

      1. Vaya a la plantilla que aún no esté lista para usar con la vista de datos y, a continuación, seleccione el icono de información junto al nombre de la plantilla.

         ![Información de la plantilla de la compañía](assets/company-template-info.png)

      1. Seleccione **[!UICONTROL Vista previa]**.

         ![Página de vista previa de la plantilla](assets/template-preview.png)

   * **Si está viendo plantillas en una vista de tarjeta** ![icono de vista de tarjeta](assets/card-view-icon.png):

      1. Busque la plantilla que aún no está lista para usar con la vista de datos.

         ![Vista de tarjeta de la plantilla de la compañía](assets/company-template-cards.png)

      1. Pase el puntero por encima de la plantilla y seleccione **[!UICONTROL Vista previa]**.

         ![Página de vista previa de la plantilla](assets/template-preview.png)

1. En la sección **[!UICONTROL Componentes faltantes]**, se muestra una lista de los componentes que faltan en la vista de datos. Seleccione **[!UICONTROL Añada estos componentes a su vista de datos]**.

   La página de configuración de la vista de datos se muestra en una nueva pestaña.

1. Seleccione la pestaña **[!UICONTROL Componentes]** de la vista de datos.

   ![Pestaña Componentes de la vista de datos](assets/template-dataview.png)

1. Para cada componente que se haya enumerado como ausente de la plantilla, realice una de las siguientes acciones en la pestaña **[!UICONTROL Componentes]**:

   * En la sección **[!UICONTROL Componentes incluidos]**, seleccione un componente que ya esté incluido en la vista de datos que desee usar para el componente que falta.

   * Agregue un nuevo componente a la vista de datos que desee utilizar para el componente que falta y, a continuación, seleccione el componente.

     Para agregar un nuevo componente a la vista de datos, busque en la lista de campos de esquema y arrástrelo a la sección **[!UICONTROL Componentes incluidos]**.

1. Con el componente seleccionado, busque el menú desplegable **[!UICONTROL Etiquetas de contexto]** en la columna derecha.

   ![Pestaña Componentes de la vista de datos](assets/template-dataview-context-label.png)

1. En el menú desplegable **[!UICONTROL Etiquetas de contexto]**, seleccione la etiqueta de contexto que tenga el mismo nombre que el componente que falta.

1. Seleccione **[!UICONTROL Guardar y continuar]**.

1. Para cada componente que falte, repita el proceso de agregar la etiqueta de contexto coincidente a un componente en la vista de datos.


## Acceder a una plantilla de la compañía

Al igual que con las plantillas que proporciona Adobe, los usuarios de la organización pueden acceder a las plantillas que crean los administradores.

Para obtener información sobre cómo obtener acceso a una plantilla de la compañía, consulte [Acceso y ejecución de una plantilla](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template) en [Uso de plantillas](/help/analysis-workspace/templates/use-templates.md).

## Ocultar la pestaña Plantillas

Los administradores pueden ocultar la pestaña Plantillas para todos los usuarios de su organización.

1. Vaya a **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Componentes]** > **[!UICONTROL Preferencias]** > **[!UICONTROL Compañia]**.
1. Seleccione la opción para **[!UICONTROL ocultar la pestaña Plantillas]**.
