---
description: Información general del lienzo de recorrido
title: Lienzo de recorrido
feature: Visualizations
role: User
hide: true
hidefromtoc: true
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: 5d65f2cee34741d985ae7b85ad62f65a68c6289a
workflow-type: tm+mt
source-wordcount: '1300'
ht-degree: 2%

---

# Información general del lienzo de recorrido

{{release-limited-testing}}

La visualización del lienzo de Recorrido le permite analizar y obtener perspectivas profundas sobre los recorridos que proporciona a sus usuarios y clientes. Permite definir un recorrido desde cero o ver uno desde Journey Optimizer y, a continuación, ver cómo abandonaron el recorrido o cómo continuaron en él.

Puede [generar análisis de recorridos de usuario](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md) utilizando cualquier combinación de eventos, elementos de dimensión, filtros e intervalos de fechas para crear nodos de recorrido. Conecte los nodos para crear el flujo del recorrido e incluya varias rutas y puntos de decisión. Arrastre nodos en el lienzo para reorganizar los eventos y las condiciones del recorrido. Los datos se actualizan en tiempo real a medida que realiza cambios.

## Funciones principales

Las características clave de la visualización del lienzo de Recorrido incluyen:

* Análisis profundo de abandonos y abandonos que se adapta a los recorridos de usuario más complejos.

* Lienzo para asignar y visualizar los distintos puntos de entrada, nodos y rutas de un recorrido de usuario.

* Interacciones de arrastrar y soltar para agregar componentes al lienzo y para cambiar la posición de nodos existentes.

* La opción para generar análisis de recorridos de usuario dentro del lienzo de Recorrido o para crearlos automáticamente en función de los recorridos de Journey Optimizer.

## Perspectivas potenciales

A continuación se muestran algunos ejemplos de los tipos de lienzo de Recorrido de perspectivas que puede ayudar a proporcionar. Puede elegir si estas perspectivas se basan en todas las personas de la vista de datos o en todas las personas que iniciaron el recorrido.

**Visitas en orden previsto**

* Número y porcentaje de personas que completaron el recorrido (llegaron al nodo final)

* Número y porcentaje de personas que llegaron a un punto determinado (nodo) del recorrido

* El paso más común que se produjo después o antes de un punto determinado (nodo) del recorrido

**Visita en orden previsto**

* Los puntos (nodos) del recorrido en los que las personas salen del recorrido con mayor frecuencia

**Otro**

* Datos adicionales para cualquier nodo del recorrido (añadiendo una dimensión de desglose para el nodo)


## Elija entre lienzo de Recorrido y visualizaciones de visitas en el orden previsto

Las visualizaciones de lienzo de recorrido son similares a las [visualizaciones de visitas en el orden previsto](/help/analysis-workspace/visualizations/fallout/fallout-flow.md), ya que ambas visualizaciones muestran dónde abandonaron las personas y continuaron en una secuencia de páginas predefinidas.

Sin embargo, hay diferencias importantes.

### Comprender las diferencias

La siguiente tabla muestra los tipos de análisis admitidos en la visualización del lienzo de Recorrido y la visualización de abandonos:

