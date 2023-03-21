---
description: El diccionario de datos de Analysis Workspace permite a los usuarios catalogar y seguir los distintos componentes de Analysis Workspace, incluido su uso previsto, cuáles están aprobados, cuáles son duplicados, etc.
title: Visualización del diccionario de datos
feature: Components
role: User, Admin
source-git-commit: 733e0e358aa34ce126687f01ffb6d89f9b0c4210
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 71%

---

# Visualización de información de componentes en el diccionario de datos

El diccionario de datos permite ver información acerca de un componente, incluida su descripción, componentes similares, otros componentes con los que se utiliza con frecuencia, etc.

Para ver información acerca de un componente en el diccionario de datos:

1. Vaya al proyecto de Analysis Workspace que contiene el componente que desea ver.

1. Seleccione el icono del [!UICONTROL **Diccionario de datos**] en el carril izquierdo de Analysis Workspace. (Las formas alternativas de acceder al diccionario de datos se describen en “Acceso al diccionario de datos” en [Información general del diccionario de datos](/help/components/data-dictionary/data-dictionary-overview.md)).

   Se muestra la ventana Diccionario de datos.

   ![data-dictionary.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Asegúrese de que el grupo de informes que contiene el componente que desea ver esté seleccionado en el menú desplegable. De forma predeterminada, se muestra el grupo de informes en el que ya se encuentra.

1. (Opcional) En el campo de búsqueda, empiece a escribir el nombre del componente que desea ver.

   El tipo de componente se puede identificar mediante el color y el icono. **Dimension** ![Dimension](assets/dimension-icon.png) son naranjas, **Segmentos** ![Icono de segmento](assets/segment-icon.png) son azules, **Intervalos de fechas** ![Icono de intervalo de fechas](assets/date-range-icon.png) son púrpura y **Métricas** ![Icono de métrica](assets/default-metric-icon.png) son verdes. El icono del Adobe ![Icono de Adobe](assets/default-calc-metric-icon.png) indica una plantilla de métrica calculada o una plantilla de segmento y el icono de la calculadora ![Icono de calculadora](assets/calculated-metric-icon-created.png) indica una métrica calculada que fue creada por un administrador de Analytics en su organización.

{{dd-filter-criteria}}

1. En la lista de componentes, seleccione el componente que desee ver.

   Se muestra la siguiente información acerca del componente:

   {{dd-component-information}}

1. (Opcional) Arrastre un componente del diccionario de datos a Analysis Workspace.