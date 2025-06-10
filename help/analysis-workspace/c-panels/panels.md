---
description: Un panel es una colección de tablas y visualizaciones
title: Resumen de paneles
feature: Panels
exl-id: be3e34a0-06c1-4200-b965-96084c2912fd
role: User
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '2129'
ht-degree: 97%

---

# Resumen de paneles

Un [!UICONTROL panel] es una colección de tablas y visualizaciones. Puede acceder a los paneles en el icono de la parte superior izquierda de Workspace o desde un [panel en blanco](/help/analysis-workspace/c-panels/blank-panel.md). Los paneles son útiles cuando desea organizar sus proyectos según períodos de tiempo, vistas de datos o casos de uso de análisis.

## Tipos de panel

Los siguientes tipos de panel están disponibles en Analysis Workspace para [!UICONTROL Customer Journey Analytics]:

| Nombre del panel | Descripción |
| --- | --- |
| [Panel en blanco](/help/analysis-workspace/c-panels/blank-panel.md) | Elija entre los paneles y las visualizaciones disponibles para iniciar el análisis. |
| [Atribución](attribution.md) | Compare y visualice rápidamente los modelos de atribución utilizando cualquier dimensión y métrica de conversión. |
| [Experimentación](experimentation.md) | Compare diferentes variaciones de experiencias de usuario, marketing o mensajería para determinar cuál es la mejor manera de impulsar un resultado específico. |
| [Freeform](freeform-panel.md) | Realice comparaciones y desgloses ilimitados y, a continuación, añada visualizaciones para contar una historia de datos enriquecida. |
| [Audiencia media por minuto de medios](average-minute-audience-panel.md) | Analizar audiencia media por minuto para un fragmento de contenido específico o durante un período de tiempo personalizado. |
| [Espectadores simultáneos de medios ](media-concurrent-viewers.md) | Analice los visualizadores simultáneos a lo largo del tiempo, con detalles sobre la frecuencia máxima de acceso y la capacidad de desglosar datos y compararlos. |
| [Tiempo invertido en la reproducción de contenido](/help/analysis-workspace/c-panels/media-playback-time-spent.md) | Analiza el tiempo invertido en la reproducción para comprender dónde se produjo el pico de concurrencia o dónde se produjeron los descensos. |
| [Elemento siguiente o anterior](next-previous.md) | Mostrar las páginas siguientes o anteriores a las que se dirigen los usuarios. |
| [Información rápida](quickinsight.md) | Crea rápidamente una tabla de forma libre y una visualización complementaria para analizar y descubrir información de manera más rápida. |


Los paneles [!UICONTROL Información rápida], [!UICONTROL En blanco] y [!UICONTROL Forma libre] son buenos lugares para iniciar el análisis, mientras que[!UICONTROL Atribución] se presta para análisis más avanzados. Hay un ![AddCircle](/help/assets/icons/AddCircle.svg) disponible en la parte inferior del lienzo, para que puedas agregar paneles en blanco en cualquier momento.

