---
description: Información rápida es una herramienta para nuevos usuarios de Workspace que les guía en la creación de tablas de datos y visualizaciones
title: Panel de información rápida
feature: Panels
exl-id: 09ebc3af-34ac-4f1f-8a5d-90da008f8697
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 26%

---

# Panel Información rápida {#quick-insights-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_quickinsights_button"
>title="Información rápida"
>abstract="Cree un panel para generar con rapidez una tabla de forma libre y una visualización adjunta para analizar y descubrir información de manera más rápida."

<!-- markdownlint-enable MD034 -->


[!UICONTROL Información rápida] proporciona una guía a los no analistas y a los nuevos usuarios de [!UICONTROL Analysis Workspace] para aprender a responder preguntas comerciales de forma rápida y sencilla. También es una buena herramienta para usuarios avanzados que desean responder a una pregunta simple rápidamente sin tener que crear una tabla ellos mismos.

La primera vez que empiece a usar este [!UICONTROL Analysis Workspace], es posible que se pregunte:

* qué visualizaciones serían más útiles,
* qué dimensiones y métricas pueden facilitar las perspectivas,
* dónde arrastrar y soltar elementos,
* dónde crear un filtro,
* y más.

Para ayudarte con estas preguntas,[!UICONTROL Quick Insights] aprovecha un algoritmo que te presenta las dimensiones, métricas, filtros e intervalos de fechas más populares que usa tu compañía. Este algoritmo se basa en el uso que hace su propia compañía de los componentes de datos en [!UICONTROL Analysis Workspace]. De hecho, verá dimensiones, métricas y filtros etiquetados con [!UICONTROL POPULAR] en la lista desplegable, como se muestra a continuación:

![Panel de información rápida.](assets/popular-tag.png)

[!UICONTROL Información rápida] le ayudará a lo siguiente:

* Crear correctamente una tabla de datos y una visualización adjunta en [!UICONTROL Analysis Workspace].
* Conocer la terminología y el vocabulario para componentes básicos y partes de [!UICONTROL Analysis Workspace].
* Realizar desgloses simples de dimensiones, añadir varias métricas o comparar filtros es fácil dentro de una [!UICONTROL tabla de forma libre].
* Cambiar o probar varios tipos de visualización para encontrar la herramienta de búsqueda para su análisis de forma rápida e intuitiva.

## Terminología clave básica

A continuación se indican algunos de los términos básicos que debe conocer. Cada tabla de datos consta de dos o más bloques de creación (componentes) que se utilizan para crear la historia de sus datos.

| Bloque de creación (componente) | Definición |
|---|---|
| **[!UICONTROL Dimensión]** | Las dimensiones son descripciones o características de datos de métricas que se pueden visualizar, desglosar y comparar en un proyecto. Son valores no numéricos y fechas que se desglosan en elementos de dimensión. Por ejemplo, *explorador* o *página* es una dimensión. |
| **[!UICONTROL Elemento de dimensión]** | Los elementos de dimensión son valores individuales para una dimensión. Por ejemplo, los elementos de dimensión para la dimensión del explorador serían *Chrome*, *Firefox*, *Edge* u otros. |
| [!UICONTROL Métrica] | Las métricas constituyen información cuantitativa sobre la actividad de la persona, tales como vistas, pulsaciones, recargas, tiempo promedio invertido, unidades, pedidos, ingresos, etc. |
| **[!UICONTROL Visualización]** | Workspace ofrece [varias visualizaciones](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) para generar representaciones visuales de sus datos. Como gráficos de barras, gráficos circulares, histogramas, gráficos de líneas, mapas, gráficos de dispersión, etc. |
| **[!UICONTROL Desglose de dimensiones]** | Un desglose de dimensiones es una forma de desglosar una dimensión por otras dimensiones. Por ejemplo, puede desglosar los estados de EE. UU. por dispositivos móviles para obtener las visitas de los dispositivos móviles por estado. O puede desglosar Dispositivos móviles por Tipos de dispositivos móviles, por Regiones, por Campañas internas y más. |
| **[!UICONTROL Filtro]** | Los filtros le permiten identificar subconjuntos de personas en función de sus características o de las interacciones con el sitio web. Por ejemplo, puede generar filtros de [!UICONTROL Personas] basados en <li>atributos: tipo de explorador, dispositivo, número de visitas, país, sexo o</li><li>interacciones: campañas, búsqueda de palabras clave, motor de búsqueda o</li><li>salidas y entradas: personas de Facebook, una página de aterrizaje definida, un dominio de referencia o</li><li> variables personalizadas: campo de formulario, categorías definidas, ID de cliente. |

## En su lugar, utilice 

Para usar un panel de **[!UICONTROL Quick insights]**:

