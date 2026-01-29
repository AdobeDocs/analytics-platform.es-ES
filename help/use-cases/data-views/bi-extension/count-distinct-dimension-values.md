---
title: Contar dimensiones de valores distintos
description: Caso de uso de dimensiones de Contar valores distintos para la extensión de BI en varias herramientas de BI en Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '950'
ht-degree: 0%

---

# Contar dimensiones de valores distintos


En este caso de uso, desea obtener el número distinto de nombres de productos de los que se ha informado durante enero de 2023.

+++ Customer Journey Analytics

Para informar sobre un recuento distinto de nombres de productos, configuró una métrica calculada en Customer Journey Analytics, con **[!UICONTROL Título]** `Product Name (Count Distinct)` e **[!UICONTROL Id. externo]** `product_name_count_distinct`.

![Métrica calculada con nombre de producto Customer Journey Analytics (recuento de distintivos)](../assets/cja-calc-metric-distinct-count-product-names.png)

A continuación, puede usar esa métrica en un ejemplo del panel **[!UICONTROL Contar valores distintos de Dimension]** para el caso de uso:

![Valores de recuento distinto de Customer Journey Analytics](../assets/cja-count-distinct-dimension-values.png)

+++

+++ Herramientas de BI

>[!PREREQUISITES]
>
>Asegúrese de que ha validado [una conexión correcta, que puede enumerar vistas de datos y que utiliza una vista de datos](connect-and-validate.md) para la herramienta de BI para la que desea probar este caso de uso.
>

>[!BEGINTABS]

>[!TAB Escritorio de Power BI]

1. Para asegurarse de que el intervalo de fechas se aplique a todas las visualizaciones, arrastre y suelte **[!UICONTROL daterangeday]** desde el panel **[!UICONTROL Datos]** a **[!UICONTROL Filtros]** en esta página.
   1. Seleccione **[!UICONTROL daterangeday es (todo)]** de **[!UICONTROL Filtros de esta página]**.
   1. Seleccione **[!UICONTROL Filtro avanzado]** como **[!UICONTROL Tipo de filtro]**.
   1. Defina el filtro para **[!UICONTROL Mostrar elementos cuando el valor]** **[!UICONTROL esté en]** `1/1/2023` **[!UICONTROL y]** **[!UICONTROL esté antes de]** `2/1/2023` o después.
   1. Seleccione **[!UICONTROL Aplicar filtro]**.

1. En el panel **[!UICONTROL Datos]**:
   1. Seleccione **[!UICONTROL datarangeday]**.
   1. Seleccione **[!UICONTROL sum cm_product_name_count_distinct]**, que es la métrica calculada definida en Customer Journey Analytics.

1. Para modificar el gráfico de barras verticales en una tabla, asegúrese de que ha seleccionado el gráfico y seleccione **[!UICONTROL Tabla]** en el panel **[!UICONTROL Visualizaciones]**.

   El escritorio de Power BI debe tener el aspecto siguiente.

   ![Tabla de varios recuentos distintos en el escritorio Power BI](../assets/uc7-powerbi-table.png)

1. Seleccione la visualización de tabla. En el menú contextual, seleccione **[!UICONTROL Copiar]** > **[!UICONTROL Copiar elemento visual]**.
1. Pegue la visualización mediante **[!UICONTROL ctrl-v]**. La copia exacta de la visualización se superpone con la original. Muévalo a la derecha en el área del informe.
1. Para modificar la visualización copiada de una tabla a una tarjeta, seleccione **[!UICONTROL Tarjeta]** de **[!UICONTROL Visualizaciones]**.

   El escritorio de Power BI debe tener el aspecto siguiente.

   ![Tabla de varios recuentos distintos en el escritorio Power BI](../assets/uc7-powerbi-final.png)

Como alternativa, puede utilizar la funcionalidad de recuento distinto de Power BI.

1. Seleccione la dimensión **[!UICONTROL product_name]**.
1. Aplique la función **[!UICONTROL Count (Distinct)]** en la dimensión **[!UICONTROL product_name]** en **[!UICONTROL Columns]**.

   ![Número de Power BI Distinct](../assets/uc7-powerbi-alternative.png)



