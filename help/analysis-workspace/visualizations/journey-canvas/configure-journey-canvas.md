---
description: Configuración de una visualización de lienzo de Recorrido
title: Lienzo de recorrido
feature: Visualizations
role: User
hide: true
hidefromtoc: true
exl-id: 53984934-6fba-4f15-aeeb-d91039260553
source-git-commit: bd50c5bdcce0617da78eed918338e44474419e31
workflow-type: tm+mt
source-wordcount: '4359'
ht-degree: 1%

---

# Configuración de una visualización de lienzo de Recorrido

{{release-limited-testing}}

La visualización del lienzo de Recorrido le permite analizar y obtener perspectivas profundas sobre los recorridos que proporciona a sus usuarios y clientes.

## información general sobre lienzo de recorrido

Consulte [descripción general del lienzo de Recorrido](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) para obtener más información sobre el lienzo de Recorrido, incluyendo:

* Funciones principales

* Perspectivas potenciales

* Diferencias entre el lienzo de Recorrido y las visitas en orden previsto

* Detalles sobre el análisis de Journey Optimizer recorrido

* Y más

## Empezar a crear una visualización de lienzo de Recorrido

1. Agregue un panel en blanco al proyecto, seleccione el icono [!UICONTROL **Visualizaciones**] en el carril izquierdo y, a continuación, arrastre la visualización [!UICONTROL **lienzo de Recorrido**] al panel.

   O

   Agregue una visualización del lienzo de Recorrido de cualquiera de las formas descritas en la sección [Agregar visualizaciones a un panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) de [Información general sobre visualizaciones](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Especifique la siguiente información básica:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **Métrica principal**] | La métrica principal afecta a los siguientes aspectos de la visualización del lienzo de Recorrido:  <ul><li>Define cómo se mueven las personas a través del recorrido.</li><li>El número total que se muestra en cada nodo.<p>Por ejemplo, si Personas es la métrica principal, cada nodo muestra el número de personas que llegaron a ese nodo en el recorrido.</p></li><li>El porcentaje que se muestra en cada nodo. (Una vez creada la visualización, puede elegir mostrar el porcentaje del total o del nodo de inicio).</li><p>Por ejemplo, si Personas es la métrica principal, cada nodo muestra el porcentaje de personas que llegaron a ese nodo en el recorrido (el porcentaje del total o del nodo de inicio).</p></li><li>Cuando se añade una dimensión a la visualización, se añaden los 3 nodos principales de la visualización en función de la métrica principal.</li></ul> |
   | [!UICONTROL **Métrica secundaria**] | La métrica secundaria es opcional. Cuando se selecciona uno, se muestra la siguiente información en cada nodo debajo de la métrica principal: <ul><li>El número total<p>Por ejemplo, si Sesiones es la métrica secundaria, cada nodo muestra el número de sesiones que llegaron a ese nodo en el recorrido.</p></li><li>El porcentaje (una vez creada la visualización, puede elegir mostrar el porcentaje del total o del nodo de inicio).</li><p>Por ejemplo, si Sesiones es la métrica secundaria, cada nodo muestra el porcentaje de sesiones que alcanzaron ese nodo en el recorrido (el porcentaje del total o del nodo de inicio).</p></li></ul> |
   | [!UICONTROL **recorrido Journey Optimizer**]<!-- name? --> | Seleccione el recorrido de Journey Optimizer que desee utilizar como base para el análisis en lienzo de Recorrido. (Como alternativa, puede dejar esta opción en blanco si desea un lienzo en blanco desde el que generar el análisis en Analysis Workspace).</p> <p>Cuando se analiza un recorrido de Journey Optimizer en lienzo de Recorrido, el recorrido se muestra con el mismo orden, secuencia y estructura que en Journey Optimizer. Para obtener más información, consulte [Analizar recorridos de Journey Optimizer](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#analyze-journey-optimizer-journeys) en [descripción general del lienzo de Recorrido](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md).</p><p>**Nota**: Esta opción solo se muestra cuando se detectan datos de Journey Optimizer en la vista de datos seleccionada en el panel de Analysis Workspace donde está agregando la visualización. Para obtener información sobre cómo cambiar la vista de datos en un panel de Analysis Workspace, consulte [Información general de Analysis Workspace](/help/analysis-workspace/home.md).</p> |

1. (Opcional) Seleccione [!UICONTROL **Mostrar configuración avanzada**] y, a continuación, especifique la siguiente información:

   | Campo | Función |
   |---------|----------|
   | [!UICONTROL **contenedor de lienzo de Recorrido**] | Elija el contenedor en el que desea centrarse en todo el recorrido. El contenedor que elija determina las estadísticas que se muestran en la visualización. (Si los nombres de contenedor difieren de los nombres predeterminados que se muestran a continuación, se personalizaron en la vista de datos).<ul><li>**Sesiones:** Restringe las estadísticas de la visualización para que se incluyan en una sola sesión definida para una persona determinada. Esto significa que los números y porcentajes que aparecen en cada nodo (que se basan en las métricas principal y secundaria) deben producirse en una sola sesión para cada persona.</li><li>**Personas:** Permite que las estadísticas de la visualización abarquen varias sesiones para una persona determinada. Esto significa que los números y porcentajes que aparecen en cada nodo (que se basan en las métricas principal y secundaria) pueden producirse en cualquier número de sesiones, siempre y cuando las sesiones pertenezcan a la misma persona. Esta es la configuración predeterminada.</li></ul> |

1. Seleccione [!UICONTROL **Generar**].

   Si tiene Journey Optimizer y ha seleccionado un recorrido de Journey Optimizer, el recorrido se muestra con el mismo orden, secuencia y estructura que en Journey Optimizer.

   <!-- add screen shot -->

   Si no tiene Journey Optimizer o si no ha seleccionado ningún recorrido de Journey Optimizer, aparece un lienzo en blanco donde puede empezar a rellenar el recorrido.

   <!-- add screen shot -->

1. Tanto si está creando un nuevo análisis a partir de un lienzo en blanco como si está analizando un recorrido de Journey Optimizer, puede configurar el recorrido tal como se describe en [Configuración de la visualización](#configure-visualization-settings).


## Configuración de visualización

Hay varias opciones de configuración disponibles en el encabezado del lienzo de Recorrido.

Para definir la configuración de la visualización del lienzo de Recorrido:

1. En Analysis Workspace, abra una visualización de lienzo de Recorrido existente o [empiece a crear una nueva](#begin-building-a-journey-canvas-visualization).

   Las opciones que le permiten configurar la visualización del lienzo de Recorrido están disponibles en el encabezado:

   ![opciones de encabezado de lienzo de Recorrido](assets/journey-canvas-header.png)

1. Configure cualquiera de las siguientes opciones que se muestran en la parte superior de la visualización:

   | Configuración | Función |
   |---------|----------|
   | [!UICONTROL **Tipo de nodo**] | Permite configurar qué tipos de nodos se muestran en la visualización. Para ocultar un tipo de nodo de la visualización, seleccione la (x) junto al tipo de nodo o anule su selección en el menú desplegable. Para mostrar un tipo de nodo oculto, selecciónelo en el menú desplegable. <p>Según el contenido de la visualización, los tipos de nodo posibles incluyen:</p><ul><li>[!UICONTROL **Leer segmento**]</li><li>[!UICONTROL **Fin**]</li><li>[!UICONTROL **Dimensión**]</li><li>[!UICONTROL **Métrica**]</li></ul><p>**Nota**: tenga en cuenta lo siguiente al utilizar este campo:</p><ul><li>Esta opción solo se muestra cuando se detectan datos de Journey Optimizer en la vista de datos seleccionada en el panel Analysis Workspace donde está agregando la visualización. Para obtener información sobre cómo cambiar la vista de datos en un panel de Analysis Workspace, consulte [Información general de Analysis Workspace](/help/analysis-workspace/home.md).</li><li>Después de modificar un recorrido de Journey Optimizer en Lienzo de Recorrido, esta opción ya no está disponible. Para obtener más información, vea [Diferencias visuales después de modificar un recorrido en lienzo de Recorrido](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#visual-differences-after-modifying-a-journey-in-journey-canvas)</li></ul></p> |
   | [!UICONTROL **Valor porcentual**] | Elija entre las siguientes opciones: <ul><li>[!UICONTROL **Porcentaje del total**]: El porcentaje de todas las personas incluidas en la vista de datos dentro del intervalo de fechas del panel.</li><li>[!UICONTROL **Porcentaje del nodo de inicio**]: El porcentaje de todas las personas incluidas en la vista de datos dentro del intervalo de fechas del panel que también cumplen los criterios del nodo de inicio del recorrido. (Esta opción solo está disponible en recorridos con un solo nodo de inicio; está desactivada en recorridos con varios nodos de inicio. Un nodo de inicio se define como cualquier nodo que no tiene una conexión entrante).</li></ul> |
   | [!UICONTROL **Configuración de flecha**] | Elija entre las siguientes opciones:<ul><li>[!UICONTROL **Ninguno**]: </li><li>[!UICONTROL **Condición**]: </li><li>[!UICONTROL **Todas las etiquetas**]: </li></ul><p>**Nota**: Esta opción solo se muestra cuando se detectan datos de Journey Optimizer en la vista de datos seleccionada en el panel de Analysis Workspace donde está agregando la visualización. Para obtener información sobre cómo cambiar la vista de datos en un panel de Analysis Workspace, consulte [Información general de Analysis Workspace](/help/analysis-workspace/home.md).</p> |
   | [!UICONTROL **Mostrar visitas en el orden previsto**] | Muestra los datos de visitas en el orden previsto de cada nodo. Muestra el número y el porcentaje de personas que abandonaron el recorrido después de un nodo determinado. <p>Las personas que no siguieron el recorrido podrían haber realizado otras acciones en el sitio, pero nunca cumplieron los criterios definidos por el siguiente nodo del recorrido.</p> |

1. Continúe con [Agregar nodos](#add-nodes).

## Agregar nodos

Los nodos de una visualización de lienzo de Recorrido representan los eventos o las acciones de un recorrido de usuario.

Los nodos se crean arrastrando los componentes de Workspace del carril izquierdo al lienzo, permitiendo que el lienzo de Recorrido elija los nodos superiores siguientes o anteriores en función de los nodos existentes, o duplicando los nodos existentes.

### Arrastre componentes desde el carril izquierdo

1. En Analysis Workspace, abra una visualización de lienzo de Recorrido existente o [empiece a crear una nueva](#begin-building-a-journey-canvas-visualization).

1. Arrastre métricas, dimensiones, elementos de dimensión, filtros o intervalos de fechas desde el carril izquierdo al lienzo. Se admiten las métricas basadas en un [campo derivado](/help/data-views/derived-fields/derived-fields.md). Sin embargo, no se admiten las métricas calculadas ni las métricas o dimensiones basadas en un [conjunto de datos de resumen](/help/data-views/summary-data.md).

   Para seleccionar varios componentes en el carril izquierdo, mantenga pulsada la tecla Mayús o Comando (en Mac) o Ctrl (en Windows).

   La visualización se actualiza de la siguiente manera, según el tipo de componente y el área del lienzo donde se coloque:

   | Tipo de componente | Colocación del componente | Actualizaciones de la visualización después de añadir un nodo |
   |---------|----------|----------|
   | Métrica | Área en blanco del lienzo | El nodo muestra dónde se colocó el componente, sin conexión con ningún nodo existente. |
   | Métrica | Un nodo existente | El componente se combina automáticamente con el nodo existente. (Consulte [Combinar nodos](#combine-nodes) para obtener más información).</p> |
   | Métrica | Una flecha entre 2 nodos existentes | El nodo se muestra entre los dos nodos existentes donde se colocó el componente y está conectado a ambos nodos existentes. (Consulte [Conectar nodos](#connect-nodes) para obtener más información).</p> |
   | Dimensión | Área en blanco del lienzo | Se crean 3 nodos para los 3 elementos de dimensión principales en los que se soltó el componente, sin conexión con ningún nodo existente. (**Nota:** Si solo se muestran 1 o 2 nodos, significa que los datos solo están disponibles para 1 o 2 de los elementos de dimensión. Si no se muestran nodos, significa que no hay datos disponibles para ninguno de los elementos de dimensión. En este caso, intente agregarla a un punto diferente del recorrido, ajustar el intervalo de fechas de la visualización o elegir una dimensión diferente).<p>Mantenga pulsada la tecla Mayús cuando suelte la dimensión en el lienzo para añadirla como un solo nodo con 3 elementos de dimensión.</p><p></p> |
   | Dimensión | Un nodo existente | Se aplica automáticamente un desglose al nodo con los 5 elementos de dimensión principales mostrados.<!--what happens if you hold Shift?--> |
   | Dimensión | Una flecha que conecta 2 nodos existentes | Se crean 3 nodos para los 3 elementos de dimensión principales que siguen al primer evento después del primer nodo (de personas/sesiones que finalmente llegan al segundo nodo). Los nodos se muestran entre los dos nodos existentes en los que se soltó el componente y cada nodo está conectado a los dos nodos existentes. (**Nota:** Si solo se muestran 1 o 2 nodos, significa que los datos solo están disponibles para 1 o 2 de los elementos de dimensión. Si no se muestran nodos, significa que no hay datos disponibles para ninguno de los elementos de dimensión. En este caso, intente agregarla a un punto diferente del recorrido, ajustar el intervalo de fechas de la visualización o elegir una dimensión diferente).<p>Mantenga pulsada la tecla Mayús cuando suelte la dimensión en el lienzo para añadirla como un solo nodo con 3 elementos de dimensión. (Consulte [Conectar nodos](#connect-nodes) para obtener más información).</p> |
   | Elemento de dimensión | Área en blanco del lienzo | El nodo muestra dónde se colocó el componente, sin conexión con ningún nodo existente. |
   | Elemento de dimensión | Un nodo existente | El componente se combina automáticamente con el nodo existente. |
   | Elemento de dimensión | Una flecha que conecta 2 nodos existentes | El nodo se muestra entre los dos nodos existentes donde se colocó el componente y está conectado a ambos nodos existentes. (Consulte [Conectar nodos](#connect-nodes) para obtener más información).</p> |
   | Filtro | Área en blanco del lienzo | El nodo muestra dónde se colocó el componente sin estar conectado con ningún otro nodo.<p>El número y el porcentaje que aparecen en el nodo incluyen el total de la métrica principal, filtrada por el filtro seleccionado.</p> <p>Por ejemplo, si se selecciona Personas como métrica principal para el recorrido, al agregar un filtro de Hoy a un área en blanco del lienzo se mostrarán todas las personas que hayan tenido un evento hoy.</p> |
   | Filtro | Un nodo existente | Aplica el filtro al nodo existente. |
   | Filtro | Una flecha que conecta 2 nodos | El nodo se muestra entre los dos nodos existentes donde se colocó el componente y está conectado a ambos nodos existentes. (Consulte [Conectar nodos](#connect-nodes) para obtener más información).</p><p>Aplica el filtro al punto de la ruta en el que se soltó el componente.</p> |
   | Intervalo de fechas | Área en blanco del lienzo | El nodo muestra dónde se colocó el componente, sin conexión con ningún otro nodo.<p>El número y el porcentaje que aparecen en el nodo incluyen el total de la métrica principal, filtrada por el intervalo de fechas seleccionado.</p> <p>Por ejemplo, si se selecciona Personas como métrica principal para el recorrido y, a continuación, se agrega un intervalo de fechas de Este mes a un área en blanco del lienzo para mostrar todas las personas que tuvieron un evento durante el mes actual.</p> |
   | Intervalo de fechas | Un nodo existente | Aplica el intervalo de fechas al nodo existente. |
   | Intervalo de fechas | Una flecha que conecta 2 nodos | El nodo se muestra entre los dos nodos existentes donde se colocó el componente y está conectado a ambos nodos existentes. (Consulte [Conectar nodos](#connect-nodes) para obtener más información).</p><p>Aplica el intervalo de fechas al punto de la ruta en el que se soltó el componente.</p> |
   | Varios componentes | Un área en blanco del lienzo | **Si ninguno de los componentes es una dimensión:**<p>Cada componente se muestra como un nodo independiente donde se soltaron los componentes, sin conexión con ningún nodo existente.</p><p>Mantenga pulsada la tecla Mayús cuando suelte los componentes en el lienzo para añadirlos como un nodo combinado. </p><p>**Si alguno de los componentes que está agregando son dimensiones:**</p><p>Cada componente se muestra como un nodo independiente donde se soltaron los componentes, sin conexión con ningún nodo existente.</p><p>Solo se puede agregar una dimensión a la vez y se crean 3 nodos para los 3 elementos de dimensión principales en los que se soltó el componente.</p><p>Mantenga pulsada la tecla Mayús cuando suelte los componentes en el lienzo para añadirlos como un nodo combinado. Los 3 elementos de dimensión principales se combinan con cada nodo. (Consulte [Combinar nodos](#combine-nodes) para obtener más información).</p> |
   | Varios componentes | Un nodo existente | Todos los componentes se combinan con el nodo existente.<p>Si alguno de los componentes que está agregando es una dimensión, los 3 elementos de dimensión principales se combinan con el nodo.</p> <p>Solo se puede añadir una dimensión a la vez.</p> |
   | Varios componentes | Una flecha que conecta 2 nodos existentes | **Si ninguno de los componentes es una dimensión:**<p>Cada componente se muestra como un nodo independiente donde los componentes se soltaron y cada nodo está conectado a ambos nodos existentes. (Consulte [Conectar nodos](#connect-nodes) para obtener más información).</p><p>Mantenga pulsada la tecla Mayús cuando suelte los componentes en el lienzo para añadirlos como un nodo combinado. (Los componentes deben ser del mismo tipo para combinarse en un solo nodo). (Consulte [Combinar nodos](#combine-nodes) para obtener más información).</p><p>**Si alguno de los componentes que está agregando son dimensiones:**</p><p>Cada componente se muestra como un nodo independiente donde los componentes se soltaron y cada nodo está conectado a ambos nodos existentes.</p><p>Solo se puede agregar una dimensión a la vez y se crean 3 nodos para los 3 elementos principales de la dimensión que siguen al primer evento después del primer nodo (de personas/sesiones que finalmente llegan al segundo nodo). Cada nodo está conectado a los dos nodos existentes. (Consulte [Conectar nodos](#connect-nodes) para obtener más información).</p><p>Mantenga pulsada la tecla Mayús cuando suelte los componentes en el lienzo para añadirlos como un nodo combinado. Los 3 elementos de dimensión principales se combinan con cada nodo y cada nodo está conectado a los dos nodos existentes. (Consulte [Combinar nodos](#combine-nodes) para obtener más información).</p> |

   Los nodos se muestran como un cuadro rectangular con la siguiente información:

   * Nombre del componente

   * El tipo de componente (como métrica o dimensión)

   * Estadísticas de métrica principal (total y porcentaje)

   * Estadísticas de métricas secundarias (total y porcentaje)

1. Repita este proceso para continuar agregando nodos para crear el recorrido.

1. Siga personalizando el recorrido como se describe en las secciones siguientes. Puede conectar nodos, cambiar el nombre de nodos, aplicar desgloses, crear audiencias, añadir restricciones de tiempo y mucho más.

### Agregar los nodos principales en función de los nodos existentes

Puede añadir automáticamente los nodos principales en función de los nodos que ya están en el lienzo.

Esta opción está disponible para los siguientes objetos del lienzo:

* Nodos individuales

* La flecha entre los nodos

#### Agregar nodos principales después de un nodo existente

Puede seleccionar un nodo y agregar los 3 nodos principales que le siguen en el recorrido.

1. Haga clic con el botón derecho en el nodo en el que desee agregar los 3 nodos principales que le siguen en el recorrido.

   Este nodo no puede tener ningún nodo existente saliendo de él en la recorrido.

1. Seleccione [!UICONTROL **Agregar nodos principales después de este nodo**].

   Los 3 nodos principales que aparecen después de este nodo en el recorrido se agregan y cada uno de ellos está conectado al nodo seleccionado como una rama independiente.

#### Agregar nodos principales antes de un nodo existente

Puede agregar los 3 nodos principales que aparecen antes de un nodo existente en el recorrido.

1. Haga clic con el botón derecho en el nodo en el que desee agregar los 3 nodos principales que le preceden en el recorrido.

   Este nodo no puede tener ningún nodo existente entrando en él en el recorrido.

1. Seleccione [!UICONTROL **Agregar nodos principales antes de este nodo**].

   Se agregan los tres nodos principales que preceden a este nodo en el recorrido y cada uno de ellos está conectado al nodo seleccionado como rama independiente.

#### Agregar nodos principales entre nodos existentes

Puede agregar los 3 nodos principales que se encuentran entre 2 nodos existentes:

1. Haga clic con el botón derecho en la flecha entre los 2 nodos donde desee agregar los 3 nodos principales del recorrido.

1. Seleccione [!UICONTROL **Agregar nodos principales**].<!-- I don't think this should have the word "next" in the UI option, because it's both next and previous. It's in between. Just "Get top nodes" sounds better to me.-->

   Los 3 nodos principales se agregan entre los 2 nodos existentes y cada uno de ellos se conecta como una rama independiente.

### Duplicar nodos

La opción de duplicado está disponible para los siguientes objetos del lienzo:

* Varios nodos

Para duplicar nodos:

1. Seleccione varios nodos que desee duplicar.

1. Haga clic con el botón derecho en uno de los nodos seleccionados y, a continuación, seleccione [!UICONTROL **Duplicar**].

## Diseño del recorrido

El orden de los nodos y las conexiones entre ellos afectan a los datos del lienzo de Recorrido. Los recorridos deben reflejar de forma visual y precisa la secuencia de eventos de los que desee informar.

Una vez añadidos los nodos al lienzo, puede reorganizarlos, combinarlos, conectarlos y añadir restricciones de tiempo entre ellos.

### Reorganizar nodos

Los recorridos del lienzo de Recorrido constan de un gráfico flexible de nodos y flechas que representan cualquier combinación de eventos, elementos de dimensión y filtros.

Puede arrastrar nodos en el lienzo para reorganizar los eventos y las condiciones del recorrido. A medida que lo haga, los datos se actualizarán en consecuencia.

### Combinar nodos

Un nodo combinado en el lienzo de Recorrido es un solo punto del recorrido del usuario (nodo) que contiene 2 o más componentes unidos mediante lógica.

#### Creación de nodos combinados

Puede realizar cualquiera de las siguientes acciones para crear nodos combinados en lienzo de Recorrido:

* Desde el carril izquierdo, arrastre un solo componente a un nodo del lienzo.

* Desde el carril izquierdo, arrastre varios componentes simultáneamente a un nodo del lienzo.

* Desde el carril izquierdo, arrastre varios componentes simultáneamente a una zona en blanco del lienzo mientras mantiene pulsada la tecla Mayús.

* En el lienzo, seleccione los nodos que desea combinar, haga clic con el botón secundario en uno de los nodos seleccionados y, a continuación, seleccione **Combinar**.<!--Is there a limit on how many you can combine? -->

#### Lógica al combinar nodos

La lógica que se aplica a los nodos cuando se combinan difiere según los tipos de componente que se combinen, de la siguiente manera:

>[!TIP]
>
>Para ver la lógica de un nodo combinado, haga clic con el botón derecho en el nodo y seleccione [!UICONTROL **Crear filtro a partir del nodo**]. La lógica se muestra en la sección [!UICONTROL **Definición**].


| Tipos de componente que se combinarán | Lógica (operador) utilizada |
|---------|----------|
| Métrica + Métrica | Unido con OR |
| DIMENSION + DIMENSION | Unido con OR |
| Filtro + Filtro | Unido con AND |
| Dimension + Métrica, Intervalo de fecha o Filtro | Unido con AND |
| Intervalo de fechas + Métrica, Filtro o Dimension | Unido con AND |
| Filtro + Métrica, Intervalo de fecha u Dimension | Unido con AND |

### Conectar nodos

Puede conectar nodos que ya están en el lienzo o puede conectar un nodo al agregarlo al lienzo.

#### Flechas entre nodos

Los nodos se conectan mediante una flecha. Tanto la dirección de la flecha como la anchura tienen significado:

* **Dirección**: indica la secuencia de eventos del recorrido

* **Anchura**: indica el volumen porcentual de un nodo a otro

#### Lógica al conectar nodos

Cuando se conectan nodos en lienzo de Recorrido, se conectan mediante el operador THEN. Esto también se conoce como [filtrado secuencial](/help/components/filters/seg-sequential-build.md).

Los nodos están conectados como una &quot;ruta eventual&quot;, lo que significa que los visitantes se cuentan siempre y cuando finalmente se muevan de un nodo a otro, independientemente de los eventos que se produzcan entre los 2 nodos.

Para ver la lógica de los nodos conectados, haga clic con el botón secundario en el nodo y seleccione [!UICONTROL **Crear filtro a partir del nodo**]. La lógica se muestra en la sección [!UICONTROL **Definición**].

#### Conectar nodos existentes

Los recorridos no pueden ser circulares, y se pueden volver a conectar con nodos previamente conectados.

Para conectar nodos en lienzo de Recorrido:

1. En el lienzo, pase el ratón sobre el nodo que aparece primero en la secuencia de recorrido que desea conectar a otro nodo.

   Aparecen 4 puntos azules a cada lado del nodo seleccionado.

1. Arrastre cualquiera de los 4 puntos azules a cualquiera de los 4 lados del nodo al que desee conectarse.

   Aparece una flecha que conecta los 2 nodos. Vea [Flechas entre nodos](#arrows-between-nodes) para obtener más información.

#### Conectar nodos al añadir un nodo

Al agregar un nodo al lienzo, puede colocarlo entre dos nodos conectados. El nodo se agrega al flujo del recorrido entre los 2 nodos existentes.

Para obtener más información, consulte [Agregar un nodo](#add-a-node).

### Agregar una restricción de tiempo entre nodos

Puede establecer una restricción de tiempo entre nodos. Cuando se establece una restricción de tiempo, si una persona sigue el recorrido definido pero tarda más tiempo del asignado en moverse entre los nodos, se considera que ha salido del recorrido.

La opción para añadir una restricción de tiempo está disponible para los siguientes objetos del lienzo:

* La flecha entre los nodos

Para añadir una restricción de tiempo:

1. Haga clic con el botón derecho en la flecha entre 2 nodos y, a continuación, seleccione [!UICONTROL **Agregar restricción de tiempo**].

<!-- 

from Travis: You can set time to be within X amount of time or after X amount of time (those are the only two options I think, but we can check with Brandon). 
1. Choose from the following options: 

-->

## Administración de nodos o flechas

### Cambiar el color de un nodo o una flecha

Puede personalizar visualmente un recorrido cambiando el color de cualquier nodo o flecha del lienzo. Por ejemplo, puede ajustar los colores para indicar un evento deseable o no deseable.

La opción para cambiar el color está disponible para los siguientes objetos del lienzo:

* Nodos individuales

* La flecha entre los nodos

Para cambiar el color de un nodo o una flecha:

1. Haga clic con el botón secundario en el nodo o flecha cuyo color desee cambiar.

1. Seleccionar [!UICONTROL **Cambiar color**]. <!--make sure "color" isn't capitalized. It is in the req doc-->

1. Seleccione el color que desee.

   Los colores siguientes están disponibles: <!--look into this interaction and color list-->

### Cambiar el nombre de un nodo o flecha

Al arrastrar un componente a una visualización de lienzo de Recorrido, se crea un nodo con el mismo nombre que el nombre del componente. Puede cambiar el nombre del nodo para que coincida mejor con el paso del recorrido que representa el nodo.

La opción para cambiar el nombre está disponible para los siguientes objetos del lienzo:

* Nodos individuales

* La flecha entre los nodos

Para cambiar el nombre de un nodo:

1. Haga clic con el botón secundario en el nodo cuyo nombre desee cambiar.

1. Seleccione [!UICONTROL **Cambiar nombre**].

1. Especifique un nombre nuevo y, a continuación, presione Entrar.<!--is that right?-->

### Aplicar un desglose

La opción para aplicar un desglose a los datos está disponible para los siguientes objetos del lienzo:

* Nodos individuales

* Varios nodos

* La flecha entre los nodos

* Varias flechas entre nodos

#### Aplicar un desglose a uno o varios nodos o flechas

1. Seleccione uno o varios nodos a los que desee aplicar un desglose y, a continuación, haga clic con el botón derecho en uno de los nodos seleccionados.

   O

   Seleccione una o más flechas entre 2 nodos donde desee aplicar el desglose y, a continuación, haga clic con el botón derecho en una de las flechas seleccionadas.

1. Seleccionar [!UICONTROL **desglose**].

#### Aplicación de un desglose a un nodo individual

Puede arrastrar una dimensión desde el carril izquierdo al nodo del lienzo en el que desea aplicar el desglose.

Para obtener más información, consulte [Agregar un nodo](#add-a-node).

### Crear un público

La opción para crear una audiencia está disponible para los siguientes objetos del lienzo:

* Nodos individuales

* Varios nodos

* La flecha entre los nodos

* Varias flechas entre nodos

Para crear una audiencia:

1. Seleccione uno o varios nodos donde desee crear una audiencia y, a continuación, haga clic con el botón derecho en uno de los nodos seleccionados.

   O

   Seleccione una o más flechas entre 2 nodos donde desee crear una audiencia y, a continuación, haga clic con el botón derecho en una de las flechas seleccionadas.

1. Seleccione [!UICONTROL **Crear audiencia**].

1. Siga creando y publicando la audiencia tal como se describe en [Crear y publicar audiencias](/help/components/audiences/publish.md).

### Ver datos de tendencia

Los datos de tendencia se pueden ver en un gráfico de líneas para los objetos del lienzo de Recorrido. <!--, with some prebuilt anomaly detection data (this is the definition in Fallout) -->

La opción tendencia está disponible para los siguientes objetos del lienzo:

* Nodos individuales

* Varios nodos

* Las flechas entre los nodos

* Varias flechas entre nodos

Para ver datos de tendencia:

1. Seleccione uno o varios nodos para los que desee ver datos de tendencia y, a continuación, haga clic con el botón derecho en uno de los nodos seleccionados.

   O

   Seleccione una o más flechas entre 2 nodos para los que desee ver datos de tendencia y, a continuación, haga clic con el botón derecho en una de las flechas seleccionadas.

1. Seleccione [!UICONTROL **Tendencia**].


### Creación de un filtro basado en un nodo o una flecha

Puede crear un nuevo filtro basado en un nodo o una flecha dentro de un recorrido. Una vez creado el filtro, puede utilizarlo en cualquier lugar de Analysis Workspace.

Los filtros creados a partir de lienzo de Recorrido utilizan [filtrado secuencial](/help/components/filters/seg-sequential-build.md). Esto significa que el filtro utiliza el operador THEN para vincular la secuencia de eventos (es decir, el recorrido) por los que fluyeron las personas, hasta llegar al nodo o la flecha seleccionados. Todos los eventos que coinciden con el nodo o la flecha seleccionados se incluyen en el filtro.

Si crea un filtro basado en un nodo que tiene varias rutas que fluyen a él, todas las rutas se incluyen en el filtro. Las rutas independientes se unen con el operador OR.

Para crear un filtro:

1. En el lienzo, haga clic con el botón derecho en el nodo o la flecha que desee utilizar para crear el filtro.

1. Seleccione [!UICONTROL **Crear filtro desde el nodo**] o [!UICONTROL **Crear filtro desde la flecha**].

   Se muestra el Generador de filtros. En la sección [!UICONTROL **Definition**], la definición del filtro se crea en función del nodo o la flecha que seleccionó y de su contexto dentro del recorrido.

1. Especifique un título para el filtro y realice cualquier otro cambio. Para obtener más información sobre cómo crear un filtro, consulte [Generador de filtros](/help/components/filters/filter-builder.md).

1. Seleccione [!UICONTROL **Guardar**] para guardar el filtro.

### Eliminación de nodos

Puede eliminar uno o varios nodos a la vez dentro de un recorrido. Cuando se elimina un nodo que está conectado entre dos nodos dentro del recorrido, los dos nodos restantes se conectan directamente.

Para eliminar nodos en lienzo de Recorrido:

1. Seleccione uno o varios nodos que desee eliminar y, a continuación, haga clic con el botón derecho en uno de los nodos seleccionados.

1. Seleccione [!UICONTROL **Eliminar**].

### Eliminar flechas entre nodos

Puede eliminar una o más flechas a la vez dentro de un recorrido. Cuando se elimina una flecha entre 2 nodos, los nodos ya no están conectados. Si la flecha formaba parte de una trayectoria más larga, la trayectoria está desconectada.

Para eliminar flechas entre nodos en lienzo de Recorrido:

1. Seleccione una o más flechas entre 2 nodos que desee eliminar y, a continuación, haga clic con el botón derecho en una de las flechas seleccionadas.

1. Seleccione [!UICONTROL **Eliminar**].


<!-- Delete this after I decide I don't want to do it this way. Will probably use sections like I hav above.

### Manage existing nodes

1. In Analysis Workspace, open an existing Journey canvas visualization, or [begin building a new one](#begin-building-a-journey-canvas-visualization).

1. Right-click an **individual node** on the canvas, then select any of the following options:
   
   | Option | Function | 
   |---------|----------|
   | [!UICONTROL **Create segment**] | B1 |
   | [!UICONTROL **Publish audience**] | B2 |
   | [!UICONTROL **Trend**] | B3 | 
   | [!UICONTROL **Breakdown**] | B2 |
   | [!UICONTROL **Get top next ...**] | B2 |
   | [!UICONTROL **Change color**] | B2 |
   | [!UICONTROL **Rename**] | B2 |
   | [!UICONTROL **Delete**] | B2 |

1. Select **multiple nodes** on the canvas, right-click one of the selected nodes, then select any of the following options:

   | Option | Function | 
   |---------|----------|
   | [!UICONTROL **Combine**] | B1 |
   | [!UICONTROL **Delete**] | B2 |
   | [!UICONTROL **Duplicate**] | B3 | 
   | [!UICONTROL **Trend**] | B2 |
   | [!UICONTROL **Breakdown**] | B2 |
   | [!UICONTROL **Create segment**] | B2 |
   | [!UICONTROL **Publish audience**] | B2 |

   -->


## Apertura de un recorrido desde Journey Optimizer


En Journey Optimizer, abra el recorrido que desee analizar en el lienzo del Recorrido.

1. Seleccione [!UICONTROL **Analizar en CJA**]. <!-- ?? -->
