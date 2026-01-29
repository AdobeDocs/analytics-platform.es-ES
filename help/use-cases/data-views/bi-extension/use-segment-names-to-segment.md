---
title: Use Los Nombres De Los Segmentos Para Segmentar
description: Utilice nombres de segmentos para segmentar casos de uso de la extensión de BI en varias herramientas de BI en Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 1%

---

# Usar nombres de segmento para segmentar

En este caso de uso, desea utilizar un segmento existente para la categoría de producto Pesca que haya definido en Customer Journey Analytics. Para segmentar e informar sobre nombres de productos y ocurrencias (eventos) durante enero de 2023.

+++ Customer Journey Analytics

Inspeccione el segmento que desee utilizar en Customer Journey Analytics.

![Customer Journey Analytics Usa Nombres De Filtro Para Filtrar](../assets/cja-fishing-products.png)

A continuación, puede utilizar ese segmento en un ejemplo **[!UICONTROL Uso de nombres de segmento en el panel Segmento]** para el caso de uso:

![Valores de recuento distinto de Customer Journey Analytics](../assets/cja-using-filter-names-to-filter.png)

+++

+++ Herramientas de BI

>[!PREREQUISITES]
>
>Asegúrese de que ha validado [una conexión correcta, que puede enumerar vistas de datos y que utiliza una vista de datos](connect-and-validate.md) para la herramienta de BI para la que desea probar este caso de uso.
>

>[!BEGINTABS]

>[!TAB Escritorio de Power BI]

1. En el panel **[!UICONTROL Datos]**:
   1. Seleccione **[!UICONTROL daterange]**.
   1. Seleccione **[!UICONTROL filterName]**.
   1. Seleccione **[!UICONTROL product_name]**.
   1. Seleccione **[!UICONTROL sumar repeticiones]**.

Verá una visualización que muestra **[!UICONTROL Error al obtener los datos de este elemento visual]**.

1. En el panel **[!UICONTROL Filtros]**:

   1. Seleccione **[!UICONTROL filterName is (All)]** de **[!UICONTROL Filtros en este elemento visual]**.
   1. Seleccione **[!UICONTROL Filtro básico]** como **[!UICONTROL Tipo de filtro]**.
   1. Debajo del campo **[!UICONTROL Buscar]**, seleccione **[!UICONTROL Productos de pesca]**, que es el nombre del filtro existente definido en Customer Journey Analytics.
   1. Seleccione **[!UICONTROL intervalo de fechas es (todo)]** de **[!UICONTROL Filtros en este elemento visual]**.
   1. Seleccione **[!UICONTROL Filtro avanzado]** como **[!UICONTROL Tipo de filtro]**.
   1. Defina el filtro para **[!UICONTROL Mostrar elementos cuando el valor]** **[!UICONTROL esté en]** `1/1/2023` **[!UICONTROL y]** **[!UICONTROL esté antes de]** `2/1/2023` o después.
   1. Seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para quitar **[!UICONTROL filterName]** de **[!UICONTROL Columnas]**.
   1. Seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para quitar **[!UICONTROL daterange]** de **[!UICONTROL Columnas]**.

   Verá la tabla actualizada con el filtro **[!UICONTROL filterName]** aplicado. El escritorio de Power BI debe tener el aspecto siguiente.

   ![Escritorio De Power BI Que Usa Nombres De Intervalo De Fechas Para Filtrar](../assets/uc9-powerbi-final.png)


>[!TAB Escritorio Tableau]

1. Seleccione la ficha **[!UICONTROL Hoja 1]** en la parte inferior para cambiar de **[!UICONTROL Fuente de datos]**. En la vista **[!UICONTROL Hoja 1]**:
   1. Arrastre la entrada **[!UICONTROL Filter Name]** de la lista **[!UICONTROL Tables]** en el estante **[!UICONTROL Filters]**.
   1. En el diálogo **[!UICONTROL Filtrar \[Nombre del filtro\]]**, asegúrese de que **[!UICONTROL Seleccionar de la lista]** está seleccionado y seleccione **[!UICONTROL Productos de pesca]** de la lista. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.
   1. Arrastre la entrada **[!UICONTROL Daterange]** de la lista **[!UICONTROL Tablas]** en el estante **[!UICONTROL Filtros]**.
   1. En el cuadro de diálogo **[!UICONTROL Campo de filtro \[Intervalo de fechas\]]**, seleccione **[!UICONTROL Intervalo de fechas]** y seleccione **[!UICONTROL Siguiente >]**.
   1. En el diálogo **[!UICONTROL Filtrar \[Daterang\]]**, seleccione **[!UICONTROL Intervalo de fechas]** y seleccione `01/01/2023` - `01/02/2023`. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.
   1. Arrastre **[!UICONTROL Product Name]** de la lista **[!UICONTROL Tablas]** a **[!UICONTROL Filas]**.
   1. Arrastre la entrada **[!UICONTROL Ocurrencias]** de la lista **[!UICONTROL Tablas]** y suelte la entrada en el campo junto a **[!UICONTROL Columnas]**. El valor cambia a **[!UICONTROL SUM(Occurrences)]**.
   1. Seleccione **[!UICONTROL Tabla de texto]** de **[!UICONTROL Mostrarme]**.
   1. Seleccione **[!UICONTROL Ajustar ancho]** del menú desplegable **[!UICONTROL Ajustar]**.

      El escritorio Tableau debe tener el aspecto siguiente.

      ![Filtro Tableau Desktop Multiple Dimension Ranked](../assets/uc9-tableau-final.png)

