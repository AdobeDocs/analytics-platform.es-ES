---
title: Ordenar
description: Caso de uso de ordenación para la extensión de BI en varias herramientas de BI en Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 1%

---

# Ordenar


En este caso de uso, desea informar sobre los ingresos de compra y las compras para nombres de productos durante enero de 2023, ordenados en orden descendente de ingresos de compra.

+++ Customer Journey Analytics

Un ejemplo del panel **[!UICONTROL Ordenar]** para el caso de uso:

![Panel de orden de Customer Journey Analytics](../assets/cja-sort.png)

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

1. En el panel **[!UICONTROL Filtros]**:
   1. Seleccione **[!UICONTROL intervalo de fechas es (todo)]** de **[!UICONTROL Filtros en este elemento visual]**.
   1. Seleccione **[!UICONTROL Filtro avanzado]** como **[!UICONTROL Tipo de filtro]**.
   1. Defina el filtro para **[!UICONTROL Mostrar elementos cuando el valor]** **[!UICONTROL esté en]** `1/1/2023` **[!UICONTROL y]** **[!UICONTROL esté antes de]** `2/1/2023` o después.

1. En el panel Visualizaciones:
   1. Seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para quitar el intervalo de fechas de las columnas.
   1. Arrastre **[!UICONTROL Suma de purchase_revenue]** al final de **[!UICONTROL los elementos de la columna]**.

1. En el informe, seleccione **[!UICONTROL Sum of purchase_revenue]** para clasificar la tabla en orden descendente según los ingresos de compra.

   El escritorio de Power BI debe tener el aspecto siguiente.

   ![Escritorio De Power BI Que Usa Nombres De Intervalo De Fechas Para Filtrar](../assets/uc11-powerbi-final.png)

La consulta ejecutada por Power BI Desktop con la extensión BI no incluye una instrucción `sort`. La falta de una instrucción `sort` implica que la ordenación se ejecuta en el lado del cliente.

```sql
select "_"."product_name",
    "_"."a0",
    "_"."a1"
from 
(
    select "rows"."product_name" as "product_name",
        sum("rows"."purchases") as "a0",
        sum("rows"."purchase_revenue") as "a1"
    from 
    (
        select "_"."daterangeName",
            "_"."daterange",
            "_"."filterId",
            "_"."filterName",
            "_"."timestamp",
            "_"."affiliate_name",
            "_"."affiliate_url",
            "_"."commerce.order.priceTotal",
            "_"."customer_city",
            "_"."customer_region",
            "_"."daterangeday",
            "_"."daterangefifteenminute",
            "_"."daterangefiveminute",
            "_"."daterangehour",
            "_"."daterangeminute",
            "_"."daterangemonth",
            "_"."daterangequarter",
            "_"."daterangesecond",
            "_"."daterangethirtyminute",
            "_"."daterangeweek",
            "_"."daterangeyear",
            "_"."hitdatetime",
            "_"."page_name",
            "_"."page_url",
            "_"."product_category",
            "_"."product_name",
            "_"."product_short_review",
            "_"."product_subCategory",
            "_"."referrer_url",
            "_"."search_engine",
            "_"."search_keywords",
            "_"."store_city",
            "_"."store_name",
            "_"."store_region",
            "_"."store_type",
            "_"."timepartdayofmonth",
            "_"."timepartdayofweek",
            "_"."timepartdayofyear",
            "_"."timeparthourofday",
            "_"."timepartminuteofhour",
            "_"."timepartmonthofyear",
            "_"."timepartquarterofyear",
            "_"."timepartweekofyear",
            "_"."cm_session_end_rate_defaultmetric",
            "_"."cm_session_person_defaultmetric",
            "_"."cm_session_start_rate_defaultmetric",
            "_"."cm_timespent_person_defaultmetric",
            "_"."cm_timespent_session_defaultmetric",
            "_"."cm_product_name_count_distinct",
            "_"."ad_views",
            "_"."adobe_sessionends",
            "_"."adobe_sessionstarts",
            "_"."adobe_timespent",
            "_"."exchange_buybacks",
            "_"."exchange_cost",
            "_"."exchange_purchases",
            "_"."exchange_revenue",
            "_"."occurrences",
            "_"."page_views",
            "_"."product_quantity",
            "_"."product_reviews",
            "_"."product_views",
            "_"."purchase_revenue",
            "_"."purchases",
            "_"."visitors",
            "_"."visits"
        from "public"."cc_data_view" "_"
        where "_"."daterange" < date '2023-02-01' and "_"."daterange" >= date '2023-01-01'
    ) "rows"
    group by "product_name"
) "_"
where not "_"."a0" is null or not "_"."a1" is null
limit 1000001
```


