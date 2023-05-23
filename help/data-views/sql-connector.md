---
title: Conector SQL
description: Descubra cómo puede utilizar el servicio de consulta, el Power BI o Tableau para acceder a las vistas de datos mediante el conector SQL.
solution: Customer Journey Analytics
feature: Data Views
hide: true
hidefromtoc: true
badgeCJASQLConnector: label="New Feature" type="Positive"
source-git-commit: 829f7556c731ce55ccf1e03e2dea69b12e4501e4
workflow-type: tm+mt
source-wordcount: '2890'
ht-degree: 2%

---

# Conector SQL

{{release-limited-testing}}

El [!DNL Customer Journey Analytics (CJA) SQL Connector] habilita el acceso SQL a [vistas de datos](./data-views.md) que haya definido en CJA. Es posible que sus ingenieros y analistas de datos estén más familiarizados con Power BI, Tableau u otras herramientas de inteligencia empresarial y visualización (también denominadas herramientas de BI). Ahora pueden crear informes y paneles basados en las mismas vistas de datos que utilizan los usuarios de CJA al crear sus proyectos de Analysis Workspace.

Adobe Experience Platform [Servicio de consultas](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=es) es la interfaz SQL para los datos disponibles en el lago de datos del Experience Platform. Con el [!DNL CJA SQL Connector] activada, la funcionalidad de [!DNL Query Service] se amplía para ver sus vistas de datos de CJA como tablas o vistas en una [!DNL Query Service] sesión. Como resultado, las herramientas de inteligencia empresarial que utilizan [!DNL Query Service] ya que su interfaz PostgresSQL se beneficia sin problemas de esta funcionalidad extendida.

Los principales beneficios son:

- No es necesario volver a crear una representación equivalente de las vistas de datos de CJA dentro de la propia herramienta de BI. <br/>Consulte [Vista de datos](data-views.md) para obtener más información sobre la funcionalidad de las vistas de datos y comprender qué se debe volver a crear.<br/>

- Buena coherencia en los informes y análisis entre las herramientas de BI y CJA.

- Combine datos de CJA con otras fuentes de datos ya disponibles en las herramientas de BI.

## Requisitos previos

Para utilizar esta funcionalidad, debe hacer lo siguiente

- Habilite la [!UICONTROL Conector SQL de CJA] en su organización de Experience Platform.

- Configure la funcionalidad para los perfiles de producto, grupos de usuarios o usuarios individuales relevantes.<br/>
Los usuarios deben tener acceso a:
   - Servicio de consultas de Experience Platform,
   - Proyectos de CJA Workspace y
   - Vistas de datos de CJA que desea utilizar.

- Use caducar con credenciales que no caduquen para conectar las herramientas de BI al conector SQL de CJA. Thr [Guía de credenciales](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=en) proporciona más información sobre cómo configurar credenciales que caducan o que no caducan.

Consulte [Control de acceso](../admin/cja-access-control.md) en la sección Administración de CJA para obtener más información.


## Uso

Para usar la variable [!DNL CJA SQL Connector] , puede utilizar SQL directamente o utilizar la experiencia de arrastrar y soltar disponible en la herramienta específica de BI.

### SQL

Puede utilizar la funcionalidad directamente en instrucciones SQL utilizando el Editor de consultas o un cliente de interfaz de línea de comandos (CLI) estándar de PostgresSQL.

+++ Editor de consultas

En la interfaz de usuario de Experience Platform:

1. Seleccionar **[!UICONTROL ** Consultas **]** de **[!UICONTROL ** ADMINISTRACIÓN DE DATOS **]** en el carril izquierdo.

2. Seleccionar ![Crear consulta](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL ** Crear consulta **]**.

3. Para ejecutar la consulta, escriba la instrucción SQL y seleccione ![Reproducir](assets/Smock_Play_18_N.svg) (o presione MAYÚS + ENTRAR).

+++


+++ CLI de PostgresSQL

1. En la interfaz de usuario de Experience Platform, busque y copie las credenciales de PostgresSQL:

   1. Seleccionar **[!UICONTROL ** Consultas **]** desde el carril izquierdo (debajo de **[!UICONTROL ** ADMINISTRACIÓN DE DATOS **]**).

   2. Seleccionar **[!UICONTROL ** Credenciales **]** desde la barra superior.

   3. Para copiar la cadena de conexión, utilice ![Copiar](assets/Smock_Copy_18_N.svg) en el **[!UICONTROL ** comando PSQL **]** sección.

