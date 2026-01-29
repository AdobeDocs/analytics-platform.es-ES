---
title: Dimension único clasificado
description: Caso de uso de clasificación de dimensión única para la extensión BI en varias herramientas BI en Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 1%

---

# Dimensión única clasificada


En este caso de uso, desea mostrar una tabla y una visualización de barra simple que muestre los ingresos de compras y compras para nombres de productos a lo largo de 2023.

+++ Customer Journey Analytics

Un ejemplo de **[!UICONTROL panel Dimension Ranked]** único para el caso de uso:

![Visualización de clasificación de dimensión única de Customer Journey Analytics](../assets/cja-single-dimension-ranked.png)

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
   1. Seleccione **[!UICONTROL product_name]**.
   1. Seleccione **[!UICONTROL sum purchase_revenue]**.
   1. Seleccionar **[!UICONTROL compras de suma]**.

   Verá una tabla vacía que muestra únicamente los encabezados de columna del elemento seleccionado. Para obtener una mejor visibilidad, amplíe la visualización.

1. En el panel **[!UICONTROL Filtros]**:

   1. Seleccione el **[!UICONTROL intervalo de fechas es (todos)]** de **[!UICONTROL Filtros en este elemento visual]**.
   1. Seleccione **[!UICONTROL Fecha relativa]** como **[!UICONTROL Tipo de filtro]**.
   1. Defina el filtro para **[!UICONTROL Mostrar elementos cuando el valor]** **[!UICONTROL esté en los últimos]** `1` **[!UICONTROL años del calendario]**.
   1. Seleccione **[!UICONTROL Aplicar filtro]**.

   Verá la tabla actualizada con el filtro **[!UICONTROL daterange]** aplicado.

1. En el panel **[!UICONTROL Visualización]**:

   1. Use ![CrossSize75](/help/assets/icons/CrossSize75.svg) para quitar **[!UICONTROL daterange]** de **[!UICONTROL Columnas]**.
   1. Arrastre y suelte **[!UICONTROL Sum of purchases_revenue]** debajo de **[!UICONTROL Sum of purchases]** en **[!UICONTROL Columnas]**.

1. En la visualización Tabla:

   1. Seleccione **[!UICONTROL Sum of purchase_revenue]** para ordenar los nombres de los productos en orden descendente de ingresos de compra. El escritorio de Power BI debe tener el aspecto siguiente.

   ![Estado de la tabla del caso de uso 5 de Power BI Desktop](../assets/uc5-pbi-table.png)

1. En el panel **[!UICONTROL Filtros]**:

   1. Seleccione **[!UICONTROL product_name is (All)]**.
   1. Establezca **[!UICONTROL Filter type]** en **[!UICONTROL Top N]**.
   1. Definir el filtro para **[!UICONTROL Mostrar elementos]** **[!UICONTROL Principales]** `10` **[!UICONTROL Por valor]**.
   1. Arrastre y suelte **[!UICONTROL purchase_revenue]** en **[!UICONTROL Por valor]** **[!UICONTROL Agregue campos de datos aquí]**.
   1. Seleccione **[!UICONTROL Aplicar filtro]**.

   Verá la tabla actualizada con valores para los ingresos de compra sincronizados con la visualización de tabla de forma libre en Analysis Workspace.

1. En el panel **[!UICONTROL Visualizaciones]**:

   1. Seleccione la visualización **[!UICONTROL Gráfico de líneas y columnas apiladas]**.

   Una visualización de gráficos de líneas y columnas apiladas reemplaza la tabla al utilizar los mismos datos que la tabla.

1. Arrastre y suelte **[!UICONTROL compras]** en **[!UICONTROL Línea eje Y]** en el panel **[!UICONTROL Visualizaciones]**.

   Se actualiza el gráfico de líneas y columnas apiladas. El escritorio de Power BI debe tener el aspecto siguiente.

   ![Gráfico de 5 casos de uso de escritorio de Power BI](../assets/uc5-pbi-chart.png)

1. Visualización del gráfico de columnas apiladas y líneas:

   1. Seleccione ![Más](/help/assets/icons/More.svg).
   1. En el menú contextual, seleccione **[!UICONTROL Mostrar como tabla]**.

   La vista principal se actualiza para mostrar una visualización de líneas y una tabla.

   ![Visualización de tendencias diarias finales del caso de uso 2 de Power BI Desktop](../assets/uc5-pbi-final.png)

