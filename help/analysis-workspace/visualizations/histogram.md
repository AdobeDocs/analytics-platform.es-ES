---
description: Un histograma es similar a un gráfico de barras, pero agrupa números en rangos (contenedores).
title: Histograma
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 90%

---

# Histograma

Un histograma es similar a un gráfico de barras, pero agrupa números en rangos (contenedores). Analytics automatiza la creación de contenedores de números en rangos, pero puede modificar la configuración en [Configuración avanzada](#section_09D774C584864D4CA6B5672DC2927477).

## Crear un histograma {#section_74647707CC984A1CB6D3097F43A30B45}

Para crear un histograma:

1. Haga clic en **[!UICONTROL Visualizaciones]** en el carril izquierdo.
1. Arrastre **[!UICONTROL Histograma]** al panel.
1. Seleccione una métrica para arrastrar a la visualización del histograma y haga clic en **[!UICONTROL Generar]**.

![](assets/histogram.png)

>[!NOTE]
>
>Los histogramas únicamente admiten métricas estándar, pero no métricas calculadas.

Aquí hemos utilizado la métrica Vistas de página por Visitantes únicos. El primer contenedor (izquierda) corresponde a 1 vista de página por persona única, el segundo bloque a dos vistas de página, etc.

![](assets/histogram2.png)

## Configuración avanzada {#section_09D774C584864D4CA6B5672DC2927477}

Para ajustar la configuración de su histograma, haga clic en el icono de Configuración (“engranaje”) en la esquina superior derecha. A continuación verá los ajustes que puede modificar:

| Configuración de histograma | Qué hace |
|---|---|
| Iniciando el depósito | Determina por qué contenedor empieza el histograma. La opción predeterminada es “1”. Puede ajustar los números iniciales de 0 hasta el infinito (sin números negativos). |
| Contenedor de métricas | Le permite aumentar/disminuir el número de rangos de fecha (contenedores). El número máximo de contenedores es 50. |
| Tamaño del contenedor de métricas | Le permite establecer el tamaño de cada contenedor. Por ejemplo, puede cambiar el tamaño del contenedor de 1 vista de página a 2 vistas de página. |
| Método de recuento | Permite seleccionar entre [Visitante](https://experienceleague.adobe.com/docs/analytics/components/metrics/unique-visitors.html?lang=es), [Visita](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=es) o Tipo de visita. Por ejemplo, vistas de página por visita o vistas de página por persona o vistas de página por evento. Para visitas, se utiliza “Ocurrencias” como métrica del eje y en una tabla de forma libre. |

<!--Russ or Meike - Check Hit Type link above. -->

**Ejemplos**:

* Iniciando el depósito: 1; Contenedores de métricas: 5; Tamaño del contenedor de métricas: 2 será el resultado en este histograma: 1-2, 3-4, 5-6, 7-8, 9-10.
* Iniciando el depósito: 0; Contenedores de métricas: 3; Tamaño del contenedor de métricas: 5 será el resultado en este histograma: 0-4, 5-9, 10-14

## Ver y editar los datos de un histograma {#section_B2CD7CDF0F6B432F928103AE7AAA3617}

Para ver o modificar los datos de origen de un gráfico de histograma, haga clic en el punto del encabezado de Histograma para ir a **[!UICONTROL Configuración de fuente de datos]** > **[!UICONTROL Mostrar fuente de datos]**.

![](assets/manage-data-source.png)

Los filtros creados previamente que se muestran en la tabla son filtros internos y no aparecerán en el selector de filtros. Haga clic en el icono “i” junto al nombre del filtro y, a continuación, haga clic en **[!UICONTROL Hacer público]** para que el filtro sea público.

![](assets/prebuilt_segments.png)

Para explorar más formas en las que administrar las tablas de datos de forma libre y otras visualizaciones, como hacer desgloses de datos, vaya [aquí](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=es).
