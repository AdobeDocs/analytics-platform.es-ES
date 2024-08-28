---
source-git-commit: d903745e105edb11ef6f43b6137e1e03d43e5e07
workflow-type: tm+mt
source-wordcount: '1253'
ht-degree: 58%

---
# Fragmentos

## Prueba limitada de fase de lanzamiento {#release-limited-testing}

>[!AVAILABILITY]
>
>La funcionalidad descrita en este artículo se encuentra en la fase prueba limitada de la versión y es posible que no esté disponible aún en su entorno. Esta nota se eliminará cuando la funcionalidad esté disponible de forma general. Para obtener información acerca del proceso de lanzamiento de Customer Journey Analytics, consulte [lanzamientos de características de Customer Journey Analytics](/help/release-notes/releases.md).

## Sección de prueba limitada de fase de lanzamiento {#release-limited-testing-section}

>[!AVAILABILITY]
>
>La funcionalidad descrita en esta sección se encuentra en la fase prueba limitada de la versión y es posible que no esté disponible aún en su entorno. Esta nota se eliminará cuando la funcionalidad esté disponible de forma general. Para obtener información acerca del proceso de lanzamiento de Customer Journey Analytics, consulte [lanzamientos de características de Customer Journey Analytics](/help/release-notes/releases.md).

## Seleccionar paquete {#select-package}

>[!NOTE]
>
>Debe tener el paquete **Select** o superior para poder usar la funcionalidad descrita en esta sección. Póngase en contacto con el administrador si no sabe qué paquete de Customer Journey Analytics tiene.

## Paquete Prime {#prime-package}

>[!NOTE]
>
>Debe tener el paquete **Prime** o superior para poder usar la funcionalidad descrita en esta sección. Póngase en contacto con el administrador si no sabe qué paquete de Customer Journey Analytics tiene.

## Paquete Ultimate {#ultimate-package}

>[!NOTE]
>
>Debe tener el paquete **Ultimate** para poder usar la funcionalidad descrita en esta sección. Póngase en contacto con el administrador si no sabe qué paquete de Customer Journey Analytics tiene.


## Criterios de filtro del diccionario de datos {#dd-filter-criteria}

1. (Opcional) Seleccione el icono **Filtrar** ![del diccionario de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) y, a continuación, cualquiera de las siguientes opciones para filtrar la lista de componentes:

   | Opción | Función |
   |---------|----------|
   | [!UICONTROL **Aprobado**] | Mostrar solo los componentes marcados como Aprobado por un administrador. |
   | [!UICONTROL **Favoritos**] | Mostrar solo los componentes que se encuentran en la lista de Favoritos. Para obtener información acerca de cómo añadir componentes a la lista de favoritos, consulte [Información general sobre componentes](/help/components/overview.md). |
   | [!UICONTROL **Dimensiones**] | Mostrar solo los componentes que son dimensiones. (Esta opción también está disponible en la pestaña [!UICONTROL **Filtros rápidos**] al acceder por primera vez al diccionario de datos). |
   | [!UICONTROL **Métricas**] | Mostrar solo los componentes que son métricas. (Esta opción también está disponible en la pestaña [!UICONTROL **Filtros rápidos**] al acceder por primera vez al diccionario de datos). |
   | [!UICONTROL **Filtros**] | Mostrar solo los componentes que son filtros. (Esta opción también está disponible en la pestaña [!UICONTROL **Filtros rápidos**] al acceder por primera vez al diccionario de datos). <!--this is Filters in Customer Journey Analytics--> |
   | [!UICONTROL **Intervalos de fechas**] | Mostrar solo los componentes que son intervalos de fechas. (Esta opción también está disponible en la pestaña [!UICONTROL **Filtros rápidos**] al acceder por primera vez al diccionario de datos). |
   | [!UICONTROL **Mostrar todo**] | Mostrar todos los componentes. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **No aprobado**] | Mostrar solo los componentes que aún no están marcados como Aprobado por un administrador. Como administrador, resulta útil a la hora de identificar los componentes que requieren su revisión y aprobación. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **Falta la descripción**] | Mostrar solo los componentes que aún no tienen descripción en el campo Descripción. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **Mostrar duplicados**] | Mostrar solo los componentes que tienen el mismo nombre o la misma descripción que otro componente en la vista de datos seleccionada. Esto incluye tanto los componentes que crea como los que proporciona Adobe. Los nombres o las descripciones deben coincidir de forma exacta para mostrarlos como duplicados. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **No hay datos recientes**] | Mostrar solo los componentes que no han recopilado ningún dato en los últimos 90 días. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **Creado por el Adobe**] <!-- I don't see this option--> | Mostrar solo los componentes creados por Adobe. No se muestran los componentes creados por un administrador u otro usuario de su organización. |

   {style="table-layout:auto"}

## Información del componente del diccionario de datos {#dd-component-information}

