---
title: Información general sobre la visualización de matrices en Analysis Workspace
description: Obtenga información sobre la visualización de matrices en Customer Journey Analytics Analysis Workspace, incluido lo que muestra, cuándo utilizarla y cómo se compara con otras visualizaciones.
feature: Visualizations
role: User
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 3199a70eee577f4e283208e2c5089c05fe20ed0d
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 2%
---

# Información general de matriz {#matrix-overview}

La visualización de matriz en Analysis Workspace permite ver cómo los elementos de dimensión de dos dimensiones se superponen o se correlacionan entre sí.

Los elementos de Dimension para una dimensión se muestran como filas (a lo largo del eje Y), mientras que los elementos de dimensión para la otra dimensión se muestran como columnas (a lo largo del eje X). Cada celda de intersección muestra los datos de superposición o correlación, que se basan en la métrica que elija.

Por ejemplo, la siguiente visualización de matriz muestra el recuento de eventos superpuestos para nombres de dispositivos por código de país.

* Dimension 1 (dimensión de fila): Nombre del dispositivo

* Dimension 2 (dimensión de columna): Código de país

* Métrica: Eventos

![Resumen de matriz](assets/matrix-overview.png)

## Funciones principales

* **Comparar dos dimensiones diferentes**: Vea cómo los elementos de una dimensión se relacionan con los elementos de otra dimensión.

* **Comparar una dimensión consigo misma**: vea cómo se relacionan los elementos de la misma dimensión.

* **Superposición**: vea la superposición de elementos de dimensión.

* **Correlación**: vea la tendencia de los elementos de dimensión juntos, en una escala de -1 (siempre se mueven en direcciones opuestas) a +1 (siempre se mueven juntos).

* **Colores de mapa de calor**: El color de celda muestra si la superposición es alta o baja, o si la correlación es positiva o negativa y su intensidad. La superposición y la correlación tienen paletas de color independientes.

## Información potencial

* Encuentre patrones y huecos en dos dimensiones. Por ejemplo, puede responder preguntas como:

  * ¿Qué campañas funcionan bien en algunas regiones pero no en otras?

  * ¿Qué tipos de contenido funcionan mejor en cada tipo de dispositivo?

* Descubra la tendencia de los elementos de dimensión en relación con los demás. Por ejemplo, puede responder preguntas como:

  * ¿Qué canales de marketing siguen la tendencia juntos a lo largo del tiempo, cuáles se mueven de forma independiente y cuáles se mueven en direcciones opuestas?

  * ¿Qué páginas tienen tráfico que sube y baja en conjunto?

* Comparar una dimensión consigo misma. Por ejemplo, puede responder preguntas como:

  * ¿Qué productos suelen comprar las mismas personas?

  * ¿Qué dispositivos utilizan juntas las mismas personas, como teléfonos móviles y tabletas?

## Elija entre visualizaciones de matriz, tabla de forma libre, Venn o Dispersión

La visualización de matriz tiene similitudes con [el uso de varias columnas de dimensión en una tabla de forma libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md), la [visualización Venn](/help/analysis-workspace/visualizations/venn.md) y la [visualización de dispersión](/help/analysis-workspace/visualizations/scatterplot.md). Cada visualización muestra cómo se relacionan los componentes entre sí, pero difieren en los componentes que utilizan y en cómo muestran los resultados.

### Cuándo utilizar cada visualización

Elija la visualización que mejor se adapte a su análisis:

* **Matriz:** Para una métrica determinada, vea la relación entre cada elemento de dimensión de una dimensión y cada elemento de dimensión de otra, incluidos los espacios y los elementos de dimensión que cambian de tendencia juntos.

* **Tabla de forma libre con varias columnas de dimensión:** Puede agregar hasta cinco dimensiones como columnas independientes a una tabla de forma libre. Los elementos de Dimension que aparecen en la misma fila de la tabla están concatenados. Agregue cualquier número de métricas a la tabla para ver los datos de métricas de cada elemento de dimensión concatenado. Filtre, ordene y agregue desgloses a elementos de dimensión concatenados.

* **Venn:** Para una sola métrica, vea la superposición de hasta 3 segmentos.

* **Dispersión:** Compare elementos de dimensión entre dos o tres métricas para encontrar patrones y periféricos.

### Conocer las diferencias

<!-- SME CHECK: Confirm the Matrix cells: segments can't be used as rows or columns. Container row: confirm what each Matrix container means for overlap, and that freeform combinations are based on the dimension items that apply to each event. -->

| Función | Matriz | Varias columnas de dimensión en una tabla de forma libre | Venn | Disperso |
| --- | --- | --- | --- | --- |
| **Componentes utilizados** | 2 dimensiones; 1 métrica<p>Compara elementos de dimensión de 2 dimensiones o de 1 dimensión consigo mismo.</p> | Hasta 5 dimensiones; cualquier número de métricas<p>Los elementos de Dimension que aparecen en la misma fila están concatenados y se comportan como un solo elemento de dimensión. Las filas concatenadas se comparan por sus valores de métrica.</p> | Hasta 3 segmentos; 1 métrica<p>Compara la superposición entre segmentos.</p> | 1 dimensión; hasta 3 métricas<p>Compara elementos de dimensión entre métricas.</p> |
| **Contenedor** | Se establece en la visualización: Persona (predeterminado), Sesión o Evento<p>Determina si la superposición cuenta elementos de dimensión que se producen para la misma persona, en la misma sesión o en el mismo evento.</p> | Sin configuración de contenedor<p>Cada fila combina los elementos de dimensión que se aplican al mismo evento. La métrica que elija, como Personas o Sesiones, determina qué se cuenta.</p> | Establecido en cada segmento<p>Cada segmento usa su propio [contenedor](/help/components/segments/seg-overview.md#containers) (persona, sesión o evento). La métrica determina qué se cuenta en cada superposición.</p> | Sin configuración de contenedor<p>Las métricas que elija determinan lo que se cuenta.</p> |
| **Diseño** | Cuadrícula, similar a una tabla dinámica<p>Los elementos de Dimension de una dimensión son filas y los elementos de dimensión de la otra dimensión son columnas.</p> | Lista<p>Cada fila combina un elemento de dimensión de cada columna de dimensión.</p> | Círculos superpuestos | Puntos en el eje X y en el eje Y |
| **Muestra superposición** | Sí<p>Muestra la superposición entre cada elemento de dimensión en las filas y cada elemento de dimensión en las columnas.</p><p>Use la vista **[!UICONTROL Recuento de superposiciones]**.</p> | Sí<p>Muestra la métrica para cada combinación de elementos de dimensión, una combinación por fila.</p> | Sí<p>Muestra la superposición entre segmentos.</p> | No |
| **Muestra correlación** | Sí, entre elementos de dimensión<p>Muestra la tendencia de los elementos de dimensión juntos a lo largo del tiempo, en una escala de -1 (direcciones opuestas) a +1 (juntos).</p><p>Use la vista **[!UICONTROL Intensidad de correlación]**.</p> | No | No | Sí, entre métricas<p>Muestra cómo se relacionan las métricas entre sí. Cada punto es un elemento de dimensión representado por un máximo de 3 métricas.</p> |

{style="table-layout:auto"}

