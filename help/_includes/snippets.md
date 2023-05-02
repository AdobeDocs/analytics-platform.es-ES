---
source-git-commit: a492cbd7801b9523072937ab1d8e707f4b423c72
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 73%

---
# Fragmentos

## Prueba limitada de fase de lanzamiento {#release-limited-testing}

>[!AVAILABILITY]
>
>La funcionalidad descrita en este artículo se encuentra en la fase prueba limitada de la versión y es posible que no esté disponible aún en su entorno. Esta nota se eliminará cuando la funcionalidad esté disponible de forma general. Para obtener información sobre el proceso de versión del Customer Journey Analytics, consulte [Versiones de funcionalidades de Customer Journey Analytics](/help/release-notes/releases.md).

## Sección de prueba limitada de fase de lanzamiento {#release-limited-testing-section}

>[!AVAILABILITY]
>
>La funcionalidad descrita en esta sección se encuentra en la fase prueba limitada de la versión y es posible que no esté disponible aún en su entorno. Esta nota se eliminará cuando la funcionalidad esté disponible de forma general. Para obtener información sobre el proceso de versión del Customer Journey Analytics, consulte [Versiones de funcionalidades de Customer Journey Analytics](/help/release-notes/releases.md).

## Criterios de filtro del diccionario de datos {#dd-filter-criteria}

1. (Opcional) Seleccione el icono **Filtrar** ![del diccionario de datos](/help/components/data-dictionary/assets/data-dictionary-filter-icon.png) y, a continuación, cualquiera de las siguientes opciones para filtrar la lista de componentes:

   | Opción | Función |
   |---------|----------|
   | [!UICONTROL **Aprobado**] | Mostrar solo los componentes marcados como Aprobado por un administrador. |
   | [!UICONTROL **Favoritos**] | Mostrar solo los componentes que se encuentran en la lista de Favoritos. Para obtener información acerca de cómo añadir componentes a la lista de favoritos, consulte [Información general sobre componentes](/help/components/overview.md). |
   | [!UICONTROL **Dimensiones**] | Mostrar solo los componentes que son dimensiones. (Esta opción también está disponible en la pestaña [!UICONTROL **Filtros rápidos**] al acceder por primera vez al diccionario de datos). |
   | [!UICONTROL **Métricas**] | Mostrar solo los componentes que son métricas. (Esta opción también está disponible en la pestaña [!UICONTROL **Filtros rápidos**] al acceder por primera vez al diccionario de datos). |
   | [!UICONTROL **Filtros**] | Mostrar solo los componentes que son Filtros. (Esta opción también está disponible en la pestaña [!UICONTROL **Filtros rápidos**] al acceder por primera vez al diccionario de datos). <!--this is Filters in CJA--> |
   | [!UICONTROL **Intervalos de fechas**] | Mostrar solo los componentes que son intervalos de fechas. (Esta opción también está disponible en la pestaña [!UICONTROL **Filtros rápidos**] al acceder por primera vez al diccionario de datos). |
   | [!UICONTROL **Mostrar todo**] | Mostrar todos los componentes. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **No aprobado**] | Mostrar solo los componentes que aún no están marcados como Aprobado por un administrador. Como administrador, resulta útil a la hora de identificar los componentes que requieren su revisión y aprobación. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **Falta la descripción**] | Mostrar solo los componentes que aún no tienen descripción en el campo Descripción. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **Mostrar duplicados**] | Mostrar solo los componentes que tengan el mismo nombre o la misma descripción que los de otro componente en el grupo de informes seleccionado. Esto incluye los componentes que crea, así como los proporcionados por el Adobe. Los nombres o las descripciones deben coincidir de forma exacta para que se muestren como duplicados. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **No hay datos recientes**] | Mostrar solo los componentes que no han recopilado ningún dato en los últimos 90 días. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **Creado por Adobe**] <!-- I don't see this option--> | Mostrar solo los componentes creados por Adobe. No se muestran los componentes creados por un administrador u otro usuario de su organización. |

   {style="table-layout:auto"}