El panel inicial predeterminado es [!UICONTROL Forma libre], pero también puede convertir el [Panel en blanco](/help/analysis-workspace/c-panels/blank-panel.md) o en [Información rápida](/help/analysis-workspace/c-panels/quickinsight.md) predeterminado. Ver [preferencias de proyectos y análisis](/help/analysis-workspace/user-preferences.md#projects--analyses-preferences).


## Crear un panel

Para crear un panel:

* Arrastra y suelta un panel del panel izquierdo **[!UICONTROL Paneles]** al lienzo.
* Selecciona un panel del [panel en blanco](blank-panel.md).
* Usa el menú **[!UICONTROL Insertar]** en Workspace y selecciona el panel. También puedes usar cualquiera de los [métodos abreviados](../build-workspace-project/fa-shortcut-keys.md) para insertar un panel.

  ![Crear un panel](assets/create-panel.png)

Puede realizar lo siguiente:

* Selecciona ![AddCircle](/help/assets/icons/AddCircle.svg) **en** cualquier panel para agregar otra visualización. Aparece una ventana emergente que te permite seleccionar una visualización.

  ![Imagen emergente que muestra posibles visualizaciones](assets/blank-panel.png)

  | Seleccionar… | Para crear un filtro: |
  |---|---|
  | ![Tabla](/help/assets/icons/Table.svg) | [Tabla de forma libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) |
  | ![Líneas](/help/assets/icons/GraphTrend.svg) | [Línea](/help/analysis-workspace/visualizations/line.md) |
  | ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [Barra](/help/analysis-workspace/visualizations/bar.md) |
  | ![123](/help/assets/icons/123.svg) | [Número de resumen](/help/analysis-workspace/visualizations/summary-number-change.md) |
  | ![Texto](/help/assets/icons/Text.svg) | [Texto](/help/analysis-workspace/visualizations/text.md) |
  | ![Canal de conversión](/help/assets/icons/ConversionFunnel.svg) | [Visita en orden previsto](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) |
  | ![Flujo de trabajo](/help/assets/icons/GraphPathing.svg) | [Flujo](/help/analysis-workspace/visualizations/c-flow/flow.md) |
  | ![GraphAreaStacked](/help/assets/icons/GraphAreaStacked.svg) | [Area stacked](/help/analysis-workspace/visualizations/area.md) |
  | ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [Tabla de cohorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md) |
  | ![GraphBullet](/help/assets/icons/GraphBullet.svg) | [Bullet](/help/analysis-workspace/visualizations/bullet-graph.md) |
  | ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [Anillo](/help/analysis-workspace/visualizations/donut.md) |
  | ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [Cambio de resumen](/help/analysis-workspace/visualizations/summary-number-change.md) |
  | ![Histograma](/help/assets/icons/Histogram.svg) | [Histograma](/help/analysis-workspace/visualizations/histogram.md) |
  | ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [Dispersión](/help/analysis-workspace/visualizations/scatterplot.md) |
  | ![Tipo](/help/assets/icons/TwoDots.svg) | [Venn](/help/analysis-workspace/visualizations/venn.md) |
  | ![GraphTree](/help/assets/icons/GraphTree.svg) | [Gráfico de rectángulos](/help/analysis-workspace/visualizations/treemap.md) |

* Selecciona ![AddCircle](/help/assets/icons/AddCircle.svg) **fuera** del último panel del área de trabajo para agregar otro [panel en blanco](blank-panel.md).


## Vista de datos

Cada panel está asociado con una [vista de datos](/help/data-views/data-views.md), identificada por ![Datos](/help/assets/icons/Data.svg) **[!UICONTROL *nombre de la vista de datos *]**&#x200B;en el menú desplegable de la parte superior derecha del panel.

Al crear un proyecto de Workspace en blanco, la vista de datos predeterminada para el panel inicial es la vista de datos en la que trabajaste por última vez en Customer Journey Analytics.

Al crear un panel nuevo, la vista de datos predeterminada se basa en la vista de datos del panel en el que trabajaste por última vez en el proyecto de Workspace.

>[!IMPORTANT]
>
>La vista de datos seleccionada determina qué dimensiones, métricas y segmentos están disponibles para crear visualizaciones en un panel.
>
>
>Al cambiar una vista de datos de un panel, es posible que algunos de los componentes no estén disponibles en esa nueva vista de datos. Este cambio puede provocar que la visualización no se represente correctamente. Puedes ver advertencias como las siguientes:
>
>* Este panel contiene componentes que no están habilitados en la vista de datos seleccionada. Cambia la vista de datos o habilita los componentes necesarios en la vista de datos.
>* No se puede procesar la visualización: comprueba las columnas y filas para asegurarte de que contienen componentes válidos.
>

## Calendario

El calendario del panel controla el intervalo de la creación de informes de las tablas y visualizaciones de un panel.

>[!NOTE]
>
>Si se utiliza un componente de intervalo de fechas ![Calendario](/help/assets/icons/Calendar.svg) dentro de una visualización o panel (por ejemplo, como segmento), el componente de intervalo de fechas anula el calendario del panel.
>


![La ventana del calendario que muestra el intervalo de fechas seleccionado.](assets/panel-calendar.png)

1. Selecciona un intervalo de fechas seleccionando primero la fecha de inicio y, a continuación, la fecha de finalización.
También puede seleccionar un **[!UICONTROL ajuste preestablecido]** en el menú desplegable [!UICONTROL *Seleccionar un ajuste preestablecido*].

1. De manera opcional, selecciona **[!UICONTROL Mostrar configuración avanzada]** para:

   * Especifica **[!UICONTROL Hora de inicio]** y **[!UICONTROL Hora de finalización]** distintas de las `12:00 AM` (`0:00`) y `11:59 PM` (`23:59`) predeterminadas. Los tiempos de finalización siempre incluyen 59 segundos. Para un intervalo de fechas que abarca muchos días, la hora de inicio se aplica al primer día del intervalo de fechas y la hora de finalización se aplica al último día del intervalo de fechas. Usa **[!UICONTROL (Restablecer valores de tiempo)]** para restablecer los valores predeterminados de las horas de inicio y finalización.
   * **[!UICONTROL Hacer que los componentes del intervalo de fecha sean relativos al calendario del panel]**. Si está desactivado, los componentes de intervalo de fechas utilizados en el panel son relativos a la hora actual. Si está habilitado, los componentes de intervalo de fechas utilizados en el panel están relacionados con el calendario del panel.
   * **[!UICONTROL Usar fechas móviles]**. Si se habilita, los intervalos de fechas preestablecidos como **[!UICONTROL últimos 7 días completos]** se actualizarán dinámicamente como progreso de fecha y hora actual. Si está desactivado, estos ajustes preestablecidos no se actualizan una vez aplicados.

     ![Fechas móviles](assets/calendar-rolling.png)

     Puedes seleccionar el texto entre corchetes (por ejemplo **[!UICONTROL inicio fijo - desplazamiento diario]**) para ampliar el panel y especificar detalles para **[!UICONTROL Inicio]** y **[!UICONTROL Fin]**.

      1. Selecciona **[!UICONTROL Inicio de]**, **[!UICONTROL Fin de]** o **[!UICONTROL Día fijo]**.
      1. Cuando hayas seleccionado **[!UICONTROL Inicio de]** o **[!UICONTROL Final de]**, puedes generar una expresión completa. Por ejemplo: **[!UICONTROL Fin de]** **[!UICONTROL año actual]** **[!UICONTROL más]** `1` **[!UICONTROL día]**. Elige el valor apropiado para cada parte individual de la expresión.
         * Selecciona valor para actual. Por ejemplo, **[!UICONTROL año actual]**.
         * Selecciona un valor para realizar cálculos adicionales. Por ejemplo, **[!UICONTROL plus]**.
         * Cuando hayas especificado un cálculo adicional, especifica un valor. Por ejemplo `1`.
         * Cuando hayas especificado un cálculo adicional, selecciona el período de tiempo que deseas utilizar para el cálculo. Por ejemplo, **[!UICONTROL día]**.

     Selecciona **[!UICONTROL Ocultar detalles]** para ocultar los detalles del cálculo de fechas móviles.

1. Selecciona **[!UICONTROL Aplicar]** para aplicar el intervalo de fechas al panel desde el que se invocó el calendario.
Selecciona **[!UICONTROL Aplicar a todos los paneles]** para aplicar el intervalo de fechas a todos los paneles del proyecto de Workspace.


## Zona de colocación {#dropzone}

La zona de colocación del panel permite aplicar segmentos y segmentos desplegables a todas las tablas y visualizaciones de un panel. Puede aplicar uno o varios segmentos a un panel.

### Segmentos 

Arrastre y suelte cualquier segmento del panel izquierdo en la zona de colocación del panel para empezar a segmentar el panel. Repita este proceso para añadir segmentos adicionales al panel. Los segmentos aparecen uno al lado del otro en la parte superior del panel.

![El panel izquierdo muestra las métricas disponibles y la métrica Cliente móvil arrastrada a la zona de colocación del panel.](assets/segment-filter.png)

#### Segmentos rápidos

Los componentes que no son segmentos también pueden arrastrarse directamente a la zona de colocación para crear segmentos rápidos, lo que le ahorrará el tiempo y el esfuerzo de ir al [Generador de segmentos](/help/components/segments/seg-builder.md). Los segmentos creados de este modo se definen automáticamente como segmentos de nivel de evento. Esta definición puede modificarse rápidamente seleccionando ![Editar](/help/assets/icons/Edit.svg) junto al nombre del segmento.


Para obtener más información, consulte [Segmentos rápidos](/help/components/segments/seg-quick.md).

![Segmentos ad hoc que se hacen públicos y se sueltan en la zona de colocación](assets/adhoc-segment-filter.png)

### Segmentos desplegables

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Segmentos desplegables](https://video.tv.adobe.com/v/327488?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

{{videoaa}}

>[!ENDSHADEBOX]


#### Segmentos desplegables estáticos

Los segmentos desplegables estáticos permiten interactuar con los datos de forma controlada. Por ejemplo, puede añadir un segmento desplegable para Tipos de dispositivos móviles, de modo que pueda segmentar el panel por tabletas, teléfonos móviles o equipos de escritorio.

Los segmentos desplegables estáticos también pueden utilizarse para consolidar muchos proyectos en uno solo. Por ejemplo, si tiene muchas versiones del mismo proyecto con diferentes segmentos de país aplicados, puede consolidar todas las versiones en un único proyecto y añadir un segmento desplegable de país.

![Segmentos desplegables estáticos que muestran el segmento &quot;Directo&quot; del canal de mercado resaltado. ](assets/dropdown-filter-intro.png)

##### Creación de segmentos desplegables dinámicos

* Para los segmentos desplegables que utilizan elementos de dimensión, selecciona una sola dimensión del panel izquierdo y suéltala en la zona desplegable del panel mientras mantiene pulsado ⇧ (*mayús*).  Esta acción crea un segmento desplegable con todos los elementos de dimensión que están asociados con esa dimensión.

  O bien, si desea que el segmento desplegable incluya solo elementos de dimensión específicos asociados a una dimensión, haga clic en el icono de flecha derecha situado junto a la dimensión deseada en el panel izquierdo. Esta acción expone todos los elementos de dimensión disponibles. Selecciona varios elementos de dimensión de esta lista usando ⇧+![Select](/help/assets/icons/Select.svg) (*shift* + *select*) o ^+![Select](/help/assets/icons/Select.svg) (*control* + *select*) y, a continuación, suéltalos en la zona de colocación del panel **mientras mantienes presionado** ⇧.

* Para los segmentos desplegables que utilizan un único tipo de componente (por ejemplo, solo dimensiones, o solo segmentos, o solo métricas), seleccione varios elementos del mismo tipo en el panel izquierdo mediante ⇧+![Seleccionar](/help/assets/icons/Select.svg) o ^+![Seleccionar](/help/assets/icons/Select.svg). A continuación, suelte los elementos en la zona de colocación del panel **mientras mantiene** ⇧.

  Se crea un único segmento desplegable con los componentes seleccionados.

* Para los segmentos desplegables que utilizan una mezcla de tipos de componentes (como 2 métricas y 3 segmentos), seleccione varios componentes utilizando ⇧+![Seleccionar](/help/assets/icons/Select.svg) o ^+![Seleccionar](/help/assets/icons/Select.svg). Coloque la selección en la zona desplegable del panel **mientras mantiene pulsado** ⇧. En este contexto, todos los tipos de componentes se tratan como segmentos desplegables independientes. Por ejemplo, si incluye tanto elementos de métrica como de dimensión en su selección, se crearán dos segmentos desplegables separados: un segmento desplegable incluirá elementos de dimensión y el otro incluirá métricas.

Un segmento desplegable proporciona las siguientes opciones de menú contextual:

* **[!UICONTROL Eliminar desplegable]**: Elimina el segmento desplegable del panel.
* **[!UICONTROL Eliminar etiqueta]**: Elimina el texto que aparece sobre un segmento desplegable. Para modificar la etiqueta, desplácese sobre ella y seleccione ![Editar etiqueta del segmento desplegable](/help/assets/icons/Edit.svg).
* **[!UICONTROL Añadir etiqueta]**: Cuando añade un segmento desplegable a un proyecto, se establece automáticamente una etiqueta con el nombre del componente. Si elimina la etiqueta, puede añadirla de nuevo con esta opción.
* **[!UICONTROL Requiere selección]**: Requiere que se fije un segmento en el panel.

##### Utilizar segmentos desplegables estáticos

Los usuarios pueden utilizar el menú desplegable de segmentos de cualquiera de las siguientes formas para segmentar el panel:

* Aplique un único segmento al panel seleccionando el segmento en el segmento desplegable.

* Aplique varios segmentos al panel seleccionando más de uno en el segmento desplegable. El panel se segmenta para incluir cualquiera de los segmentos seleccionados.


#### Segmentos desplegables dinámicos

Los segmentos desplegables dinámicos le permiten determinar los valores disponibles en función de los datos dentro del intervalo de informes del panel y los valores de otros segmentos desplegables. Por ejemplo, puede crear dos desplegables dinámicos utilizando las dimensiones Países y Ciudades. Al seleccionar un país en el menú desplegable **[!UICONTROL Países]**, el menú desplegable **[!UICONTROL Ciudades]** se ajusta dinámicamente para mostrar solo las ciudades de ese país.

Este mismo concepto se aplica a todas las dimensiones; solo son visibles los elementos de dimensión que aparecen dentro del intervalo de fechas y los segmentos seleccionados del panel. Los elementos de dimensión seleccionados en los segmentos desplegables estáticos afectan a los valores disponibles en los segmentos desplegables dinámicos. Sin embargo, lo contrario no es verdadero; los elementos de dimensión seleccionados en los segmentos desplegables dinámicos no afectan a los valores disponibles en los segmentos desplegables estáticos.

La selección manual de elementos de dimensión está disponible si prevé que se recopilará un determinado elemento de dimensión en el futuro. También puede borrar un segmento desplegable dinámico para que no contenga un valor, lo que permitirá que otros segmentos desplegables dinámicos contengan más valores. Seleccione **[!UICONTROL Restablecer todo]** para borrar la selección de todos los segmentos desplegables de ese panel.

Para crear un segmento desplegable dinámico, haga lo siguiente:

* Arrastre y suelte una sola dimensión en la zona desplegable del panel **mientras mantiene pulsado** ⇧.

Tenga en cuenta que los segmentos desplegables dinámicos no están disponibles para métricas, segmentos o intervalos de fechas.

Al hacer clic con el botón derecho en un segmento desplegable dinámico, se proporcionan las mismas opciones que en los segmentos desplegables estáticos.


## Menú contextual

Para obtener más funcionalidades, haz clic con el botón derecho en el encabezado del panel.

![Las opciones del botón derecho para un encabezado de panel.](assets/right-click-menu.png)

Las opciones disponibles son las siguientes:

| Opción | Descripción |
| --- | --- |
| **[!UICONTROL Insertar panel copiado]** | Permite pegar un panel copiado en otro lugar del proyecto o en otro proyecto. |
| **[!UICONTROL Insertar visualización copiada]** | Pega una visualización copiada en otro lugar dentro del panel, proyecto o en un proyecto diferente. |
| **[!UICONTROL Aplicar el grupo de informes a todos los paneles]** | Aplica la vista de datos de este panel a todos los demás paneles del proyecto. |
| **[!UICONTROL Copiar panel]** | Copia un panel para poder insertarlo en otro lugar del proyecto o en un proyecto completamente diferente. |
| **[!UICONTROL Duplicar panel]** | Crea un duplicado exacto del panel actual que podrá modificar a continuación. |
| **[!UICONTROL Contraer todos los paneles]** | Contraer todos los paneles del proyecto. |
| **[!UICONTROL Ampliar todos los paneles]** | Ampliar todos los paneles del proyecto. |
| **[!UICONTROL Contraer todas las visualizaciones del panel]** | Contraer todas las visualizaciones del panel actual. |
| **[!UICONTROL Ampliar todas las visualizaciones del panel]** | Ampliar todas las visualizaciones del panel actual. |
| **[!UICONTROL Editar descripción]** | Añade (o edita) una descripción de texto para el panel. |
| **[!UICONTROL Obtener vínculo del panel]** | Dirigir a los usuarios a un panel concreto de un proyecto. Al hacer clic en el vínculo, el destinatario deberá iniciar sesión antes de que se le dirija al panel exacto al que está vinculado. |

## Configuración

Algunos paneles (como [!UICONTROL Atribución], [!UICONTROL Experimentación], [!UICONTROL Audiencia media por minuto de medios] y otros) tienen un cuadro de diálogo de configuración para ayudarte a crear la visualización. Usa ![Editar](/help/assets/icons/Edit.svg) en la parte superior del panel para acceder y cambiar la configuración.

![Configurar un panel](/help/analysis-workspace/c-panels/assets/configure-panel.png)
