---
title: Campos derivados
description: Un campo derivado especifica la manipulación en el tiempo del informe de campos de esquema o componentes estándar a través de un conjunto de funciones disponibles y plantillas de función.
solution: Customer Journey Analytics
feature: Data Views
hide: true
hidefromtoc: true
exl-id: 1ba38aa6-7db4-47f8-ad3b-c5678e5a5974
source-git-commit: b7338c66ba3f78bd082e6d8da43b91b5517f48ac
workflow-type: tm+mt
source-wordcount: '3265'
ht-degree: 9%

---

# Campos derivados

{{release-limited-testing}}

Los campos derivados son un aspecto importante de la funcionalidad de informes en tiempo real en Customer Journey Analytics (CJA). Un campo derivado permite definir manipulaciones de datos (a menudo complejas) sobre la marcha, mediante un generador de reglas personalizable. A continuación, puede utilizar ese campo derivado como componente (métrica o dimensión) en [Espacio de trabajo](../../analysis-workspace/home.md) o incluso definir como un componente en [Vista de datos](../data-views.md).

Los campos derivados pueden ahorrar una gran cantidad de tiempo y esfuerzo, en comparación con la transformación o manipulación de los datos en otras ubicaciones fuera de CJA. Como [Preparación de datos](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=es), [Distiller de datos](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html?lang=en), o dentro de sus propios procesos de carga de transformación de extracción (ETL)/transformación de carga de extracción (ELT).

Los campos derivados se definen dentro de [Vistas de datos](../data-views.md), se basan en un conjunto de funciones definidas como reglas y se aplican a los campos estándar o de esquema disponibles.

Los casos de uso de ejemplo son:

- Defina un campo Nombre de página derivado que corrija los valores de nombre de página recopilados incorrectamente para corregir los valores de nombre de página.

- Defina un campo Canal de marketing derivado que determine el canal de marketing adecuado en función de una o más condiciones (por ejemplo, parámetro de URL, dirección URL de página o nombre de página).

## Interfaz de campo derivada

Cuando se crea o edita un campo derivado, se utiliza la interfaz de campo derivada.

![Cuadro de diálogo de campo derivado](assets/derived-field-dialog.png)


