---
title: Administrar anotaciones
description: Obtenga información sobre cómo administrar anotaciones en Workspace.
feature: Components
exl-id: 12f2cc2f-477c-4f16-afdd-b0db84725b32
role: User
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 91%

---

# Administración de anotaciones

Puedes compartir, filtrar, etiquetar, aprobar, copiar, eliminar anotaciones y marcar anotaciones como favoritas desde una interfaz de administración central de [!UICONTROL Anotaciones]. Para administrar anotaciones:

* Selecciona **[!UICONTROL Componentes]** en la interfaz principal y luego selecciona **[!UICONTROL Anotaciones]**.


>[!NOTE]
>
>Las anotaciones que crees en un proyecto específico de Workspace no aparecerán en el administrador de [!UICONTROL Anotaciones], a menos que hayas puesto la anotación a disposición de todos los proyectos.
>

## Administrador de anotaciones

El administrador Anotaciones tiene los siguientes elementos de interfaz:

![Interfaz de anotaciones](assets/annotations-manager.png)

### Lista de anotaciones

La lista de anotaciones ➊ muestra todas las anotaciones que posee, las anotaciones que se han asignado a todos sus proyectos y las anotaciones que se han compartido con usted. La lista tiene las siguientes columnas:

| Columna | Descripción |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Selecciona para favorecer a ![Star](/help/assets/icons/Star.svg) o para desfavorecer de ![StarOutline](/help/assets/icons/StarOutline.svg) de una anotación. |
| **[!UICONTROL Título y descripción]** | Aparecen en el Generador de anotaciones. Para editar el título y la descripción, selecciona el vínculo del título: abre el [Generador de anotaciones](/help/components/annotations/create-annotations.md#annotation-builder). Se indica una anotación compartida con ![Share](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Vista de datos]** | Las vistas de datos a las que se aplica esta anotación. |
| **[!UICONTROL Propietario]** | El propietario de la anotación. Si no eres el administrador, solo podrás ver las anotaciones que te pertenecen o que se han compartido contigo. |
| **[!UICONTROL Intervalo de fecha aplicado]** | La fecha o el intervalo de fechas al que se aplica esta anotación. |
| **[!UICONTROL Etiquetas]** | Las etiquetas de esta anotación. |
| **[!UICONTROL Compartido con]** | Indica cuántos individuos o grupos han compartido la anotación. Selecciona para abrir el cuadro de diálogo **[!UICONTROL Compartir componente]**. |
| **[!UICONTROL Fecha de modificación]** | Muestra la fecha y la hora de la última modificación de la anotación. |

{style="table-layout:auto"}

Usa ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para especificar qué columnas deseas mostrar.

### Barra de acciones

Puede realizar acciones en anotaciones mediante la barra de acciones ➋. La barra de acciones contiene las siguientes acciones:

| Icono | Acción | Descripción |
|:--:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Agregue]** | Agrega otra anotación con el [Generador de anotaciones](create-annotations.md#annotation-builder). |
| ![Buscar](/help/assets/icons/Search.svg) | [!UICONTROL *Buscar por título*] | Cuando no se selecciona ninguna anotación en la lista, busca anotaciones mediante este campo de búsqueda. |
| ![Etiqueta](/help/assets/icons/Label.svg) | **[!UICONTROL Etiqueta]** | Etiquetar las anotaciones seleccionadas. En el cuadro de diálogo **[!UICONTROL Componente de etiqueta]**, selecciona o anula la selección de las etiquetas para las anotaciones seleccionadas. Selecciona **[!UICONTROL Guardar]** para guardar las etiquetas de las anotaciones seleccionadas. |
| ![Compartir](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Compartir]** | Compartir las anotaciones seleccionadas. En el cuadro de diálogo **[!UICONTROL Compartir componente]**, puedes ![Buscar](/help/assets/icons/Search.svg) *Buscar individuos o grupos* o puede seleccionar **[!UICONTROL Organización]** o **[!UICONTROL Grupos]**. Selecciona **[!UICONTROL Guardar]** para guardar los detalles de uso compartido de las anotaciones seleccionadas. Consulta [Compartir anotaciones](#share-annotations) para obtener más información.  |
| ![Eliminar](/help/assets/icons/Delete.svg) | **[!UICONTROL Eliminar]** | Eliminar las anotaciones seleccionadas. Se te pedirá una confirmación. |
| ![Editar](/help/assets/icons/Edit.svg) | **[!UICONTROL Cambiar el nombre]** | Cambiar el nombre de una sola anotación seleccionada. Cuando se selecciona, puedes cambiar el nombre de la anotación en línea. |
| ![Copiar](/help/assets/icons/Copy.svg) | **[!UICONTROL Copiar]** | Copia las anotaciones seleccionadas. Las nuevas anotaciones se crean con el mismo nombre y sufijo (Copiar) |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exportar a CSV]** | Exportar las anotaciones a un archivo de `Annotations List.csv`. |

### Barra de filtro activa

La barra de filtros ➌ muestra los filtros activos (si los hay). Puedes quitar rápidamente un filtro con ![CrossSize75](/help/assets/icons/CrossSize75.svg). Si se especifica más de un filtro, puedes quitar todos los filtros usando **[!UICONTROL Quitar todos]**.

### Panel Filtro

Puede filtrar anotaciones utilizando el panel izquierdo **[!UICONTROL Filtro]** ➍. El panel Filtro muestra el tipo de filtro y el número de anotaciones que lo respetan. Selecciona ![Filtro](/help/assets/icons/Filter.svg) para alternar la visualización del panel de filtros.

Filtrar la lista de filtros

1. Selecciona ![Filtro](/help/assets/icons/Filter.svg) para abrir el panel Filtros. Si necesitas más espacio para la lista Filtros, puedes seleccionar ![Filtro](/help/assets/icons/Filter.svg) una vez más para cerrar el panel.
1. Puedes filtrar las anotaciones mediante cualquiera de las [secciones de filtro](#filter-sections) disponibles.

   >[!INFO]
   >
   >*Elementos* hacen referencia a los elementos de anotación mostrados en la [lista de anotaciones](manage-annotations.md#annotations-list).
   > 

#### Filtrar secciones

{{tagfiltersection}}
{{dataviewfiltersection}}
{{ownerfiltersection}}
{{daterangefiltersection}}
{{otherfiltersfiltersection}}


La [lista de anotaciones](manage-annotations.md#annotations-list) se actualiza automáticamente según la configuración del filtro. Puedes ver los filtros configurados en la [barra de filtros activa](manage-annotations.md#active-filter-bar).


## Edición de anotaciones

Puedes editar las anotaciones de dos formas:

* En un proyecto de Workspace, usa el icono [Información del componente](/help/components/use-components-in-workspace.md#component-info).

* En la lista [[!UICONTROL Anotaciones]](#annotations-list), selecciona el título de la anotación.

Utiliza el [Generador de anotaciones](/help/components/annotations/create-annotations.md#annotation-builder) para editar la anotación.

## Compartir anotaciones

Lo siguiente se aplica cuando se comparten anotaciones o se trabaja con anotaciones compartidas contigo:

* Las anotaciones solo de proyecto de un proyecto que compartas con otros usuarios se mostrarán para esos usuarios. Los usuarios no pueden editar ni eliminar estas anotaciones solo de proyecto.
* Si guardas una anotación y la compartes directamente con un usuario, solo podrá editarla o eliminarla si el usuario tiene derechos de administrador.

* Si se comparte un proyecto contigo, las anotaciones creadas en ese proyecto solo se mostrarán en ese proyecto. Si la anotación se comparte directamente contigo, aparecerá en todos los proyectos en los que se pueda mostrar.

## Anotaciones y zonas horarias

Todas las anotaciones se crean con una marca de tiempo, pero no con información de “hora” o “zona horaria”. En el momento del informe, se utiliza la zona horaria de la vista de datos configurada para el panel.
