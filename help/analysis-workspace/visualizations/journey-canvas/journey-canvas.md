---
description: Información general sobre el lienzo de recorrido
title: 'Lienzo de recorrido '
feature: Visualizations
role: User
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: 770320a0b16d26e0755203a3524b000db30cac82
workflow-type: tm+mt
source-wordcount: '1988'
ht-degree: 84%

---

# Información general sobre el lienzo de recorrido {#journey-canvas-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_button"
>title="Lienzo de recorrido "
>abstract="Muestra cómo las personas avanzan o abandonan en una serie de puntos de contacto. Se utiliza para recorridos con varios puntos de entrada y rutas, o para analizar recorridos creados en Journey Optimizer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_panel"
>title="Lienzo de recorrido "
>abstract="Analice cómo las personas avanzan o abandonan un recorrido definido. Cree análisis de los recorridos de usuario creando un gráfico flexible de nodos y flechas que representen cualquier combinación de eventos, elementos de dimensión y segmentos. Arrastre los nodos en el lienzo para reorganizar los eventos y las condiciones del recorrido. A medida que lo haga, los datos se actualizarán en consecuencia. <br/><br/>Los clientes con acceso a Adobe Journey Optimizer pueden analizar los recorridos de Journey Optimizer existentes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_button"
>title="Lienzo de recorrido "
>abstract="Muestra cómo las personas avanzan o abandonan en una serie de puntos de contacto. Se utiliza para recorridos con varios puntos de entrada y rutas, o para analizar recorridos creados en Journey Optimizer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_panel"
>title="Lienzo de recorrido "
>abstract="Analice cómo las personas avanzan o abandonan un recorrido definido. Cree análisis de los recorridos de usuario creando un gráfico flexible de nodos y flechas que representen cualquier combinación de eventos, elementos de dimensión y segmentos. Arrastre los nodos en el lienzo para reorganizar los eventos y las condiciones del recorrido. A medida que lo haga, los datos se actualizarán en consecuencia. <br/><br/>Los clientes con acceso a Adobe Journey Optimizer pueden analizar los recorridos de Journey Optimizer existentes."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_En este artículo se describe la visualización de lienzo de recorrido en_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**.<br/>No hay ninguna visualización equivalente en **Adobe Analytics**._

>[!ENDSHADEBOX]

La visualización de lienzo de recorrido le permite analizar y obtener información detallada sobre los recorridos que proporciona a sus usuarios y clientes. Le permite definir un recorrido desde cero o ver uno de Journey Optimizer y, a continuación, ver cómo los visitantes se fueron (abandonaron) o continuaron (fracasaron) en el recorrido.

Puede [generar análisis de recorridos de usuario](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) utilizando cualquier combinación de eventos, elementos de dimensión, segmentos e intervalos de fechas para crear nodos de recorrido. Conecte los nodos para crear el flujo del recorrido e incluya varias rutas y puntos de decisión. Arrastre los nodos en el lienzo para reorganizar los eventos y las condiciones del recorrido. Los datos se actualizan en tiempo real a medida que realiza cambios.