>[!TAB Buscador]

1. En la interfaz **[!UICONTROL Explorar]** de Looker, asegúrate de tener una configuración limpia. Si no, seleccione ![Configuración](/help/assets/icons/Setting.svg) **[!UICONTROL Quitar campos y filtros]**.
1. Seleccione **[!UICONTROL + Filtro]** debajo de **[!UICONTROL Filtros]**.
1. En el diálogo **[!UICONTROL Agregar filtro]**:
   1. Seleccionar **[!UICONTROL ‣ Vista De Datos Cc]**
   1. En la lista de campos, seleccione **[!UICONTROL ‣ Daterange Date]** y después **[!UICONTROL Daterange Date]**.
      ![Filtro de búsqueda](../assets/uc2-looker-filter.png)
1. Especifique el filtro **[!UICONTROL Cc Data View Daterange Date]** ya que **[!UICONTROL está en el intervalo]** **[!UICONTROL 2023/01/01]** **[!UICONTROL hasta (antes)]** **[!UICONTROL 2023/02/01]**.
1. Seleccione **[!UICONTROL + Filtro]** debajo de **[!UICONTROL Filtros]** para agregar otro filtro.
1. En el diálogo **[!UICONTROL Agregar filtro]**:
   1. Seleccionar **[!UICONTROL ‣ Vista De Datos Cc]**
   1. En la lista de campos, seleccione **[!UICONTROL ‣ Nombre del filtro]**.
1. Asegúrese de que **[!UICONTROL es]** la selección para el filtro.
1. Seleccione **[!UICONTROL Productos de pesca]** de la lista de valores posibles.
1. Desde la sección **[!UICONTROL ‣ Vista de datos CC]** en el carril izquierdo:
   1. Seleccione **[!UICONTROL Nombre de producto]**.
   1. Seleccione **[!UICONTROL Count]** debajo de **[!UICONTROL MEASURES]** en el carril izquierdo (en la parte inferior).
1. Seleccione **[!UICONTROL Ejecutar]**.
1. Seleccione **[!UICONTROL ‣ visualización]**.

Debería ver una visualización y una tabla similares a las que se muestran a continuación.

![Recuento de buscadores distinto](../assets/uc9-looker-result.png)



>[!TAB Jupyter Notebook]

1. Introduzca las siguientes instrucciones en una nueva celda.

   ```python
   data = %sql SELECT filterName FROM cc_data_view;
   style = {'description_width': 'initial'}
   filter_name = widgets.Dropdown(
      options=[d for d, in data],
      description='Filter Name:',
      style=style
   )
   display(filter_name)
   ```

1. Ejecute la celda. Debería ver una salida similar a la captura de pantalla siguiente.

   ![Resultados de Jupyter Notebook](../assets/uc9-jupyter-input.png)

1. Seleccione **[!UICONTROL Productos de pesca]** en el menú desplegable.

1. Introduzca las siguientes instrucciones en una nueva celda.

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_name AS `Product Name`, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
                  AND filterName = '{filter_name.value}' \
               GROUP BY 1 \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby('Product Name', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.barplot(x='Events', y='Product Name', data=df)
   plt.show()
   display(data)
   ```

1. Ejecute la celda. Debería ver una salida similar a la captura de pantalla siguiente.

   ![Resultados de Jupyter Notebook](../assets/uc9-jupyter-results.png)


>[!TAB EstudioRS]

1. Escriba las siguientes instrucciones entre ` ```{r} ` y ` ``` ` en un nuevo fragmento. Asegúrese de utilizar el nombre de filtro adecuado. Por ejemplo, `Fishing Products`.

   ```R
   ## Dimension filtered by name
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01" & filterName == "Fishing Products") %>%
      group_by(product_name) %>%
      count() %>%
      arrange(desc(n), .by_group = FALSE)
   print(df)
   ```

1. Ejecuta el fragmento. Debería ver una salida similar a la captura de pantalla siguiente.

   ![Resultados de RStudio](../assets/uc9-rstudio-results.png)


>[!ENDTABS]

+++
