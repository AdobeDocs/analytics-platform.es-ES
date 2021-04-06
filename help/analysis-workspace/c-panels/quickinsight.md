---
description: Quick Insights es una herramienta para nuevos usuarios de Workspace que les guía en la creación de tablas de datos y visualizaciones
title: Panel de información rápida
exl-id: 09ebc3af-34ac-4f1f-8a5d-90da008f8697
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '1101'
ht-degree: 75%

---

# Panel de información rápida

>[!NOTE]
>
>Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

>[!IMPORTANT]
>
>**[!UICONTROL Quick]** Insightspanel está actualmente en pruebas limitadas. [Más información](https://docs.adobe.com/content/help/es-ES/analytics/landing/an-releases.html)

[!UICONTROL Quick Insights] proporciona una guía a los no analistas y a los nuevos usuarios de [!UICONTROL Analysis Workspace] para aprender a responder preguntas comerciales de forma rápida y sencilla. También es una buena herramienta para usuarios avanzados que desean responder a una pregunta simple rápidamente sin tener que crear una tabla ellos mismos.

La primera vez que empiece a utilizar este [!UICONTROL Analysis Workspace], es posible que se pregunte qué visualizaciones serían más útiles, qué dimensiones y métricas podrían facilitar las perspectivas, dónde arrastrar y soltar elementos, dónde crear un filtro, etc.

Para ayudarle con esto, y en función del uso que haga su propia empresa de los componentes de datos en [!UICONTROL Analysis Workspace], [!UICONTROL Quick Insights] aprovecha un algoritmo que le presentará las dimensiones, métricas, filtros e intervalos de fechas más populares que utilice su empresa. De hecho, verá dimensiones, métricas y filtros etiquetados como [!UICONTROL Popular] en la lista desplegable, como se muestra a continuación:

![](assets/popular-tag.png)

[!UICONTROL Quick Insights] le ayudará a lo siguiente:

* Crear correctamente una tabla de datos y una visualización adjunta en [!UICONTROL Analysis Workspace].
* Conocer la terminología y el vocabulario para componentes básicos y partes de [!UICONTROL Analysis Workspace].
* Realizar desgloses simples de dimensiones, agregar varias métricas o comparar filtros fácilmente dentro de una [!UICONTROL tabla improvisada].
* Cambiar o probar varios tipos de visualización para encontrar la herramienta de búsqueda para su análisis de forma rápida e intuitiva.

## Terminología clave básica

A continuación se incluyen algunos de los términos básicos que debe conocer. Cada tabla de datos consta de dos o más bloques de creación (componentes) que se utilizan para crear la historia de sus datos.

| Bloque de creación (componente) | Definición |
|---|---|
| [!UICONTROL Dimensión] | Las dimensiones son descripciones o características de datos de métricas que se pueden visualizar, desglosar y comparar en un proyecto. Son valores no numéricos y fechas que se desglosan en elementos de dimensión. Por ejemplo, “explorador” o “página” son dimensiones. |
| [!UICONTROL Elemento de dimensión] | Los elementos de dimensión son valores individuales para una dimensión. Por ejemplo, los elementos de dimensión para la dimensión del navegador serían “Chrome”, “Firefox”, “Edge”, etc. |
| [!UICONTROL Métrica] | Las métricas constituyen información cuantitativa sobre la actividad del visitante, tales como vistas, pulsaciones, recargas, tiempo promedio invertido, unidades, pedidos, ingresos, etc. |
| [!UICONTROL Visualización] | Workspace oferta [una serie de visualizaciones](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) para crear representaciones visuales de sus datos, como gráficos de barras, gráficos circulares, histogramas, gráficos de líneas, mapas, gráficos de dispersión, etc. |
| [!UICONTROL Desglose de dimensiones] | Un desglose de dimensión es una forma de desglosar literalmente una dimensión por otras dimensiones. En nuestro ejemplo, puede desglosar los estados de EE. UU. por dispositivos móviles para obtener las visitas de los dispositivos móviles por estado o puede desglosar Dispositivos móviles por Tipos de dispositivos móviles, por Regiones, por Campañas internas, etc. |
| [!UICONTROL filter] | los filtros permiten identificar subconjuntos de visitantes en función de sus características o de las interacciones con el sitio web. Por ejemplo, puede generar filtros de [!UICONTROL Visitor] basados en atributos: tipo de explorador, dispositivo, número de visitas, país, sexo o según las interacciones: campañas, búsqueda de palabras clave, motor de búsqueda o en función de salidas y entradas: visitantes de Facebook, una página de aterrizaje definida, un dominio de referencia o en función de variables personalizadas: campo de formulario, categorías definidas, ID de cliente. |

## Introducción a Quick Insights

1. Inicie sesión en Adobe Analytics con las credenciales que se le han proporcionado.
1. Vaya a [!UICONTROL Workspace], haga clic en **[!UICONTROL Crear nuevo proyecto]** y, a continuación, haga clic en **[!UICONTROL Quick Insights]**. (También puede acceder a este panel desde el menú **[!UICONTROL Panel]** en el carril izquierdo).

   ![](assets/qibuilder.png)

   ![](assets/qi-panel.png)

1. Cuando termine el inicio por primera vez, consulte el breve tutorial que le enseña algunos de los conceptos básicos del panel [!UICONTROL Quick Insights]. O bien, haga clic en **[!UICONTROL Omitir tutorial]**.
1. Seleccione los componentes básicos (también conocidos como componentes): dimensiones (naranja), métricas (verde), filtros (azul) o intervalos de fechas (púrpura) Debe seleccionar al menos una dimensión y una métrica para crear una tabla automáticamente.

   ![](assets/qibuilder2.png)

   Existen tres formas de seleccionar los componentes:
   * Arrástrelos y suéltelos desde el carril izquierdo.
   * Si sabe lo que está buscando: Comience a escribir y [!UICONTROL Quick Insights] rellenará automáticamente la búsqueda.
   * Haga clic en la lista desplegable y busque en la lista.

1. Cuando haya agregado al menos una dimensión y una métrica, se creará lo siguiente:

   * Una tabla improvisada con la dimensión (Estados de EE. UU. en este ejemplo) verticalmente y la métrica (Visitas) horizontalmente en la parte superior. Consulte esta tabla:

   ![](assets/qibuilder3.png)

   * Una visualización adjunta, en este caso un [gráfico de barras](/help/analysis-workspace/visualizations/bar.md). La visualización que se genera se basa en el tipo de datos agregados a la tabla. Cualquier dato basado en el tiempo (como [!UICONTROL Visitas] por día/mes) tiene un [!UICONTROL gráfico de líneas] predeterminado. Cualquier dato no basado en el tiempo (como [!UICONTROL Visitas] por [!UICONTROL dispositivo]) tiene el valor predeterminado de un [!UICONTROL gráfico de barras]. Puede cambiar el tipo de visualización haciendo clic en la flecha desplegable situada junto al tipo de visualización.


1. (Opcional) Desglose las dimensiones y vea los elementos de dimensión haciendo clic en la flecha derecha (>) junto a la dimensión.

1. Agregue más ajustes tal y como se describe a continuación en “Más sugerencias”.

1. Para guardar el proyecto, haga clic en **[!UICONTROL Proyecto > Guardar]**.

## Más sugerencias

En el [!UICONTROL Generador de Quick Insights], aparecerán otras sugerencias útiles, algunas de ellas en función de la última acción.

* En primer lugar, complete el tutorial **[!UICONTROL Más sugerencias]**: Acceda a ella a través de la Ayuda (?) junto al título de [!UICONTROL Quick Insights]. Este tutorial se muestra 24 horas después de crear un proyecto con al menos una dimensión y una métrica.

   ![](assets/qibuilder4.png)

* **Desglose por**: Puede usar hasta 3 niveles de desgloses en dimensiones para explorar en profundidad los datos que realmente necesita.

   ![](assets/qibuilder5.png)

* **Añadir más métricas**: Puede agregar hasta dos métricas más utilizando el operador AND para agregarlas a la tabla.

   ![](assets/qibuilder6.png)

* **Añadir más filtros**: Puede agregar hasta dos filtros más utilizando los operadores AND u OR para agregarlos a la tabla. Observe lo que sucede en la tabla cuando agrega Usuarios móviles OR Visitantes fieles. Están uno al lado del otro, encima de las métricas. Si agregara Usuarios móviles Y Visitantes fieles, vería los resultados de ambos filtros juntos y se apilarían uno encima del otro en la tabla.

   ![](assets/qibuilder7.png)

## Limitaciones conocidas

Si intenta editar directamente dentro de la tabla, el panel de [!UICONTROL Quick Insights] no estará sincronizado. Puede restaurarla a la configuración anterior de [!UICONTROL Quick Insights] haciendo clic en **[!UICONTROL Resincronizar generador]** en la parte superior derecha del panel.

![](assets/qibuilder9.png)

Recibirá una advertencia antes de agregar cualquier cosa directamente a la tabla:

![](assets/qibuilder8.png)

De lo contrario, la creación directa hará que la tabla ahora se comporte como una tabla improvisada tradicional, sin las funciones útiles para los nuevos usuarios.