>[!TAB Escritorio Tableau]

1. Seleccione la ficha **[!UICONTROL Hoja 1]** en la parte inferior para cambiar de **[!UICONTROL Fuente de datos]**. En la vista **[!UICONTROL Hoja 1]**:
   1. Arrastre la entrada **[!UICONTROL Daterange]** de la lista **[!UICONTROL Tablas]** en el estante **[!UICONTROL Filtros]**.
   1. En el cuadro de diálogo **[!UICONTROL Campo de filtro \[Intervalo de fechas\]]**, seleccione **[!UICONTROL Intervalo de fechas]** y seleccione **[!UICONTROL Siguiente >]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtrar \[Daterange\]]**, seleccione **[!UICONTROL Intervalo de fechas]** y seleccione `01/01/2023` - `1/2/2023`. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.
   1. Arrastre **[!UICONTROL Product Name]** de la lista **[!UICONTROL Tablas]** y suelte la entrada en el campo situado junto a **[!UICONTROL Filas]**.
   1. Arrastre la entrada **[!UICONTROL Purchases]** de la lista **[!UICONTROL Tables]** y suelte la entrada en el campo situado junto a **[!UICONTROL Columns]**. El valor cambia a **[!UICONTROL SUM(Purchases)]**.
   1. Arrastre la entrada **[!UICONTROL Ingresos de compras]** de la lista **[!UICONTROL Tablas]** y suelte la entrada en el campo junto a **[!UICONTROL Columnas]**, junto a **[!UICONTROL SUMA(Compras)]**. El valor cambia a **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Seleccione **[!UICONTROL Tabla de texto]** de **[!UICONTROL Mostrarme]**.
   1. Seleccione **[!UICONTROL Ajustar ancho]** del menú desplegable **[!UICONTROL Ajustar]**.
   1. Seleccione el encabezado de columna **[!UICONTROL Ingresos de compra]** y ordene la tabla en esta columna en orden descendente.

      El escritorio Tableau debe tener el aspecto siguiente.

      ![Orden de escritorio Tableau](../assets/uc11-tableau-final.png)

La consulta ejecutada por Tableau Desktop con la extensión BI no incluye una instrucción `sort`. La falta de esta instrucción `sort` implica que la ordenación se ejecuta en el lado del cliente.

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok",
  SUM("cc_data_view"."purchases") AS "sum:purchases:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (DATE '2023-01-01')) AND ("cc_data_view"."daterange" <= (DATE '2023-02-01')))
