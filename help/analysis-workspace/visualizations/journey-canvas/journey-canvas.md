---
description: Información general del lienzo de recorrido
title: 'Lienzo del recorrido '
feature: Visualizations
role: User
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: 3c9827c4930568edb2022c699585f716a8ca72fe
workflow-type: tm+mt
source-wordcount: '1988'
ht-degree: 8%

---

# Información general del lienzo de recorrido {#journey-canvas-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_button"
>title="Lienzo del recorrido "
>abstract="Muestra cómo las personas avanzan o abandonan en una serie de puntos de contacto. Se utiliza para recorridos con varios puntos de entrada y rutas, o para analizar recorridos creados en Journey Optimizer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_panel"
>title="Lienzo del recorrido "
>abstract="Analice cómo las personas avanzan o abandonan un recorrido definido. Genere análisis de los recorridos de los usuarios creando un gráfico flexible de nodos y flechas que representen cualquier combinación de eventos, elementos de dimensión y filtros. Arrastre los nodos por el lienzo para reorganizar los eventos y las condiciones del recorrido. A medida que lo haga, los datos se actualizarán en consecuencia. <br/><br/>Los clientes con acceso a Adobe Journey Optimizer pueden analizar los recorridos de Journey Optimizer existentes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_button"
>title="Lienzo del recorrido "
>abstract="Muestra cómo las personas avanzan o abandonan en una serie de puntos de contacto. Se utiliza para viajes con varios puntos de entrada y rutas, o para analizar recorridos creados en Journey Optimizer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_panel"
>title="Lienzo del recorrido "
>abstract="Analice cómo las personas avanzan o abandonan un recorrido definido. Genere análisis de los recorridos de los usuarios creando un gráfico flexible de nodos y flechas que representen cualquier combinación de eventos, elementos de dimensión y filtros. Arrastre los nodos por el lienzo para reorganizar los eventos y las condiciones del recorrido. A medida que lo haga, los datos se actualizarán en consecuencia. <br/><br/>Los clientes con acceso a Adobe Journey Optimizer pueden analizar los recorridos de Journey Optimizer existentes."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_Este artículo documenta la visualización del lienzo de Recorrido en_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**.<br/>No hay ninguna visualización equivalente en **Adobe Analytics**._

>[!ENDSHADEBOX]

La visualización del lienzo de Recorrido le permite analizar y obtener perspectivas profundas sobre los recorridos que proporciona a sus usuarios y clientes. Permite definir un recorrido desde cero o ver uno desde Journey Optimizer y, a continuación, ver cómo abandonaron el recorrido o cómo continuaron en él.

Puede [generar análisis de recorridos de usuario](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) utilizando cualquier combinación de eventos, elementos de dimensión, filtros e intervalos de fechas para crear nodos de recorrido. Conecte los nodos para crear el flujo del recorrido e incluya varias rutas y puntos de decisión. Arrastre nodos en el lienzo para reorganizar los eventos y las condiciones del recorrido. Actualizaciones de datos en tiempo real a medida que realiza cambios.

