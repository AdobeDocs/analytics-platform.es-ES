---
title: Administración de filtros
description: Descubra cómo administrar filtros en Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: 97b831d7eee477ee7ef0bf8ae65e6a415d243464
workflow-type: ht
source-wordcount: '884'
ht-degree: 100%

---

# Administración de filtros


Puede [compartir](filters-share.md), [filtrar](filters-filter.md), [etiquetar](filters-tag.md), [aprobar](filters-approve.md), cambiar el nombre, [copiar](filters-copy.md), eliminar, exportar filtros y marcar filtros como [favoritos](filters-favorite.md) desde una interfaz de administración central de [!UICONTROL Filtros]. Para administrar filtros:

* Seleccione **[!UICONTROL Componentes]** en la interfaz principal y luego seleccione **[!UICONTROL Filtros]**.


>[!NOTE]
>
>Los filtros rápidos que cree en un proyecto específico de Workspace no aparecerán en el administrador de [!UICONTROL Filtros], a menos que haya puesto el filtro a disposición de todos los proyectos.
>

## Administrador de filtros

El administrador de filtros contiene los siguientes elementos de interfaz:

![Interfaz de filtros](assets/filters-manager.png)

### Lista de filtros

La lista de filtros ➊ muestra todos los filtros de la que es propietario, los filtros que se han asignado a todos los proyectos y los filtros que se han compartido con usted. La lista tiene las siguientes columnas:

