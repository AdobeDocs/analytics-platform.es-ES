---
description: El diccionario de datos de Analysis Workspace permite a los usuarios catalogar y seguir los distintos componentes de Analysis Workspace, incluido su uso previsto, cuáles están aprobados, cuáles son duplicados, etc.
title: Edición de entradas en el diccionario de datos
feature: Components
role: Admin
exl-id: 2d232811-e34a-4667-819c-cbe2a3e72702
source-git-commit: 74ec307b878b77a40ef1f5dbf54f2b59d88b41fe
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 58%

---

# Edición de entradas de componentes en el diccionario de datos

Los administradores de Customer Journey Analytics pueden editar entradas de componentes en el diccionario de datos para una vista de datos determinada. Todos los usuarios de la vista de datos pueden ver los cambios realizados.

Para editar un componente en el diccionario de datos:

1. Vaya al proyecto de Analysis Workspace que contiene el componente que desea editar.

1. Seleccione el icono del **Diccionario de datos** en el carril izquierdo de Analysis Workspace. (Las formas alternativas de acceder al diccionario de datos se describen en “Acceso al diccionario de datos” en [Información general del diccionario de datos](/help/components/data-dictionary/data-dictionary-overview.md)).

   Se muestra la ventana Diccionario de datos.

   ![Vista de administrador del diccionario de datos](assets/data-dictionary-admin.png)

1. Asegúrese de que la vista de datos correcta está seleccionada en el menú desplegable. De forma predeterminada, se muestra la vista de datos en la que ya se encuentra.

1. (Opcional) En el campo de búsqueda, empiece a escribir el nombre del componente que desea editar.

   El tipo de componente se puede identificar mediante el color y el icono. **Dimension** ![Dimension](assets/dimension-icon.png) son naranjas, **Segmentos** ![Icono de segmento](assets/segment-icon.png) son azules, **Intervalos de fechas** ![Icono de intervalo de fechas](assets/date-range-icon.png) son púrpura y **Métricas** ![Icono de métrica](assets/default-metric-icon.png) son verdes. El icono del Adobe ![Icono de Adobe](assets/default-calc-metric-icon.png) indica una plantilla de métrica calculada o una plantilla de segmento y el icono de la calculadora ![Icono de calculadora](assets/calculated-metric-icon-created.png) indica una métrica calculada que fue creada por un administrador de Analytics en su organización.

{{dd-filter-criteria}}

1. En la lista de componentes, seleccione el componente que desea editar.

1. Seleccione el icono **Editar** ![icono Editar del diccionario de datos](assets/data-dictionary-edit-icon.png) junto al nombre del componente.

1. Edite cualquiera de la siguiente información acerca del componente:

   {{dd-component-information}}

1. Haga clic en el icono **Guardar** ![icono Guardar del diccionario de datos](assets/data-dictionary-save-icon.png) para guardar los cambios.