GROUP BY 1
```

>[!TAB Buscador]

1. En la interfaz **[!UICONTROL Explorar]** de Looker, actualice la conexión. Seleccione ![Configuración](/help/assets/icons/Setting.svg) **[!UICONTROL Borrar caché y actualizar]**.
1. En la interfaz **[!UICONTROL Explorar]** de Looker, asegúrate de tener una configuración limpia. Si no, seleccione ![Configuración](/help/assets/icons/Setting.svg) **[!UICONTROL Quitar campos y filtros]**.
1. Seleccione **[!UICONTROL + Filtro]** debajo de **[!UICONTROL Filtros]**.
1. En el diálogo **[!UICONTROL Agregar filtro]**:
   1. Seleccionar **[!UICONTROL ‣ Vista De Datos Cc]**
   1. En la lista de campos, seleccione **[!UICONTROL ‣ Daterange Date]** y después **[!UICONTROL Daterange Date]**.
      ![Filtro de búsqueda](../assets/uc2-looker-filter.png)
1. Especifique el filtro **[!UICONTROL Cc Data View Daterange Date]** ya que **[!UICONTROL está en el intervalo]** **[!UICONTROL 2023/01/01]** **[!UICONTROL hasta (antes)]** **[!UICONTROL 2023/02/01]**.
1. En la sección **[!UICONTROL ‣ Vista de datos CC]** del carril izquierdo, seleccione **[!UICONTROL Nombre de producto]**.
1. Desde la sección **[!UICONTROL ‣ Campos personalizados]** en el carril izquierdo:
   1. Seleccione **[!UICONTROL Medida personalizada]** del menú desplegable **[!UICONTROL + Agregar]**.
   1. En el diálogo **[!UICONTROL Crear medida personalizada]**:
      1. Seleccione **[!UICONTROL Ingresos de compra]** del menú desplegable **[!UICONTROL Campo para medir]**.
      1. Seleccione **[!UICONTROL Sum]** del menú desplegable **[!UICONTROL Tipo de medida]**.
      1. Escriba un nombre de campo personalizado para **[!UICONTROL Name]**. Por ejemplo: `Sum of Purchase Revenue`.
      1. Seleccione la ficha **[!UICONTROL Detalles del campo]**.
      1. Seleccione **[!UICONTROL Decimals]** del menú desplegable **[!UICONTROL Formato]** y asegúrese de que `0` se ha introducido en **[!UICONTROL Decimals]**.
         ![Campo de métrica personalizada de observador](../assets/uc5-looker-customfield.png)
      1. Seleccione **[!UICONTROL Guardar]**.
1. Asegúrese de seleccionar **[!UICONTROL ↓]** (**[!UICONTROL Orden descendente: 1]**) en la columna **[!UICONTROL Ingresos de compra]**.
1. Seleccione **[!UICONTROL Ejecutar]**.
1. Seleccione **[!UICONTROL ‣ visualización]**.

Debería ver una visualización y una tabla similares a las que se muestran a continuación.

![Recuento de buscadores distinto](../assets/uc11-looker-result.png)


La consulta generada por Looker mediante la extensión de BI incluye `ORDER BY`, lo que implica que la ordenación se ejecuta mediante Looker y la extensión de BI.

```sql
-- Looker Query Context '{"user_id":6,"history_slug":"fc83573987b999306eaf6e1a3f2cde70","instance_slug":"71d4667f0b76c0011463658f45c3f7a3"}' 
SELECT
    cc_data_view."product_name"  AS "cc_data_view.product_name",
    COALESCE(SUM(CAST(( cc_data_view."purchase_revenue"  ) AS DOUBLE PRECISION)), 0) AS "purchase_revenue"
FROM
    "public"."cc_data_view" AS "cc_data_view"
WHERE ((( cc_data_view."daterange"  ) >= (DATE_TRUNC('day', DATE '2024-01-31')) AND ( cc_data_view."daterange"  ) < (DATE_TRUNC('day', DATE '2023-02-01'))))
GROUP BY
    1
ORDER BY
    2 DESC
FETCH NEXT 500 ROWS ONLY
```


>[!TAB Jupyter Notebook]

1. Introduzca las siguientes instrucciones en una nueva celda.

   ```python
   data = %sql SELECT product_name AS `Product Name`, SUM(purchase_revenue) AS `Purchase Revenue`, SUM(purchases) AS `Purchases` \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
               GROUP BY 1 \
               ORDER BY `Purchase Revenue` DESC \
               LIMIT 5;
   display(data)
   ```

1. Ejecute la celda. Debería ver una salida similar a la captura de pantalla siguiente.

   ![Resultados de Jupyter Notebook](../assets/uc11-jupyter-results.png)

La consulta la ejecuta la extensión de BI tal como se define en Jupyter Notebook.


>[!TAB EstudioRS]

1. Escriba las siguientes instrucciones entre ` ```{r} ` y ` ``` ` en un nuevo fragmento.

   ```R
   ## Dimension 1 Sorted
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01") %>%
      group_by(product_name) %>%
      summarise(purchase_revenue = sum(purchase_revenue), purchases = sum(purchases), .groups = "keep") %>%
      arrange(desc(purchase_revenue), .by_group = FALSE)
   print(df)
   ```

1. Ejecuta el fragmento. Debería ver una salida similar a la captura de pantalla siguiente.

   ![Resultados de RStudio](../assets/uc11-rstudio-results.png)

La consulta generada por RStudio mediante la extensión de BI incluye `ORDER BY`, lo que implica que el pedido se aplica a través de RStudio y la extensión de BI.

```sql
SELECT
  "product_name",
  SUM("purchase_revenue") AS "purchase_revenue",
  SUM("purchases") AS "purchases"
FROM (
  SELECT "cc_data_view".*
  FROM "cc_data_view"
  WHERE ("daterange" >= '2023-01-01' AND "daterange" < '2023-02-01')
) AS "q01"
GROUP BY "product_name"
ORDER BY "purchase_revenue" DESC
LIMIT 1000
```

>[!ENDTABS]

+++