| Opción | Función |
|---------|----------|
| [!UICONTROL **Aprobado**] | <p>Indica que el administrador revisó y aprobó el componente.</p><p>Los administradores ven una opción para [!UICONTROL **Desaprobar**]. Al seleccionar esta opción, se marca el componente como &quot;No aprobado&quot; para los usuarios.</p> |
| [!UICONTROL **No aprobado**] | <p>Indica que el administrador aún no ha revisado y aprobado el componente.</p><p>Los administradores ven la opción para [!UICONTROL **Aprobar**]. Al seleccionar esta opción, el componente se marca como “Aprobado” para los usuarios.</p> |
| [!UICONTROL **Descripción**] | Describe la función deseada del componente. (El administrador de Analytics agrega esta información, tal como se describe en [Adición de descripciones de componentes](/help/components/add-component-descriptions.md)). |
| [!UICONTROL **Usado frecuentemente con**] | <p>Muestra los componentes que se utilizan con más frecuencia con el componente que está viendo.</p><p>Se muestran hasta 5 componentes en los 5 tipos de componentes principales: Métrica, Métrica calculada, Dimension, Filtro e Intervalo de fechas.</p><p>Esta lista se basa en los datos de los últimos 90 días. Solo se muestran los componentes a los que tiene acceso de vista.</p><p>Los administradores pueden depurar los componentes que los usuarios ven en esta sección al seleccionar los componentes deseados en los campos desplegables [!UICONTROL **Incluir siempre**] y [!UICONTROL **Excluir siempre**]. Antes de depurar los componentes que ven los usuarios, aplique el filtro **Mostrar todo** para asegurarse de que ve los componentes que no se han compartido con usted y que otro administrador podría haber agregado.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **Similar a**] | <p>Muestra componentes con nombres similares al componente que está viendo.</p><p>Se muestran hasta 5 componentes en los 5 tipos de componentes principales: Métrica, Métrica calculada, Dimension, Filtro e Intervalo de fechas.</p><p>Solo se muestran los componentes a los que tiene acceso de vista.</p><p>Aquí se mostrará cualquier componente duplicado de la vista de datos. Los administradores de Analytics deben identificar y eliminar todos los componentes duplicados, tal como se describe en [Monitorización del estado del diccionario de datos](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Los administradores pueden depurar los componentes que los usuarios ven en esta sección seleccionando los componentes deseados en los campos desplegables [!UICONTROL **Incluir siempre**] y [!UICONTROL **Excluir siempre**]. Antes de depurar los componentes que ven los usuarios, aplique el filtro **Mostrar todo** para asegurarse de que ve los componentes que no se han compartido con usted y que otro administrador podría haber agregado.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**Nota:** Actualmente, la sección **Similar a** incluye solo los componentes que crea y no los proporcionados por Adobe. En una versión futura se agregarán componentes proporcionados por Adobe.</p> |
| [!UICONTROL **Compatibilidad del producto**] | Indica en qué Customer Journey Analytics se puede utilizar esta métrica calculada. <p>Los valores posibles son:</p><ul><li>[!UICONTROL **En cualquier lugar del Customer Journey Analytics**]: la métrica calculada se puede usar en todos los Customer Journey Analytics, incluso en Analysis Workspace, Report Builder, etc.</li><li>[!UICONTROL **En cualquier lugar del Customer Journey Analytics (excluida la experimentación)**]: la métrica calculada se puede usar en todo el Customer Journey Analytics, excepto en el panel Experimentación.</li> <p>Para obtener información acerca de los criterios que determinan si se puede usar una métrica calculada con experimentación, consulte [Usar métricas calculadas en el panel Experimentación](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel) en [Panel de experimentación](/help/analysis-workspace/c-panels/experimentation.md).</p></ul> |
| [!UICONTROL **Etiquetas**] | Muestra todas las etiquetas aplicadas al componente. Los usuarios con acceso de administrador pueden añadir etiquetas al editar el componente. |
| [!UICONTROL **Tipo de componente**] | Muestra el tipo de componente que es, ya sea un Dimension, una métrica, un filtro o un intervalo de fechas. |
| [!UICONTROL **Creado por**] | Muestra el nombre del usuario que ha creado el componente. |
| [!UICONTROL **Vista previa**] | Muestra una vista previa del aspecto del componente en Analysis Workspace. |
| [!UICONTROL **Fecha de la última modificación**] | Muestra el día en que se modificó por última vez el componente. Esta sección se muestra al ver filtros, métricas, métricas calculadas e intervalos de fechas. |

{style="table-layout:auto"}

## Opciones de ordenación de componentes {#components-sort-options}

| Opción | Función |
|---------|----------|
| [!UICONTROL **Recomendado**] | Ordena los componentes con los recomendados en la parte superior de la lista. Los componentes que usted u otras personas de su organización utilizan con más frecuencia y más recientemente aparecen en la parte superior de la lista. |
| [!UICONTROL **Alfabético**] | Ordena los componentes alfabéticamente. |
| [!UICONTROL **Categórica**] | Ordena los componentes según su tipo (dimensión, métrica, filtro, intervalo de fechas). |

{style="table-layout:auto"}

## Comparación del tiempo {#apply-time-comparison}

Puede comparar el período de tiempo actual con un período de tiempo anterior. Si selecciona una opción en este menú, cada punto de datos recibe un homólogo con líneas punteadas de color similar. Este homólogo representa la misma métrica en el intervalo de fechas anterior seleccionado. Al establecer esta opción, se duplica el número de elementos del gráfico y de las filas de la tabla.

Las opciones de comparación de tiempo disponibles incluyen el periodo anterior, 13 semanas antes, 52 semanas antes y un intervalo de fechas personalizado. Si selecciona Intervalo de fechas personalizado, aparecen opciones adicionales para permitirle seleccionar el número y la granularidad. Si selecciona Ninguno, se elimina la comparación de fechas.
