---
description: El Generador de filtros proporciona un lienzo al que arrastrar y en el que soltar los Dimension de métricas, los filtros y los eventos para filtrar a las personas en función de la lógica, las reglas y los operadores de la jerarquía de contenedor. Esta herramienta de desarrollo integrado le permite generar y guardar filtros simples o complejos que identifican atributos y acciones de personas en visitas y eventos.
title: Generar filtros
feature: Filters
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '1450'
ht-degree: 4%

---

# Generar filtros {#build-filters}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_filters_createaudience"
>title="Crear audiencia"
>abstract="Las audiencias se pueden crear a partir de un filtro y compartir con Adobe Experience Platform para su activación."

<!-- markdownlint-enable MD034 -->


El cuadro de diálogo **[!UICONTROL Generador de filtros]** se usa para crear filtros nuevos o editar los existentes. El cuadro de diálogo se titula **[!UICONTROL Nuevo filtro]** o **[!UICONTROL Editar filtro]** para los filtros que crea o administra desde el administrador de [[!UICONTROL Filtros]](/help/components/filters/manage-filters.md).

>[!BEGINTABS]

>[!TAB Generador de filtros]

![Ventana de detalles del filtro que muestra los campos y las opciones descritos en la sección siguiente.](assets/filter-builder.png)

>[!TAB Crear o editar filtro]

![Ventana de detalles del filtro que muestra los campos y las opciones descritos en la sección siguiente.](assets/create-edit-filter.png)

>[!ENDTABS]