2. Abra la CLI de PostgresSQL.

3. Para iniciar sesión y comenzar a ejecutar las consultas, pegue la cadena de conexión en la CLI de PostgresSQL.

+++

Consulte [Guía de IU del Editor de consultas](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=en) para obtener más información.


### Herramientas de BI

Actualmente, el conector SQL de CJA es compatible con Power BI y Tableau.

+++ Power BI

1. En la interfaz de usuario de Adobe Experience Platform, busque los detalles de las credenciales de PostgresSQL.

   1. Seleccionar **[!UICONTROL ** Consultas **]** desde el carril izquierdo (debajo de **[!UICONTROL ** ADMINISTRACIÓN DE DATOS **]**).

   2. Seleccionar **[!UICONTROL ** Credenciales **]** desde la barra superior.

   3. Uso ![Copiar](assets/Smock_Copy_18_N.svg) para copiar cada uno de los parámetros de credenciales de Postgres ([!UICONTROL Host], [!UICONTROL Puerto], [!UICONTROL Base de datos], [!UICONTROL Nombre de usuario]y otros) cuando sea necesario en Power BI.

2. En Power BI:

   1. En la ventana principal, seleccione **[!UICONTROL ** Obtención de datos **]** en la barra de herramientas superior.

   2. Seleccionar **[!UICONTROL ** Más...**]** en el carril izquierdo.

   3. En el **Obtener datos** pantalla, buscar `PostgresSQL` y seleccione la **[!UICONTROL ** Base de datos PostgresSQL **]** de la lista.

   4. En el **[!UICONTROL ** Base de datos PostgressSQL **]** diálogo:

      1. Pegar **[!UICONTROL ** Host **]** parámetro de consultas de Experience Platform [!UICONTROL Credenciales] en **[!UICONTROL ** Servidor **]** campo de texto.

      2. Pegar **[!UICONTROL ** Base de datos **]** parámetro de consultas de Experience Platform [!UICONTROL Credenciales] in **[!UICONTROL ** Base de datos **]** campo de texto.

         Añadir `?FLATTEN` a la **[!UICONTROL ** Base de datos **]** parámetro, por lo que se ve como `prod:all?FLATTEN` por ejemplo. Consulte [Acoplar estructuras de datos anidadas para usarlas con herramientas de BI de terceros](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) para obtener más información.

      3. Cuando se le solicite **[!UICONTROL ** Conectividad de datos **]** modo, seleccione **[!UICONTROL ** DirectQuery **]** para garantizar que las estructuras de datos se acoplan correctamente.

      4. Se le pedirá que **[!UICONTROL ** Nombre de usuario **]** y **[!UICONTROL ** Contraseña **]**. Utilice los parámetros equivalentes de Consultas del Experience Platform [!UICONTROL Credenciales].
   5. Power BI Después de iniciar sesión correctamente, las tablas de vista de datos de CJA aparecen en el **[!UICONTROL ** Navegador **]**. Las tablas de vistas de datos se identifican mediante `dv_` en sus nombres.


   6. Seleccione las tablas de vista de datos que desee utilizar y seleccione **[!UICONTROL ** Cargar **]**.

   Todas las dimensiones y métricas asociadas con una o más tablas seleccionadas aparecen en el panel derecho, listas para utilizarse en las visualizaciones.

   Consulte [Conectar la Power BI al servicio de consultas](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=en) para obtener más información.

+++

+++Tableau

1. En la interfaz de usuario de Experience Platform, busque los detalles de las credenciales de PostgresSQL.

   1. Seleccionar **[!UICONTROL ** Consultas **]** desde el carril izquierdo (debajo de **[!UICONTROL ** ADMINISTRACIÓN DE DATOS **]**).

   2. Seleccionar **[!UICONTROL ** Credenciales **]** desde la barra superior.

   3. Uso ![Copiar](assets/Smock_Copy_18_N.svg) para copiar cada uno de los parámetros de credenciales de Postgres ([!UICONTROL Host], [!UICONTROL Puerto], [!UICONTROL Base de datos], [!UICONTROL Nombre de usuario]y otros) cuando sea necesario en Tableau.

