---
description: El Creador de métricas calculadas proporciona un lienzo en el que arrastrar y soltar dimensiones, métricas, segmentos y funciones para crear métricas personalizadas basadas en lógica de jerarquía de contenedor, reglas y operadores. Esta herramienta de desarrollo integrada le permite crear y guardar métricas calculadas simples o métricas calculadas avanzadas complejas.
title: Crear métricas calculadas
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: ec2fc88372814b01a04d4cc824181222ee55a83d
workflow-type: tm+mt
source-wordcount: '1628'
ht-degree: 94%

---

# Crear métricas calculadas {#build-metrics}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="Compatibilidad del producto"
>abstract="Indica en qué parte de Customer Journey Analytics se puede utilizar esta métrica calculada, por ejemplo, en Analysis Workspace, Report Builder, etc. Algunas métricas calculadas no se pueden usar con la experimentación."
>additional-url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation" text="Uso de métricas calculadas en experimentación"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_externalid"
>title="ID externo"
>abstract="Cambiar el ID externo puede afectar al modo en que la métrica calculada aparece en las fuentes externas, como las herramientas de inteligencia empresarial"

Customer Journey Analytics proporciona un lienzo para arrastrar y soltar dimensiones, métricas, segmentos y funciones para crear métricas personalizadas basadas en lógica de jerarquía de contenedores, reglas y operadores. Esta herramienta de desarrollo integrada le permite crear y guardar métricas calculadas simples o complejas.

Puede usar el creador de métricas calculadas para crear o editar métricas calculadas. Cuando se crean de esta manera, las métricas calculadas están disponibles en la lista de componentes y, a continuación, se pueden utilizar en proyectos de toda la organización. También puede crear rápidamente una métrica calculada que esté disponible solamente para el proyecto en el que se creó, tal como se describe en [Crear métricas calculadas para un solo proyecto](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) en [Métricas](/help/components/apply-create-metrics.md).

[Crear una métrica calculada](cm-workflow.md) describe las diferentes opciones disponibles para crear una nueva métrica calculada.

## Áreas del creador de métricas calculadas

El cuadro de diálogo **[!UICONTROL Generador de métricas calculadas]** se usa para crear anotaciones nuevas o editar las existentes. El cuadro de diálogo se titula **[!UICONTROL Nueva métrica calculada]** o **[!UICONTROL Editar métrica calculada]** para las anotaciones que cree o administre desde el administrador de [[!UICONTROL Métricas calculadas]](/help/components/calc-metrics/cm-workflow/cm-manager.md).

>[!BEGINTABS]

>[!TAB Generador de métricas calculadas]

![Ventana de detalles de métricas calculadas que muestra los campos y las opciones descritas en la sección siguiente.](assets/calculated-metric-builder.png)

>[!TAB Crear o editar métricas calculadas]

![Ventana de detalles de métricas calculadas que muestra los campos y las opciones descritas en la sección siguiente.](assets/create-edit-calculated-metric.png)

>[!ENDTABS]

