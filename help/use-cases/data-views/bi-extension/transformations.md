---
title: Transformaciones
description: Caso de uso de transformaciones para la extensión BI en varias herramientas BI en Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 0%

---

# Transformaciones


Desea comprender las transformaciones de los objetos de Customer Journey Analytics, como dimensiones, métricas, filtros, métricas calculadas e intervalos de fechas, realizadas por las distintas herramientas de BI.

+++ Customer Journey Analytics

En Customer Journey Analytics, usted define en una [vista de datos](/help/data-views/data-views.md), qué componentes de sus conjuntos de datos y cómo se exponen como [dimensiones](/help/components/dimensions/overview.md) y [métricas](/help/components/apply-create-metrics.md). Esa definición de dimensión y métricas se expone a las herramientas de BI que utilizan la extensión de BI.
Utiliza componentes como [Filtros](/help/components/segments/seg-overview.md), [Métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md) e [intervalos de fechas](/help/components/date-ranges/overview.md) como parte de sus proyectos de Workspace. Estos componentes también se exponen a las herramientas de BI que utilizan la extensión de BI.

+++

+++ Herramientas de BI

>[!PREREQUISITES]
>
>Asegúrese de que ha validado [una conexión correcta, que puede enumerar vistas de datos y que utiliza una vista de datos](connect-and-validate.md) para la herramienta de BI para la que desea probar este caso de uso.
>

>[!BEGINTABS]

>[!TAB Escritorio de Power BI]

Los objetos Customer Journey Analytics están disponibles en el panel **[!UICONTROL Datos]** y se recuperan de la tabla seleccionada en Power BI Desktop. Por ejemplo, **[!UICONTROL public.cc_data_view]**. El nombre de la tabla es el mismo que el ID externo definido para la vista de datos en Customer Journey Analytics. Por ejemplo, la vista de datos con **[!UICONTROL Título]** `C&C - Data View` y **[!UICONTROL Id. externo]** `cc_data_view`.

**Dimensiones**
Las dimensiones de Customer Journey Analytics se identifican con el [!UICONTROL ID de componente]. El [!UICONTROL ID de componente] está definido en la vista de datos de Customer Journey Analytics. Por ejemplo, la dimensión **[!UICONTROL Product Name]** de Customer Journey Analytics tiene un [!UICONTROL ID de componente] **[!UICONTROL product_name]**, que es el nombre de la dimensión en Power BI Desktop.
Las dimensiones de intervalo de fechas de Customer Journey Analytics como **[!UICONTROL Day]**, **[!UICONTROL Week]**, **[!UICONTROL Month]** y más están disponibles como **[!UICONTROL daterangeday]**, **[!UICONTROL daterangeweek]**, **[!UICONTROL daterangemonth]** y más.

**Métricas**
Las métricas de Customer Journey Analytics se identifican con el [!UICONTROL ID de componente]. El [!UICONTROL ID de componente] está definido en la vista de datos de Customer Journey Analytics. Por ejemplo, la métrica **[!UICONTROL Ingresos de compra]** en Customer Journey Analytics tiene un [!UICONTROL ID de componente] **[!UICONTROL purchase_revenue]**, que es el nombre de la métrica en Power BI Desktop. Un **[!UICONTROL ∑]** indica las métricas. Cuando se usa una métrica en cualquier visualización, se cambia el nombre de la métrica a **[!UICONTROL Suma de *métrica *]**.

**Filtros**
Los filtros que defina en Customer Journey Analytics están disponibles como parte del campo **[!UICONTROL filterName]**. Cuando usa un campo **[!UICONTROL filterName]** en Power BI Desktop, puede especificar qué filtro utilizar.

**Métricas calculadas**
Las métricas calculadas que define en Customer Journey Analytics se identifican con el [!UICONTROL ID externo] que ha definido para la métrica calculada. Por ejemplo, la métrica calculada **[!UICONTROL Product Name (Count Distinct)]** tiene [!UICONTROL ID externo] **[!UICONTROL product_name_count_distinct]** y se muestra como **[!UICONTROL cm_product_name_count_distinct]**&#x200B;t en Power BI Desktop.

