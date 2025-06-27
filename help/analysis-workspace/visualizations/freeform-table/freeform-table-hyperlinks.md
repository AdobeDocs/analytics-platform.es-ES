---
title: Creación De Hipervínculos Para Dimensiones En Una Tabla De Forma Libre
description: Obtenga información sobre cómo crear hipervínculos para elementos de dimensión en una tabla de forma libre en Analysis Workspace.
feature: Visualizations
role: User
exl-id: 24fc2d24-b8c2-4664-8b9c-beda284f9033
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '1605'
ht-degree: 97%

---

# Crear hipervínculos

Puede crear hipervínculos para elementos de dimensión a fin de que se pueda hacer clic en ellos dentro de una tabla de forma libre en Analysis Workspace.

Esta funcionalidad es especialmente útil al crear hipervínculos para los siguientes tipos de elementos de dimensión:

* Elementos de dimensión que tienen valores de URL (por ejemplo, una dimensión URL de página).

* Elementos de dimensión que contienen desgloses con valores de URL (por ejemplo, una dimensión Nombre de página que tiene un desglose de una dimensión URL de página).

* Elementos de dimensión o desgloses que tienen valores que forman parte de una dirección URL (por ejemplo, una dimensión Nombre de página que forma parte de una dirección URL).


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Crear hipervínculos en una tabla de forma libre](https://video.tv.adobe.com/v/3430411/?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


## Crear hipervínculo

Tenga en cuenta lo siguiente al crear hipervínculos para uno o varios elementos de dimensión:

* Los hipervínculos que cree se almacenarán en la tabla de forma libre del proyecto de Analysis Workspace. Los hipervínculos no persisten cuando se utilizan los mismos elementos de dimensión o dimensión en otra tabla o proyecto.

* Si cambia la vista de datos de la tabla de forma libre, cualquier hipervínculo que se haya creado para dimensiones o elementos de dimensión en la tabla seguirá disponible. Esta funcionalidad supone que la dimensión sigue existiendo en la vista de datos.

* No se comprueba la validez de las direcciones URL al crear el hipervínculo. Si

   * crear un hipervínculo con una dirección URL no válida, o
   * crear un hipervínculo que haga referencia a un elemento de dimensión que no tiene un valor de dirección URL (ya sea haciendo referencia al elemento de dimensión directamente o utilizando las variables `$value` o `$breakdown`),

  a continuación, los usuarios que hacen clic en el hipervínculo ven un mensaje de error que indica que la dirección URL no es válida.

* Los hipervínculos creados para un solo elemento de dimensión anulan los hipervínculos creados en la dimensión.

* Los hipervínculos no funcionan en [archivos PDF descargados](/help/analysis-workspace/export/download-send.md).

Para crear hipervínculos para uno o varios elementos de dimensión:

1. En una tabla de forma libre de Analysis Workspace, realice una de las siguientes acciones:

   * **Crear un hipervínculo para un solo elemento de dimensión:** haga clic con el botón secundario en el elemento de dimensión de la tabla para la que desea crear el hipervínculo y, a continuación, seleccione [!UICONTROL **Crear hipervínculo**].

      1. Abra el menú contextual del elemento de dimensión.
      1. Seleccione [!UICONTROL **Crear hipervínculo**] en el menú contextual.

         Se muestra el cuadro de diálogo [!UICONTROL **Crear hipervínculo**]. El nombre del elemento de dimensión para el que está creando un hipervínculo se muestra en el cuadro de diálogo.

         ![Crear hipervínculo para un solo cuadro de diálogo de elemento](assets/hyperlink-dialog-single.png)

   * **Crear hipervínculos para todos los elementos de dimensión de una columna de dimensión:** haga clic con el botón secundario en el nombre de dimensión en el encabezado de columna de dimensión y, a continuación, seleccione [!UICONTROL **Crear hipervínculos para todos los elementos de dimensión**].

      1. Abra el menú contextual desde el encabezado de la columna de dimensión.
      1. Seleccione [!UICONTROL **Crear hipervínculo para todos los elementos de dimensión**] del menú contextual.

         <!-- Do we really need a screenshot ![Create hyperlink for a dimension](assets/hyperlink-multiple-add.png) -->

         Se muestra el cuadro de diálogo [!UICONTROL **Crear hipervínculos para todos los elementos de dimensión**]. El nombre de la dimensión para la que está creando hipervínculos se muestra en el cuadro de diálogo.

         ![Cuadro de diálogo Crear hipervínculos](assets/hyperlink-dialog-multiple.png)

1. Elija entre las siguientes opciones:

   * [!UICONTROL **Use el valor del elemento de dimensión como la dirección URL**]: elija esta opción para los elementos de dimensión que tengan valores de dirección URL, como una dimensión de dirección URL de página.

     Por ejemplo, si utiliza una dimensión URL de página en la que el valor de cada elemento de dimensión es una URL, al seleccionar esta opción se crea un hipervínculo a la URL.

   * [!UICONTROL **Crear una dirección URL personalizada**]: especifique una dirección URL personalizada estática o dinámica. Elija esta opción para crear hipervínculos para elementos de dimensión que no tienen valores de URL.

     Por ejemplo: está utilizando una dimensión Nombre de página en la que el valor de cada elemento de dimensión es el nombre de una página (y no una dirección URL completa). A continuación, seleccione esta opción para especificar un hipervínculo para utilizarlo como vínculo para el elemento de dimensión.

     Si desea crear direcciones URL dinámicas para varios elementos de dimensión, puede utilizar las variables `$value` y `$breakdown` en la dirección URL personalizada. Consulte la siguiente tabla para obtener más información.

     Para crear una dirección URL personalizada, especifique la siguiente información:

     | Campo | Descripción |
     |---------|----------|
     | [!UICONTROL **URL personalizada**] | Especifique una dirección URL personalizada que desee usar para los hipervínculos. Las direcciones URL deben introducirse como direcciones URL completas. Por ejemplo: <https://www.example.com><p>La dirección URL personalizada que cree puede ser estática o dinámica:</p> <ul><li>**Direcciones URL estáticas:** puede especificar una dirección URL estática para un solo elemento de dimensión o para todos los elementos de dimensión cuando desee que los elementos vayan todos a la misma dirección URL. Por ejemplo: `https://wiki.internal.company_name/page_name#item_definition`</p></li><li>**Direcciones URL dinámicas:** puede crear una dirección URL dinámica si desea crear hipervínculos únicos para varios elementos de dimensión o para todos los elementos de dimensión de una columna de dimensión.<p>Para que las direcciones URL personalizadas sean dinámicas, debe incluir una variable en la dirección URL para cambiar la dirección URL en función del valor de la dimensión o del valor de la dimensión de desglose.</p><p>Al utilizar variables, los elementos de dimensión que contengan caracteres no válidos en las direcciones URL (como espacios) se codifican con URL.</p><p>Las siguientes variables están disponibles: (**Nota**: aunque estas variables se pueden usar en la misma dirección URL, es más habitual usarlas por separado.)</p> <ul><li>**`$value`:** le permite insertar el valor del elemento de dimensión en la dirección URL especificada. <p>Supongamos que desea crear hipervínculos para todos los elementos de dimensión Nombre de página en una tabla de forma libre, donde el valor de cada elemento de dimensión forma parte de la dirección URL de una página web. En este caso, puede construir una sola dirección URL personalizada que se ajuste dinámicamente a cada elemento de dimensión. <br/>Por ejemplo: `https://company-name.com/browse/product#\$value`</p><p>Cuando esta dirección URL personalizada se aplica a los elementos de dimensión Nombre de página cuyos valores son &quot;ProductoY&quot; y &quot;ProductoZ&quot;, los hipervínculos generados tienen este aspecto: <br/>`https://company-name.com/browse/product#ProductY` y <br/>`https://company-name.com/browse/product#ProductZ` </p><p>![usar valores en hipervínculos](assets/table-hyperlinks-vaule.png)</p><p>**Sugerencia**: añadir solamente la variable `$value` al campo de dirección URL personalizada es lo mismo que seleccionar la opción [!UICONTROL **Utilizar el valor del elemento de dimensión**] cuando se crea la dirección URL.</p></li><li>**`$breakdown`:** le permite insertar el valor del elemento de dimensión de desglose en la dirección URL especificada. Con `$breakdown`, puede utilizar una dimensión con un nombre descriptivo en el informe (como una dimensión Nombre de producto). Y generar un hipervínculo basado en una dimensión de desglose que podría ser menos fácil de usar (como una dimensión de ID de producto o URL de página).<p>Cuando se hace referencia a una dimensión de desglose, es más habitual tener un solo elemento de desglose para un elemento de dimensión determinado. Si hay varios elementos de desglose para un elemento de dimensión determinado, el valor del primer elemento de desglose se utiliza en la dirección URL. Si no se muestra ningún elemento de desglose, la URL no es válida. A los elementos de desglose se les aplica el mismo orden de clasificación que a la tabla.</p><p>Especifique la dimensión de desglose en el campo [!UICONTROL **Dimensión de desglose**] que aparece a continuación.</p> <p>Considere el ejemplo de escenario que se ha descrito para el campo [!UICONTROL **Dimensión de desglose**] que aparece a continuación.</p></li></ul> |
     | [!UICONTROL **Dimensión de desglose (opcional)**] | Empiece escribiendo el nombre de la dimensión de desglose que desea utilizar y, a continuación, selecciónela en el menú desplegable. <p>Si selecciona una dimensión de desglose en este campo, debe hacer referencia a ella utilizando la variable `$breakdown` en la dirección URL que especifique en el campo [!UICONTROL **URL personalizada**].</p><p>Supongamos que desea crear hipervínculos para todos los elementos de dimensión Nombre de producto en una tabla de forma libre. Cada elemento de dimensión Nombre de producto contiene un desglose de una dimensión de ID de producto.</p></p>En este caso, puede crear hipervínculos para cada dimensión Nombre de producto que dirija a los usuarios a la página de producto mediante el valor de la dimensión de desglose de ID de producto. </p><p>Añada la variable `$breakdown` al final de la dirección URL personalizada que especifique en el campo [!UICONTROL **Dirección URL personalizada**]. Por ejemplo:</p><p>`https://company-name.com/browse/product/$breakdown`</p>Cuando esta dirección URL personalizada se aplica a los elementos de dimensión Nombre de producto (que tienen elementos de dimensión de desglose cuyos valores son &quot;ProductoY&quot; y &quot;ProductoZ&quot;), los hipervínculos generados tienen el siguiente aspecto:<br/>`https://company-name.com/browse/product/ProductY` y <br/>`https://company-name.com/browse/product/ProductZ`</p><p>A continuación, seleccione la dimensión de ID de producto en el campo [!UICONTROL **Dimensión de desglose**] </p><p>![usar desgloses en hipervínculos](assets/table-hyperlinks-breakdown.png)</p> |

1. Seleccione [!UICONTROL **Crear**].

   Los usuarios que ven la tabla de forma libre ven los elementos de dimensión con hipervínculos. Al hacer clic en un elemento de dimensión, los usuarios se dirigen a las páginas hipervinculadas en una pestaña del explorador independiente.

   <!-- add screenshot of a table with hyperlinks.-->

1. [Guarde el proyecto](/help/analysis-workspace/build-workspace-project/save-projects.md) para guardar los cambios.

## Edición de hipervínculos

Puede editar hipervínculos que se hayan creado en dimensiones o elementos de dimensión en una tabla de forma libre.

1. En una tabla de forma libre de Analysis Workspace, realice una de las siguientes acciones:

   * **Edite un hipervínculo para un solo elemento de dimensión:**

      1. Abra el menú contextual del elemento de dimensión.
      1. Seleccione [!UICONTROL **Editar hipervínculo**] en el menú contextual.

     <!-- Do we really need a screenshot? ![Edit hyperlink for a single dimension item](assets/hyperlink-single-edit.png)-->

   * **Edite hipervínculos para todos los elementos de dimensión de una columna de dimensión:**

      1. Abra el menú contextual desde el encabezado de la columna de dimensión.
      1. Seleccione **[!UICONTROL Editar hipervínculo para todos los elementos de dimensión]** en el menú contextual.

     <!-- Do we really need a screenshot? ![Edit hyperlink for a dimension](assets/hyperlink-dimension-edit.png)-->

1. Seleccione [!UICONTROL **Editar hipervínculos para todos los elementos de dimensión**] en el menú del botón derecho.

   Se muestra el cuadro de diálogo [!UICONTROL **Editar hipervínculos para elementos de dimensión**].

1. Para obtener información sobre las opciones de configuración para editar el hipervínculo, consulte el paso 3 de la sección anterior [Crear hipervínculos para uno o más elementos de dimensión](#create-hyperlinks-for-one-or-more-dimension-items) y, a continuación, seleccione [!UICONTROL **Aplicar**] cuando haya terminado con las actualizaciones.

1. [Guarde el proyecto](/help/analysis-workspace/build-workspace-project/save-projects.md) para guardar los cambios.

## Quitar hipervínculos

Puede quitar los hipervínculos que se han creado para los elementos de dimensión en una tabla de forma libre.

>[!NOTE]
>
>En una tabla de forma libre, si elimina una dimensión que contiene hipervínculos, estos no se mantienen si vuelve a añadir la misma dimensión a la tabla de forma libre.

Para quitar los hipervínculos de los elementos de dimensión:

1. En una tabla de forma libre de Analysis Workspace, realice una de las siguientes acciones:

   * **Quite un hipervínculo de un solo elemento de dimensión:**

      1. Abra el menú contextual del elemento de dimensión.
      1. Seleccione [!UICONTROL **Quitar hipervínculo**] en el menú contextual.
         <!-- Do we really need a screenshot? ![Remove hyperlink from a single dimension item](assets/hyperlink-single-remove.png)-->

   * **Quitar hipervínculos de todos los elementos de dimensión de una columna de dimensión:**

      1. Abra el menú contextual desde el encabezado de la columna de dimensión.
      1. Seleccione **[!UICONTROL Quitar hipervínculo para todos los elementos de dimensión]** en el menú contextual.

     <!-- Do we really need a screenshot? [Remove hyperlink from a dimension](assets/hyperlink-dimension-remove.png)-->



   El hipervínculo se quita del elemento de dimensión individual si ha seleccionado un solo elemento de dimensión. O de todos los elementos de dimensión si seleccionó el nombre de la dimensión en el encabezado de la columna de dimensión.

1. [Guarde el proyecto](/help/analysis-workspace/build-workspace-project/save-projects.md) para guardar los cambios.
