---
title: Conector SQL
description: Aprenda cómo puede utilizar Query Service, Power BI o Tableau para acceder a las Vistas de datos mediante el Conector SQL.
solution: Customer Journey Analytics
feature: Data Views
hide: true
hidefromtoc: true
source-git-commit: 7d072538c42210f5de7c9c38df05423350e694b0
workflow-type: tm+mt
source-wordcount: '2879'
ht-degree: 2%

---

# Conector SQL

{{release-limited-testing}}

La variable [!DNL Customer Journey Analytics (CJA) SQL Connector] habilita el acceso SQL a la variable [vistas de datos](./data-views.md) que ha definido en CJA. Es posible que sus ingenieros y analistas de datos estén más familiarizados con Power BI, Tableau u otras herramientas de visualización e inteligencia empresarial (también denominadas herramientas de BI). Ahora pueden crear informes y tableros basados en las mismas vistas de datos que utilizan los usuarios de CJA al crear sus proyectos de Analysis Workspace.

Adobe Experience Platform [Servicio de consultas](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=es) es la interfaz SQL a los datos disponibles en el lago de datos de Experience Platform. Con la variable [!DNL CJA SQL Connector] activada, la funcionalidad de [!DNL Query Service] se amplía para ver sus vistas de datos de CJA como tablas o vistas en un [!DNL Query Service] sesión. Como resultado, las herramientas de inteligencia empresarial que utilizan [!DNL Query Service] ya que su interfaz PostgresSQL se beneficia sin problemas de esta amplia funcionalidad.

Los principales beneficios son:

- No es necesario volver a crear una representación equivalente de las vistas de datos de CJA dentro de la propia herramienta BI. <br/>Consulte [Vista de datos](data-views.md) para obtener más información sobre la funcionalidad de las vistas de datos para comprender lo que se debe recrear.<br/>

- Buena coherencia en informes y análisis entre las herramientas de BI y CJA.

- Combine los datos de CJA con otras fuentes de datos ya disponibles en las herramientas de BI.

## Requisitos previos

Para utilizar esta funcionalidad, debe

- Active la variable [!UICONTROL Conector SQL de CJA] en su organización Experience Platform.

- Configure la funcionalidad para los perfiles de producto, grupos de usuarios o usuarios individuales relevantes.<br/>
Los usuarios deben tener acceso a:
   - Servicio de Consulta de Experience Platform,
   - proyectos de CJA Workspace y
   - Las vistas de datos de CJA que desean utilizar.

- Utilice la caducidad de las credenciales no caducadas para conectar las herramientas de BI al conector SQL de CJA. Consulte [Guía de credenciales](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=en) para obtener más información sobre la configuración de credenciales que caducan o credenciales que no caducan.


## Uso

Para usar la variable [!DNL CJA SQL Connector] , puede utilizar SQL directamente o utilizar la experiencia de arrastrar y soltar disponible en la herramienta BI específica.

### SQL

Puede utilizar la funcionalidad directamente en instrucciones SQL utilizando el Editor de consultas o un cliente estándar de la interfaz de línea de comandos (CLI) PostgresSQL.

+++ Editor de consultas

En la interfaz de usuario del Experience Platform:

1. Select **[!UICONTROL ** Consultas **]** from **[!UICONTROL ** ADMINISTRACIÓN DE DATOS **]** en el carril izquierdo.

2. Select ![Crear consulta](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL ** Crear consulta **]**.

3. Para ejecutar la consulta, escriba la instrucción SQL y seleccione la ![Play](assets/Smock_Play_18_N.svg) (o pulse MAYÚS + ENTRAR).

+++


+++ CLI PostgresSQL

1. En la interfaz de usuario del Experience Platform, busque y copie las credenciales de PostgresSQL:

   1. Select **[!UICONTROL ** Consultas **]** desde el carril izquierdo (debajo de **[!UICONTROL ** ADMINISTRACIÓN DE DATOS **]**).

   2. Select **[!UICONTROL ** Credenciales **]** en la barra superior.

   3. Para copiar la cadena de conexión, utilice ![Copiar](assets/Smock_Copy_18_N.svg) en el **[!UICONTROL ** PSQL, comando **]** para obtener más información.

2. Abra la CLI de PostgresSQL.

3. Para iniciar sesión e iniciar la ejecución de sus consultas, pegue la cadena de conexión en la CLI de PostgresSQL.

+++

Consulte [Guía de la interfaz de usuario del Editor de consultas](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=en) para obtener más información.