1. Especifica los siguientes detalles (![Necesario](/help/assets/icons/Required.svg) es obligatorio):

   | Elemento | Descripción |
   | --- | --- |
   | **[!UICONTROL Vista de datos]** | Puede seleccionar la vista de datos para la métrica calculada.  La métrica calculada que defina estará disponible en los proyectos de Workspace en función de la vista de datos seleccionada. |
   | **[!UICONTROL Métrica solo de proyecto]** | Aparece un cuadro de información en la parte superior de este cuadro de diálogo cuando edita una métrica calculada que se creó para un solo proyecto, como se describe en [Crear métricas calculadas para un solo proyecto](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project). <p>Si desea que esta métrica calculada esté disponible para todos los proyectos, seleccione la opción **[!UICONTROL Poner esta métrica a disposición de todos los proyectos y agregarla a la lista de componentes]**.</p> |
   | **[!UICONTROL Título]** ![Requerido](/help/assets/icons/Required.svg) | Asigne una métrica calculada, como por ejemplo `Conversion Rate`. |
   | **[!UICONTROL ID externo]** ![Requerido](/help/assets/icons/Required.svg) | El nombre de la métrica calculada al utilizar una herramienta de BI externa y la extensión de BI. El valor se define automáticamente como `undefined_xxx` a menos que lo reemplace. |
   | **[!UICONTROL Descripción]** | Proporcione una descripción para el segmento, por ejemplo, `Calculated metric to define the conversion rate.`. No es necesario describir la fórmula para la métrica calculada, dado que la fórmula ya está disponible automáticamente en [!UICONTROL Resumen]. |
   | **[!UICONTROL Formato]** | Seleccione un formato para la métrica calculada: puede elegir entre **[!UICONTROL Decimal]**, **[!UICONTROL Hora]**, **[!UICONTROL Porcentaje]** y **[!UICONTROL Moneda]**. |
   | **[!UICONTROL Cifras decimales]** | Especifique el número de decimales para el formato seleccionado. Solo se habilita cuando el formato seleccionado es Decimal, Moneda y Porcentaje. |
   | **[!UICONTROL Mostrar tend ascendente como]** | Especifique si una tendencia ascendente de la métrica calculada se muestra como ▲ **[!UICONTROL Bueno (verde)]** o como ▼ **[!UICONTROL Malo (rojo)]**. |
   | **[!UICONTROL Moneda]** | Especifique la moneda de la métrica calculada. Solo se habilita cuando el formato seleccionado es Moneda. |
   | **[!UICONTROL Etiquetas]** | Organice la métrica calculada creando o aplicando una o varias etiquetas. Empiece a escribir para buscar las etiquetas existentes que puede seleccionar. O presione **[!UICONTROL Entrar]** para agregar una etiqueta nueva. Selecciona ![CrossSize75](/help/assets/icons/CrossSize75.svg) para quitar una etiqueta. |
   | **[!UICONTROL Vista previa]** | La vista previa abarca los últimos 90 días y es una forma de medir si ha definido la métrica correctamente. |
   | **[!UICONTROL Resumen]** | Muestra un resumen de la definición de la métrica calculada. <br/>Por ejemplo: ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Pedidos totales]** ![Dividir](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Sesiones]**. |
   | **[!UICONTROL Definición]** ![Requerida](/help/assets/icons/Required.svg) | Defina su segmento con el [Generador de definiciones](#definition-builder). |

1. Para comprobar si la definición de la métrica calculada es correcta, use la **[!UICONTROL Vista previa]** actualizada constantemente de los resultados de la métrica calculada. La **[!UICONTROL vista previa]** abarca los últimos 90 días y evalúa la definición de su métrica calculada de manera continua.

   La **[!UICONTROL compatibilidad del producto]** indica si la métrica calculada se puede usar en experimentación. Entre los posibles valores están:
   * **[!UICONTROL En cualquier lugar de Customer Journey Analytics]**: la métrica calculada se puede usar en todo Customer Journey Analytics.
   * **[!UICONTROL En cualquier lugar de Customer Journey Analytics (excepto en experimentación)]**: la métrica calculada se puede usar en todo Customer Journey Analytics, excepto en el panel Experimentación.

1. Seleccionar…
   * Selecciona **[!UICONTROL Guardar]** para guardar la métrica calculada.
   * **[!UICONTROL Guardar como]** para guardar una copia de la métrica calculada.
   * **[!UICONTROL Cancelar]** para cancelar los cambios realizados en una anotación o cancelar la creación de una nueva métrica calculada.


## Generador de definiciones

Utilice el generador de definiciones para arrastrar y soltar dimensiones, métricas, segmentos y funciones para crear métricas personalizadas basadas en lógica de jerarquía de contenedor, reglas y operadores. En esa construcción, puede utilizar métricas estándar, métricas definidas por Adobe, métricas calculadas, segmentos, dimensiones y funciones. Todos estos componentes están disponibles en el panel de componentes del generador de métricas calculadas. Además, puede utilizar operadores y contenedores en la definición.

![Crear métrica calculada](/help/components/calc-metrics/cm-workflow/assets/create-calculated-metric.gif)

Solo las métricas se definen como componentes singulares en el área **[!UICONTROL Definición]**. Todos los demás componentes se definen como un contenedor, métricas de ajuste u otros contenedores. Consulte [Detalles de conexión](#containers) para obtener más información.

### Métricas

Para añadir una métrica:

* Arrastre y suelte un componente ![Eventos](/help/assets/icons/Event.svg) **[!UICONTROL Métricas]** del panel de componentes en **[!UICONTROL Arrastre y suelte aquí métricas, dimensiones, elementos de dimensión, filtros o funciones]**. Puede usar ![Buscar](/help/assets/icons/Search.svg) en la barra de componentes para buscar componentes específicos.

Cuando se utiliza una métrica calculada como parte de la definición, la métrica calculada se expande.

Para reemplazar una métrica:

1. Seleccione ![Configuración](/help/assets/icons/Setting.svg) en un componente de métrica en el área de **[!UICONTROL Definición]**.
1. En el cuadro de diálogo emergente puede definir el tipo de métrica y un modelo de atribución. Consulte [Tipo de métrica y atribución](m-metric-type-alloc.md)

Para eliminar una métrica:

* Seleccione ![Cerrar](/help/assets/icons/Close.svg) en la métrica.

### Operadores

Los operadores permiten especificar el operador entre componentes o contenedores. Los operadores aparecen automáticamente entre

* dos o más métricas en un contenedor,
* dos o más contenedores en un contenedor,
* una o más métricas y uno o más contenedores en un contenedor.

Puede seleccionar:

| Símbolo | Operador |
|:---:|---|
| ![Dividir](/help/assets/icons/Divide.svg) | Dividir (predeterminado) |
| ![Cierre](/help/assets/icons/Close.svg) | Multiplicar |
| ![Eliminar](/help/assets/icons/Remove.svg) | Restar |
| ![Agregue](/help/assets/icons/Add.svg) | Agregar |

### Número estático

Puede añadir un número estático a la definición de métrica calculada. Para añadir un número estático:

* Seleccione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Añadir]** desde un contenedor.
* Seleccione **[!UICONTROL Número estático]**. Aparece un contenedor de número estático.
* Seleccione [!UICONTROL *Haga clic para añadir un valor*] y escriba un valor.


### Contenedores

Las dimensiones, los segmentos y las funciones se añaden como contenedores a una definición de métrica calculada. También puede añadir un contenedor genérico. Los contenedores funcionan como una expresión matemática y determinan el orden de las operaciones. Cualquier elemento dentro de un contenedor se procesa antes que el siguiente componente o contenedor.


#### Contenedor de segmentos

Utiliza el concepto de contenedor de segmentos para crear una [métrica segmentada](metrics-with-segments.md). Puede construir un contenedor de segmentos utilizando un segmento o un segmento que cree a partir de una dimensión.

* Para añadir un contenedor de segmentos a partir de una dimensión:

   1. Arrastre y suelte un componente ![Dimensiones](/help/assets/icons/Dimensions.svg) **[!UICONTROL Dimensiones]** del panel de componentes hasta **[!UICONTROL Arrastrar y soltar aquí métricas, dimensiones, elementos de dimensión, segmentos o funciones]**. Puede utilizar la ![Búsqueda](/help/assets/icons/Search.svg) en la barra de componentes para buscar componentes específicos.
   1. En la ventana emergente **[!UICONTROL Crear segmento a partir de Dimension]**, defina la condición del segmento. Seleccione en la lista de operadores y seleccione o introduzca un valor. Por ejemplo, **[!UICONTROL Mes]** **[!UICONTROL es igual a]** ![ChevronDown](/help/assets/icons/ChevronDown.svg) `Sep 2024`.
   1. Seleccione **[!UICONTROL Listo]**. Se ha añadido un contenedor de segmentos a la **[!UICONTROL Definición]**.


* Para añadir un contenedor de segmentos desde un filtro, puede utilizar:

   * Arrastre y suelte un componente ![Segmentación](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segmentos]** del panel de componentes hasta **[!UICONTROL Arrastrar y soltar aquí métricas, dimensiones, elementos de dimensión, segmentos o funciones]**. Puede utilizar la ![Búsqueda](/help/assets/icons/Search.svg) en la barra de componentes para buscar segmentos específicos.
Se añade automáticamente un contenedor de segmentos a la **[!UICONTROL Definición]**, con el nombre del segmento.

   * Arrastre y suelte un componente ![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segment]** del panel de componentes en un contenedor genérico. El contenedor se modifica para convertirse en un contenedor de segmentos.

   * Seleccione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Añadir]** desde un contenedor:

      1. Seleccione **[!UICONTROL Segmento]**. Se ha añadido un contenedor de segmentos a la **[!UICONTROL Definición]**.
      1. En el nuevo contenedor de segmentos, seleccione un segmento del menú desplegable [!UICONTROL *Seleccionar...*].

  >[!TIP]
  >
  >Puede añadir más de un segmento a un contenedor.

  Los segmentos del contenedor reciben el nombre del componente de segmento. Por ejemplo, ![Segmentación](/help/assets/icons/Segmentation.svg) **[!UICONTROL Sesiones web]**. Seleccione ![InfoOutline](/help/assets/icons/InfoOutline.svg) para mostrar una ventana emergente con más detalles sobre el segmento. En la ventana emergente, seleccione ![Editar](/help/assets/icons/Edit.svg) para editar la definición del segmento.

