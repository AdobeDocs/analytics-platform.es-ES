---
title: Casos de uso para la extensión de BI en Customer Journey Analytics
description: Casos de uso múltiple que muestran cómo utilizar la extensión de BI en varias herramientas de BI en Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
hide: true
hidefromtoc: true
exl-id: 07db28b8-b688-4a0c-8fb3-28a124342d25
source-git-commit: d6d6777f3d40a979eefecea6ab6d4bd818be2401
workflow-type: tm+mt
source-wordcount: '9736'
ht-degree: 1%

---

# Casos de uso de extensión de BI

Este artículo explica cómo realizar una serie de casos de uso mediante la extensión de BI de Customer Journey Analytics. En cada caso de uso se explica la funcionalidad del Customer Journey Analytics, seguida de detalles para cada una de las herramientas de BI admitidas:

* **Escritorio de Power BI**. La versión utilizada es 2.137.1102.0 de 64 bits (octubre de 2024).
* **Escritorio Tableau**. La versión utilizada es 2024.1.5 (20241.24.0705.0334) de 64 bits.

Los siguientes casos de uso están documentados:

* **Conectar**
   * [Conexión y lista de vistas de datos](#connect-and-validate)

* **Informar y analizar**
   * [Tendencia diaria](#daily-trend)
   * [Tendencia horaria](#hourly-trend)
   * [Tendencia mensual](#monthly-trend)
   * [Dimensión única clasificada](#single-dimension-ranked)
   * [Clasificación de varias dimensiones](#multiple-dimension-ranked)
   * [Contar valores de dimensión distintos](#count-distinct-dimension-values)
   * [Usar nombres de intervalo de fechas para filtrar](#use-date-range-names-to-filter)
   * [Usar nombres de filtro para filtrar](#use-filter-names-to-filter)
   * [Uso de valores de dimensión para filtrar](#use-dimension-values-to-filter)
   * [Ordenar](#sort)
   * [Límites](#limits)

* **Comprender**

   * [Transformaciones](#transformations)
   * [Visualizaciones](#visualizations)
   * [Advertencias](#caveats)

El caso de uso **connect** se centra en cómo conectar herramientas de BI mediante la extensión de BI de Customer Journey Analytics.

Los casos de uso de **report and analysis** indican cómo realizar visualizaciones de Customer Journey Analytics similares en las herramientas de BI admitidas actualmente.

Los casos de uso **entiendo** proporcionan más detalles sobre:

* Transformaciones que se producen cuando se utilizan las herramientas de un BI para informar y analizar.
* Similitudes y diferencias de visualización entre las herramientas de Customer Journey Analytics y BI.
* Advertencias de cada una de las herramientas de BI que debe tener en cuenta.


## Conexión y validación

En este ejemplo de uso se configura la conexión de la herramienta BI al Customer Journey Analytics, se enumeran las vistas de datos disponibles y se selecciona una vista de datos para utilizarla.

+++ Customer Journey Analytics

Las instrucciones hacen referencia a un entorno de ejemplo con los siguientes objetos:

* Vista de datos: **[!UICONTROL C&amp;C - Vista de datos]** ??.
* Dimension: **[!UICONTROL Nombre de producto]** ?? y **[!UICONTROL Categoría de producto]** ??.
* Métricas: **[!UICONTROL Ingresos de compras]** ?? y **[!UICONTROL Compras]** ??.
* Filtro: **[!UICONTROL Productos de pesca]** ??.

![Configuración de base de Customer Journey Analytics](assets/cja-base.png){zoomable="yes"}

Cuando revise los casos de uso, reemplace estos objetos de ejemplo por objetos adecuados para su entorno específico.

+++

+++ Herramientas de BI

>[!BEGINTABS]

>[!TAB Escritorio de Power BI]

1. Acceda a las credenciales y los parámetros necesarios desde la interfaz de usuario del servicio de consultas de Experience Platform.

   1. Vaya a la zona protegida del Experience Platform.
   1. Seleccione ![Consultas](/help/assets/icons/DataSearch.svg) **[!UICONTROL Consultas]** del carril izquierdo.
   1. Seleccione la ficha **[!UICONTROL Credenciales]** en la interfaz de **[!UICONTROL Consultas]**.
   1. Seleccione `prod:cja` del menú desplegable **[!UICONTROL Base de datos]**.

      ![Credenciales del servicio de consulta](assets/queryservice-credentials.png){zoomable="yes"}

1. Inicie Power BI Desktop.
   1. En la interfaz principal, seleccione **[!UICONTROL Obtener datos de otras fuentes]**.
   1. En el diálogo **[!UICONTROL Obtener datos]**:
      ![Base de datos PostgreSQL de Power BI](assets/powerbi-postgresql.png){zoomable="yes"}
      1. Busque y seleccione **[!UICONTROL base de datos PostgreSQL]**.
      1. Seleccione **[!UICONTROL Conectar]**.
   1. En el diálogo **[!UICONTROL Base de datos PostgreSQL]**:
      ![Configuración de base de datos y servidor de escritorio de PowerBI](assets/powerbi-serverdatabase.png){zoomable="yes"}
      1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar y pegar los valores de **[!UICONTROL Host]** y **[!UICONTROL Puerto]** del panel **[!UICONTROL Consulta]** **[!UICONTROL Credenciales que caducan]** del Experience Platform, separados por `:` como valor de **[!UICONTROL Servidor]**. Por ejemplo: `examplecompany.platform-query.adobe.io:80`.
      1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar y pegar el valor **[!UICONTROL Base de datos]** del panel **[!UICONTROL Consulta]** **[!UICONTROL Credenciales que caducan]** del Experience Platform. Agregue `?FLATTEN` al valor que pegue. Por ejemplo, `prod:cja?FLATTEN`.
      1. Seleccione **[!UICONTROL DirectQuery]** como **[!UICONTROL modo de conectividad de datos]**.
      1. Seleccione **[!UICONTROL Aceptar]**.
   1. En el cuadro de diálogo **[!UICONTROL Base de datos PostgreSQL]** - **[!UICONTROL Base de datos]**:
      ![Usuario y contraseña de PowerBI Desktop](assets/powerbi-userpassword.png){zoomable="yes"}
      1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar los valores de **[!UICONTROL Nombre de usuario]** y **[!UICONTROL Contraseña]** del panel **[!UICONTROL Consulta]** **[!UICONTROL Credenciales que caducan]** del Experience Platform en los campos **[!UICONTROL Nombre de usuario]** y **[!UICONTROL Contraseña]**. Si usa una [credencial que no caduca](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect), use la contraseña de la credencial que no caduca.
      1. Asegúrese de que el menú desplegable de **[!UICONTROL Seleccione el nivel en el que aplicar esta configuración a]** esté establecido en el **[!UICONTROL Servidor]** que ha definido anteriormente.
      1. Seleccione **[!UICONTROL Conectar]**.
   1. En el cuadro de diálogo **[!UICONTROL Navegador]**, se recuperan las vistas de datos. Esta recuperación puede tardar un poco. Una vez recuperado, verá lo siguiente en Power BI Desktop.
      ![Datos de carga de escritorio de Power BI](assets/powerbi-navigator-load.png){zoomable="yes"}
      1. Seleccione **[!UICONTROL public.cc_data_view]** de la lista del panel izquierdo.
      1. Existen dos opciones:
         1. Seleccione **[!UICONTROL Cargar]** para continuar y finalizar la instalación.
         1. Seleccione **[!UICONTROL Transformar datos]**. Verá un cuadro de diálogo en el que, opcionalmente, puede aplicar transformaciones como parte de la configuración.
            ![Datos de transformación de escritorio de Power BI](assets/powerbi-transform-data.png){zoomable="yes"}
            * Seleccione **[!UICONTROL Cerrar y aplicar]**.
   1. Después de un tiempo, **[!UICONTROL public.cc_data_view]** se mostrará en el panel **[!UICONTROL Datos]**. Seleccione ![ChevronRight](/help/assets/icons/ChevronRight.svg) para mostrar dimensiones y métricas.
      Power BI ![Datos Del Servidor De Escritorio Cargados](assets/powerbi-navigator-loaded.png){zoomable="yes"}


### Para ACOPLAR o no

Power BI Desktop admite los siguientes escenarios para el parámetro `FLATTEN`. Consulte [Acoplar datos anidados](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) para obtener más información.

| Parámetro FLATTEN | Ejemplo | Admitido | Observaciones |
|---|---|:---:|---|
| Ninguno | `prod:cja` | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | |
| `?FLATTEN` | `prod:cja?FLATTEN` | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | **Opción recomendada para usar!** |
| `%3FFLATTEN` | `prod:cja%3FFLATTEN` | ![CerrarCírculo](/help/assets/icons/CloseCircle.svg) | Error en Power BI Desktop: **[!UICONTROL No se pudo autenticar con las credenciales proporcionadas. Inténtelo de nuevo.]** |

### Más información

* [Requisitos previos](/help/data-views/bi-extension.md#prerequisites)
* [Guía de credenciales](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials)
* [Conectar Power BI al servicio de consultas](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/power-bi).




>[!TAB Escritorio Tableau]

1. Acceda a las credenciales y los parámetros necesarios desde la interfaz de usuario del servicio de consultas de Experience Platform.

   1. Vaya a la zona protegida del Experience Platform.
   1. Seleccione ![Consultas](/help/assets/icons/DataSearch.svg) **[!UICONTROL Consultas]** del carril izquierdo.
   1. Seleccione la ficha **[!UICONTROL Credenciales]** en la interfaz de **[!UICONTROL Consultas]**.
   1. Seleccione `prod:cja` del menú desplegable **[!UICONTROL Base de datos]**.

      ![Credenciales del servicio de consulta](assets/queryservice-credentials.png){zoomable="yes"}

1. Inicie Tableau.
   1. Seleccione **[!UICONTROL PostgreSQL]** del carril izquierdo debajo de **[!UICONTROL A un servidor]**. Si no está disponible, seleccione **[!UICONTROL Más...]** y seleccione **[!UICONTROL PostgreSQL]** de los **[!UICONTROL Conectores instalados]**.
      ![Conectores Tableau](assets/tableau-connectors.png){zoomable="yes"}
   1. En el cuadro de diálogo **[!UICONTROL PostgreSQL]**, en la ficha **[!UICONTROL General]**:
      ![Cuadro de diálogo de inicio de sesión en Tableau](assets/tableau-signin.png){zoomable="yes"}
      1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar y pegar el **[!UICONTROL host]** del panel **[!UICONTROL Consulta]** **[!UICONTROL Credenciales que caducan]** del Experience Platform en el **[!UICONTROL Servidor]**.
      1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar y pegar el **[!UICONTROL puerto]** del panel **[!UICONTROL Consulta]** **[!UICONTROL Credenciales que caducan]** del Experience Platform en el **[!UICONTROL puerto]**.
      1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar y pegar la **[!UICONTROL base de datos]** del panel **[!UICONTROL Consulta]** **[!UICONTROL Credenciales que caducan]** del Experience Platform en la **[!UICONTROL base de datos]**. Agregue `%3FFLATTEN` al valor que pegue. Por ejemplo: `prod:cja%3FFLATTEN`.
      1. Seleccione **[!UICONTROL Nombre de usuario y Contraseña]** del menú desplegable **[!UICONTROL Autenticación]**.
      1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar y pegar el **[!UICONTROL nombre de usuario]** del panel **[!UICONTROL Consulta]** **[!UICONTROL Credenciales de caducidad]** del Experience Platform en el **[!UICONTROL nombre de usuario]**.
      1. Use ![Copiar](/help/assets/icons/Copy.svg) para copiar y pegar la **[!UICONTROL contraseña]** del panel **[!UICONTROL Consulta]** **[!UICONTROL Credenciales de caducidad]** del Experience Platform en **[!UICONTROL Contraseña]**. Si usa una [credencial que no caduca](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect), use la contraseña de la credencial que no caduca.
      1. Asegúrese de comprobar **[!UICONTROL Requerir SSL]**.
      1. Seleccione **[!UICONTROL Iniciar sesión]**.

      Verá un cuadro de diálogo **[!UICONTROL Solicitud en curso]** mientras Tableau Desktop valida la conexión.
   1. En la ventana principal, verá en la página **[!UICONTROL Source de datos]**, en el panel izquierdo:
      * Nombre de la conexión, debajo de **[!UICONTROL Connections]**.
      * Nombre de la base de datos, debajo de **[!UICONTROL Database]**.
      * Una lista de tablas, debajo de **[!UICONTROL Tabla]**.
        ![Tableau conectado](assets/tableau-connected.png){zoomable="yes"}
      1. Arrastre la entrada **[!UICONTROL cc_data_view]** y suéltela en la vista principal que dice **[!UICONTROL Arrastrar tablas]** aquí.
   1. La ventana principal muestra detalles de la vista de datos **[!UICONTROL cc_data_view]**.
      ![Tableau conectado](assets/tableau-validation.png){zoomable="yes"}

### Para ACOPLAR o no

Tableau Desktop admite los siguientes escenarios para el parámetro `FLATTEN`. Consulte [Acoplar datos anidados](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) para obtener más información.

| Parámetro FLATTEN | Ejemplo | Admitido | Observaciones |
|---|---|:---:|---|
| Ninguno | `prod:cja` | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | |
| `?FLATTEN` | `prod:cja?FLATTEN` | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | |
| `%3FFLATTEN` | `prod:cja%3FFLATTEN` | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | **Opción recomendada para usar**. Tenga en cuenta que `%3FFLATTEN` es una versión de `?FLATTEN` con codificación de dirección URL. |

### Más información

* [Requisitos previos](/help/data-views/bi-extension.md#prerequisites)
* [Guía de credenciales](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials)
* [Conectar Tableau Desktop al servicio de consultas](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/tableau).



>[!ENDTABS]

+++


## Tendencia diaria

En este caso de uso, desea mostrar una tabla y una visualización de línea simple que muestre una tendencia diaria de ocurrencias (eventos) desde el 1 de enero de 2023 hasta el 31 de enero de 2023.

+++ Customer Journey Analytics

Un ejemplo del panel **[!UICONTROL Tendencia diaria]** para el caso de uso:

![Panel de tendencias diarias de Customer Journey Analytics](assets/cja_daily_trend.png){zoomable="yes"}

+++

+++ Herramientas de BI

>[!PREREQUISITES]
>
>Asegúrese de que ha validado una conexión correcta de [y de que puede enumerar y usar vistas de datos](#connect-and-validate) para la herramienta de BI para la que desea probar este caso de uso.
>

>[!BEGINTABS]

>[!TAB Escritorio de Power BI]

1. En el panel **[!UICONTROL Datos]**:
   1. Seleccione **[!UICONTROL daterangeday]**.
   1. Seleccionar **[!UICONTROL ∑ repeticiones]**.

   Verá una tabla que muestra las ocurrencias del mes actual. Para obtener una mejor visibilidad, amplíe la visualización.

1. En el panel **[!UICONTROL Filtros]**:

   1. Seleccione **[!UICONTROL daterangedday is (All)]** de **[!UICONTROL Filtros en esta imagen]**.
   1. Seleccione **[!UICONTROL Filtro avanzado]** como **[!UICONTROL Tipo de filtro]**.
   1. Defina el filtro para **[!UICONTROL Mostrar elementos cuando el valor]** **[!UICONTROL esté en]** `1/1/2023` **[!UICONTROL y]** **[!UICONTROL esté antes de]** `2/1/2023.`. Puede usar el icono del calendario para elegir y seleccionar fechas.
   1. Seleccione **[!UICONTROL Aplicar filtro]**.

   Verá la tabla actualizada con el filtro **[!UICONTROL daterangeday]** aplicado.

1. En el panel **[!UICONTROL Visualizaciones]**, seleccione la visualización **[!UICONTROL Gráfico de líneas]**.

   Una visualización de gráfico de líneas reemplaza la tabla mientras utiliza los mismos datos que la tabla. El escritorio de Power BI debe tener el aspecto siguiente.

   ![Filtro de intervalo de fechas del caso de uso 2 del escritorio de Power BI](assets/uc2-pbi-daterange.png){zoomable="yes"}

1. En la visualización del gráfico de líneas:

   1. Seleccione ![Más](/help/assets/icons/More.svg).
   1. En el menú contextual, seleccione **[!UICONTROL Mostrar como tabla]**.

   La vista principal se actualiza para mostrar una visualización de líneas y una tabla. El escritorio de Power BI debe tener el aspecto siguiente.

   ![Visualización de tendencias diarias finales del caso de uso 2 del escritorio de Power BI](assets/uc2-pbi-final.png){zoomable="yes"}

>[!TAB Escritorio Tableau]

1. Seleccione la ficha **[!UICONTROL Hoja 1]** en la parte inferior para cambiar de la vista **[!UICONTROL Fuente de datos]**. En la vista **[!UICONTROL Hoja 1]**:
   1. Arrastre la entrada **[!UICONTROL Daterange]** de la lista **[!UICONTROL Tablas]** en el panel **[!UICONTROL Datos]** y suéltela en el estante **[!UICONTROL Filtros]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtros de campo \[Intervalo de fechas\]]**, seleccione **[!UICONTROL Intervalo de fechas]** y seleccione **[!UICONTROL Siguiente >]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtrar \[Daterange]]**, seleccione **[!UICONTROL Intervalo de fechas]** y especifique un período de `01/01/2023` - `01/02/2023`.

      ![Filtro Tableau para escritorio](assets/uc2-tableau-filter.png){zoomable="yes"}

   1. Arrastre y suelte **[!UICONTROL Daterangeday]** de la lista **[!UICONTROL Tablas]** en el panel **[!UICONTROL Datos]** y suelte la entrada en el campo junto a **[!UICONTROL Columnas]**.
      * Seleccione **[!UICONTROL Día]** del menú desplegable **[!UICONTROL Daterangeday]**, para que el valor se actualice a **[!UICONTROL DAY(Daterangeday)]**.
   1. Arrastre y suelte **[!UICONTROL Ocurrencias]** de la lista **[!UICONTROL Tablas (*Nombres de medida*)]** en el panel **[!UICONTROL Datos]** y suelte la entrada en el campo junto a **[!UICONTROL Filas]**.
      * Los valores se convierten automáticamente a **[!UICONTROL SUM(Occurrences)]**.
   1. Modifique **[!UICONTROL Estándar]** a **[!UICONTROL Vista completa]** desde el menú desplegable **[!UICONTROL Ajustar]** de la barra de herramientas.

      El escritorio Tableau debe tener el aspecto siguiente.

      ![Tableau Desktop Graph](assets/uc2-tableau-graph.png){zoomable="yes"}

1. Seleccione **[!UICONTROL Duplicate]** del menú contextual de la ficha **[!UICONTROL Hoja 1]** para crear una segunda hoja.
1. Seleccione **[!UICONTROL Rename]** del menú contextual de la ficha **[!UICONTROL Hoja 1]** para cambiar el nombre de la hoja a `Graph`.
1. Seleccione **[!UICONTROL Rename]** del menú contextual de la ficha **[!UICONTROL Hoja 1 (2)]** para cambiar el nombre de la hoja a `Data`.
1. Asegúrese de que la hoja **[!UICONTROL Data]** esté seleccionada. En la vista **[!UICONTROL Datos]**:
   1. Seleccione **[!UICONTROL Mostrarme]** en la parte superior derecha y seleccione **[!UICONTROL Tabla de texto]** (visualización superior izquierda superior) para modificar el contenido de la vista de datos a una tabla.
   1. Seleccione **[!UICONTROL Intercambiar filas y columnas]** en la barra de herramientas.
   1. Modifique **[!UICONTROL Estándar]** a **[!UICONTROL Vista completa]** desde el menú desplegable **[!UICONTROL Ajustar]** de la barra de herramientas.

      El escritorio Tableau debe tener el aspecto siguiente.

      ![Datos de escritorio Tableau](assets/uc2-tableau-data.png){zoomable="yes"}

1. Seleccione el botón de pestaña **[!UICONTROL Nuevo panel]** (en la parte inferior) para crear una nueva vista de **[!UICONTROL panel 1]**. En la vista **[!UICONTROL Panel 1]**:
   1. Arrastre y suelte la hoja **[!UICONTROL Graph]** del estante **[!UICONTROL Sheets]** en la vista **[!UICONTROL Dashboard 1]** que dice *Colocar hojas aquí*.
   1. Arrastre y suelte la hoja **[!UICONTROL Data]** del estante **[!UICONTROL Sheets]** debajo de la hoja **[!UICONTROL Graph]** en la vista **[!UICONTROL Dashboard 1]**.
   1. Seleccione la hoja **[!UICONTROL Data]** en la vista y modifique **[!UICONTROL Toda la vista]** a **[!UICONTROL Anchura de la corrección]**.

      El escritorio Tableau debe tener el aspecto siguiente.

      ![Tablero de escritorio Tableau 1](assets/uc2-tableau-dashboard.png){zoomable="yes"}

>[!ENDTABS]

+++


## Tendencia horaria

En este caso de uso, desea mostrar una tabla y una visualización de línea simple que muestre una tendencia horaria de ocurrencias (eventos) para el 1 de enero de 2023.

+++ Customer Journey Analytics

Un ejemplo del panel **[!UICONTROL Tendencia horaria]** para el caso de uso:

![Visualizaciones de tendencias por hora de Customer Journey Analytics](assets/cja_hourly_trend.png){zoomable="yes"}

+++

+++ Herramientas de BI

>[!PREREQUISITES]
>
>Asegúrese de que ha validado [una conexión correcta, que puede enumerar vistas de datos y que utiliza una vista de datos](#connect-and-validate) para la herramienta de BI para la que desea probar este caso de uso.
>

>[!BEGINTABS]

>[!TAB Escritorio de Power BI]

El Power BI ![AlertRed](/help/assets/icons/AlertRed.svg) no entiende **cómo manejar los campos de fecha y hora, por lo que no se admiten dimensiones como**[!UICONTROL  daterangehour ]**y**[!UICONTROL  daterangeminute ]**.**

>[!TAB Escritorio Tableau]

1. Seleccione la ficha **[!UICONTROL Hoja 1]** en la parte inferior para cambiar de **[!UICONTROL Fuente de datos]**. En la vista **[!UICONTROL Hoja 1]**:
   1. Arrastre la entrada **[!UICONTROL Daterange]** de la lista **[!UICONTROL Tablas]** en el panel **[!UICONTROL Datos]** y suéltela en el estante **[!UICONTROL Filtros]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtros de campo \[Intervalo de fechas\]]**, seleccione **[!UICONTROL Intervalo de fechas]** y seleccione **[!UICONTROL Siguiente >]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtrar \[Daterange]]**, seleccione **[!UICONTROL Intervalo de fechas]** y especifique un período de `01/01/2023` - `02/01/2023`.

      ![Filtro Tableau para escritorio](assets/uc3-tableau-filter.png){zoomable="yes"}

   1. Arrastre y suelte **[!UICONTROL Daterangehour]** de la lista **[!UICONTROL Tablas]** en el panel **[!UICONTROL Datos]** y suelte la entrada en el campo junto a **[!UICONTROL Columnas]**.
      * Seleccione **[!UICONTROL Más]** > **[!UICONTROL Horas]** del menú desplegable **[!UICONTROL Daterangeday]**, para que el valor se actualice a **[!UICONTROL HOUR(Daterangeday)]**.
   1. Arrastre y suelte **[!UICONTROL Ocurrencias]** de la lista **[!UICONTROL Tablas (*Nombres de medida*)]** en el panel **[!UICONTROL Datos]** y suelte la entrada en el campo junto a **[!UICONTROL Filas]**.
      * Los valores se convierten automáticamente a **[!UICONTROL SUM(Occurrences)]**.
   1. Modifique **[!UICONTROL Estándar]** a **[!UICONTROL Vista completa]** desde el menú desplegable **[!UICONTROL Ajustar]** de la barra de herramientas.

      El escritorio Tableau debe tener el aspecto siguiente.

      ![Tableau Desktop Graph](assets/uc3-tableau-graph.png){zoomable="yes"}

1. Seleccione **[!UICONTROL Duplicate]** del menú contextual de la ficha **[!UICONTROL Hoja 1]** para crear una segunda hoja.
1. Seleccione **[!UICONTROL Rename]** del menú contextual de la ficha **[!UICONTROL Hoja 1]** para cambiar el nombre de la hoja a `Graph`.
1. Seleccione **[!UICONTROL Rename]** del menú contextual de la ficha **[!UICONTROL Hoja 1 (2)]** para cambiar el nombre de la hoja a `Data`.
1. Asegúrese de que la hoja **[!UICONTROL Data]** esté seleccionada. En la vista **[!UICONTROL Datos]**:
   1. Seleccione **[!UICONTROL Mostrarme]** en la parte superior derecha y seleccione **[!UICONTROL Tabla de texto]** (visualización superior izquierda superior) para modificar el contenido de la vista de datos a una tabla.
   1. Arrastre **[!UICONTROL HOUR(Daterangeday)]** de **[!UICONTROL Columnas]** a **[!UICONTROL Filas]**.
   1. Modifique **[!UICONTROL Estándar]** a **[!UICONTROL Vista completa]** desde el menú desplegable **[!UICONTROL Ajustar]** de la barra de herramientas.

      El escritorio Tableau debe tener el aspecto siguiente.

      ![Datos de escritorio Tableau](assets/uc3-tableau-data.png){zoomable="yes"}

1. Seleccione el botón de pestaña **[!UICONTROL Nuevo panel]** (en la parte inferior) para crear una nueva vista de **[!UICONTROL panel 1]**. En la vista **[!UICONTROL Panel 1]**:
   1. Arrastre y suelte la hoja **[!UICONTROL Graph]** del estante **[!UICONTROL Sheets]** en la vista **[!UICONTROL Dashboard 1]** que dice *Colocar hojas aquí*.
   1. Arrastre y suelte la hoja **[!UICONTROL Data]** del estante **[!UICONTROL Sheets]** debajo de la hoja **[!UICONTROL Graph]** en la vista **[!UICONTROL Dashboard 1]**.
   1. Seleccione la hoja **[!UICONTROL Data]** en la vista y modifique **[!UICONTROL Toda la vista]** a **[!UICONTROL Anchura de la corrección]**.

      La vista del **[!UICONTROL panel 1]** debería ser similar a la siguiente.

      ![Tablero de escritorio Tableau 1](assets/uc3-tableau-dashboard.png){zoomable="yes"}


>[!ENDTABS]

+++


## Tendencia mensual

En este caso de uso, desea mostrar una tabla y una visualización de línea simple que muestre una tendencia mensual de la incidencia (eventos) para 2023.

+++ Customer Journey Analytics

Un ejemplo del panel **[!UICONTROL Tendencia mensual]** para el caso de uso:

![Visualización de tendencias mensuales de Customer Journey Analytics](assets/cja_monthly_trend.png){zoomable="yes"}

+++

+++ Herramientas de BI

>[!PREREQUISITES]
>
>Asegúrese de que ha validado [una conexión correcta, que puede enumerar vistas de datos y que utiliza una vista de datos](#connect-and-validate) para la herramienta de BI para la que desea probar este caso de uso.
>

>[!BEGINTABS]

>[!TAB Escritorio de Power BI]

1. En el panel **[!UICONTROL Datos]**:
   1. Seleccione **[!UICONTROL daterangemonth]**.
   1. Seleccionar **[!UICONTROL ∑ repeticiones]**.

   Verá una tabla que muestra las ocurrencias del mes actual. Para obtener una mejor visibilidad, amplíe la visualización.

1. En el panel **[!UICONTROL Filtros]**:

   1. Seleccione **[!UICONTROL daterangemonth is (All)]** de **[!UICONTROL Filtros en este elemento visual]**.
   1. Seleccione **[!UICONTROL Filtro avanzado]** como **[!UICONTROL Tipo de filtro]**.
   1. Defina el filtro para **[!UICONTROL Mostrar elementos cuando el valor]** **[!UICONTROL esté en]** `1/1/2023` **[!UICONTROL y]** **[!UICONTROL esté antes de]** `1/1/2024.`. Puede usar el icono del calendario para elegir y seleccionar fechas.
   1. Seleccione **[!UICONTROL Aplicar filtro]**.

   Verá la tabla actualizada con el filtro **[!UICONTROL daterangemonth]** aplicado.

1. En el panel **[!UICONTROL Visualizaciones]**:

   1. Seleccione la visualización **[!UICONTROL Gráfico de líneas]**.

   Una visualización de gráfico de líneas reemplaza la tabla mientras utiliza los mismos datos que la tabla. El escritorio de Power BI debe tener el aspecto siguiente.

   ![Filtro de intervalo de fechas del caso de uso 2 del escritorio de Power BI](assets/uc4-pbi-filter-daterange.png){zoomable="yes"}

1. En la visualización del gráfico de líneas:

   1. Seleccione ![Más](/help/assets/icons/More.svg).
   1. En el menú contextual, seleccione **[!UICONTROL Mostrar como tabla]**.

   La vista principal se actualiza para mostrar una visualización de líneas y una tabla. El escritorio de Power BI debe tener el aspecto siguiente.

   ![Visualización de tendencias diarias finales del caso de uso 2 del escritorio de Power BI](assets/uc4-pbi-filter-final.png){zoomable="yes"}

>[!TAB Escritorio Tableau]

1. Seleccione la ficha **[!UICONTROL Hoja 1]** en la parte inferior para cambiar de **[!UICONTROL Fuente de datos]**. En la vista **[!UICONTROL Hoja 1]**:
   1. Arrastre la entrada **[!UICONTROL Daterange]** de la lista **[!UICONTROL Tablas]** en el panel **[!UICONTROL Datos]** y suéltela en el estante **[!UICONTROL Filtros]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtros de campo \[Intervalo de fechas\]]**, seleccione **[!UICONTROL Intervalo de fechas]** y seleccione **[!UICONTROL Siguiente >]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtrar \[Daterange]]**, seleccione **[!UICONTROL Intervalo de fechas]** y especifique un período de `01/01/2023` - `01/01/2024`.

      ![Filtro Tableau para escritorio](assets/uc4-tableau-filter.png){zoomable="yes"}

   1. Arrastre y suelte **[!UICONTROL Daterangeday]** de la lista **[!UICONTROL Tablas]** en el panel **[!UICONTROL Datos]** y suelte la entrada en el campo junto a **[!UICONTROL Columnas]**.
      * Seleccione **[!UICONTROL MONTH]** en el menú desplegable **[!UICONTROL Daterangeday]**, para que el valor se actualice a **[!UICONTROL MONTH(Daterangeday)]**.
   1. Arrastre y suelte **[!UICONTROL Ocurrencias]** de la lista **[!UICONTROL Tablas (*Nombres de medida*)]** en el panel **[!UICONTROL Datos]** y suelte la entrada en el campo junto a **[!UICONTROL Filas]**.
      * Los valores se convierten automáticamente a **[!UICONTROL SUM(Occurrences)]**.
   1. Modifique **[!UICONTROL Estándar]** a **[!UICONTROL Vista completa]** desde el menú desplegable **[!UICONTROL Ajustar]** de la barra de herramientas.

      El escritorio Tableau debe tener el aspecto siguiente.

      ![Tableau Desktop Graph](assets/uc4-tableau-graph.png){zoomable="yes"}

1. Seleccione **[!UICONTROL Duplicate]** del menú contextual de la ficha **[!UICONTROL Hoja 1]** para crear una segunda hoja.
1. Seleccione **[!UICONTROL Rename]** del menú contextual de la ficha **[!UICONTROL Hoja 1]** para cambiar el nombre de la hoja a `Graph`.
1. Seleccione **[!UICONTROL Rename]** del menú contextual de la ficha **[!UICONTROL Hoja 1 (2)]** para cambiar el nombre de la hoja a `Data`.
1. Asegúrese de que la hoja **[!UICONTROL Data]** esté seleccionada. En la vista Datos:
   1. Seleccione **[!UICONTROL Mostrarme]** en la parte superior derecha y seleccione **[!UICONTROL Tabla de texto]** (visualización superior izquierda superior) para modificar el contenido de la vista de datos a una tabla.
   1. Arrastre **[!UICONTROL MONTH(Daterangeday)]** de **[!UICONTROL Columnas]** a **[!UICONTROL Filas]**.
   1. Modifique **[!UICONTROL Estándar]** a **[!UICONTROL Vista completa]** desde el menú desplegable **[!UICONTROL Ajustar]** de la barra de herramientas.

      El escritorio Tableau debe tener el aspecto siguiente.

      ![Datos de escritorio Tableau](assets/uc4-tableau-data.png){zoomable="yes"}

1. Seleccione el botón de pestaña **[!UICONTROL Nuevo panel]** (en la parte inferior) para crear una nueva vista de **[!UICONTROL panel 1]**. En la vista **[!UICONTROL Panel 1]**:
   1. Arrastre y suelte la hoja **[!UICONTROL Graph]** del estante **[!UICONTROL Sheets]** en la vista **[!UICONTROL Dashboard 1]** que dice *Colocar hojas aquí*.
   1. Arrastre y suelte la hoja **[!UICONTROL Data]** del estante **[!UICONTROL Sheets]** debajo de la hoja **[!UICONTROL Graph]** en la vista **[!UICONTROL Dashboard 1]**.
   1. Seleccione la hoja **[!UICONTROL Data]** en la vista y modifique **[!UICONTROL Toda la vista]** a **[!UICONTROL Anchura de la corrección]**.

      El escritorio Tableau debe tener el aspecto siguiente.

      ![Tablero de escritorio Tableau 1](assets/uc4-tableau-dashboard.png){zoomable="yes"}

>[!ENDTABS]

+++


## Dimensión única clasificada

En este caso de uso, desea mostrar una tabla y una visualización de barra simple que muestre los ingresos de compras y compras para nombres de productos a lo largo de 2023.

+++ Customer Journey Analytics

Un ejemplo del panel **[!UICONTROL Clasificación de un solo Dimension]** para el caso de uso:

![Visualización de clasificación de dimensión única de Customer Journey Analytics](assets/cja-single-dimension-ranked.png){zoomable="yes"}
+++

+++ Herramientas de BI

>[!PREREQUISITES]
>
>Asegúrese de que ha validado [una conexión correcta, que puede enumerar vistas de datos y que utiliza una vista de datos](#connect-and-validate) para la herramienta de BI para la que desea probar este caso de uso.
>

>[!BEGINTABS]

>[!TAB Escritorio de Power BI]

1. En el panel **[!UICONTROL Datos]**:
   1. Seleccione **[!UICONTROL daterange]**.
   1. Seleccione **[!UICONTROL product_name]**.
   1. Seleccione **[!UICONTROL ∑ purchase_revenue]**.
   1. Seleccione **[!UICONTROL ∑ compras]**.

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

   ![Estado de la tabla del caso de uso 5 del escritorio de Power BI](assets/uc5-pbi-table.png){zoomable="yes"}

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

   ![Gráfico del caso de uso 5 del escritorio de Power BI](assets/uc5-pbi-chart.png){zoomable="yes"}

1. Visualización del gráfico de columnas apiladas y líneas:

   1. Seleccione ![Más](/help/assets/icons/More.svg).
   1. En el menú contextual, seleccione **[!UICONTROL Mostrar como tabla]**.

   La vista principal se actualiza para mostrar una visualización de líneas y una tabla.

   ![Visualización de tendencias diarias finales del caso de uso 2 del escritorio de Power BI](assets/uc5-pbi-final.png){zoomable="yes"}

>[!TAB Escritorio Tableau]

1. Seleccione la ficha **[!UICONTROL Hoja 1]** en la parte inferior para cambiar de **[!UICONTROL Fuente de datos]**. En la vista **[!UICONTROL Hoja 1]**:
   1. Arrastre la entrada **[!UICONTROL Daterange]** de la lista **[!UICONTROL Tablas]** en el panel **[!UICONTROL Datos]** y suéltela en el estante **[!UICONTROL Filtros]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtros de campo \[Intervalo de fechas\]]**, seleccione **[!UICONTROL Intervalo de fechas]** y seleccione **[!UICONTROL Siguiente >]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtrar \[Daterange]]**, seleccione **[!UICONTROL Intervalo de fechas]** y especifique un período de `01/01/2023` - `31/12/2024`. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.

      ![Filtro Tableau para escritorio](assets/uc5-tableau-filter.png){zoomable="yes"}

   1. Arrastre y suelte **[!UICONTROL Product Name]** de la lista **[!UICONTROL Tablas]** en el panel **[!UICONTROL Datos]** y suelte la entrada en el campo junto a **[!UICONTROL Filas]**.
   1. Arrastre y suelte **[!UICONTROL Purchases]** de la lista **[!UICONTROL Tables (*Measure Names*)]** en el panel **[!UICONTROL Datos]** y suelte la entrada en el campo junto a **[!UICONTROL Rows]**.
      * Los valores se convierten automáticamente a **[!UICONTROL SUM(Purchases)]**.
   1. Arrastre y suelte **[!UICONTROL Ingresos de compra]** de la lista **[!UICONTROL Tablas (*Nombres de medida*)]** en el panel **[!UICONTROL Datos]** y suelte la entrada en el campo junto a **[!UICONTROL Columnas]** y a la izquierda de **[!UICONTROL SUM(Compras)]**.
      * Los valores se convierten automáticamente a **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Para ordenar ambos gráficos en orden descendente de ingresos de compra, pase el ratón sobre el título **[!UICONTROL Ingresos de compra]** y seleccione el icono de ordenación.
   1. Para limitar el número de entradas en los gráficos, seleccione **[!UICONTROL SUM(Purchase Revenue)]** en **[!UICONTROL Filas]** y en el menú desplegable seleccione **[!UICONTROL Filtro]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtrar \[Ingresos de compra\]]**, seleccione **[!UICONTROL Rango de valores]** e introduzca los valores apropiados. Por ejemplo: `1,000,000` - `2,000,000`. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.
   1. Para convertir los dos gráficos de barras en un gráfico combinado dual, seleccione **[!UICONTROL SUM(Purchases)]** en **[!UICONTROL Rows]** y en el menú desplegable, seleccione **[!UICONTROL Dual Axis]**. Los gráficos de barras se transforman en un diagrama de puntos.
   1. Para modificar el diagrama de puntos en un gráfico de barras:
      1. Seleccione **[!UICONTROL SUM(Purchases)]** en el área de **[!UICONTROL Marks]** y seleccione **[!UICONTROL Line]** del menú desplegable.
      1. Seleccione **[!UICONTROL SUM(Purchase Revenue)]** en el área de **[!UICONTROL Marcas]** y seleccione **[!UICONTROL Barra]** en el menú desplegable.

   El escritorio Tableau debe tener el aspecto siguiente.

   ![Tableau Desktop Graph](assets/uc5-tableau-graph.png){zoomable="yes"}

1. Seleccione **[!UICONTROL Duplicate]** del menú contextual de la ficha **[!UICONTROL Hoja 1]** para crear una segunda hoja.
1. Seleccione **[!UICONTROL Rename]** del menú contextual de la ficha **[!UICONTROL Hoja 1]** para cambiar el nombre de la hoja a `Data`.
1. Seleccione **[!UICONTROL Rename]** del menú contextual de la ficha **[!UICONTROL Hoja 1 (2)]** para cambiar el nombre de la hoja a `Graph`.
1. Asegúrese de que la hoja **[!UICONTROL Data]** esté seleccionada.
   1. Seleccione **[!UICONTROL Mostrarme]** en la parte superior derecha y seleccione **[!UICONTROL Tabla de texto]** (visualización superior izquierda superior) para modificar el contenido de los dos gráficos a una tabla.
   1. Para ordenar los ingresos de compra en orden descendente, pase el ratón sobre **[!UICONTROL Ingresos de compra]** en la tabla y seleccione ![SortOrderDown](/help/assets/icons/SortOrderDown.svg).
   1. Seleccione **[!UICONTROL Vista completa]** del menú desplegable **[!UICONTROL Ajustar]**.

   El escritorio Tableau debe tener el aspecto siguiente.

   ![Datos de escritorio Tableau](assets/uc5-tableau-data.png){zoomable="yes"}

1. Seleccione el botón de pestaña **[!UICONTROL Nuevo panel]** (en la parte inferior) para crear una nueva vista de **[!UICONTROL panel 1]**. En la vista **[!UICONTROL Panel 1]**:
   1. Arrastre y suelte la hoja **[!UICONTROL Graph]** del estante **[!UICONTROL Sheets]** en la vista **[!UICONTROL Dashboard 1]** que dice *Colocar hojas aquí*.
   1. Arrastre y suelte la hoja **[!UICONTROL Data]** del estante **[!UICONTROL Sheets]** debajo de la hoja **[!UICONTROL Graph]** en la vista **[!UICONTROL Dashboard 1]**.
   1. Seleccione la hoja **[!UICONTROL Data]** en la vista y modifique **[!UICONTROL Toda la vista]** a **[!UICONTROL Anchura de la corrección]**.

   La vista del **[!UICONTROL panel 1]** debería ser similar a la siguiente.

   ![Tablero de escritorio Tableau 1](assets/uc5-tableau-dashboard.png){zoomable="yes"}

>[!ENDTABS]

+++


## Clasificación de varias dimensiones

En este caso de uso, desea mostrar una tabla que desglose los ingresos de compra y las compras para nombres de productos dentro de las categorías de productos en 2023. Además, desea utilizar algunas visualizaciones para ilustrar la distribución de categorías de productos y las contribuciones de nombres de productos dentro de cada categoría de producto.

+++ Customer Journey Analytics

Un ejemplo del panel **[!UICONTROL Múltiples Dimension clasificados]** para el caso de uso:

![Panel de varios Dimension de Customer Journey Analytics](assets/cja-multiple-dimension-ranked.png){zoomable="yes"}

+++

+++ Herramientas de BI

>[!PREREQUISITES]
>
>Asegúrese de que ha validado [una conexión correcta, que puede enumerar vistas de datos y que utiliza una vista de datos](#connect-and-validate) para la herramienta de BI para la que desea probar este caso de uso.
>

>[!BEGINTABS]

>[!TAB Escritorio de Power BI]

1. Para asegurarse de que el intervalo de fechas se aplique a todas las visualizaciones, arrastre y suelte **[!UICONTROL daterangeday]** desde el panel **[!UICONTROL Datos]** a **[!UICONTROL Filtros en esta página]**.
   1. Seleccione **[!UICONTROL daterangeday es (todo)]** de **[!UICONTROL Filtros de esta página]**.
   1. Seleccione **[!UICONTROL Fecha relativa]** como **[!UICONTROL Tipo de filtro]**.
   1. Defina el filtro para **[!UICONTROL Mostrar elementos cuando el valor]** **[!UICONTROL esté en los últimos]** `1` **[!UICONTROL años del calendario]**.
   1. Seleccione **[!UICONTROL Aplicar filtro]**.

1. En el panel **[!UICONTROL Datos]**:
   1. Seleccione **[!UICONTROL datarangeday]**.
   1. Seleccione **[!UICONTROL product_category]**.
   1. Seleccione **[!UICONTROL product_name]**.
   1. Seleccionar **[!UICONTROL ∑ purchase_revenue]**
   1. Seleccionar **[!UICONTROL ∑ compras]**

1. Para modificar el gráfico de barras verticales en una tabla, asegúrese de que ha seleccionado la tabla y seleccione **[!UICONTROL Matriz]** en el panel **[!UICONTROL Visualizaciones]**.
   * Arrastre **[!UICONTROL product_name]** de **[!UICONTROL Columns]** y suelte el campo debajo de **[!UICONTROL product_category]**y en **[!UICONTROL Rows]** en el panel **[!UICONTROL Visualización]**.

1. Para limitar el número de productos mostrados en la tabla, seleccione **[!UICONTROL product_name is (All)]** en el panel **[!UICONTROL Filtros]**.

   1. Seleccione **[!UICONTROL Filtro avanzado]**.
   1. Seleccionar **[!UICONTROL Tipo de filtro]** **[!UICONTROL N superior]** **[!UICONTROL Mostrar elementos]** **[!UICONTROL Superior]** `15` **[!UICONTROL Por valor]**.
   1. Arrastre **[!UICONTROL compras]** desde el panel **[!UICONTROL Datos]** al **[!UICONTROL Agregar campos de datos aquí]**.
   1. Seleccione **[!UICONTROL Aplicar filtro]**.

1. Para mejorar la legibilidad, seleccione **[!UICONTROL Ver]** en el menú superior, seleccione **[!UICONTROL Vista de página]** > **[!UICONTROL Tamaño real]** y cambie el tamaño de la visualización de la tabla.

1. Para desglosar cada categoría en la tabla, seleccione **[!UICONTROL +]** en el nivel de categoría de producto. El escritorio de Power BI debe tener el aspecto siguiente.

   ![Tabla de matrices clasificadas de varios Dimension de escritorio de Power BI](assets/uc6-powerbi-data.png){zoomable="yes"}

1. Seleccione **[!UICONTROL Página principal]** en el menú superior y seleccione **[!UICONTROL Nuevo elemento visual]**. Se agrega una nueva imagen al informe.

1. En el panel **[!UICONTROL Datos]**:
   1. Seleccione **[!UICONTROL product_category]**.
   1. Seleccione **[!UICONTROL product_name]**.
   1. Seleccione **[!UICONTROL purchase_revenue]**.

1. Para modificar la imagen, seleccione el gráfico de barras y seleccione **[!UICONTROL Gráfico de rectángulos]** en el panel **[!UICONTROL Visualizaciones]**.
1. Asegúrese de que **[!UICONTROL product_category]** aparece debajo de **[!UICONTROL Category]** y que **[!UICONTROL product_name]** aparece debajo de **[!UICONTROL Detalles]** en el panel **[!UICONTROL Visualizaciones]**.

   El escritorio de Power BI debe tener el aspecto siguiente.

   ![Diagrama de clasificación de varios Dimension de escritorio de Power BI](assets/uc6-powerbi-treemap.png){zoomable="yes"}

1. Seleccione **[!UICONTROL Página principal]** en el menú superior y seleccione **[!UICONTROL Nuevo elemento visual]**. Se agrega una nueva imagen al informe.

1. En el panel **[!UICONTROL Datos]**:
   1. Seleccione **[!UICONTROL product_category]**.
   1. Seleccione **[!UICONTROL purchase_revenue]**.
   1. Seleccione **[!UICONTROL compra]**.

1. En el panel **[!UICONTROL Visualizaciones]**:
   1. Para modificar la visualización, seleccione **[!UICONTROL Gráfico de líneas y columnas apiladas]**.
   1. Arrastre **[!UICONTROL sum_of_purchases]** desde **[!UICONTROL eje Y de columna]** hasta **[!UICONTROL eje Y de línea]**.

1. En el informe, reorganice las visualizaciones individuales.

   El escritorio de Power BI debe tener el aspecto siguiente.

   ![Varios Dimension de escritorio de Power BI clasificados como finales](assets/uc6-powerbi-final.png){zoomable="yes"}


>[!TAB Escritorio Tableau]

1. Seleccione la ficha **[!UICONTROL Hoja 1]** en la parte inferior para cambiar de **[!UICONTROL Fuente de datos]**. En la vista **[!UICONTROL Hoja 1]**:
   1. Arrastre la entrada **[!UICONTROL Daterange]** de la lista **[!UICONTROL Tablas]** en el panel **[!UICONTROL Datos]** y suéltela en el estante **[!UICONTROL Filtros]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtros de campo \[Intervalo de fechas\]]**, seleccione **[!UICONTROL Intervalo de fechas]** y seleccione **[!UICONTROL Siguiente >]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtrar \[Daterange]]**, seleccione **[!UICONTROL Fechas relativas]**, seleccione **[!UICONTROL Años]** y especifique **[!UICONTROL Año anterior]**. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.

      El escritorio Tableau debe tener el aspecto siguiente.

      ![Filtro de varios Dimension de escritorio Tableau](assets/uc6-tableau-filter.png){zoomable="yes"}

   1. Arrastre **[!UICONTROL Product Category]** y suéltelo junto a **[!UICONTROL Columns]**.
   1. Arrastre **[!UICONTROL Ingresos de compra]** y suéltelo junto a **[!UICONTROL Filas]**. El valor cambia a **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Arrastre Purchases y suéltelas junto a **[!UICONTROL Rows]**. El valor cambia a **[!UICONTROL SUM(Purchases)]**.
   1. Seleccione **[!UICONTROL SUM(Purchases)]** y en el menú desplegable seleccione **[!UICONTROL Dual Axis]**.
   1. Seleccione **[!UICONTROL SUM(Purchases)]** en **[!UICONTROL Marcas]** y seleccione **[!UICONTROL Línea]** en el menú desplegable.
   1. Seleccione **[!UICONTROL SUM(Purchase Revenue)]** en **[!UICONTROL Marcas]** y seleccione **[!UICONTROL Barra]** en el menú desplegable.
   1. Seleccione **[!UICONTROL Vista completa]** del menú **[!UICONTROL Ajustar]**.
   1. Seleccione el título **[!UICONTROL Ingresos de compra]** en el gráfico y asegúrese de que los ingresos de compra estén en orden ascendente.

      El escritorio Tableau debe tener el aspecto siguiente.

      ![Categoría Clasificada De Varios Dimension De Tableau Desktop](assets/uc6-tableau-category.png){zoomable="yes"}

1. Cambie el nombre de la hoja **[!UICONTROL Hoja 1]** actual a `Category`.
1. Seleccione **[!UICONTROL Nueva hoja de cálculo]** para crear una hoja nueva y renómbrala a `Data`.

   1. Arrastre la entrada **[!UICONTROL Daterange]** de la lista **[!UICONTROL Tablas]** en el panel **[!UICONTROL Datos]** y suéltela en el estante **[!UICONTROL Filtros]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtros de campo \[Intervalo de fechas\]]**, seleccione **[!UICONTROL Intervalo de fechas]** y seleccione **[!UICONTROL Siguiente >]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtrar \[Daterange]]**, seleccione **[!UICONTROL Fechas relativas]**, seleccione **[!UICONTROL Años]** y especifique **[!UICONTROL Año anterior]**. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.
   1. Arrastre **[!UICONTROL Ingresos de compra]** desde el panel **[!UICONTROL Datos]** hasta **[!UICONTROL Columnas]**. El valor cambia a **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Arrastre **[!UICONTROL Compra]** desde el panel **[!UICONTROL Datos]** hasta **[!UICONTROL Columnas]**, junto a **[!UICONTROL Ingresos de compra]**. El valor cambia a **[!UICONTROL SUM(Purchases)]**.
   1. Arrastre **[!UICONTROL Categoría de producto]** del panel **[!UICONTROL Datos]** a **[!UICONTROL Filas]**.
   1. Arrastre **[!UICONTROL Nombre de producto]** del panel **[!UICONTROL Datos]** a **[!UICONTROL Filas]**, junto a **[!UICONTROL Categoría de producto]**.
   1. Para cambiar las dos barras horizontales a una tabla, seleccione **[!UICONTROL Tabla de texto]** de **[!UICONTROL Mostrarme]**.
   1. Para limitar el número de productos, seleccione **[!UICONTROL Compras]** en **[!UICONTROL Valores de medida]**. En el menú desplegable, seleccione **[!UICONTROL Filtro]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtrar \[Compras\]]**, seleccione **[!UICONTROL Al menos]** e introduzca `7000`. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.
   1. Seleccione **[!UICONTROL Ajustar ancho]** en **[!UICONTROL el menú desplegable]** Ajustar ancho.

      El escritorio Tableau debe tener el aspecto siguiente.

      ![Datos de clasificación de varios Dimension en Tableau Desktop](assets/uc6-tableau-data.png){zoomable="yes"}

1. Seleccione **[!UICONTROL Nueva hoja de cálculo]** para crear una nueva hoja y cambiarle el nombre a **[!UICONTROL Diagrama de árbol]**.
   1. Arrastre la entrada **[!UICONTROL Daterange]** de la lista **[!UICONTROL Tablas]** en el panel **[!UICONTROL Datos]** y suéltela en el estante **[!UICONTROL Filtros]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtros de campo \[Intervalo de fechas\]]**, seleccione **[!UICONTROL Intervalo de fechas]** y seleccione **[!UICONTROL Siguiente >]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtrar \[Daterange]]**, seleccione **[!UICONTROL Fechas relativas]**, seleccione **[!UICONTROL Años]** y especifique **[!UICONTROL Año anterior]**. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.
   1. Arrastre **[!UICONTROL Ingresos de compra]** del panel **[!UICONTROL Datos]** a **[!UICONTROL Filas]**. Los valores cambian a **[!UICONTROL SUM(Ingresos de compra)]**.
   1. Arrastre **[!UICONTROL Compra]** desde el panel **[!UICONTROL Datos]** a **[!UICONTROL Filas]**, junto a **[!UICONTROL Ingresos de compra]**. El valor cambia a **[!UICONTROL SUM(Purchases)]**.
   1. Arrastre **[!UICONTROL Categoría de producto]** del panel **[!UICONTROL Datos]** a **[!UICONTROL Columnas]**.
   1. Arrastre **[!UICONTROL Product Name]** del panel **[!UICONTROL Datos]** a **[!UICONTROL Columnas]**.
   1. Para cambiar los dos gráficos de barras verticales por un diagrama, seleccione **[!UICONTROL Diagrama de árbol]** de **[!UICONTROL Mostrarme]**.
   1. Para limitar el número de productos, seleccione **[!UICONTROL Compras]** en **[!UICONTROL Valores de medida]**. En el menú desplegable, seleccione **[!UICONTROL Filtro]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtrar \[Compras\]]**, seleccione **[!UICONTROL Al menos]** e introduzca `7000`. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.
   1. Seleccione **[!UICONTROL Ajustar ancho]** del menú desplegable **[!UICONTROL Ajustar]**.

      El escritorio Tableau debe tener el aspecto siguiente.

      ![Datos de clasificación de varios Dimension en Tableau Desktop](assets/uc6-tableau-treemap.png){zoomable="yes"}

1. Seleccione el botón de pestaña **[!UICONTROL Nuevo panel]** (en la parte inferior) para crear una nueva vista de **[!UICONTROL panel 1]**. En la vista **[!UICONTROL Panel 1]**:
   1. Arrastre y suelte la hoja **[!UICONTROL Category]** del estante **[!UICONTROL Sheets]** en la vista **[!UICONTROL Dashboard 1]** que dice *Drop sheets here*.
   1. Arrastre y suelte la hoja **[!UICONTROL Treemap]** del estante **[!UICONTROL Sheets]** debajo de la hoja **[!UICONTROL Category]** en la vista **[!UICONTROL Dashboard 1]**.
   1. Arrastre y suelte la hoja **[!UICONTROL Data]** del estante **[!UICONTROL Sheets]** debajo de la hoja **[!UICONTROL Treemap]** en la vista **[!UICONTROL Dashboard 1]**.
   1. Cambie el tamaño de cada una de las hojas de la vista.

   La vista del **[!UICONTROL panel 1]** debería ser similar a la siguiente.

   ![Tablero de escritorio Tableau 1](assets/uc6-tableau-final.png){zoomable="yes"}

>[!ENDTABS]

+++


## Contar valores de dimensión distintos

Desea obtener el número distinto de nombres de productos sobre los que se ha informado durante enero de 2023.

+++ Customer Journey Analytics

Para informar sobre un recuento distinto de nombres de productos, configuró una métrica calculada en Customer Journey Analytics, con **[!UICONTROL Title]** `Product Name (Count Distinct)` y **[!UICONTROL External Id]** `product_name_count_distinct`.

![Métrica calculada Nombre de producto de Customer Journey Analytics (recuento de distintivos)](assets/cja-calc-metric-distinct-count-product-names.png){zoomable="yes"}

A continuación, puede usar esa métrica en un ejemplo del panel **[!UICONTROL Contar valores de Dimension distintos]** para el caso de uso:

![Valores de Recuento Distintos Customer Journey Analytics](assets/cja-count-distinct-dimension-values.png){zoomable="yes"}

+++

+++ Herramientas de BI

>[!PREREQUISITES]
>
>Asegúrese de que ha validado [una conexión correcta, que puede enumerar vistas de datos y que utiliza una vista de datos](#connect-and-validate) para la herramienta de BI para la que desea probar este caso de uso.
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
   1. Seleccione **[!UICONTROL ∑ cm_product_name_count_distinct]**, que es la métrica calculada definida en el Customer Journey Analytics.

1. Para modificar el gráfico de barras verticales en una tabla, asegúrese de que ha seleccionado el gráfico y seleccione **[!UICONTROL Tabla]** en el panel **[!UICONTROL Visualizaciones]**.

   El escritorio de Power BI debe tener el aspecto siguiente.

   ![Tabla de recuento múltiple de escritorio de Power BI](assets/uc7-powerbi-table.png){zoomable="yes"}

1. Seleccione la visualización de tabla. En el menú contextual, seleccione **[!UICONTROL Copiar]** > **[!UICONTROL Copiar elemento visual]**.
1. Pegue la visualización mediante **[!UICONTROL ctrl-v]**. La copia exacta de la visualización se superpone con la original. Muévalo a la derecha en el área del informe.
1. Para modificar la visualización copiada de una tabla a una tarjeta, seleccione **[!UICONTROL Tarjeta]** de **[!UICONTROL Visualizaciones]**.

   El escritorio de Power BI debe tener el aspecto siguiente.

   ![Tabla de recuento múltiple de escritorio de Power BI](assets/uc7-powerbi-final.png){zoomable="yes"}

Como alternativa, puede utilizar la funcionalidad de recuento distinto de Power BI.

1. Seleccione la dimensión **[!UICONTROL product_name]**.
1. Aplique la función **[!UICONTROL Count (Distinct)]** en la dimensión **[!UICONTROL product_name]** en **[!UICONTROL Columns]**.

   ![Número de Power BI distinto](assets/uc7-powerbi-alternative.png){zoomable="yes"}



>[!TAB Escritorio Tableau]

1. Seleccione la ficha **[!UICONTROL Hoja 1]** en la parte inferior para cambiar de **[!UICONTROL Fuente de datos]**. En la vista **[!UICONTROL Hoja 1]**:
   1. Arrastre la entrada **[!UICONTROL Daterange]** de la lista **[!UICONTROL Tablas]** en el panel **[!UICONTROL Datos]** y suéltela en el estante **[!UICONTROL Filtros]**.
   1. En el cuadro de diálogo **[!UICONTROL Campo de filtro \[Intervalo de fechas\]]**, seleccione **[!UICONTROL Intervalo de fechas]** y seleccione **[!UICONTROL Siguiente >]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtrar \[Daterange]]**, seleccione **[!UICONTROL Intervalo de fechas]** y seleccione `01/01/2023` - `31/1/2023`. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.
   1. Arrastre **[!UICONTROL Cm Product Name Count Distinct]** A **[!UICONTROL Filas]**. El valor cambia a **[!UICONTROL SUM(Cm Product Name Count Distinct)]**. Este campo es la métrica calculada que ha definido en Customer Journey Analytics.
   1. Arrastre **[!UICONTROL Daterangeday]** y suéltelo junto a **[!UICONTROL Columns]**. Seleccione **[!UICONTROL Daterangeday]** y en el menú desplegable seleccione **[!UICONTROL Día]**.
   1. Para modificar la visualización de líneas en una tabla, seleccione **[!UICONTROL Tabla de texto]** de **[!UICONTROL Mostrar]**.
   1. Seleccione **[!UICONTROL Intercambiar filas y columnas]** en la barra de herramientas.
   1. Seleccione **[!UICONTROL Ajustar ancho]** del menú desplegable **[!UICONTROL Ajustar]**.

      El escritorio Tableau debe tener el aspecto siguiente.

      ![Filtro de varios Dimension de escritorio Tableau](assets/uc7-tableau-data.png){zoomable="yes"}

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

   ![Filtro de varios Dimension de escritorio Tableau](assets/uc7-tableau-card.png){zoomable="yes"}

1. Seleccione el botón de pestaña **[!UICONTROL Nuevo panel]** (en la parte inferior) para crear una nueva vista de **[!UICONTROL panel 1]**. En la vista **[!UICONTROL Panel 1]**:
   1. Arrastre y suelte la hoja **[!UICONTROL Tarjeta]** del estante **[!UICONTROL Hojas]** en la vista **[!UICONTROL Panel 1]** que dice *Colocar hojas aquí*.
   1. Arrastre y suelte la hoja **[!UICONTROL Data]** del estante **[!UICONTROL Sheets]** debajo de la hoja **[!UICONTROL Card]** en la vista **[!UICONTROL Dashboard 1]**.

   La vista del **[!UICONTROL panel 1]** debería ser similar a la siguiente.

   ![Tablero de escritorio Tableau 1](assets/uc7-tableau-final.png){zoomable="yes"}


También puede utilizar la funcionalidad de recuento distinto de Tableau Desktop.

1. Use **[!UICONTROL Nombre De Producto]** en lugar de **[!UICONTROL Nombre De Producto Cm Recuento Distinto]**.
1. Aplicar **[!UICONTROL Medida]** > **[!UICONTROL Recuento (distinto)]** en **[!UICONTROL Nombre de producto]** en **[!UICONTROL Marcas]**.

   ![Número de Power BI distinto](assets/uc7-tableau-alternative.png){zoomable="yes"}

>[!ENDTABS]

+++



## Usar nombres de intervalo de fechas para filtrar

Desea utilizar un intervalo de fechas que haya definido en Customer Journey Analytics para filtrar e informar sobre ocurrencias (eventos) durante el último año.

+++ Customer Journey Analytics

Para informar usando un intervalo de fechas, configuró un intervalo de fechas en Customer Journey Analytics, con **[!UICONTROL Título]** `Last Year 2023`.

![Customer Journey Analytics: use nombres de intervalo de fechas para filtrar](assets/cja-daterange.png){zoomable="yes"}

A continuación, puede usar ese intervalo de fechas en un ejemplo **[!UICONTROL Uso del panel Nombres de intervalo de fechas para filtrar]** para el caso de uso:

![Valores de Recuento Distintos Customer Journey Analytics](assets/cja-using-date-range-filter-names-to-filter.png){zoomable="yes"}

Observe cómo el intervalo de fechas definido en la visualización de tabla de forma libre anula el intervalo de fechas aplicado al panel.

+++

+++ Herramientas de BI

>[!PREREQUISITES]
>
>Asegúrese de que ha validado [una conexión correcta, que puede enumerar vistas de datos y que utiliza una vista de datos](#connect-and-validate) para la herramienta de BI para la que desea probar este caso de uso.
>

>[!BEGINTABS]

>[!TAB Escritorio de Power BI]

1. En el panel **[!UICONTROL Datos]**:
   1. Seleccione **[!UICONTROL daterangemonth]**.
   1. Seleccione **[!UICONTROL daterangeName]**.
   1. Seleccionar **[!UICONTROL ∑ repeticiones]**.

   Verá una visualización que muestra **[!UICONTROL Error al obtener los datos de este elemento visual]**.

1. En el panel **[!UICONTROL Filtros]**:

   1. Seleccione **[!UICONTROL daterangeName is (All)]** de **[!UICONTROL Filtros en este elemento visual]**.
   1. Seleccione **[!UICONTROL Filtro básico]** como **[!UICONTROL Tipo de filtro]**.
   1. Debajo del campo **[!UICONTROL Buscar]**, seleccione **[!UICONTROL Último año 2023]**, que es el nombre del intervalo de fechas definido en el Customer Journey Analytics.
   1. Seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para quitar **[!UICONTROL daterangeName]** de **[!UICONTROL Columnas]**.

   Verá la tabla actualizada con el filtro **[!UICONTROL daterangeName]** aplicado. El escritorio de Power BI debe tener el aspecto siguiente.

   ![Escritorio De Power BI Que Usa Nombres De Intervalo De Fechas Para Filtrar](assets/uc8-powerbi-final.png){zoomable="yes"}

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

      ![Filtro de varios Dimension de escritorio Tableau](assets/uc8-tableau-final.png){zoomable="yes"}

>[!ENDTABS]

+++



## Usar nombres de filtro para filtrar

Desea utilizar un filtro existente para la categoría de productos de pesca, que ha definido en Customer Journey Analytics, para filtrar e informar sobre los nombres de productos y las ocurrencias (eventos) durante enero de 2023.

+++ Customer Journey Analytics

Inspect utiliza el filtro que desea utilizar en Customer Journey Analytics.

![El Customer Journey Analytics Usa Nombres De Filtro Para Filtrar](assets/cja-fishing-products.png){zoomable="yes"}

A continuación, puede usar ese filtro en un ejemplo **[!UICONTROL Uso de nombres de intervalo de fechas para filtrar]** panel para el caso de uso:

![Valores de Recuento Distintos Customer Journey Analytics](assets/cja-using-filter-names-to-filter.png){zoomable="yes"}

+++

+++ Herramientas de BI

>[!PREREQUISITES]
>
>Asegúrese de que ha validado [una conexión correcta, que puede enumerar vistas de datos y que utiliza una vista de datos](#connect-and-validate) para la herramienta de BI para la que desea probar este caso de uso.
>

>[!BEGINTABS]

>[!TAB Escritorio de Power BI]

1. En el panel **[!UICONTROL Datos]**:
   1. Seleccione **[!UICONTROL daterange]**.
   1. Seleccione **[!UICONTROL filterName]**.
   1. Seleccione **[!UICONTROL product_name]**.
   1. Seleccionar **[!UICONTROL ∑ repeticiones]**.

Verá una visualización que muestra **[!UICONTROL Error al obtener los datos de este elemento visual]**.

1. En el panel **[!UICONTROL Filtros]**:

   1. Seleccione **[!UICONTROL filterName is (All)]** de **[!UICONTROL Filtros en este elemento visual]**.
   1. Seleccione **[!UICONTROL Filtro básico]** como **[!UICONTROL Tipo de filtro]**.
   1. Debajo del campo **[!UICONTROL Buscar]**, seleccione **[!UICONTROL Productos de pesca]**, que es el nombre del filtro existente definido en el Customer Journey Analytics.
   1. Seleccione **[!UICONTROL intervalo de fechas es (todo)]** de **[!UICONTROL Filtros en este elemento visual]**.
   1. Seleccione **[!UICONTROL Filtro avanzado]** como **[!UICONTROL Tipo de filtro]**.
   1. Defina el filtro para **[!UICONTROL Mostrar elementos cuando el valor]** **[!UICONTROL esté en]** `1/1/2023` **[!UICONTROL y]** **[!UICONTROL esté antes de]** `2/1/2023` o después.
   1. Seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para quitar **[!UICONTROL filterName]** de **[!UICONTROL Columnas]**.
   1. Seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para quitar **[!UICONTROL daterange]** de **[!UICONTROL Columnas]**.

   Verá la tabla actualizada con el filtro **[!UICONTROL filterName]** aplicado. El escritorio de Power BI debe tener el aspecto siguiente.

   ![Escritorio De Power BI Que Usa Nombres De Intervalo De Fechas Para Filtrar](assets/uc9-powerbi-final.png){zoomable="yes"}


>[!TAB Escritorio Tableau]

1. Seleccione la ficha **[!UICONTROL Hoja 1]** en la parte inferior para cambiar de **[!UICONTROL Fuente de datos]**. En la vista **[!UICONTROL Hoja 1]**:
   1. Arrastre la entrada **[!UICONTROL Filter Name]** de la lista **[!UICONTROL Tables]** en el estante **[!UICONTROL Filters]**.
   1. En el diálogo **[!UICONTROL Filtrar \[Nombre del filtro\]]**, asegúrese de que **[!UICONTROL Seleccionar de la lista]** está seleccionado y seleccione **[!UICONTROL Productos de pesca]** de la lista. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.
   1. Arrastre la entrada **[!UICONTROL Daterange]** de la lista **[!UICONTROL Tablas]** en el estante **[!UICONTROL Filtros]**.
   1. En el cuadro de diálogo **[!UICONTROL Campo de filtro \[Intervalo de fechas\]]**, seleccione **[!UICONTROL Intervalo de fechas]** y seleccione **[!UICONTROL Siguiente >]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtrar \[Daterange]]**, seleccione **[!UICONTROL Intervalo de fechas]** y seleccione `01/01/2023` - `01/02/2023`. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.
   1. Arrastre **[!UICONTROL Product Name]** de la lista **[!UICONTROL Tablas]** a **[!UICONTROL Filas]**.
   1. Arrastre la entrada **[!UICONTROL Ocurrencias]** de la lista **[!UICONTROL Tablas]** y suelte la entrada en el campo junto a **[!UICONTROL Columnas]**. El valor cambia a **[!UICONTROL SUM(Occurrences)]**.
   1. Seleccione **[!UICONTROL Tabla de texto]** de **[!UICONTROL Mostrarme]**.
   1. Seleccione **[!UICONTROL Ajustar ancho]** del menú desplegable **[!UICONTROL Ajustar]**.

      El escritorio Tableau debe tener el aspecto siguiente.

      ![Filtro de varios Dimension de escritorio Tableau](assets/uc9-tableau-final.png){zoomable="yes"}

>[!ENDTABS]

+++


## Uso de valores de dimensión para filtrar

Se crea un nuevo filtro en Customer Journey Analytics que filtra los productos de la categoría de productos de caza. A continuación, desea utilizar el nuevo filtro para informar sobre nombres de productos y ocurrencias (eventos) para productos de la categoría de caza durante enero de 2023.

+++ Customer Journey Analytics

Cree un nuevo Customer Journey Analytics con **[!UICONTROL Title]** `Hunting Products` en.

![El Customer Journey Analytics Usa Valores De Dimension Para Filtrar](assets/cja-hunting-products.png){zoomable="yes"}

A continuación, puede usar ese filtro en un ejemplo **[!UICONTROL Uso de valores de Dimension para filtrar]** panel para el caso de uso:

![Valores de Recuento Distintos Customer Journey Analytics](assets/cja-using-dimension-values-to-filter.png){zoomable="yes"}

+++

+++ Herramientas de BI

>[!PREREQUISITES]
>
>Asegúrese de que ha validado [una conexión correcta, que puede enumerar vistas de datos y que utiliza una vista de datos](#connect-and-validate) para la herramienta de BI para la que desea probar este caso de uso.
>

>[!BEGINTABS]

>[!TAB Escritorio de Power BI]

1. Seleccione **[!UICONTROL Inicio]** en el menú y, a continuación, seleccione **[!UICONTROL Actualizar]** en la barra de herramientas. Debe actualizar la conexión para recoger el nuevo filtro que acaba de definir en Customer Journey Analytics.

1. En el panel **[!UICONTROL Datos]**:
   1. Seleccione **[!UICONTROL daterange]**.
   1. Seleccione **[!UICONTROL filterName]**.
   1. Seleccione **[!UICONTROL product_name]**.
   1. Seleccionar **[!UICONTROL ∑ repeticiones]**.

Verá una visualización que muestra **[!UICONTROL Error al obtener los datos de este elemento visual]**.

1. En el panel **[!UICONTROL Filtros]**:
   1. Seleccione **[!UICONTROL filterName is (All)]** de **[!UICONTROL Filtros en este elemento visual]**.
   1. Seleccione **[!UICONTROL Filtro básico]** como **[!UICONTROL Tipo de filtro]**.
   1. Debajo del campo **[!UICONTROL Buscar]**, seleccione **[!UICONTROL Productos de caza]**, que es el nombre del filtro existente definido en el Customer Journey Analytics.
   1. Seleccione **[!UICONTROL intervalo de fechas es (todo)]** de **[!UICONTROL Filtros en este elemento visual]**.
   1. Seleccione **[!UICONTROL Filtro avanzado]** como **[!UICONTROL Tipo de filtro]**.
   1. Defina el filtro para **[!UICONTROL Mostrar elementos cuando el valor]** **[!UICONTROL esté en]** `1/1/2023` **[!UICONTROL y]** **[!UICONTROL esté antes de]** `2/1/2023` o después.
   1. Seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para quitar **[!UICONTROL filterName]** de **[!UICONTROL Columnas]**.
   1. Seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para quitar **[!UICONTROL daterange]** de **[!UICONTROL Columnas]**.

   Verá la tabla actualizada con el filtro **[!UICONTROL filterName]** aplicado. El escritorio de Power BI debe tener el aspecto siguiente.

   ![Escritorio De Power BI Que Usa Nombres De Intervalo De Fechas Para Filtrar](assets/uc10-powerbi-final.png){zoomable="yes"}



>[!TAB Escritorio Tableau]

1. En la vista **[!UICONTROL Data Source]**, debajo de **[!UICONTROL Data]**, en el menú contextual de **[!UICONTROL cc_data_view(prod:cja%3FFLATTEN)]**, seleccione **[!UICONTROL Actualizar]**. Debe actualizar la conexión para recoger el nuevo filtro que acaba de definir en Customer Journey Analytics.
1. Seleccione la ficha **[!UICONTROL Hoja 1]** en la parte inferior para cambiar de **[!UICONTROL Fuente de datos]**. En la vista **[!UICONTROL Hoja 1]**:
   1. Arrastre la entrada **[!UICONTROL Filter Name]** de la lista **[!UICONTROL Tables]** en el estante **[!UICONTROL Filters]**.
   1. En el diálogo **[!UICONTROL Filtrar \[Nombre del filtro\]]**, asegúrese de que **[!UICONTROL Seleccionar de la lista]** está seleccionado y seleccione **[!UICONTROL Productos de caza]** de la lista. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.
   1. Arrastre la entrada **[!UICONTROL Daterange]** de la lista **[!UICONTROL Tablas]** en el estante **[!UICONTROL Filtros]**.
   1. En el cuadro de diálogo **[!UICONTROL Campo de filtro \[Intervalo de fechas\]]**, seleccione **[!UICONTROL Intervalo de fechas]** y seleccione **[!UICONTROL Siguiente >]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtrar \[Daterange]]**, seleccione **[!UICONTROL Intervalo de fechas]** y seleccione `01/01/2023` - `1/2/2023`. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.
   1. Arrastre **[!UICONTROL Product Name]** de la lista **[!UICONTROL Tablas]** a **[!UICONTROL Filas]**.
   1. Arrastre la entrada **[!UICONTROL Ocurrencias]** de la lista **[!UICONTROL Tablas]** y suelte la entrada en el campo junto a **[!UICONTROL Columnas]**. El valor cambia a **[!UICONTROL SUM(Occurrences)]**.
   1. Seleccione **[!UICONTROL Tabla de texto]** de **[!UICONTROL Mostrarme]**.
   1. Seleccione **[!UICONTROL Ajustar ancho]** del menú desplegable **[!UICONTROL Ajustar]**.

      El escritorio Tableau debe tener el aspecto siguiente.

      ![Filtro de varios Dimension de escritorio Tableau](assets/uc10-tableau-final.png){zoomable="yes"}

>[!ENDTABS]

+++



## Ordenar

Desea informar sobre los ingresos de compra y las compras de nombres de productos durante enero de 2023, ordenados en orden descendente de ingresos de compra.

+++ Customer Journey Analytics

Un ejemplo del panel **[!UICONTROL Ordenar]** para el caso de uso:

![Panel de orden de Customer Journey Analytics](assets/cja-sort.png){zoomable="yes"}

+++

+++ Herramientas de BI

>[!PREREQUISITES]
>
>Asegúrese de que ha validado [una conexión correcta, que puede enumerar vistas de datos y que utiliza una vista de datos](#connect-and-validate) para la herramienta de BI para la que desea probar este caso de uso.
>

>[!BEGINTABS]

>[!TAB Escritorio de Power BI]

1. En el panel **[!UICONTROL Datos]**:
   1. Seleccione **[!UICONTROL daterange]**.
   1. Seleccione **[!UICONTROL product_name]**.
   1. Seleccione **[!UICONTROL ∑ purchase_revenue]**.
   1. Seleccione **[!UICONTROL ∑ compras]**.

1. En el panel **[!UICONTROL Filtros]**:
   1. Seleccione **[!UICONTROL intervalo de fechas es (todo)]** de **[!UICONTROL Filtros en este elemento visual]**.
   1. Seleccione **[!UICONTROL Filtro avanzado]** como **[!UICONTROL Tipo de filtro]**.
   1. Defina el filtro para **[!UICONTROL Mostrar elementos cuando el valor]** **[!UICONTROL esté en]** `1/1/2023` **[!UICONTROL y]** **[!UICONTROL esté antes de]** `2/1/2023` o después.

1. En el panel Visualizaciones:
   1. Seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para quitar el intervalo de fechas de las columnas.
   1. Arrastre **[!UICONTROL Suma de purchase_revenue]** al final de **[!UICONTROL los elementos de la columna]**.

1. En el informe, seleccione **[!UICONTROL Sum of purchase_revenue]** para clasificar la tabla en orden descendente según los ingresos de compra.

   El escritorio de Power BI debe tener el aspecto siguiente.

   ![Escritorio De Power BI Que Usa Nombres De Intervalo De Fechas Para Filtrar](assets/uc11-powerbi-final.png){zoomable="yes"}

La consulta ejecutada por el escritorio de Power BI mediante la extensión BI no incluye una instrucción `sort`. La falta de una instrucción `sort` implica que la ordenación se ejecuta en el lado del cliente.

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
   1. En el cuadro de diálogo **[!UICONTROL Filtrar \[Daterange]]**, seleccione **[!UICONTROL Intervalo de fechas]** y seleccione `01/01/2023` - `1/2/2023`. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.
   1. Arrastre **[!UICONTROL Product Name]** de la lista **[!UICONTROL Tablas]** y suelte la entrada en el campo situado junto a **[!UICONTROL Filas]**.
   1. Arrastre la entrada **[!UICONTROL Purchases]** de la lista **[!UICONTROL Tables]** y suelte la entrada en el campo situado junto a **[!UICONTROL Columns]**. El valor cambia a **[!UICONTROL SUM(Purchases)]**.
   1. Arrastre la entrada **[!UICONTROL Ingresos de compras]** de la lista **[!UICONTROL Tablas]** y suelte la entrada en el campo junto a **[!UICONTROL Columnas]**, junto a **[!UICONTROL SUMA(Compras)]**. El valor cambia a **[!UICONTROL SUM(Purchase Revenue)]**.
   1. Seleccione **[!UICONTROL Tabla de texto]** de **[!UICONTROL Mostrarme]**.
   1. Seleccione **[!UICONTROL Ajustar ancho]** del menú desplegable **[!UICONTROL Ajustar]**.
   1. Seleccione el encabezado de columna **[!UICONTROL Ingresos de compra]** y ordene la tabla en esta columna en orden descendente.

      El escritorio Tableau debe tener el aspecto siguiente.

      ![Orden de escritorio Tableau](assets/uc11-tableau-final.png){zoomable="yes"}

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

>[!ENDTABS]

+++

## Límites

Desea informar sobre las 5 ocurrencias principales de nombres de productos durante 2023.

+++ Customer Journey Analytics

Un ejemplo del panel **[!UICONTROL Límite]** para el caso de uso:

![Panel de límite de Customer Journey Analytics](assets/cja-limit.png){zoomable="yes"}

+++

+++ Herramientas de BI

>[!PREREQUISITES]
>
>Asegúrese de que ha validado [una conexión correcta, que puede enumerar vistas de datos y que utiliza una vista de datos](#connect-and-validate) para la herramienta de BI para la que desea probar este caso de uso.
>

>[!BEGINTABS]

>[!TAB Escritorio de Power BI]

1. En el panel **[!UICONTROL Datos]**:
   1. Seleccione **[!UICONTROL daterange]**.
   1. Seleccione **[!UICONTROL product_name]**.
   1. Seleccionar **[!UICONTROL ∑ repeticiones]**.

1. En el panel **[!UICONTROL Filtros]**:
   1. Seleccione **[!UICONTROL intervalo de fechas es (todo)]** de **[!UICONTROL Filtros en este elemento visual]**.
   1. Seleccione **[!UICONTROL Fecha relativa]** como **[!UICONTROL Tipo de filtro]**.
   1. Defina el filtro para **[!UICONTROL Mostrar elementos cuando el valor]** **[!UICONTROL esté en los últimos]** `1` **[!UICONTROL años del calendario]**.
   1. Seleccione **[!UICONTROL Aplicar filtro]**.
   1. Seleccione **[!UICONTROL product_name is (All)]** de **[!UICONTROL Filtros en este elemento visual]**.
   1. Seleccione **[!UICONTROL N]** principales como **[!UICONTROL tipo de filtro]**.
   1. Seleccionar **[!UICONTROL Mostrar elementos]** **[!UICONTROL Principales]** `5` **[!UICONTROL Por valor]**.
   1. Arrastre y suelte **[!UICONTROL ∑ ocurrencias]** del panel **[!UICONTROL Datos]** y suéltelo en **[!UICONTROL Agregar campos de datos aquí]**.
   1. Seleccione **[!UICONTROL Aplicar filtro]**.

1. En el panel Visualización:
   * Seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para quitar el intervalo de fechas de las columnas.

   El escritorio de Power BI debe tener el aspecto siguiente.

   ![Escritorio De Power BI Que Usa Nombres De Intervalo De Fechas Para Filtrar](assets/uc12-powerbi-final.png){zoomable="yes"}

La consulta ejecutada por el escritorio de Power BI mediante la extensión de BI incluye una instrucción `limit`, pero no la esperada. Power BI Desktop aplica el límite de las 5 ocurrencias principales utilizando resultados de nombres de productos explícitos.

```sql
select "_"."product_name",
    "_"."a0"
from 
(
    select "rows"."product_name" as "product_name",
        sum("rows"."occurrences") as "a0"
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
        where (("_"."product_name" in ('Saltwater Monofilament Line', 'Pop-Up Beach Tent', 'Instant Pop-Up Tent', 'Envelop Sleeping Bag', 'Waterproof Tackle Bag')) and "_"."daterange" < date '2024-01-01') and "_"."daterange" >= date '2023-01-01'
    ) "rows"
    group by "product_name"
) "_"
where not "_"."a0" is null
limit 1000001
```

>[!TAB Escritorio Tableau]

1. Seleccione la ficha **[!UICONTROL Hoja 1]** en la parte inferior para cambiar de **[!UICONTROL Fuente de datos]**. En la vista **[!UICONTROL Hoja 1]**:
   1. Arrastre la entrada **[!UICONTROL Daterange]** de la lista **[!UICONTROL Tablas]** en el estante **[!UICONTROL Filtros]**.
   1. En el cuadro de diálogo **[!UICONTROL Campo de filtro \[Intervalo de fechas\]]**, seleccione **[!UICONTROL Intervalo de fechas]** y seleccione **[!UICONTROL Siguiente >]**.
   1. En el cuadro de diálogo **[!UICONTROL Filtrar \[Daterange]]**, seleccione **[!UICONTROL Fechas relativas]**, **[!UICONTROL Años]** y **[!UICONTROL Años anteriores]**. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.
   1. Arrastre **[!UICONTROL Product Name]** de la lista **[!UICONTROL Tablas]** a **[!UICONTROL Filas]**.
   1. Arrastre la entrada **[!UICONTROL Ocurrencias]** de la lista **[!UICONTROL Tablas]** y suelte la entrada en el campo junto a **[!UICONTROL Columnas]**. El valor cambia a **[!UICONTROL SUM(Occurrences)]**.
   1. Seleccione **[!UICONTROL Tabla de texto]** de **[!UICONTROL Mostrarme]**.
   1. Seleccione **[!UICONTROL Ajustar ancho]** del menú desplegable **[!UICONTROL Ajustar]**.
   1. Seleccione **[!UICONTROL Nombre de producto]** en **[!UICONTROL Filas]**. Seleccione **[!UICONTROL Filtro]** en el menú desplegable.
      1. En el cuadro de diálogo **[!UICONTROL Filtrar \[Nombre de producto\]]**, seleccione la pestaña **[!UICONTROL Superior]**.
      1. Seleccione **[!UICONTROL Por campo:]** **[!UICONTROL Principales]** `5` **[!UICONTROL por ocurrencias]** **[!UICONTROL Suma]**.
      1. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.

         ![AlertRed](/help/assets/icons/AlertRed.svg) Verá que la tabla desaparece. Seleccionar los 5 nombres de productos principales por ocurrencias **no** funciona correctamente usando este filtro.
      1. Seleccione **[!UICONTROL Product Name]** en el estante **[!UICONTROL Filter]** y en el menú desplegable seleccione **[!UICONTROL Remove]**. La tabla vuelve a aparecer.
   1. Seleccione **[!UICONTROL SUM(Occurrences)]** en el estante de **[!UICONTROL Marcas]**. Seleccione **[!UICONTROL Filtro]** en el menú desplegable.
      1. En el diálogo **[!UICONTROL Filtrar \[Ocurrencias\]]**, seleccione **[!UICONTROL Al menos]**.
      1. Escriba `47.799` como valor. Este valor garantiza que solo se muestren los 5 elementos principales en la tabla. Seleccione **[!UICONTROL Aplicar]** y **[!UICONTROL Aceptar]**.

         El escritorio Tableau debe tener el aspecto siguiente.

         ![Límites de Tableau Desktop](assets/uc12-tableau-final.png){zoomable="yes"}

Como se muestra más arriba, esta consulta ejecutada por Tableau Desktop, al definir un filtro de las 5 ocurrencias principales en los nombres de productos, falla.

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok"
FROM "public"."cc_data_view" "cc_data_view"
  INNER JOIN (
  SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
    SUM("cc_data_view"."occurrences") AS "$__alias__0"
  FROM "public"."cc_data_view" "cc_data_view"
  GROUP BY 1
  ORDER BY 2 DESC,
    1 ASC
  LIMIT 5
) "t0" ON (CAST("cc_data_view"."product_name" AS TEXT) = "t0"."product_name")
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1
```

A continuación, se muestra la consulta ejecutada por Tableau Desktop al definir un filtro de los 5 principales casos. El límite no es visible en la consulta y en el lado del cliente aplicado.

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1
```

>[!ENDTABS]

+++

## Transformaciones

Desea comprender las transformaciones de los objetos de Customer Journey Analytics, como dimensiones, métricas, filtros, métricas calculadas e intervalos de fechas, realizadas por las distintas herramientas de BI.

+++ Customer Journey Analytics

En Customer Journey Analytics, usted define en una [vista de datos](/help/data-views/data-views.md), qué componentes de sus conjuntos de datos y cómo se exponen como [dimensiones](/help/components/dimensions/overview.md) y [métricas](/help/components/apply-create-metrics.md). Esa definición de dimensión y métricas se expone a las herramientas de BI que utilizan la extensión de BI.
Utiliza componentes como [Filtros](/help/components/filters/filters-overview.md), [Métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md) e [intervalos de fechas](/help/components/date-ranges/overview.md) como parte de sus proyectos de Workspace. Estos componentes también se exponen a las herramientas de BI que utilizan la extensión de BI.

+++

+++ Herramientas de BI

>[!PREREQUISITES]
>
>Asegúrese de que ha validado [una conexión correcta, que puede enumerar vistas de datos y que utiliza una vista de datos](#connect-and-validate) para la herramienta de BI para la que desea probar este caso de uso.
>

>[!BEGINTABS]

>[!TAB Escritorio de Power BI]

Los objetos de Customer Journey Analytics están disponibles en el panel **[!UICONTROL Datos]** y se recuperan de la tabla seleccionada en Power BI Desktop. Por ejemplo, **[!UICONTROL public.cc_data_view]**. El nombre de la tabla es el mismo que el ID externo definido para la vista de datos en Customer Journey Analytics. Por ejemplo, la vista de datos con **[!UICONTROL Título]** `C&C - Data View` y **[!UICONTROL Id. externo]** `cc_data_view`.

**Dimension**
Los Dimension del Customer Journey Analytics se identifican mediante el [!UICONTROL ID de componente]. El [!UICONTROL ID de componente] está definido en la vista de datos del Customer Journey Analytics. Por ejemplo, la dimensión **[!UICONTROL Product Name]** del Customer Journey Analytics tiene un [!UICONTROL ID de componente] **[!UICONTROL product_name]**, que es el nombre de la dimensión en Power BI Desktop.
Las dimensiones de intervalo de fechas de Customer Journey Analytics, como **[!UICONTROL Day]**, **[!UICONTROL Week]**, **[!UICONTROL Month]** y más están disponibles como **[!UICONTROL daterangeday]**, **[!UICONTROL daterangeweek]**, **[!UICONTROL daterangemonth]** y más.

**Métricas**
Las métricas del Customer Journey Analytics se identifican con el [!UICONTROL ID de componente]. El [!UICONTROL ID de componente] está definido en la vista de datos del Customer Journey Analytics. Por ejemplo, la métrica **[!UICONTROL Ingresos de compra]** del Customer Journey Analytics tiene un [!UICONTROL ID de componente] **[!UICONTROL purchase_revenue]**, que es el nombre de la métrica en Power BI Desktop. Un **[!UICONTROL ∑]** indica las métricas. Cuando se usa una métrica en cualquier visualización, se cambia el nombre de la métrica a **[!UICONTROL Suma de *métrica *]**.

**Filtros**
Los filtros que defina en Customer Journey Analytics están disponibles como parte del campo **[!UICONTROL filterName]**. Cuando usa un campo **[!UICONTROL filterName]** en Power BI Desktop, puede especificar qué filtro utilizar.

**Métricas calculadas**
Las métricas calculadas que define en Customer Journey Analytics se identifican con el [!UICONTROL ID externo] que ha definido para la métrica calculada. Por ejemplo, la métrica calculada **[!UICONTROL Product Name (Count Distinct)]** tiene [!UICONTROL ID externo] **[!UICONTROL product_name_count_distinct]** y se muestra como **[!UICONTROL cm_product_name_count_distinct]**t en el escritorio de Power BI.

**Intervalos de fechas**
Los intervalos de fechas que defina en Customer Journey Analytics están disponibles como parte del campo **[!UICONTROL intervaloDeFechas]**. Cuando usa un campo **[!UICONTROL daterangeName]**, puede especificar qué intervalo de fecha usar.

**Transformaciones personalizadas**
Power BI Desktop proporciona funcionalidad de transformación personalizada mediante [expresiones de análisis de datos (DAX)](https://learn.microsoft.com/en-us/dax/dax-overview). Por ejemplo, desea ejecutar el caso de uso de clasificación de dimensión única con nombres de producto en minúsculas.

1. En la vista Informe, seleccione la visualización de barras.
1. Seleccione product_name en el panel Datos.
1. Seleccione Nueva columna en la barra de herramientas.
1. En el editor de fórmulas, defina una nueva columna denominada `product_name_lower`, como `product_name_lower = LOWER('public.cc_data_view[product_name])`.
   ![Transformación de escritorio de Power BI a inferior](assets/uc14-powerbi-transformation.png){zoomable="yes"}
1. Asegúrese de seleccionar la nueva columna product_name_lower en el panel de datos en lugar de la columna product_name.
1. Seleccione Informe como tabla de ![Más](/help/assets/icons/More.svg) en la visualización de tabla.

   El escritorio de Power BI debe tener el aspecto siguiente.
   ![Final de transformación de escritorio de Power BI](assets/uc14-powerbi-final.png){zoomable="yes"}

El resultado de la transformación personalizada es una actualización de las consultas SQL. Consulte el uso de la función `lower` en el siguiente ejemplo de SQL:

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

Los objetos Customer Journey Analytics están disponibles en la barra lateral **[!UICONTROL Data]** siempre que trabaje en una hoja. Y se recuperan de la tabla que ha seleccionado como parte de la página **[!UICONTROL Fuente de datos]** en Tableau. Por ejemplo, **[!UICONTROL cc_data_view]**. El nombre de la tabla es el mismo que el ID externo definido para la vista de datos en Customer Journey Analytics. Por ejemplo, la vista de datos con **[!UICONTROL Título]** `C&C - Data View` y **[!UICONTROL Id. externo]** `cc_data_view`.

**Dimension**
Los Dimension del Customer Journey Analytics se identifican con el [!UICONTROL nombre del componente]. El [!UICONTROL nombre del componente] está definido en la vista de datos del Customer Journey Analytics. Por ejemplo, la dimensión **[!UICONTROL Nombre de producto]** del Customer Journey Analytics tiene un [!UICONTROL Nombre de componente] **[!UICONTROL Nombre de producto]**, que es el nombre de la dimensión en Tableau. **[!UICONTROL Abc]** identifica todas las dimensiones.
Las dimensiones de intervalo de fechas de Customer Journey Analytics, como **[!UICONTROL Day]**, **[!UICONTROL Week]**, **[!UICONTROL Month]** y más están disponibles como **[!UICONTROL Daterangeday]**, **[!UICONTROL Daterangeweek]**, **[!UICONTROL Daterangemonth]** y más. Cuando se utiliza una dimensión de intervalo de fechas, se debe seleccionar una definición adecuada de fecha u hora para aplicarla a esa dimensión de intervalo de fechas en el menú desplegable. Por ejemplo, **[!UICONTROL Year]**, **[!UICONTROL Quarter]**, **[!UICONTROL Month]**, **[!UICONTROL Day]**.

**Métricas**
Las métricas del Customer Journey Analytics se identifican con el [!UICONTROL Nombre del componente]. El [!UICONTROL Nombre de componente] está definido en la vista de datos del Customer Journey Analytics. Por ejemplo, la métrica **[!UICONTROL Ingresos de compra]** del Customer Journey Analytics tiene un [!UICONTROL Nombre de componente] **[!UICONTROL Ingresos de compra]**, que es el nombre de la métrica en Tableau. **[!UICONTROL #]** identifica todas las métricas. Cuando usa una métrica en cualquier visualización, se cambia el nombre de la métrica a **[!UICONTROL Sum(*metric*)]**.

**Filtros**
Los filtros que defina en Customer Journey Analytics están disponibles como parte del campo **[!UICONTROL Nombre del filtro]**. Cuando usa un campo **[!UICONTROL Nombre del filtro]** en Tableau, puede especificar qué filtro utilizar.

**Métricas calculadas**
Las métricas calculadas que defina en Customer Journey Analytics se identificarán con el [!UICONTROL Título] que haya definido para la métrica calculada. Por ejemplo, la métrica calculada **[!UICONTROL Product Name (Count Distinct)]** tiene [!UICONTROL Title] **[!UICONTROL Product Name (Count Distinct)]** y se muestra como **[!UICONTROL Cm Product Name Count Distinct]** en Tableau.

**Intervalos de fechas**
Los intervalos de fechas que defina en Customer Journey Analytics están disponibles como parte del campo **[!UICONTROL Nombre del intervalo de fechas]**. Cuando usa un campo **[!UICONTROL Nombre del intervalo de fechas]**, puede especificar qué intervalo de fechas utilizar.

**Transformaciones personalizadas**
Tableau Desktop proporciona funcionalidad de transformación personalizada mediante [Campos calculados](https://help.tableau.com/current/pro/desktop/en-us/calculations_calculatedfields_create.htm). Por ejemplo, desea ejecutar el caso de uso de clasificación de dimensión única con nombres de producto en minúsculas.

1. Seleccione **[!UICONTROL Análisis]** > **[!UICONTROL Crear campo calculado]** en el menú principal.
   1. Defina **[!UICONTROL Nombre de producto en minúsculas]** con la función `LOWER([Product Name])`.
      ![Campo calculado Tableau](assets/uc14-tableau-calculated-field.png){zoomable="yes"}
   1. Seleccione **[!UICONTROL Aceptar]**.
1. Seleccione la hoja **[!UICONTROL Data]**.
   1. Arrastre **[!UICONTROL Nombre de producto en minúsculas]** de **[!UICONTROL Tablas]** y suelte la entrada en el campo junto a **[!UICONTROL Filas]**.
   1. Quitar **[!UICONTROL Nombre de producto]** de **[!UICONTROL Filas]**.
1. Seleccione la vista **[!UICONTROL Panel 1]**.

El escritorio Tableau debe tener el aspecto siguiente.

![Tableau Desktop después de la transformación](assets/uc14-tableau-final.png){zoomable="yes"}

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

>[!ENDTABS]

+++



## Visualizaciones

En este caso de uso, quiero comprender cómo se pueden crear de manera similar las visualizaciones, disponibles en Customer Journey Analytics, mediante las visualizaciones disponibles en las herramientas de BI.

+++ Customer Journey Analytics

El Customer Journey Analytics tiene varias visualizaciones. Consulte [Visualizaciones](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) para obtener una introducción y una descripción general de todas las visualizaciones posibles.

+++

+++ Herramientas de BI

>[!BEGINTABS]

>[!TAB Escritorio de Power BI]

### Comparación

Para la mayoría de las visualizaciones de Customer Journey Analytics, Power BI Desktop ofrece experiencias equivalentes. Consulte la tabla siguiente.

| Icono | Visualización del Customer Journey Analytics | Visualización de escritorio de Power BI |
| :---: | --- | ---| 
| ![GraphArea](/help/assets/icons/GraphArea.svg) | [Área](/help/analysis-workspace/visualizations/area.md) | [Gráfico de área, gráfico de área apilada y gráfico de área 100%](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#area-charts-basic-layered-and-stacked) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [Barra](/help/analysis-workspace/visualizations/bar.md) | [Gráfico de columnas agrupadas](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [Barra apilada](/help/analysis-workspace/visualizations/bar.md) | [Gráfico de columnas apiladas y gráfico de columnas apiladas al 100%](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![GraphBullet](/help/assets/icons/GraphBullet.svg)</p> | [Bullet](/help/analysis-workspace/visualizations/bullet-graph.md) |  |
| ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [Tabla de cohorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |  |
| ![Combo](/help/assets/icons/ComboChart.svg) | [Combo](/help/analysis-workspace/visualizations/combo-charts.md) | [Gráfico de líneas y columnas apiladas y Gráfico de líneas y columnas agrupadas](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#combo-charts) |
| ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [Anillo](/help/analysis-workspace/visualizations/donut.md) | [Gráfico de anillo](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#doughnut-charts) |
| ![Canal de conversión](/help/assets/icons/ConversionFunnel.svg) | [Visita en orden previsto](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | [Canal](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#funnel-charts). |
| ![Rutas de gráficos](/help/assets/icons/GraphPathing.svg) | [Flujo](/help/analysis-workspace/visualizations/c-flow/flow.md) | ¿Árbol de descomposición? |
| ![VerTabla](/help/assets/icons/ViewTable.svg)</p> | [Tabla de forma libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | [Tabla](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#tables) y [Matriz](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#matrix) |
| ![GraphHistogram](/help/assets/icons/Histogram.svg) | [Histograma](/help/analysis-workspace/visualizations/histogram.md) |  |
| ![GraphBarHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [Barra horizontal](/help/analysis-workspace/visualizations/horizontal-bar.md) | [Gráfico de barras agrupadas](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![GraphBarHorizontalStacked](/help/assets/icons/GraphBarHorizontalStacked.svg) | [Barra horizontal apilada](/help/analysis-workspace/visualizations/horizontal-bar.md) | [Gráfico de barras apiladas y gráfico de barras apiladas al 100%](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![Rama3](/help/assets/icons/Branch3.svg) | [lienzo de Recorrido](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) | [Árbol de descomposición](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#decomposition-tree) |
| ![Métricas clave](/help/assets/icons/KeyMetrics.svg) | [Resumen de métricas clave](/help/analysis-workspace/visualizations/key-metric.md) |  |
| ![TendenciaGráfico](/help/assets/icons/GraphTrend.svg) | [Líneas](/help/analysis-workspace/visualizations/line.md) | [Gráfico de líneas](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#line-charts) |
| ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [Dispersión](/help/analysis-workspace/visualizations/scatterplot.md) | [Gráfico de dispersión](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#scatter) |
| ![ReglaDePágina](/help/assets/icons/PageRule.svg) | [Encabezado de sección](/help/analysis-workspace/visualizations/section-header.md) | [Cuadro de texto](https://learn.microsoft.com/en-us/power-bi/paginated-reports/report-design/textbox/add-move-or-delete-a-text-box-report-builder-and-service) |
| ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [Cambio de resumen](/help/analysis-workspace/visualizations/summary-number-change.md) | [Tarjeta](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#cards) |
| ![123](/help/assets/icons/123.svg)</p> | [Número de resumen](/help/analysis-workspace/visualizations/summary-number-change.md) | [Tarjeta](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#cards) |
| ![Texto](/help/assets/icons/Text.svg) | [Texto](/help/analysis-workspace/visualizations/text.md) | [Cuadro de texto](https://learn.microsoft.com/en-us/power-bi/paginated-reports/report-design/textbox/add-move-or-delete-a-text-box-report-builder-and-service) |
| ![VistaDeCuadrículaModerna](/help/assets/icons/ModernGridView.svg) | [Gráfico de rectángulos](/help/analysis-workspace/visualizations/treemap.md)<p> | [Gráfico de rectángulos](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#treemaps) |
| ![Tipo](/help/assets/icons/TwoDots.svg) | [Venn](/help/analysis-workspace/visualizations/venn.md) | |


### Explorar en profundidad

Power BI admite [modo de obtención de detalles](https://learn.microsoft.com/en-us/power-bi/consumer/end-user-drill) para explorar detalles en profundidad sobre determinadas visualizaciones. En el siguiente ejemplo, se analizan los ingresos por compras para categorías de productos. En el menú contextual de una barra que representa una categoría de producto, puede seleccionar **[!UICONTROL Profundizar]**.

![explorar en profundidad de Power BI](assets/uc15-powerbi-drilldown.png){zoomable="yes"}

Profundizar actualizará la visualización con los ingresos de compra de los productos dentro de la categoría de producto seleccionada.

![aumentar detalle de Power BI](assets/uc15-powerbi-drillup.png){zoomable="yes"}

El desglose genera la siguiente consulta SQL que utiliza una cláusula `WHERE`:

```sql
select "_"."product_category" as "c25",
    "_"."product_name" as "c26",
    "_"."a0" as "a0"
from 
(
    select "_"."product_category",
        "_"."product_name",
        "_"."a0"
    from 
    (
        select "_"."product_category",
            "_"."product_name",
            "_"."a0"
        from 
        (
            select "rows"."product_category" as "product_category",
                "rows"."product_name" as "product_name",
                sum("rows"."purchase_revenue") as "a0"
            from 
            (
                select "_"."product_category",
                    "_"."product_name",
                    "_"."purchase_revenue"
                from "public"."cc_data_view" "_"
                where ("_"."daterange" >= date '2023-01-01' and "_"."product_category" = 'Fishing') and "_"."daterange" < date '2024-01-01'
            ) "rows"
            group by "product_category",
                "product_name"
        ) "_"
        where not "_"."a0" is null
    ) "_"
) "_"
order by "_"."product_category",
        "_"."product_name"
limit 1001
```

>[!TAB Escritorio Tableau]

### Comparación

Para la mayoría de las visualizaciones Customer Journey Analytics, Tableau ofrece experiencias equivalentes. Consulte la tabla siguiente.

| Icono | Visualización del Customer Journey Analytics | Visualización de escritorio de Power BI |
| :---: | --- | ---| 
| ![GraphArea](/help/assets/icons/GraphArea.svg) | [Área](/help/analysis-workspace/visualizations/area.md) | [Gráfico de áreas](https://help.tableau.com/current/pro/desktop/en-us/qs_area_charts.htm) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [Barra](/help/analysis-workspace/visualizations/bar.md) | [Gráfico de barras](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [Barra apilada](/help/analysis-workspace/visualizations/bar.md) |  |
| ![GraphBullet](/help/assets/icons/GraphBullet.svg)</p> | [Bullet](/help/analysis-workspace/visualizations/bullet-graph.md) | [Gráfico de viñetas](https://help.tableau.com/current/pro/desktop/en-us/qs_bullet_graphs.htm) |
| ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [Tabla de cohorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |  |
| ![Combo](/help/assets/icons/ComboChart.svg) | [Combo](/help/analysis-workspace/visualizations/combo-charts.md) | [Gráficos combinados](https://help.tableau.com/current/pro/desktop/en-us/qs_combo_charts.htm) |
| ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [Anillo](/help/analysis-workspace/visualizations/donut.md) | |
| ![Canal de conversión](/help/assets/icons/ConversionFunnel.svg) | [Visita en orden previsto](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | |
| ![Rutas de gráficos](/help/assets/icons/GraphPathing.svg) | [Flujo](/help/analysis-workspace/visualizations/c-flow/flow.md) |  |
| ![VerTabla](/help/assets/icons/ViewTable.svg)</p> | [Tabla de forma libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | [Tabla de texto](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_text.htm) |
| ![GraphHistogram](/help/assets/icons/Histogram.svg) | [Histograma](/help/analysis-workspace/visualizations/histogram.md) | [Histograma](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_histogram.htm) |
| ![GraphBarHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [Barra horizontal](/help/analysis-workspace/visualizations/horizontal-bar.md) | [Gráfico de barras](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![GraphBarHorizontalStacked](/help/assets/icons/GraphBarHorizontalStacked.svg) | [Barra horizontal apilada](/help/analysis-workspace/visualizations/horizontal-bar.md) | [Gráfico de barras](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![Rama3](/help/assets/icons/Branch3.svg) | [lienzo de Recorrido](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) | |
| ![Métricas clave](/help/assets/icons/KeyMetrics.svg) | [Resumen de métricas clave](/help/analysis-workspace/visualizations/key-metric.md) |  |
| ![TendenciaGráfico](/help/assets/icons/GraphTrend.svg) | [Líneas](/help/analysis-workspace/visualizations/line.md) | [Gráfico de líneas](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_line.htm) |
| ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [Dispersión](/help/analysis-workspace/visualizations/scatterplot.md) | [Diagrama de puntos](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_scatter.htm) |
| ![ReglaDePágina](/help/assets/icons/PageRule.svg) | [Encabezado de sección](/help/analysis-workspace/visualizations/section-header.md) |  |
| ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [Cambio de resumen](/help/analysis-workspace/visualizations/summary-number-change.md) | |
| ![123](/help/assets/icons/123.svg)</p> | [Número de resumen](/help/analysis-workspace/visualizations/summary-number-change.md) | |
| ![Texto](/help/assets/icons/Text.svg) | [Texto](/help/analysis-workspace/visualizations/text.md) | |
| ![VistaDeCuadrículaModerna](/help/assets/icons/ModernGridView.svg) | [Gráfico de rectángulos](/help/analysis-workspace/visualizations/treemap.md)<p> | [Gráfico de rectángulos](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_treemap.htm) |
| ![Tipo](/help/assets/icons/TwoDots.svg) | [Venn](/help/analysis-workspace/visualizations/venn.md) | |


### Explorar en profundidad

Tableau admite [modo de obtención de detalles](https://learn.microsoft.com/en-us/power-bi/consumer/end-user-drill) a través de [jerarquías](https://help.tableau.com/current/pro/desktop/en-us/qs_hierarchies.htm). En el ejemplo siguiente, se crea una jerarquía al seleccionar el campo Nombre del producto en las tablas y arrastrarlo sobre Categoría del producto. A continuación, en el menú contextual de una barra que representa una categoría de producto, puede seleccionar **[!UICONTROL + Explorar en profundidad]**.

![Exploración en profundidad de Tableau](assets/uc15-tableau-drilldown.png){zoomable="yes"}

Profundizar actualizará la visualización con los ingresos de compra de los productos dentro de la categoría de producto seleccionada.

![Exploración en profundidad de Tableau](assets/uc15-tableau-drillup.png){zoomable="yes"}

El desglose genera la siguiente consulta SQL que utiliza una cláusula GROUP BY:

```sql
SELECT CAST("cc_data_view"."product_category" AS TEXT) AS "product_category",
  CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1,
  2
```

La consulta **no** limita los resultados a la categoría de producto seleccionada; solo la visualización muestra la categoría de producto seleccionada.

![Exploración en profundidad de Tableau](assets/uc15-tableau-drillup2.png){zoomable="yes"}

También puede crear un tablero de aumento de detalle en el que un elemento visual sea el resultado de la selección en otro elemento visual. En el ejemplo siguiente, la visualización **[!UICONTROL Categorías de productos]** se usa como filtro para actualizar la tabla **[!UICONTROL Nombres de productos]**. Este filtro de visualización es solo de cliente y no genera una consulta SQL adicional.

![Filtro de visualización Tableau](assets/uc15-tableau-visualizationfilter.png){zoomable="yes"}


>[!ENDTABS]

+++


## Advertencias

Cada una de las herramientas de BI admitidas tiene algunas advertencias para trabajar con la extensión de BI de Customer Journey Analytics.

+++ Herramientas de BI

>[!BEGINTABS]

>[!TAB Escritorio de Power BI]

* El filtrado avanzado de intervalos de fechas de Power BI Desktop es exclusivo.  Para la fecha de finalización, debe seleccionar una fecha posterior al día en el que desee generar el informe. Por ejemplo **[!UICONTROL es el]** `1/1/2023` **[!UICONTROL y antes]** `1/2/2023` o después.
* El valor predeterminado de Power BI Desktop es **[!UICONTROL Importar]** al crear una conexión. Asegúrese de usar **[!UICONTROL Direct Query]**.
* Power BI Desktop expone las transformaciones de datos a través de Power Query.  Power Query funciona principalmente con conexiones de tipo Import, por lo que muchas transformaciones que se aplican, como funciones de fecha o cadena, generarán un error que indica que debe cambiar a una conexión de tipo Import.  Si necesita transformar los datos en el momento de la consulta, debe utilizar dimensiones y métricas derivadas para que Power BI no necesite realizar las transformaciones en sí.
* Power BI Desktop no entiende cómo gestionar columnas de tipo fecha-hora, por lo que las dimensiones **[!UICONTROL daterange *X *]**como**[!UICONTROL daterangehour ]**y**[!UICONTROL daterangeminute ]**no son compatibles.
* De forma predeterminada, Power BI Desktop intenta realizar varias conexiones con un máximo de sesiones de Query Service.  Debe entrar en la configuración de Power BI del proyecto y desactivar las consultas paralelas.
* Power BI Desktop realiza todas las operaciones de ordenación y limitación en el lado del cliente, y también tiene una semántica diferente para el filtrado superior *X* que incluye valores vinculados, de modo que no puede crear exactamente la misma ordenación y limitación que en Analysis Workspace.
* Las versiones anteriores del lanzamiento de octubre de 2024 de Power BI Desktop rompen las fuentes de datos de PostgreSQL. Asegúrese de utilizar la versión mencionada en este artículo.

>[!TAB Escritorio Tableau]

* El filtrado Tableau Desktop Range of Dates es exclusivo. Para la fecha de finalización, debe seleccionar una fecha posterior al día en el que desee generar el informe.
* De manera predeterminada, cuando se agrega una dimensión de fecha y hora como **[!UICONTROL Daterangemonth]** a las filas de una hoja, Tableau Desktop ajustará el campo en una función **[!UICONTROL YEAR()]**.  Para obtener lo que desea, debe seleccionar esa dimensión y en el menú desplegable, seleccionar la función de fecha que desee utilizar.  Por ejemplo, cambie **[!UICONTROL Year]** a **[!UICONTROL Month]** cuando intente usar **[!UICONTROL Daterangemonth]**.
* Limitar los resultados a los *X* principales no es obvio en Tableau Desktop. Puede limitar los resultados explícitamente o mediante un campo calculado y la función **[!UICONTROL INDEX()]**.  Agregar un filtro *X* superior a una dimensión genera SQL complejo mediante una combinación interna no compatible.

>[!ENDTABS]

+++
