---
description: Quick Insights es una herramienta para nuevos usuarios de Workspace que les guía en la creación de tablas de datos y visualizaciones
title: Panel de perspectivas rápidas
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '1101'
ht-degree: 6%

---


# Panel de perspectivas rápidas

>[!NOTE] Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

>[!IMPORTANT]
>
>**[!UICONTROL El panel de perspectivas]** rápidas se encuentra actualmente en pruebas limitadas. [Más información](https://docs.adobe.com/content/help/es-ES/analytics/landing/an-releases.html)

[!UICONTROL Quick Insights] proporciona una guía a los no analistas y a los nuevos usuarios de [!UICONTROL Analysis Workspace] para aprender a responder preguntas comerciales de forma rápida y sencilla. También es una buena herramienta para usuarios avanzados que desean responder a una pregunta simple rápidamente sin tener que crear una tabla ellos mismos.

Al utilizar este [!UICONTROL Analysis Workspace]por primera vez, es posible que se pregunte qué visualizaciones serían más útiles, qué dimensiones y métricas podrían facilitar las perspectivas, dónde arrastrar y soltar elementos, dónde crear un segmento, etc.

Para ayudarle con esto, y en función del uso que haga su propia compañía de los componentes de datos en el [!UICONTROL Analysis Workspace], [!UICONTROL Quick Insights] aprovecha un algoritmo que le presentará las dimensiones, métricas, segmentos e intervalos de fechas más populares que utilice su compañía. De hecho, verá dimensiones, métricas y segmentos etiquetados como [!UICONTROL populares] en la lista desplegable, como se muestra a continuación:

![](assets/popular-tag.png)

[!UICONTROL Quick Insights] le ayuda

* Cree correctamente una tabla de datos y una visualización adjunta en el [!UICONTROL Analysis Workspace].
* Conozca la terminología y el vocabulario para componentes básicos y piezas de [!UICONTROL Analysis Workspace].
* Realice desgloses simples de dimensiones, agregue varias métricas o compare segmentos fácilmente dentro de una tabla [!UICONTROL improvisada].
* Cambie o pruebe varios tipos de visualización para encontrar la herramienta de búsqueda para su análisis de forma rápida e intuitiva.

## Terminología clave básica

A continuación se incluyen algunos de los términos básicos con los que debe estar familiarizado. Cada tabla de datos consta de dos o más bloques de creación (componentes) que se utilizan para contar el historial de datos.

| Bloque de creación (componente) | Definición |
|---|---|
| [!UICONTROL Dimensión] | Las dimensiones son descripciones o características de los datos de métricas que se pueden ver, desglosar y comparar en un proyecto. Son valores no numéricos y fechas que se desglosan en elementos de dimensión. Por ejemplo, &quot;browser&quot; o &quot;page&quot; son dimensiones. |
| [!UICONTROL Elemento de dimensión] | Los elementos de dimensión son valores individuales para una dimensión. Por ejemplo, los elementos de dimensión para la dimensión del navegador serían &quot;Chrome&quot;, &quot;Firefox&quot;, &quot;Edge&quot;, etc. |
| [!UICONTROL Métrica] | Las métricas constituyen información cuantitativa sobre la actividad del visitante, tales como vistas, pulsaciones, recargas, tiempo promedio invertido, unidades, pedidos, ingresos, etc. |
| [!UICONTROL Visualización] | Workspace offers [a number of visualizations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) to build visual representations of your data, such as bar charts, donut charts, histograms, line charts, maps, scatterplots, and others. |
| [!UICONTROL Desglose de dimensiones] | Un desglose de dimensión es una forma de desglosar literalmente una dimensión por otras dimensiones. En nuestro ejemplo, puede desglosar los estados de EE. UU. por dispositivos móviles para obtener las visitas de los dispositivos móviles por estado o puede desglosar Dispositivos móviles por tipos de dispositivos móviles, por regiones, por Campañas internas, etc. |
| [!UICONTROL Segmento] | Los segmentos permiten identificar subconjuntos de visitantes en función de las características o las interacciones con el sitio web. Por ejemplo, puede generar segmentos de [!UICONTROL Visitante] basados en atributos: tipo de explorador, dispositivo, número de visitas, país, sexo o según las interacciones: campañas, búsqueda de palabras clave, motor de búsqueda o en función de salidas y entradas: visitantes de Facebook, una página de aterrizaje definida, un dominio de referencia o basados en variables personalizadas: campo de formulario, categorías definidas, ID de cliente. |

## Introducción a Quick Insights

1. Inicie sesión en Adobe Analytics con las credenciales que se le han proporcionado.
1. Vaya a [!UICONTROL Workspace] , haga clic en **[!UICONTROL Crear nuevo proyecto]** y, a continuación, haga clic en **[!UICONTROL Quick Insights]**. (También puede acceder a este panel desde el menú **[!UICONTROL Panel]** en el carril izquierdo).

   ![](assets/qibuilder.png)

   ![](assets/qi-panel.png)

1. Cuando termine el inicio por primera vez, consulte el breve tutorial que le enseña algunos de los conceptos básicos del panel [!UICONTROL Perspectivas] rápidas. O bien, haga clic para **[!UICONTROL omitir tutorial]**.
1. Seleccione los componentes (también conocidos como componentes): dimensiones (naranja), métricas (verde), segmentos (azul) o intervalos de fechas (púrpura) Debe seleccionar al menos una dimensión y una métrica para crear una tabla automáticamente.

   ![](assets/qibuilder2.png)

   Existen tres formas de seleccionar los componentes:
   * Arrástrelos y suéltelos desde el carril izquierdo.
   * Si sabe lo que está buscando: La escritura de Inicios y las perspectivas [!UICONTROL rápidas] le rellenarán los espacios en blanco.
   * Haga clic en la lista desplegable y busque la lista.

1. Cuando haya agregado al menos una dimensión y una métrica, se creará lo siguiente:

   * Una tabla improvisada con la dimensión (aquí, Estados de EE.UU.) verticalmente y la métrica (aquí, Visitas) horizontalmente en la parte superior. Consulte esta tabla:

   ![](assets/qibuilder3.png)

   * Una visualización adjunta, en este caso un gráfico [de barras](/help/analysis-workspace/visualizations/bar.md). La visualización que se genera se basa en el tipo de datos agregados a la tabla. Cualquier dato basado en el tiempo (como [!UICONTROL Visitas] por día/mes) tiene un gráfico de [!UICONTROL líneas] predeterminado. Cualquier dato no basado en el tiempo (como [!UICONTROL Visitas] por [!UICONTROL dispositivo]) tiene el valor predeterminado de un gráfico de [!UICONTROL barras] . Puede cambiar el tipo de visualización haciendo clic en la flecha desplegable situada junto al tipo de visualización.


1. (Opcional) Desglose las dimensiones y vea los elementos de dimensión haciendo clic en la flecha > derecha junto a la dimensión.

1. Intente agregar más refinamientos como se describe a continuación en &quot;Más sugerencias&quot;.

1. Para guardar el proyecto, haga clic en **[!UICONTROL Proyecto > Guardar]**.

## Más sugerencias

En el Generador [!UICONTROL de perspectivas]rápidas aparecerán otras sugerencias útiles, algunas de ellas en función de la última acción.

* En primer lugar, complete el tutorial **[!UICONTROL Más sugerencias]** : Acceda a ella a través de la Ayuda (?) junto al título de [!UICONTROL Quick Insights] . Este tutorial se muestra 24 horas después de crear un proyecto con al menos una dimensión y una métrica.

   ![](assets/qibuilder4.png)

* **Desglose por**: Puede usar hasta 3 niveles de desgloses en dimensiones para explorar en profundidad los datos que realmente necesita.

   ![](assets/qibuilder5.png)

* **Añadir más métricas**: Puede agregar hasta dos métricas más utilizando el operador Y para agregarlas a la tabla.

   ![](assets/qibuilder6.png)

* **Añadir más segmentos**: Puede agregar hasta dos segmentos más utilizando los operadores Y u O para agregarlos a la tabla. Observe lo que sucede en la tabla cuando agrega Usuarios móviles O Visitantes fieles. Están uno al lado del otro, encima de las métricas. Si agregara Usuarios móviles Y Visitantes fieles, vería los resultados de ambos segmentos juntos y se apilarían uno encima del otro en la tabla.

   ![](assets/qibuilder7.png)

## Limitaciones conocidas

Si intenta editar directamente dentro de la tabla, el panel [!UICONTROL Perspectivas] rápidas no estará sincronizado. Puede restaurarla a la configuración anterior de [!UICONTROL Quick Insights] haciendo clic en **[!UICONTROL Resincronizar generador]** en la parte superior derecha del panel.

![](assets/qibuilder9.png)

Recibirá una advertencia antes de agregar cualquier cosa directamente a la tabla:

![](assets/qibuilder8.png)

De lo contrario, la creación directa hará que la tabla ahora se comporte como una tabla improvisada tradicional, sin las funciones útiles para los nuevos usuarios.