### Herramientas de BI

Actualmente, el conector SQL de CJA es compatible con Power BI y Tableau.

+++ Power BI

1. En la interfaz de usuario de Adobe Experience Platform, busque los detalles de sus credenciales PostgresSQL.

   1. Select **[!UICONTROL ** Consultas **]** desde el carril izquierdo (debajo de **[!UICONTROL ** ADMINISTRACIÓN DE DATOS **]**).

   2. Select **[!UICONTROL ** Credenciales **]** en la barra superior.

   3. Uso ![Copiar](assets/Smock_Copy_18_N.svg) para copiar cada uno de los parámetros de credenciales de Postgres ([!UICONTROL Host], [!UICONTROL Puerto], [!UICONTROL Base de datos], [!UICONTROL Nombre de usuario], y otros) cuando sea necesario en Power BI.

2. En Power BI:

   1. En la ventana principal, seleccione **[!UICONTROL ** Obtención de datos **]** en la barra de herramientas superior.

   2. Select **[!UICONTROL ** Más...**]** en el carril izquierdo.

   3. En el **Obtener datos** pantalla, buscar `PostgresSQL` y seleccione **[!UICONTROL ** Base de datos PostgresSQL **]** de la lista.

   4. En el **[!UICONTROL ** Base de datos PostgressSQL **]** diálogo:

      1. Pegar **[!UICONTROL ** Host **]** parámetro de consultas de Experience Platform [!UICONTROL Credenciales] into **[!UICONTROL ** Servidor **]** campo de texto.

      2. Pegar **[!UICONTROL ** Base de datos **]** parámetro de consultas de Experience Platform [!UICONTROL Credenciales] en **[!UICONTROL ** Base de datos **]** campo de texto.

         Agregar `?FLATTEN` a **[!UICONTROL ** Base de datos **]** para que parezca `prod:all?FLATTEN` por ejemplo. Consulte [Acoplar estructuras de datos anidadas para usarlas con herramientas de BI de terceros](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) para obtener más información.

      3. Cuando se le pida que **[!UICONTROL ** Conectividad de datos **]** modo, seleccione **[!UICONTROL ** DirectQuery **]** para garantizar que las estructuras de datos se acoplan correctamente.

      4. Se le pedirá que **[!UICONTROL ** Nombre de usuario **]** y **[!UICONTROL ** Contraseña **]**. Usar parámetros equivalentes de consultas de Experience Platform [!UICONTROL Credenciales].
   5. Después de iniciar sesión correctamente, las tablas de vista de datos de CJA aparecen en el informe de **[!UICONTROL ** Navegador **]**. Las tablas de la vista de datos se identifican utilizando `dv_` en sus nombres.


   6. Seleccione las tablas de vista de datos que desee utilizar y seleccione **[!UICONTROL ** Cargar **]**.

   Todas las dimensiones y métricas asociadas con una o más tablas seleccionadas aparecen en el panel derecho, listo para su uso en las visualizaciones.

   Consulte [Conectar Power BI al servicio de consulta](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=en) para obtener más información.

+++

+++Tableau

1. En la interfaz de usuario del Experience Platform, busque los detalles de sus credenciales PostgresSQL.

   1. Select **[!UICONTROL ** Consultas **]** desde el carril izquierdo (debajo de **[!UICONTROL ** ADMINISTRACIÓN DE DATOS **]**).

   2. Select **[!UICONTROL ** Credenciales **]** en la barra superior.

   3. Uso ![Copiar](assets/Smock_Copy_18_N.svg) para copiar cada uno de los parámetros de credenciales de Postgres ([!UICONTROL Host], [!UICONTROL Puerto], [!UICONTROL Base de datos], [!UICONTROL Nombre de usuario], y otros) cuando sea necesario en Tableau.