1. Cree un panel de **[!UICONTROL Quick insights]**. Para obtener información sobre cómo crear un panel, consulte [Crear un panel](panels.md#create-a-panel).

1. La primera vez que uses un panel de **[!UICONTROL Quick insights]**, quizá quieras ver el breve [!UICONTROL tutorial de introducción] que te enseña algunos de los conceptos básicos. Seleccione ![HelpOutline](/help/assets/icons/HelpOutline.svg) junto al título del panel Quick Insights y seleccione **[!UICONTROL Tutorial introductorio]** en la ventana emergente.

1. Especifique [input](#panel-input) para el panel.

1. Observe la [salida](#panel-output) del panel.


### Entrada de panel

Seleccione los componentes básicos:

* **[!UICONTROL Analizar]** - especifique una dimensión (naranja)
* **[!UICONTROL por]**: especifique una métrica (verde)
* **[!UICONTROL filtrar por]** - especificar un filtro (azul)
* **[!UICONTROL en]** - especifique un intervalo de datos (púrpura).

Debe seleccionar al menos una dimensión y una métrica para que la visualización funcione correctamente.



Puede especificar los componentes básicos de tres formas:

* Arrastre y suelte los componentes desde el panel izquierdo.
* Empiece a escribir en uno de los campos de bloque de creación. Cuando se encuentra la entrada, el campo de bloque de creación se rellena automáticamente con los valores posibles.
* Especifique una lista desplegable de bloque de creación (por ejemplo `Country` en **[!UICONTROL Analizar]**) y busque el valor que desee usar en la lista de valores posibles (con ![ChevronRight](/help/assets/icons/ChevronRight.svg)) (por ejemplo, **[!UICONTROL Código de país]**).

Seleccione **[!UICONTROL Borrar]** para borrar todos los campos de entrada.


### Salida de panel

1. Cuando haya agregado al menos una dimensión y una métrica, podrá ver los resultados.

   ![La tabla de forma libre que muestra la dimensión verticalmente y la métrica horizontalmente.](assets/quick-insights-output.png)

   * Una tabla de forma libre con la dimensión (código de país) y métrica (sesiones), filtradas por sesiones web durante los últimos 12 meses.

   * Una visualización adjunta, en este caso un [gráfico de barras](/help/analysis-workspace/visualizations/bar.md). La visualización que se genera se basa en el tipo de datos agregados a la tabla. Cualquier dato basado en el tiempo (como [!UICONTROL Sesiones] por día/mes) tiene el valor predeterminado de un gráfico de [!UICONTROL líneas]. Cualquier dato no basado en el tiempo (como [!UICONTROL Sesiones] por [!UICONTROL Dispositivo]) tiene el valor predeterminado de un gráfico de [!UICONTROL barras]. Puede cambiar el tipo de visualización haciendo clic en la flecha desplegable situada junto al tipo de visualización.

1. Intente agregar más ajustes como se describe a continuación en [Más sugerencias](#more-tips)

1. Es posible que desee guardar el proyecto usando **[!UICONTROL Proyecto > Guardar]**.

## Más sugerencias

Aparecen otras sugerencias útiles en [!UICONTROL Quick Insights Builder], algunas de ellas en función de la última acción.

* En primer lugar, quizá desee completar el tutorial **[!UICONTROL Más sugerencias]**. Este tutorial se muestra 24 horas después de crear un proyecto con al menos una dimensión y una métrica. Seleccione ![EsquemaDeAyuda](/help/assets/icons/HelpOutline.svg) junto al título del panel Quick Insights y seleccione **[!UICONTROL Más sugerencias]** en la ventana emergente.

  ![Se muestra la notificación del Panel de información rápida después de seleccionar el icono Ayuda.](assets/qibuilder4.png)

* Puede analizar varias dimensiones y métricas, combinar o comparar filtros y especificar un rango de datos:

  ![Resultado del Generador de Quick Insights](assets/qibuilder-result.png)

   * **[!UICONTROL Analizar]** dimensión **[!UICONTROL Desglose por]**: puede usar hasta 3 niveles de desgloses en dimensiones para explorar en profundidad los datos que realmente necesita. Consulte ➊, ➋ y ➌.

   * Agregar más métricas **[!UICONTROL por]**: puede agregar hasta dos métricas más. Consulte ➍ y ➎.

   * **[!UICONTROL filtrar por]**: puede agregar hasta dos filtros más. Por ejemplo, agregue Reservas como filtro y combínelo con los filtros Reservas frecuentes y Prospectos que compare. Consulte ➏, ➐ y ➑.

   * activado: puede especificar el rango de datos. Consulte ➒.

## Limitaciones conocidas

Si intenta editar directamente en la tabla, el panel [!UICONTROL Quick Insights] puede no estar sincronizado. Seleccione **[!UICONTROL Resincronizar generador]** en la parte superior derecha del panel para restaurarlo a la configuración anterior de [!UICONTROL Quick Insights].

Recibe una advertencia antes de agregar cualquier cosa directamente a la tabla:

![Advertencia de la opción Resincronizar generador.](assets/qibuilder-outofsync.png)

De lo contrario, la creación directa hace que la tabla se comporte como una tabla de forma libre tradicional, sin las funciones útiles para los nuevos usuarios.


>[!MORELIKETHIS]
>
>[Crear un panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>