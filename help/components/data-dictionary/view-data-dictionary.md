---
description: El diccionario de datos de Analysis Workspace permite a los usuarios catalogar y seguir los distintos componentes de Analysis Workspace, incluido su uso previsto, cuáles están aprobados, cuáles son duplicados, etc.
title: Ver información del componente
feature: Components
role: User, Admin
exl-id: 1e538679-12e0-487c-917f-2ff2f1cc8436
source-git-commit: 4bfa32ba3a7902d31edefab17a00206f922a8382
workflow-type: tm+mt
source-wordcount: '1217'
ht-degree: 54%

---

# Ver información del componente

El diccionario de datos permite ver información acerca de un componente, incluida su descripción, componentes similares, otros componentes con los que se utiliza con frecuencia, etc.

Para ver información acerca de un componente en el diccionario de datos:

1. Vaya al proyecto de Analysis Workspace que contiene el componente que desea ver.

1. Seleccione el icono [!UICONTROL **Diccionario de datos**] en el panel izquierdo de Analysis Workspace. (Las formas alternativas de acceder al diccionario de datos se describen en “Acceso al diccionario de datos” en [Información general del diccionario de datos](/help/components/data-dictionary/data-dictionary-overview.md)).

   Se muestra la ventana Diccionario de datos.

   ![Ventana del diccionario de datos que muestra segmentos rápidos para dimensiones, métricas, segmentos e intervalos de fechas](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Asegúrese de que la vista de datos que contiene el componente que desea ver está seleccionada en el menú desplegable. De forma predeterminada, se muestra la vista de datos en la que ya se encuentra.

1. (Opcional) En el campo de búsqueda, empiece a escribir el nombre del componente que desea ver.

   El tipo de componente se puede identificar mediante colores e iconos. **Dimensiones** ![Icono de Dimension](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) son de color naranja, **Filtros** ![Icono de segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) de color azul, **Intervalos de fecha** ![Icono de intervalo de fecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) de color púrpura y **Métricas** ![Icono de métrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) de color verde. El icono de Adobe ![Adobe](assets/default-calc-metric-icon.png) indica una plantilla de métrica calculada o de segmento, y el icono de calculadora ![Calculator icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indica una métrica calculada que creó un administrador de Analytics en su organización.

1. (Opcional) Seleccione el icono **Filtro** ![Icono del filtro del diccionario de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) y, a continuación, seleccione cualquiera de las siguientes opciones de segmento para segmentar la lista de componentes:

   | Opción | Función |
   |---------|----------|
   | [!UICONTROL **Aprobado**] | Mostrar solo los componentes marcados como Aprobado por un administrador. |
   | [!UICONTROL **Favoritos**] | Mostrar solo los componentes que se encuentran en la lista de Favoritos. Para obtener información acerca de cómo añadir componentes a la lista de favoritos, consulte [Información general sobre componentes](/help/components/overview.md). |
   | [!UICONTROL **Dimensiones**] | Mostrar solo los componentes que son dimensiones. (Esta opción también está disponible en la pestaña [!UICONTROL **Segmentos rápidos**] al acceder por primera vez al diccionario de datos). |
   | [!UICONTROL **Métricas**] | Mostrar solo los componentes que son métricas. (Esta opción también está disponible en la pestaña [!UICONTROL **Segmentos rápidos**] al acceder por primera vez al diccionario de datos). |
   | [!UICONTROL **Filtros**] | Mostrar solo los componentes que son filtros. (Esta opción también está disponible en la ficha [!UICONTROL **Segmentos rápidos**] al acceder por primera vez al diccionario de datos). <!--this is Filters in Customer Journey Analytics--> |
   | [!UICONTROL **Intervalos de fechas**] | Mostrar solo los componentes que son intervalos de fechas. (Esta opción también está disponible en la pestaña [!UICONTROL **Segmentos rápidos**] al acceder por primera vez al diccionario de datos). |
   | [!UICONTROL **Mostrar todo**] | Mostrar todos los componentes. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **No aprobado**] | Mostrar solo los componentes que aún no están marcados como Aprobado por un administrador. Como administrador, resulta útil a la hora de identificar los componentes que requieren su revisión y aprobación. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **Falta la descripción**] | Mostrar solo los componentes que aún no tienen descripción en el campo Descripción. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **Mostrar duplicados**] | Mostrar solo los componentes que tienen el mismo nombre o la misma descripción que otro componente en la vista de datos seleccionada. Esto incluye tanto los componentes que crea como los que proporciona Adobe. Los nombres o las descripciones deben coincidir de forma exacta para mostrarlos como duplicados. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **No hay datos recientes**] | Mostrar solo los componentes que no han recopilado ningún dato en los últimos 90 días. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **Creado por Adobe**] <!-- I don't see this option--> | Mostrar solo los componentes creados por Adobe. No se muestran los componentes creados por un administrador u otro usuario de su organización. |

   {style="table-layout:auto"}

1. (Opcional) Seleccione el icono **Sort** ![Sort components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) y, a continuación, seleccione cualquiera de las siguientes opciones de segmento para ordenar la lista de componentes:

   {{components-sort-options}}