2. En Tableau:

   1. Select **[!UICONTROL ** Más **]** from **[!UICONTROL ** A un servidor **]** en el carril izquierdo.

   2. Select **[!UICONTROL ** PostgresSQL **]** de la lista.

   3. En el [!UICONTROL PostgresSQL] diálogo:

      1. Pegar **[!UICONTROL ** Host **]** parámetro de consultas de Experience Platform [!UICONTROL Credenciales] into **[!UICONTROL ** Servidor **]** campo de texto.

      2. Pegar **[!UICONTROL ** Puerto **]** parámetro de consultas de Experience Platform [!UICONTROL Credenciales] into **[!UICONTROL ** Puerto **]** campo de texto.

      3. Pegar **[!UICONTROL ** Base de datos **]** parámetro de consultas de Experience Platform [!UICONTROL Credenciales] into **[!UICONTROL ** Base de datos **]** campo de texto.

         Agregar `%3FFLATTEN` a **[!UICONTROL ** Base de datos **]** para que parezca `prod:all%3FFLATTEN` por ejemplo. Consulte [Acoplar estructuras de datos anidadas para usarlas con herramientas de BI de terceros](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) para obtener más información.

      4. Select **[!UICONTROL ** Nombre de usuario y contraseña **]** from **[!UICONTROL ** Autenticación **]** lista.

      5. Pegar **[!UICONTROL ** Nombre de usuario **]** parámetro de consultas de Experience Platform [!UICONTROL Credenciales] into **[!UICONTROL ** Nombre de usuario **]** campo de texto.

      6. Pegar **[!UICONTROL ** Contraseña **]** parámetro de consultas de Experience Platform [!UICONTROL Credenciales] into **[!UICONTROL ** Contraseña **]** campo de texto.

      7. Select **[!UICONTROL ** Iniciar sesión **]**.
   4. Las vistas de datos de CJA aparecen como tablas en la **[!UICONTROL ** Tabla **]** lista. El prefijo de las tablas de vista de datos es `dv_`.

   5. Arrastre las tablas que desee utilizar en el lienzo.

   Ahora puede trabajar con los datos de las tablas de vista de datos para crear sus informes y visualizaciones.

   Consulte [Conexión de Tableau al servicio de consulta](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=en) para obtener más información.

+++

Consulte [Conectar clientes con el servicio de consulta](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en) para obtener información general y más información sobre las distintas herramientas disponibles.

## Funcionalidad

De forma predeterminada, las vistas de datos tienen un nombre seguro para la tabla generado a partir de su nombre descriptivo. Por ejemplo, la vista de datos denominada [!UICONTROL Mis datos web] tiene el nombre de vista `dv_my_web_data`.

Si desea utilizar los ID de vista de datos como nombres de tabla, puede agregar la variable opcional `CJA_USE_IDS` al conectar. Por ejemplo, `prod:all?CJA_USE_IDS` muestra sus vistas de datos con nombres como `dv_ABC123`.

### Gobernanza de datos

La configuración relacionada con el control de datos en Customer Journey Analytics se hereda de Adobe Experience Platform. La integración entre CJA y Gobernanza de datos de Adobe Experience Platform permite el etiquetado de datos de CJA confidenciales y la aplicación de directivas de privacidad.

Las etiquetas y directivas de privacidad creadas en conjuntos de datos consumidos por Experience Platform se pueden ver en el flujo de trabajo de vistas de datos de CJA. Por lo tanto, los datos consultados mediante el conector SQL de CJA muestran advertencias o errores adecuados cuando no se cumplen las etiquetas y políticas de privacidad definidas.

### Vistas de datos de lista

En la CLI estándar de PostgreSQL, puede enumerar sus vistas mediante `\dv`

```sql
prod:all=> \dv
                                     List of relations
 Schema |                              Name                              | Type |  Owner             
--------+----------------------------------------------------------------+------+----------
 public | dv_adobe_analytics_spa                                         | view | postgres
 public | dv_adobe_analytics_spa_cja_adobe_users_only_                   | view | postgres
 public | dv_adobe_analytics_spa_cja_customers_only_                     | view | postgres
 public | dv_adobe_analytics_spa_core_aa_only_                           | view | postgres
 public | dv_adobe_analytics_spa_trad_aa_customers_only_                 | view | postgres
 public | dv_cja_audit_logs                                              | view | postgres
 public | dv_cja_connections_ui_prod_analytics_format_                   | view | postgres
 public | dv_cja_for_adobe_spark_usage                                   | view | postgres
 public | dv_cja_new_dimesnions                                          | view | postgres
 public | dv_cja_test_dimensions                                         | view | postgres
 public | dv_cja_usage_account_based_customers_only_                     | view | postgres
 public | dv_combined_trad_aa_apps                                       | view | postgres
 public | dv_customer_journey_analytics_sc_demo_users_                   | view | postgres
```

### Anidado frente a aplanado