2. En Tableau:

   1. Seleccionar **[!UICONTROL ** Más **]** de **[!UICONTROL ** A un servidor **]** en el carril izquierdo.

   2. Seleccionar **[!UICONTROL ** PostgresSQL **]** de la lista.

   3. En el [!UICONTROL PostgresSQL] diálogo:

      1. Pegar **[!UICONTROL ** Host **]** parámetro de consultas de Experience Platform [!UICONTROL Credenciales] en **[!UICONTROL ** Servidor **]** campo de texto.

      2. Pegar **[!UICONTROL ** Puerto **]** parámetro de consultas de Experience Platform [!UICONTROL Credenciales] en **[!UICONTROL ** Puerto **]** campo de texto.

      3. Pegar **[!UICONTROL ** Base de datos **]** parámetro de consultas de Experience Platform [!UICONTROL Credenciales] en **[!UICONTROL ** Base de datos **]** campo de texto.

         Añadir `%3FFLATTEN` a la **[!UICONTROL ** Base de datos **]** parámetro, por lo que se ve como `prod:all%3FFLATTEN` por ejemplo. Consulte [Acoplar estructuras de datos anidadas para usarlas con herramientas de BI de terceros](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) para obtener más información.

      4. Seleccionar **[!UICONTROL ** Nombre de usuario y contraseña **]** de **[!UICONTROL ** Autenticación **]** lista.

      5. Pegar **[!UICONTROL ** Nombre de usuario **]** parámetro de consultas de Experience Platform [!UICONTROL Credenciales] en **[!UICONTROL ** Nombre de usuario **]** campo de texto.

      6. Pegar **[!UICONTROL ** Contraseña **]** parámetro de consultas de Experience Platform [!UICONTROL Credenciales] en **[!UICONTROL ** Contraseña **]** campo de texto.

      7. Seleccionar **[!UICONTROL ** Iniciar sesión **]**.
   4. Las vistas de datos de CJA se muestran como tablas en la **[!UICONTROL ** Tabla **]** lista. Las tablas de vista de datos tienen el prefijo `dv_`.

   5. Arrastre las tablas que desee utilizar en el lienzo.

   Ahora puede trabajar con los datos de las tablas de vista de datos para crear sus informes y visualizaciones.

   Consulte [Conexión de Tableau con el servicio de consultas](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=en) para obtener más información.

+++

Consulte [Conectar clientes al servicio de consultas](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en) para obtener información general y más detallada sobre las distintas herramientas disponibles.

## Funcionalidad

De forma predeterminada, las vistas de datos tienen un nombre seguro para tablas generado a partir de su nombre descriptivo. Por ejemplo, la vista de datos denominada [!UICONTROL Mis datos web] tiene el nombre de la vista `dv_my_web_data`.

Si desea utilizar los ID de vista de datos como nombres de tabla, puede añadir los `CJA_USE_IDS` estableciendo en el nombre de la base de datos al conectarse. Por ejemplo, `prod:all?CJA_USE_IDS` muestra sus vistas de datos con nombres como `dv_ABC123`.

### Gobernanza de datos

La configuración relacionada con la gobernanza de datos en Customer Journey Analytics se hereda de Adobe Experience Platform. La integración entre CJA y Gobernanza de datos de Adobe Experience Platform permite el etiquetado de datos de CJA confidenciales y la aplicación de directivas de privacidad.

Las etiquetas y directivas de privacidad creadas en conjuntos de datos consumidos por Experience Platform se pueden ver en el flujo de trabajo de vistas de datos de CJA. Por lo tanto, los datos consultados mediante el conector SQL de CJA muestran advertencias o errores adecuados al no cumplir con las etiquetas y directivas de privacidad definidas.

### Enumerar vistas de datos

En la CLI estándar de PostgreSQL, puede enumerar las vistas mediante `\dv`

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

### Anidado frente a plano

De forma predeterminada, el esquema de las vistas de datos utiliza estructuras anidadas, al igual que los esquemas XDM originales. La integración también admite `FLATTEN` opción. Puede utilizar esta opción para forzar el acoplamiento del esquema de las vistas de datos (y de cualquier otra tabla de la sesión). El acoplamiento permite un uso más sencillo en herramientas de BI que no admiten esquemas estructurados. Consulte [Uso de estructuras de datos anidadas en el servicio de consultas](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) para obtener más información.

### SQL compatible

Consulte [Referencia SQL del servicio de consultas](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=en) para obtener la referencia completa sobre qué tipo de SQL se admite.

Consulte la tabla Patrones a continuación para obtener una descripción general de los patrones y ejemplos.

+++Patrones