| Columna | Descripción |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Seleccione ![Star](/help/assets/icons/Star.svg) para favorecer o bien seleccione ![StarOutline](/help/assets/icons/StarOutline.svg) para desfavorecer un filtro. Consulte [Marcar filtro como favorito](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL Título y descripción]** | Para editar el filtro, seleccione el vínculo del título, que abre el [Generador de filtros](filter-builder.md). Un filtro compartido se indica con ![Compartir](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Vista de datos]** | Las vistas de datos a las que se aplica este filtro. |
| **[!UICONTROL Propietario]** | El propietario del filtro. Como usuario, solamente verá los filtros que sean de su propiedad o las anotaciones que compartan con usted. |
| **[!UICONTROL Etiquetas]** | Las etiquetas de este filtro. |
| **[!UICONTROL Compartido con]** | Indica con cuántas personas o grupos ha compartido el filtro. Seleccione esta opción para abrir el cuadro de diálogo **[!UICONTROL Compartir componente]**. Consulte [Compartir filtros ](filters-share.md) para obtener más información. |
| **[!UICONTROL Fecha de modificación]** | Fecha y hora de la última modificación del proyecto. |
| **[!UICONTROL Utilizado en]** | Muestra dónde se están utilizando los filtros actualmente y cuántas veces se están utilizando en cada área. <p>Por ejemplo, si el filtro se está utilizando en 40 proyectos y 2 alertas, el valor de esta columna se muestra como [!UICONTROL **42 componentes**].</p> <p>Seleccione el valor de esta columna para ver el desglose del lugar donde se están utilizando los filtros (por ejemplo, [!UICONTROL **Proyectos (40)**], [!UICONTROL **Cuadros de resultados móviles (2)**]). Además, puede ver la lista de elementos en los que se utilizan los filtros. Por ejemplo, para ver la lista de proyectos en los que se están usando, seleccione el vínculo [!UICONTROL **Proyectos (40)**].</p><p>Cada una de las siguientes áreas muestra el número de instancias de filtros que se están utilizando en esa área:</p>  <ul><li>[!UICONTROL **Proyectos**]<p>Contiene filtros que se [crearon en el generador de filtros](/help/components/filters/filter-builder.md#) y que están disponibles para todos los proyectos.</p></li><li>[!UICONTROL **Componentes ad hoc**]<p>Contiene filtros que se [crearon como filtros rápidos](/help/components/filters/quick-filters.md) y que están disponibles solamente dentro de un solo proyecto.</p></li><li>[!UICONTROL **Proyectos programados**]</li><li>[!UICONTROL **Cuadros de resultados móviles**]</li><li>[!UICONTROL **Anotaciones**]</li><li>[!UICONTROL **Métricas calculadas**]</li><li>[!UICONTROL **Report Builder**]<p>Al seleccionar esta opción, se descarga un archivo CSV con las siguientes columnas de datos:</p><ul><li>Nombre de Report Builder</li><li>Último acceso</li><li>ID usuario de IMS de último acceso</li><li>Nombre de usuario de último acceso</li></ul></li></ul><p>Esta información puede ayudarle a determinar si un componente es valioso para los usuarios de su organización, dónde se utiliza y si debe eliminarse o modificarse.</p><p>Tenga en cuenta lo siguiente cuando vea esta columna:</p><ul><li>Esta columna solo está disponible para los administradores del sistema.</li><li>La columna [!UICONTROL **Utilizado en**] no se muestra de manera predeterminada. Utilice ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para configurar la visualización de esta columna.</li><li>Esta información no incluye el uso de la API o Data Warehouse.</li><li>Si no hay datos en esta columna para un componente determinado pero el componente tiene una fecha de [!UICONTROL **Último uso**], es posible que el componente se haya utilizado en un análisis sin que se haya guardado.</li><li>La información de uso está disponible a partir de septiembre de 2023.</li></ul><p>Puede utilizar el [Diccionario de datos](/help/components/data-dictionary/data-dictionary-overview.md) junto con esta información para ayudarle a realizar un seguimiento y comprender mejor cómo se utilizan los componentes en su organización.</p> |
| **[!UICONTROL Último uso]** | La última vez que se utilizó el filtro. |

{style="table-layout:auto"}

Usa ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para especificar qué columnas deseas mostrar.

### Barra de acciones

Puede realizar acciones en los filtros mediante la barra de acciones ➋. La barra de acciones contiene las siguientes acciones:

| Acción | Descripción |
|---|---|
| ![AgregarCírculo](/help/assets/icons/AddCircle.svg) **[!UICONTROL Añadir]** | Añade otra anotación con el [Generador de filtros](filter-builder.md). |
| ![Búsqueda](/help/assets/icons/Search.svg) [!UICONTROL *Búsqueda por el título*] | Cuando no se selecciona ningún filtro en la lista, busque los filtros mediante este campo de búsqueda. |
| ![Etiqueta](/help/assets/icons/Label.svg) **[!UICONTROL Etiqueta]** | Etiquete los filtros seleccionados. En el cuadro de diálogo **[!UICONTROL Filtro de etiqueta]**, seleccione o anule la selección de las etiquetas para los filtros seleccionados. Seleccione **[!UICONTROL Guardar]** para guardar las etiquetas de los filtros seleccionados. Consulte [Filtros de etiqueta](/help/components/filters/filters-tag.md) para obtener más información. |
| ![Compartir](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Compartir]** | Comparta los filtros seleccionados. En el cuadro de diálogo **[!UICONTROL Compartir filtro]**, puede ![Búsqueda](/help/assets/icons/Search.svg) *Buscar personas o grupos* o puede seleccionar **[!UICONTROL Organización]** o **[!UICONTROL Grupos]**.  Seleccione **[!UICONTROL Guardar]** para guardar los detalles de uso compartido de los filtros seleccionados. Consulte [Compartir filtros](filters-share.md) para obtener más información. |
| ![Eliminar](/help/assets/icons/Delete.svg) **[!UICONTROL Eliminar]** | Elimine los filtros seleccionados. Se le pedirá una confirmación. |
| ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Cambiar nombre]** | Cambie el nombre de un solo filtro seleccionado. Cuando se selecciona, puede cambiar el nombre del filtro en línea. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Aprobar]** | Apruebe los filtros seleccionados. Consulte [Aprobar filtros](filters-approve.md) para obtener más información. |
| ![Copiar](/help/assets/icons/Copy.svg)  **[!UICONTROL Copiar]** | Copie el filtro seleccionado. Los nuevos filtros se crean con el mismo nombre y sufijo`(Copy)`.  |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exportar a CSV]** | Exporte los filtros a un archivo `Filters List.csv`. |

### Barra de filtro activa

La barra de filtros ➌ muestra los filtros activos aplicados desde el panel de filtros a la lista de filtros (si los hay). Puedes quitar rápidamente un filtro con ![CrossSize75](/help/assets/icons/CrossSize75.svg). Si se especifica más de un filtro, puedes quitar todos los filtros usando **[!UICONTROL Quitar todos]**.

### Panel Filtro

Puede filtrar la lista de filtros mediante el panel izquierdo ➍ ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Filtro]**. El panel Filtro muestra el tipo de filtro y el número de filtros que respetan el filtro específico. Selecciona ![Filtro](/help/assets/icons/Filter.svg) para alternar la visualización del panel de filtros.

Consulte [Filtrar la lista de filtros](filters-filter.md) para obtener más información.
