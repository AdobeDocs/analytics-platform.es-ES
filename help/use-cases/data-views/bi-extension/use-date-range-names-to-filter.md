---
title: Usar nombres de intervalo de fechas para filtrar
description: Utilice nombres de intervalos de fechas para filtrar casos de uso de la extensión de BI en varias herramientas de BI en Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 1%

---

# Usar nombres de intervalo de fechas para filtrar

En este caso de uso, desea utilizar un intervalo de fechas que ha definido en Customer Journey Analytics para filtrar e informar sobre ocurrencias (eventos) durante el último año.

+++ Customer Journey Analytics

Para informar usando un intervalo de fechas, configuró un intervalo de fechas en Customer Journey Analytics, con **[!UICONTROL Título]** `Last Year 2023`.

![Customer Journey Analytics Use nombres de intervalo de fechas para filtrar](../assets/cja-daterange.png)

A continuación, puede usar ese intervalo de fechas en un ejemplo **[!UICONTROL Uso del panel Nombres de intervalo de fechas para filtrar]** para el caso de uso:

![Valores de recuento distinto de Customer Journey Analytics](../assets/cja-using-date-range-filter-names-to-filter.png)

Observe cómo el intervalo de fechas definido en la visualización de tabla de forma libre anula el intervalo de fechas aplicado al panel.

+++

+++ Herramientas de BI

>[!PREREQUISITES]
>
>Asegúrese de que ha validado [una conexión correcta, que puede enumerar vistas de datos y que utiliza una vista de datos](connect-and-validate.md) para la herramienta de BI para la que desea probar este caso de uso.
>

>[!BEGINTABS]

>[!TAB Escritorio de Power BI]

1. En el panel **[!UICONTROL Datos]**:
   1. Seleccione **[!UICONTROL daterangemonth]**.
   1. Seleccione **[!UICONTROL daterangeName]**.
   1. Seleccione **[!UICONTROL sumar repeticiones]**.

   Verá una visualización que muestra **[!UICONTROL Error al obtener los datos de este elemento visual]**.

1. En el panel **[!UICONTROL Filtros]**:

   1. Seleccione **[!UICONTROL daterangeName is (All)]** de **[!UICONTROL Filtros en este elemento visual]**.
   1. Seleccione **[!UICONTROL Filtro básico]** como **[!UICONTROL Tipo de filtro]**.
   1. Debajo del campo **[!UICONTROL Buscar]**, seleccione **[!UICONTROL Último año 2023]**, que es el nombre del intervalo de fechas definido en Customer Journey Analytics.
   1. Seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para quitar **[!UICONTROL daterangeName]** de **[!UICONTROL Columnas]**.

   Verá la tabla actualizada con el filtro **[!UICONTROL daterangeName]** aplicado. El escritorio de Power BI debe tener el aspecto siguiente.

   ![Escritorio De Power BI Que Usa Nombres De Intervalo De Fechas Para Filtrar](../assets/uc8-powerbi-final.png)

>[!TAB Escritorio Tableau]

1. Seleccione la ficha **[!UICONTROL Hoja 1]** en la parte inferior para cambiar de **[!UICONTROL Fuente de datos]**. En la vista **[!UICONTROL Hoja 1]**:
   1. Arrastre la entrada **[!UICONTROL Daterange Name]** de la lista **[!UICONTROL Tablas]** en el estante **[!UICONTROL Filtros]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtrar \[Nombre de intervalo de fechas\]]**, asegúrese de que **[!UICONTROL Seleccionar de la lista]** está seleccionado y seleccione **[!UICONTROL Último año 2023]** de la lista. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.
   1. Arrastre la entrada **[!UICONTROL Daterangemonth]** de la lista **[!UICONTROL Tablas]** y suéltela en el campo junto a **[!UICONTROL Filas]**. Seleccione **[!UICONTROL Daterangemonth]** y seleccione **[!UICONTROL Month]**. El valor cambia a **[!UICONTROL MONTH(Daterangemonth)]**.
   1. Arrastre la entrada **[!UICONTROL Ocurrencias]** de la lista **[!UICONTROL Tablas]** y suelte la entrada en el campo junto a **[!UICONTROL Columnas]**. El valor cambia a **[!UICONTROL SUM(Occurrences)]**.
   1. Seleccione **[!UICONTROL Tabla de texto]** de **[!UICONTROL Mostrarme]**.
   1. Seleccione **[!UICONTROL Intercambiar filas y columnas]** en la barra de herramientas.
   1. Seleccione **[!UICONTROL Ajustar ancho]** del menú desplegable **[!UICONTROL Ajustar]**.

      El escritorio Tableau debe tener el aspecto siguiente.

      ![Filtro Tableau Desktop Multiple Dimension Ranked](../assets/uc8-tableau-final.png)