| Patrón | Ejemplo |
|---|---|
| Detección de esquemas | <pre>SELECT * FROM dv1 WHERE 1=0</pre> |
| Clasificación / Desglose | <pre>SELECCIONAR dim1, SUM(metric1) AS m1<br/>DESDE dv1<br/>DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;<br/>AGRUPAR POR dim1</pre><pre>SELECCIONAR dim1, SUM(metric1) AS m1<br/>DESDE dv1<br/>WHERE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39; AND<br/>  filterId = &#39;12345&#39;<br/>AGRUPAR POR dim1</pre><pre>SELECCIONAR dim1, SUM(metric1) AS m1<br/>DESDE dv1<br/>WHERE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39; AND<br/>  Y (dim2 = &#39;A&#39; O dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>AGRUPAR POR dim1</pre> |
| Cláusula HAVING | <pre>SELECCIONAR dim1, SUM(metric1) AS m1<br/>DESDE dv1<br/>DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;<br/>AGRUPAR POR dim1<br/>CON m1 > 100</pre> |
| Distinto, superior <br/>valores de dimensión | <pre>SELECCIONE DISTINCT dim1 FROM dv1</pre><pre>SELECT dim1 AS dv1<br/>DESDE dv1<br/>DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;<br/>AGRUPAR POR dim1</pre><pre>SELECT dim1 AS dv1<br/>DESDE dv1<br/>WHERE \`timestamp\` >= &#39;2022-01-01&#39; AND \`timestamp\` &lt; &#39;2022-01-02&#39;<br/>AGRUPAR POR dim1<br/>ORDENAR POR SUMA(métrica1)<br/>LÍMITE DE 15</pre> |
| Totales de métricas | <pre>SELECCIONAR SUMA(metric1) COMO m1<br/>DESDE dv1<br/>DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;</pre> |
| De varias dimensiones<br/>desglose<br/>y distintivos de primer nivel | <pre>SELECCIONAR dim1, dim2, SUM(metric1) AS m1<br/>DESDE dv1<br/>DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;<br/>AGRUPAR POR dim1, dim2</pre><pre>SELECCIONAR dim1, dim2, SUM(metric1) AS m1<br/>DESDE dv1<br/>DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;<br/>AGRUPAR POR 1, 2<br/>ORDENAR POR 1, 2</pre><pre>SELECCIONAR DISTINTO dim1, dim2<br/>DESDE dv1</pre> |
| Subselección:<br/>Resultado adicional<br/>filtrado | <pre>SELECCIONAR dim1, m1<br/>DESDE (<br/>  SELECCIONAR dim1, SUM(metric1) AS m1<br/>  DESDE dv1<br/>  DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;</br>  AGRUPAR POR dim1<br/>)<br/>DONDE dim1 en (&#39;A&#39;, &#39;B&#39;)</pre> |
| Subselección:<br/>Unirse a<br/>conjunto de datos no en<br/>CJA | <pre>SELECT b.key, a.dim1, a.m1<br/>DESDE (<br/>  SELECCIONAR dim1, SUM(metric1) AS m1<br/>  DESDE dv1<br/>  DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;<br/>  AGRUPAR POR dim1<br/>) a<br/>Búsquedas de LEFT JOIN b en a.dim1 = b.key</pre> |
| Subselección:<br/>Realización de consultas<br/>data-views | <pre>Clave SELECT, SUM(m1) AS total<br/>DESDE (<br/>  SELECT dim1 AS clave, SUM(metric1) AS m1<br/>  DESDE dv1<br/>  DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;<br/>  AGRUPAR POR dim1<br/><br/>  UNIÓN<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  DESDE dv2<br/>  DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;<br/>  AGRUPAR POR dim2<br/>GROUP BY key<br/>ORDENAR POR total</pre> |
| Subselección: <br/>Fuente con capas, <br/>filtrado, <br/>y agregación | Capas con subselecciones:<br><pre>SELECT filas.dim1, SUM(filas.m1) AS total<br/>DESDE (<br/>  SELECT \_.dim1,\_.m1<br/>  DESDE (<br/>    SELECT \* FROM dv1<br/>    DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;<br/>  ) \_<br/>  WHERE \_.dim1 in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) filas<br/>AGRUPAR POR 1<br/>ORDENAR POR total</pre><br/>Capas que utilizan CTE CON:<br/><pre>WITH rows AS (<br/>  CON \_ COMO (<br/>    SELECT * FROM áreas_de_datos<br/>    DONDE \`timestamp\` ENTRE &#39;2021-01-01&#39; Y &#39;2021-02-01&#39;<br/>  )<br/>  SELECT _.item, _.units FROM _<br/>  WHERE _.item IS NOT NULL<br/>)<br/>SELECT filas.elemento, SUM(filas.unidades) AS unidades<br/>FROM filas WHERE rows.item in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>GROUP BY rows.item</pre> |
| Selecciona dónde<br/>las métricas van antes que<br/> o se mezclan con<br/>las dimensiones | <pre>SELECCIONAR SUMA(metric1) COMO m1, dim1<br/>DESDE dv1<br/>DONDE \`timestamp\` ENTRE &#39;2022-01-01&#39; Y &#39;2022-01-02&#39;<br/>AGRUPAR POR 2</pre> |

{style="table-layout:auto"}

+++

### Dimensiones

Puede seleccionar cualquiera de las dimensiones disponibles de forma predeterminada o definidas en la vista de datos. Las dimensiones se seleccionan por su ID.

### Métricas

Las métricas disponibles para seleccionar son:

- cualquiera de las métricas disponibles de forma predeterminada,

- definido en la vista de datos,

- métricas calculadas que son compatibles con la vista de datos a la que el usuario tiene acceso.

Seleccione una métrica por su ID dentro de un `SUM(metric)` expresión igual que haría con otros orígenes SQL.

Puede usar:

- `SELECT COUNT(*)` o `COUNT(1)` para obtener la métrica ocurrencias.

- `SELECT COUNT(DISTINCT dimension)` o `SELECT APPROX_COUNT_DISTINCT(dimension)` para contar los valores distintos aproximados de una dimensión. Consulte los detalles en [Recuento de distintivos](#counting-distincts).

- [Cálculos en línea](#inline-calculations) para combinar métricas sobre la marcha o hacer cálculos matemáticos sobre ellas.

#### Recuento de distintivos

Debido a la naturaleza subyacente de cómo funciona CJA, la única dimensión para la que puede obtener un recuento distinto exacto es la siguiente `adobe_personid` dimensión. Las siguientes instrucciones SQL `SELECT COUNT(DISTINCT adobe_personid)` o `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` devuelve el valor de la métrica de visitantes predeterminada que es el recuento de personas distintas. Para otras dimensiones, se devuelve un recuento distinto aproximado.

#### Métricas condicionales

Puede incrustar un `IF` o `CASE` cláusula en el `SUM` o `COUNT` funciones para añadir filtros adicionales específicos de una métrica seleccionada. Añadir estas cláusulas es similar a aplicar un filtro a una columna de métrica en una tabla de informes de Workspace.

Ejemplos:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### Cálculos en línea

Puede aplicar atributos adicionales a las expresiones de métrica en su `SELECT` en lugar de tener las matemáticas definidas en una métrica calculada. En la tabla siguiente se enumera qué tipo de expresiones se admiten.

| Operador o función | Detalles |
|---|---|
| `+`, `-`, `*`, `/`, y `%` | Agregar, restar, multiplicar, dividir y modular/resto |
| `-X` o `+X` | Cambiar el signo de una métrica donde X es la expresión de métrica |
| `PI()` | constante de |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH`, y `TANH` | Funciones matemáticas unarias |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Funciones matemáticas binarias |