>[!TAB Escritorio Tableau]

1. Seleccione la ficha **[!UICONTROL Hoja 1]** en la parte inferior para cambiar de **[!UICONTROL Fuente de datos]**. En la vista **[!UICONTROL Hoja 1]**:
   1. Arrastre la entrada **[!UICONTROL Daterange]** de la lista **[!UICONTROL Tablas]** en el panel **[!UICONTROL Datos]** y suéltela en el estante **[!UICONTROL Filtros]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtros de campo \[Intervalo de fechas\]]**, seleccione **[!UICONTROL Intervalo de fechas]** y seleccione **[!UICONTROL Siguiente >]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtrar \[Daterange\]]**, seleccione **[!UICONTROL Intervalo de fechas]** y especifique un período de `01/01/2023` - `31/12/2023`. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.

      ![Filtro Tableau para escritorio](../assets/uc5-tableau-filter.png)

   1. Arrastre y suelte **[!UICONTROL Product Name]** de la lista **[!UICONTROL Tablas]** en el panel **[!UICONTROL Datos]** y suelte la entrada en el campo junto a **[!UICONTROL Filas]**.
   1. Arrastre y suelte **[!UICONTROL Purchases]** de la lista **[!UICONTROL Tables (*Measure Names*)]** en el panel **[!UICONTROL Datos]** y suelte la entrada en el campo junto a **[!UICONTROL Rows]**. El valor se convierte automáticamente a **[!UICONTROL SUM(Purchases)]**.
   1. Arrastre y suelte **[!UICONTROL Ingresos de compra]** de la lista **[!UICONTROL Tablas (*Nombres de medida*)]** en el panel **[!UICONTROL Datos]** y suelte la entrada en el campo junto a **[!UICONTROL Columnas]** y a la izquierda de **[!UICONTROL SUM(Compras)]**. El valor se convierte automáticamente a **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Para ordenar ambos gráficos en orden descendente de ingresos de compra, pase el ratón sobre el título **[!UICONTROL Ingresos de compra]** y seleccione el icono de ordenación.
   1. Para limitar el número de entradas en los gráficos, seleccione **[!UICONTROL SUM(Purchase Revenue)]** en **[!UICONTROL Filas]** y en el menú desplegable seleccione **[!UICONTROL Filtro]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtrar \[Ingresos de compra\]]**, seleccione **[!UICONTROL Rango de valores]** e introduzca los valores apropiados. Por ejemplo: `1,000,000` - `2,000,000`. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.
   1. Para convertir los dos gráficos de barras en un gráfico combinado dual, seleccione **[!UICONTROL SUM(Purchases)]** en **[!UICONTROL Rows]** y en el menú desplegable, seleccione **[!UICONTROL Dual Axis]**. Los gráficos de barras se transforman en un diagrama de puntos.
   1. Para modificar el diagrama de puntos en un gráfico de barras:
      1. Seleccione **[!UICONTROL SUM(Purchases)]** en el área de **[!UICONTROL Marks]** y seleccione **[!UICONTROL Line]** del menú desplegable.
      1. Seleccione **[!UICONTROL SUM(Purchase Revenue)]** en el área de **[!UICONTROL Marcas]** y seleccione **[!UICONTROL Barra]** del menú desplegable.

   El escritorio Tableau debe tener el aspecto siguiente.

   ![Tableau Desktop Graph](../assets/uc5-tableau-graph.png)

1. Seleccione **[!UICONTROL Duplicate]** del menú contextual de la ficha **[!UICONTROL Hoja 1]** para crear una segunda hoja.
1. Seleccione **[!UICONTROL Rename]** del menú contextual de la ficha **[!UICONTROL Hoja 1]** para cambiar el nombre de la hoja a `Data`.
1. Seleccione **[!UICONTROL Rename]** del menú contextual de la ficha **[!UICONTROL Hoja 1 (2)]** para cambiar el nombre de la hoja a `Graph`.
1. Asegúrese de que la hoja **[!UICONTROL Data]** esté seleccionada.
   1. Seleccione **[!UICONTROL Mostrarme]** en la parte superior derecha y seleccione **[!UICONTROL Tabla de texto]** (visualización superior izquierda superior) para modificar el contenido de los dos gráficos a una tabla.
   1. Para ordenar los ingresos de compra en orden descendente, pase el ratón sobre **[!UICONTROL Ingresos de compra]** en la tabla y seleccione ![SortOrderDown](/help/assets/icons/SortOrderDown.svg).
   1. Seleccione **[!UICONTROL Vista completa]** del menú desplegable **[!UICONTROL Ajustar]**.

   El escritorio Tableau debe tener el aspecto siguiente.

   ![Datos de escritorio Tableau](../assets/uc5-tableau-data.png)