[Los nodos están conectados](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#logic-when-connecting-nodes) como una &quot;ruta eventual&quot;, lo que significa que los visitantes se cuentan siempre y cuando eventualmente se muevan de una nodo a otra, independientemente de los eventos que ocurran entre los 2 nodos. El tiempo asignado para que los usuarios se desplacen por la ruta viene determinado por la configuración contenedor.

![Lienzo de viaje](assets/journey-canvas.png)

## Funciones principales

Las características clave de la visualización del lienzo del recorrido incluyen:

* Profundo análisis de visita en orden previsto y caídas que se adapta a los viajes de usuario más complejos.

* Un lienzo para mapear y visualizar los diversos puntos de entrada, nodos y rutas de un viaje usuario.

* Interacciones de arrastrar y soltar para agregar componentes al lienzo y para cambiar la posición de los nodos existentes.

* La opción de versión análisis de usuario recorridos dentro del lienzo de Journey o de crearlos automáticamente en función de los viajes de Journey Optimizer.

## Perspectivas potenciales

El lienzo de viaje proporciona información procesable para los recorridos más complejos.

### Ruta con el tasa de conversión más alto {#conversion-rate-caption}

El conocimiento más destacado en el lienzo de Journey se muestra como un título en la parte superior del lienzo.

Esta leyenda resume cuál de todos los caminos en el viaje tuvo el tasa de conversión más alto.

Cuando el recorrido contiene varios nodos inicio, el rótulo tiene gustar este aspecto:

![Lienzo de viaje conocimiento pie de ilustración](assets/journey-canvas-caption.png)

Cuando el viaje contiene una sola inicio nodo, el rótulo tiene gustar este aspecto:

![Lienzo de viaje conocimiento pie de ilustración inicio nodo única](assets/journey-canvas-caption-singlestart.png)

Tenga en cuenta lo siguiente al interpretar este rótulo:

* Una _ruta se define como una nodo_ inicio que está conectada por flechas a un nodo final, con cualquier número de nodos conectados entre ellos.

* El cálculo del tasa de conversión depende del tipo de viaje (el número de nodos inicio y nodos finales contenidos en el viaje, y si los caminos se cruzan entre ellos).

  En la tabla siguiente se describe cómo se calculan las tasas de conversión en función del tipo de recorrido:

  | tipo de recorrido | Cálculo de tasa de conversión | Ejemplo |
  |---------|----------|---------|
  | **Un solo nodo inicial y un solo nodo final** | La tasa de conversión se calcula dividiendo el número del nodo final por el del nodo inicial. | ![Viaje con múltiples inicios que convergen en un nodo común](assets/journey-canvas-single-path.png) |
  | **Un único inicio nodo y varios nodos finales** | La tasa de conversión se calcula encontrando el nodo final con el número más alto y dividiendo ese número por el del inicio nodo. | ![Viaje con múltiples inicios que convergen en un nodo común](assets/journey-canvas-singlestart-multiend.png) |
  | **Varias rutas independientes, cada una de las cuales contiene una única nodo inicio y una única nodo final** | La tasa de conversión se calcula dividiendo el número del nodo final por el del nodo de inicio. La ruta con el tasa de conversión más alto se describe en el pie de ilustración. | ![Viaje con múltiples inicios que convergen en un nodo común](assets/journey-canvas-multi-start-separate.png) |
  | **Múltiples nodos de inicio que en cualquier punto del recorrido convergen en una nodo común** | La tasa de conversión se calcula encontrando el nodo final con el número más alto y dividiendo ese número por el del inicio nodo con el número más bajo. | ![Viaje con múltiples inicios que convergen en un nodo común](assets/journey-canvas-multi-start-converge.png) |

### Abandonos, Abandonos y mucho más

A continuación se muestran algunos ejemplos de otras perspectivas que el lienzo de Recorrido puede ayudar a proporcionar. Puede elegir si estas perspectivas se basan en todas las personas de la vista de datos, todas las personas que iniciaron el recorrido o todas las personas del nodo anterior del recorrido.

#### Visita en orden imprevisto

* Número y porcentaje de personas que completaron el recorrido (llegaron al nodo final)

* Número y porcentaje de personas que llegaron a un nodo determinado del recorrido

* El paso más común que se produjo después o antes de un nodo determinado del recorrido

#### Visita en orden previsto

* Los nodos del recorrido donde las personas cayeron con mayor frecuencia del recorrido (nunca llegaron a ninguno de los nodos inmediatamente siguientes)

#### Datos adicionales para cada nodo

* Añada una dimensión de desglose en cualquier nodo del recorrido para ver datos adicionales de ese nodo específico

## Elija entre visualizaciones de lienzo de Recorrido, Visitas en el orden previsto o Flujo

La visualización de lienzo de viaje tiene similitudes con la [visualización](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) de abandonos y la [visualización](/help/analysis-workspace/visualizations/c-flow/flow.md) de Flujo, pero con diferencias importantes.

### Comprender las diferencias

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### Cuándo usar Journey canvas

El lienzo de viaje es esencial para:

* Las análisis de visitas en el orden previsto que implican viajes con múltiples puntos de entrada y rutas.

* Recorridos no lineales con varios puntos de entrada y rutas, con una secuencia predefinida de páginas.

* Análisis exploratorio y ad hoc basado en un recorrido predefinido.

* Análisis que requiere una métrica principal distinta de Sesión, Persona u Ocurrencias.

* Análisis más profundo de los recorridos que se originaron en Adobe Journey Optimizer.

Use [la tabla anterior](#understand-the-differences) para comprender las diferencias entre las visualizaciones de lienzo de Recorrido, Visitas en el orden previsto y Flujo.

## Analizar Journey Optimizer recorrido

>[!NOTE]
>
>Si su organización no tiene acceso a Journey Optimizer, puede seguir [versión análisis en Journey Canvas](#build-analyses-in-customer-journey-analytics).

Análisis de los recorridos de Journey Optimizer en Journey Canvas proporciona información profunda y procesable sobre cómo las personas interactúan con un viaje.

Cuando analiza un viaje de Journey Optimizer en el lienzo de Journey, el recorrido se muestra con el mismo orden, Secuencia y estructura que en Journey Optimizer. Si realiza cambios significativos en un recorrido dentro del lienzo de Journey, [los cambios ya no se sincronizarán desde Journey Optimizer](#synchronization-between-journey-optimizer-and-journey-canvas).

### Beneficios de analizar los recorridos de Journey Optimizer con Journey Canvas

Journey Canvas proporciona análisis profundos y exhaustivos que no son posibles en Journey Optimizer.

El uso del lienzo de Journey para analizar los recorridos creados en Journey Optimizer ofrece varias ventajas:

* Crear eventos mediante cualquier Customer Journey Analytics dimensiones, métricas filtros o intervalos de fechas.

  En Journey Optimizer, un usuario técnico debe crear un evento para poder añadirlo a un recorrido.

* Crear audiencias en función de un nodo personalizado que cree (inicia el generador de audiencia de Customer Journey Analytics).

  En Journey Optimizer, solo puede crear audiencias para actividades predefinidas.

* Analice las visitas en orden imprevisto y las visita en orden previsto

* Desglose eventos con cualquier dimensión

* Combinar eventos

* Conectar eventos

* Cambiar nombre y eliminar eventos

* Mucho más

### Sincronización entre Journey Optimizer y Journey Canvas

Tenga en cuenta los siguientes comportamientos para comprender la sincronización entre Journey Optimizer y Journey Canvas:

* **La sincronización de datos es unidireccional**

  Después de crear un análisis de un viaje de Journey Optimizer en el lienzo de Journey, los datos se sincronizan en una sola dirección, desde Journey Optimizer hasta Journey Canvas. Esto significa que los cambios realizados en un recorrido en el lienzo de viaje nunca se reflejan en Journey Optimizer.

* **La modificación de un recorrido en el lienzo del recorrido detiene la sincronización**

  Los cambios realizados a un recorrido en Journey Optimizer sincronizar al lienzo [de Journey solo si el viaje no se ha modificado significativamente en el lienzo](#differences-after-modifying-a-journey-in-journey-canvas) de Journey. Después de modificar un recorrido en el lienzo del recorrido, los cambios que realice en el Optimizador de recorridos no se reflejarán en el lienzo del recorrido. Para ver los cambios reflejados en el lienzo del recorrido, puede eliminar y [volver a crear el recorrido en el lienzo del recorrido](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

* **El uso de un vincular &quot;Compartir con cualquiera&quot; requiere que el proyecto se guarde en Customer Journey Analytics después de realizar cambios en Journey Optimizer**

  Cuando se utiliza la vincular &quot;Compartir con cualquiera&quot;, los cambios realizados en Journey Optimizer no se reflejan en el lienzo de Journey hasta que el proyecto se guarda en Customer Journey Analytics.

  Para obtener más información sobre los vínculos &quot;Compartir con cualquiera&quot;, consulte [Compartir un proyecto con cualquier persona (no se requiere longin) en [Proyectos](/help/analysis-workspace/curate-share/share-projects.md) compartidos](/help/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required).

### Diferencias después de modificar un recorrido en el lienzo del recorrido {#differences-after-modifying}

Después de modificar un recorrido de Journey Optimizer en el lienzo de Journey, pueden producirse cambios en procesamiento de datos, las funciones disponibles y el comportamiento de sincronización.

Si realiza una modificación significativa en un recorrido de Journey Optimizer en el lienzo de Journey, pueden producirse cambios en procesamiento de datos, las funciones disponibles y el comportamiento de sincronización. Una modificación significativa incluye cualquiera de los siguientes:

* Adición o eliminación de un nodo

* Agregar o quitar una flecha entre nodos

* Cambio de los componentes de una nodo

Si realiza otros cambios en un recorrido de Journey Optimizer en el lienzo de Journey, como arrastrar un nodo o agregar un desglose, las diferencias descritas en las secciones siguientes no se aplicarán.

>[!NOTE]
>
>Para devolver el viaje a su estado original, puede presionar Ctrl+z después de realizar su primer cambio en el lienzo del viaje. O bien, puede eliminar y [volver a crear el recorrido en el lienzo del recorrido](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)

#### Diferencias en el procesamiento de datos

Después de modificar un recorrido de Journey Optimizer en el lienzo de Journey, es posible que observe cambios en los datos si su recorrido contiene métricas que tienen modelos de atribución no predeterminados.

Esto se debe a que, a diferencia de Journey Optimizer, el lienzo de Recorrido permite aplicar varias dimensiones dentro de un solo recorrido. Esta capacidad significa que no se admite la atribución de [métricas](/help/data-views/component-settings/attribution.md).

#### Diferencias de características

Después de modificar un recorrido de Journey Optimizer en lienzo de Recorrido, las opciones disponibles en el campo desplegable [!UICONTROL **Configuración de flecha**] cambian según las modificaciones que se realicen. Para obtener más información, consulte [Configurar opciones](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

El campo [!UICONTROL **Tipo de nodo**] solo está disponible en Journey Optimizer. No está disponible cuando se ve un recorrido de Journey Optimizer en lienzo de Recorrido, independientemente de si se realizan modificaciones en el recorrido en lienzo de Recorrido.

#### Diferencias de sincronización

Los cambios realizados en un recorrido en Journey Optimizer se sincronizan con el lienzo de Recorrido solo si el recorrido permanece sin modificar en el lienzo de Recorrido.

Después de modificar un recorrido de Journey Optimizer en lienzo de Recorrido, los cambios realizados en el recorrido en Journey Optimizer no se reflejarán en el lienzo de Recorrido. Para ver los cambios reflejados en el lienzo de Recorrido, puede eliminar y [volver a crear el recorrido en el lienzo de Recorrido](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### Diferencias terminológicas entre Journey Optimizer y Customer Journey Analytics

Ciertos términos que significan una cosa en Journey Optimizer significan otra en Customer Journey Analytics. Cuando se utiliza lienzo de Recorrido, se utilizan los términos de Customer Journey Analytics.

| Término | Lienzo del recorrido  | Journey Optimizer |
|---------|----------|---------|
| **Evento** | Una de las varias métricas estándar disponibles en Customer Journey Analytics. Este Métrica cuenta los elementos gustar ingresos, suscripciones o posibles clientes generados. | Categoría de actividad que almacena en déclencheur un recorrido personalizado, como una compra en línea. |

### Analizar un recorrido de Journey Optimizer en lienzo de Recorrido

Para obtener información sobre cómo analizar un recorrido de Journey Optimizer en lienzo de Recorrido, consulte [Configuración de una visualización de lienzo de Recorrido](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

## Generar análisis en lienzo de Recorrido

Puede crear análisis en lienzo de Recorrido basados en cualquier dimensión o métrica disponible en Analysis Workspace. O bien, puede analizar los recorridos creados en Journey Optimizer. Para obtener más información, consulte [Configurar una visualización de lienzo de](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) recorrido.


>[!MORELIKETHIS]
>
> * [Guía para la visualización de Journey Canvas en Adobe Systems Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-guide-to-journey-canvas-visualization-in-adobe-customer/ba-p/737857)

