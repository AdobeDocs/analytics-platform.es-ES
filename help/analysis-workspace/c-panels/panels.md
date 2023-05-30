---
description: Un panel es una colección de tablas y visualizaciones
title: Resumen de paneles
feature: Panels
exl-id: be3e34a0-06c1-4200-b965-96084c2912fd
source-git-commit: c18ed01f899b7a521c67ed6a0008210099b858bf
workflow-type: tm+mt
source-wordcount: '1232'
ht-degree: 51%

---

# Resumen de paneles

Un [!UICONTROL panel] es una colección de tablas y visualizaciones. Puede acceder a los paneles desde el icono de la parte superior izquierda de Workspace o desde una [panel en blanco](/help/analysis-workspace/c-panels/blank-panel.md). Los paneles son útiles cuando desea organizar sus proyectos según períodos de tiempo, vistas de datos o casos de uso de análisis.

## Tipos de panel

Los siguientes tipos de panel están disponibles en Analysis Workspace para [!UICONTROL Customer Journey Analytics]:

| Nombre del panel | Descripción |
| --- | --- |
| [Panel en blanco](/help/analysis-workspace/c-panels/blank-panel.md) | Elija entre los paneles y las visualizaciones disponibles para iniciar el análisis. |
| [Panel de información rápida](quickinsight.md) | Cree rápidamente una tabla de forma libre y una visualización complementaria para analizar y descubrir información de manera más rápida. |
| [Panel de Attribution](attribution.md) | Compare y visualice rápidamente los modelos de atribución utilizando cualquier dimensión y métrica de conversión. |
| [Panel de forma libre](freeform-panel.md) | Realice comparaciones y desgloses ilimitados y, a continuación, añada visualizaciones para contar una historia de datos enriquecida. |
| [Panel de visualizadores simultáneos de medios](media-concurrent-viewers.md) | Analice los visualizadores simultáneos a lo largo del tiempo, con detalles sobre la frecuencia máxima de acceso y la capacidad de desglosar datos y compararlos. |
| [Panel Tiempo invertido en la reproducción de medios](media-playback-timespent/media-playback-time-spent.md) | Analice el tiempo invertido en la reproducción para comprender dónde se produjo el pico de concurrencia o dónde se produjeron los descensos. |

![](assets/panel-overview.png)

Los paneles [!UICONTROL Quick Insights], [!UICONTROL En blanco] y [!UICONTROL Forma libre] son buenos lugares para iniciar el análisis, mientras que [!UICONTROL Attribution IQ] se presta para análisis más avanzados. Hay un botón `"+"` disponible en los proyectos para que pueda agregar paneles en blanco en cualquier momento.

El panel inicial predeterminado es [!UICONTROL Forma libre], pero también puede convertir el [Panel en blanco](/help/analysis-workspace/c-panels/blank-panel.md) en el panel predeterminado.

## Calendario {#calendar}

El calendario del panel controla el intervalo de la creación de informes de las tablas y visualizaciones de un panel.

Nota: Si se utiliza un componente de intervalo de fechas (púrpura) en una tabla, una visualización o en la zona desplegable de un panel, se anulará el calendario del panel.

![](assets/panel-calendar.png)

Puede aplicar un intervalo de fechas de nivel de minuto bajo la configuración avanzada del calendario del panel. Si realiza informes en un intervalo de fechas que abarca muchos días, la hora de inicio se aplica al primer día y la hora de finalización se aplica al último día del intervalo.

## Zona de colocación {#dropzone}

La zona de colocación del panel permite aplicar filtros y filtros desplegables a todas las tablas y visualizaciones dentro de un panel. Puede aplicar uno o varios filtros a un panel. El título sobre cada filtro se puede modificar haciendo clic en el lápiz de edición, o bien puede hacer clic con el botón derecho para eliminarlo por completo.

### Filtros

Arrastre y suelte cualquier filtro del carril izquierdo en la zona desplegable del panel para empezar a filtrar el panel.

![](assets/segment-filter.png)

### Filtros ad hoc

Los componentes que no son filtros también se pueden arrastrar directamente a la zona de colocación para crear filtros ad hoc, lo que le ahorrará el tiempo y el tener que utilizar el Generador de filtros. Los filtros creados de esta manera se definen automáticamente como filtros de nivel de evento. Puede modificar esta definición haciendo clic en el icono de información (i) junto al filtro, seleccionando el icono de edición con forma de lápiz y editándola en el Generador de filtros.

Los filtros ad hoc son un tipo de filtro rápido y son locales del proyecto. No aparecen en el carril izquierdo a menos que las haga públicas.

Para obtener más información, consulte [Filtros rápidos](/help/components/filters/quick-filters.md).

![](assets/adhoc-segment-filter.png)

### Filtros desplegables estáticos

Los filtros desplegables permiten interactuar con los datos de forma controlada. Por ejemplo, puede añadir un filtro desplegable para tipos de dispositivos móviles para poder filtrar el panel por dispositivos de tableta, teléfonos móviles o equipos de escritorio.

Los filtros desplegables también se pueden utilizar para consolidar muchos proyectos en uno. Por ejemplo, si tiene muchas versiones del mismo proyecto con diferentes filtros de país aplicados, puede consolidar todas las versiones en un único proyecto y añadir un filtro desplegable de país.

![](assets/dropdown-filter-intro.png)