1. Seleccione el botón de pestaña **[!UICONTROL Nuevo panel]** (en la parte inferior) para crear una nueva vista de **[!UICONTROL panel 1]**. En la vista **[!UICONTROL Panel 1]**:
   1. Arrastre y suelte la hoja **[!UICONTROL Graph]** del estante **[!UICONTROL Sheets]** en la vista **[!UICONTROL Dashboard 1]** que dice *Colocar hojas aquí*.
   1. Arrastre y suelte la hoja **[!UICONTROL Data]** del estante **[!UICONTROL Sheets]** debajo de la hoja **[!UICONTROL Graph]** en la vista **[!UICONTROL Dashboard 1]**.
   1. Seleccione la hoja **[!UICONTROL Data]** en la vista y modifique **[!UICONTROL Toda la vista]** a **[!UICONTROL Anchura de la corrección]**.

   La vista del **[!UICONTROL panel 1]** debería ser similar a la siguiente.

   ![Tablero de escritorio Tableau 1](../assets/uc5-tableau-dashboard.png)



>[!TAB Buscador]

1. En la interfaz **[!UICONTROL Explorar]** de Looker, asegúrate de tener una configuración limpia. Si no, seleccione ![Configuración](/help/assets/icons/Setting.svg) **[!UICONTROL Quitar campos y filtros]**.
1. Seleccione **[!UICONTROL + Filtro]** debajo de **[!UICONTROL Filtros]**.
1. En el diálogo **[!UICONTROL Agregar filtro]**:
   1. Seleccionar **[!UICONTROL ‣ Vista De Datos Cc]**
   1. En la lista de campos, seleccione **[!UICONTROL ‣ Daterange Date]** y después **[!UICONTROL Daterange Date]**.
      ![Filtro de búsqueda](../assets/uc2-looker-filter.png)
1. Especifique el filtro **[!UICONTROL Cc Data View Daterange Date]** ya que **[!UICONTROL está en el intervalo]** **[!UICONTROL 2023/01/01]** **[!UICONTROL hasta (antes)]** **[!UICONTROL 2024/01/01]**.
1. En la sección **[!UICONTROL ‣ Vista de datos CC]** del carril izquierdo, seleccione **[!UICONTROL Nombre de producto]**.
1. Desde la sección **[!UICONTROL ‣ Campos personalizados]** en el carril izquierdo:
   1. Seleccione **[!UICONTROL Medida personalizada]** del menú desplegable **[!UICONTROL + Agregar]**.
   1. En el diálogo **[!UICONTROL Crear medida personalizada]**:
      1. Seleccione **[!UICONTROL Ingresos de compra]** del menú desplegable **[!UICONTROL Campo para medir]**.
      1. Seleccione **[!UICONTROL Sum]** del menú desplegable **[!UICONTROL Tipo de medida]**.
      1. Escriba un nombre de campo personalizado para **[!UICONTROL Name]**. Por ejemplo: `Purchase Revenue`.
      1. Seleccione la ficha **[!UICONTROL Detalles del campo]**.
      1. Seleccione **[!UICONTROL Decimals]** del menú desplegable **[!UICONTROL Formato]** y asegúrese de que `0` se ha introducido en **[!UICONTROL Decimals]**.
         ![Campo de métrica personalizada de observador](../assets/uc5-looker-customfield.png)
      1. Seleccione **[!UICONTROL Guardar]**.
   1. Seleccione **[!UICONTROL Medida personalizada]** una vez más en el menú desplegable **[!UICONTROL + Agregar]**. En el cuadro de diálogo de medida **[!UICONTROL Crear personalizado]**:
      1. Seleccione **[!UICONTROL Compras]** del menú desplegable **[!UICONTROL Campo para medir]**.
      1. Seleccione **[!UICONTROL Sum]** del menú desplegable **[!UICONTROL Tipo de medida]**.
      1. Escriba un nombre de campo personalizado para **[!UICONTROL Name]**. Por ejemplo: `Sum of Purchases`.
      1. Seleccione la ficha **[!UICONTROL Detalles del campo]**.
      1. Seleccione **[!UICONTROL Decimals]** del menú desplegable **[!UICONTROL Formato]** y asegúrese de que `0` se ha introducido en **[!UICONTROL Decimals]**.
      1. Seleccione **[!UICONTROL Guardar]**.
   1. Ambos campos se añaden automáticamente a la vista de datos.