>[!TAB Escritorio Tableau]

1. Seleccione la ficha **[!UICONTROL Hoja 1]** en la parte inferior para cambiar de **[!UICONTROL Fuente de datos]**. En la vista **[!UICONTROL Hoja 1]**:
   1. Arrastre la entrada **[!UICONTROL Daterange]** de la lista **[!UICONTROL Tablas]** en el panel **[!UICONTROL Datos]** y suéltela en el estante **[!UICONTROL Filtros]**.
   1. En el cuadro de diálogo **[!UICONTROL Campo de filtro \[Intervalo de fechas\]]**, seleccione **[!UICONTROL Intervalo de fechas]** y seleccione **[!UICONTROL Siguiente >]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtrar \[Daterange\]]**, seleccione **[!UICONTROL Intervalo de fechas]** y seleccione `01/01/2023` - `31/1/2023`. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.
   1. Arrastre **[!UICONTROL Cm Product Name Count Distinct]** A **[!UICONTROL Filas]**. El valor cambia a **[!UICONTROL SUM(Cm Product Name Count Distinct)]**. Este campo es la métrica calculada que ha definido en Customer Journey Analytics.
   1. Arrastre **[!UICONTROL Daterangeday]** y suéltelo junto a **[!UICONTROL Columns]**. Seleccione **[!UICONTROL Daterangeday]** y en el menú desplegable seleccione **[!UICONTROL Día]**.
   1. Para modificar la visualización de líneas en una tabla, seleccione **[!UICONTROL Tabla de texto]** de **[!UICONTROL Mostrar]**.
   1. Seleccione **[!UICONTROL Intercambiar filas y columnas]** en la barra de herramientas.
   1. Seleccione **[!UICONTROL Ajustar ancho]** del menú desplegable **[!UICONTROL Ajustar]**.

      El escritorio Tableau debe tener el aspecto siguiente.

      ![Filtro Tableau Desktop Multiple Dimension Ranked](../assets/uc7-tableau-data.png)

1. Seleccione **[!UICONTROL Duplicate]** del menú contextual de la ficha **[!UICONTROL Hoja 1]** para crear una segunda hoja.
1. Seleccione **[!UICONTROL Rename]** del menú contextual de la ficha **[!UICONTROL Hoja 1]** para cambiar el nombre de la hoja a `Data`.
1. Seleccione **[!UICONTROL Rename]** del menú contextual de la ficha **[!UICONTROL Hoja 1 (2)]** para cambiar el nombre de la hoja a `Card`.

1. Asegúrese de haber seleccionado la vista **[!UICONTROL Tarjeta]**.
1. Seleccione **[!UICONTROL DAY(Daterangeday)]** y en el menú desplegable seleccione **[!UICONTROL Mes]**. El valor cambia a **[!UICONTROL MONTH(Daterangeday)]**.
1. Seleccione **[!UICONTROL SUM(Cm Product Name Count Distinct)]** en **[!UICONTROL Marcas]** y, en el menú desplegable, seleccione **[!UICONTROL Formato]**.
1. Para cambiar el tamaño de la fuente, en el panel **[!UICONTROL Formato SUM(CM Product Name Count Distinct)]**, seleccione **[!UICONTROL Fuente]** en **[!UICONTROL Predeterminada]** y seleccione **[!UICONTROL 72]** para el tamaño de fuente.
1. Para alinear el número, selecciona **[!UICONTROL Automático]** junto a **[!UICONTROL Alineación]** y establece **[!UICONTROL Horizontal]** como centrado.
1. Para usar números enteros, selecciona **[!UICONTROL 123.456]** junto a **[!UICONTROL Números]** y selecciona **[!UICONTROL Número (personalizado)]**. Establezca **[!UICONTROL Lugares decimales]** en `0`.

   El escritorio Tableau debe tener el aspecto siguiente.

   ![Filtro Tableau Desktop Multiple Dimension Ranked](../assets/uc7-tableau-card.png)

