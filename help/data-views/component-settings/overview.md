---
title: Configuración de componentes
description: Vea la configuración principal de un componente de vista de datos.
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: c0a3fd138b21c2aa0ac6c11e182f58f57a056b42
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 77%

---

# Configuración de componentes

Configuración principal que utiliza un componente de vista de datos.

![Configuración de componentes](../assets/component-settings.png)

| Configuración | Descripción/caso de uso |
| --- | --- |
| [!UICONTROL Tipo de componente] | Requerido. Permite cambiar un componente de Métrica a Dimension o viceversa. Si se cambia esta selección desplegable, el componente pasará al área de componentes incluidos correspondiente. |
| [!UICONTROL Nombre del componente] | Requerido. Permite especificar el nombre descriptivo que aparecerá en Analysis Workspace. Puede cambiar el nombre de un componente para darle un nombre específico para la vista de datos. |
| [!UICONTROL Descripción] | Opcional, pero recomendada. Proporciona información sobre el componente a otros usuarios. |
| [!UICONTROL Etiquetas] | Opcional. Le permite etiquetar el componente con etiquetas personalizadas o listas para usar para facilitar la búsqueda y el filtrado en la IU de Analysis Workspace. |
| [!UICONTROL Etiquetas de contexto] | Opcional. Una lista desplegable de etiquetas definidas por el sistema disponibles que se pueden aplicar a un componente. Estas etiquetas pueden ser necesarias para definir un conjunto de componentes utilizados para la creación de informes en proyectos o paneles de Analysis Workspace. |
| [!UICONTROL Nombre del campo de esquema] | Nombre del campo de esquema. |
| [!UICONTROL Tipo de conjunto de datos] | Requerido. Campo no editable que muestra el tipo de conjunto de datos (evento, búsqueda o perfil) del que procede el componente. |
| [!UICONTROL Conjunto de datos] | Campo no editable que muestra el conjunto de datos desde el que se originó el componente. Este campo puede contener varios conjuntos de datos. |
| [!UICONTROL Tipo de esquema] | Campo no editable que muestra el tipo de datos del componente. Aunque puede utilizar cualquier tipo de campo de esquema admitido en Platform, no todos los tipos de campos son compatibles con CJA. Se admiten los siguientes tipos de datos: `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String` y `Boolean`. Solo el `String` El tipo de datos de esquema está permitido actualmente en los conjuntos de datos de búsqueda. |
| [!UICONTROL ID de componente] | Requerido. La [API de CJA](https://adobe.io/cja-apis/docs) utiliza este campo para hacer referencia al componente. Cada componente de una vista de datos debe ser único. Adobe genera automáticamente un ID para cada componente; sin embargo, puede hacer clic en el icono de edición y modificar el ID del componente. Al cambiar este ID de componente, se rompen todos los proyectos existentes de Workspace que contienen este componente. Aunque cada componente necesita un ID único en una sola vista de datos, puede utilizar el mismo ID de componente en otras vistas de datos. Si utiliza el mismo ID de componente en otras vistas de datos, puede hacer que los proyectos de Workspace sean compatibles en todas las vistas de datos. <br/>Para los componentes basados en perfiles y búsquedas, el ID del componente tiene un prefijo de ID basado en el ID del conjunto de datos (por ejemplo: `642b28fcc1f0ee1c074265a0.person.name.firstName`). Si desea reutilizar un componente basado en perfiles o búsquedas, como `person.name.firstName`, en el proyecto de Workspace y configure este componente en diferentes vistas de datos, asegúrese de cambiar el nombre del ID del componente de forma exclusiva (por ejemplo: `myUniqueID.person.name.firstName`) en las vistas de datos. |
| [!UICONTROL Ruta] | Requerido. Campo no editable que muestra la ruta de esquema de la que procede el componente. |
| [!UICONTROL Etiquetas de uso de datos] | Cualquier etiqueta de uso de datos asignada a este componente en Adobe Experience Platform.  [Más información](/help/data-views/data-governance.md) |
| [!UICONTROL Ocultar componente en creación de informes] | Permite depurar el componente fuera de la vista de datos para los usuarios que no son administradores. Los administradores aún pueden acceder a él haciendo clic en [!UICONTROL Mostrar todos los componentes] en un proyecto de Analysis Workspace. |

{style="table-layout:auto"}

Aquí hay un vídeo sobre la configuración de componentes en las vistas de datos:

>[!VIDEO](https://video.tv.adobe.com/v/333112/?quality=12)
