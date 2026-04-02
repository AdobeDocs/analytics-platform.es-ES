---
description: Aprenda a configurar y especificar los puntos de contacto para crear una secuencia de visitas en el orden previsto multidimensional.
title: Configuración De Una Visualización De Abandonos
feature: Visualizations
exl-id: 3d888673-d7b1-45ef-bd3a-97b98466fb0e
role: User
source-git-commit: 295e4c9b3b9dff5ba650456c3f62817b30fe1e3d
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 39%

---

# Configurar una visualización de abandonos {#configure-fallout-visualization}


Puede especificar **puntos de contacto** para crear una secuencia de visitas en el orden previsto multidimensional. En muchos casos, un punto de contacto es una página del sitio. Sin embargo, los puntos de contacto no se limitan a las páginas. Por ejemplo, puede añadir eventos, como unidades, así como personas únicas y visitas de retorno. También puede agregar dimensiones, como una categoría, un tipo de explorador o un término de búsqueda interna.

Incluso puede añadir segmentos dentro de un punto de contacto. Por ejemplo, es posible que quiera comparar segmentos como los usuarios de iOS y Android. Arrastre los segmentos deseados sobre las visitas en el orden previsto, y la información sobre esos segmentos se añadirá al informe de visitas en el orden previsto. Si desea mostrar solo esos segmentos, puede quitar la línea de base de Todas las personas.

Las visualizaciones de visitas en el orden previsto no tienen limitaciones en cuanto al número de puntos de contacto que puede añadir o al número de componentes que puede utilizar.

Puede realizar rutas en dimensiones, métricas y segmentos. Por ejemplo, supongamos que alguien está mirando `shoes, shirt` en una página y en la siguiente mira `shirt, socks`. El siguiente informe de flujo de productos desde zapatos será camiseta y calcetines, NO camiseta.

## Usar