**Intervalos de fechas**
Los intervalos de fechas que defina en Customer Journey Analytics están disponibles como parte del campo **[!UICONTROL intervaloDeFechas]**. Cuando usa un campo **[!UICONTROL daterangeName]**, puede especificar qué intervalo de fecha usar.

**Transformaciones personalizadas**
Power BI Desktop proporciona funcionalidad de transformación personalizada mediante [expresiones de análisis de datos (DAX)](https://learn.microsoft.com/en-us/dax/dax-overview). Por ejemplo, desea ejecutar el caso de uso [Single dimension ranked](#single-dimension-ranked) con nombres de productos en minúsculas.

1. En la vista Informe, seleccione la visualización de barras.
1. Seleccione **[!UICONTROL product_name]** en el panel Datos.
1. Seleccione **[!UICONTROL Nueva columna]** en la barra de herramientas.
1. En el editor de fórmulas, defina una nueva columna denominada `product_name_lower`, como `product_name_lower = LOWER('public.cc_data_view[product_name])`.
   ![Transformación de Power BI Desktop a Lower](../assets/uc14-powerbi-transformation.png)
1. Asegúrese de seleccionar la nueva columna **[!UICONTROL product_name_lower]** en el panel **[!UICONTROL Datos]** en lugar de la columna **[!UICONTROL product_name]**.
1. Seleccione **[!UICONTROL Informar como tabla]** de ![Más](/help/assets/icons/More.svg) en la visualización de tabla.

   El escritorio de Power BI debe tener el aspecto siguiente.
   ![Final de transformación de escritorio de Power BI](../assets/uc14-powerbi-final.png)

La transformación personalizada resulta en una actualización de las consultas SQL. Consulte el uso de la función `lower` en el siguiente ejemplo de SQL:

```sql
select "_"."product_name_lower",
    "_"."a0",
    "_"."a1"
from 
(
    select "rows"."product_name_lower" as "product_name_lower",
        sum("rows"."purchases") as "a0",
        sum("rows"."purchase_revenue") as "a1"
    from 
    (
        select "_"."daterange" as "daterange",
            "_"."product_name" as "product_name",
            "_"."purchase_revenue" as "purchase_revenue",
            "_"."purchases" as "purchases",
            lower("_"."product_name") as "product_name_lower"
        from 
        (
            select "_"."daterange",
                "_"."product_name",
                "_"."purchase_revenue",
                "_"."purchases"
            from 
            (
                select "daterange",
                    "product_name",
                    "purchase_revenue",
                    "purchases"
                from "public"."cc_data_view" "$Table"
            ) "_"
            where ("_"."daterange" < date '2024-01-01' and "_"."daterange" >= date '2023-01-01') and ("_"."product_name" in ('4G Cellular Trail Camera', '4K Wildlife Trail Camera', 'Wireless Trail Camera', '8-Person Cabin Tent', '20MP No-Glow Trail Camera', 'HD Wildlife Camera', '4-Season Mountaineering Tent', 'Trail Camera', '16MP Trail Camera with Solar Panel', '10-Person Family Tent'))
        ) "_"
    ) "rows"
    group by "product_name_lower"
) "_"
where not "_"."a0" is null or not "_"."a1" is null
limit 1000001
```

>[!TAB Escritorio Tableau]

Los objetos Customer Journey Analytics están disponibles en la barra lateral **[!UICONTROL Datos]** siempre que trabaje en una hoja. Y se recuperan de la tabla que ha seleccionado como parte de la página **[!UICONTROL Fuente de datos]** en Tableau. Por ejemplo, **[!UICONTROL cc_data_view]**. El nombre de la tabla es el mismo que el ID externo definido para la vista de datos en Customer Journey Analytics. Por ejemplo, la vista de datos con **[!UICONTROL Título]** `C&C - Data View` y **[!UICONTROL Id. externo]** `cc_data_view`.

**Dimensiones**
Las dimensiones de Customer Journey Analytics se identifican con el [!UICONTROL nombre del componente]. El [!UICONTROL nombre del componente] está definido en la vista de datos de Customer Journey Analytics. Por ejemplo, la dimensión **[!UICONTROL Nombre de producto]** en Customer Journey Analytics tiene un [!UICONTROL Nombre de componente] **[!UICONTROL Nombre de producto]**, que es el nombre de la dimensión en Tableau. **[!UICONTROL Abc]** identifica todas las dimensiones.
Las dimensiones de intervalo de fechas de Customer Journey Analytics como **[!UICONTROL Day]**, **[!UICONTROL Week]**, **[!UICONTROL Month]** y más están disponibles como **[!UICONTROL Daterangeday]**, **[!UICONTROL Daterangeweek]**, **[!UICONTROL Daterangemonth]** y más. Cuando se utiliza una dimensión de intervalo de fechas, se debe seleccionar una definición adecuada de fecha u hora para aplicarla a esa dimensión de intervalo de fechas en el menú desplegable. Por ejemplo, **[!UICONTROL Year]**, **[!UICONTROL Quarter]**, **[!UICONTROL Month]**, **[!UICONTROL Day]**.

**Métricas**
Las métricas de Customer Journey Analytics se identifican con el [!UICONTROL Nombre del componente]. El [!UICONTROL Nombre de componente] está definido en la vista de datos de Customer Journey Analytics. Por ejemplo, la métrica **[!UICONTROL Ingresos de compras]** en Customer Journey Analytics tiene un [!UICONTROL Nombre de componente] **[!UICONTROL Ingresos de compras]**, que es el nombre de la métrica en Tableau. **[!UICONTROL #]** identifica todas las métricas. Cuando usa una métrica en cualquier visualización, se cambia el nombre de la métrica a **[!UICONTROL Sum(*metric*)]**.

**Filtros**
Los filtros que defina en Customer Journey Analytics están disponibles como parte del campo **[!UICONTROL Nombre del filtro]**. Cuando usa un campo **[!UICONTROL Nombre del filtro]** en Tableau, puede especificar qué filtro utilizar.

**Métricas calculadas**
Las métricas calculadas que define en Customer Journey Analytics se identifican con el [!UICONTROL Título] que ha definido para la métrica calculada. Por ejemplo, la métrica calculada **[!UICONTROL Product Name (Count Distinct)]** tiene [!UICONTROL Title] **[!UICONTROL Product Name (Count Distinct)]** y se muestra como **[!UICONTROL Cm Product Name Count Distinct]** en Tableau.

**Intervalos de fechas**
Los intervalos de fechas que defina en Customer Journey Analytics están disponibles como parte del campo **[!UICONTROL Nombre del intervalo de fechas]**. Cuando usa un campo **[!UICONTROL Nombre del intervalo de fechas]**, puede especificar qué intervalo de fechas utilizar.

**Transformaciones personalizadas**
Tableau Desktop proporciona funcionalidad de transformación personalizada mediante [Campos calculados](https://help.tableau.com/current/pro/desktop/en-us/calculations_calculatedfields_create.htm). Por ejemplo, desea ejecutar el caso de uso [Single dimension ranked](#single-dimension-ranked) con nombres de productos en minúsculas.

1. Seleccione **[!UICONTROL Análisis]** > **[!UICONTROL Crear campo calculado]** en el menú principal.
   1. Defina **[!UICONTROL Nombre de producto en minúsculas]** con la función `LOWER([Product Name])`.
      ![Campo calculado Tableau](../assets/uc14-tableau-calculated-field.png)
   1. Seleccione **[!UICONTROL Aceptar]**.
1. Seleccione la hoja **[!UICONTROL Data]**.
   1. Arrastre **[!UICONTROL Nombre de producto en minúsculas]** de **[!UICONTROL Tablas]** y suelte la entrada en el campo junto a **[!UICONTROL Filas]**.
   1. Quitar **[!UICONTROL Nombre de producto]** de **[!UICONTROL Filas]**.
1. Seleccione la vista **[!UICONTROL Panel 1]**.

El escritorio Tableau debe tener el aspecto siguiente.

![Tableau Desktop después de la transformación](../assets/uc14-tableau-final.png)

El resultado de la transformación personalizada es una actualización de las consultas SQL. Consulte el uso de la función `LOWER` en el siguiente ejemplo de SQL:

```sql
SELECT LOWER(CAST(CAST("cc_data_view"."product_name" AS TEXT) AS TEXT)) AS "Calculation_1562467608097775616",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok",
  SUM("cc_data_view"."purchases") AS "sum:purchases:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (DATE '2023-01-01')) AND ("cc_data_view"."daterange" <= (DATE '2023-12-31')))
GROUP BY 1
HAVING ((SUM("cc_data_view"."purchase_revenue") >= 999999.99999998999) AND (SUM("cc_data_view"."purchase_revenue") <= 2000000.00000002))
```

>[!TAB Buscador]

Los objetos Customer Journey Analytics están disponibles en la interfaz **[!UICONTROL Explorar]**. Y se recuperan como parte de la configuración de la conexión, el proyecto y el modelo en Looker. Por ejemplo, **[!UICONTROL cc_data_view]**. El nombre de la vista es el mismo que el ID externo definido para la vista de datos en Customer Journey Analytics. Por ejemplo, la vista de datos con **[!UICONTROL Título]** `C&C - Data View` y **[!UICONTROL Id. externo]** `cc_data_view`.

**Dimensiones**
Las dimensiones de Customer Journey Analytics se muestran como **[!UICONTROL DIMENSION]** en el carril izquierdo de **[!UICONTROL Cc Data View]**. La dimensión se define en la vista de datos de Customer Journey Analytics. Por ejemplo, la dimensión **[!UICONTROL Product Name]** de Customer Journey Analytics tiene un **[!UICONTROL DIMENSION]** **[!UICONTROL Product Name]**, que es el nombre de la dimensión en Looker.
Las dimensiones de intervalo de fechas de Customer Journey Analytics como **[!UICONTROL Day]**, **[!UICONTROL Week]**, **[!UICONTROL Month]** y más están disponibles como **[!UICONTROL Daterangeday Date]**, **[!UICONTROL Daterangeweek Date]**, **[!UICONTROL Daterangemonth Date]** y más.  Cuando se utiliza una dimensión de intervalo de fechas, se debe seleccionar una definición adecuada de fecha u hora. Por ejemplo, **[!UICONTROL Year]**, **[!UICONTROL Quarter]**, **[!UICONTROL Month]**, **[!UICONTROL Date]**.

**Métricas**
Las métricas de Customer Journey Analytics se muestran como **[!UICONTROL DIMENSION]** en en el carril izquierdo de **[!UICONTROL Cc Data View]**. Por ejemplo, la métrica **[!UICONTROL Ingresos de compras]** en Customer Journey Analytics tiene **[!UICONTROL DIMENSION]** **[!UICONTROL Ingresos de compras]**. Para utilizar realmente como métrica, cree un campo de medida personalizado como se muestra en los ejemplos anteriores, o utilice el acceso directo en una dimensión. Por ejemplo, **[!UICONTROL ⋮]**, seleccione **[!UICONTROL Agregado]** y, a continuación, seleccione **[!UICONTROL Suma]**.

**Filtros**
Los filtros que defina en Customer Journey Analytics están disponibles como parte del campo **[!UICONTROL Nombre del filtro]**. Cuando usa un campo **[!UICONTROL Nombre de filtro]** en el Buscador, puede especificar qué filtro utilizar.

**Métricas calculadas**
Las métricas calculadas que define en Customer Journey Analytics se identifican con el [!UICONTROL Título] que ha definido para la métrica calculada. Por ejemplo, la métrica calculada **[!UICONTROL Product Name (Count Distinct)]** tiene [!UICONTROL Title] **[!UICONTROL Product Name (Count Distinct)]** y se muestra como **[!UICONTROL Cm Product Name Count Distinct]** en Looker.

**Intervalos de fechas**
Los intervalos de fechas que defina en Customer Journey Analytics están disponibles como parte del campo **[!UICONTROL Nombre del intervalo de fechas]**. Cuando usa un campo **[!UICONTROL Nombre del intervalo de fechas]**, puede especificar qué intervalo de fechas utilizar.

**Transformaciones personalizadas**
Looker proporciona una funcionalidad de transformación personalizada mediante generadores de campos personalizados, como se muestra arriba. Por ejemplo, desea ejecutar el caso de uso [Single dimension ranked](#single-dimension-ranked) con nombres de productos en minúsculas.

1. Desde la sección **[!UICONTROL ‣ Campos personalizados]** en el carril izquierdo:
   1. Seleccione **[!UICONTROL Dimension personalizado]** del menú desplegable **[!UICONTROL + Agregar]**.
   1. Escriba `lower(${cc_data_view.product_name})` en el área de texto **[!UICONTROL Expresión]**. Se le ayudará con la sintaxis correcta cuando empiece a escribir `Product Name`.
      ![Ejemplo de transformación de localizador](../assets/uc14-looker-transformation.png)
   1. Escriba `product name` como **[!UICONTROL Nombre]**.
   1. Seleccione **[!UICONTROL Guardar]**.

Debería ver una tabla similar como se muestra a continuación.

![Resultado de transformación del buscador](../assets/uc14-looker-result.png)


El resultado de la transformación personalizada es una actualización de las consultas SQL. Consulte el uso de la función `LOWER` en el siguiente ejemplo de SQL:

```sql
SELECT
    LOWER((cc_data_view."product_name")) AS "product_name",
    COALESCE(SUM(CAST(( cc_data_view."purchase_revenue"  ) AS DOUBLE PRECISION)), 0) AS "sum_of_purchase_revenue",
    COALESCE(SUM(CAST(( cc_data_view."purchases"  ) AS DOUBLE PRECISION)), 0) AS "sum_of_purchases"
FROM public.cc_data_view  AS cc_data_view
WHERE ((( cc_data_view."daterange"  ) >= (DATE_TRUNC('day', DATE '2023-01-01')) AND ( cc_data_view."daterange"  ) < (DATE_TRUNC('day', DATE '2024-01-01'))))
GROUP BY
    1
ORDER BY
    2 DESC
FETCH NEXT 500 ROWS ONLY
```

>[!TAB Jupyter Notebook]

Los objetos de Customer Journey Analytics (dimensiones, métricas, filtros, métricas calculadas e intervalos de fechas) están disponibles como parte de las consultas SQL incrustadas que cree. Consulte ejemplos anteriores.

**Transformaciones personalizadas**

1. Introduzca las siguientes instrucciones en una nueva celda.

   ```python
   data = %sql SELECT LOWER(product_category) AS `Product Category`, COUNT(*) AS EVENTS \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01' \
               GROUP BY 1 \
               ORDER BY `Events` DESC \
               LIMIT 5;
   display(data)
   ```

1. Ejecute la celda. Debería ver una salida similar a la captura de pantalla siguiente.

   ![Resultados de Jupyter Notebook](../assets/uc13-jupyter-results.png)

La consulta la ejecuta la extensión de BI tal como se define en Jupyter Notebook.

>[!TAB EstudioRS]

Los componentes de Customer Journey Analytics (dimensiones, métricas, filtros, métricas calculadas e intervalos de fechas) están disponibles como objetos con nombres similares en el lenguaje R. Consulte los componentes que utilizan el componente Consulte ejemplos anteriores.

**Transformaciones personalizadas**

1. Escriba las siguientes instrucciones entre ` ` ``{r} ` y ` `` ` ` en un nuevo fragmento.

   ```R
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange <= "2024-01-01") %>%
      mutate(d2=lower(product_category)) %>%
      group_by(d2) %>%
      count() %>%
      arrange(d2, .by_group = FALSE)
   print(df)
   ```

1. Ejecuta el fragmento. Debería ver una salida similar a la captura de pantalla siguiente.

   ![Resultados de RStudio](../assets/uc13-rstudio-results.png)

La consulta generada por RStudio mediante la extensión de BI incluye `lower`, lo que implica que RStudio y la extensión de BI ejecutan la transformación personalizada.

```sql
SELECT "d2", COUNT(*) AS "n"
FROM (
  SELECT "cc_data_view".*, lower("product_category") AS "d2"
  FROM "cc_data_view"
  WHERE ("daterange" >= '2023-01-01' AND "daterange" <= '2024-01-01')
) AS "q01"
GROUP BY "d2"
ORDER BY "d2"
LIMIT 1000
```

>[!ENDTABS]

+++

