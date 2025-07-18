---
description: Descubra cómo el Generador de segmentos proporciona un lienzo al que arrastrar y en el que soltar las métricas, las dimensiones, los segmentos y los eventos para segmentar a los visitantes en función de la lógica, las reglas y los operadores de la jerarquía de contenedor. Descubra cómo puede generar y guardar segmentos simples o complejos que identifican atributos y acciones de visitantes en visitas y visitas individuales de páginas.
title: Generar segmentos
feature: Filters, Segments
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '1570'
ht-degree: 87%

---

# Generar segmentos {#build-segments}

>[!CONTEXTUALHELP]
>id="components_filters_createaudience"
>title="Creación de público"
>abstract="Los públicos se pueden crear a partir de un segmento y compartirse con Adobe Experience Platform para su activación."

>[!CONTEXTUALHELP]
>id="components_filters_datapreview"
>title="Previsualización de los datos"
>abstract="Compara los datos de este segmento con los datos de la vista de datos. El porcentaje de vista previa se basa en el número total de la vista de datos de los **últimos 90 días**.<br><br/>Si la vista previa no se carga, es posible que la conexión aún esté reponiendo los datos."

El cuadro de diálogo **[!UICONTROL Generador de segmentos]** se usa para crear segmentos nuevos o editar los existentes. El cuadro de diálogo se titula **[!UICONTROL Nuevo segmento]** o **[!UICONTROL Editar segmento]** para los segmentos que se creen o administren desde el administrador de [[!UICONTROL Segmentos]](/help/components/segments/seg-manage.md).

>[!BEGINTABS]

>[!TAB Generador de segmentos]

![Ventana de detalles del segmento que muestra los campos y las opciones descritas en la sección siguiente.](assets/filter-builder.png)

>[!TAB Crear o editar segmento]

![Ventana de detalles del segmento que muestra los campos y las opciones descritas en la sección siguiente.](assets/create-edit-filter.png)

>[!ENDTABS]

1. Especifica los siguientes detalles (![Necesario](/help/assets/icons/Required.svg) es obligatorio):

   | Elemento | Descripción |
   | --- | --- |
   | **[!UICONTROL Vista de datos]** | Puede seleccionar la vista de datos para el segmento.  El segmento que defina estará disponible como segmento en la ficha [Configuración](/help/data-views/create-dataview.md#settings-filters) de una vista de datos. |
   | **[!UICONTROL Segmento solo de proyecto]** | Un cuadro de información que explica que el segmento solo es visible en el proyecto en el que se crea y que este no se añade a la lista de componentes. Habilite **[!UICONTROL Poner este segmento a disposición de todos los proyectos y añadirlo a la lista de componentes]** para cambiar esa configuración. Este cuadro de información solo es visible cuando crea un [segmento rápido](seg-quick.md) y convierte su información en un segmento normal mediante la opción **[!UICONTROL Abrir generador]** de la interfaz de [!UICONTROL Segmento rápido]. |
   | **[!UICONTROL Título]** ![Requerido](/help/assets/icons/Required.svg) | Asigne un nombre al segmento como, por ejemplo, `Last month mobile customers`. |
   | **[!UICONTROL Descripción]** | Proporcione una descripción para el segmento, por ejemplo, `Segment to define the mobile customers for the last month`. |
   | **[!UICONTROL Etiquetas]** | Organice el segmento creando o aplicando una o varias etiquetas. Empiece a escribir para buscar las etiquetas existentes que puede seleccionar. O presione **[!UICONTROL Entrar]** para agregar una etiqueta nueva. Selecciona ![CrossSize75](/help/assets/icons/CrossSize75.svg) para quitar una etiqueta. |
   | **[!UICONTROL Definición]** ![requerida](/help/assets/icons/Required.svg) | Defina su segmento con el [Generador de definiciones](#definition-builder). |

   {style="table-layout:auto"}

1. Para comprobar si la definición del segmento es correcta, utilice la previsualización constantemente actualizada de los resultados del segmento situada en la parte superior derecha.
1. Para crear una audiencia a partir del segmento y compartir la audiencia con Experience Platform, seleccione **[!UICONTROL Crear audiencia a partir del segmento]**. Consulte [Crear y publicar audiencias](/help/components/audiences/publish.md) para obtener más información.
1. Seleccione lo siguiente:
   * **[!UICONTROL Guardar]** para guardar el segmento.
   * **[!UICONTROL Guardar como]** para guardar una copia del segmento.
   * **[!UICONTROL Eliminar]** para eliminar el segmento.
   * **[!UICONTROL Cancelar]** para cancelar los cambios realizados en un segmento o cancelar la creación de un nuevo segmento.


## Generador de definiciones

El Generador de definiciones se utiliza para crear la definición del segmento. En esa construcción, se utilizan componentes, contenedores, operadores y lógica.

Se puede configurar el tipo y el ámbito de la definición:

1. Para especificar el tipo de definición, especifique si desea que la generación incluya o excluya una definición. Seleccione ![Configuración](/help/assets/icons/Setting.svg) **[!UICONTROL Opciones]** y, luego, **[!UICONTROL Incluir]** o **[!UICONTROL Excluir]** del menú desplegable.
1. Para especificar el ámbito de su definición, seleccione en el menú desplegable **[!UICONTROL Incluir]** o **[!UICONTROL Excluir]** si desea que el ámbito de la definición sea **[!UICONTROL Evento]**, **[!UICONTROL Sesión]**, **[!UICONTROL Persona]**, **[!UICONTROL Cuenta global]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Cuenta]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Oportunidad]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, o **[!UICONTROL Grupo comprador]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}