1. En la lista de componentes, seleccione el componente que desee ver.

   Se muestra la siguiente información acerca del componente:

   | Opción | Función |
   |---------|----------|
   | [!UICONTROL **Aprobado**] | <p>Indica que el administrador revisó y aprobó el componente.</p><p>Los administradores ven una opción para [!UICONTROL **Desaprobar**]. Al seleccionar esta opción, se marca el componente como &quot;No aprobado&quot; para los usuarios.</p> |
   | [!UICONTROL **No aprobado**] | <p>Indica que el administrador aún no ha revisado y aprobado el componente.</p><p>Los administradores ven la opción para [!UICONTROL **Aprobar**]. Al seleccionar esta opción, el componente se marca como “Aprobado” para los usuarios.</p> |
   | [!UICONTROL **Etiqueta de contexto**] | Este campo solo aparece si la etiqueta de contexto del componente se ha actualizado en la vista de datos. <p>Para obtener más información, consulte [Configuración de componentes](/help/data-views/component-settings/overview.md). </p> |
   | [!UICONTROL **Descripción**] | Describe la función deseada del componente. (El administrador de Analytics agrega esta información, tal como se describe en [Adición de descripciones de componentes](/help/components/add-component-descriptions.md)). |
   | [!UICONTROL **Usado frecuentemente con**] | <p>Muestra los componentes que se utilizan con más frecuencia con el componente que está viendo.</p><p>Se muestran hasta 5 componentes en los 5 tipos de componentes principales: Métrica, Métrica calculada, Dimension, Filtro e Intervalo de fechas.</p><p>Esta lista se basa en los datos de los últimos 90 días. Solo se muestran los componentes a los que tiene acceso de vista.</p><p>Los administradores pueden depurar los componentes que los usuarios ven en esta sección al seleccionar los componentes deseados en los campos desplegables [!UICONTROL **Incluir siempre**] y [!UICONTROL **Excluir siempre**]. Antes de depurar los componentes que ven los usuarios, aplique el segmento **Mostrar todo** para asegurarse de que ve los componentes que no se han compartido con usted y que otro administrador podría haber agregado.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p> |
   | [!UICONTROL **Similar a**] | <p>Muestra componentes con nombres similares al componente que está viendo.</p><p>Se muestran hasta 5 componentes en los 5 tipos de componentes principales: Métrica, Métrica calculada, Dimension, Filtro e Intervalo de fechas.</p><p>Solo se muestran los componentes a los que tiene acceso de vista.</p><p>Aquí se mostrará cualquier componente duplicado de la vista de datos. Los administradores de Analytics deben identificar y eliminar todos los componentes duplicados, tal como se describe en [Monitorización del estado del diccionario de datos](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Los administradores pueden depurar los componentes que los usuarios ven en esta sección seleccionando los componentes deseados en los campos desplegables [!UICONTROL **Incluir siempre**] y [!UICONTROL **Excluir siempre**]. Antes de depurar los componentes que ven los usuarios, aplique el segmento **Mostrar todo** para asegurarse de que ve los componentes que no se han compartido con usted y que otro administrador podría haber agregado.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p><p>**Nota:** Actualmente, la sección **Similar a** incluye solo los componentes que crea y no los proporcionados por Adobe. En una versión futura se agregarán componentes proporcionados por Adobe.</p> |
   | [!UICONTROL **Compatibilidad del producto**] | Indica en qué parte de Customer Journey Analytics se puede utilizar esta métrica calculada. <p>Los valores posibles son:</p><ul><li>[!UICONTROL **En cualquier lugar de Customer Journey Analytics**]: la métrica calculada se puede usar en todo Customer Journey Analytics, incluso en Analysis Workspace, Report Builder, etc.</li><li>[!UICONTROL **En cualquier lugar de Customer Journey Analytics (excepto en experimentación)**]: la métrica calculada se puede usar en todo Customer Journey Analytics, excepto en el panel Experimentación.</li> <p>Para obtener información acerca de los criterios que determinan si se puede usar una métrica calculada con experimentación, consulte [Usar métricas calculadas en el panel Experimentación](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel) en [Panel de experimentación](/help/analysis-workspace/c-panels/experimentation.md).</p></ul> |
   | [!UICONTROL **Etiquetas**] | Muestra todas las etiquetas aplicadas al componente. Los usuarios con acceso de administrador pueden añadir etiquetas al editar el componente. |
   | [!UICONTROL **Tipo de componente**] | Enumera el tipo de componente que es, ya sea una Dimension, una métrica, un filtro o un intervalo de fechas. |
   | [!UICONTROL **Creado por**] | Muestra el nombre del usuario que ha creado el componente. |
   | [!UICONTROL **Vista previa**] | Muestra una vista previa del aspecto del componente en Analysis Workspace. |
   | [!UICONTROL **Fecha de la última modificación**] | Muestra el día en que se modificó por última vez el componente. Esta sección se muestra al ver filtros, métricas, métricas calculadas e intervalos de fechas. |

   {style="table-layout:auto"}

1. (Opcional) Arrastre un componente del diccionario de datos a Analysis Workspace.