Para quitar un segmento de un contenedor:

* Seleccione ![Cerrar](/help/assets/icons/Close.svg) junto al nombre del segmento.

Consulte [Métricas segmentadas](metrics-with-segments.md) para obtener más detalles y ejemplos.

#### Contenedor de funciones

Para añadir un contenedor de funciones, puede utilizar:

* Arrastrar y soltar:

   1. Arrastre y suelte un componente ![Función](/help/assets/icons/Effect.svg) **[!UICONTROL Funciones]** del panel de componentes hasta **[!UICONTROL Arrastrar y soltar aquí métricas, dimensiones, elementos de dimensión, filtros o funciones]**. Puede utilizar la ![Búsqueda](/help/assets/icons/Search.svg) en la barra de componentes para buscar funciones específicas.
   1. Se añade automáticamente un contenedor de funciones a la **[!UICONTROL Definición]** utilizando el nombre de la función.

* Seleccione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Añadir]** desde un contenedor:

   1. Seleccione **[!UICONTROL Función]**.
   1. En el contenedor, seleccione una función del menú desplegable [!UICONTROL *Seleccionar...*].

El contenedor de funciones recibe el nombre del componente de funciones. Por ejemplo, ![Función](/help/assets/icons/Effect.svg) **[!UICONTROL SQUARE ROOT (métrica)]**. Seleccione ![InfoOutline](/help/assets/icons/InfoOutline.svg) para mostrar una ventana emergente con más detalles sobre la función. Seleccione **[!UICONTROL Más información]** para obtener más información sobre la función.

Consulte [Uso de funciones](cm-using-functions.md) para obtener detalles sobre cómo utilizar funciones y qué funciones están disponibles para crear una métrica calculada.


#### Contenedor genérico

Para añadir un contenedor genérico:

* Seleccione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Añadir]** desde un contenedor
* Seleccione **[!UICONTROL Contenedor]**. Se añade un nuevo contenedor genérico vacío a la **[!UICONTROL Definición]**. Puede utilizar un contenedor genérico para anidar o crear una jerarquía en la definición de la métrica calculada.


#### Eliminación de un contenedor

Para eliminar un contenedor, seleccione ![Cerrar](/help/assets/icons/Close.svg) en el nivel de contenedor.

>[!MORELIKETHIS]
>
>[Uso de funciones](cm-using-functions.md)
>&#x200B;>[Segmentos ](/help/components/segments/seg-overview.md)
>
