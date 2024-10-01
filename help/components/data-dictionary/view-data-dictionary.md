---
description: El diccionario de datos de Analysis Workspace permite a los usuarios catalogar y seguir los distintos componentes de Analysis Workspace, incluido su uso previsto, cuáles están aprobados, cuáles son duplicados, etc.
title: Visualización del diccionario de datos
feature: Components
role: User, Admin
exl-id: 1e538679-12e0-487c-917f-2ff2f1cc8436
source-git-commit: de04792035aa7c235751019ee9f9fe5b74b9b102
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 75%

---

# Visualización de información de componentes en el diccionario de datos

El diccionario de datos permite ver información acerca de un componente, incluida su descripción, componentes similares, otros componentes con los que se utiliza con frecuencia, etc.

Para ver información acerca de un componente en el diccionario de datos:

1. Vaya al proyecto de Analysis Workspace que contiene el componente que desea ver.

1. Seleccione el icono [!UICONTROL **Diccionario de datos**] en el panel izquierdo de Analysis Workspace. (Las formas alternativas de acceder al diccionario de datos se describen en “Acceso al diccionario de datos” en [Información general del diccionario de datos](/help/components/data-dictionary/data-dictionary-overview.md)).

   Se muestra la ventana Diccionario de datos.

   ![Ventana del diccionario de datos con filtros rápidos para Dimension, métricas, segmentos e intervalos de fechas](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Asegúrese de que la vista de datos que contiene el componente que desea ver está seleccionada en el menú desplegable. De forma predeterminada, se muestra la vista de datos en la que ya se encuentra.

1. (Opcional) En el campo de búsqueda, empiece a escribir el nombre del componente que desea ver.

   El tipo de componente se puede identificar mediante colores e iconos. **Icono de Dimension** ![Dimension](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) es naranja, **Filtros** ![Icono de segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) es azul, **Intervalos de fecha** ![Icono de intervalo de fecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) es púrpura y **Métricas** ![Icono de métrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) es verde. El icono de Adobe ![icono de Adobe](assets/default-calc-metric-icon.png) indica una plantilla de métricas calculadas o de filtros y el icono de calculadora ![icono de calculadora](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indica una métrica calculada creada por un administrador de Analytics de su organización.

{{dd-filter-criteria}}

1. (Opcional) Seleccione el icono de **Ordenar** ![icono de Ordenar componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) y, a continuación, seleccione cualquiera de las siguientes opciones de filtro para ordenar la lista de componentes:

   {{components-sort-options}}

1. En la lista de componentes, seleccione el componente que desee ver.

   Se muestra la siguiente información acerca del componente:

   {{dd-component-information}}

1. (Opcional) Arrastre un componente del diccionario de datos a Analysis Workspace.