| Función | Visualización de lienzo de recorrido | Visualización de visitas en el orden previsto |
|---------|----------|---------|
| Recorridos lineales | Sí | Sí |
| Recorridos no lineales con varios puntos de entrada y rutas | Sí | No |
| Adobe Journey Optimizer recorrido | Sí | No |
| Métrica principal | Cualquier métrica, incluidas las métricas calculadas | Solo se pueden usar las métricas de Sesión o Usuario |
| Métrica secundaria | Sí<p>Cualquier métrica, incluidas las métricas calculadas</p> | No |
| Comparar filtros | No | Sí<p>Comparar un número ilimitado de filtros [1](/help/analysis-workspace/visualizations/fallout/compare-segments-fallout.md#compare-filters-in-fallout)</p> |

### Elija la visualización que desea utilizar

Antes de elegir entre usar lienzo de Recorrido o Visitas en el orden previsto, asegúrese de [comprender las diferencias entre los dos](#understand-the-differences).

Si el análisis de visitas en el orden previsto implica solamente un recorrido lineal que tiene un único principio y un único final conocidos, considere la posibilidad de usar una [visualización de visitas en el orden previsto](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) como una opción más sencilla para estos recorridos de usuario más directos.

El lienzo de recorrido es esencial para el análisis de abandonos que implican recorridos con varios puntos de entrada y rutas o para analizar los recorridos creados en Journey Optimizer.

## Analizar Journey Optimizer recorrido

>[!NOTE]
>
>Si su organización no tiene acceso a Journey Optimizer, todavía puede [crear análisis en lienzo de Recorrido](#build-analyses-in-customer-journey-analytics).

El análisis de recorridos de Journey Optimizer en lienzo de Recorrido proporciona perspectivas profundas y procesables sobre cómo las personas interactúan con un recorrido.

Cuando se analiza un recorrido de Journey Optimizer en lienzo de Recorrido, el recorrido se muestra con el mismo orden, secuencia y estructura que en Journey Optimizer. Si puede realizar cambios en un recorrido dentro del lienzo de Recorrido, [los cambios ya no se sincronizan desde Journey Optimizer](#synchronization-between-journey-optimizer-and-journey-canvas).

### Ventajas del análisis de recorridos de Journey Optimizer con lienzo de Recorrido

El lienzo de recorrido proporciona un análisis profundo y exhaustivo que no es posible en Journey Optimizer.

El uso del lienzo de Recorrido para analizar los recorridos creados en Journey Optimizer ofrece varias ventajas:

* Cree eventos mediante dimensiones, métricas, filtros o intervalos de fechas de Customer Journey Analytics.

  En Journey Optimizer, un usuario técnico debe crear un evento para poder añadirlo a un recorrido.

* Cree audiencias en función de un nodo personalizado que haya creado (inicia el generador de audiencias de Customer Journey Analytics).

  En Journey Optimizer, solo puede crear audiencias para actividades predefinidas.

* Analizar visitas en el orden previsto y abandonos

* Desglose de eventos con cualquier dimensión

* Combinación de eventos

* Conectar eventos

* Cambiar nombre y eliminar eventos

* Mucho más

### Sincronización entre Journey Optimizer y el lienzo de Recorrido

Después de crear un análisis de un recorrido de Journey Optimizer en lienzo de Recorrido, los datos se sincronizan en una sola dirección, de Journey Optimizer a lienzo de Recorrido. Esto significa que los cambios realizados en un recorrido en lienzo de Recorrido nunca se reflejan en Journey Optimizer.

Además, los cambios realizados en un recorrido en Journey Optimizer se sincronizan con el lienzo de Recorrido solo si el recorrido permanece sin modificar en el lienzo de Recorrido. Después de modificar un recorrido en lienzo de Recorrido, los cambios realizados en el recorrido en Journey Optimizer no se reflejarán en el lienzo de Recorrido. Para ver los cambios reflejados en el lienzo de Recorrido, puede eliminar y [volver a crear el recorrido en el lienzo de Recorrido](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### Diferencias después de modificar un recorrido en lienzo de Recorrido {#differences-after-modifying}

Después de modificar un recorrido de Journey Optimizer en lienzo de Recorrido, pueden producirse cambios en el procesamiento de datos, las funciones disponibles y el comportamiento de sincronización.

Si realiza una modificación significativa en un recorrido de Journey Optimizer en lienzo de Recorrido, pueden producirse cambios en el procesamiento de datos, las funciones disponibles y el comportamiento de sincronización. Una modificación significativa incluye cualquiera de las siguientes opciones:

* Adición o eliminación de un nodo

* Adición o eliminación de una flecha entre nodos

* Cambio de los componentes de un nodo

Si realiza otros cambios en un recorrido de Journey Optimizer en lienzo de Recorrido, como arrastrar un nodo o agregar un desglose, no se aplicarán las diferencias que se describen en las secciones siguientes.

>[!NOTE]
>
>Para devolver el recorrido a su estado original, puede presionar Ctrl+z después de realizar el primer cambio en el lienzo de Recorrido. O bien, puede eliminar y [volver a crear el recorrido en lienzo de Recorrido](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)

#### Diferencias de procesamiento de datos

Después de modificar un recorrido de Journey Optimizer en lienzo de Recorrido, es posible que observe cambios en los datos si el recorrido contiene métricas que tienen modelos de atribución no predeterminados.

Esto se debe a que, a diferencia de Journey Optimizer, el lienzo de Recorrido permite aplicar varias dimensiones dentro de un solo recorrido. Esta capacidad significa que no se admite la atribución de [métricas](/help/data-views/component-settings/attribution.md).

#### Diferencias de características

Después de modificar un recorrido de Journey Optimizer en lienzo de Recorrido, la funcionalidad puede cambiar para las siguientes funciones, según las modificaciones:

* Los valores mostrados en el campo [!UICONTROL **Tipo de nodo**] cambian.

* Las opciones disponibles en el campo desplegable [!UICONTROL **Configuración de flecha**] cambian.

Para obtener más información acerca de estos campos, vea [Configurar opciones](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

#### Diferencias de sincronización

Los cambios realizados en un recorrido en Journey Optimizer se sincronizan con el lienzo de Recorrido solo si el recorrido permanece sin modificar en el lienzo de Recorrido.

Después de modificar un recorrido de Journey Optimizer en lienzo de Recorrido, los cambios realizados en el recorrido en Journey Optimizer no se reflejarán en el lienzo de Recorrido. Para ver los cambios reflejados en el lienzo de Recorrido, puede eliminar y [volver a crear el recorrido en el lienzo de Recorrido](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

### Diferencias terminológicas entre Journey Optimizer y Customer Journey Analytics

Ciertos términos que significan una cosa en Journey Optimizer significan otra en Customer Journey Analytics. Cuando se utiliza lienzo de Recorrido, se utilizan los términos de Customer Journey Analytics.

| Término | Lienzo de recorrido | Journey Optimizer |
|---------|----------|---------|
| **Evento** | Una de las varias métricas estándar que están disponibles en Customer Journey Analytics. Esta métrica cuenta cosas como ingresos, suscripciones o posibles clientes generados. | Categoría de actividad que almacena en déclencheur un recorrido personalizado, como una compra en línea. |

### Analizar un recorrido de Journey Optimizer en lienzo de Recorrido

Para obtener información sobre cómo analizar un recorrido de Journey Optimizer en lienzo de Recorrido, consulte [Configuración de una visualización de lienzo de Recorrido](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).

## Generar análisis en lienzo de Recorrido

Puede crear análisis en lienzo de Recorrido basados en cualquier dimensión o métrica disponible en Analysis Workspace. O bien, puede analizar los recorridos creados en Journey Optimizer. Para obtener más información, consulte [Configuración de una visualización de lienzo de Recorrido](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).