>[!TAB Buscador]

1. En la interfaz **[!UICONTROL Explorar]** de Looker, asegúrate de tener una configuración limpia. Si no, seleccione ![Configuración](/help/assets/icons/Setting.svg) **[!UICONTROL Quitar campos y filtros]**.
1. Seleccione **[!UICONTROL + Filtro]** debajo de **[!UICONTROL Filtros]**.
1. En el diálogo **[!UICONTROL Agregar filtro]**:
   1. Seleccionar **[!UICONTROL ‣ Vista De Datos Cc]**
   1. En la lista de campos, seleccione **[!UICONTROL ‣ Nombre del intervalo de fechas]**.
1. Especifique el filtro **[!UICONTROL Cc Data View Daterange Name]** como **[!UICONTROL is]** y seleccione **[!UICONTROL Last Year 2023]** de la lista de valores.
1. Desde la sección **[!UICONTROL ‣ Vista de datos CC]** en el carril izquierdo:
   1. Seleccione **[!UICONTROL Mes de intervalo de fechas]** y después **[!UICONTROL Mes]**.
   1. Seleccione **[!UICONTROL Count]** debajo de **[!UICONTROL MEASURES]** en el carril izquierdo (en la parte inferior).
1. Seleccione **[!UICONTROL Ejecutar]**.
1. Seleccione **[!UICONTROL ‣ visualización]**.

Debería ver una visualización y una tabla similares a las que se muestran a continuación.

![Recuento de buscadores distinto](../assets/uc8-looker-result.png)


>[!TAB Jupyter Notebook]

1. Introduzca las siguientes instrucciones en una nueva celda.

   ```python
   data = %sql SELECT daterangeName FROM cc_data_view;
   style = {'description_width': 'initial'}
   daterange_name = widgets.Dropdown(
      options=[d for d, in data],
      description='Date Range Name:',
      style=style
   )
   display(daterange_name)
   ```

1. Ejecute la celda. Debería ver una salida similar a la captura de pantalla siguiente.

   ![Resultados de Jupyter Notebook](../assets/uc8-jupyter-input.png)

1. Seleccione **[!UICONTROL Productos de pesca]** en el menú desplegable.

1. Introduzca las siguientes instrucciones en una nueva celda.

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT daterangemonth AS Month, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterangeName = '{daterange_name.value}' \
               GROUP BY 1 \
               ORDER BY Month ASC
   df = data.DataFrame()
   df = df.groupby('Month', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.lineplot(x='Month', y='Events', data=df)
   plt.show()
   display(data)
   ```

1. Ejecute la celda. Debería ver una salida similar a la captura de pantalla siguiente.

   ![Resultados de Jupyter Notebook](../assets/uc8-jupyter-results.png)


>[!TAB EstudioRS]

1. Escriba las siguientes instrucciones entre ` ` ``{r} ` y ` `` ` ` en un nuevo fragmento. Asegúrese de utilizar el nombre de intervalo de fechas adecuado. Por ejemplo, `Last Year 2023`.

   ```R
   ## Monthly Events for Last Year
   df <- dv %>%
      filter(daterangeName == "Last Year 2023") %>%
      group_by(daterangemonth) %>%
      count() %>%
      arrange(daterangemonth, .by_group = FALSE)
   ggplot(df, aes(x = daterangemonth, y = n)) +
      geom_line(color = "#69b3a2") +
      ylab("Events") +
      xlab("Hour")
   print(df)
   ```

1. Ejecuta el fragmento. Debería ver una salida similar a la captura de pantalla siguiente.

   ![Resultados de RStudio](../assets/uc8-rstudio-results.png)

>[!ENDTABS]

+++

