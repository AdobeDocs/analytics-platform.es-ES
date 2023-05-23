---
description: El diccionario de datos de Analysis Workspace permite a los usuarios catalogar y seguir los distintos componentes de Analysis Workspace, incluido su uso previsto, cuáles están aprobados, cuáles son duplicados, etc.
title: Edición de entradas en el diccionario de datos
feature: Components
role: Admin
exl-id: 2d232811-e34a-4667-819c-cbe2a3e72702
source-git-commit: ec8760cf9984d4e962992f613c4a58a52fa29d47
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 45%

---

# Edición de entradas de componentes en el diccionario de datos

Los administradores de Customer Journey Analytics pueden editar las entradas de los componentes del diccionario de datos para una vista de datos determinada. Todos los usuarios de la vista de datos pueden ver los cambios realizados.

Para editar un componente en el diccionario de datos:

1. Vaya al proyecto de Analysis Workspace que contiene el componente que desea editar.

1. Seleccione el icono del **Diccionario de datos** en el carril izquierdo de Analysis Workspace. (Las formas alternativas de acceder al diccionario de datos se describen en “Acceso al diccionario de datos” en [Información general del diccionario de datos](/help/components/data-dictionary/data-dictionary-overview.md)).

Se muestra la ventana Diccionario de datos.

![Vista de administrador del diccionario de datos](assets/data-dictionary-admin.png)

1. Asegúrese de que está seleccionada la vista de datos correcta en el menú desplegable. De forma predeterminada, se muestra la vista de datos en la que ya se encuentra.

1. (Opcional) En el campo de búsqueda, empiece a escribir el nombre del componente que desea editar.

El tipo de componente se puede identificar mediante colores e iconos. **Dimension** ![Icono de Dimension](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) son naranjas, **Segmentos** ![Icono de segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) son azules, **Intervalos de fechas** ![Icono de intervalo de fecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) son morados y **Métricas** ![Icono de métrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) son verdes. El Adobe de métricas indica una plantilla de métrica calculada o de segmento, y el icono de la calculadora ![Icono Calculadora](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indicó una métrica calculada que creó un administrador de Analytics en su organización.

{{dd-filter-criteria}}

1. (Opcional) Seleccione la **Ordenar** icono ![Icono Ordenar componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), luego seleccione cualquiera de las siguientes opciones de filtro para ordenar la lista de componentes:

{{components-sort-options}}

1. En la lista de componentes, seleccione el componente que desea editar.

1. Seleccione el icono **Editar** ![icono Editar del diccionario de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) junto al nombre del componente.

1. Edite cualquiera de la siguiente información acerca del componente:

{{dd-component-information}}

1. Haga clic en el icono **Guardar** ![icono Guardar del diccionario de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg) para guardar los cambios.