Siempre puede cambiar esta configuración más adelante.

### Componentes

Una parte vital de la creación de la definición del segmento es el uso de dimensiones, métricas, segmentos existentes e intervalos de fechas. Todos estos componentes están disponibles en el panel del componente del generador de segmentos.

![Empiece a crear una definición](assets/start-building-filter.gif){width=100%}

Para añadir un componente, haga lo siguiente:

1. Arrastre y suelte un componente del panel de componentes hasta **[!UICONTROL Arrastre y suelte aquí métricas, segmentos o dimensiones]**. Puede utilizar la ![Búsqueda](/help/assets/icons/Search.svg) en la barra de componentes para buscar componentes específicos.
1. Especifique los detalles del componente. Por ejemplo, seleccione un valor en **[!UICONTROL Seleccionar valor]**. O bien, introduzca un valor El hecho de especificar uno o varios valores y cómo hacerlo dependen del componente y del operador.
1. Si lo desea, modifique el operador predeterminado. Por ejemplo, de **[!UICONTROL es igual a]** a **[!UICONTROL es igual a cualquiera de]**. Consulte [Operadores](seg-operators.md) para obtener información general sobre los operadores disponibles.

Para editar un componente:

* Seleccione un operador nuevo para el componente en el menú desplegable del operador.
* Seleccione o especifique un valor diferente para el operador, si procede.
* Si el tipo de componente es una dimensión, puede definir el modelo de atribución. Consulte [Modelo de atribución](#attribution) para obtener más información.

Para eliminar un componente:

* Seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) en un componente.

### Contenedores

Puede agrupar varios componentes en uno o varios contenedores y definir la lógica dentro de los contenedores y entre ellos. Los contenedores le permiten crear definiciones complejas para su segmento.

![Añadir un contenedor](assets/add-container.gif){Width=100%}