1. Seleccione el botón de pestaña **[!UICONTROL Nuevo panel]** (en la parte inferior) para crear una nueva vista de **[!UICONTROL panel 1]**. En la vista **[!UICONTROL Panel 1]**:
   1. Arrastre y suelte la hoja **[!UICONTROL Tarjeta]** del estante **[!UICONTROL Hojas]** en la vista **[!UICONTROL Panel 1]** que dice *Colocar hojas aquí*.
   1. Arrastre y suelte la hoja **[!UICONTROL Data]** del estante **[!UICONTROL Sheets]** debajo de la hoja **[!UICONTROL Card]** en la vista **[!UICONTROL Dashboard 1]**.

   La vista del **[!UICONTROL panel 1]** debería ser similar a la siguiente.

   ![Tablero de escritorio Tableau 1](../assets/uc7-tableau-final.png)


También puede utilizar la funcionalidad de recuento distinto de Tableau Desktop.

1. Use **[!UICONTROL Nombre De Producto]** en lugar de **[!UICONTROL Nombre De Producto Cm Recuento Distinto]**.
1. Aplicar **[!UICONTROL Medida]** > **[!UICONTROL Recuento (distinto)]** en **[!UICONTROL Nombre de producto]** en **[!UICONTROL Marcas]**.

   ![Número de tableau distinto](../assets/uc7-tableau-alternative.png)


>[!TAB Buscador]

1. En la interfaz **[!UICONTROL Explorar]** de Looker, asegúrate de tener una configuración limpia. Si no, seleccione ![Configuración](/help/assets/icons/Setting.svg) **[!UICONTROL Quitar campos y filtros]**.
1. Seleccione **[!UICONTROL + Filtro]** debajo de **[!UICONTROL Filtros]**.
1. En el diálogo **[!UICONTROL Agregar filtro]**:
   1. Seleccionar **[!UICONTROL ‣ Vista De Datos Cc]**
   1. En la lista de campos, seleccione **[!UICONTROL ‣ Daterange Date]** y después **[!UICONTROL Daterange Date]**.
      ![Filtro de búsqueda](../assets/uc2-looker-filter.png)
1. Especifique el filtro **[!UICONTROL Cc Data View Daterange Date]** ya que **[!UICONTROL está en el intervalo]** **[!UICONTROL 2023/01/01]** **[!UICONTROL hasta (antes)]** **[!UICONTROL 2023/02/01]**.
1. Desde la sección **[!UICONTROL ‣ Vista de datos CC]** en el carril izquierdo:
   1. Seleccione **[!UICONTROL Fecha de intervalo de fechas]** y después **[!UICONTROL Fecha]**.
   1. Seleccione **[!UICONTROL Agregado Xtender Count Distinct]** del menú contextual **⋮ More** en **[!UICONTROL Nombre del producto]**.
      ![Menú contextual del nombre del producto del buscador](../assets/uc7-looker-count-distinct.png)
1. Seleccione **[!UICONTROL Ejecutar]**.
1. Seleccione **[!UICONTROL ‣ Visualización]** y seleccione 6︎⃣ en la barra de herramientas para mostrar una visualización de Valor único.

Debería ver una visualización y una tabla similares a las que se muestran a continuación.

![Recuento de buscadores distinto](../assets/uc7-looker-result.png)


>[!TAB Jupyter Notebook]

1. Introduzca las siguientes instrucciones en una nueva celda.

   ```
   data = %sql SELECT COUNT(DISTINCT(product_name)) AS `Product Name` \
      FROM cc_data_view \
      WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01';
   display(data)
   ```

1. Ejecute la celda. Debería ver una salida similar a la captura de pantalla siguiente.

   ![Resultados de Jupyter Notebook](../assets/uc7-jupyter-results.png)


>[!TAB EstudioRS]

1. Escriba las siguientes instrucciones entre ` ` ``{r} ` y ` `` ` ` en un nuevo fragmento.

   ```R
   ## Count Distinct
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01") %>%
      summarise(product_name_count_distinct = n_distinct(product_name))
   print(df)
   ```

1. Ejecuta el fragmento. Debería ver una salida similar a la captura de pantalla siguiente.

   ![Resultados de RStudio](../assets/uc7-rstudio-results.png)


>[!ENDTABS]

+++