{style="table-layout:auto"}

### Columnas especiales

**Marca de tiempo**

El `timestamp` se utiliza una columna especial para proporcionar los intervalos de fechas para la consulta. Un intervalo de fecha se puede definir con una variable `BETWEEN` expresión o un par de `timestamp` `>`, `>=`, `<`, `<=` cheques `AND`ed juntos.
El `timestamp` es opcional y, si no se proporciona ningún intervalo completo, se utilizan los valores predeterminados:

- Si solo se proporciona un mínimo (`timestamp > X` o ` timestamp >= X`), el intervalo es de X a ahora.

- Si solo se proporciona un máximo (`timestamp < X` o `timestamp <= X`), el rango es de X-30 días a X.

- Si no se proporciona nada, el intervalo va de ahora a 30 días.

El intervalo de marca de hora se convierte en un filtro global de intervalo de fecha en RankedRequest.
El campo de marca de tiempo también se puede utilizar en funciones de fecha y hora para analizar y truncar la marca de tiempo del evento.

**Intervalo de fechas**

El `daterange` la columna especial funciona de forma similar a  `timestamp`, sin embargo, el filtrado se limita a días completos. El `daterange` también es opcional y tiene los mismos valores predeterminados de intervalo que `timestamp`.
El `daterange` El campo también se puede utilizar en Funciones de fecha y hora para analizar y truncar la fecha del evento.