## Información del componente del diccionario de datos {#dd-component-information}

| Opción | Función |
|---------|----------|
| [!UICONTROL **Aprobado**] | <p>Indica que el administrador revisó y aprobó el componente.</p><p>Los administradores ven una opción para [!UICONTROL **Desaprobar**]. Al seleccionar esta opción, el componente se marca como &quot;No aprobado&quot; para los usuarios.</p> |
| [!UICONTROL **No aprobado**] | <p>Indica que el administrador aún no ha revisado y aprobado el componente.</p><p>Los administradores ven la opción para [!UICONTROL **Aprobar**]. Al seleccionar esta opción, el componente se marca como “Aprobado” para los usuarios.</p> |
| [!UICONTROL **Descripción**] | Describe la función deseada del componente. (El administrador de Analytics agrega esta información, tal como se describe en [Adición de descripciones de componentes](/help/components/add-component-descriptions.md)). |
| [!UICONTROL **Usado frecuentemente con**] | <p>Muestra los componentes que se utilizan con más frecuencia con el componente que está viendo.</p><p>Se muestran hasta 5 componentes en los 5 tipos de componentes principales: Métrica, Métrica calculada, Dimension, Filtro e Intervalo de fechas.</p><p>Esta lista se basa en los datos de los últimos 90 días. Solo se muestran los componentes a los que tiene acceso de vista.</p><p>Los administradores pueden depurar los componentes que los usuarios ven en esta sección al seleccionar los componentes deseados en los campos desplegables [!UICONTROL **Incluir siempre**] y [!UICONTROL **Excluir siempre**]. Antes de depurar los componentes que ven los usuarios, aplique primero la variable **Mostrar todo** para asegurarse de que está viendo componentes que no se han compartido con usted y que podría haber sido agregados por otro administrador.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **Similar a**] | <p>Muestra componentes con nombres similares al componente que está viendo.</p><p>Se muestran hasta 5 componentes en los 5 tipos de componentes principales: Métrica, Métrica calculada, Dimension, Filtro e Intervalo de fechas.</p><p>Solo se muestran los componentes a los que tiene acceso de vista.</p><p>Aquí se mostrará cualquier componente duplicado del grupo de informes. Los administradores de Analytics deben identificar y eliminar todos los componentes duplicados, tal como se describe en [Monitorización del estado del diccionario de datos](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Los administradores pueden depurar los componentes que los usuarios ven en esta sección seleccionando los componentes deseados en los campos desplegables [!UICONTROL **Incluir siempre**] y [!UICONTROL **Excluir siempre**]. Antes de depurar los componentes que ven los usuarios, aplique primero la variable **Mostrar todo** para asegurarse de que está viendo componentes que no se han compartido con usted y que podría haber sido agregados por otro administrador.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**Nota:** Actualmente, la sección **Similar a** incluye solo los componentes que crea y no los proporcionados por Adobe. En una versión futura se agregarán componentes proporcionados por Adobe.</p> |
| [!UICONTROL **Etiquetas**] | Muestra todas las etiquetas aplicadas al componente. Los usuarios con acceso de administrador pueden añadir etiquetas al editar el componente. |
| [!UICONTROL **Tipo de componente**] | Muestra el tipo de componente que es, ya sea un Dimension, una métrica, un filtro o un intervalo de fechas. |
| [!UICONTROL **Creado por**] | Muestra el nombre del usuario que ha creado el componente. |
| [!UICONTROL **Vista previa**] | Muestra una vista previa del aspecto del componente en Analysis Workspace. |
| [!UICONTROL **Fecha de la última modificación**] | Muestra el día en que se modificó por última vez el componente. Esta sección se muestra al ver filtros, métricas, métricas calculadas e intervalos de fechas. |

{style="table-layout:auto"}