* Para añadir un contenedor, seleccione **[!UICONTROL Añadir contenedor]** en ![Configuración](/help/assets/icons/Setting.svg) **[!UICONTROL Opciones]**.
* Para añadir un componente existente al contenedor, arrastre y suelte el componente en el contenedor.
* Para añadir otro componente al contenedor, arrastre y suelte un componente del panel del componente en el contenedor. Utilice la línea de inserción azul como guía.
* Para añadir otro componente fuera del contenedor, arrastre y suelte un componente del panel del componente fuera del contenedor, pero dentro del contenedor de definición principal. Utilice la línea de inserción azul como guía.
* Para modificar la lógica entre los componentes de un contenedor, entre contenedores o entre un contenedor y un componente, seleccione los operadores **[!UICONTROL And]**, **[!UICONTROL Or]**, **[!UICONTROL Then]** adecuados. Al seleccionar Entonces, convierte el segmento en un segmento secuencial. Consulte [Crear segmento secuencial](seg-sequential-build.md) para obtener más información.
* Para cambiar el nivel de contenedor, selecciona ![Globo](/help/assets/icons/Globe.svg) **[!UICONTROL Cuenta global]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, ![Cuenta](/help/assets/icons/Account.svg) **[!UICONTROL Cuenta]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, ![Oportunidad](/help/assets/icons/Opportunity.svg) **[!UICONTROL Oportunidad]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, ![Grupo de compra](/help/assets/icons/BuyingGroup.svg) **[!UICONTROL Grupo de compra]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, ![WebPage](/help/assets/icons/WebPage.svg) **[!UICONTROL Evento]**, ![Visita](/help/assets/icons/Visit.svg) **[!UICONTROL Sesión]** o ![Usuario](/help/assets/icons/User.svg) **[!UICONTROL Persona]**.

Puede usar ![Configuración](/help/assets/icons/Setting.svg) en un contenedor para las siguientes acciones:

| Acción del contenedor | Descripción |
|---|---|
| **[!UICONTROL Añadir contenedor]** | Añada un contenedor anidado al contenedor. |
| **[!UICONTROL Exclusión]** | Excluya el resultado del contenedor en la definición del segmento. Una fina barra izquierda roja identifica un contenedor de exclusión. |
| **[!UICONTROL Inclusión]** | Incluya el resultado del contenedor en la definición del segmento. Incluir es la opción. Una fina barra gris a la izquierda identifica un contenedor de inclusión. |
| **[!UICONTROL Contenedor de nombres]** | Cambie el nombre del contenedor desde la descripción predeterminada. Escriba un nombre en el campo de texto. Si no proporciona ninguna entrada, se utiliza la descripción predeterminada. |
| **[!UICONTROL Eliminar contenedor]** | Elimine el contenedor de la definición. |


## Intervalos de fechas

Puede generar segmentos que contengan intervalos de fechas móviles. Por lo tanto, puede responder preguntas sobre campañas o eventos en curso. Por ejemplo, puede crear un segmento que incluya *a todas las personas que hayan efectuado una compra en línea en los últimos 60 días*.