Para crear un filtro desplegable estático:

* Para filtros desplegables que utilizan elementos de dimensión, haga clic en el icono de flecha derecha junto a la dimensión deseada en el carril izquierdo. Esta acción expone todos los elementos de dimensión disponibles. Seleccionar varios elementos de dimensión de esta lista utilizando `[Shift + Click]` o `[Ctrl + Click]`, luego suéltelos en la zona desplegable del panel **mientras sostiene`[Shift]`**.
* Para filtros desplegables que utilizan otros componentes, como métricas, filtros o intervalos de fechas, seleccione varios componentes mediante `[Shift + Click]` o `[Ctrl + Click]`. Coloque la selección en la zona desplegable del panel **mientras sostiene`[Shift]`**. Todos los tipos de componentes se tratan como filtros en este contexto.
* Un solo filtro desplegable solo puede contener un solo tipo de componente. Si incluye varios tipos de componentes en la selección, se crea un filtro desplegable independiente por tipo de componente. Por ejemplo, si incluye métricas y elementos de dimensión en la selección, se crean dos filtros desplegables independientes. Un filtro desplegable incluye elementos de dimensión y el otro incluye métricas.

Seleccione una de las opciones de la lista desplegable para cambiar los datos del panel. También puede optar por no filtrar ninguno de los datos del panel seleccionando **[!UICONTROL Sin filtro]**.

![](assets/create-dropdown.png)

Al hacer clic con el botón derecho en un filtro desplegable, se proporcionan las siguientes opciones:

* **[!UICONTROL Añadir etiqueta]**: Cuando se añade un filtro desplegable a un proyecto, se establece automáticamente una etiqueta en el nombre del componente. Si elimina la etiqueta, puede agregarla de nuevo con esta opción.
* **[!UICONTROL Eliminar etiqueta]**: elimine el texto situado encima de un filtro desplegable.
* **[!UICONTROL Eliminar filtro desplegable]**: elimina el filtro desplegable del panel.

[Vea el vídeo](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html?lang=es) para obtener más información sobre cómo añadir filtros desplegables al proyecto.

### Filtros desplegables dinámicos

Los filtros desplegables dinámicos le permiten determinar los valores disponibles en función de los datos dentro del intervalo de informes del panel y los valores de otros filtros desplegables. Por ejemplo, puede crear dos desplegables dinámicos utilizando las dimensiones Países y Ciudades. Al seleccionar un país de la lista desplegable UICONTROL Países, la lista desplegable Ciudades se ajusta dinámicamente para mostrar solo las ciudades de ese país.

Este mismo concepto se aplica a todas las dimensiones; solo son visibles los elementos de dimensión que aparecen dentro del intervalo de fechas y los filtros seleccionados del panel. Los elementos de Dimension seleccionados en los filtros desplegables estáticos afectan a los valores disponibles en los filtros desplegables dinámicos. Sin embargo, lo contrario no es verdadero; los elementos de Dimension seleccionados en los filtros desplegables dinámicos no afectan a los valores disponibles en los filtros desplegables estáticos.

La selección manual de elementos de dimensión está disponible si prevé que se recopilará un determinado elemento de dimensión en el futuro. También puede borrar un filtro desplegable dinámico para que no contenga un valor, lo que permitirá que otros filtros desplegables dinámicos contengan más valores. Seleccionar **[!UICONTROL Restablecer todo]** para borrar la selección de todos los filtros desplegables de ese panel.

Para crear un filtro desplegable dinámico:

* Arrastre y suelte una sola dimensión en la zona desplegable del panel **mientras sostiene`[Shift]`**.
* Los filtros desplegables dinámicos no están disponibles para métricas, filtros o intervalos de fechas.
* Haga clic con el botón derecho en un filtro desplegable y seleccione **[!UICONTROL Eliminar filtro]** para eliminarlo.

Al hacer clic con el botón derecho en un filtro desplegable dinámico, se proporcionan las mismas opciones que en los filtros desplegables estáticos.

## Menú contextual {#right-click}

Para obtener más funcionalidades, haga clic con el botón derecho en el encabezado del panel.

![](assets/right-click-menu.png)

Las configuraciones disponibles son las siguientes:

| Configuración | Descripción |
| --- | --- |
| [!UICONTROL Insertar panel copiado/visualización] | Permite pegar (&quot;insertar&quot;) un panel copiado o una visualización en otro lugar del proyecto, o en otro proyecto. |
| [!UICONTROL Copiar panel] | Permite hacer clic con el botón derecho y copiar un panel para poder insertarlo en otro lugar del proyecto o en un proyecto diferente. |
| [!UICONTROL Duplicar panel] | Crea un duplicado exacto del panel actual que podrá modificar a continuación. |
| [!UICONTROL Contraer/expandir todos los paneles] | Contrae y expande todos los paneles del proyecto. |
| [!UICONTROL Contraer/expandir todas las visualizaciones del panel] | Contrae y expande todas las visualizaciones del panel actual. |
| [!UICONTROL Editar descripción] | Añade (o edita) una descripción de texto para el panel. |
| [!UICONTROL Obtener vínculo del panel] | Le permite dirigir a los usuarios a un panel concreto de un proyecto. Al hacer clic en el vínculo, el destinatario deberá iniciar sesión antes de que se le dirija al panel exacto al que está vinculado. |