|  | Nombre | Descripción |
|---------|----------|--------|
| 1 | **Selector** | Utilice el área del selector para seleccionar, arrastrar y soltar el ![Función](assets/Smock_Function_18_N.svg) función,![Icono de plantilla de función](assets/Smock_FileTemplate_18_N.svg) plantilla de función,![Icono de campo Esquema](assets/Smock_Folder_18_N.svg) campo de esquema, o![Icono de campo estándar](assets/Smock_DragHandle_18_N.svg)campo estándar en el generador de reglas. <br/>Utilice la lista desplegable para seleccionar entre [!UICONTROL Funciones], [!UICONTROL Plantillas de funciones], [!UICONTROL Campos de esquema]y [!UICONTROL Campos estándar].<br/>Puede buscar los campos de función, función, esquema y estándar utilizando la variable ![Icono de búsqueda](assets/Smock_Search_18_N.svg) Cuadro de búsqueda. <br/>Puede filtrar la lista de objetos seleccionada seleccionando ![Icono de filtro](assets/Smock_Filter_18_N.svg) Filtre y especifique los filtros en la [!UICONTROL Filtrar campos por] diálogo. Puede eliminar fácilmente los filtros mediante ![Icono Cerrar](assets/CrossSize75.svg) para cada filtro. |
| 2 | **Generador de reglas** | El campo derivado se genera secuencialmente usando una o más reglas. Una regla es una implementación específica de una función y, por lo tanto, siempre está asociada a una sola función. Para crear una regla, arrastre y suelte una función en el generador de reglas. El tipo de función determina la interfaz de la regla.<br/>Consulte la [Interfaz de regla](#rule-interface) para obtener más información. <br/>Puede insertar una función al principio, al final o entre reglas ya disponibles en el generador de reglas. La última regla del generador de reglas determina el resultado final del campo derivado. |
| 3 | **[!UICONTROL ** Configuración de campos **]** | Puede nombrar y describir el campo derivado e inspeccionar su tipo de campo. |
| 4 | **[!UICONTROL ** Salida final **]** | Esta área muestra una vista previa actualizada sobre la marcha de los valores de salida, basada en los datos de los últimos 30 días y en los cambios realizados en el campo derivado en el generador de reglas. |

{style="table-layout:auto"}

## Asistente de plantilla de campo

Cuando accede a la interfaz de Derived field por primera vez, la variable [!UICONTROL Comience con una plantilla de campo] se muestra.

1. Seleccione la plantilla que mejor describa el tipo de campo que está intentando crear.
2. Seleccione el **[!UICONTROL ** Select **]** para continuar.

El cuadro de diálogo Campo derivado se rellena con reglas (y funciones) necesarias o útiles para el tipo de campo seleccionado. Consulte [Plantillas de funciones](#function-templates) para obtener más información sobre las plantillas disponibles.

## Interfaz de regla

Cuando define una regla en el generador de reglas, utiliza la interfaz de reglas.

![Interfaz de regla](assets/rule-interface.png)

|  | Nombre | Descripción |
|---------|----------|--------|
| A | **Nombre de regla** | De forma predeterminada, el nombre de la regla es **Regla X** (X que hace referencia a un número de secuencia). Para editar el nombre de una regla, seleccione su nombre y escriba el nuevo nombre, por ejemplo `Query Parameter`. |
| B | **Nombre de función** | El nombre de función seleccionado para la regla, por ejemplo [!DNL URL PARSE]. Cuando la función es la última de la secuencia de funciones y determina los valores de salida finales, el nombre de la función va seguido de [!DNL FINAL OUTPUT], por ejemplo [!DNL URL PARSE - FINAL OUTPUT]. <br/>Para mostrar una ventana emergente con más información sobre la función, seleccione ![Icono de ayuda](assets/Smock_HelpOutline_18_N.svg). |
| C | **Descripción de la regla** | Si lo desea, puede agregar una descripción a una regla.<br/>Select ![Más icono](assets/More.svg)y, a continuación, seleccione **[!UICONTROL ** Agregar descripción **]** para agregar una descripción o **[!UICONTROL ** Editar descripción **]** para editar una descripción existente.<br/>Utilice el editor para introducir una descripción. Puede utilizar la barra de herramientas para dar formato al texto (mediante el selector de estilos, negrita, cursiva, subrayado, derecha, izquierda, centrado, color, lista de números, lista de viñetas) y agregar vínculos a información externa. <br/>Para finalizar la edición de la descripción, haga clic fuera del editor. |
| D | **Área de función** | Define la lógica de la función. La interfaz depende del tipo de función. Consulte [Referencia de funciones](#function-reference) sobre información detallada para cada una de las funciones admitidas. |

{style="table-layout:auto"}

## Crear un campo derivado

1. Seleccione una vista de datos existente o cree una vista de datos. Consulte [Vistas de datos](../data-views.md) para obtener más información.

2. Seleccione el **[!UICONTROL ** Componentes **]** de la vista Datos.

3. Select **[!UICONTROL ** Crear campo derivado **]** desde el carril izquierdo.

4. Para definir el campo derivado, utilice la variable [!UICONTROL Crear campo derivado] interfaz. Consulte [Interfaz de campo derivada](#derived-field-interface).

   Para guardar el nuevo campo derivado, seleccione **[!UICONTROL ** Guardar **]**.

5. El nuevo campo derivado se agrega al **[!UICONTROL ** Campos derivados >**]** como parte de **[!UICONTROL ** Campos de esquema **]** en el carril izquierdo de la vista de datos.


## Editar un campo derivado

1. Seleccione una vista de datos existente. Consulte [Vistas de datos](../data-views.md) para obtener más información.

2. Seleccione el **[!UICONTROL ** Componentes **]** de la vista Datos.

3. Select **[!UICONTROL ** Campos de esquema **]** en la ficha [!UICONTROL Conexión] en la parte izquierda.

4. Select **[!UICONTROL ** Campos derivados >**]** contenedor.

5. Pase el ratón sobre el campo derivado que desee editar y seleccione ![Icono Editar](assets/Smock_Edit_18_N.svg).

6. Para editar el campo derivado, utilice el [!UICONTROL Editar campo derivado] interfaz. Consulte [Interfaz de campo derivada](#derived-field-interface).

   - Select **[!UICONTROL ** Guardar **]** para guardar el campo derivado actualizado.

   - Select **[!UICONTROL ** Cancelar **]** para cancelar los cambios realizados en el campo derivado.

   - Select **[!UICONTROL ** Guardar como **]** para guardar el campo derivado como un nuevo campo derivado. El nuevo campo derivado tiene el mismo nombre que el campo derivado original editado con `(copy)` añadida a él.

## Eliminar un campo derivado

1. Seleccione una vista de datos existente. Consulte [Vistas de datos](../data-views.md) para obtener más información.

2. Seleccione el **[!UICONTROL ** Componentes **]** de la vista Datos.

3. Select **[!UICONTROL ** Campos de esquema **]** en [!UICONTROL Conexión] panel.

4. Select **[!UICONTROL ** Campos derivados >**]** contenedor.

5. Pase el ratón sobre el campo derivado que desee eliminar y seleccione ![Icono Editar](assets/Smock_Edit_18_N.svg).

6. En el **[!UICONTROL ** Editar campo derivado **]** , seleccione Eliminar.

   A [!UICONTROL Eliminar componente] le pedirá que confirme la eliminación. Considere cualquier referencia externa que pueda existir al campo derivado fuera de la vista Datos.

   - Select **[!UICONTROL ** Continuar **]** para eliminar el campo derivado.


## Plantillas de funciones

Para crear rápidamente un campo derivado para casos de uso específicos, hay disponibles plantillas de función. Se puede acceder a estas plantillas de función desde el área Selector de la interfaz de campo Derivado o se presentan cuando se utilizan por primera vez en la [!UICONTROL Comience con una plantilla de campo] asistente.


### Canales de marketing

Esta plantilla está configurada para usar la variable [Análisis De Url](#dnl-url-parse) y [Case When](#dnl-case-when) funciona varias veces para obtener los valores adecuados de una dirección URL. A continuación, se aplica lógica a estos valores para asociar la dirección URL a un canal de marketing específico.

+++ Detalles

Para utilizar la plantilla, debe especificar los parámetros correctos para cada función enumerada como parte de las reglas de la plantilla. Consulte [Referencia de funciones](#function-reference) para obtener más información.

![Generador de reglas de plantilla de canal de marketing](assets/marketing-channel-template.png)

+++

<!--

+++ Data clean up template

>[!WARNING]
>
>Could not find any information on this template.
+++

-->

## Referencia de funciones

Para cada función admitida, consulte los detalles siguientes sobre:

- especificaciones:
   - tipo de datos de entrada: tipo de datos admitidos,
   - entrada: valores posibles de entrada,
   - operadores incluidos: operadores admitidos para esta función (si los hay),
   - límite: número máximo de reglas con esta función que puede utilizar en un campo derivado,
   - salida.

- casos de uso, incluidos:
   - datos antes de definir el campo derivado
   - definición del campo derivado
   - datos después de definir el campo derivado

- restricciones (opcional)


<!-- Concatenate -->

### [!DNL Concatenate]

Combina dos o más campos, campos derivados o valores introducidos por el usuario en un único campo con delimitadores definidos.

+++ Detalles

## Especificaciones {#concatenate-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Límite | Output |
|---|---|---|:--:|---|
| <p>Cadena</p> | <ul><li>Dos o más valores para combinar<ul><li>Campos</li><li>Valor derivado de una regla anterior</li><li>Valor introducido por el usuario</li></ul></li><li>Delimitadores<ul><li>Entrada o selección de un delimitador para cada valor</li></ul></li> </ul> | <p>N/A</p> | <p>2</p> | <p>Nuevo campo derivado</p> |

{style="table-layout:auto"}


## Caso de uso {#concatenate-uc}

Actualmente recopila códigos de origen y de destino de aeropuerto como campos independientes. Le gustaría tomar los dos campos y combinarlos en una sola dimensión separada por un guión (-). Así que puede analizar la combinación de origen y destino para identificar las rutas principales reservadas.

Suposiciones:

- Los valores de origen y destino se recopilan en campos separados en la misma tabla.
- El usuario determina utilizar el delimitador &quot;-&quot; entre los valores.

Imagine que se producen las siguientes reservas:

- El cliente ABC123 registra un vuelo entre Salt Lake City (SLC) y Orlando (MCO)
- El cliente ABC456 registra un vuelo entre Salt Lake City (SLC) y Los Ángeles (LAX)
- El cliente ABC789 registra un vuelo entre Salt Lake City (SLC) y Seattle (SEA)
- El cliente ABC987 registra un vuelo entre Salt Lake City (SLC) y San José (SJO)
- El cliente ABC654 registra un vuelo entre Salt Lake City (SLC) y Orlando (MCO)

El informe deseado debería tener el siguiente aspecto:

| Origen/destino | Registros |
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
| SLC | LAX |
| SLC | SEA |
| SLC | SJO |
| SLC | MCO |

{style="table-layout:auto"}

### Campo derivado {#concatenate-derivedfield}

Puede definir una nueva **[!UICONTROL ** Origen - Destino **]** campo derivado. Utilice la variable **[!UICONTROL CONCATENATE]** para definir una regla para concatenar la variable [!UICONTROL Original] y [!UICONTROL Destino] campos que utilizan la variable `-` [!UICONTROL Delimitador].

![[!DNL Concatenate] regla](assets/concatenate.png)

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

<!-- CASE WHEN -->

### [!DNL Case When]

Aplica condiciones basadas en criterios definidos de uno o varios campos. Estos criterios se utilizan para definir los valores de un nuevo campo derivado, en función de la secuencia de las condiciones.

+++ Detalles

## Especificaciones {#casewhen-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Límite | Output |
|---|---|---|:---:|---|
| <ul><li>Cadena</li><li>Numéricos</li><li>Fecha/Fecha-Hora</li></ul> | <ul><li>Campos de entrada</li><li>Criterios</li></ul> | <p><u>Cadenas</u></p><ul><li>Es igual a</li><li>Es igual a cualquier término</li><li>Contiene la frase</li><li>Contiene cualquier término</li><li>Contiene todos los términos</li><li>Comienza con</li><li>Comienza con cualquier término</li><li>Finaliza con</li><li>Finaliza con cualquier término</li><li>No es igual a</li><li>No coincide con ningún término</li><li>No contiene la frase</li><li>No contiene ningún término</li><li>No contiene todos los términos</li><li>No comienza con</li><li>No comienza con ningún término</li><li>No finaliza con</li><li>No termina con ningún término</li><li>Se ha establecido</li><li>No se ha establecido</li></ul><p><u>Numéricos</u></p><ul><li>Es igual a</li><li>No es igual a</li><li>Es mayor que</li><li>Es mayor que o igual a</li><li>Es menor que</li><li>Es menor que o igual a</li><li>Se ha establecido</li><li>No se ha establecido</li></ul><p><u>Fechas</u></p><ul><li>Es igual a</li><li>No es igual a</li><li>Es posterior a</li><li>Es posterior o igual a</li><li>Es anterior a</li><li>Es anterior o igual a</li><li>Se ha establecido</li><li>No se ha establecido</li></ul> | <p>5</p> | <p>Nuevo campo derivado</p> |

{style="table-layout:auto"}


## Caso de uso 1 {#casewhen-uc1}

Para definir reglas que identifiquen varios canales de marketing, aplique la lógica en cascada para establecer un campo de canal de marketing en el valor correcto:

- Si el referente es de un motor de búsqueda y la página tiene un valor de cadena de consulta donde `cid` contains `ps_`, el canal de marketing debe identificarse como un **Búsqueda de pago**.
- Si el referente es de un motor de búsqueda y la página no tiene la cadena de consulta `cid`, el canal de marketing debe identificarse como un **Búsqueda natural**.
- Si una página tiene un valor de cadena de consulta donde `cid` contains `em_`, el canal de marketing debe identificarse como un **Correo electrónico**.
- Si una página tiene un valor de cadena de consulta donde `cid` contains `ds_`, el canal de marketing debe identificarse como un **Publicidad en pantalla**.
- Si una página tiene un valor de cadena de consulta donde `cid` contains `so_`, el canal de marketing debe identificarse como un **Social de pago**.
- Si el referente procede de un dominio de referencia de twitter.com, facebook.com, linkedin.com o tiktok.com, el canal de marketing debe identificarse como un **Social natural**.
- Si no coincide ninguna de las reglas anteriores, el canal de marketing debe identificarse como **Otro referente**.

Si el sitio recibe los siguientes eventos de ejemplo, que contienen Referente y Dirección URL de la página, estos eventos deben identificarse de la siguiente manera:

| Evento | Remitente del reenvío | URL de la página | Canal de marketing |
|:--:|----|----|----|
| 1 | `https://facebook.com` | `https://site.com/home` | Social natural |
| 2 | `https://abc.com` | `https://site.com/?cid=ds_12345678` | Mostrar |
| 3 |  | `https://site.com/?cid=em_12345678` | Correo electrónico |
| 4 | `https://google.com` | `https://site.com/?cid=ps_abc098765` | Búsqueda de pago |
| 5 | `https://google.com` | `https://site.com/?cid=em_765544332` | Correo electrónico |
| 6 | `https://google.com` |  | Búsqueda natural |

{style="table-layout:auto"}

### Datos anteriores {#casewhen-uc1-databefore}

| Remitente del reenvío | URL de la página |
|----|----|
| `https://facebook.com` | `https://site.com/home` |
| `https://abc.com` | `https://site.com/?cid=ds_12345678` |
|  | `https://site.com/?cid=em_12345678` |
| `https://google.com` | `https://site.com/?cid=ps_abc098765` |
| `https://google.com` | `https://site.com/?cid=em_765544332` |
| `https://google.com` |

{style="table-layout:auto"}

### Campo derivado {#casewhen-uc1-derivedfield}

Puede definir una nueva `Marketing Channel` campo derivado. Utilice la variable **[!UICONTROL CASO CUANDO]** funciones para definir reglas que creen valores para la variable en función de los valores existentes para `Page URL` y `Referring URL` campo .

Tenga en cuenta el uso de la función **[!UICONTROL ** URL PARSE **]** para definir reglas para recuperar los valores de `Page Url` y `Referring Url` antes de que **[!UICONTROL ** CASO CUANDO **]** se aplican.

![[!DNL Case when] regla 1](assets/case-when-1.png)

### Datos después de {#casewhen-uc1-dataafter}

| Canal de marketing |
|----|
| Social natural |
| Mostrar |
| Correo electrónico |
| Búsqueda de pago |
| Correo electrónico |
| Búsqueda natural |

{style="table-layout:auto"}


## Caso de uso 2 {#casewhen-uc2}

Ha recopilado varias variaciones diferentes de búsqueda dentro de la dimensión Métodos de búsqueda de productos . Para comprender el rendimiento general de la búsqueda en comparación con la exploración, debe pasar una buena cantidad de tiempo combinando los resultados manualmente.

El sitio recopila los siguientes valores para la dimensión Métodos de búsqueda de productos . Al final, todos estos valores indican una búsqueda.

| Valor recopilado | Valor real |
|---|---|
| search p13n_no | búsqueda |
| search p13n_yes | búsqueda |
| ajuste de búsqueda p13n_no | búsqueda |
| refinar búsqueda p13n_yes | búsqueda |
| redirección de búsqueda p13n_yes | búsqueda |
| search-redirect | búsqueda |

{style="table-layout:auto"}


### Datos anteriores {#casewhen-uc2-databefore}

| Métodos de búsqueda de productos |
|----|
| search p13_no |
| search p13_yes |
| examinar |
| ajuste de búsqueda p13_no |
| refinar búsqueda p13_yes |
| examinar |
| redirección de búsqueda p13_yes |
| search-redirect |
| examinar |

{style="table-layout:auto"}

### Campo derivado {#casewhen-uc2-derivedfield}

Puede definir una `Product Finding Methods (new)` campo derivado. Cree lo siguiente **[!UICONTROL ** CASO CUANDO **]** reglas en el generador de reglas. Estas reglas aplican lógica a todas las posibles variaciones de las **[!UICONTROL ** Métodos de búsqueda de productos **]** valores de campo para `search` y `browse` usando la variable **[!UICONTROL Contiene la frase]** criterio.

![[!DNL Case When] regla 2](assets/case-when-2.png)

### Datos después de {#casewhen-uc2-dataafter}

| Métodos de búsqueda de productos (nuevo) |
|----|
| búsqueda |
| búsqueda |
| examinar |
| búsqueda |
| búsqueda |
| examinar |
| búsqueda |
| búsqueda |
| examinar |

{style="table-layout:auto"}


## Caso de uso 3 {#casewhen-uc3}

Como compañía de viajes, le gustaría tener una duración de viaje acumulada para viajes reservados, así puede informar sobre las longitudes acumuladas de los viajes.

Suposiciones:

- La organización está recopilando la duración del viaje en un campo numérico.
- Les gustaría agrupar duraciones de 1-3 días en un cubo llamado &quot;viaje corto&quot;
- Les gustaría agrupar duraciones de 4 a 7 días en un cubo llamado &quot;viaje mediano&quot;
- Les gustaría agrupar duraciones de más de 8 días en un cubo llamado &quot;viaje largo&quot;
- Se reservaron 132 viajes durante un día
- Se reservaron 110 viajes durante dos días
- Se reservaron 105 viajes durante 3 días
- Se reservaron 99 viajes durante 4 días
- Se reservaron 92 viajes durante 5 días
- Se reservaron 85 viajes durante 6 días
- Se reservaron 82 viajes durante 7 días
- Se reservaron 78 viajes durante 8 días
- Se reservaron 50 viajes durante 9 días
- Se reservaron 44 viajes durante 10 días
- Se reservaron 38 viajes durante 11 días
- Se reservaron 31 viajes durante 12 días

El informe deseado debería tener el siguiente aspecto:

| Tipo de duración del viaje | Registros |
|----|---:|
| viaje medio | 358 |
| viaje corto | 347 |
| viaje largo | 241 |

{style="table-layout:auto"}

### Datos anteriores {#casewhen-uc3-databefore}

| Duración del viaje |
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

Puede definir una `Trip Duration (bucketed)` campo derivado. Cree lo siguiente **[!UICONTROL ** CASO CUANDO **]** en el generador de reglas. Esta regla aplica lógica para agrupar el antiguo **[!UICONTROL ** Duración del viaje **]** valores de campo en tres valores: `short trip`, `medium  trip`y `long trip`.

![[!DNL Case When] regla 3](assets/case-when-3.png)


### Datos después de {#casewhen-uc3-dataafter}

| Duración del viaje (agrupado) |
|---|
| viaje corto |
| viaje largo |
| viaje corto |
| viaje medio |
| viaje medio |
| viaje largo |
| viaje medio |
| viaje corto |
| viaje corto |
| viaje corto |
| viaje largo |
| viaje largo |


## Restricciones

CJA utiliza una estructura de contenedor anidada, modelada después de Adobe Experience Platform [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es) (Modelo de datos de experiencia). Consulte [Contenedores](../create-dataview.md#containers) y [Contenedores de filtro](../../components/filters/filters-overview.md#filter-containers) para obtener más información en segundo plano. Este modelo de contenedor, aunque flexible por naturaleza, impone algunas restricciones al usar el generador de reglas.

CJA utiliza el siguiente modelo de contenedor predeterminado:

<p align="center">
<img src="./assets/containers.png" width="50%" valign="middle">
</p>



Las siguientes restricciones se aplican y se aplican cuando _seleccionar_ y _configuración_ valores.

|  | Restricciones |
|:---:|----|
| **<span style='color: red'>A</span>** | Valores que _select_ dentro del mismo [!UICONTROL If], [!UICONTROL Else Si] construir (usar [!UICONTROL Y] o [!UICONTROL O]) en una regla debe proceder del mismo contenedor y puede ser de cualquier tipo (cadena ![Cadena](assets/Smock_ABC_18_N.svg), numérico ![Numérico](assets/Smock_123_18_N.svg), etc.). <br/>![Dependencia A](assets/dependency-a.png) |
| **<span style='color: red'>B</span>** | Todos los valores que _set_ en una regla debe ser del mismo contenedor y tener el mismo tipo o un valor derivado del mismo tipo. <br/> ![Dependencia B](assets/dependency-b.png) |
| **<span style='color: blue'>C</span>** | Los valores que _select_ ross [!UICONTROL If], [!UICONTROL Else Si] construcciones en la regla do _not_ deben proceder del mismo contenedor y _not_ deben ser del mismo tipo. <br/> ![Dependencia C](assets/dependency-c.png) |

{style="table-layout:auto"}

+++


<!-- FIND AND REPLACE -->

### [!DNL Find and Replace]

Busca todos los valores de un campo seleccionado y reemplaza esos valores por un valor diferente en un nuevo campo derivado.

+++ Detalles

## Especificaciones {#findreplace-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Límite | Output |
|---|---|---|:---:|---|
| <p>Cadena</p> | <ul><li><span>Criterios de campo &quot;Cuándo reemplazar&quot;</span></li><li><span>Valor de campo &quot;Reemplazar con&quot;</span><ul><li><span>Introducido por el usuario</span></li><li><span>Campo separado</span></li></ul></li></ul> | <p><u>Cadenas</u></p><ul><li>Buscar todo y reemplazar todo</li></ul> | <p>1</p> | <p>Nuevo campo derivado</p> |

{style="table-layout:auto"}


## Caso de uso {#findreplace-uc}

Ha recibido algunos valores mal formados para el informe de canales de marketing externos, por ejemplo `email%20 marketing` en lugar de `email marketing`. Estos valores mal formados fracturan los informes y dificultan la visualización del rendimiento del correo electrónico. Desea reemplazar `email%20marketing` con `email marketing`.

**Informe original**

| Canales de marketing externo | Sesiones |
|---|--:|
| marketing por correo electrónico | 500 |
| correo electrónico %20marketing | 24 |

{style="table-layout:auto"}

**Informe preferido**

| Canales de marketing externo | Sesiones |
|---|--:|
| marketing por correo electrónico | 524 |


### Datos anteriores {#findreplace-uc-databefore}

| Marketing externo |
|----|
| marketing por correo electrónico |
| email%20marketing |
| marketing por correo electrónico |
| marketing por correo electrónico |
| email%20marketing |

{style="table-layout:auto"}

### Campo derivado {#findreplace-uc-derivedfield}

Puede definir una `Email Marketing (updated)` campo derivado. Utilice la variable **[!UICONTROL BUSCAR Y REEMPLAZAR]** para definir una regla para buscar y reemplazar todas las ocurrencias de `email%20marketing` con `email marketing`.

![[!DNL Find and Replace] regla](assets/find-and-replace.png)

### Datos después de {#findreplace-uc-dataafter}

| Marketing externo<br/>(campo derivado) |
|----|
| marketing por correo electrónico |
| marketing por correo electrónico |
| marketing por correo electrónico |
| marketing por correo electrónico |
| marketing por correo electrónico |

{style="table-layout:auto"}

+++


<!-- LOOKUP -->

### [!DNL Lookup]

Define un conjunto de valores de búsqueda que se sustituyen por los valores correspondientes.

+++ Detalles


## Especificaciones {#lookup-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Límite | Output |
|---|---|---|:---:|---|
| <ul><li>Cadena</li><li>Numéricos</li><li>Fecha</li></ul> | <ul><li>Campo único</li><li>Archivo de búsqueda<ul><li>Columna clave</li><li>Nueva columna de campo</li></ul></li></ul> | <p>N/A</p> | <p>5</p> | <p>Nuevo campo derivado</p> |

{style="table-layout:auto"}


## Caso de uso 1 {#lookup-uc1}

Tiene un archivo CSV que incluye una columna clave para `hotelID` y una o más columnas adicionales asociadas al `hotelID`: `city`, `rooms`, `hotel name`.
Está recopilando ID de hotel en una dimensión, pero le gustaría crear una dimensión Nombre de hotel derivada del `hotelID` en el archivo CSV.

**Estructura y contenido del archivo CSV**

| hotelID | city | habitaciones | nombre del hotel |
|---|---|---:|---|
| SLC123 | Salt Lake City | 40 | Centro de SLC |
| LAX342 | Los ángeles | 60 | Aeropuerto de LA |
| SFO456 | San Francisco | 75 | Calle de mercado |

{style="table-layout:auto"}

**Informe actual**

| ID del hotel | Vistas del producto |
|---|---:|
| SLC123 | 200 |
| LX342 | 198 |
| SFO456 | 190 |

{style="table-layout:auto"}


**Informe deseado**

| Nombre del hotel | Vistas del producto |
|----|----:|
| Centro de SLC | 200 |
| Aeropuerto de LA | 198 |
| Calle de mercado | 190 |

{style="table-layout:auto"}

### Datos anteriores {#lookup-uc1-databefore}

| ID del hotel |
|----|
| SLC123 |
| LAX342 |
| SFO456 |

{style="table-layout:auto"}


### Campo derivado {#lookup-uc1-derivedfield}

Puede definir una `Hotel Name` campo derivado. Utilice la variable **[!UICONTROL ** BUSCAR **]** para definir una regla en la que puede buscar valores de la variable **[!UICONTROL ** ID del hotel **]** y reemplace por nuevos valores.

![[!DNL Lookup] regla 1](assets/lookup-1.png)

### Datos después de {#lookup-uc1-dataafter}

| Nombre del hotel |
|----|
| Centro de SLC |
| Aeropuerto de LA |
| Calle de mercado |

{style="table-layout:auto"}


## Caso de uso 2 {#lookup-uc2}

Ha recopilado direcciones URL en lugar del nombre de página descriptivo de varias páginas. Esta colección mixta de valores rompe los informes.

### Datos anteriores {#lookup-uc2-databefore}

| Nombre de la página |
|---|
| Página principal |
| Búsqueda de vuelo |
| `http://www.adobetravel.ca/Hotel-Search` |
| `https://www.adobetravel.com/Package-Search` |
| Ofertas |
| `http://www.adobetravel.ca/user/reviews` |
| `https://www.adobetravel.com.br/Generate-Quote/preview` |

{style="table-layout:auto"}

### Campo derivado {#lookup-uc2-derivedfield}

Puede definir una `Page Name (updated)` campo derivado. Utilice la variable **[!UICONTROL ** BUSCAR **]** para definir una regla en la que puede buscar valores de **[!UICONTROL ** Nombre de la página **]** y reemplace por valores correctos actualizados.

![[!DNL Lookup] regla 2](assets/lookup-2.png)

### Datos después de {#lookup-uc2-dataafter}

| Nombre de página (actualizado) |
|---|
| Página principal |
| Búsqueda de vuelo |
| Búsqueda en el hotel |
| Búsqueda de paquetes |
| Ofertas |
| Reseñas |
| Generar cotización |

+++

<!-- URL PARSE -->

### [!DNL URL Parse]

Analiza diferentes partes de una dirección URL, incluidos los parámetros de protocolo, host, ruta o consulta.

+++ Detalles

## Especificaciones {#urlparse-io}

| Tipo de datos de entrada | Entrada | Operadores incluidos | Límite | Output |
|---|---|---|:---:|---|
| <ul><li>Cadena</li></ul> | <ul><li>Campo único</li><li>Opción de análisis<ul><li>Obtener protocolo</li><li>Obtener host</li><li>Obtener ruta</li><li>Obtener valor de la consulta<ul><li>Parámetro de consulta</li></ul></li><li>Obtener valor de hash</li></ul></li></ul></li></ul> | <p>N/A</p> | <p>5</p> | <p>Nuevo campo derivado</p> |

{style="table-layout:auto"}


## Caso de uso 1 {#urlparse-uc1}

Solo desea utilizar el dominio de referencia de la dirección URL de referencia como parte del conjunto de reglas de un canal de marketing.

### Datos anteriores {#urlparse-uc1-databefore}

| Dirección URL de referencia |
|----|
| `https://www.google.com/` |
| `https://duckduckgo.com/` |
| `https://t.co/` |
| `https://l.facebook.com/` |

{style="table-layout:auto"}

### Campo derivado {#urlparse-uc1-derivedfield}

Puede definir una  `Referring Domain` campo derivado. Utilice la variable **[!UICONTROL ** URL PARSE **]** para definir una regla para recuperar el host de la variable **Dirección URL de referencia** y guardarlo en el nuevo campo derivado.

![[!DNL Url Parse] regla 1](assets/url-parse-1.png)

### Datos después de {#urlparse-uc1-dataafter}

| Dominio de referente |
|----|
| www.google.com |
| duckduckgo.com |
| t.co |
| l.facebook.com |

{style="table-layout:auto"}


## Caso de uso 2 {#urlparse-uc2}

Desea utilizar el valor de la variable `cid` de una cadena de consulta en una URL de página como parte del resultado de un informe de código de seguimiento derivado.

### Datos anteriores {#urlparse-uc2-databefore}

| URL de la página |
|----|
| `https://www.adobe.com/?cid=abc123` |
| `https://www.adobe.com/?em=email1234&cid=def123` |
| `https://www.adobe.com/landingpage?querystring1=test&test2=1234&cid=xyz123` |

{style="table-layout:auto"}

### Campo derivado {#urlparse-uc2-derivedfield}

Puede definir una `Query String CID` campo derivado. Utilice la variable **[!UICONTROL ** URL PARSE **]** para definir una regla para recuperar el valor del parámetro de cadena de consulta en la dirección URL de la página, especificar `cid` como parámetro de consulta. El valor de salida se almacena en el nuevo campo derivado.

![[!DNL Url Parse] regla 2](assets/url-parse-2.png)

### Datos después de {#urlparse-uc2-dataafter}

| CID de cadena de consulta |
|----|
| abc123 |
| def123 |
| xyz123 |

{style="table-layout:auto"}

+++