![Segmento con intervalo de fechas móviles](assets/filter-rolling-date-range.gif)


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Intervalos de fechas móviles en segmentos](https://video.tv.adobe.com/v/25403/?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


## Apilar segmentos {#stack}

Puede crear un segmento mediante segmentos. Cuando utiliza segmentos en un segmento, puede optimizarlo y reducir la complejidad.

Imagine que desea segmentar la combinación de tipo de dispositivo (2) y estados de Estados Unidos (50). Puede crear 100 segmentos, cada uno para la combinación única de tipo de dispositivo (teléfono móvil frente a tableta) y por estado de los EE. UU. Para obtener los usuarios de tabletas de California, debe utilizar uno de los 100 segmentos:

![Segmento simple para California y tableta](assets/filter-ca-tablet-single.png)

O bien, puede definir 52 segmentos: 50 segmentos para los estados de Estados Unidos, uno para el teléfono móvil y otro para la tableta. Y luego apilar los segmentos para obtener los mismos resultados. Para obtener los usuarios de tabletas de California, apilaría dos segmentos:

![Segmento apilado para CA y tableta](assets/filter-ca-tablet-stacked.png)


## Atribución {#attribution}

>[!CONTEXTUALHELP]
>id="components_filters_attribution_repeating"
>title="Repetido"
>abstract="Incluye instancias y valores persistentes para la dimensión."


>[!CONTEXTUALHELP]
>id="components_filters_attribution_instance"
>title="Instancia"
>abstract="Incluye instancias para la dimensión."


>[!CONTEXTUALHELP]
>id="components_filters_attribution_nonrepeatinginstance"
>title="Instancia no repetida"
>abstract="Incluye instancias únicas (no repetitivas) para la dimensión."




Cuando se utiliza una dimensión en el Generador de segmentos, se tienen las opciones para especificar el modelo de atribución para esa dimensión. El modelo de atribución que seleccione determina si los datos cumplen los requisitos para la condición especificada para el componente de dimensión.

Seleccione ![Configuración](/help/assets/icons/Setting.svg) dentro del componente de dimensión y seleccione uno de los modelos de atribución en la ventana emergente:

| Modelos | Descripción |
|---|---|
| **[!UICONTROL Modelo repetitivo (predeterminado)]** | Incluya valores de instancia y persistentes para la dimensión para determinar la calificación. |
| **[!UICONTROL Instancia]** | Incluya solo valores de instancia para la dimensión para determinar la calificación. |
| **[!UICONTROL Instancia no repetida]** | Incluya valores de instancia únicos (no repetitivos) para la dimensión para determinar la calificación. |


![Modelo de atribución en la dimensión al crear un segmento](assets/filter-dimension-attribution.png)

### Ejemplo

Como parte de una definición de segmento, ha especificado la siguiente condición: Nombre de página es igual a Mujeres. Similar al ejemplo anterior. Repita esta definición de segmento con los otros dos modelos de atribución. Por lo tanto, tiene tres segmentos, cada uno con su propio modelo de atribución:

* Página Mujeres - Atribución - Repetición (predeterminada)
* Página Mujeres - Atribución - Instancia
* Página Mujeres - Atribución - Instancia no repetida


La tabla siguiente explica, para cada modelo de atribución, qué eventos entrantes se clasifican como ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) para esa condición.


| Página Mujeres - Atribución - <br/>*modelo de atribución* | Evento 1:<br/>Nombre de página igual a<br/>Mujeres | Evento 2:<br/>Nombre de página igual a<br/>Hombres | Evento 3:<br/>Nombre de página igual a<br/>Mujer | Evento 4:<br/>Nombre de página igual a<br/>Mujer<br/>(persistió) | Evento 5:<br/>Nombre de página igual a<br/>Cierre de compra | Evento 6:<br/>Nombre de página igual a<br/>Mujeres | Evento 7:<br/>Nombre de página igual a<br/>Inicio |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| Repetido (predeterminado) | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | ![Eliminar](/help/assets/icons/Remove.svg) | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | ![Eliminar](/help/assets/icons/Remove.svg) | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | ![Eliminar](/help/assets/icons/Remove.svg) |
| Instancia | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | ![Eliminar](/help/assets/icons/Remove.svg) | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | ![Eliminar](/help/assets/icons/Remove.svg) | ![Eliminar](/help/assets/icons/Remove.svg) | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | ![Eliminar](/help/assets/icons/Remove.svg) |
| Instancia no repetida | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | ![Eliminar](/help/assets/icons/Remove.svg) | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | ![Eliminar](/help/assets/icons/Remove.svg) | ![Eliminar](/help/assets/icons/Remove.svg) | ![Círculo de verificación](/help/assets/icons/CheckmarkCircle.svg) | ![Eliminar](/help/assets/icons/Remove.svg) |

Un informe de ejemplo sobre los eventos que utilizan los tres segmentos tiene este aspecto:

![Segmentar los resultados del modelo de atribución](assets/filter-dimension-attribution-results.png)