[Los nodos están conectados](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#logic-when-connecting-nodes) como una &quot;ruta eventual&quot;, lo que significa que los visitantes se contabilizan siempre y cuando finalmente se desplacen un nodo al otro, independientemente de los eventos que se produzcan entre los dos nodos. El tiempo asignado para que los usuarios se desplacen por la ruta viene determinado por la configuración del contenedor.

![Lienzo de recorrido](assets/journey-canvas.png)

## Funciones principales

Entre las principales características de la visualización de lienzo de recorrido se incluyen:

* Un análisis en profundidad de la visita en el orden previsto y de la visita de paso que se adapta a los recorridos de usuario más complejos.

* Un lienzo para asignar y visualizar los distintos puntos de entrada, nodos y rutas de un recorrido de usuario.

* Interacciones de arrastrar y soltar para añadir componentes al lienzo y para cambiar la posición de los nodos existentes.

* La opción para generar análisis de recorridos de usuario dentro del lienzo de recorrido o para crearlos automáticamente en función de los recorridos de Journey Optimizer.

## Información potencial

El lienzo de recorrido proporciona información práctica para los recorridos más complejos.

### Ruta con la tasa de conversión más alta {#conversion-rate-caption}

El dato más destacado del lienzo de recorrido se muestra como un subtítulo en la parte superior del propio lienzo.

En este subtítulo se resume cuál de todas las rutas del recorrido tuvo la tasa de conversión más alta.

Cuando el recorrido contiene varios nodos de inicio, el subtítulo se muestra de la forma siguiente:

![Subtítulo del lienzo de recorrido](assets/journey-canvas-caption.png)

Cuando el recorrido contiene un solo nodo de inicio, el subtítulo se muestra de la forma siguiente:

![Nodo de inicio único del subtítulo de información del lienzo de recorrido](assets/journey-canvas-caption-singlestart.png)

Tenga en cuenta lo siguiente al interpretar este subtítulo:

* Una _ruta_ se define como un nodo de inicio que está conectado mediante flechas a un nodo final, con cualquier número de nodos conectados entre ellos.

* El cálculo de la tasa de conversión depende del tipo de recorrido (el número de nodos iniciales y finales que contiene el recorrido y si las rutas se cruzan entre sí).

  En la tabla siguiente se describe cómo se calculan las tasas de conversión en función del tipo de recorrido:

  | Tipo de recorrido | Cálculo de la tasa de conversión | Ejemplo |
  |---------|----------|---------|
  | **Un solo nodo inicial y un solo nodo final** | La tasa de conversión se calcula dividiendo el número del nodo final por el del nodo inicial. | ![Recorrido con varios inicios que convergen en un nodo común](assets/journey-canvas-single-path.png) |
  | **Un solo nodo inicial y varios nodos finales** | La tasa de conversión se calcula buscando el nodo final con el número más alto y dividiendo ese número por el del nodo inicial. | ![Recorrido con varios inicios que convergen en un nodo común](assets/journey-canvas-singlestart-multiend.png) |
  | **Varias rutas independientes, cada una de las cuales contiene un solo nodo inicial y un solo nodo final** | La tasa de conversión se calcula dividiendo el número del nodo final por el del nodo inicial. La ruta con la tasa de conversión más alta se describe en el subtítulo. | ![Recorrido con varios inicios que convergen en un nodo común](assets/journey-canvas-multi-start-separate.png) |
  | **Varios nodos de inicio que en cualquier punto del recorrido convergen en un nodo común** | La tasa de conversión se calcula buscando el nodo final con el número más alto y dividiendo ese número por el del nodo inicial con el número más bajo. | ![Recorrido con varios inicios que convergen en un nodo común](assets/journey-canvas-multi-start-converge.png) |

### Visita de paso, visita en orden previsto y mucho más

A continuación se muestran algunos ejemplos de otras informaciones que el lienzo de recorrido puede ayudar a proporcionar. Puede decidir si estas informaciones se basan en todas las personas de la vista de datos, todas las personas que iniciaron el recorrido o todas las personas del nodo anterior del recorrido.

#### Visita en orden imprevisto

* El número y porcentaje de personas que completaron el recorrido (llegaron al nodo final)

* El número y porcentaje de personas que llegaron a un nodo determinado del recorrido

* El paso más habitual que se produjo después o antes de un nodo determinado del recorrido

#### Visita en orden previsto

* Los nodos del recorrido en el que las personas abandonaron con mayor frecuencia el recorrido (no llegaron a ninguno de los nodos inmediatamente posteriores)

#### Datos adicionales para cada nodo

* Añada una dimensión de desglose en cualquier nodo del recorrido para ver los datos adicionales de ese nodo específico

## Elija entre visualizaciones Lienzo de recorrido, Visita en orden previsto o Flujo

La visualización de Lienzo de recorrido tiene similitudes con la [visualización Visita en orden previsto](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) y la [visualización Flujo](/help/analysis-workspace/visualizations/c-flow/flow.md), pero con diferencias importantes.

### Conocer las diferencias

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### Cuándo utilizar el lienzo de recorrido

El lienzo de recorrido es esencial para lo siguiente:

* Análisis de visitas en el orden previsto que implica recorridos con varios puntos de entrada y rutas.

* Recorridos no lineales con varios puntos de entrada y rutas, con una secuencia predefinida de páginas.

* Análisis exploratorio y ad hoc basado en un recorrido predefinido.

* Análisis que requiere una métrica principal distinta de Sesión, Persona u Ocurrencias.

* Análisis más profundo de los recorridos que se originaron en Adobe Journey Optimizer.

Utilice la [la tabla anterior](#understand-the-differences) para conocer las diferencias entre las visualizaciones Lienzo de recorrido, Visita en orden previsto y Flujo.

## Análisis de los recorridos de Journey Optimizer

>[!NOTE]
>
>Si su organización no tiene acceso a Journey Optimizer, todavía puede [crear análisis en el lienzo de recorrido](#build-analyses-in-customer-journey-analytics).

El análisis de recorridos de Journey Optimizer en el lienzo de recorrido proporciona información en profundidad y práctica sobre cómo las personas interactúan con un recorrido.

Cuando se analiza un recorrido de Journey Optimizer en el lienzo de recorrido, el recorrido se muestra con el mismo orden, la misma secuencia y misma estructura que en Journey Optimizer. Si realiza cambios significativos en un recorrido dentro del lienzo de recorrido, [los cambios ya no se sincronizan desde Journey Optimizer](#synchronization-between-journey-optimizer-and-journey-canvas).

### Ventajas del análisis de recorridos de Journey Optimizer con el lienzo de recorridos

El lienzo de recorrido ofrece un análisis en profundidad y exhaustivo que no es posible en Journey Optimizer.

Usar el lienzo de recorrido para analizar los recorridos creados en Journey Optimizer ofrece varias ventajas:

* Cree eventos utilizando cualquier dimensión, métrica, segmento o intervalo de fechas de Customer Journey Analytics.

  En Journey Optimizer, un usuario técnico debe crear un evento para poder añadirlo a un recorrido.

* Cree públicos en función de un nodo personalizado que haya creado (inicia el generador de públicos de Customer Journey Analytics).

  En Journey Optimizer, solo puede crear públicos para actividades predefinidas.

* Analizar la visita de paso y la visita en el orden previsto

* Desglosar eventos con cualquier dimensión

* Combinar eventos

* Conectar eventos

* Renombrar y eliminar eventos

* Mucho más

### Sincronización entre Journey Optimizer y el lienzo de recorrido

Tenga en cuenta los siguientes comportamientos para comprender la sincronización entre Journey Optimizer y los lienzos de Recorrido:

* **La sincronización de datos es unidireccional**

  Después de crear un análisis de un recorrido de Journey Optimizer en el lienzo de recorrido, los datos se sincronizan en una sola dirección, de Journey Optimizer al lienzo de recorrido. Esto significa que los cambios realizados en un recorrido en el lienzo de recorrido nunca se reflejan en Journey Optimizer.

* **Al modificar un recorrido en el lienzo del Recorrido, se detiene la sincronización**

  Los cambios realizados en un recorrido de Journey Optimizer se sincronizan con el lienzo de Recorrido [sólo si el recorrido no se ha modificado significativamente en el lienzo de Recorrido](#differences-after-modifying-a-journey-in-journey-canvas). Después de modificar un recorrido en el lienzo de recorrido, los cambios realizados en el recorrido en Journey Optimizer no se reflejarán en el lienzo de recorrido. Para ver los cambios reflejados en el lienzo de recorrido, puede eliminar y [volver a crear el recorrido en el lienzo de recorrido](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

* **El uso del vínculo &quot;Compartir con alguien&quot; requiere que el proyecto se guarde en Customer Journey Analytics después de realizar cambios en Journey Optimizer**

  Al utilizar el vínculo &quot;Compartir con cualquiera&quot;, los cambios realizados en Journey Optimizer no se reflejan en los lienzos de Recorrido hasta que el proyecto se guarda en Customer Journey Analytics.

  Para obtener más información sobre los vínculos &quot;Compartir con quien quieras&quot;, consulta [Compartir un proyecto con quien quieras (ya no es obligatorio)](/help/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required) en [Compartir proyectos](/help/analysis-workspace/curate-share/share-projects.md).

### Diferencias después de modificar un recorrido en el lienzo de recorrido {#differences-after-modifying}

Después de modificar un recorrido de Journey Optimizer en el lienzo de recorrido, pueden producirse cambios en el procesamiento de datos, las funciones disponibles y el comportamiento de la sincronización.

Si realiza una modificación significativa en un recorrido de Journey Optimizer en el lienzo de recorrido, pueden producirse cambios en el procesamiento de datos, las funciones disponibles y el comportamiento de la sincronización. Una modificación significativa incluye cualquiera de las siguientes opciones:

* Añadir o eliminar un nodo

* Añadir o eliminar una flecha entre nodos

* Cambiar los componentes de un nodo

Si realiza otros cambios en un recorrido de Journey Optimizer en el lienzo de recorrido, como arrastrar un nodo o añadir un desglose, no se aplicarán las diferencias que se describen en las secciones siguientes.

>[!NOTE]
>
>Para devolver el recorrido a su estado original, puede pulsar Ctrl+z después de realizar el primer cambio en el lienzo de recorrido. O bien, puede eliminar y [volver a crear el recorrido en lienzo de recorrido](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)

#### Diferencias en el procesamiento de datos

Después de modificar un recorrido de Journey Optimizer en lienzo de recorrido, es posible que observe cambios en los datos si el recorrido contiene métricas que tienen modelos de atribución no predeterminados.

Esto se debe a que, a diferencia de Journey Optimizer, el lienzo de recorrido permite aplicar varias dimensiones dentro de un solo recorrido. Esta capacidad significa que no se admite la atribución de [métricas](/help/data-views/component-settings/attribution.md).

#### Diferencias de características

Después de modificar un recorrido de Journey Optimizer en lienzo de Recorrido, las opciones disponibles en el campo desplegable [!UICONTROL **Configuración de flecha**] cambian según las modificaciones que se realicen. Para obtener más información, consulte [Configuración de ajustes](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

El campo [!UICONTROL **Tipo de nodo**] solo está disponible en Journey Optimizer. No está disponible cuando se ve un recorrido de Journey Optimizer en el lienzo de recorrido, independientemente de si se realizan modificaciones en el recorrido en el lienzo de recorridos.

#### Diferencias de sincronización

Los cambios realizados en un recorrido en Journey Optimizer se sincronizan con el lienzo de recorrido solo si el recorrido permanece sin modificar en el lienzo de recorrido.

Después de modificar un recorrido de Journey Optimizer en el lienzo de recorrido, los cambios realizados en el recorrido en Journey Optimizer no se reflejarán en el lienzo de recorrido. Para ver los cambios reflejados en el lienzo de recorridos, puede eliminar y [volver a crear el recorrido en el lienzo de recorrido](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### Diferencias terminológicas entre Journey Optimizer y Customer Journey Analytics

Determinados términos que significan una cosa en Journey Optimizer significan otra en Customer Journey Analytics. Cuando se utiliza lienzo de recorrido, se utilizan los términos de Customer Journey Analytics.

| Término | Lienzo de recorrido  | Journey Optimizer |
|---------|----------|---------|
| **Evento** | Una de las diversas métricas estándar disponibles en Customer Journey Analytics. Esta métrica cuenta aspectos como los ingresos, las suscripciones o los posibles clientes generados.  | La categoría de actividad que activa un recorrido personalizado, como una compra en línea. |

### Análisis de un recorrido de Journey Optimizer en el lienzo de recorridos

Para obtener información sobre cómo analizar un recorrido de Journey Optimizer en el lienzo de recorridos, consulte [Configuración de una visualización de lienzo de recorridos](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

## Generar análisis en el lienzo de recorridos

Puede crear análisis en el lienzo de recorridos que estén basados en cualquier dimensión o métrica disponible en Analysis Workspace. O bien, puede analizar los recorridos creados en Journey Optimizer. Para obtener más información, consulte [Configuración de una visualización de lienzo de recorridos](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).


>[!MORELIKETHIS]
>
> * [Guía para la visualización del lienzo de Recorrido en Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-guide-to-journey-canvas-visualization-in-adobe-customer/ba-p/737857)