De forma predeterminada, el esquema de las vistas de datos utiliza estructuras anidadas, al igual que los esquemas XDM originales. La integración también admite el `FLATTEN` . Puede utilizar esta opción para forzar que se aplana el esquema de las vistas de datos (y cualquier otra tabla de la sesión). El acoplamiento permite un uso más sencillo en las herramientas de BI que no admiten esquemas estructurados. Consulte [Trabajo con estructuras de datos anidadas en el servicio de consulta](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) para obtener más información.

### SQL compatible

Consulte [Referencia SQL del servicio de consulta](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=en) para obtener la referencia completa sobre qué tipo de SQL se admite.

Consulte la tabla Patrones a continuación para obtener una descripción general de los patrones y ejemplos.

+++Patrones

| Patrón | Ejemplo |
|---|---|
| Detección de esquemas | <pre>SELECCIONE * DESDE Dv1 DONDE 1=0</pre> |
| Clasificación/Desglose | <pre>SELECT dim1, SUM(metric1) AS m1<br/>DESDE dv1<br/>DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;<br/>AGRUPAR POR dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>DESDE dv1<br/>DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39; Y<br/>  filterId = &#39;12345&#39;<br/>AGRUPAR POR dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>DESDE dv1<br/>DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39; Y<br/>  AND (dim2 = &#39;A&#39; O dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;)<br/>AGRUPAR POR dim1</pre> |
| cláusula HAVING | <pre>SELECT dim1, SUM(metric1) AS m1<br/>DESDE dv1<br/>DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;<br/>AGRUPAR POR dim1<br/>TENIENDO m1 > 100 |
| Distinto, superior <br/>valores de dimensión | <pre>SELECCIONE DISTINCT dim1 DESDE dv1</pre><pre>SELECT dim1 AS dv1<br/>DESDE dv1<br/>DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;<br/>AGRUPAR POR dim1</pre><pre>SELECT dim1 AS dv1<br/>DESDE dv1<br/>WHERE \`timestamp\` >= &#39;2022-01-01&#39; Y \`timestamp\` &lt; &#39;2022-01-02&#39;<br/>AGRUPAR POR dim1<br/>ORDER BY SUM(metric1)<br/>LÍMITE 15</pre> |
| Totales de métricas | <pre>SELECCIONE SUM(metric1) AS m1<br/>DESDE dv1<br/>DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;</pre> |
| Varias dimensiones<br/>desgloses<br/>y distinciones superiores | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>DESDE dv1<br/>DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;<br/>AGRUPAR POR dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>DESDE dv1<br/>DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;<br/>AGRUPAR POR 1, 2<br/>ORDEN DE 1, 2</pre><pre>SELECCIONE DISTINCT dim1, dim2<br/>DESDE dv1</pre> |
| Selección secundaria:<br/>Resultado adicional<br/>filtrado | <pre>SELECT dim1, m1<br/>DE (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  DESDE dv1<br/>  DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;</br>  AGRUPAR POR dim1<br/>)<br/>WHERE dim1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| Selección secundaria:<br/>Unirse a<br/>el conjunto de datos no está en<br/>CJA | <pre>SELECT b.key, a.dim1, a.m1<br/>DE (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  DESDE dv1<br/>  DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;<br/>  AGRUPAR POR dim1<br/>) a<br/>BÚSQUEDAS DE UNIÓN IZQUIERDA b ON a.dim1 = b.key</pre> |
| Selección secundaria:<br/>Realización de consultas entre<br/>vistas de datos | <pre>Clave SELECT, SUM(m1) AS total<br/>DE (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  DESDE dv1<br/>  DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;<br/>  AGRUPAR POR dim1<br/><br/>  UNIÓN<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  DE dv2<br/>  DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;<br/>  AGRUPAR POR dim2<br/>AGRUPAR POR clave<br/>ORDEN POR total</pre> |
| Selección secundaria: <br/>Origen en capas, <br/>filtrado, <br/>y agregación | Capas con subselecciones:<br><pre>SELECCIONE rows.dim1, SUM(rows.m1) COMO total<br/>DE (<br/>  SELECCIONE \_.dim1,\_.m1<br/>  DE (<br/>    SELECCIONE \* DESDE Dv1<br/>    DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;<br/>  ) \_<br/>  WHERE \_.dim1 in (&quot;A&quot;, &quot;B&quot;, &quot;C&quot;)<br/>filas )<br/>AGRUPAR POR 1<br/>ORDEN POR total</pre><br/>Capas que utilizan CTE CON:<br/><pre>CON filas como (<br/>  CON \_ AS (<br/>    SELECT * FROM data_ares<br/>    DONDE \`timestamp\` ENTRE &#39;2021-01-01&#39; Y &#39;2021-02-01&#39;<br/>  )<br/>  SELECCIONE _.item, _.unit DE _<br/>  DONDE _.item NO ES NULO<br/>)<br/>SELECCIONE rows.item, SUM(rows.Units) COMO unidades<br/>DE filas WHERE rows.item en (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>AGRUPAR POR filas.elemento</pre> |
| Selecciona dónde está la variable<br/>métricas anteriores<br/> o se mezclan con<br/>las dimensiones | <pre>SELECT SUM(metric1) AS m1, dim1<br/>DESDE dv1<br/>DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;<br/>GRUPO POR 2</pre> |

{style="table-layout:auto"}

+++

### Dimensiones

Puede seleccionar cualquiera de las dimensiones disponibles de forma predeterminada o definidas en la vista de datos. Puede seleccionar una dimensión por su ID.

### Métricas

Las métricas disponibles para seleccionar son:

- cualquiera de las métricas disponibles de forma predeterminada,

- definida en la vista de datos,

- métricas calculadas compatibles con la vista de datos a la que el usuario tiene acceso.

Puede seleccionar una métrica por su ID dentro de un `SUM(metric)` como lo haría con otras fuentes SQL.

Puede usar:

- `SELECT COUNT(*)` o `COUNT(1)` para obtener la métrica ocurrencias.

- `SELECT COUNT(DISTINCT dimension)` o `SELECT APPROX_COUNT_DISTINCT(dimension)` para contar los valores distintos aproximados de una dimensión. Consulte los detalles en [Recuento de diferencias](#counting-distincts).

- [Cálculos en línea](#inline-calculations) para combinar métricas sobre la marcha y/o hacer cálculos sobre ellas.

#### Recuento de diferencias

Debido a la naturaleza subyacente de cómo funciona CJA, la única dimensión para la que puede obtener un recuento distinto exacto es la `adobe_personid` dimensión. Las siguientes instrucciones SQL `SELECT COUNT(DISTINCT adobe_personid)` o `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` devuelven el valor de la métrica de visitantes predeterminada, que es el recuento de personas distintas. Para otras dimensiones, se devuelve un recuento aproximado distinto.

#### Métricas condicionales

Puede incrustar un `IF` o `CASE` en el `SUM` o `COUNT` funciones para agregar filtros adicionales específicos de una métrica seleccionada. Añadir estas cláusulas es similar a aplicar un filtro a una columna de métrica en una tabla de informe de Workspace.

Ejemplos:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### Cálculos en línea

Puede aplicar adicionales a las expresiones de métricas en su `SELECT` en lugar de tener las matemáticas definidas en una métrica calculada. En la tabla siguiente se indica qué tipo de expresiones se admiten.

| Operador o función | Detalles |
|---|---|
| `+`, `-`, `*`, `/`, y `%` | Agregar, restar, multiplicar, dividir y modular/restante |
| `-X` o `+X` | Cambiar el signo o una métrica donde X es la expresión de métrica |
| `PI()` | π constante |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH`y `TANH` | Funciones matemáticas unarias |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Funciones matemáticas binarias |

