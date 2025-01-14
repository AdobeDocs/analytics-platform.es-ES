---
description: El diccionario de datos de Analysis Workspace permite a los usuarios catalogar y seguir los distintos componentes de Analysis Workspace, incluido su uso previsto, cuáles están aprobados, cuáles son duplicados, etc.
title: Editar entradas de componente
feature: Components
role: Admin
exl-id: 2d232811-e34a-4667-819c-cbe2a3e72702
source-git-commit: 8c975a37e6772ab3bae1f86c4ccad27ebf0596cc
workflow-type: tm+mt
source-wordcount: '1195'
ht-degree: 62%

---

# Editar entradas de componente

Los administradores de Customer Journey Analytics pueden editar las entradas de los componentes del diccionario de datos para una vista de datos determinada. Todos los usuarios de la vista de datos pueden ver los cambios realizados.

Para editar un componente en el diccionario de datos:

1. Vaya al proyecto de Analysis Workspace que contiene el componente que desea editar.

1. Seleccione el icono **Diccionario de datos** en el panel de botones de Analysis Workspace. (Las formas alternativas de acceder al diccionario de datos se describen en “Acceso al diccionario de datos” en [Información general del diccionario de datos](/help/components/data-dictionary/data-dictionary-overview.md)).

   Se muestra la ventana Diccionario de datos.

   ![Vista del administrador del diccionario de datos que muestra el estado del diccionario](assets/data-dictionary-admin.png)

1. Asegúrese de que está seleccionada la vista de datos correcta en el menú desplegable. De forma predeterminada, se muestra la vista de datos en la que ya se encuentra.

1. (Opcional) En el campo de búsqueda, empiece a escribir el nombre del componente que desea editar.

   El tipo de componente se puede identificar mediante colores e iconos. **Icono de Dimension** ![Dimension](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) es naranja, **Filtros** ![Icono de segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) es azul, **Intervalos de fecha** ![Icono de intervalo de fecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) es púrpura y **Métricas** ![Icono de métrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) es verde. El Adobe de la calculadora ![Calculator icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indica una métrica calculada creada por un administrador de Analytics de su organización.

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

1. (Opcional) Seleccione el icono de **Ordenar** ![icono de Ordenar componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) y, a continuación, seleccione cualquiera de las siguientes opciones de filtro para ordenar la lista de componentes:

{{components-sort-options}}

1. En la lista de componentes, seleccione el componente que desea editar.

1. Seleccione el icono **Editar** ![icono Editar del diccionario de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) junto al nombre del componente.

1. Edite cualquiera de la siguiente información acerca del componente:

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

1. Haga clic en el icono **Guardar** ![icono Guardar del diccionario de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg) para guardar los cambios.