1. Añada una visualización de ![Canal de conversión](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL Abandonos]**. Consulte [Añadir una visualización a un panel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Arrastre un componente al menú desplegable **[!UICONTROL Agregar punto de contacto]**.

   >[!TIP]
   >
   >Puede agregar una sola página al informe de visitas en el orden previsto, en lugar de toda la dimensión. Haga clic en la flecha derecha ![ChevronRight](/help/assets/icons/ChevronRight.svg) de la dimensión de página para seleccionar una página específica, como **[!UICONTROL inicio]**, y agregarla al informe de visitas en el orden previsto.

   ![La página de inicio de la dimensión Página de inicio se arrastró al campo Añadir punto de contacto.](assets/fallout-drag.png)

1. Siga añadiendo puntos de contacto hasta que la secuencia se haya completado.

   Los números dentro de un círculo en la parte gris de la barra muestran la visita en el orden previsto entre puntos de contacto (no la visita en el orden previsto total hasta ese punto). Los números en círculo de la parte verde de la barra muestran la caída correcta desde el punto de contacto anterior al punto de contacto actual.

   ![Visualización de abandonos](assets/fallout-visualization.png)

   Al agregar puntos de contacto, puede realizar cualquiera de las siguientes acciones:

   * Combine varios componentes arrastrando uno o más componentes adicionales a un único punto de contacto.

     >[!NOTE]
     >
     >Varios segmentos se unen con AND, mientras que los elementos (como elementos de dimensión y métricas) se unen con OR.

   * Reordene los puntos de contacto arrastrándolos a un nivel diferente dentro de la jerarquía de visitas en el orden previsto.

   * Combine dos puntos de contacto arrastrando un punto de contacto a otro. Suelte el punto de contacto cuando vea la palabra **[!UICONTROL Combinar]**.

   * Restrinja los puntos de contacto individuales al siguiente evento (a diferencia de *eventualmente*) dentro de la ruta. Debajo de cada punto de contacto hay un selector con las opciones **[!UICONTROL Ruta de acceso eventual]** y **[!UICONTROL Siguiente evento]**, como se muestra a continuación:

     | Opción | Descripción |
     |---|---|
     | **[!UICONTROL Ruta eventual]** (predeterminada) | Se cuentan las personas que *eventualmente* aterrizarán en la siguiente página del recorrido, pero no necesariamente en el siguiente evento. |
     | **[!UICONTROL Evento siguiente]** | Se cuentan las personas que aterrizarán en la siguiente página de la ruta en el siguiente evento. |

   * Pase el ratón sobre un punto de contacto para ver las visitas en el orden previsto y otra información sobre ese nivel. La información incluye el nombre del punto de contacto, el recuento de personas y la tasa de éxito. También puede comparar la tasa de éxito con otros puntos de contacto.

## Configuración {#settings}

>[!CONTEXTUALHELP]
>id="workspace_fallout_container"
>title="Contenedor de visitas en el orden previsto"
>abstract="Seleccione un contenedor para analizar las rutas. Esta selección le ayuda a comprender la participación y limita el análisis al contenedor seleccionado."

Como parte de la visualización, hay disponibles ajustes específicos.

| Contenedor de visitas en el orden previsto | Descripción |
|--- |--- |
| **[!UICONTROL Sesión]** o **[!UICONTROL Persona]** | Cambie entre [!UICONTROL Sesión] y [!UICONTROL Persona] para analizar la ruta de la persona. El valor predeterminado es [!UICONTROL Persona]. Esta configuración le permite comprender el compromiso de la persona a nivel de persona (a lo largo de las sesiones) o restringir el análisis a una única sesión. |


## Menú contextual

Como parte de la visualización, hay opciones específicas de menú contextual disponibles.

### Acceso al menú contextual

Puede acceder al menú contextual de cualquiera de las siguientes maneras:

* Pase el ratón sobre un punto de contacto de la visualización y seleccione **[!UICONTROL Haga clic para analizar]**.

  ![Acceder al menú contextual desde el cursor](assets/fallout-tooltip-analyze.png)

* Haga clic con el botón derecho en un punto de contacto de la visualización.

  ![Opciones de visitas en el orden previsto](assets/fallout-options.png)

### Opciones del menú contextual

Las opciones de menú contextual disponibles son las siguientes:

| Opción | Descripción |
|--- |--- |
| **[!UICONTROL Punto de contacto de la tendencia]** | Consulte los datos de tendencia para un punto de contacto en un gráfico de líneas en el cual se hayan incorporado previamente algunos datos de detección de anomalías. |
| **[!UICONTROL Punto de contacto de tendencia (%)]** | Realiza la tendencia del porcentaje total de visitas en el orden previsto. |
| **[!UICONTROL Tendencia de todos los puntos de contacto (%)]** | Realiza la tendencia de todos los porcentajes de puntos de contacto en las visitas en el orden previsto (excepto **[!UICONTROL Todas las personas]**, si se incluye) en el mismo gráfico. |
| **[!UICONTROL Desglosar visitas en el orden previsto en este punto de contacto]** | Vea qué hicieron las personas entre dos puntos de contacto (este punto de contacto y el siguiente) si continuaron hasta el siguiente punto de contacto. Esto crea una tabla de forma libre que muestra las dimensiones. Se pueden reemplazar dimensiones y otros elementos de la tabla. Por ejemplo, una tabla con la etiqueta **[!UICONTROL Visitas en el orden previsto: Todas las personas > Página es igual a cualquiera de inicio]** y contiene **[!UICONTROL Página]** como dimensión y **[!UICONTROL Personas]** segmentadas por el [segmento rápido de solo proyecto](/help/components/segments/seg-quick.md) **[!UICONTROL Visitas en el orden previsto: Todas las personas > Página es igual a cualquiera de inicio]** como métrica. Inspeccione el segmento para comprender cómo se determina el segmento de alternativa. |
| **[!UICONTROL Desglosar visitas en orden previsto en este punto de contacto]** | Vea qué han hecho las personas que no han seguido la funnel inmediatamente después del paso seleccionado. Esto crea una tabla de forma libre que muestra las dimensiones. Se pueden reemplazar dimensiones y otros elementos de la tabla. Por ejemplo, una tabla con la etiqueta **[!UICONTROL Visitas en el orden previsto: Personas > Página es igual a cualquiera de las páginas de inicio]** y contiene **[!UICONTROL Página]** como dimensión y **[!UICONTROL Personas]** segmentadas por el [segmento rápido de solo proyecto](/help/components/segments/seg-quick.md) **[!UICONTROL Visitantes en el orden previsto: Todos los visitantes > Página es igual a cualquiera de las páginas de inicio]** como métrica. Inspeccione el segmento para comprender cómo se determina el segmento de visitas en el orden previsto. |
| **[!UICONTROL Crear segmento a partir de touchpoint]** | Cree un nuevo segmento a partir de un punto de contacto seleccionado. |

>[!MORELIKETHIS]
>
>[Añadir una visualización a un panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Configuración de visualización](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menú contextual de visualización](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