1. Seleccione **[!UICONTROL + Filtro]** para agregar otros **[!UICONTROL Filtros]** y para limitar los datos.
1. En el cuadro de diálogo **[!UICONTROL Agregar filtro]**, seleccione **[!UICONTROL ‣ Campos personalizados]** y después **[!UICONTROL Ingresos de compra]**.
1. Realice las selecciones adecuadas e introduzca los valores propuestos, de modo que el filtro indique **[!UICONTROL está entre inclusivo]** `1000000` **[!UICONTROL Y]** `2000000`.
1. Seleccione **[!UICONTROL Ejecutar]**.
1. Seleccione **[!UICONTROL ‣ Visualización]** para mostrar la visualización de líneas.
1. Seleccione **[!UICONTROL Editar]** en **[!UICONTROL Visualización]** para actualizar la visualización. En el cuadro de diálogo emergente:
   1. Seleccione la ficha **[!UICONTROL Serie]**.
   1. Desplácese hacia abajo para ver **[!UICONTROL Compras]** y cambie **[!UICONTROL Tipo]** a **[!UICONTROL Línea]**.
   1. Seleccione la ficha **[!UICONTROL Y]**.
   1. Arrastre **[!UICONTROL Compras]** desde el contenedor **[!UICONTROL Izquierda 1]** hasta donde se lee **[!UICONTROL *Arrastre la serie aquí para crear un nuevo eje izquierdo *]**. Esta acción crea un contenedor&#x200B;**[!UICONTROL &#x200B; Left 2 &#x200B;]**.
      ![Configuración de visualización de buscador](../assets/uc5-looker-visualization.png)
   1. Seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) junto a **[!UICONTROL Editar]** para ocultar el cuadro de diálogo emergente

Debería ver una visualización y una tabla similares a las que se muestran a continuación.

![Tendencia diaria de resultados de búsqueda](../assets/uc5-looker-result.png)


>[!TAB Jupyter Notebook]

1. Introduzca las siguientes instrucciones en una nueva celda.

   ```
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_name AS `Product Name`, SUM(purchase_revenue) AS `Purchase Revenue`, SUM(purchases) AS `Purchases` \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01' \
               GROUP BY 1 \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby('Product Name', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.barplot(x='Purchase Revenue', y='Product Name', data=df)
   plt.show()
   display(data)
   ```

1. Ejecute la celda. Debería ver una salida similar a la captura de pantalla siguiente.

   ![Resultados de Jupyter Notebook](../assets/uc5-jupyter-results.png)


>[!TAB EstudioRS]

1. Escriba las siguientes instrucciones entre ` ` ``{r} ` y ` `` ` ` en un nuevo fragmento.

   ```R
   library(tidyr)
   
   ## Single dimension ranked
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2024-01-01") %>%
      group_by(product_name) %>%
      summarise(purchase_revenue = sum(purchase_revenue), purchases = sum(purchases)) %>%
      arrange(product_name, .by_group = FALSE)
   dfV <- df %>%
      head(5)
   ggplot(dfV, aes(x = purchase_revenue, y = product_name)) +
      geom_col(position = "dodge") +
      geom_text(aes(label = purchase_revenue), vjust = -0.5)
   print(df)
   ```

1. Ejecuta el fragmento. Debería ver una salida similar a la captura de pantalla siguiente.

   ![Resultados de RStudio](../assets/uc5-rstudio-results.png)

>[!ENDTABS]

+++