{style="table-layout:auto"}

### Columnas especiales

**Marca de tiempo**

La variable `timestamp` se utiliza una columna especial para proporcionar los intervalos de fechas para la consulta. Un intervalo de fechas se puede definir con un `BETWEEN` expresión o un par de `timestamp` `>`, `>=`, `<`, `<=` comprobaciones `AND`ed juntos.
La variable `timestamp` es opcional y si no se proporciona ningún intervalo completo, se utilizan los valores predeterminados:

- Si solo se proporciona un mínimo (`timestamp > X` o ` timestamp >= X`), el rango va de X a ahora.

- Si solo se proporciona un máximo (`timestamp < X` o `timestamp <= X`), el intervalo va de X a 30 días a X.

- Si no se proporciona nada, el intervalo va de ahora a 30 días hasta ahora.

El intervalo de marca de tiempo se convierte en un filtro global de intervalo de fechas en RankedRequest.
El campo de marca de tiempo también se puede usar en funciones de fecha y hora para analizar y truncar la marca de tiempo del evento.

**Intervalo de fechas**

La variable `daterange` la columna especial funciona de forma similar a  `timestamp`, sin embargo, el filtrado está limitado a días completos. La variable `daterange` también es opcional y tiene el mismo intervalo predeterminado que `timestamp`.
La variable `daterange` también se puede utilizar en funciones de fecha y hora para analizar y truncar la fecha del evento.