**filterId**

El `filterId` special column es opcional y se utiliza para aplicar un filtro definido externamente a la consulta. La aplicación de un filtro definido externamente a una consulta es similar a arrastrar un filtro a un panel en Workspace. Pueden proporcionar varios ID de filtro `AND`-Los repito.

### Cláusula WHERE

La cláusula WHERE se controla en tres pasos:

1. Busque el intervalo de fechas desde la variable `timestamp` campo especial.

2. Buscar cualquier definido externamente `filterId`s para incluir en el filtro.

3. Convierta las expresiones restantes en filtros específicos.

La administración se realiza analizando el primer nivel de `AND`s en el `WHERE` Cláusula. Cada nivel superior `AND`La expresión &quot;ed&quot; debe coincidir con una de las expresiones anteriores. Cualquier cosa más profunda que el primer nivel de `AND`s, o, si el `WHERE` Cláusula utiliza `OR`Al estar en el nivel superior, se gestiona como un filtro ad hoc.

### ORDENAR POR

De forma predeterminada, la consulta ordena los resultados por la primera métrica seleccionada en orden descendente. Puede sobrescribir el orden de clasificación predeterminado especificando `ORDER BY ... ASC` o `ORDER BY ... DESC`. Si utiliza `ORDER BY`, debe especificar `ORDER BY` en la primera métrica seleccionada.

También puede voltear el orden utilizando `-` (menos) delante de la métrica. Ambas afirmaciones a continuación resultan en el mismo orden:

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### Compatibilidad con funciones generales

| Función | Ejemplo | Detalles |
|---|---|---|
| [CAST(tipo AS de columna)](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` o <br/> `` `timestamp`::string `` | Actualmente no se admite la conversión de tipos, pero no se produce ningún error. El `CAST` se ignora la función. |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Analizar una cadena de tiempo como una marca de tiempo para usarla en un `WHERE` Cláusula. |
| [TO_TIMESTAMP(timeString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Analizar una cadena de tiempo como una marca de tiempo para usarla en un `WHERE` , proporcionando opcionalmente un formato para esa cadena de tiempo. |
| [DATE(fechaCadena)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Analizar una cadena de fecha como una marca de tiempo para usarla en un `WHERE` Cláusula. |
| [TO_DATE(dateString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Analizar una cadena de fecha como una marca de tiempo para usarla en un `WHERE` , proporcionando opcionalmente un formato para esa cadena de fecha. |

{style="table-layout:auto"}

### Compatibilidad con funciones de Dimension

Estas funciones se pueden utilizar en dimensiones en la variable `SELECT`, `WHERE` o en métricas condicionales.

**Funciones de cadena**

| Función | Ejemplo | Detalles |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Genere una identidad de dimensión dinámica en el campo pasado. |

{style="table-layout:auto"}

**Funciones de fecha y hora**

| Función | Ejemplo | Detalles |
|---|---|---|
| [YEAR(fecha o fecha-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. |
| [MONTH(fecha o fecha-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. |
| [DAY(fecha o fecha-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. |
| [DAYOFWEEK(fecha o fecha-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. Utilice el ID del elemento en lugar del valor, ya que necesita el número y no el nombre descriptivo. |
| [DAYOFYEAR(fecha o fecha-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. |
| [WEEK(fecha o fecha-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. |
| [QUARTER(fecha o fecha-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. |
| [HOUR(fecha o fecha-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. Utilice el ID del elemento en lugar del valor, ya que necesita el número y no el nombre descriptivo. |
| [MINUTE(fecha o fecha-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. |
| [EXTRACT(parte DESDE fecha o fecha-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. Utilice el ID del elemento en lugar del valor para algunas partes de esta función, ya que necesita el número y no el nombre descriptivo.<br/>Las piezas compatibles son:<br>- Palabras clave: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- Cadenas:  `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, o `'MINUTE'`. |
| [DATE_PART(parte, fecha o fecha-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. Utilice el ID del elemento en lugar del valor para algunas partes de esta función, ya que necesita el número y no el nombre descriptivo.<br/>Las partes de cadena compatibles son: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, o `'MINUTE'`. |
| [DATE_TRUNC(granularidad, fecha o fecha-hora)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado.<br/>Las granularidades de cadena admitidas son: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, o `'MINUTE'`. |

{style="table-layout:auto"}

