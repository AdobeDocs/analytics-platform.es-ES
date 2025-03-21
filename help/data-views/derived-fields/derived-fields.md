---
title: Campos derivados
description: Un campo derivado especifica la manipulación en tiempo de informe de los campos de esquema o los componentes estándar a través de un conjunto de funciones disponibles y plantillas de funciones.
solution: Customer Journey Analytics
feature: Derived Fields
exl-id: bcd172b2-cd13-421a-92c6-e8c53fa95936
role: Admin
source-git-commit: 261d4b5e18531f7971a894bc4cd571b764c625f1
workflow-type: tm+mt
source-wordcount: '8844'
ht-degree: 17%

---

# Campos derivados {#derived-fields}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_derivedfields"
>title="Campos derivados"
>abstract="Un campo derivado permite definir manipulaciones de datos sobre la marcha, mediante un generador de reglas personalizable. A continuación, puede usar ese campo derivado como componente (métrica o dimensión) en Workspace o incluso definirlo como componente en la vista Datos."

<!-- markdownlint-enable MD034 -->


Los campos derivados son un aspecto importante de la funcionalidad de creación de informes en tiempo real de Adobe Customer Journey Analytics. Un campo derivado permite definir manipulaciones de datos (a menudo complejas) sobre la marcha, mediante un generador de reglas personalizable. A continuación, puede usar ese campo derivado como componente (métrica o dimensión) en [Workspace](../../analysis-workspace/home.md) o incluso definir más el campo derivado como componente en [Vista de datos](../data-views.md).

Los campos derivados pueden ahorrar una cantidad significativa de tiempo y esfuerzo, en comparación con la transformación o manipulación de los datos en otras ubicaciones fuera de Customer Journey Analytics. Por ejemplo, [preparación de datos](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=es), [Distiller de datos](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html) o dentro de sus propios procesos de carga de transformación de extracción (ETL)/transformación de carga de extracción (ELT).

Los campos derivados se definen en [vistas de datos](../data-views.md), se basan en un conjunto de funciones definidas como reglas y se aplican a los campos de esquema o estándar disponibles.

Algunos casos de uso son:

- Defina un campo Nombre de página derivado que corrija los valores incorrectos de nombre de página recopilados para corregir los valores de nombre de página.

- Defina un campo de canal de marketing derivado que determine el canal de marketing adecuado en función de una o varias condiciones (por ejemplo, parámetro de URL, dirección URL de página, nombre de página).

## Interfaz de campo derivada {#interface}

Cuando se crea o edita un campo derivado, se utiliza la interfaz de campo derivado.

![Captura de pantalla del cuadro de diálogo Campo derivado](assets/derived-field-dialog.png)



