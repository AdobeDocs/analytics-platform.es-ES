---
description: Uso de filtros rápidos en Analysis Workspace para Customer Journey Analytics
title: Filtros rápidos
feature: Workspace Basics
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 4bf8c616965718426efe880865acb0e5054b6a31
workflow-type: ht
source-wordcount: '1170'
ht-degree: 100%

---

# Filtros rápidos

Los filtros rápidos le permiten explorar datos rápidamente dentro de un proyecto de Workspace, sin necesidad de crear un filtro en [Generador de filtros](/help/components/filters/create-filters.md).



>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Segmentos rápidos en Analysis Workspace](https://video.tv.adobe.com/v/341466/?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


Si desea utilizar filtros rápidos, tenga en cuenta lo siguiente:

* Los filtros rápidos se crean directamente en un proyecto de Workspace. Como resultado, un filtro rápido se aplica solo al proyecto de Workspace en el que crea el filtro rápido. Los filtros rápidos del proyecto de Workspace no están disponibles en otros proyectos y no se pueden compartir con otros usuarios.
* Solo se pueden especificar tres condiciones como parte de un filtro rápido.
* Los filtros rápidos no admiten contenedores anidados ni condiciones secuenciales.
* Puede editar filtros rápidos dentro de un proyecto compartido de Workspace. Por lo tanto, otros usuarios pueden editar los filtros rápidos de un proyecto de Workspace que haya compartido con estos usuarios.

## Crear

Los filtros rápidos se aplican a los paneles. Puede crear uno o más filtros rápidos para cada panel del proyecto de Workspace. Cualquier usuario de Analysis Workspace puede crea filtros rápidos.

Para crear un filtro rápido:

* Seleccione ![FilterAdd](/help/assets/icons/FilterAdd.svg) en la parte superior del panel. <br/>A continuación, edite directamente el filtro en el [Generador de filtros rápidos](#quick-filter-builder).
* Arrastre un componente desde el panel de componentes hasta la zona de colocación de filtros del encabezado del panel. Una vez colocado, pase el puntero por encima del ratón sobre el filtro y seleccione ![Editar](/help/assets/icons/Edit.svg) para editar el filtro en el [Generador de filtros rápidos](#quick-filter-builder).

Cuando cree un filtro rápido arrastrando y soltando, tenga en cuenta lo siguiente:

* No se admiten todos los tipos de componentes. Las métricas calculadas no son compatibles y solo son compatibles las dimensiones y métricas a partir de las cuales se pueden crear filtros.
* En el caso de los componentes de dimensiones y métricas, el [Generador de filtros rápidos](#quick-filter-builder) crea automáticamente una condición `exists`. Por ejemplo, si arrastra y suelta `City`, se creará la condición `City exists`.
* En el caso de los valores de dimensión, el [Generador de filtros rápidos](#quick-filter-builder) crea automáticamente una condición `equals`. Por ejemplo, si arrastra y suelta `amsterdam` desde la dimensión `City`, se creará la condición `City equals amsterdam`.
* Si arrastra y suelta `unspecified` o `none`, el [Generador de filtros rápidos](#quick-filter-builder) creará automáticamente una condición `does not exist`.

Los filtros rápidos que cree aparecerán en la parte superior del panel. Los filtros rápidos tienen una barra izquierda fina de color azul claro. Cuando un filtro rápido se encuentra en modo de edición con el [Generador de filtros rápidos](#quick-filter-builder), el fondo del filtro rápido es de color azul claro.

Los resultados de los filtros rápidos que cree en un panel se aplican (mediante la lógica AND) a todas las visualizaciones que forman parte del panel.


## Administrar

Para administrar un filtro rápido, pase el puntero del ratón por encima de **[!UICONTROL Filtro rápido]** específico.

* Seleccione ![Editar](/help/assets/icons/Edit.svg) para abrir el [Generador de filtros rápidos](#quick-filter-builder) y edite el filtro rápido.
* Seleccione ![InfoOutline](/help/assets/icons/InfoOutline.svg) para abrir una ventana emergente. La ventana emergente muestra información sobre el filtro. Puede seleccionar **[!UICONTROL Poner a disposición de todos los proyectos y añadir a su lista de componentes]** para añadir el filtro a la lista de componentes ![Filtro](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filtros]** en el panel de componentes. Verá un cuadro de diálogo **[!UICONTROL Guardar filtro rápido]**, que le pedirá que especifique un nombre para el filtro. Seleccione **[!UICONTROL Guardar]** para continuar. Su [!UICONTROL filtro rápido] se convierte en un **[!UICONTROL Filtro]**. Ya no puede editar el filtro con el [Generador de filtros rápidos](#quick-filter-builder). En su lugar, debe editar el filtro como un filtro normal, usando el [Generador de filtros](filter-builder.md).

## Generador de filtros rápidos

Consulte a continuación un ejemplo del Generador de filtros rápidos. En el ejemplo, se abre el generador para un filtro rápido denominado `Call Reason = Order Change AND Online Orders is greater than or equal 1`. Ambos filtros rápidos de la parte superior se aplican al panel [!UICONTROL Tablero Valor de pedido promedio] y a todas las visualizaciones que contiene, como la tabla de forma libre [!UICONTROL Valor de pedido promedio por país].

![Generador de filtros rápidos](assets/quick-filter-builder.png)

El generador de filtros rápidos consta de las siguientes áreas y botones.

### Área de encabezado

El área de encabezado determina el nombre, tipo y ámbito del filtro rápido. También muestra un gráfico de los resultados del filtro rápido.

| Elemento | Descripción |
|---|---|
| **[!UICONTROL Nombre]** | El nombre se deriva automáticamente de la definición del filtro rápido. |
| **[!UICONTROL Personas]** <br/>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) ![Alerta](/help/assets/icons/Alert.svg) | Vista previa de los datos resultantes del filtro rápido. Una barra y un porcentaje proporcionan información de la cantidad de datos generales que forman parte del resultado del filtro rápido. Una ![alerta](/help/assets/icons/Alert.svg) roja indica que el filtro rápido no devuelve datos. |
| **[!UICONTROL Incluir]**<br/>**[!UICONTROL Excluir]** | Seleccione en el menú desplegable ![ChevronDown](/help/assets/icons/ChevronDown.svg) si desea incluir o excluir los resultados del filtro rápido de los datos del panel. |
| **[!UICONTROL Evento]**<br/>**[!UICONTROL Sesión]**<br/>**[!UICONTROL Persona]** | Seleccione en el menú desplegable ![ChevronDown](/help/assets/icons/ChevronDown.svg) el ámbito del filtro rápido. |

### Área de condición

El área de condición especifica las condiciones (hasta un máximo de tres). Para cada condición, puede especificar lo siguiente:

| Elemento | Descripción |
|---|---|
| **[!UICONTROL Dimension]**<br/>**[!UICONTROL Métrica]**<br/>**[!UICONTROL Intervalo de fecha]** | Seleccione en el menú desplegable ![ChevronDown](/help/assets/icons/ChevronDown.svg) si desea especificar una condición para una dimensión, métrica o intervalo de fechas. |
| **[!UICONTROL *componente *]** | El campo de componente de la condición. Puede [!UICONTROL *Escribir para añadir*] un componente, seleccionar un componente de la lista o arrastrar y soltar un componente desde el panel de componentes. Solo puede soltar componentes similares en el campo de componente de la condición. Por ejemplo, solo puede soltar un componente de dimensión del panel de componentes en una condición de dimensión. <br/>También puede arrastrar y soltar para reemplazar un componente existente.<br/>Seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para eliminar el componente del campo de componente. |
| **[!UICONTROL *operador *]** | El operador del componente. Consulte [Operadores](operators.md) para obtener más información. Solo está disponible para dimensiones y métricas. |
| **[!UICONTROL *value *]** | El valor de la condición. Según el operador seleccionado, el valor puede seleccionarse de una lista o puede introducir un valor. |
| ![CrossSize75](/help/assets/icons/CrossSize75.svg) | Seleccione esta opción para eliminar una condición del filtro rápido. |

### Botones

| Botón | Descripción |
|---|---|
| **[!UICONTROL AND]**<br/>**[!UICONTROL OR]** | Solo está disponible cuando se define más de una condición. Seleccione en el menú desplegable ![ChevronDown](/help/assets/icons/ChevronDown.svg) entre las condiciones. La selección determina la lógica booleana para el filtro rápido. No se puede mezclar lógica cuando se tienen tres condiciones. La lógica booleana es **[!UICONTROL AND]** o **[!UICONTROL OR]**. |
| ![AddCircle](/help/assets/icons/AddCircle.svg) | Añada otra condición al filtro rápido. Este botón sólo está disponible cuando se han definido una o dos condiciones para el filtro rápido. |
| **[!UICONTROL Aplicar]** | Aplique los cambios al filtro rápido. |
| **[!UICONTROL Abrir creador]** | Se le solicitará confirmación con un cuadro de diálogo **[!UICONTROL ¿Está seguro?]**. Si selecciona **[!UICONTROL Aceptar]**, ya no podrá modificar su filtro en el [Generador de filtros rápidos](#quick-filter-builder). El nombre de su filtro rápido se cambiará a **[!UICONTROL Filtro]** aparecerá una barra izquierda delgada de color azul más oscuro.<br/>Se abre el [Generador de filtros](filter-builder.md) normal con la opción de **[!UICONTROL Poner este filtro a disposición de todos los proyectos y añadirlo a la lista de componentes]**. <ul><li>Si selecciona esta opción y selecciona **[!UICONTROL Aplicar]**, el filtro se añadirá a la lista de componentes ![Filtro](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filtros]** del panel de componentes.</li><li>Si no selecciona esta opción y selecciona **[!UICONTROL Aplicar]**, el filtro seguirá siendo un filtro solo de proyecto de Workspace.</li></ul> |
| **[!UICONTROL Cancelar]** | Seleccione esta opción para cancelar la creación o edición de un filtro rápido. |

## Filtros rápidos frente a filtros

Los filtros rápidos son exactamente lo que su nombre indica. Puede crear y editar filtros rápidos rápidamente en línea y ver los efectos inmediatamente en el panel.

Los filtros tienen las siguientes ventajas en comparación con los filtros rápidos.

* Los filtros se pueden publicar en todos sus proyectos de Workspace
* Los filtros admiten una mayor complejidad mediante el uso de contenedores anidados y jerárquicos, y secuencias (mediante filtros de secuencia).