1. Especifique los siguientes detalles (![Necesario](/help/assets/icons/Required.svg) es obligatorio):

   | Elemento | Descripción |
   | --- | --- |
   | **[!UICONTROL Vista de datos]** | Puede seleccionar la vista de datos para el filtro.  El filtro que defina estará disponible como filtro en la ficha [Configuración](/help/data-views/create-dataview.md#settings-filters) de una vista de datos. |
   | **[!UICONTROL Filtro solo de proyecto]** | Un cuadro de información para explicar que el filtro solo está visible en el proyecto en el que se crea y que el filtro no se agregará a la lista de componentes. Habilite **[!UICONTROL Ponga este filtro a disposición de todos sus proyectos y agréguelo a la lista de componentes]** para cambiar esa configuración. Este cuadro de información solo está visible cuando crea un [filtro rápido](quick-filters.md) y convierte la información de filtro rápido en un filtro normal mediante **[!UICONTROL Abrir generador]** desde la interfaz de [!UICONTROL Filtro rápido]. |
   | **[!UICONTROL Título]** ![Requerido](/help/assets/icons/Required.svg) | Asigne un nombre al filtro, por ejemplo, `Last month mobile customers`. |
   | **[!UICONTROL Descripción]** | Proporcione una descripción para el filtro, por ejemplo, `Filter to define the mobile customers for the last month`. |
   | **[!UICONTROL Etiquetas]** | Organice el filtro creando o aplicando una o más etiquetas. Empiece a escribir para buscar las etiquetas existentes que puede seleccionar. O presione **[!UICONTROL ENTRAR]** para agregar una etiqueta nueva. Seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para quitar una etiqueta. |
   | **[!UICONTROL Definición]** ![Requerida](/help/assets/icons/Required.svg) | Defina su filtro con el [generador de definiciones](#definition-builder). |

   {style="table-layout:auto"}

1. Para comprobar si la definición del filtro es correcta, utilice la previsualización constantemente actualizada de los resultados del filtro en la parte superior derecha.
1. Para crear una audiencia a partir del filtro y compartirla con el Experience Platform, selecciona **[!UICONTROL Crear audiencia a partir del filtro]**. Consulte [Crear y publicar audiencias](/help/components/audiences/publish.md) para obtener más información.
1. Seleccionar:
   * **[!UICONTROL Guardar]** para guardar el filtro.
   * **[!UICONTROL Guardar como]** para guardar una copia del filtro.
   * **[!UICONTROL Eliminar]** para eliminar el filtro.
   * **[!UICONTROL Cancelar]** para cancelar los cambios realizados en el filtro o para cancelar la creación de un nuevo filtro.


## Generador de definiciones

Utilice el Generador de definiciones para crear la definición del filtro. En esa construcción, se utilizan componentes, contenedores, operadores y lógica.

Puede configurar el tipo y el ámbito de la definición:

1. Para especificar el tipo de definición, especifique si desea que la generación incluya o excluya una definición. Seleccione ![Configuración](/help/assets/icons/Setting.svg) **[!UICONTROL Opciones]** y en el menú desplegable **[!UICONTROL Incluir]** o **[!UICONTROL Excluir]**.
1. Para especificar el ámbito de su definición, seleccione en el menú desplegable **[!UICONTROL Incluir]** o **[!UICONTROL Excluir]** si desea que el ámbito de la definición sea **[!UICONTROL Evento]**, **[!UICONTROL Sesión]** o **[!UICONTROL Persona]**.

Siempre puede cambiar esta configuración más adelante.

### Componentes

Una parte vital de la creación de la definición del filtro es el uso de dimensiones, métricas, filtros existentes e intervalos de fechas. Todos estos componentes están disponibles en el panel de componentes del Generador de filtros.

![Empiece a crear una definición](assets/start-building-filter.gif){width=100%}

Para añadir un componente:

1. Arrastre y suelte un componente del panel Componentes en **[!UICONTROL Arrastre y suelte las métricas, los filtros o los Dimension aquí]**. Puede usar ![Buscar](/help/assets/icons/Search.svg) en la barra de componentes para buscar componentes específicos.
1. Especifique los detalles del componente. Por ejemplo, seleccione un valor de **[!UICONTROL Seleccionar valor]**. O introduzca un valor. El hecho de especificar uno o varios valores y cómo hacerlo dependen del componente y del operador.
1. Si lo desea, modifique el operador predeterminado. Por ejemplo, de **[!UICONTROL igual a]** a **[!UICONTROL es igual a cualquiera de]**. Consulte [Operadores](operators.md) para obtener una descripción detallada de los operadores disponibles.

Para editar un componente:

* Seleccione un operador nuevo para el componente en el menú desplegable del operador.
* Seleccione o especifique un valor diferente para el operador, si procede.
* Si el tipo de componente es una dimensión, puede definir el modelo de atribución. Consulte [Modelo de atribución](#attribution-models) para obtener más información.

Para eliminar un componente:

* Seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) en un componente.

### Contenedores

Puede agrupar varios componentes en uno o más contenedores y definir la lógica dentro de los contenedores y entre ellos. Los contenedores le permiten crear definiciones complejas para su filtro.

![Agregar un contenedor](assets/add-container.gif){Width=100%}

* Para agregar un contenedor, selecciona **[!UICONTROL Agregar contenedor]** de ![Configuración](/help/assets/icons/Setting.svg) **[!UICONTROL Opciones]**.
* Para agregar un componente existente al contenedor, arrastre y suelte el componente en el contenedor.
* Para agregar otro componente al contenedor, arrastre y suelte un componente del panel de componentes en el contenedor. Utilice la línea de inserción azul como guía.
* Para agregar otro componente fuera del contenedor, arrastre y suelte un componente desde el panel del componente fuera del contenedor, pero dentro del contenedor de definición principal. Utilice la línea de inserción azul como guía.
* Para modificar la lógica entre los componentes de un contenedor, entre contenedores o entre un contenedor y un componente, seleccione los **[!UICONTROL And]**, **[!UICONTROL Or]**, **[!UICONTROL Then]** adecuados. Al seleccionar Entonces, convierta el filtro en un filtro secuencial. Consulte [Crear filtro secuencial](seg-sequential-build.md) para obtener más información.
* Para cambiar el nivel de contenedor, seleccione ![WebPage](/help/assets/icons/WebPage.svg) **[!UICONTROL Evento]**, ![Visita](/help/assets/icons/Visit.svg) **[!UICONTROL Sesión]** o ![Usuario](/help/assets/icons/User.svg) **[!UICONTROL Persona]**.

Puede usar ![Setting](/help/assets/icons/Setting.svg) en un contenedor para las siguientes acciones:

| Acción de contenedor | Descripción |
|---|---|
| **[!UICONTROL Agregar contenedor]** | Agregue un contenedor anidado al contenedor. |
| **[!UICONTROL Exclusión]** | Excluya el resultado del contenedor en la definición del filtro. Una fina barra izquierda roja identifica un contenedor de exclusión. |
| **[!UICONTROL Inclusión]** | Incluya el resultado del contenedor en la definición del filtro. Incluir es la opción predeterminada. Una delgada barra izquierda gris identifica un contenedor de inclusión. |
| **[!UICONTROL Contenedor de nombres]** | Cambie el nombre del contenedor desde la descripción predeterminada. Escriba un nombre en el campo de texto. Si no proporciona ninguna entrada, se utiliza la descripción predeterminada. |
| **[!UICONTROL Eliminar contenedor]** | Elimine el contenedor de la definición. |


## Intervalos de fechas

Puede generar filtros que contengan intervalos de fechas móviles. Por lo tanto, puede responder preguntas sobre campañas o eventos en curso. Por ejemplo, puede generar un filtro que incluya a *todas las personas que hayan realizado una compra en línea en los últimos 60 días*.

![Filtro con intervalo de fechas móvil](assets/filter-rolling-date-range.gif)

+++ Aquí tiene un vídeo sobre el uso de intervalos de fechas móviles en los filtros

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

{{videoaa}}

+++

## Apilado de filtros {#stack}

Puede crear un filtro mediante filtros. Cuando utiliza filtros en un filtro, puede optimizarlo y reducir la complejidad.

Imagine que desea filtrar la combinación de tipo de dispositivo (2) y estados de EE. UU. (50). Puede crear 100 filtros, cada uno para la combinación única de tipo de dispositivo (teléfono móvil frente a tableta) y estado de EE. UU. Para obtener los usuarios de tabletas de California, debe utilizar uno de los 100 filtros:

![Filtro simple para CA y tableta](assets/filter-ca-tablet-single.png)

O bien, puede definir 52 filtros: 50 filtros para los estados de Estados Unidos, uno para el teléfono móvil y otro para la tableta. Y luego apilar los filtros para obtener los mismos resultados. Para obtener los usuarios de tabletas californianos, apilaría dos filtros:

![Filtro apilado para CA y tableta](assets/filter-ca-tablet-stacked.png)


## Atribución {#attribution}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_filters_attribution_repeating"
>title="Repetido"
>abstract="Incluye instancias y valores persistentes para la dimensión."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_filters_attribution_instance"
>title="Instancia"
>abstract="Incluye instancias y valores persistentes para la dimensión."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_filters_attribution_nonrepeatinginstance"
>title="Instancia no repetida"
>abstract="Incluye instancias únicas (no repetitivas) para la dimensión."

<!-- markdownlint-enable MD034 -->



Cuando se utiliza una dimensión en el Generador de filtros, se tienen las opciones para especificar el modelo de atribución para esa dimensión. El modelo de atribución que seleccione determina si los datos cumplen los requisitos para la condición especificada para el componente de dimensión.

Seleccione ![Setting](/help/assets/icons/Setting.svg) dentro del componente de dimensión y seleccione uno de los modelos de atribución en la ventana emergente:

| Modelos | Descripción |
|---|---|
| **[!UICONTROL Modelo repetitivo (predeterminado)]** | Incluya valores de instancia y persistentes para la dimensión para determinar la calificación. |
| **[!UICONTROL Instancia]** | Incluya solo valores de instancia para la dimensión para determinar la calificación. |
| **[!UICONTROL Instancia no repetida]** | Incluya valores de instancia únicos (no repetitivos) para la dimensión para determinar la calificación. |


![Modelo de atribución en la dimensión al crear un filtro](assets/filter-dimension-attribution.png)

### Ejemplo

Como parte de una definición de filtro, ha especificado la siguiente condición: Nombre de página es igual a Mujeres. Similar al ejemplo anterior. Repita esta definición de filtro con los otros dos modelos de atribución. Por lo tanto, tiene tres filtros, cada uno con su propio modelo de atribución:

* Página Mujer - Atribución - Repetición (predeterminada)
* Página de mujeres - Atribución - Instancia
* Página Mujeres - Atribución - Instancia no repetida


La tabla siguiente explica, para cada modelo de atribución, qué eventos entrantes se clasifican como ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) para esa condición.


| Página de mujeres - Atribución - <br/>*modelo de atribución* | Evento 1:<br/>Nombre de página igual a<br/>Mujeres | Evento 2:<br/>Nombre de página igual a<br/>Hombres | Evento 3:<br/>Nombre de página igual a<br/>Mujer | Evento 4:<br/>Nombre de página igual a<br/>Mujer<br/>(persistió) | Evento 5:<br/>Nombre de página igual a<br/>Cierre de compra | Evento 6:<br/>Nombre de página igual a<br/>Mujeres | Evento 7:<br/>Nombre de página igual a<br/>Inicio |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| Repetido (predeterminado) | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | ![Eliminar](/help/assets/icons/Remove.svg) | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | ![Eliminar](/help/assets/icons/Remove.svg) | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | ![Eliminar](/help/assets/icons/Remove.svg) |
| Instancia | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | ![Eliminar](/help/assets/icons/Remove.svg) | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | ![Eliminar](/help/assets/icons/Remove.svg) | ![Eliminar](/help/assets/icons/Remove.svg) | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | ![Eliminar](/help/assets/icons/Remove.svg) |
| Instancia no repetida | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | ![Eliminar](/help/assets/icons/Remove.svg) | ![Eliminar](/help/assets/icons/Remove.svg) | ![Eliminar](/help/assets/icons/Remove.svg) | ![Eliminar](/help/assets/icons/Remove.svg) | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | ![Eliminar](/help/assets/icons/Remove.svg) |

Un informe de ejemplo sobre los eventos que utilizan los tres filtros tiene este aspecto:

![Filtrar resultados del modelo de atribución](assets/filter-dimension-attribution-results.png)
