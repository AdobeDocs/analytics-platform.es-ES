---
title: Configuración de componentes
description: Vea la configuración principal de un componente de vista de datos.
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 98%

---

# Configuración de componentes {#component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_settings"
>title="Configuración de componentes"
>abstract="Vea y configure el nombre, la descripción y otras configuraciones relacionadas con un componente.<br/><br/>**Parámetros **<br/>**Ocultar componente en informes**: si activas esta casilla, se ocultará este componente a los usuarios que no sean administradores en los informes. Los administradores aún pueden acceder a él haciendo clic en **[!UICONTROL Mostrar todos los componentes]** en un proyecto de Workspace."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_contextlabels"
>title="Etiquetas de contexto"
>abstract="La eliminación de una etiqueta de contexto puede afectar a paneles o informes específicos donde se requiera el componente."

<!-- markdownlint-enable MD034 -->


La siguiente información describe la configuración que utiliza un componente de vista de datos.

![La configuración de componentes se describe en esta sección](../assets/component-settings.png)

| Configuración | Descripción/caso de uso |
| --- | --- |
| [!UICONTROL Tipo de componente] | Requerido. Permite cambiar un componente de Métrica a Dimensión o viceversa. Si se cambia esta lista desplegable, el componente pasará al área de componentes incluidos correspondiente. |
| [!UICONTROL Nombre del componente] | Requerido. Permite especificar el nombre descriptivo que aparecerá en Analysis Workspace. Puede cambiar el nombre de un componente para darle un nombre específico para la vista de datos. |
| [!UICONTROL Descripción] | Opcional, pero recomendada. Proporciona información sobre el componente a otros usuarios. |
| [!UICONTROL Etiquetas] | Opcional. Le permite etiquetar el componente con etiquetas personalizadas o listas para usar para facilitar la búsqueda y el filtrado en la IU de Analysis Workspace. |
| [!UICONTROL Etiquetas de contexto] | Opcional. Lista desplegable de etiquetas disponibles definidas por el sistema que se pueden aplicar a un componente. <p>Estas etiquetas pueden ser necesarias en las siguientes situaciones:</p> <ul><li>Para definir un conjunto de componentes que puede utilizar en los informes de experimentación utilizando el [Panel de experimentación](/help/analysis-workspace/c-panels/experimentation.md) en los proyectos de Analysis Workspace.<p>Para obtener más información, consulte [Integración con Journey Optimizer](/help/integrations/ajo.md#data-view) e [Creación de informes de Target](/help/integrations/at.md) para obtener más información.</p></li><li>Al utilizar plantillas que proporciona Adobe. De forma predeterminada, algunas plantillas que proporciona Adobe no funcionarán porque contienen componentes que no están en la vista de datos.<p>Para cada componente que falta, existe una etiqueta de contexto coincidente disponible en la vista de datos. Debe añadir la etiqueta de contexto coincidente a un componente que ya está en la vista de datos o añadir uno nuevo a la vista de datos y añadirle la etiqueta de contexto.</p><p>Para obtener más información, consulte [Añadir componentes que faltan a la vista de datos para una plantilla determinada](/help/analysis-workspace/templates/create-templates.md#add-missing-components-to-the-data-view-for-a-given-template) en el artículo [Creación y administración de plantillas](/help/analysis-workspace/templates/create-templates.md).</p> |
| [!UICONTROL Nombre del campo de esquema] | Nombre del campo de esquema. |
| [!UICONTROL Tipo de conjunto de datos] | Requerido. Campo no editable que muestra el tipo de conjunto de datos (evento, búsqueda o perfil) del que procede el componente. |
| [!UICONTROL Conjunto de datos] | Campo no editable que muestra el conjunto de datos desde el que se originó el componente. Este campo puede contener varios conjuntos de datos. |
| [!UICONTROL Tipo de esquema] | Campo no editable que muestra el tipo de datos del componente. Aunque puede utilizar cualquier tipo de campo de esquema admitido en Platform, no todos los tipos de campos son compatibles con Customer Journey Analytics. Se admiten los siguientes tipos de datos: `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String` y `Boolean`. Solo se permite el tipo de datos de esquema `String` en los conjuntos de datos de búsqueda en este momento. |
| [!UICONTROL ID de componente] | Requerido. La [API de Customer Journey Analytics](https://adobe.io/cja-apis/docs) utiliza este campo para hacer referencia al componente. Cada componente de una vista de datos debe ser único. Adobe genera automáticamente un ID para cada componente; sin embargo, puede hacer clic en el icono de edición y modificar el ID del componente. Al cambiar este ID de componente, se rompen todos los proyectos existentes de Workspace que contienen este componente. Aunque cada componente necesita un ID único en una sola vista de datos, puede utilizar el mismo ID de componente en otras vistas de datos. Si utiliza el mismo ID de componente en otras vistas de datos, puede hacer que los proyectos del Espacio de trabajo sean compatibles en todas las vistas de datos. <br/>Para los componentes basados en perfiles y búsquedas, el ID del componente tiene un prefijo de ID basado en el ID del conjunto de datos (por ejemplo: `642b28fcc1f0ee1c074265a0.person.name.firstName`). Si desea reutilizar un componente basado en perfiles o búsquedas, como `person.name.firstName`, en el proyecto de Workspace y configure este componente en diferentes vistas de datos, asegúrese de cambiar el nombre del ID del componente de forma exclusiva (por ejemplo: `myUniqueID.person.name.firstName`) en las vistas de datos. |
| [!UICONTROL Ruta] | Requerido. Campo no editable que muestra la ruta de esquema de la que procede el componente. |
| [!UICONTROL Etiquetas de uso de datos] | Cualquier etiqueta de uso de datos asignada a este componente en Adobe Experience Platform. [Más información](/help/data-views/data-governance.md). |
| [!UICONTROL Ocultar componente en creación de informes] | Permite depurar el componente fuera de la vista de datos para los usuarios que no son administradores. Los administradores aún pueden acceder a él haciendo clic en [!UICONTROL Mostrar todos los componentes] en un proyecto de Analysis Workspace. |

{style="table-layout:auto"}



>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuración de tipo de componente](https://video.tv.adobe.com/v/333112/?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


