---
title: Administrar filtros
description: Obtenga información sobre cómo administrar filtros en Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: 97b831d7eee477ee7ef0bf8ae65e6a415d243464
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 4%

---

# Administrar filtros


Puede [compartir](filters-share.md), [filtrar](filters-filter.md), [etiquetar](filters-tag.md), [aprobar](filters-approve.md), cambiar el nombre, [copiar](filters-copy.md), eliminar, exportar filtros y marcar filtros como [favoritos](filters-favorite.md) desde una interfaz de administración central de [!UICONTROL Filtros]. Para administrar filtros:

* Seleccione **[!UICONTROL Componentes]** en la interfaz principal y luego seleccione **[!UICONTROL Filtros]**.


>[!NOTE]
>
>Los filtros rápidos que cree en un proyecto específico de Workspace no aparecerán en el administrador de [!UICONTROL Filtros], a menos que haya puesto el filtro a disposición de todos sus proyectos.
>

## Administrador de filtros

El administrador de filtros tiene los siguientes elementos de interfaz:

![Interfaz de filtros](assets/filters-manager.png)

### Lista de filtros

La lista de filtros ➊ muestra todos los filtros que posee, los filtros con ámbito en todos sus proyectos y los filtros que se han compartido con usted. La lista tiene las columnas siguientes:

| Columna | Descripción |
| --- | --- | 
| ![EsquemaDeEstrella](/help/assets/icons/StarOutline.svg) | Seleccione un filtro para favorecer a ![Estrella](/help/assets/icons/Star.svg) o para anular la preferencia de ![EsquemaDeEstrella](/help/assets/icons/StarOutline.svg). Ver [Marcar filtro como favorito](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL Título y descripción]** | Para editar el filtro, seleccione el vínculo del título, que abre el [Generador de filtros](filter-builder.md). Se ha indicado un filtro compartido con ![Compartir](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Vista de datos]** | Las vistas de datos a las que se aplica este filtro. |
| **[!UICONTROL Propietario]** | El propietario del filtro. Como usuario, solo verá los filtros que le pertenecen o las anotaciones que se han compartido con usted. |
| **[!UICONTROL Etiquetas]** | Las etiquetas de este filtro. |
| **[!UICONTROL Compartido con]** | El número de individuos o grupos con los que compartió el filtro. Seleccione para abrir el cuadro de diálogo **[!UICONTROL Compartir componente]**. Consulte [Compartir filtros](filters-share.md) para obtener más información. |
| **[!UICONTROL Fecha de modificación]** | Fecha y hora de la última modificación del filtro. |
| **[!UICONTROL Utilizado en]** | Mostrar dónde se están utilizando los filtros actualmente y cuántas veces se están utilizando en cada área. <p>Por ejemplo, si el filtro se está utilizando en 40 proyectos y 2 alertas, el valor de esta columna se muestra como [!UICONTROL **42 componentes**].</p> <p>Seleccione el valor de esta columna para ver el desglose de dónde se están utilizando los filtros (por ejemplo, [!UICONTROL **Proyectos (40)**], [!UICONTROL **Cuadros de resultados móviles (2)**]). Además, puede ver la lista de elementos en los que se utilizan los filtros. Por ejemplo, para ver la lista de proyectos donde se están usando, seleccione el vínculo [!UICONTROL **Proyectos (40)**].</p><p>Cada una de las siguientes áreas muestra el número de instancias de filtros que se están utilizando en esa área:</p>  <ul><li>[!UICONTROL **Proyectos**]<p>Contiene filtros que se [crearon en el generador de filtros](/help/components/filters/filter-builder.md#) y que están disponibles para todos los proyectos.</p></li><li>[!UICONTROL **Componentes ad hoc**]<p>Contiene filtros que se [crearon como filtros rápidos](/help/components/filters/quick-filters.md) y que están disponibles solamente dentro de un solo proyecto.</p></li><li>[!UICONTROL **Proyectos programados**]</li><li>[!UICONTROL **Cuadros de resultados móviles**]</li><li>[!UICONTROL **Anotaciones**]</li><li>[!UICONTROL **Métricas calculadas**]</li><li>[!UICONTROL **Report Builder**]<p>Al seleccionar esta opción, se descarga un archivo CSV con las siguientes columnas de datos:</p><ul><li>Nombre del Report Builder</li><li>Último acceso</li><li>Identificador de usuario de IMS de último acceso</li><li>Último nombre de usuario accedido</li></ul></li></ul><p>Esta información le ayuda a determinar si un componente es valioso para los usuarios de su organización, dónde se utiliza y si debe eliminarse o modificarse.</p><p>Tenga en cuenta lo siguiente cuando vea esta columna:</p><ul><li>Esta información solo está disponible para los administradores del sistema.</li><li>La columna [!UICONTROL **Utilizada en**] no se muestra de manera predeterminada. Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para configurar la visualización de esta columna.</li><li>Esta información no incluye el uso de la API o la Data Warehouse.</li><li>Si no hay datos en esta columna para un componente determinado pero el componente tiene una fecha de [!UICONTROL **Último uso**], es posible que el componente se haya utilizado en un análisis sin que se haya guardado.</li><li>La información de uso está disponible a partir de septiembre de 2023.</li></ul><p>Puede usar el [Diccionario de datos](/help/components/data-dictionary/data-dictionary-overview.md) junto con esta información para ayudarle a realizar un seguimiento y comprender mejor cómo se utilizan los componentes en su organización.</p> |
| **[!UICONTROL Último uso]** | La última vez que se utilizó el filtro. |

{style="table-layout:auto"}

Use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para especificar qué columnas desea mostrar.

### Barra de acciones

Puede realizar acciones en los filtros mediante el ➋ de barra de acciones. La barra de acciones contiene las siguientes acciones:

| Acción | Descripción |
|---|---|
| ![AgregarCírculo](/help/assets/icons/AddCircle.svg) **[!UICONTROL Agregar]** | Agregue otro filtro con el [Generador de filtros](filter-builder.md). |
| ![Buscar](/help/assets/icons/Search.svg) [!UICONTROL *Buscar por título*] | Cuando no se selecciona ningún filtro en la lista, busque filtros utilizando este campo de búsqueda. |
| ![Etiqueta](/help/assets/icons/Label.svg) **[!UICONTROL Etiqueta]** | Etiquete los filtros seleccionados. En el cuadro de diálogo **[!UICONTROL Filtro de etiquetas]**, seleccione o anule la selección de las etiquetas de los filtros seleccionados. Seleccione **[!UICONTROL Guardar]** para guardar las etiquetas de los filtros seleccionados. Consulte [Filtros de etiquetas](/help/components/filters/filters-tag.md) para obtener más información. |
| ![Compartir](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Compartir]** | Compartir los filtros seleccionados. En el cuadro de diálogo **[!UICONTROL Compartir filtro]**, puede ![Buscar](/help/assets/icons/Search.svg) *Buscar individuos o grupos* o puede seleccionar **[!UICONTROL Organización]** o **[!UICONTROL Grupos]**. Seleccione **[!UICONTROL Guardar]** para guardar los detalles de uso compartido de los filtros seleccionados. Consulte [Compartir filtros](filters-share.md) para obtener más información. |
| ![Eliminar](/help/assets/icons/Delete.svg) **[!UICONTROL Eliminar]** | Eliminar los filtros seleccionados. Se le pedirá una confirmación. |
| ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Cambiar nombre]** | Cambie el nombre de un solo filtro seleccionado. Cuando se selecciona, puede cambiar el nombre del filtro en línea. |
| ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Aprobar]** | Apruebe los filtros seleccionados. Consulte [Aprobar filtros](filters-approve.md) para obtener más información. |
| ![Copiar](/help/assets/icons/Copy.svg) **[!UICONTROL Copiar]** | Copie el filtro seleccionado. Los nuevos filtros se crean con el mismo nombre y sufijo `(Copy)`. |
| ![ArchivoCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exportar a CSV]** | Exportar los filtros a un archivo de `Filters List.csv`. |

### Barra de filtro activa

La ➌ de la barra de filtros muestra los filtros activos aplicados desde el panel de filtros a la lista de filtros (si los hay). Puede quitar rápidamente un filtro con ![CrossSize75](/help/assets/icons/CrossSize75.svg). Si se especifica más de un filtro, puede quitar todos los filtros usando **[!UICONTROL Quitar todos]**.

### Panel Filtro

Puede filtrar la lista de filtros mediante el ➍ del panel izquierdo ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]**. El panel Filtro muestra el tipo de filtro y el número de filtros que respetan el filtro específico. Seleccione ![Filter](/help/assets/icons/Filter.svg) para alternar la visualización del panel de filtros.

Ver [Filtrar la lista de filtros](filters-filter.md) para obtener más información.