|  | Nombre | Descripción |
|---------|----------|--------|
| 1 | **Selector** | Utilice el área de selector para seleccionar y arrastrar la función, la plantilla de función, el campo de esquema o el campo estándar y colocarlos en el generador de reglas. <br/>Utilice la lista desplegable para seleccionar entre: <br/>![Función](assets/Smock_Function_18_N.svg) [!UICONTROL Funciones] - enumera [funciones](#function-reference), </br>![icono de plantilla de función](assets/Smock_FileTemplate_18_N.svg) [!UICONTROL Plantillas de función] - enumera [plantillas de función](#function-templates) disponibles, <br/>![icono de campo de esquema](assets/Smock_Folder_18_N.svg) [!UICONTROL Campos de esquema] - enumera los campos disponibles de las categorías de conjuntos de datos (evento, perfil, búsqueda) y los campos derivados definidos anteriormente, y <br/>![icono de campo estándar](assets/Smock_DragHandle_18_N.svg) fields]: campos disponibles estándar (como ID de conjunto de datos de Platform). [!UICONTROL  En el selector solo se muestran los campos estándar numéricos y de cadena. Si la función admite otros tipos de datos, se pueden seleccionar campos estándar con estos otros tipos de datos para valores o campos dentro de la interfaz de regla.<br/>Puede buscar funciones, plantillas de funciones, esquemas y campos estándar mediante el cuadro de búsqueda ![Icono de búsqueda](assets/Smock_Search_18_N.svg). <br/>Puede filtrar la lista de objetos seleccionados seleccionando ![Icono de filtro](assets/Smock_Filter_18_N.svg) Filtrar y especificar filtros en el cuadro de diálogo [!UICONTROL Filtrar campos por]. Puede quitar filtros fácilmente usando ![Icono de cierre](assets/CrossSize75.svg) para cada filtro. |
| 2 | **Generador de reglas** | El campo derivado se genera secuencialmente utilizando una o más reglas. Una regla es una implementación específica de una función y, por lo tanto, siempre se asocia con una sola función. Para crear una regla, arrastre y suelte una función en el generador de reglas. El tipo de función determina la interfaz de la regla.<br/>Consulte la [interfaz de reglas](#rule-interface) para obtener más información. <br/>Puede insertar una función al principio, al final o entre las reglas que ya están disponibles en el generador de reglas. La última regla del generador de reglas determina el resultado final del campo derivado. |
| 3 | **[!UICONTROL ** Configuración de campo **]** | Puede asignar un nombre al campo derivado, describirlo e inspeccionar su tipo de campo. |
| 4 | **[!UICONTROL ** Salida final **]** | Esta área muestra una previsualización actualizada sobre la marcha de los valores de salida, basada en los datos de los últimos 30 días y los cambios realizados en el campo derivado del generador de reglas. |

{style="table-layout:auto"}

## Asistente de plantilla de campo {#wizard}

Cuando accede a la interfaz de campos derivados por primera vez, se muestra el asistente [!UICONTROL Comenzar con una plantilla de campo].

1. Seleccione la plantilla que mejor describa el tipo de campo que está intentando crear.
2. Seleccione el botón **[!UICONTROL ** Seleccionar **]** para continuar.

El cuadro de diálogo de campo derivado se rellena con reglas (y funciones) necesarias o útiles para el tipo de campo seleccionado. Consulte [Plantillas de funciones](#function-templates) para obtener más información sobre las plantillas disponibles.

## Interfaz de regla {#rules}

Cuando define una regla en el generador de reglas, utiliza la interfaz de reglas.

![Captura de pantalla de la interfaz de regla de campo derivada](assets/rule-interface.png)

|  | Nombre | Descripción |
|---------|----------|--------|
| A | **Nombre de regla** | De manera predeterminada, el nombre de regla es **Regla X** (X hace referencia a un número de secuencia). Para editar el nombre de una regla, seleccione su nombre y escriba el nuevo nombre, por ejemplo `Query Parameter`. |
| B | **Nombre de función** | El nombre de función seleccionado para la regla, por ejemplo [!UICONTROL URL PARSE]. Cuando la función es la última de la secuencia de funciones y determina los valores de salida finales, el nombre de la función va seguido de [!UICONTROL - SALIDA FINAL], por ejemplo [!UICONTROL ANÁLISIS DE URL - SALIDA FINAL]. <br/>Para mostrar una ventana emergente con más información sobre la función, seleccione ![icono de Ayuda](assets/Smock_HelpOutline_18_N.svg). |
| C | **Descripción de regla** | Si lo desea, puede agregar una descripción a una regla.<br/>Seleccione ![icono Más](assets/More.svg) y, a continuación, seleccione **[!UICONTROL ** Agregar descripción **]** para agregar una descripción o **[!UICONTROL ** Editar descripción **]** para editar una descripción existente.<br/>Use el editor para escribir una descripción. Puede utilizar la barra de herramientas para dar formato al texto (mediante el selector de estilo, negrita, cursiva, subrayado, derecha, izquierda, centrado, color, lista de números, lista de viñetas) y agregar vínculos a información externa. <br/>Para terminar de editar la descripción, haga clic fuera del editor. |
| D | **Área de función** | Define la lógica de la función. La interfaz depende del tipo de función. La lista desplegable de [!UICONTROL Campo] o [!UICONTROL Valor] muestra todas las categorías de campos (reglas, campos estándar, campos) disponibles, según el tipo de entrada que espera la función. También puede arrastrar y soltar un campo del selector de Campos de esquema y estándar en un Campo o Valor. Cuando ese campo arrastrado se origina desde un conjunto de datos de búsqueda, se inserta automáticamente una función de búsqueda antes de la función que defina. <br/>Vea [Referencia de función](#function-reference) en información detallada para cada una de las funciones admitidas. |

{style="table-layout:auto"}

## Crear un campo derivado {#create}

1. Seleccione una vista de datos existente o cree una vista de datos. Consulte [Vistas de datos](../data-views.md) para obtener más información.

2. Seleccione la ficha **[!UICONTROL ** Componentes **]** de la vista de datos.

3. Seleccione **[!UICONTROL ** Crear campo derivado **]** del carril izquierdo.

4. Para definir el campo derivado, utilice la interfaz [!UICONTROL Crear campo derivado]. Consulte [Interfaz de campo derivada](#derived-field-interface).

   Para guardar el nuevo campo derivado, seleccione **[!UICONTROL ** Guardar **]**.

5. El nuevo campo derivado se agregará al contenedor [!UICONTROL Campos derivados >] como parte de **[!UICONTROL ** Campos de esquema **]** en el carril izquierdo de la vista de datos.


## Editar un campo derivado {#edit}

1. Seleccione una vista de datos existente. Consulte [Vistas de datos](../data-views.md) para obtener más información.

2. Seleccione la ficha **[!UICONTROL ** Componentes **]** de la vista de datos.

3. Seleccione la ficha **[!UICONTROL ** Campos de esquema **]** en el panel [!UICONTROL Conexión] de la izquierda.

4. Seleccione **[!UICONTROL ** Campos derivados >**]** contenedor.

5. Pase el ratón sobre el campo derivado que quiera editar y seleccione ![Editar icono](assets/Smock_Edit_18_N.svg).

6. Para editar el campo derivado, use la interfaz [!UICONTROL Editar campo derivado]. Consulte [Interfaz de campo derivada](#derived-field-interface).

   - Seleccione **[!UICONTROL ** Guardar **]** para guardar el campo derivado actualizado.

   - Seleccione **[!UICONTROL ** Cancelar **]** para cancelar los cambios realizados en el campo derivado.

   - Seleccione **[!UICONTROL ** Guardar como **]** para guardar el campo derivado como un nuevo campo derivado. El nuevo campo derivado tiene el mismo nombre que el campo derivado editado original con `(copy)` agregado.

Alternativamente, si ha utilizado un campo derivado como componente para dimensiones o métricas en la vista de datos:

1. Seleccione el componente. Tenga en cuenta que el componente puede tener un nombre diferente al campo derivado.

1. En el panel Componente, seleccione el ![icono Editar](assets/Smock_Edit_18_N.svg) junto al campo derivado, debajo del nombre del campo Esquema.

1. Para editar el campo derivado, use la interfaz [!UICONTROL Editar campo derivado]. Consulte [Interfaz de campo derivada](#derived-field-interface).

   - Seleccione **[!UICONTROL ** Guardar **]** para guardar el campo derivado actualizado.

   - Seleccione **[!UICONTROL ** Cancelar **]** para cancelar los cambios realizados en el campo derivado.

   - Seleccione **[!UICONTROL ** Guardar como **]** para guardar el campo derivado como un nuevo campo derivado. El nuevo campo derivado tiene el mismo nombre que el campo derivado editado original con `(copy)` agregado.



## Eliminar un campo derivado {#delete}

1. Seleccione una vista de datos existente. Consulte [Vistas de datos](../data-views.md) para obtener más información.

2. Seleccione la ficha **[!UICONTROL ** Componentes **]** de la vista de datos.

3. Seleccione la ficha **[!UICONTROL ** Campos de esquema **]** en el panel [!UICONTROL Conexión].

4. Seleccione **[!UICONTROL ** Campos derivados >**]** contenedor.

5. Pase el ratón sobre el campo derivado que quiera eliminar y seleccione ![Editar icono](assets/Smock_Edit_18_N.svg).

6. En la interfaz [!UICONTROL Editar campo derivado], seleccione **[!UICONTROL Eliminar]**.

   Un cuadro de diálogo [!UICONTROL Eliminar componente] le pedirá que confirme la eliminación. Considere cualquier referencia externa que pueda existir al campo derivado fuera de la vista de datos.

   - Seleccione **[!UICONTROL ** Continuar **]** para eliminar el campo derivado.

Alternativamente, si ha utilizado un campo derivado como componente para dimensiones o métricas en la vista de datos:

1. Seleccione el componente. Tenga en cuenta que el componente puede tener un nombre diferente al campo derivado.

1. En el panel Componente, seleccione el ![icono Editar](assets/Smock_Edit_18_N.svg) junto al campo derivado, debajo del nombre del campo Esquema.

1. En la interfaz [!UICONTROL Editar campo derivado], seleccione **[!UICONTROL Eliminar]**.

   Un cuadro de diálogo [!UICONTROL Eliminar componente] le pedirá que confirme la eliminación. Considere cualquier referencia externa que pueda existir al campo derivado fuera de la vista de datos.

   - Seleccione **[!UICONTROL ** Continuar **]** para eliminar el campo derivado.

>[!NOTE]
>
>Los campos derivados se administran en el nivel de conexión en Customer Journey Analytics. Cualquier cambio realizado en un campo derivado en cualquiera de las vistas de datos asociadas con esa conexión se aplica a todas estas vistas de datos asociadas.



## Plantillas de funciones {#templates}

Para crear rápidamente un campo derivado para casos de uso específicos, hay plantillas de función disponibles. Se puede acceder a estas plantillas de función desde el área de selector de la interfaz de campo derivada o se presentan al utilizarlas por primera vez en el asistente [!UICONTROL Comenzar con una plantilla de campo].


### Canales de marketing {#mchannel}

Esta plantilla de función utiliza una colección de reglas para crear canales de marketing.

+++ Detalles

Para utilizar la plantilla, debe especificar los parámetros correctos para cada función enumerada como parte de las reglas de la plantilla. Consulte [Referencia de función](#function-reference) para obtener más información.

![Captura de pantalla del generador de reglas de plantilla de canal de mercadotecnia](assets/function-template-marketing-channel-template.png)

+++

### Rechazos {#bounces}

Esta plantilla de función utiliza una colección de reglas para identificar los rechazos del sitio.

+++ Detalles

{{select-package}}

Para utilizar la plantilla, debe especificar los parámetros correctos para cada función enumerada como parte de las reglas de la plantilla. Consulte [Referencia de función](#function-reference) para obtener más información.

![Captura de pantalla del generador de reglas de devoluciones](assets/function-template-bounces.png)

+++

### Combinación multidimensional {#multi-dim}

Esta plantilla de función combina dos valores en uno.

+++ Detalles

{{select-package}}

Para utilizar la plantilla, debe especificar los parámetros correctos para cada función enumerada como parte de las reglas de la plantilla. Consulte [Referencia de función](#function-reference) para obtener más información.

![Captura de pantalla del generador de reglas de combinación de varias Dimension](assets/function-template-multi-dimension-combine.png)

+++

### Nombre descriptivo del conjunto de datos {#friendlyname}

Esta plantilla de función proporciona un nombre de conjunto de datos legible.

+++ Detalles

{{select-package}}

Para utilizar la plantilla, debe especificar los parámetros correctos para cada función enumerada como parte de las reglas de la plantilla. Consulte [Referencia de función](#function-reference) para obtener más información.

![Captura de pantalla del generador de reglas Nombre de conjunto de datos descriptivo](assets/function-template-friendly-dataset-name.png)

+++

### Nombre de página de URL {#pagename}

Esta plantilla de función crea un nombre de página simple.

+++ Detalles

{{select-package}}

Para utilizar la plantilla, debe especificar los parámetros correctos para cada función enumerada como parte de las reglas de la plantilla. Consulte [Referencia de función](#function-reference) para obtener más información.

![Captura de pantalla del nombre de página del generador de reglas de URL](assets/function-template-page-name-from-url.png)

+++

### Temporada de vacaciones {#holiday}

Esta plantilla de función clasifica las horas clave del año.

+++ Detalles

{{select-package}}

Para utilizar la plantilla, debe especificar los parámetros correctos para cada función enumerada como parte de las reglas de la plantilla. Consulte [Referencia de función](#function-reference) para obtener más información.

![Captura de pantalla del generador de reglas para la temporada de vacaciones](assets/function-template-holiday-season.png)

+++

### Metas mensuales {#goals}

Esta plantilla de función establece objetivos mensuales personalizados.

+++ Detalles

{{select-package}}

Para utilizar la plantilla, debe especificar los parámetros correctos para cada función enumerada como parte de las reglas de la plantilla. Consulte [Referencia de función](#function-reference) para obtener más información.

![Captura de pantalla del generador mensual de reglas para objetivos](assets/function-template-monthly-goals.png)

+++

### Obtener todos los valores de la lista delimitada {#allvalues}

Esta plantilla de función convierte una lista limitada en una matriz.

+++ Detalles

{{select-package}}

Para utilizar la plantilla, debe especificar los parámetros correctos para cada función enumerada como parte de las reglas de la plantilla. Consulte [Referencia de función](#function-reference) para obtener más información.

![Captura de pantalla del generador de reglas Obtener todos los valores en lista delimitada](assets/function-template-get-all-values-in-delimited-list.png)

+++

### Obtener el primer valor de la lista delimitada {#firstvalue}

Esta plantilla de función obtiene el primer valor de una lista delimitada.

+++ Detalles

{{select-package}}

Para utilizar la plantilla, debe especificar los parámetros correctos para cada función enumerada como parte de las reglas de la plantilla. Consulte [Referencia de función](#function-reference) para obtener más información.

![Captura de pantalla del generador de reglas Obtener primer valor en lista delimitada](assets/function-template-get-first-value-in-delimited-list.png)

+++

### Obtener el último valor de la lista delimitada {#lastvalue}

Esta plantilla de función obtiene el último valor de una lista delimitada.

+++ Detalles

{{select-package}}

Para utilizar la plantilla, debe especificar los parámetros correctos para cada función enumerada como parte de las reglas de la plantilla. Consulte [Referencia de función](#function-reference) para obtener más información.

![Captura de pantalla del generador de reglas Obtener el último valor de la lista delimitada](assets/function-template-get-last-value-in-delimited-list.png)

+++

### Nombre de dominio {#domain}

Esta plantilla de función extrae el nombre de dominio mediante una expresión regular.

+++ Detalles

{{select-package}}

Para utilizar la plantilla, debe especificar los parámetros correctos para cada función enumerada como parte de las reglas de la plantilla. Consulte [Referencia de función](#function-reference) para obtener más información.

![Captura de pantalla del generador de reglas de nombres de dominio](assets/function-template-domain-name.png)

+++

### Obtener parámetro de cadena de consulta {#querystring}

Esta plantilla de función extrae valores de cadena de consulta.

+++ Detalles

{{select-package}}

Para utilizar la plantilla, debe especificar los parámetros correctos para cada función enumerada como parte de las reglas de la plantilla. Consulte [Referencia de función](#function-reference) para obtener más información.

![Captura de pantalla del generador de reglas del parámetro de cadena de consulta Get](assets/function-template-get-query-string-parameter.png)

+++

### Campo de transición {#transition}

Esta plantilla de función cambia la creación de informes de un campo a otro.

+++ Detalles

{{select-package}}

Para utilizar la plantilla, debe especificar los parámetros correctos para cada función enumerada como parte de las reglas de la plantilla. Consulte [Referencia de función](#function-reference) para obtener más información.

![Captura de pantalla del generador de reglas de campo de transición](assets/function-template-transition-field.png)

+++

### Detección de bots simples {#botdetection}

Esta plantilla de función implementa la identificación de bots ligeros.

+++ Detalles

{{select-package}}

Para utilizar la plantilla, debe especificar los parámetros correctos para cada función enumerada como parte de las reglas de la plantilla. Consulte [Referencia de función](#function-reference) para obtener más información.

![Captura de pantalla del generador de reglas de detección de bots simples](assets/function-template-simple-bot-detection.png)

+++

### Vínculo de salida {#exit}

Esta plantilla de función identifica el último vínculo en el que se hizo clic en una sesión.

+++ Detalles

{{select-package}}

Para utilizar la plantilla, debe especificar los parámetros correctos para cada función enumerada como parte de las reglas de la plantilla. Consulte [Referencia de función](#function-reference) para obtener más información.

![Captura de pantalla del generador de reglas de Vínculo de salida](assets/function-template-exit-link.png)

+++

### Vínculo de descarga {#download}

Esta plantilla de función indica vínculos de descarga comunes.

+++ Detalles

{{select-package}}

Para utilizar la plantilla, debe especificar los parámetros correctos para cada función enumerada como parte de las reglas de la plantilla. Consulte [Referencia de función](#function-reference) para obtener más información.

![Captura de pantalla del generador de reglas de vínculos de descarga](assets/function-template-download-link.png)

+++

<!--

+++ Data clean up template

>[!WARNING]
>
>Could not find any information on this template.
+++

-->

## Referencia de función {#functionref}

{{select-package}}

Para cada función admitida, busque los detalles siguientes en:

- especificaciones:
   - tipo de datos de entrada: tipo de datos admitidos,
   - input: posibles valores para input,
   - operadores incluidos: operadores admitidos para esta función (si los hay),
   - limitaciones: limitaciones que se aplican a esta función específica,
   - salida.

- casos de uso, incluidos:
   - datos antes de definir el campo derivado,
   - cómo definir el campo derivado,
   - después de definir el campo derivado.

- restricciones (si procede).


<!-- CASE WHEN -->

### Caso de que {#casewhen}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_casewhen"
>title="Caso de que"
>abstract="Esta función proporciona la capacidad de aplicar condiciones basadas en criterios definidos de uno o varios campos. Estos criterios se utilizan para definir los valores del nuevo campo derivado en función de la secuencia de las condiciones."

<!-- markdownlint-enable MD034 -->


Aplica condicionales, según los criterios definidos en uno o varios campos. Estos criterios se utilizan para definir los valores en un nuevo campo derivado, según la secuencia de las condiciones.

+++ Detalles

## Especificaciones {#casewhen-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Limitaciones | Output |
|---|---|---|---|---|
| <ul><li>Cadena</li><li>Numéricos</li><li>Fecha</li></ul> | <ul><li>[!UICONTROL If], [!UICONTROL Else If] contenedor:</p><ul><li>[!UICONTROL Valor]</li><ul><li>Reglas</li><li>Campos estándar</li><li>Campos</li></ul><li>[!UICONTROL Criterio] (consulte operadores incluidos, según el tipo de valor seleccionado)</li></ul></li><li>[!UICONTROL Luego establezca el valor en], [!UICONTROL De lo contrario, establezca el valor en]:</p><ul><li>[!UICONTROL Valor]</li><ul><li>Reglas</li><li>Campos estándar</li><li>Campos</li></ul></ul></li></ul> | <p>Cadenas</p><ul><li>Es igual a</li><li>Es igual a cualquier término</li><li>Contiene la frase</li><li>Contiene cualquier término</li><li>Contiene todos los términos</li><li>Comienza con</li><li>Comienza con cualquier término</li><li>Finaliza con</li><li>Finaliza con cualquier término</li><li>No es igual a</li><li>No coincide con ningún término</li><li>No contiene la frase</li><li>No contiene ningún término</li><li>No contiene todos los términos</li><li>No comienza con</li><li>No comienza con ningún término</li><li>No finaliza con</li><li>No termina con ningún término</li><li>Se ha establecido</li><li>No se ha establecido</li></ul><p>Numéricos</p><ul><li>Es igual a</li><li>No es igual a</li><li>Es mayor que</li><li>Es mayor que o igual a</li><li>Es menor que</li><li>Es menor que o igual a</li><li>Se ha establecido</li><li>No se ha establecido</li></ul><p>Fechas</p><ul><li>Es igual a</li><li>No es igual a</li><li>es posterior a</li><li>Es posterior o igual a</li><li>Es antes de</li><li>Es anterior o igual a</li><li>Se ha establecido</li><li>No se ha establecido</li></ul> | <ul><li>5 funciones por campo derivado</li><li>200 [operadores](#operators) por campo derivado. Un ejemplo de operador único es &quot;El dominio de referencia contiene Google&quot;. </li></ul> | <p>Nuevo campo derivado</p> |

{style="table-layout:auto"}

## Caso de uso 1 {#casewhen-uc1}

Desea definir reglas para identificar varios canales de marketing aplicando una lógica en cascada para establecer un campo de canal de marketing en el valor adecuado:

- Si el referente es de un motor de búsqueda y la página tiene un valor de cadena de consulta donde `cid` contiene `ps_`, el canal de marketing debe identificarse como una [!DNL *búsqueda de pago*].
- Si el referente es de un motor de búsqueda y la página no tiene la cadena de consulta `cid`, el canal de marketing debe identificarse como una [!DNL *búsqueda natural*].
- Si una página tiene un valor de cadena de consulta donde `cid` contiene `em_`, el canal de marketing debe identificarse como [!DNL *correo electrónico*].
- Si una página tiene un valor de cadena de consulta donde `cid` contiene `ds_`, el canal de marketing debe identificarse como [!DNL *anuncio para mostrar*].
- Si una página tiene un valor de cadena de consulta donde `cid` contiene `so_`, el canal de marketing debe identificarse como [!DNL *Social de pago*].
- Si el referente es de un dominio referente de [!DNL twitter.com], [!DNL facebook.com], [!DNL linkedin.com] o [!DNL tiktok.com], el canal de marketing debe identificarse como un [!DNL *Social natural*].
- Si ninguna de las reglas anteriores coincide, el canal de marketing debe identificarse como [!DNL *Otro referente*].

En caso de que el sitio reciba los siguientes eventos de ejemplo, que contienen [!UICONTROL Referente] y [!UICONTROL Dirección URL de la página], estos eventos se deben identificar de la siguiente manera:

| [!DNL Event] | [!DNL Referrer] | [!DNL Page URL] | [!DNL Marketing Channel] |
|:--:|----|----|----|
| 1 | `https://facebook.com` | `https://site.com/home` | [!DNL Natural Social] |
| 2 | `https://abc.com` | `https://site.com/?cid=ds_12345678` | [!DNL Display] |
| 3 | | `https://site.com/?cid=em_12345678` | [!DNL Email] |
| 4 | `https://google.com` | `https://site.com/?cid=ps_abc098765` | [!DNL Paid Search] |
| 5 | `https://google.com` | `https://site.com/?cid=em_765544332` | [!DNL Email] |
| 6 | `https://google.com` |  | [!DNL Natural Search] |

{style="table-layout:auto"}

### Datos anteriores {#casewhen-uc1-databefore}

| [!DNL Referrer] | [!DNL Page URL] |
|----|----|
| `https://facebook.com` | `https://site.com/home` |
| `https://abc.com` | `https://site.com/?cid=ds_12345678` |
|  | `https://site.com/?cid=em_12345678` |
| `https://google.com` | `https://site.com/?cid=ps_abc098765` |
| `https://google.com` | `https://site.com/?cid=em_765544332` |
| `https://google.com` | |

{style="table-layout:auto"}

### Campo derivado {#casewhen-uc1-derivedfield}

Usted define un campo derivado de `Marketing Channel`. Utilice las funciones [!UICONTROL CASE WHEN] para definir reglas que creen valores para el campo en función de los valores existentes para el campo `Page URL` y `Referring URL`.

Observe el uso de la función [!UICONTROL URL PARSE] para definir reglas que recuperen los valores de `Page Url` y `Referring Url` antes de aplicar las reglas [!UICONTROL CASE WHEN].

![Captura de pantalla del caso de la regla 1](assets/case-when-1.png)

### Datos después de {#casewhen-uc1-dataafter}

| [!DNL Marketing Channel] |
|----|
| [!DNL Natural Social] |
| [!DNL Display] |
| [!DNL Email] |
| [!DNL Paid Search] |
| [!DNL Email] |
| [!DNL Natural Search] |

{style="table-layout:auto"}


## Caso de uso 2 {#casewhen-uc2}

Ha recopilado varias variaciones diferentes de búsqueda dentro de su dimensión [!DNL Product Finding Methods]. Para comprender el rendimiento general de la búsqueda frente a la exploración, debe dedicar una gran cantidad de tiempo a combinar los resultados manualmente.

Su sitio recopila los siguientes valores para su dimensión [!DNL Product Finding Methods]. Al final, todos estos valores indican una búsqueda.

| Valor recopilado | Valor real |
|---|---|
| [!DNL search p13n_no] | [!DNL search] |
| [!DNL search p13n_yes] | [!DNL search] |
| [!DNL search refine p13n_no] | [!DNL search] |
| [!DNL search refine p13n_yes] | [!DNL search] |
| [!DNL search redirect p13n_yes] | [!DNL search] |
| [!DNL search-redirect] | [!DNL search] |

{style="table-layout:auto"}


### Datos anteriores {#casewhen-uc2-databefore}

| [!DNL Product Finding Methods] |
|----|
| [!DNL search p13_no] |
| [!DNL search p13_yes] |
| [!DNL browse] |
| [!DNL search refine p13_no] |
| [!DNL search refine p13_yes] |
| [!DNL browse] |
| [!DNL search redirect p13_yes] |
| [!DNL search-redirect] |
| [!DNL browse] |

{style="table-layout:auto"}

### Campo derivado {#casewhen-uc2-derivedfield}

Usted define un campo derivado de `Product Finding Methods (new)`. Usted crea las siguientes reglas [!UICONTROL CASE WHEN] en el generador de reglas. Estas reglas aplican lógica a todas las posibles variaciones de los antiguos valores de campo de [!UICONTROL Métodos de búsqueda de productos] para `search` y `browse` utilizando el criterio [!UICONTROL Contiene la frase].

![Captura de pantalla del caso cuando la regla 2](assets/case-when-2.png)

### Datos después de {#casewhen-uc2-dataafter}

| [!DNL Product Finding Methods (new)] |
|----|
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |

{style="table-layout:auto"}


## Caso de uso 3 {#casewhen-uc3}

Como empresa de viajes, le gustaría agrupar la duración del viaje en viajes reservados para poder informar sobre la duración total de los viajes.

Suposiciones:

- La organización está recopilando la duración del viaje en un campo numérico.
- Les gustaría agrupar las duraciones de 1 a 3 días en un contenedor denominado &#39;[!DNL short trip]&#39;
- Les gustaría agrupar las duraciones de 4 a 7 días en un contenedor denominado &#39;[!DNL medium trip]&#39;
- Les gustaría agrupar duraciones de más de 8 días en un contenedor denominado &#39;[!DNL long trip]&#39;
- Se reservaron 132 viajes para un día de duración
- Se reservaron 110 viajes para una duración de 2 días
- Se reservaron 105 viajes para una duración de 3 días
- Se reservaron 99 viajes para una duración de 4 días
- Se reservaron 92 viajes para una duración de 5 días
- Se reservaron 85 viajes para una duración de 6 días
- Se reservaron 82 viajes para una duración de 7 días
- Se reservaron 78 viajes para una duración de 8 días
- Se reservaron 50 viajes para una duración de 9 días
- Se reservaron 44 viajes para una duración de 10 días
- Se reservaron 38 viajes para una duración de 11 días
- Se reservaron 31 viajes para una duración de 12 días

El informe deseado debería tener un aspecto similar al siguiente:

| [!DNL Trip Duration Type] | [!DNL Bookings] |
|----|---:|
| [!DNL medium trip] | 358 |
| [!DNL short trip] | 347 |
| [!DNL long trip] | 241 |

{style="table-layout:auto"}

### Datos anteriores {#casewhen-uc3-databefore}

| [!DNL Trip Duration] |
|---:|
| 1 |
| 12 |
| 3 |
| 6 |
| 4 |
| 8 |
| 6 |
| 2 |
| 1 |
| 2 |
| 21 |
| 8 |

### Campo derivado {#casewhen-uc3-derivedfield}

Usted define un campo derivado de `Trip Duration (bucketed)`. Cree la siguiente regla [!UICONTROL CASE WHEN] en el generador de reglas. Esta regla aplica lógica para agrupar los antiguos valores de campo de [!UICONTROL Duración del viaje] en tres valores: `short trip`, `medium  trip` y `long trip`.

![Captura de pantalla del caso cuando la regla 3](assets/case-when-3.png)


### Datos después de {#casewhen-uc3-dataafter}

| [!DNL Trip Duration (bucketed)] |
|---|
| [!DNL short trip] |
| [!DNL long trip] |
| [!DNL short trip] |
| [!DNL medium trip] |
| [!DNL medium trip] |
| [!DNL long trip] |
| [!DNL medium trip] |
| [!DNL short trip] |
| [!DNL short trip] |
| [!DNL short trip] |
| [!DNL long trip] |
| [!DNL long trip] |


## Más información {#casewhen-more-info}

Customer Journey Analytics usa una estructura de contenedor anidada, siguiendo el modelo de Adobe Experience Platform [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es) (modelo de datos de experiencia). Consulte [Contenedores](../create-dataview.md#containers) y [Contenedores de filtro](../../components/filters/filters-overview.md#filter-containers) para obtener más información. Este modelo de contenedor, aunque flexible por naturaleza, impone algunas restricciones al utilizar el generador de reglas.

Customer Journey Analytics utiliza el siguiente modelo de contenedor predeterminado:

<p align="center">
<img src="./assets/containers.png" width="50%" valign="middle">
</p>

Las siguientes restricciones se aplican y se aplican al *seleccionar* y *establecer* valores.

|  | Restricciones |
|:---:|----|
| **A** | Los valores que *seleccione* dentro de la misma construcción [!UICONTROL If], [!UICONTROL Else If] (con [!UICONTROL And] u [!UICONTROL Or]) en una regla deben proceder del mismo contenedor y pueden ser de cualquier tipo (cadena ![String](assets/Smock_ABC_18_N.svg), numérico ![Numeric](assets/Smock_123_18_N.svg), etc.). <br/>![Captura de pantalla de la dependencia A](assets/dependency-a.png) |
| **B** | Todos los valores que *estableció* en una regla deben pertenecer al mismo contenedor y tener el mismo tipo o un valor derivado del mismo tipo. <br/> ![Captura de pantalla de la dependencia B](assets/dependency-b.png) |
| **C** | Los valores que *seleccione* en [!UICONTROL If], [!UICONTROL Else If] construcciones en la regla *no* deben originarse en el mismo contenedor y *no* deben ser del mismo tipo. <br/> ![Captura de pantalla de la dependencia C](assets/dependency-c.png) |

{style="table-layout:auto"}

+++

<!-- CLASSIFY -->

### Clasificar {#classify}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_classify"
>title="Clasificar"
>abstract="Esta función proporciona la capacidad de definir un conjunto de valores que se sustituyen por los valores correspondientes mediante la entrada de texto."

<!-- markdownlint-enable MD034 -->


Define un conjunto de valores que se reemplazan por los valores correspondientes en un nuevo campo derivado.

+++ Detalles

## Especificaciones {#classify-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Limitaciones | Output |
|---|---|---|---|---|
| <ul><li>Cadena</li><li>Numéricos</li><li>Fecha</li></ul> | <ul><li>[!UICONTROL Campo para clasificar]:<ul><li>Reglas</li><li>Campos estándar</li><li>Campos</li></ul></li><li>[!UICONTROL Cuando el valor es igual a] y [!UICONTROL Reemplazar valores por]:</p><ul><li>Cadena</li></ul><li>Mostrar valores originales<ul><li>Booleano</li></ul></li></ul> | <p>N/A</p> | <ul><li>5 funciones por campo derivado</li><li>200 [operadores](#operators) por campo derivado. Cada entrada de [!UICONTROL Cuando el valor es igual al valor original] [!UICONTROL Reemplazar el valor por un nuevo valor] se considera una operación.</li></ul> | <p>Nuevo campo derivado</p> |

{style="table-layout:auto"}


## Caso de uso 1 {#classify-uc1}

Tiene un archivo CSV que incluye una columna de clave para `hotelID` y una o más columnas adicionales asociadas con `hotelID`: `city`, `rooms`, `hotel name`.
Está recopilando [!DNL Hotel ID] en una dimensión, pero desea crear una dimensión [!DNL Hotel Name] derivada de `hotelID` en el archivo CSV.

**Contenido y estructura de archivos CSV**

| [!DNL hotelID] | [!DNL city] | [!DNL rooms] | [!DNL hotel name] |
|---|---|---:|---|
| [!DNL SLC123] | [!DNL Salt Lake City] | 40 | [!DNL SLC Downtown] |
| [!DNL LAX342] | [!DNL Los Angeles] | 60 | [!DNL LA Airport] |
| [!DNL SFO456] | [!DNL San Francisco] | 75 | [!DNL Market Street] |
| [!DNL AMS789] | [!DNL Amsterdam] | 50 | [!DNL Okura] |

{style="table-layout:auto"}

**Informe actual**

| [!DNL Hotel ID] | Vistas del producto |
|---|---:|
| [!DNL SLC123] | 200 |
| [!DNL LX342] | 198 |
| [!DNL SFO456] | 190 |
| [!DNL AMS789] | 150 |

{style="table-layout:auto"}


**Informe deseado**

| [!DNL Hotel Name] | Vistas del producto |
|----|----:|
| [!DNL SLC Downtown] | 200 |
| [!DNL LA Airport] | 198 |
| [!DNL Market Street] | 190 |

{style="table-layout:auto"}

### Datos anteriores {#classify-uc1-databefore}

| [!DNL Hotel ID] |
|----|
| [!DNL SLC123] |
| [!DNL LAX342] |
| [!DNL SFO456] |
| [!DNL AMS789] |

{style="table-layout:auto"}


### Campo derivado {#classify-uc1-derivedfield}

Usted define un campo derivado de `Hotel Name`. La función [!UICONTROL CLASSIFY] se usa para definir una regla en la que se pueden clasificar valores del campo [!UICONTROL Id. de hotel] y reemplazarlos con valores nuevos.

Si desea incluir valores originales que no ha definido como parte de los valores que se van a clasificar (por ejemplo, ID de hotel AMS789), asegúrese de seleccionar **[!UICONTROL Mostrar valores originales]**. Esto garantiza que AMS789 forme parte de la salida del campo derivado, a pesar de que ese valor no se clasifique.

![Captura de pantalla de la regla de clasificación 1](assets/classify-1.png)

### Datos después de {#classify-uc1-dataafter}

| [!DNL Hotel Name] |
|----|
| [!DNL SLC Downtown] |
| [!DNL LA Airport] |
| [!DNL Market Street] |

{style="table-layout:auto"}


## Caso de uso 2 {#classify-uc2}

Ha recopilado direcciones URL en lugar del nombre de página descriptivo de varias páginas. Esta colección mixta de valores interrumpe la creación de informes.

### Datos anteriores {#classify-uc2-databefore}

| [!DNL Page Name] |
|---|
| [!DNL Home Page] |
| [!DNL Flight Search] |
| `http://www.adobetravel.ca/Hotel-Search` |
| `https://www.adobetravel.com/Package-Search` |
| [!DNL Deals & Offers] |
| `http://www.adobetravel.ca/user/reviews` |
| `https://www.adobetravel.com.br/Generate-Quote/preview` |

{style="table-layout:auto"}

### Campo derivado {#classify-uc2-derivedfield}

Usted define un campo derivado de `Page Name (updated)`. La función [!UICONTROL CLASSIFY] se usa para definir una regla en la que se pueden clasificar los valores del campo [!UICONTROL Nombre de página] existente y reemplazarlos con valores correctos actualizados.

![Captura de pantalla de la regla de clasificación 2](assets/classify-2.png)

### Datos después de {#classify-uc2-dataafter}

| [!DNL Page Name (updated)] |
|---|
| [!DNL Home Page] |
| [!DNL Flight Search] |
| [!DNL Hotel Search] |
| [!DNL Package Search] |
| [!DNL Deals & Offers] |
| [!DNL Reviews] |
| [!DNL Generate Quote] |


## Más información {#classify-moreinfo}

La siguiente funcionalidad adicional está disponible en la interfaz de reglas de clasificación:

- Para borrar rápidamente todos los valores de tabla, seleccione ![Borrar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Erase_18_N.svg) **[!UICONTROL Borrar todos los valores de tabla]**.
- Para cargar un archivo CSV que contenga valores originales para Cuando los valores sean iguales y los nuevos valores para Reemplazar valores con, seleccione ![CSV](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg) **[!UICONTROL Cargar CSV]**.
- Para descargar una plantilla para crear un archivo CSV con valores nuevos y originales que cargar, selecciona ![Descargar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Download_18_N.svg) **[!UICONTROL Descargar plantilla CSV]**.
- Para descargar un archivo CSV con todos los valores nuevos y originales rellenados en la interfaz de reglas, seleccione ![Descargar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Download_18_N.svg) **[!UICONTROL Descargar valores CSV]**.


+++

<!-- CONCATENATE -->

### Concatenar {#concatenate}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_concatenate"
>title="Concatenar"
>abstract="Esta función proporciona la capacidad de combinar dos o más campos, campos derivados o valores de cadena introducidos por el usuario en un único campo con delimitadores definidos"

<!-- markdownlint-enable MD034 -->


Combina valores de campo en un único campo derivado nuevo con delimitadores definidos.

+++ Detalles

## Especificaciones {#concatenate-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Limitaciones | Output |
|---|---|---|---|---|
| <ul><li>Cadena</li></ul> | <ul><li>[!UICONTROL Valor]:<ul><li>Reglas</li><li>Campos estándar</li><li>Campos</li><li>Cadena</li></ul></li><li>[!UICONTROL Delimitador]:<ul><li>Cadena</li></ul></li> </ul> | <p>N/A</p> | <p>2 funciones por campo derivado</p> | <p>Nuevo campo derivado</p> |

{style="table-layout:auto"}


## Caso de uso {#concatenate-uc}

Actualmente, recopila los códigos de aeropuerto de origen y destino como campos independientes. Desea tomar los dos campos y combinarlos en una sola dimensión separada por un guion (-). Por lo tanto, puede analizar la combinación de origen y destino para identificar las rutas principales reservadas.

Suposiciones:

- Los valores de origen y destino se recopilan en campos independientes en la misma tabla.
- El usuario determina si se debe utilizar el delimitador &quot;-&quot; entre los valores.

Imagine que se producen las siguientes reservas:

- El cliente ABC123 reserva un vuelo entre Salt Lake City (SLC) y Orlando (MCO)
- Cliente ABC456 reserva un vuelo entre Salt Lake City (SLC) y Los Ángeles (LAX)
- Cliente ABC789 reserva un vuelo entre Salt Lake City (SLC) y Seattle (SEA)
- Cliente ABC987 reserva un vuelo entre Salt Lake City (SLC) y San José (SJO)
- Cliente ABC654 reserva un vuelo entre Salt Lake City (SLC) y Orlando (MCO)

El informe deseado debería tener un aspecto similar al siguiente:

| Origen/Destino | Reservas |
|----|---:|
| SLC-MCO | 2 |
| SLC-LAX | 1 |
| SLC-SEA | 1 |
| SLC-SJO | 1 |

{style="table-layout:auto"}


### Datos anteriores {#concatenate-uc-databefore}

| Origen | Destino |
|----|---:|
| SLC | MCO |
| SLC | LAXO |
| SLC | SEA |
| SLC | SJO |
| SLC | MCO |

{style="table-layout:auto"}

### Campo derivado {#concatenate-derivedfield}

Usted define un campo derivado de `Origin - Destination`. Utiliza la función [!UICONTROL CONCATENATE] para definir una regla que concatene los campos [!UICONTROL Original] y [!UICONTROL Destino] mediante el `-` [!UICONTROL Delimitador].

![Captura de pantalla de la regla de concatenación](assets/concatenate.png)

### Datos después de {#concatenate-dataafter}

| Origen - Destino<br/>(campo derivado) |
|---|
| SLC-MCO |
| SLC-LAX |
| SLC-SEA |
| SLC-SJO |
| SLC-MCO |

{style="table-layout:auto"}

+++


### Deduplicar {#dedup}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_deduplicate"
>title="Deduplicar"
>abstract="Esta función proporciona la capacidad de configurar un campo para que solo cuente los valores de forma no repetitiva en el nivel de sesión o de persona. Además, se puede utilizar un ID de anulación de duplicación para garantizar que, en función de un ID determinado (como un ID de compra), solo se emplee un valor (la primera instancia o la última)."

<!-- markdownlint-enable MD034 -->


Evita contar un valor varias veces.

+++ Detalles


## Especificaciones {#deduplicate-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Limitaciones | Output |
|---|---|---|---|---|
| <ul><li>Cadena</li><li>Numéricos</li></ul> | <ul><li>[!UICONTROL Valor]:<ul><li>Reglas</li><li>Campos estándar</li><li>Campos</li><li>Cadena</li></ul></li><li>[!UICONTROL Ámbito]:<ul><li>Persona</li><li>Sesión</li></ul></li><li>[!UICONTROL ID de anulación de duplicación]:<ul><li>Reglas</li><li>Campos estándar</li><li>Campos</li><li>Cadena</li></ul><li>[!UICONTROL Valor que conservar]:<ul><li>Mantener primera instancia</li><li>Mantener última instancia</li></ul></li></ul> | <p>N/A</p> | <p>5 funciones por campo derivado</p> | <p>Nuevo campo derivado</p> |

{style="table-layout:auto"}


## Caso de uso 1 {#deduplicate-uc1}

Desea evitar el recuento de ingresos duplicados cuando un usuario vuelve a cargar la página de confirmación de reserva. Utilice el ID de confirmación de reserva en el identificador para no volver a contar los ingresos cuando se reciban en el mismo evento.

### Datos anteriores {#deduplicate-uc1-databefore}

| ID de confirmación de reserva | Ingresos |
|----|---:|
| ABC123456789 | 359 |
| ABC123456789 | 359 |
| ABC123456789 | 359 |

{style="table-layout:auto"}

### Campo derivado {#deduplicate-uc1-derivedfield}

Usted define un campo derivado de `Booking Confirmation`. Utiliza la función [!UICONTROL DEDUPLICATE] para definir una regla que anule la duplicación de [!UICONTROL Value] [!DNL Booking] para [!UICONTROL Scope] [!DNL Person] mediante [!UICONTROL ID de anulación de duplicación] [!UICONTROL ID de confirmación de reserva]. Selecciona [!UICONTROL Conservar primera instancia] como [!UICONTROL Valor que mantener].

![Captura de pantalla de la regla de concatenación](assets/deduplicate-1.png)

### Datos después de {#deduplicate-uc1-dataafter}

| ID de confirmación de reserva | Ingresos |
|----|---:|
| ABC123456789 | 359 |
| ABC123456789 | 0 |
| ABC123456789 | 0 |

{style="table-layout:auto"}

## Caso de uso 2 {#deduplicate-uc2}

Los eventos se utilizan como un proxy para las pulsaciones de campañas con campañas de marketing externas. Las recargas y redirecciones están ocasionando que la métrica de eventos esté inflada. Desea deduplicar la dimensión de código de seguimiento para que solo se recopile la primera y minimizar el recuento excesivo de eventos.

### Datos anteriores {#deduplicate-uc2-databefore}

| ID de visitante | Canal de marketing | Eventos |
|----|---|---:|
| ABC123 | búsqueda de pago | 1 |
| ABC123 | búsqueda de pago | 1 |
| ABC123 | búsqueda de pago | 1 |
| DEF123 | email | 1 |
| DEF123 | email | 1 |
| JKL123 | búsqueda natural | 1 |
| JKL123 | búsqueda natural | 1 |

{style="table-layout:auto"}

### Campo derivado {#deduplicate-uc2-derivedfield}

Usted define un nuevo campo derivado de `Tracking Code (deduplicated)`. Utiliza la función [!UICONTROL DEDUPLICATE] para definir una regla que anule la duplicación del [!UICONTROL código de seguimiento] con un [!UICONTROL ámbito de anulación de duplicación] de [!UICONTROL Session] y [!UICONTROL Mantenga la primera instancia] como [!UICONTROL Valor que mantener].

![Captura de pantalla de la regla de concatenación](assets/deduplicate-2.png)

### Datos después de {#deduplicate-uc2-dataafter}

| ID de visitante | Canal de marketing | Eventos |
|----|---|---:|
| ABC123 | búsqueda de pago | 1 |
| DEF123 | email | 1 |
| JKL123 | búsqueda natural | 1 |

{style="table-layout:auto"}

+++


<!-- FIND AND REPLACE -->

### Buscar y reemplazar {#find-and-replace}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_findandreplace"
>title="Buscar y reemplazar"
>abstract="Esta función proporciona la capacidad de buscar todos los valores de un campo seleccionado y reemplazarlos con un valor diferente en un nuevo campo derivado."

<!-- markdownlint-enable MD034 -->


Busca todos los valores de un campo seleccionado y reemplaza esos valores por un valor diferente en un nuevo campo derivado.

+++ Detalles

## Especificaciones {#findreplace-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Limitaciones | Output |
|---|---|---|---|---|
| <ul><li>Cadena</li></ul> | <ul><li>[!UICONTROL Valor]<ul><li>Reglas</li><li>Campos estándar</li><li>Campos</li></ul></li><li>[!UICONTROL Buscar todos], [!UICONTROL y reemplazar todos con]:<ul><li>Cadena</li></ul></li></ul></ul> | <p>Cadenas</p><ul><li>[!UICONTROL Buscar todos], [!UICONTROL y reemplazar todos con]</li></ul> | <p>5 funciones por campo derivado</p> | <p>Nuevo campo derivado</p> |

{style="table-layout:auto"}


## Caso de uso {#findreplace-uc}

Ha recibido algunos valores mal formados para su informe de canales de marketing externos, por ejemplo `email%20 marketing` en lugar de `email marketing`. Estos valores mal formados fracturan los informes y dificultan la visualización del rendimiento del correo electrónico. Desea reemplazar `email%20marketing` por `email marketing`.

**Informe original**

| [!DNL External Marketing Channels] | [!DNL Sessions] |
|---|--:|
| [!DNL email marketing] | 500 |
| [!DNL email %20marketing] | 24 |

{style="table-layout:auto"}

**Informe preferido**

| [!DNL External Marketing Channels] | [!DNL Sessions] |
|---|--:|
| [!DNL email marketing] | 524 |


### Datos anteriores {#findreplace-uc-databefore}

| [!DNL External Marketing] |
|----|
| [!DNL email marketing] |
| [!DNL email%20marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email%20marketing] |

{style="table-layout:auto"}

### Campo derivado {#findreplace-uc-derivedfield}

Usted define un campo derivado de `Email Marketing (updated)`. Utiliza la función [!UICONTROL BUSCAR Y REEMPLAZAR] para definir una regla que busque y reemplace todas las ocurrencias de `email%20marketing` por `email marketing`.

![Captura de pantalla de la regla Buscar y reemplazar](assets/find-and-replace.png)

### Datos después de {#findreplace-uc-dataafter}

| [!DNL External Marketing (updated)] |
|----|
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |

{style="table-layout:auto"}

+++


<!-- LOOKUP -->

### Búsqueda {#lookup}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_lookup"
>title="Búsqueda"
>abstract="Esta función proporciona la capacidad de utilizar campos de un conjunto de datos de búsqueda mediante una clave coincidente entre conjuntos de datos."

<!-- markdownlint-enable MD034 -->


Valores de búsqueda que utilizan un campo de un conjunto de datos de búsqueda y devuelven un valor en un nuevo campo derivado o para un procesamiento de reglas adicional.

+++ Detalles

## Especificación {#lookup-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Límite | Output |
|---|---|---|---|---|
| <ul><li>Cadena</li><li>Numéricos</li><li>Fecha</li></ul> | <ul><li>[!UICONTROL Campo para aplicar la búsqueda]:</li><ul><li>Reglas</li><li>Campos estándar</li><li>Campos</li></ul><li>[!UICONTROL Conjunto de datos de búsqueda]</li><ul><li>Conjunto de datos</li></ul><li>[!UICONTROL Clave de coincidencia]<ul><li>Reglas</li><li>Campos</li></ul></li><li>Valores que se deben devolver<ul><li>Reglas</li><li>Campos</li></ul></li></ul> | <p>N/A</p> | <p>3 funciones por campo derivado</p> | <p>Nuevo campo o valor derivado para un procesamiento posterior en la regla siguiente</p> |

{style="table-layout:auto"}

## Caso de uso {#lookup-uc}

Desea buscar el nombre de la actividad mediante el ID de actividad recopilado cuando sus clientes hicieron clic en un banner personalizado que se muestra a través de Adobe Target. Desea utilizar un conjunto de datos de búsqueda con actividades de Analytics for Target (A4T) que contenga ID de actividad y nombres de actividad.

### Conjunto de datos de búsqueda A4T {#lookup-uc-lookup}

| ID de actividad | Nombre de la actividad |
|---|---|
| 415851 | Páginas de categoría de prueba MVT |
| 415852 | Luma: Campaign Max 2022 |
| 402922 | Titulares de página de inicio |

{style="table-layout:auto"}

### Campo derivado {#lookup-uc-derivedfield}

Usted define un campo derivado de `Activity Name`. La función [!UICONTROL BUSCAR] se usa para definir una regla para buscar el valor de los datos recopilados, especificada en el campo [!UICONTROL Campo al que aplicar la búsqueda] (por ejemplo **[!DNL ActivityIdentifier]**). Selecciona el conjunto de datos de búsqueda de la lista [!UICONTROL Conjunto de datos de búsqueda] (por ejemplo, **[!DNL New CJA4T Activities]**). A continuación, selecciona el campo de identificador (por ejemplo **[!DNL ActivityIdentifier]**) de la lista [!UICONTROL Clave coincidente] y el campo que se devolverá de la lista [!UICONTROL Values to return] (por ejemplo **[!DNL ActivityName]**).

![Captura de pantalla de la regla en minúsculas](assets/lookup.png)

## Más información {#lookup-more-info}

La función de búsqueda se aplica en el momento del informe a los datos recuperados por Customer Journey Analytics del conjunto de datos de búsqueda que ha configurado como parte de la conexión.

Puede insertar rápidamente una función [!UICONTROL Lookup] en el generador de reglas, que ya contiene una o más funciones.

1. Seleccione **[!UICONTROL Campos de esquema]** del selector.
1. Seleccione ![Icono de campo de esquema](assets/Smock_Folder_18_N.svg) **[!UICONTROL Conjuntos de datos de búsqueda]**.
1. Seleccione el conjunto de datos de búsqueda y busque el campo que desee utilizar para la búsqueda.
1. Arrastre y suelte el campo de búsqueda en cualquiera de los campos de entrada disponibles para una función (por ejemplo, Case When). Si es válido, un cuadro azul, etiquetado **[!UICONTROL + Agregar]**, le permite soltar el campo e insertar automáticamente una función de búsqueda antes de la función en la que soltó el campo de búsqueda. La función de búsqueda insertada se rellena automáticamente con valores relevantes para todos los campos.
   ![Arrastre de búsqueda](assets/lookup-drag.png)

+++


<!-- LOWERCASE -->

### Minúsculas {#lowercase}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_lowercase"
>title="Minúsculas"
>abstract="Esta función convierte todo el texto de la cadena en valores en minúsculas."

<!-- markdownlint-enable MD034 -->


Convierte los valores de un campo a minúsculas y los almacena en un nuevo campo derivado.

+++ Detalles

## Especificación {#lowercase-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Límite | Output |
|---|---|---|---|---|
| <ul><li>Cadena</li><li>Numéricos</li><li>Fecha</li></ul> | <ul><li>[!UICONTROL Campo]:</li><ul><li>Reglas</li><li>Campos estándar</li><li>Campos</li></ul> | <p>N/A</p> | <p>2 funciones por campo derivado</p> | <p>Nuevo campo derivado</p> |

{style="table-layout:auto"}

## Caso de uso {#lowercase-uc}

Desea convertir todos los nombres de productos recopilados en minúsculas para un sistema de informes adecuado.

### Datos anteriores {#lowercase-uc-databefore}

| Nombres de productos recopilados | Vistas del producto |
|---|---:|
| Raqueta de tenis | 35 |
| Raqueta de tenis | 33 |
| raqueta de tenis | 21 |
| Bate de béisbol | 15 |
| Bate de béisbol | 12 |
| bate de béisbol | 10 |

{style="table-layout:auto"}

### Campo derivado {#lowercase-uc-derivedfield}

Usted define un campo derivado de `Product Names`. Utilice la función [!UICONTROL LOWERCASE] para definir una regla que convierta el valor del campo [!UICONTROL Nombres de productos recopilados] a minúsculas y almacene esa información en el nuevo campo derivado.

![Captura de pantalla de la regla en minúsculas](assets/lowercase.png)


### Datos después de {#lowercase-uc-dataafter}

| Nombres de productos | Vistas del producto |
|---|---|
| raqueta de tenis | 89 |
| bate de béisbol | 37 |

{style="table-layout:auto"}

+++

<!-- MATH -->

### Math {#math}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_math"
>title="Math"
>abstract="Esta función proporciona la capacidad de realizar operaciones matemáticas en un campo. La función se puede aprovechar para realizar operaciones aritméticas básicas, como suma, resta, multiplicación y división."

<!-- markdownlint-enable MD034 -->


Utilice operadores matemáticos básicos (sumar, restar, multiplicar, dividir y aumentar a una potencia) en campos numéricos.

+++ Detalles

## Especificación {#math-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Límite | Output |
|---|---|---|---|---|
| <ul><li>Numéricos</li></ul> | <ul><li>Uno o varios campos numéricos</li><li>Uno o varios operadores (sumar, restar, multiplicar, dividir, aumentar a una potencia)</li><li>Valor de entrada del usuario</li></ul> | <ul><li>`+` (agregar)</li><li>`-` (restar)</li><li>`*` (multiplicar)</li><li>`/` (dividir)</li><li>`^` (aumento de potencia)</li></ul> | <ul><li>25 operaciones por campo derivado</li><li>5 funciones matemáticas por campo derivado</li></ul> | <p>Nuevo campo derivado</p> |

{style="table-layout:auto"}

## Caso de uso {#math-uc}

Debido a la inflación, desea corregir las cifras de ingresos de los datos CRM ingeridos con una inflación del 5 %.

### Datos anteriores {#math-uc-databefore}

| ID de CRM | Ingresos anuales |
|---|---:|
| 1234 | 35.070.000 |
| 4133 | 7.500.000 |
| 8110 | 10.980 |
| 2201 | 42.620 |

{style="table-layout:auto"}

### Campo derivado {#math-uc-derivedfield}

Usted define un campo derivado de `Corrected Annual Revenue`. La función [!UICONTROL MATH] se usa para definir una regla que multiplica el número de ingresos anuales original por 1,05.

![Captura de pantalla de la regla matemática](assets/math.png)


### Datos después de {#math-uc-dataafter}

| ID de CRM | Ingresos anuales corregidos |
|---|---:|
| 1234 | 36.823.500 |
| 4133 | 7.875.000 |
| 8110 | 11,529,00 |
| 2201 | 44.751 |

{style="table-layout:auto"}

## Más información {#math-more-info}

Para crear una fórmula:

1. Empiece a escribir en el campo Fórmula y los campos numéricos que coincidan con lo que escriba aparecerán en un menú emergente. También puede arrastrar y soltar un campo numérico desde los campos disponibles en el panel izquierdo.
   ![Más información matemática 1](assets/math-more-info-1.png)

1. Agregue el operando (por ejemplo `*` para multiplicar) seguido de otro campo o un valor estático. Puede utilizar paréntesis para definir fórmulas más complejas.

1. Para insertar un valor estático (por ejemplo, `1.05`), escriba el valor y seleccione **[!UICONTROL Agregar *x* como valor estático]** o **[!UICONTROL Agregar -*x* como valor estático negativo]** en el menú emergente.
   ![Más información matemática 2](assets/math-more-info-2.png)

1. La marca de verificación verde ![Checkmark](./assets/checkmark.svg)</span> indica si la fórmula matemática es válida; de lo contrario, verá una advertencia ![Alert](./assets/alert.svg) y el mensaje [!UICONTROL Expresión de fórmula no válida].
   ![Más información matemática 3](assets/math-more-info-3.png)

Hay algunas consideraciones importantes al trabajar con números estáticos en la función [!UICONTROL MATH]:

- Los valores estáticos deben asociarse con un campo. Por ejemplo, no se admite el uso de la función [!UICONTROL MATH] con solo campos estáticos.
- No se puede usar el operador de subida a alimentación (`ˆ`) en un valor estático.
- Si utiliza varios valores estáticos en una fórmula, estos valores estáticos deben agruparse con paréntesis para que la fórmula sea válida. Por ejemplo:

   - Esta fórmula devuelve un error.
     ![Más información matemática 4](assets/math-more-info-4.png)

   - Esta fórmula es válida.
     ![Más información matemática 5](assets/math-more-info-5.png)

Utilice la función Math para cálculos basados en el nivel de visita. Utilice la función [Resumir](#summarize) para los cálculos basados en el ámbito de evento, sesión o persona.

+++


<!-- MERGE FIELDS -->

### Combinar campos {#merge}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_mergefields"
>title="Combinar campos"
>abstract="Esta función proporciona la capacidad de tomar valores de dos campos diferentes e incluir sus valores respectivos en una sola dimensión. La regla comprueba primero si se ha establecido el primer valor. Si no, utilizará el segundo valor y así sucesivamente."

<!-- markdownlint-enable MD034 -->


Combina valores de dos campos diferentes en un nuevo campo derivado.

+++ Detalles

## Especificación {#merge-fields-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Límite | Output |
|---|---|---|---|---|
| <ul><li>Cadena</li><li>Numéricos</li><li>Fecha</li></ul> | <ul><li>[!UICONTROL Campo]:</li><ul><li>Reglas</li><li>Campos estándar</li><li>Campos</li></ul> | <p>N/A</p> | <p>5 funciones por campo derivado</p> | <p>Nuevo campo derivado</p> |

{style="table-layout:auto"}

## Caso de uso {#merge-fields-uc}

Desea crear una dimensión compuesta por el campo de nombre de página y el campo de motivo de la llamada con la intención de analizar el recorrido en los distintos canales.

### Datos anteriores {#merge-fields-uc-databefore}

| Nombre de la página | Sesión | Visitantes |
|---|--:|--:|
| página de ayuda | 250 | 200 |
| página principal | 500 | 250 |
| página de detalles del producto | 300 | 200 |

{style="table-layout:auto"}

| Motivo de la llamada | Sesión | Visitantes |
|---|--:|--:|
| preguntas sobre mi pedido | 275 | 250 |
| realizar un cambio en mi pedido | 150 | 145 |
| problema con el pedido | 100 | 95 |

{style="table-layout:auto"}

### Campo derivado {#merge-fields-uc-derivedfield}

Usted define un campo derivado de `Cross Channel Interactions`. La función [!UICONTROL MERGE FIELDS] se usa para definir una regla para combinar los valores del campo [!UICONTROL Nombre de página] y el campo [!UICONTROL Motivo de la llamada] y almacenarlos en el nuevo campo derivado.

![Captura de pantalla de la regla de campos combinados](assets/merge-fields.png)

### Datos después de {#merge-fields-uc-dataafter}

| Interacciones entre canales | Sesiones | Visitantes |
|---|--:|--:|
| página principal | 500 | 250 |
| página de detalles del producto | 300 | 200 |
| preguntas sobre mi pedido | 275 | 250 |
| página de ayuda | 250 | 200 |
| realizar un cambio en mi pedido | 150 | 145 |
| problema con el pedido | 100 | 95 |

{style="table-layout:auto"}

## Más información {#merge-fields-moreinfo}

Debe seleccionar el mismo tipo de campos dentro de una regla de campos combinados. Por ejemplo, si selecciona un campo Fecha, todos los demás campos que desee combinar deben ser campos Fecha.

![Captura de pantalla de restricciones en campos de combinación](assets/merge-fields-constraint.png)

+++


<!-- NEXT OR PREVIOUS -->

### Siguiente o anterior {#next-previous}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_nextprevious"
>title="Siguiente o anterior"
>abstract="Esta función proporciona la capacidad de ver el valor siguiente o anterior recopilado para un campo determinado."

<!-- markdownlint-enable MD034 -->


Toma un campo como entrada y resuelve el valor siguiente o anterior de ese campo dentro del ámbito de la sesión o el uso. Esto solo se aplicará a los campos de tabla Visita y Evento.

+++ Detalles

## Especificación {#prevornext-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Límite | Output |
|---|---|---|---|---|
| <ul><li>Cadena</li><li>Numéricos</li><li>Fecha</li></ul> | <ul><li>[!UICONTROL Campo]:</li><ul><li>Reglas</li><li>Campos estándar</li><li>Campos</li></ul><li>[!UICONTROL Método]:<ul><li>Valor anterior</li><li>Siguiente valor</li></ul></li><li>[!UICONTROL Ámbito]:<ul><li>Persona</li><li>Sesión</li></ul></li><li>[!UICONTROL Índice]:<ul><li>Numéricos</li></ul><li>[!UICONTROL Incluir repeticiones]:<ul><li>Booleano</li></ul></li></ul> | <p>N/A</p> | <p>3 funciones por campo derivado</p> | <p>Nuevo campo derivado</p> |

{style="table-layout:auto"}

## Caso de uso {#prevornext-uc1}

Desea saber cuál es el valor **next** o **previous** de los datos que recibe, teniendo en cuenta los valores repetidos.

### Datos {#prevornext-uc1-databefore}

**Ejemplo 1 - Gestión de repeticiones de inclusión**

| Datos recibidos | Siguiente valor<br/>Session<br/>Index = 1<br/>Incluir repeticiones | Siguiente valor<br/>Session<br/>Index = 1<br/>NO incluir repeticiones | Valor anterior<br/>Session<br/>Index = 1<br/>Incluir repeticiones | Valor anterior<br/>Session<br/>Index = 1<br/>NO incluir repeticiones |
|---|---|---|---|---|
| Creative Cloud | Creative Cloud | búsqueda | *Sin valor* | *Sin valor* |
| Creative Cloud | búsqueda | búsqueda | Creative Cloud | *Sin valor* |
| búsqueda | búsqueda | información del producto | Creative Cloud | Creative Cloud |
| búsqueda | información del producto | información del producto | búsqueda | Creative Cloud |
| información del producto | búsqueda | búsqueda | búsqueda | búsqueda |
| búsqueda | detalles del producto | información del producto | información del producto | información del producto |
| información del producto | búsqueda | búsqueda | búsqueda | búsqueda |
| búsqueda | búsqueda | *Sin valor* | información del producto | información del producto |
| búsqueda | *Sin valor* | *Sin valor* | búsqueda | información del producto |

{style="table-layout:auto"}

**Ejemplo 2 - Gestión de repeticiones de inclusión con valores en blanco en los datos recibidos**

| Datos recibidos | Siguiente valor<br/>Session<br/>Index = 1<br/>Incluir repeticiones | Siguiente valor<br/>Session<br/>Index = 1<br/>NO incluir repeticiones | Valor anterior<br/>Session<br/>Index = 1<br/>Incluir repeticiones | Valor anterior<br/>Session<br/>Index = 1<br/>NO incluir repeticiones |
|---|---|---|---|---|
| Creative Cloud | Creative Cloud | búsqueda | *Sin valor* | *Sin valor* |
| Creative Cloud | Creative Cloud | búsqueda | Creative Cloud | *Sin valor* |
| Creative Cloud | búsqueda | búsqueda | Creative Cloud | *Sin valor* |
| búsqueda | búsqueda | información del producto | Creative Cloud | Creative Cloud |
|   |   |   |   |   |
| búsqueda | búsqueda | información del producto | búsqueda | Creative Cloud |
| búsqueda | información del producto | información del producto | búsqueda | Creative Cloud |
| información del producto | *Sin valor* | *Sin valor* | búsqueda | búsqueda |
|   |   |   |   |   |

{style="table-layout:auto"}

### Campo derivado {#prevnext-uc1-derivedfield}

Usted define un campo derivado `Next Value` o `Previous value`. Utiliza la función [!UICONTROL NEXT OR PREVIOUS] para definir una regla que selecciona el campo [!UICONTROL Datos recibidos], selecciona [!UICONTROL Siguiente valor] o [!UICONTROL Valor anterior] como [!UICONTROL Método], [!UICONTROL Sesión] como Ámbito y establece el valor de [!UICONTROL Índice] como `1`.

![Captura de pantalla de la regla de campos combinados](assets/prevnext-next.png)

## Más información {#prevnext-moreinfo}

Solo puede seleccionar campos que pertenezcan a la tabla Visita o Evento.

[!UICONTROL Repeticiones de inclusión] determina cómo controlar los valores repetidos para la función [!UICONTROL NEXT OR PREVIOUS].

- Incluya looks repetidos y los valores siguientes o anteriores. Si se selecciona [!UICONTROL Incluir repeticiones], se omitirán las repeticiones secuenciales de los valores siguientes o anteriores de la visita actual.

- Las filas sin valores (en blanco) para un campo seleccionado no tendrán valores anteriores o siguientes devueltos como parte de la salida de la función [!UICONTROL NEXT O PREVIOUS].

+++

<!-- REGEX REPLACE -->

### Reemplazo de regex {#regex-replace}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_regexreplace"
>title="Reemplazo de regex"
>abstract="Esta función proporciona la capacidad de extraer partes de una cadena mediante expresiones regulares."

<!-- markdownlint-enable MD034 -->


Reemplaza un valor de un campo mediante una expresión regular en un nuevo campo derivado.

+++ Detalles

## Especificación {#regex-replace-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Límite | Output |
|---|---|---|---|---|
| <ul><li>Cadena</li><li>Numéricos</li></ul> | <ul><li>[!UICONTROL Campo]:</li><ul><li>Reglas</li><li>Campos estándar</li><li>Campos</li></ul></ul><ul><li>[!UICONTROL Regex]:</li><ul><li>Cadena</li></ul></li><li>[!UICONTROL Formato de salida]:<ul><li>Cadena</li></ul></ul><ul><li>Con distinción de mayúsculas y minúsculas</li><ul><li>Booleano</li></ul></li></ul></li> | <p>N/A</p> | <p>1 función por campo derivado</p> | <p>Nuevo campo derivado</p> |

{style="table-layout:auto"}

## Caso de uso {#regex-replace-uc}

Desea obtener una parte de una dirección URL y utilizarla como identificador de página único para analizar el tráfico. Se usa `[^/]+(?=/$|$)` para la expresión regular a fin de capturar el final de la dirección URL y `$1` como patrón de salida.

### Datos anteriores {#regex-replace-uc-databefore}

| URL de la página |
|---|
| `https://business.adobe.com/products/analytics/adobe-analytics-benefits.html` |
| `https://business.adobe.com/products/analytics/adobe-analytics.html` |
| `https://business.adobe.com/products/experience-platform/customer-journey-analytics.html` |
| `https://business.adobe.com/products/experience-platform/adobe-experience-platform.html` |

{style="table-layout:auto"}

### Campo derivado {#regex-replace-uc-derivedfield}

Crea un campo derivado de `Page Identifier`. Utiliza la función [!UICONTROL REGEX REPLACE] para definir una regla que reemplace el valor del campo [!UICONTROL URL de referencia] con un [!UICONTROL Regex] de `[^/]+(?=/$|$)` y [!UICONTROL formato de salida] de `$1`.

![Captura de pantalla de la regla de reemplazo de regex](assets/regex-replace.png)


### Datos después de {#regex-replace-uc-dataafter}

| Identificador de página |
|---|
| adobe-analytics-benefits.html |
| adobe-analytics.html |
| customer-journey-analytics.html |
| adobe-experience-platform.html |

## Más información {#regex-replace-more-info}

Customer Journey Analytics utiliza un subconjunto de la sintaxis regex de Perl. Se admiten las expresiones siguientes:

| Expresión | Descripción |
| --- | --- |
| `a` | Un solo carácter `a`. |
| `a\|b` | Un solo carácter `a` o `b`. |
| `[abc]` | Un solo carácter `a`, `b` o `c`. |
| `[^abc]` | Cualquier carácter individual distinto de `a`, `b` o `c`. |
| `[a-z]` | Cualquier carácter individual del intervalo de `a`-`z`. |
| `[a-zA-Z0-9]` | Cualquier carácter individual del intervalo de `a`-`z`, `A`-`Z` o dígitos de `0`-`9`. |
| `^` | Coincide con el principio de la línea. |
| `$` | Coincide con el final de la línea. |
| `\A` | Inicio de cadena. |
| `\z` | Final de cadena. |
| `.` | Coincide con cualquier carácter. |
| `\s` | Cualquier carácter de espacio en blanco. |
| `\S` | Cualquier carácter que no sea un espacio en blanco. |
| `\d` | Cualquier dígito. |
| `\D` | Cualquier carácter que no sea un dígito. |
| `\w` | Cualquier letra, número o guion bajo. |
| `\W` | Cualquier carácter que no sea de palabra. |
| `\b` | Cualquier límite de palabra. |
| `\B` | Cualquier carácter que no sea un límite de palabra. |
| `\<` | Inicio de la palabra. |
| `\>` | Fin de la palabra. |
| `(...)` | Capturar todo lo incluido. |
| `(?:...)` | Captura sin marca. Evita que se haga referencia a la coincidencia en la cadena de salida. |
| `a?` | Cero o uno de `a`. |
| `a*` | Cero o más de `a`. |
| `a+` | Uno más de los `a`. |
| `a{3}` | Exactamente 3 de `a`. |
| `a{3,}` | 3 o más de `a`. |
| `a{3,6}` | Entre 3 y 6 de `a`. |

Puede utilizar estas secuencias en el [!UICONTROL Formato de salida] cualquier número de veces y en cualquier orden para obtener la salida de cadena deseada.

| Secuencia de marcador de posición de salida | Descripción |
| --- | --- |
| `$&` | Genera lo que coincide con toda la expresión. |
| `$n` | Genera lo que coincidió con la subexpresión nth. Por ejemplo, `$1` genera la primera subexpresión. |
| ``$` `` | Genera el texto entre el final de la última coincidencia encontrada (o el inicio del texto si no se encontró ninguna coincidencia anterior) y el inicio de la coincidencia actual. |
| `$+` | Genera lo que coincidió con la última subexpresión marcada en la expresión regular. |
| `$$` | Genera el carácter de cadena `"$"`. |

{style="table-layout:auto"}

+++

<!-- SPLIT -->

### Split {#split}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_split"
>title="Split"
>abstract="Esta función proporciona la capacidad de dividir un campo en varios campos en función de un delimitador."

<!-- markdownlint-enable MD034 -->


Divide un valor de un campo en un nuevo campo derivado.

+++ Detalles

## Especificación {#split-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Límite | Output |
|---|---|---|---|---|
| <ul><li>Cadena</li><li>Numéricos</li></ul> | <ul><li>[!UICONTROL Campo]:</li><ul><li>Reglas</li><li>Campos estándar</li><li>Campos</li></ul></ul><ul><li>[!UICONTROL Método]:</li><ul><li>Desde la izquierda</li><li>Desde la derecha</li><li>Convertir en matriz</li></ul></li><li>Para el delimitador:<ul><li>Cadena</li></ul><li>Para el índice:<ul><li>Numéricos</li></ul></li> | <p>N/A</p> | <p>2 funciones por campo derivado</p> | <p>Nuevo campo derivado</p> |

{style="table-layout:auto"}

## Caso de uso 1 {#split-uc1}

Las respuestas de la aplicación de voz se recopilan en una lista delimitada en una sola dimensión. Desea que cada valor de la lista sea un valor único en el informe de respuestas.

### Datos anteriores {#split-uc1-databefore}

| Respuestas de aplicación de voz | Eventos |
|---|--:|
| fue genial, hizo perfecto sentido, recomendará a los demás | 1 |
| fue genial, algo confuso, recomendará a otros | 1 |
| no fue genial, muy confuso, no se lo recomendaré a otros | 1 |

{style="table-layout:auto"}

### Campo derivado {#split-u1-derivedfield}

Crea un campo derivado de `Responses`. Utiliza la función [!UICONTROL SPLIT] para definir una regla que use el método [!UICONTROL Convert to array] para convertir los valores del campo [!UICONTROL Respuesta de aplicación de voz] usando `,` como [!UICONTROL Delimitador].

![Captura de pantalla de la regla dividida 1](assets/split-1.png)

### Datos después de {#split-uc1-dataafter}

| Respuestas | Eventos |
|---|--:|
| fue genial | 2 |
| recomendará a otras personas | 2 |
| no fue genial | 1 |
| tenía sentido | 1 |
| algo confuso | 1 |
| muy confuso | 1 |
| no recomendará a otras personas | 1 |

{style="table-layout:auto"}

## Caso de uso 2 {#split-uc2}

Las respuestas de la aplicación de voz se recopilan en una lista delimitada en una sola dimensión. Desea las respuestas del primer valor de la lista a su propia dimensión. Desea colocar el último valor de la lista en su propia dimensión.

### Datos anteriores {#split-uc2-databefore}

| Respuestas | Eventos |
|---|--:|
| fue grandioso, hizo perfecto sentido, recomendará a otros | 1 |
| fue genial, algo confuso, recomendará a otros | 1 |
| no fue genial, muy confuso, no se lo recomendaré a otros | 1 |

{style="table-layout:auto"}

### Campo derivado {#split-u2-derivedfield}

Crea un campo derivado de `First Response`. La función [!UICONTROL SPLIT] se usa para definir una regla que toma el primer valor del campo [!UICONTROL Responses] de la izquierda de la respuesta `,` como delimitador.

![Captura de pantalla de la regla dividida - primer valor](assets/split-2.png)

Cree un campo derivado de `Second Response` para tomar el último valor del campo [!UICONTROL Respuestas] seleccionando Desde la derecha, 1 como Delimitador y 1 como Índice.

![Captura de pantalla de la regla dividida - último valor](assets/split-3.png)

### Datos después de {#split-uc2-dataafter}

| Primera respuesta | Eventos |
|---|--:|
| fue genial | 2 |
| no fue genial | 1 |

{style="table-layout:auto"}

| Segunda respuesta | Eventos |
|---|--:|
| recomendará a otras personas | 2 |
| no recomendará a otras personas | 1 |

{style="table-layout:auto"}

+++

<!-- SUMMARIZE -->

### Resumir {#summarize}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_summarize"
>title="Resumir"
>abstract="Esta función proporciona la capacidad de acumular valores en el nivel de evento, sesión o persona. Según el tipo de campo del campo seleccionado, habrá diferentes opciones disponibles."

<!-- markdownlint-enable MD034 -->


Aplica funciones de tipo agregación a métricas o dimensiones en los niveles de evento, sesión y usuario.

+++ Detalles

## Especificación {#summarize-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Límite | Output |
|---|---|---|---|---|
| <ul><li>Cadena</li><li>Numéricos</li><li>Fecha</li></ul> | <ul><li>Valor<ul><li>Reglas</li><li>Campos estándar</li><li>Campos</li></ul></li><li>Métodos de resumen</li><li>Ámbito<ul><li>Evento</li><li>Sesión</li><li>Persona</li></ul></li></ul> | <ul><li>Numéricos<ul><li>MAX: devuelve el mayor valor de un conjunto de valores</li><li>MIN: devuelve el menor valor de un conjunto de valores</li><li>MEDIANA: devuelve la mediana para un conjunto de valores.</li><li>MEDIA: devuelve el promedio de un conjunto de valores.</li><li>SUM: devuelve la suma de un conjunto de valores.</li><li>COUNT - devuelve el número de valores recibidos</li><li>DISTINCT: devuelve un conjunto de valores distintos</li></ul></li><li>Cadenas<ul><li>DISTINCT: devuelve un conjunto de valores distintos</li><li>COUNT DISTINCT: devuelve el número de valores distintos</li><li>MÁS COMÚN: devuelve el valor de cadena que se recibe con más frecuencia</li><li>MENOS COMÚN: devuelve el valor de cadena que se recibe con menor frecuencia</li><li>PRIMERO: el primer valor recibido; solo aplicable a las tablas de sesión y evento</li><li>LAST: el último valor recibido; solo aplicable a las tablas de sesión y evento</li></ul></li><li>Fechas<ul><li>DISTINCT: devuelve un conjunto de valores distintos</li><li>COUNT DISTINCT: devuelve el número de valores distintos</li><li>MÁS COMÚN: devuelve el valor de cadena que se recibe con más frecuencia</li><li>MENOS COMÚN: devuelve el valor de cadena que se recibe con menor frecuencia</li><li>PRIMERO: el primer valor recibido; solo aplicable a las tablas de sesión y evento</li><li>LAST: el último valor recibido; solo aplicable a las tablas de sesión y evento</li><li>MÁS TEMPRANO: el valor más antiguo recibido (determinado por la hora); solo aplicable a las tablas de sesión y evento</li><li>ÚLTIMA: el último valor recibido (determinado por la hora); solo aplicable a las tablas de sesión y evento</li></ul></li></ul> | 3 funciones por campo derivado | Nuevo campo derivado |

{style="table-layout:auto"}

## Caso de uso {#summarize-uc}

Desea clasificar los ingresos de los productos agregados al carro de compras en tres categorías diferentes: Pequeño, Medium y Grande. Esto le permite analizar e identificar las características de los clientes de alto valor.

### Datos anteriores {#summarize-uc-databefore}

Suposiciones:

- Los ingresos de Agregar al carro de compras se recopilan como un campo numérico.

Escenarios:

- CustomerABC123 agrega 35 $ al carro de compras para ProductABC y, a continuación, agrega por separado ProductDEF al carro de compras por 75 $.
- CustomerDEF456 añade 50 $ al carro de compras para ProductGHI y, a continuación, agrega por separado ProductJKL al carro de compras por 275 $.
- CustomerGHI789 añade 500 $ al carro de compras para ProductMNO.

Lógica:

- Si el total de ingresos de un visitante por adición al carro de compras es inferior a 150 $, establézcalo en Pequeño.
- Si el total de ingresos de un visitante por adición al carro de compras es mayor que 150 dólares, pero menor que 500 dólares, se debe establecer en Medium.
- Si el total de ingresos de un visitante que se agregan al carro de compras es mayor o igual que 500 $, establézcalo en Grande.

Resultados:

- Total de ingresos por adición al carro de compras por 110 $ para CustomerABC123.
- Total de ingresos por adición al carro de compras por 325 $ para CustomerDEF456.
- Total de ingresos por $500 para CustomerGHI789.

### Campo derivado {#summarize-uc-derivedfield}

Crea un campo derivado de `Add To Cart Revenue Size`. Utiliza la función [!UICONTROL SUMMARIZE] y el [!UICONTROL método Sum] [!UICONTROL Summarize] con [!UICONTROL Scope] establecido en [!UICONTROL Person] para sumar los valores del campo [!UICONTROL cart_add]. A continuación, utilice una segunda regla [!UICONTROL CASE WHEN] para dividir el resultado en los tres tamaños de categoría.

![Captura de pantalla de la regla de resumen 1](assets/summarize.png)



### Datos después de {#summarize-uc-dataafter}

| Tamaño de ingresos de añadir al carro | Visitantes |
|---|--:|
| Pequeño | 1 |
| Medio | 1 |
| Grande | 1 |

{style="table-layout:auto"}

## Más información {#summarize-more-info}

Utilice la función Resumir para cálculos basados en eventos, sesiones o personas. Utilice la función [Math](#math) para los cálculos basados en el nivel de visita.

+++

<!-- TRIM -->

### Recortar {#trim}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_trim"
>title="Recortar"
>abstract="Esta función proporciona la capacidad de recortar espacios en blanco o caracteres especiales desde el principio o el final de una cadena. También la capacidad de especificar el número de caracteres que se utilizarán para el valor devuelto, ya sea desde el principio o el final de la cadena."

<!-- markdownlint-enable MD034 -->


Recorta los espacios en blanco, los caracteres especiales o el número de caracteres desde el principio o el final de los valores de campo en un nuevo campo derivado.

+++ Detalles

## Especificación {#trim-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Límite | Output |
|---|---|---|---|---|
| <ul><li>Cadena</li></ul> | <ul><li>[!UICONTROL Campo]<ul><li>Reglas</li><li>Campos estándar</li><li>Campos</li></ul></li><li>Recortar espacios en blanco</li><li>Recortar caracteres especiales<ul><li>Entrada de caracteres especiales</li></ul></li><li>Recortar desde la izquierda<ul><li>Desde <ul><li>Inicio de cadena</li><li>Posición<ul><li>Posición #</li></ul></li><li>Cadena<ul><li>Valor de cadena</li><li>Índice</li><li>Indicador para incluir cadena</li></ul></li></ul></li><li>Hasta<ul><li>Fin de cadena</li><li>Posición<ul><li>Posición #</li></ul></li><li>Cadena<ul><li>Valor de cadena</li><li>Índice</li><li>Indicador para incluir cadena</li></ul></li><li>Longitud</li></ul></li></ul></li><li>Recortar desde la derecha<ul><li>Desde <ul><li>Fin de cadena</li><li>Posición<ul><li>Posición #</li></ul></li><li>Cadena<ul><li>Valor de cadena</li><li>Índice</li><li>Indicador para incluir cadena</li></ul></li></ul></li><li>Hasta<ul><li>Inicio de cadena</li><li>Posición<ul><li>Posición #</li></ul></li><li>Cadena<ul><li>Valor de cadena</li><li>Índice</li><li>Indicador para incluir cadena</li></ul></li><li>Longitud</li></ul></li></ul></li></ul> | <p>N/A</p> | <p>1 función por campo derivado</p> | <p>Nuevo campo derivado</p> |


## Caso de uso 1 {#trim-uc1}

Los datos del producto se recopilan, pero esos datos contienen caracteres de espacio en blanco ocultos que fragmentan los informes. Desea recortar fácilmente cualquier espacio en blanco en exceso

### Datos anteriores {#trim-uc1-databefore}

| ID del producto | Eventos |
|---|--:|
| `"prod12356 "` | 1 |
| `"prod12356"` | 1 |
| `" prod12356"` | 1 |

{style="table-layout:auto"}

### Campo derivado {#trim-u1-derivedfield}

Crea un campo derivado de `Product Identifier`. Utiliza la función [!UICONTROL TRIM] para definir una regla para **[!UICONTROL Recortar espacio en blanco]** desde el campo **[!UICONTROL ID del producto]**.

![Captura de pantalla de la regla dividida 1](assets/trim-1.png)

### Datos después de {#trim-uc1-dataafter}

| Identificador de producto | Eventos |
|---|--:|
| `"prod12356"` | 3 |

{style="table-layout:auto"}

## Caso de uso 2 {#trim-uc2}

Los datos sobre los nombres de páginas recopilados incluyen algunos caracteres especiales erróneos al final del nombre de página que deben eliminarse.

### Datos anteriores {#trim-uc2-databefore}

| Nombre | Eventos |
|---|--:|
| página principal# | 1 |
| ¿página principal? | 1 |
| página principal% | 1 |
| página principal&amp; | 1 |
| página principal/ | 1 |

{style="table-layout:auto"}

### Campo derivado {#trim-u2-derivedfield}

Crea un campo derivado de `Page Name`. Utiliza la función [!UICONTROL TRIM] para definir una regla para [!UICONTROL Recortar caracteres especiales] del campo [!UICONTROL Nombre] con los [!UICONTROL caracteres especiales] `#?%&/`.

![Captura de pantalla de la regla dividida - primer valor](assets/trim-2.png)

### Datos después de {#trim-uc2-dataafter}

| Nombre de la página | Eventos |
|---|--:|
| página principal | 5 |

{style="table-layout:auto"}


## Caso de uso 3 {#trim-uc3}

Los datos se recopilan, incluido un ID de tienda. StoreID contiene el código de estado de EE. UU. abreviado como los dos primeros caracteres. Sólo desea utilizar ese código de estado en los informes.

### Datos anteriores {#trim-uc3-databefore}

| storeID | Eventos |
|---|--:|
| CA293842 | 1 |
| CA423402 | 1 |
| UT123418 | 1 |
| UT189021 | 1 |
| ID028930 | 1 |
| O234223 | 1 |
| NV22342 | 1 |

{style="table-layout:auto"}

### Campo derivado {#trim-u3-derivedfield}

Crea un campo derivado de `Store Identifier`. Utiliza la función [!UICONTROL TRIM] para definir una regla para [!UICONTROL Truncar desde el lado derecho] del campo [!UICONTROL storeID] desde el final de la cadena a la posición `3`.

![Captura de pantalla de la regla dividida - primer valor](assets/trim-3.png)

### Datos después de {#trim-uc3-dataafter}

| Identificador de tienda | Eventos |
|---|--:|
| CA | 2 |
| UT | 2 |
| ID | 1 |
| O BIEN | 1 |
| NV | 1 |

{style="table-layout:auto"}
+++


<!-- URL PARSE -->

### Análisis de URL {#urlparse}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_urlparse"
>title="Análisis de URL"
>abstract="Esta función proporciona la capacidad de analizar diferentes partes de una URL, incluidos el host, la ruta o los parámetros de consulta."

<!-- markdownlint-enable MD034 -->


Analiza diferentes partes de una dirección URL, incluidos el protocolo, el host, la ruta de acceso o los parámetros de consulta.

+++ Detalles

## Especificaciones {#urlparse-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Límite | Output |
|---|---|---|---|---|
| <ul><li>Cadena</li></ul> | <ul><li>[!UICONTROL Campo]:</li><ul><li>Reglas</li><li>Campos estándar</li><li>Campos</li></ul><li>[!UICONTROL Opción]:<ul><li>[!UICONTROL Obtener protocolo]</li><li>[!UICONTROL Obtener host]</li><li>[!UICONTROL Obtener ruta]</li><li>[!UICONTROL Obtener valor de cadena de consulta]<ul><li>[!UICONTROL Parámetro de consulta]:<ul><li>Cadena</li></ul></li></ul></li><li>[!UICONTROL Obtener valor hash]</li></ul></li></ul></li></ul> | <p>N/A</p> | <p>5 funciones por campo derivado</p> | <p>Nuevo campo derivado</p> |

{style="table-layout:auto"}


## Caso de uso 1 {#urlparse-uc1}

Solo desea utilizar el dominio de referencia de la dirección URL de referencia como parte del conjunto de reglas de un canal de marketing.

### Datos anteriores {#urlparse-uc1-databefore}

| [!DNL Referring URL] |
|----|
| `https://www.google.com/` |
| `https://duckduckgo.com/` |
| `https://t.co/` |
| `https://l.facebook.com/` |

{style="table-layout:auto"}

### Campo derivado {#urlparse-uc1-derivedfield}

Usted define un campo derivado de `Referring Domain`. La función [!UICONTROL URL PARSE] se usa para definir una regla para recuperar el host del campo [!UICONTROL URL de referencia] y almacenarla en el nuevo campo derivado.

![Captura de pantalla de la regla de análisis de URL 1](assets/url-parse-1.png)

### Datos después de {#urlparse-uc1-dataafter}

| [!DNL Referrer Domain] |
|----|
| [!DNL www.google.com] |
| [!DNL duckduckgo.com] |
| [!DNL t.co] |
| [!DNL l.facebook.com] |

{style="table-layout:auto"}


## Caso de uso 2 {#urlparse-uc2}

Desea usar el valor del parámetro `cid` de una cadena de consulta en un [!DNL Page URL] como parte del resultado de un informe de código de seguimiento derivado.

### Datos anteriores {#urlparse-uc2-databefore}

| [!DNL Page URL] |
|----|
| `https://www.adobe.com/?cid=abc123` |
| `https://www.adobe.com/?em=email1234&cid=def123` |
| `https://www.adobe.com/landingpage?querystring1=test&test2=1234&cid=xyz123` |

{style="table-layout:auto"}

### Campo derivado {#urlparse-uc2-derivedfield}

Usted define un campo derivado de `Query String CID`. La función [!UICONTROL URL PARSE] se usa para definir una regla que recupere el valor del parámetro de cadena de consulta en el campo [!UICONTROL Page URL], especificando `cid` como parámetro de consulta. El valor de salida se almacena en el nuevo campo derivado.

![Captura de pantalla de la regla de análisis de URL 2](assets/url-parse-2.png)

### Datos después de {#urlparse-uc2-dataafter}

| [!DNL Query String CID] |
|----|
| [!DNL abc123] |
| [!DNL def123] |
| [!DNL xyz123] |

{style="table-layout:auto"}

+++

## Limitaciones

Las siguientes limitaciones se aplican a la funcionalidad de campo Derivado en general:

- Puede utilizar un máximo de diez campos de esquema diferentes (sin incluir los campos estándar) al definir reglas para un campo derivado.
   - De este máximo de diez campos de esquema diferentes, solo se permite un máximo de tres campos de esquema de búsqueda o de perfil.
- Puede tener un máximo de 100 campos derivados por conexión de Customer Journey Analytics.


### Resumen de las limitaciones de funciones

| Función | Limitaciones |
|---|---|
| <p>Caso de que</p> | <ul><li>5 Caso Cuando las funciones por campo derivado</li><li>200 [operadores](#operators) por campo derivado</li></ul> |
| <p>Clasificar</p> | <ul><li>5 Clasificar funciones por campo derivado</li><li>200 [operadores](#operators) por campo derivado</li></ul> |
| <p>Concatenar</p> | <ul><li>2 Concatenar funciones por campo derivado</li></ul> |
| <p>Deduplicar</p> | <ul><li>5 Funciones de deduplicación por campo derivado</li></ul> |
| <p>Buscar y reemplazar</p> | <ul><li>2 Funciones Buscar y reemplazar por campo derivado</li></ul> |
| <p>Búsqueda</p> | <ul><li>5 Funciones de búsqueda por campo derivado</li></ul> |
| <p>Minúsculas</p> | <ul><li>2 Funciones en minúsculas por campo derivado</li></ul> |
| <p>Math</p> | <ul><li>25 operaciones por campo derivado</li><li>5 funciones matemáticas por campo derivado</li></ul> |
| <p>Combinar campos</p> | <ul><li>2 funciones Combinar campos por campo derivado</li></ul> |
| <p>Siguiente o anterior</p> | <ul><li>3 Funciones Siguiente o Anterior por campo derivado</li></ul> |
| <p>Reemplazo de regex</p> | <ul><li>1 función Regex Replace por campo derivado</li></ul> |
| <p>Split</p> | <ul><li>2 Funciones divididas por campo derivado</li></ul> |
| <p>Resumir</p> | <ul><li>3 Funciones de resumen por campo derivado</li></ul> |
| <p>Recortar</p> | <ul><li>1 función Recortar por campo derivado</li></ul> |
| <p>Análisis de URL</p> | <ul><li>5 funciones de análisis de URL por campo derivado</li></ul> |

{style="table-layout:auto"}

### Operadores

Un operador en una construcción If o Else If dentro de una función Case When es la combinación de un criterio con un valor **one**. Cada valor adicional del criterio se suma al número de operadores.

Por ejemplo, la condición siguiente utiliza 13 operadores.

![Operadores de muestra](assets/operators-sample.png)

Un operador en la función Classify es una sola entrada para [!UICONTROL When value equal Original value] [!UICONTROL Reemplazar valor por New value].

Por ejemplo, la regla Classify a continuación utiliza 3 operadores.

![Captura de pantalla de la regla de clasificación 1](assets/classify-1.png)


## Más información {#trim-more-info}

[`Trim`](#trim) y [`Lowercase`](#lowercase) son características que ya están disponibles en la configuración de componentes de [Vistas de datos](../component-settings/overview.md). El uso de campos derivados permite combinar estas funciones para realizar una transformación de datos más compleja directamente en Customer Journey Analytics. Por ejemplo, puede usar `Lowercase` para quitar la distinción entre mayúsculas y minúsculas en un campo de evento y, a continuación, usar [`Lookup`](#lookup) para hacer coincidir el nuevo campo en minúsculas con un conjunto de datos de búsqueda que solo tenga claves en minúsculas. O puede usar `Trim` para quitar caracteres antes de configurar `Lookup` en el nuevo campo.

La compatibilidad con los campos de búsqueda y perfil en los campos derivados permite transformar los datos en función de búsquedas de eventos y atributos de perfil. Esto puede resultar especialmente útil en escenarios B2B con datos de nivel de cuenta en conjuntos de datos de perfil o búsqueda. Además, esta compatibilidad es útil para manipular los datos en campos comunes a partir de datos de búsqueda (como información de campaña y tipo de oferta) o de datos de perfil (como nivel de miembro y tipo de cuenta).

>[!MORELIKETHIS]
>
>- [Blog: Aprovechando al máximo sus datos: un marco para usar campos derivados en Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/making-the-most-of-your-data-a-framework-for-using-derived/ba-p/601670)
>- [Blog: Casos de uso de campos derivados para Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/derived-fields-use-cases-for-customer-journey-analytics/ba-p/601679)
>- [Blog: Mejoras en los campos derivados de Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/adobe-customer-journey-analytics-derived-fields-enhancements/ba-p/697808)

