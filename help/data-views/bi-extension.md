---
title: Extensión de Customer Journey Analytics BI
description: Descubra cómo puede utilizar Power BI o Tableau Desktop para acceder a las vistas de datos mediante la extensión de BI de Customer Journey Analytics.
solution: Customer Journey Analytics
feature: BI Extension
role: Admin
exl-id: ab7e1f15-ead9-46b7-94b7-f81802f88ff5
source-git-commit: 8b90f74d64ef35f4a9f0f1177dab27c9680ccb4c
workflow-type: tm+mt
source-wordcount: '3116'
ht-degree: 60%

---

# Extensión de Customer Journey Analytics BI

{{select-package}}

[!DNL Customer Journey Analytics BI extension] habilita el acceso SQL a las [vistas de datos](./data-views.md) que ha definido en Customer Journey Analytics. Es posible que sus ingenieros y analistas de datos estén más familiarizados con Power BI, Tableau Desktop u otras herramientas de inteligencia empresarial y visualización (también denominadas herramientas de BI). Ahora pueden crear informes y paneles basados en las mismas vistas de datos que utilizan los usuarios de Customer Journey Analytics al crear sus proyectos de Analysis Workspace.

El [servicio de consultas](https://experienceleague.adobe.com/es/docs/experience-platform/query/home) de Adobe Experience Platform es la interfaz SQL de los datos disponibles en el lago de datos de Experience Platform. Con [!DNL Customer Journey Analytics BI extension] activado, la funcionalidad de [!DNL Query Service] se amplía para ver las vistas de datos de Customer Journey Analytics como tablas o vistas en una sesión de [!DNL Query Service]. Como resultado, las herramientas de inteligencia empresarial que utilizan [!DNL Query Service] como su interfaz PostgresSQL se benefician sin problemas de esta funcionalidad ampliada.

Las principales ventajas son las siguientes:

* No es necesario volver a crear una representación equivalente de vistas de datos de Customer Journey Analytics dentro de la propia herramienta de BI. <br/>Vea [Vistas de datos](data-views.md) para obtener más información sobre la funcionalidad de las vistas de datos y comprender qué se debe volver a crear.
* Mayor coherencia en la creacion de informes y análisis entre las herramientas de BI y Customer Journey Analytics.
* Combinar datos de Customer Journey Analytics con otras fuentes de datos ya disponibles en las herramientas de BI.

## Requisitos previos

Para usar esta funcionalidad, puede usar credenciales que caduquen o no caduquen para conectar las herramientas de BI a [!DNL Customer Journey Analytics BI extension]. La [Guía de credenciales](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials) proporciona más información sobre cómo configurar credenciales que caducan o que no caducan.
A continuación se muestran pasos adicionales para configurar los permisos de CJA
<!---   Enable the [!UICONTROL Customer Journey Analytics BI extension] in your Experience Platform organization. -->

### Credenciales que caducan

Para utilizar credenciales que caducan, puede:

* Conceder acceso al Experience Platform y al Customer Journey Analytics.
* Conceder acceso de administrador de producto a Customer Journey Analytics para que pueda ver, editar, actualizar o eliminar conexiones y vistas de datos.

O bien puede:

* Conceda acceso a las vistas de datos a las que desee acceder.
* Conceder acceso a la extensión de BI de Customer Journey Analytics.

### Credenciales que no caducan

Para usar credenciales que no caduquen:

* Cree credenciales que no caduquen en Experience Platform.
* Conceda acceso a las credenciales que no caducan siguiendo los pasos mencionados en [Credenciales que caducan](#Expiring-credentials).

Consulte [Control de acceso con Recorrido del cliente](../technotes/access-control.md) para obtener más información, en concreto los [permisos adicionales de administrador de productos](../technotes/access-control.md#product-admin-additional-permissions) y los [permisos de Customer Journey Analytics en el Admin Console](../technotes/access-control.md#customer-journey-analytics-permissions-in-admin-console).


## Uso

Para usar la funcionalidad de [!DNL Customer Journey Analytics BI extension], puede utilizar SQL directamente o utilizar la experiencia de arrastrar y soltar disponible en la herramienta específica de BI.

### SQL

Puede utilizar la funcionalidad directamente en las instrucciones SQL utilizando el editor de consultas o un cliente de interfaz de línea de comandos (CLI) estándar de PostgresSQL.

+++ Editor de consultas

En Adobe Experience Platform:

1. Seleccione **[!UICONTROL ** Consultas **]** de **[!UICONTROL ** ADMINISTRACIÓN DE DATOS **]** en el carril izquierdo.

1. Seleccione ![Crear consulta](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL ** Crear consulta **]**.

1. Seleccione la `cja` **[!UICONTROL ** base de datos **]**.

1. Para ejecutar la consulta, escriba la instrucción SQL y seleccione el botón ![Reproducir](assets/Smock_Play_18_N.svg) (o presione `[SHIFT]` + `[ENTER]`).

+++


+++ CLI de PostgresSQL

1. Busque y copie sus credenciales de PostgresSQL en Adobe Experience Platform:

   1. Seleccione **[!UICONTROL ** Consultas **]** en el carril izquierdo (debajo de **[!UICONTROL ** ADMINISTRACIÓN DE DATOS **]**).

   1. Seleccione **[!UICONTROL ** Credenciales **]** en la barra superior.

   1. Seleccione la `cja` **[!UICONTROL ** base de datos **]**.

   1. Para copiar la cadena de comandos, use ![Copiar](assets/Smock_Copy_18_N.svg) en la sección **[!UICONTROL ** Comando PSQL **]**.

1. Abra una ventana de comando o de terminal.

1. Para iniciar sesión y comenzar a ejecutar las consultas, pegue la cadena de comando en el terminal.

+++

Consulte la [guía de la interfaz de usuario del editor de consultas](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/user-guide) para obtener más información.


### Herramientas de BI

Actualmente, [!DNL Customer Journey Analytics BI extension] es compatible y se ha probado solo para Power BI y Tableau Desktop. Otras herramientas de BI que usan la interfaz PSQL podrían funcionar también, pero aún no son compatibles oficialmente.

+++ Power BI

1. Busque los detalles de las credenciales de PostgresSQL en Adobe Experience Platform:

   1. Seleccione **[!UICONTROL ** Consultas **]** en el carril izquierdo (debajo de **[!UICONTROL ** ADMINISTRACIÓN DE DATOS **]**).

   1. Seleccione **[!UICONTROL ** Credenciales **]** en la barra superior.

   1. Seleccione la `cja` **[!UICONTROL ** base de datos **]**.

   1. Utilice ![Copiar](assets/Smock_Copy_18_N.svg) para copiar cada uno de los parámetros de credenciales de Postgres ([!UICONTROL host], [!UICONTROL Puerto], [!UICONTROL base de datos], [!UICONTROL nombre de usuario]y otros) cuando sea necesario en Power BI.

1. En Power BI:

   1. En la ventana principal, seleccione **[!UICONTROL ** Obtener datos **]** en la barra de herramientas superior.

   1. Seleccione **[!UICONTROL Más…]** en el carril izquierdo.

   1. En la pantalla **Obtener datos**, busque `PostgresSQL` y seleccione la **[!UICONTROL ** base de datos PostgresSQL **]** de la lista.

   1. En el cuadro de diálogo **[!UICONTROL ** Base de datos de PostgressSQL **]**:

      1. Pegue el parámetro **[!UICONTROL ** Host **]** de las consultas de Experience Platform [!UICONTROL Credentials] en el campo de texto **[!UICONTROL ** Server **]**.

      1. Pegue el parámetro **[!UICONTROL ** Database **]** de las consultas de Experience Platform [!UICONTROL Credentials] en el campo de texto **[!UICONTROL ** Database **]**.

         Añada `?FLATTEN` al parámetro **[!UICONTROL ** Base de datos **]**, para que se vea como `prod:cja?FLATTEN`, por ejemplo. Consulte [Acoplar estructuras de datos anidadas para usarlas con herramientas de BI de terceros](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) para obtener más información.

      1. Cuando se le pida el modo **[!UICONTROL Conectividad de datos]**, seleccione **[!UICONTROL DirectQuery]**.

      1. Se le solicitará el **[!UICONTROL nombre de usuario]** y la **[!UICONTROL contraseña]**. Utilice los parámetros equivalentes de las [!UICONTROL credenciales] de consultas de Experience Platform.


   1. Después de iniciar sesión correctamente, las tablas de vista de datos del Customer Journey Analytics aparecen en Power BI **[!UICONTROL ** Navigator **]**.

   1. Seleccione las tablas de vista de datos que desee utilizar y seleccione **[!UICONTROL ** cargar **]**.

   Todas las dimensiones y métricas asociadas con una o más tablas seleccionadas aparecen en el panel derecho, listas para utilizarse en las visualizaciones.

   Consulte [Conectar Power BI al servicio de consultas](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/power-bi) para obtener más información.

+++

+++Tableau Desktop

1. Busque los detalles de las credenciales de PostgresSQL en Adobe Experience Platform:

   1. Seleccione **[!UICONTROL ** Consultas **]** en el carril izquierdo (debajo de **[!UICONTROL ** ADMINISTRACIÓN DE DATOS **]**).

   1. Seleccione **[!UICONTROL ** Credenciales **]** en la barra superior.

   1. Seleccione la ` cja` **[!UICONTROL ** base de datos **]**.

   1. Use ![Copiar](assets/Smock_Copy_18_N.svg) para copiar cada uno de los parámetros de credenciales de Postgres ([!UICONTROL Host], [!UICONTROL Puerto], [!UICONTROL Base de datos], [!UICONTROL Nombre de usuario] y otros) cuando sea necesario en Tableau Desktop.

1. En Tableau Desktop:

   1. Seleccione **[!UICONTROL ** Más **]** de **[!UICONTROL ** A un servidor **]** en el carril izquierdo.

   1. Seleccione **[!UICONTROL ** PostgresSQL **]** de la lista.

   1. En el cuadro de diálogo de [!UICONTROL PostgresSQL]:

      1. Pegue el parámetro **[!UICONTROL ** Host **]** de las consultas de Experience Platform [!UICONTROL Credentials] en el campo de texto **[!UICONTROL ** Server **]**.

      1. Pegue el parámetro **[!UICONTROL ** Port **]** de las consultas de Experience Platform [!UICONTROL Credentials] en el campo de texto **[!UICONTROL ** Port **]**.

      1. Pegue el parámetro **[!UICONTROL ** Database **]** de las consultas de Experience Platform [!UICONTROL Credentials] en el campo de texto **[!UICONTROL ** Database **]**.

         Añada `%3FFLATTEN` al parámetro **[!UICONTROL ** Base de datos **]**, para que se vea como `prod:cja%3FFLATTEN`, por ejemplo. Consulte [Acoplar estructuras de datos anidadas para usarlas con herramientas de BI de terceros](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) para obtener más información.

      1. Seleccione **[!UICONTROL ** Nombre de usuario y contraseña **]** de la lista **[!UICONTROL ** Autenticación **]**.

      1. Pegue el parámetro **[!UICONTROL ** Nombre de usuario **]** de [!UICONTROL Credenciales] de consultas de Experience Platform en el campo de texto **[!UICONTROL ** Nombre de usuario **]**.

      1. Pegue el parámetro **[!UICONTROL ** Password **]** de las consultas de Experience Platform [!UICONTROL Credentials] en el campo de texto **[!UICONTROL ** Password **]**.

      1. Seleccione **[!UICONTROL ** Iniciar sesión **]**.

   1. Las vistas de datos del Customer Journey Analytics se muestran como tablas en la lista **[!UICONTROL ** Tabla **]**.

   1. Arrastre las tablas que desee utilizar en el lienzo.

   Ahora puede trabajar con los datos de las tablas de vista de datos para crear sus informes y visualizaciones.

   Consulte [Conectar Tableau con el servicio de consultas](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/tableau) para obtener más información.

+++

Consulte [Conectar clientes al servicio de consultas](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/overview) para obtener información general y más detallada sobre las distintas herramientas disponibles.

Consulte [Casos de uso](/help/use-cases/data-views/bi-extension-usecases.md) sobre cómo realizar una serie de casos de uso con la extensión de BI de Customer Journey Analytics

## Funcionalidad

De forma predeterminada, las vistas de datos tienen un nombre seguro para las tablas generadas a partir de su nombre descriptivo. Por ejemplo, la vista de datos [!UICONTROL Mi vista de datos web] tiene el nombre de vista `my_web_data_view`. Puede definir un nombre preferido para usar en la herramienta de BI para la vista de datos. Consulte [Configuración de vista de datos](create-dataview.md#settings) para obtener más información.

Si desea utilizar los ID de vista de datos como nombres de tabla, puede añadir el `CJA_USE_IDS` opcional estableciendo en el nombre de la base de datos al conectarse. Por ejemplo, `prod:cja?CJA_USE_IDS` muestra sus vistas de datos con nombres como `dv_ABC123`.

### Gobernanza de datos

La configuración relacionada con la gobernanza de datos en Customer Journey Analytics se hereda de Adobe Experience Platform. La integración entre Customer Journey Analytics y Gobernanza de datos de Adobe Experience Platform permite el etiquetado de datos confidenciales de Customer Journey Analytics y la aplicación de directivas de privacidad.

Las etiquetas de privacidad y las políticas creadas en conjuntos de datos consumidos por Experience Platform se pueden ver en el flujo de trabajo de vistas de datos de Customer Journey Analytics. Por lo tanto, los datos consultados con [!DNL Customer Journey Analytics BI extension] muestran advertencias o errores adecuados cuando no cumplen con las etiquetas y directivas de privacidad definidas.

### Enumerar vistas de datos

En la CLI estándar de PostgreSQL, puede enumerar las vistas mediante `\dv`

```sql
prod:all=> \dv
                       List of relations
 Schema |                    Name                    | Type |  Owner             
--------+--------------------------------------------+------+----------
 public | my_web_data_view                           | view | postgres
 public | my_mobile_data_view                        | view | postgres
```

### Anidado frente al acoplamiento

De forma predeterminada, el esquema de las vistas de datos utiliza estructuras anidadas, al igual que los esquemas XDM originales. La integración también admite la opción `FLATTEN`. Puede utilizar esta opción para forzar el acoplamiento del esquema de las vistas de datos (y de cualquier otra tabla de la sesión). El acoplamiento permite un uso más sencillo en herramientas de BI que no admiten esquemas estructurados. Consulte [Trabajar con estructuras de datos anidadas en el servicio de consultas](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) para obtener más información.


### Valores predeterminados y limitaciones

Al usar la extensión de BI, se aplican los siguientes valores predeterminados y limitaciones adicionales:

* La extensión de BI requiere un límite de filas para los resultados de la consulta. El valor predeterminado es 50, pero puede invalidarlo en SQL con `LIMIT n`, donde `n` es 1 - 50000.
* La extensión de BI requiere un intervalo de fechas para limitar las filas utilizadas en los cálculos. El valor predeterminado son los últimos 30 días, pero puede invalidarlo en la cláusula SQL `WHERE` con las columnas especiales [`timestamp`](#timestamp) o [`daterange`](#date-range).
* La extensión de BI requiere consultas de agregado. No puede usar SQL como `SELECT * FROM ...` para obtener las filas subyacentes sin procesar. En un nivel superior, las consultas agregadas deben utilizar:
   * Seleccionar totales usando `SUM` y/o `COUNT`.<br/> Por ejemplo, `SELECT SUM(metric1), COUNT(*) FROM ...`
   * Seleccione las métricas desglosadas por una dimensión. <br/>Por ejemplo, `SELECT dimension1, SUM(metric1), COUNT(*) FROM ... GROUP BY dimension1`
   * Seleccione valores de métrica distintos.<br/>Por ejemplo, `SELECT DISTINCT dimension1 FROM ...`

     Consulte para obtener más información [SQL compatible](#supported-sql).


### SQL compatible

Consulte [Referencia SQL del servicio de consultas](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/overview) para obtener la referencia completa sobre qué tipo de SQL se admite.

Consulte la tabla siguiente para ver ejemplos del SQL que puede utilizar.

+++ Ejemplos

| Patrón | Ejemplo |
|---|---|
| Detección de esquemas | <pre>SELECT * FROM dv1 WHERE 1=0</pre> |
| Clasificación o desglose | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  filterId = &#39;12345&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  AND (dim2 = &#39;A&#39; OR dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>GROUP BY dim1</pre> |
| Cláusula `HAVING` | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>HAVING m1 > 100</pre> |
| Valores de dimensión <br/>distintos, superiores | <pre>SELECT DISTINCT dim1 FROM dv1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` >= &#39;2022-01-01&#39; AND \`timestamp\` &lt; &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>ORDER BY SUM(metric1)<br/>LIMIT 15</pre> |
| Totales de métricas | <pre>SELECT SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</pre> |
| <br/>Desgloses<br/> de varias dimensiones y superiores distintos | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 1, 2<br/>ORDER BY 1, 2</pre><pre>SELECT DISTINCT dim1, dim2<br/>FROM dv1</pre> |
| Subseleccionar:<br/>Filtrar <br/>resultados adicionales | <pre>SELECT dim1, m1<br/>FROM (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</br>  GROUP BY dim1<br/>)<br/>WHERE dim1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| Subseleccionar:<br/>Realizando consultas en<br/>vistas de datos | <pre>SELECT key, SUM(m1) AS total<br/>FROM (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim1<br/><br/>  UNION<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  FROM dv2<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim2<br/>GROUP BY key<br/>ORDER BY total</pre> |
| Subselección: <br/>origen con capas, <br/>filtrado, <br/>y agregación | Capas con subselecciones:<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>FROM (<br/>  SELECT \_.dim1,\_.m1<br/>  FROM (<br/>    SELECT \* FROM dv1<br/>    WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  ) \_<br/>  WHERE \_.dim1 in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) rows<br/>GROUP BY 1<br/>ORDER BY total</pre><br/>Capas que utilizan CTE WITH:<br/><pre>CON filas COMO (<br/> CON \_ AS (<br/>)    SELECT * FROM áreas_de_datos<br/>    WHERE \`timestamp\` ENTRE &#39;2021-01-01&#39; Y &#39;2021-02-01&#39;<br/> )<br/> SELECT \_.item, \_.units FROM \_<br/> WHERE \_.item IS NOT NULL<br/>)<br/>SELECCIONAR filas.item, SUM(rows.units) AS units<br/>FROM rows.item in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>GROUP BY rows.item</pre> |
| Selecciones donde <br/>las métricas van antes que <br/> o se mezclan con <br/>las dimensiones | <pre>SELECT SUM(metric1) AS m1, dim1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 2</pre> |

{style="table-layout:auto"}

+++

### Dimensiones

Puede seleccionar cualquiera de las dimensiones disponibles de forma predeterminada o definidas en la vista de datos. La dimensión se selecciona por su ID.

### Métricas

Las métricas disponibles para seleccionar son las siguientes:

* Cualquiera de las métricas disponibles de forma predeterminada;
* Definido en la vista de datos;
* Métricas calculadas compatibles con la vista de datos a la que el usuario tiene acceso.

Seleccione una métrica por su ID dentro de una expresión `SUM(metric)` igual que lo haría con otros orígenes SQL.

Puede usar lo siguiente:

* `SELECT COUNT(*)` o `COUNT(1)` para obtener la métrica de ocurrencias.
* `SELECT COUNT(DISTINCT dimension)` o `SELECT APPROX_COUNT_DISTINCT(dimension)` para contar los valores distintos aproximados de una dimensión. Ver detalles en [Recuento de valores distintos](#counting-distinct-values).
* [Cálculos en línea](#inline-calculations) para combinar métricas sobre la marcha o hacer cálculos matemáticos con ellas.

#### Recuento de valores distintos

Debido a la naturaleza subyacente del funcionamiento de Customer Journey Analytics, la única dimensión para la que puede obtener un recuento de distintos exactos es la dimensión `adobe_personid`. Las siguientes instrucciones SQL `SELECT COUNT(DISTINCT adobe_personid)` o `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` devuelven el valor de la métrica de personas predeterminada, que es el recuento de personas distintas. Para otras dimensiones, se devuelve un recuento distinto aproximado.

#### Métricas condicionales

Puede incrustar una cláusula `IF` o `CASE` en las funciones `SUM` o `COUNT` para añadir filtrado adicional específico de una métrica seleccionada. Añadir estas cláusulas es similar a aplicar un filtro a una columna de métrica en una tabla de informes de Workspace.

Ejemplos:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN metric1 END) AS m1
```

#### Cálculos en línea

Puede aplicar matemáticas adicionales a las expresiones de métricas en su `SELECT`. Esta matemática se puede utilizar en lugar de definir la matemática en una métrica calculada. En la tabla siguiente se enumeran los tipos de expresiones admitidos.

| Operador o función | Detalles |
|---|---|
| `+`, `-`, `*`, `/` y `%` | Sumar, restar, multiplicar, dividir y módulo/resto |
| `-X` o `+X` | Cambiar el signo de una métrica donde X es la expresión de métrica |
| `PI()` | Constante π |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH` y `TANH` | Funciones matemáticas unarias |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Funciones matemáticas binarias |

{style="table-layout:auto"}

### Columnas especiales

#### Marca de tiempo

La columna especial `timestamp` se utiliza para proporcionar los intervalos de fechas para la consulta. Un intervalo de fecha se puede definir con una expresión `BETWEEN` o un par de `timestamp` `>`, `>=`, `<`, `<=` comprobados `AND` conjuntamente.
El `timestamp` es opcional y, si no se proporciona ningún intervalo completo, se utilizan los valores predeterminados:

* Si solo se proporciona un mínimo (`timestamp > X` o ` timestamp >= X`), el intervalo es de X a ahora.
* Si solo se proporciona un máximo (`timestamp < X` o `timestamp <= X`), el intervalo va de X menos 30 días a X.
* Si no se proporciona nada, el intervalo va de ahora a menos 30 días.

El intervalo de marca de tiempo se convierte en un filtro global de intervalo de fecha en RankedRequest.
El campo de marca de tiempo también se puede utilizar en funciones de fecha y hora para analizar o truncar la marca de tiempo del evento.

#### Intervalo de fechas

La columna especial `daterange` funciona de manera similar a `timestamp`; sin embargo, el filtrado se limita a días completos. El `daterange` también es opcional y tiene los mismos valores predeterminados de intervalo que `timestamp`.
El campo `daterange` también se puede usar en funciones de fecha/hora para analizar o truncar la fecha del evento.

La columna especial `daterangeName` se puede usar para filtrar la consulta usando un intervalo de fechas con nombre como `Last Quarter`.

>[!NOTE]
>
>Power BI no admite `daterange` métricas con menos de un día (hora, 30 minutos, 5 minutos, etc.).
>

#### Identificador de filtro

La columna especial `filterId` es opcional y se utiliza para aplicar un filtro definido externamente a la consulta. La aplicación de un filtro definido externamente a una consulta es similar a arrastrar un filtro en un panel en Workspace. `AND` puede usar varios ID de filtro al usarlos.

Junto con `filterId`, puede usar `filterName` para usar el nombre de un filtro en lugar del identificador.

### Cláusula Where

La cláusula `WHERE` se administra en tres pasos:

1. Busque el intervalo de fechas en los campos especiales `timestamp`, `daterange` o `daterangeName`.

1. Busque `filterId`s o `filterName`s definidos externamente para incluirlos en el filtro.

1. Convierta las expresiones restantes en filtros ad hoc.

La gestión se realiza analizando el primer nivel de `AND`s en la cláusula `WHERE`. Cada expresión de nivel superior `AND` debe coincidir con una de las expresiones anteriores. Lo que esté por debajo del primer nivel de `AND`s, o si la cláusula `WHERE` utiliza `OR` en el nivel superior, se gestiona como un filtro ad hoc.

### Orden de clasificación

De forma predeterminada, la consulta ordena los resultados por la primera métrica seleccionada en orden descendente. Puede sobrescribir el orden de clasificación predeterminado especificando `ORDER BY ... ASC` o `ORDER BY ... DESC`. Si utiliza `ORDER BY`, debe especificar `ORDER BY` en la primera métrica seleccionada.

También puede cambiar el orden utilizando `-` (menos) delante de la métrica. Las dos sentencias siguientes dan como resultado el mismo orden:

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### Compatibilidad general con funciones

| Función | Ejemplo | Detalles |
|---|---|---|
| [Reparto](https://spark.apache.org/docs/latest/api/sql/index.html?lang=es#cast) | ``CAST(`timestamp` AS STRING)`` o <br/> `` `timestamp`::string `` | Actualmente, no se admite la conversión de tipos, pero no se genera ningún error. Se ignora la función `CAST`. |
| [Marca de tiempo](https://spark.apache.org/docs/latest/api/sql/index.html?lang=es#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Analice una cadena de tiempo como una marca de tiempo para utilizarla dentro de una cláusula `WHERE`. |
| [A marca de tiempo](https://spark.apache.org/docs/latest/api/sql/index.html?lang=es#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Analice una cadena de tiempo como una marca de tiempo para usarla dentro de una cláusula `WHERE`, proporcionando opcionalmente un formato para esa cadena de tiempo. |
| [Fecha](https://spark.apache.org/docs/latest/api/sql/index.html?lang=es#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Analice una cadena de fecha como una marca de tiempo para utilizarla dentro de una cláusula `WHERE`. |
| [Hasta la fecha](https://spark.apache.org/docs/latest/api/sql/index.html?lang=es#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Analice una cadena de fecha como una marca de tiempo para utilizarla dentro de una cláusula `WHERE`, proporcionando opcionalmente un formato para esa cadena de fecha. |

{style="table-layout:auto"}

### Compatibilidad con funciones de Dimension

Estas funciones se pueden usar en dimensiones de la cláusula `SELECT`, `WHERE` o en métricas condicionales.

**Funciones de cadena**

| Función | Ejemplo | Detalles |
|---|---|---|
| [Inferior](https://spark.apache.org/docs/latest/api/sql/index.html?lang=es#lower) | ``SELECT LOWER(name) AS lower_name`` | Genere una identidad de dimensión dinámica en el campo pasado. |

{style="table-layout:auto"}

**Funciones de fecha y hora**

| Función | Ejemplo | Detalles |
|---|---|---|
| [Año](https://spark.apache.org/docs/latest/api/sql/index.html?lang=es#year) | ``SELECT YEAR(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. |
| [Mes](https://spark.apache.org/docs/latest/api/sql/index.html?lang=es#month) | ``SELECT MONTH(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. |
| [Día](https://spark.apache.org/docs/latest/api/sql/index.html?lang=es#day) | ``SELECT DAY(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. |
| [Día de la semana](https://spark.apache.org/docs/latest/api/sql/index.html?lang=es#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. Utilice el ID del elemento en lugar del valor, ya que necesita el número y no el nombre descriptivo. |
| [Día del año](https://spark.apache.org/docs/latest/api/sql/index.html?lang=es#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. |
| [Semana](https://spark.apache.org/docs/latest/api/sql/index.html?lang=es#week) | ``SELECT WEEK(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. |
| [Trimestre](https://spark.apache.org/docs/latest/api/sql/index.html?lang=es#quarter) | ``SELECT QUARTER(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. |
| [Hora](https://spark.apache.org/docs/latest/api/sql/index.html?lang=es#hour) | ``SELECT HOUR(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. Utilice el ID del elemento en lugar del valor, ya que necesita el número y no el nombre descriptivo. |
| [Minuto](https://spark.apache.org/docs/latest/api/sql/index.html?lang=es#minute) | ``SELECT MINUTE(`timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. |
| [Extraer](https://spark.apache.org/docs/latest/api/sql/index.html?lang=es#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. Utilice el ID del elemento en lugar del valor para algunas partes de esta función, ya que necesita el número y no el nombre descriptivo.<br/>Las partes compatibles son:<br>- Palabras clave: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- Cadenas:  `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` o `'MINUTE'`. |
| [Fecha (parte)](https://spark.apache.org/docs/latest/api/sql/index.html?lang=es#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado. Utilice el ID del elemento en lugar del valor para algunas partes de esta función, ya que necesita el número y no el nombre descriptivo.<br/>Las partes de cadena compatibles son: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'` o `'MINUTE'`. |
| [Fecha (truncada)](https://spark.apache.org/docs/latest/api/sql/index.html?lang=es#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Genere una identidad de dimensión dinámica en el campo pasado.<br/>Las granularidades de cadena compatibles son: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, o `'MINUTE'`. |

{style="table-layout:auto"}

### Compatibilidad parcial

Algunas funcionalidades de SQL solo se admiten parcialmente con la extensión de BI y no devuelven los mismos resultados que se ven con otras bases de datos.  Esta funcionalidad específica se utiliza en SQL generado por varias herramientas de BI, para las que la extensión de BI no tiene una coincidencia exacta. Como resultado, la extensión de BI se centra en una implementación limitada que cubre el uso mínimo de la herramienta de BI sin arrojar errores. Consulte la tabla siguiente para obtener más detalles.

| Función | Ejemplo | Detalles |
|---|---|---|
| MIN() &amp; MAX() | ``MIN(daterange)`` o <br/> ``MAX(daterange)`` | `MIN()` el `timestamp`, `daterange` o cualquiera de los `daterangeX` como `daterangeday` regresará hace 2 años.<br/><br/> `MAX()` el `timestamp`, `daterange` o cualquiera de los `daterangeX` como `daterangeday` devolverá la fecha/hora actual.<br/><br/>`MIN()` o `MAX()` en cualquier otra dimensión, métrica o expresión devolverá 0. |

{style="table-layout:auto"}