**filterId**

La variable `filterId` especial es opcional y se utiliza para aplicar un filtro definido externamente a la consulta. Aplicar un filtro definido externamente a una consulta es similar a arrastrar un filtro a un panel en Workspace. Puede proporcionar varios ID de filtro `AND`-a ellos.

### Cláusula WHERE

La cláusula WHERE se gestiona en tres pasos:

1. Busque el intervalo de fechas en el `timestamp` campo especial.

2. Buscar cualquier definido externamente `filterId`s para incluir en el filtro.

3. Convierta las expresiones restantes en filtros específicos.

El control se realiza analizando el primer nivel de `AND`en la variable `WHERE` cláusula. Cada nivel superior `AND`La expresión ed debe coincidir con una de las anteriores. Cualquier cosa más profunda que el primer nivel de `AND`s, o si la variable `WHERE` cláusulas `OR`s en el nivel superior, se gestiona como un filtro ad hoc.

### ORDENAR POR

De forma predeterminada, la consulta ordena los resultados por la primera métrica seleccionada en orden descendente. Puede sobrescribir el orden de clasificación predeterminado especificando: `ORDER BY ... ASC` o `ORDER BY ... DESC`. Si usa `ORDER BY`, debe especificar `ORDER BY` en la primera métrica seleccionada.

También puede voltear el orden utilizando `-` (menos) delante de la métrica. Las dos instrucciones siguientes dan como resultado el mismo orden:

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### Compatibilidad con funciones generales

| Función | Ejemplo | Detalles |
|---|---|---|
| [CAST (tipo de columna AS)](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` o <br/> `` `timestamp`::string `` | Actualmente no se admite la conversión de tipo, pero no se produce ningún error. La variable `CAST` se ignora. |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Analizar una cadena de hora como una marca de tiempo para usarla dentro de un `WHERE` cláusula. |
| [TO_TIMESTAMP(timeString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Analizar una cadena de hora como una marca de tiempo para usarla dentro de un `WHERE` , proporcionando opcionalmente un formato para esa cadena de hora. |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Analizar una cadena de fecha como una marca de tiempo para usarla dentro de un `WHERE` cláusula. |
| [TO_DATE(dateString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Analizar una cadena de fecha como una marca de tiempo para usarla dentro de un `WHERE` , proporcionando opcionalmente un formato para esa cadena de fecha. |

{style="table-layout:auto"}

### Compatibilidad con funciones de Dimension

Estas funciones se pueden utilizar en dimensiones del `SELECT`, `WHERE` o en métricas condicionales.

**Funciones de cadena**

| Función | Ejemplo | Detalles |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Genere una identidad de dimensión dinámica en el campo pasado. |

{style="table-layout:auto"}

**Funciones de fecha y hora**

| Función | Ejemplo | Detalles |
|---|---|---|
| [AÑO(fecha o hora)](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. |
| [MONTH(fecha o fecha-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. |
| [DAY (fecha o hora)](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. |
| [DAYOFWEEK (fecha o hora)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. Utilice el ID del elemento en lugar del valor, ya que necesita el número, no el nombre descriptivo. |
| [DAYOFYEAR(fecha o fecha-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. |
| [SEMANA (fecha o hora)](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. |
| [TRIMESTRE (fecha o hora)](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. |
| [HOUR(fecha o fecha-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. Utilice el ID del elemento en lugar del valor, ya que necesita el número, no el nombre descriptivo. |
| [MINUTE(fecha o fecha-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. |
| [EXTRACTO(parte DE fecha o hora)](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. Utilice el ID del elemento en lugar del valor para algunas partes de esta función, ya que necesita el número, no el nombre descriptivo.<br/>Los elementos compatibles son:<br>- Palabras clave: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- Cadenas:  `'YEAR'`, &#39;`Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, &#39;`DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`o `'MINUTE'`. |
| [DATE_PART(parte, fecha o fecha-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. Utilice el ID del elemento en lugar del valor para algunas partes de esta función, ya que necesita el número, no el nombre descriptivo.<br/>Los elementos de cadena admitidos son: `'YEAR'`, &#39;`Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, &#39;`DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`o `'MINUTE'`. |
| [DATE_TRUNC(granularidad, fecha o fecha-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado.<br/>Las granularidades de cadena admitidas son: `'YEAR'`, &#39;`Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, &#39;`DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`o `'MINUTE'`. |

{style="table-layout:auto"}

