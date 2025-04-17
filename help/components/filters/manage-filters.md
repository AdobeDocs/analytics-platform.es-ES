---
title: Administración de segmentos
description: Obtenga información sobre cómo administrar segmentos en Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: 66ec61ea64f1265d887d4941a22e1f9757120daa
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 32%

---

# Administración de segmentos


Puede [compartir](filters-share.md), [segmento](filters-filter.md), [etiqueta](filters-tag.md), [aprobar](filters-approve.md), cambiar el nombre, [copiar](filters-copy.md), eliminar, exportar segmentos y marcar segmentos como [favoritos](filters-favorite.md) desde una interfaz de administración central de [!UICONTROL Segmento]. Para administrar segmentos:

* Seleccione **[!UICONTROL Componentes]** en la interfaz principal y luego seleccione **[!UICONTROL Segmentos]**.


>[!NOTE]
>
>Los segmentos rápidos que cree en un proyecto específico de Workspace no aparecerán en el administrador de [!UICONTROL Filtros], a menos que haya puesto el segmento a disposición de todos los proyectos.
>

## Administrador de segmentos

El Administrador de segmentos tiene los siguientes elementos de interfaz:

![Interfaz de segmento](assets/filters-manager.png)

### Lista de segmentos

La ➊ de lista de segmentos muestra todos los segmentos que posee, los segmentos a los que se ha dado ámbito en todos sus proyectos y los segmentos que se han compartido con usted. La lista tiene las siguientes columnas:

| Columna | Descripción |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Seleccione para favorecer a ![Estrella](/help/assets/icons/Star.svg) o para anular el favor de ![EsquemaDeEstrella](/help/assets/icons/StarOutline.svg) en un segmento. Ver [Marcar segmento como favorito](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL Título y descripción]** | Para editar el segmento, seleccione el vínculo del título, que abre el [Generador de filtros](filter-builder.md). Se ha indicado un segmento compartido con ![Compartir](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Vista de datos]** | Las vistas de datos a las que se aplica este segmento. |
| **[!UICONTROL Propietario]** | El propietario del segmento. Como usuario, solo verá los segmentos que le pertenecen o las anotaciones que se han compartido con usted. |
| **[!UICONTROL Etiquetas]** | Las etiquetas de este segmento. |
| **[!UICONTROL Compartido con]** | El número de individuos o grupos con los que compartió el segmento. Seleccione esta opción para abrir el cuadro de diálogo **[!UICONTROL Compartir componente]**. Consulte [Compartir segmentos](filters-share.md) para obtener más información. |
| **[!UICONTROL Fecha de modificación]** | La fecha y la hora de la última modificación del segmento. |
| **[!UICONTROL Utilizado en]** | Muestre dónde se están utilizando los segmentos actualmente y cuántas veces se están utilizando en cada área. <p>Por ejemplo, si el segmento se está utilizando en 40 proyectos y 2 alertas, el valor de esta columna se muestra como [!UICONTROL **42 componentes**].</p> <p>Seleccione el valor de esta columna para ver el desglose de dónde se están utilizando los segmentos (por ejemplo, [!UICONTROL **Proyectos (40)**], [!UICONTROL **Cuadros de resultados móviles (2)**]). Además, puede ver la lista de elementos en los que se utilizan los segmentos. Por ejemplo, para ver la lista de proyectos en los que se están usando, seleccione el vínculo [!UICONTROL **Proyectos (40)**].</p><p>Cada una de las siguientes áreas muestra el número de instancias de segmentos que se están utilizando en esa área:</p>  <ul><li>[!UICONTROL **Proyectos**]<p>Contiene segmentos que se [crearon en el generador de segmentos](/help/components/filters/filter-builder.md#) y que están disponibles para todos los proyectos.</p></li><li>[!UICONTROL **Componentes ad hoc**]<p>Contiene segmentos que se [crearon como segmentos rápidos](/help/components/filters/quick-filters.md) y que solo están disponibles dentro de un solo proyecto.</p></li><li>[!UICONTROL **Proyectos programados**]</li><li>[!UICONTROL **Cuadros de resultados móviles**]</li><li>[!UICONTROL **Anotaciones**]</li><li>[!UICONTROL **Métricas calculadas**]</li><li>[!UICONTROL **Report Builder**]<p>Al seleccionar esta opción, se descarga un archivo CSV con las siguientes columnas de datos:</p><ul><li>Nombre de Report Builder</li><li>Último acceso</li><li>ID usuario de IMS de último acceso</li><li>Nombre de usuario de último acceso</li></ul></li></ul><p>Esta información puede ayudarle a determinar si un componente es valioso para los usuarios de su organización, dónde se utiliza y si debe eliminarse o modificarse.</p><p>Tenga en cuenta lo siguiente cuando vea esta columna:</p><ul><li>Esta columna solo está disponible para los administradores del sistema.</li><li>La columna [!UICONTROL **Utilizado en**] no se muestra de manera predeterminada. Utilice ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para configurar la visualización de esta columna.</li><li>Esta información no incluye el uso de la API o Data Warehouse.</li><li>Si no hay datos en esta columna para un componente determinado pero el componente tiene una fecha de [!UICONTROL **Último uso**], es posible que el componente se haya utilizado en un análisis sin que se haya guardado.</li><li>La información de uso está disponible a partir de septiembre de 2023.</li></ul><p>Puede utilizar el [Diccionario de datos](/help/components/data-dictionary/data-dictionary-overview.md) junto con esta información para ayudarle a realizar un seguimiento y comprender mejor cómo se utilizan los componentes en su organización.</p> |
| **[!UICONTROL Último uso]** | La última vez que se utilizó el segmento. |

Usa ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) para especificar qué columnas deseas mostrar.

### Barra de acciones

Puede realizar acciones en los segmentos mediante el ➋ de barras de acciones. La barra de acciones contiene las siguientes acciones:

| Acción | Descripción |
|---|---|
| ![AgregarCírculo](/help/assets/icons/AddCircle.svg) **[!UICONTROL Añadir]** | Agregue otro segmento con el [Generador de filtros](filter-builder.md). |
| ![Búsqueda](/help/assets/icons/Search.svg) [!UICONTROL *Búsqueda por el título*] | Cuando no haya ningún segmento seleccionado en la lista, busque segmentos utilizando este campo de búsqueda. |
| ![Etiqueta](/help/assets/icons/Label.svg) **[!UICONTROL Etiqueta]** | Etiquete los segmentos seleccionados. En el cuadro de diálogo **[!UICONTROL Segmento de etiqueta]**, seleccione o anule la selección de las etiquetas de los segmentos seleccionados. Seleccione **[!UICONTROL Guardar]** para guardar las etiquetas de los segmentos seleccionados. Consulte [Etiquetar segmentos](/help/components/filters/filters-tag.md) para obtener más información. |
| ![Compartir](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Compartir]** | Compartir los segmentos seleccionados. En el cuadro de diálogo **[!UICONTROL Compartir segmento]**, puede ![Buscar](/help/assets/icons/Search.svg) *Buscar individuos o grupos* o puede seleccionar **[!UICONTROL Organización]** o **[!UICONTROL Grupos]**. Seleccione **[!UICONTROL Guardar]** para guardar los detalles de uso compartido de los segmentos seleccionados. Consulte [Compartir segmentos](filters-share.md) para obtener más información. |
| ![Eliminar](/help/assets/icons/Delete.svg) **[!UICONTROL Eliminar]** | Eliminar los segmentos seleccionados. Se le pedirá una confirmación. |
| ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Cambiar nombre]** | Cambiar el nombre de un solo segmento seleccionado. Cuando se selecciona, puede cambiar el nombre del segmento en línea. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Aprobar]** | Apruebe los segmentos seleccionados. Consulte [Aprobar segmentos](filters-approve.md) para obtener más información. |
| ![Copiar](/help/assets/icons/Copy.svg)  **[!UICONTROL Copiar]** | Copie el segmento seleccionado. Los segmentos nuevos se crean con el mismo nombre y sufijo `(Copy)`. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exportar a CSV]** | Exportar los segmentos a un archivo de `Filters List.csv`. |

### Barra de segmento activa

La ➌ de la barra de segmentos muestra los segmentos activos aplicados desde el panel de segmentos a la lista de segmentos (si los hay). Puede quitar rápidamente un segmento con ![CrossSize75](/help/assets/icons/CrossSize75.svg). Si se especifica más de un segmento, puede quitar todos los segmentos usando **[!UICONTROL Quitar todos]**.

### Panel de segmentos

Puede segmentar la lista de segmentos mediante el ➍ del panel izquierdo ![Segmento](/help/assets/icons/Filter.svg) **[!UICONTROL Filtro]**. El panel de segmentos muestra el tipo de segmento y el número de segmentos que respetan el segmento específico. Seleccione ![Segmento](/help/assets/icons/Filter.svg) para alternar la visualización del panel de segmentos.

Ver [Filtrar la lista de segmentos](filters-filter.md) para obtener más información.
