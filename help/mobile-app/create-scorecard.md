---
description: Cómo crear un cuadro de resultados de paneles de Adobe Analytics
title: Creación de un cuadro de resultados
feature: Analytics Dashboards
role: User, Admin
exl-id: 12531600-7e88-4d56-a2a5-e5b346f91937
solution: Customer Journey Analytics
source-git-commit: 7065215f89f964e7504f3e95996b352410b89779
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Creación de un cuadro de resultados móvil

La siguiente información enseña a los depuradores de datos de Adobe Analytics sobre cómo configurar y presentar paneles para los usuarios ejecutivos. Para empezar, puede ver el vídeo del Generador de cuadros de resultados de los paneles de Adobe Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/343458)

>[!NOTE]
>Las capturas de pantalla del cuadro de resultados de esta página se tomaron en la IU de Adobe Analytics, no de CJA. Las IU son casi idénticas.

Un cuadro de resultados de Adobe Analytics muestra visualizaciones de datos clave para los usuarios ejecutivos en un diseño en mosaico, tal y como se muestra a continuación:

![Ejemplo de informe de valoración](assets/intro_scorecard.png)

Como gestor de datos del cuadro de resultados, puede utilizar el Generador del cuadro de resultados para configurar los mosaicos que aparecerán en el cuadro de resultados de su consumidor ejecutivo. También puede configurar cómo se pueden ajustar las vistas detalladas o los desgloses cuando se pulsen los mosaicos. La interfaz del Generador de informes de valoración se muestra a continuación:

![Generador de informes de valoración](assets/scorecard_builder.png)

Para crear un cuadro de resultados, deberá hacer lo siguiente:

1. Acceda a la plantilla [!UICONTROL informe de valoración móvil en blanco].
2. Configure el cuadro de resultados con datos y guárdelo.

## Acceda a la plantilla [!UICONTROL informe de valoración móvil en blanco] {#template}

Puede acceder a la plantilla del [!UICONTROL cuadro de resultados móvil en blanco] al crear un nuevo proyecto o desde el menú Herramientas.

### Creación de un nuevo proyecto {#create}

1. Abra Adobe Analytics y haga clic en la ficha **[!UICONTROL Espacio de trabajo]**.
1. Haga clic en **[!UICONTROL Crear nuevo proyecto]** y seleccione la plantilla de proyecto **[!UICONTROL Informe de valoración móvil en blanco]**.
1. Haga clic en **[!UICONTROL Crear]**.

![Plantilla del informe de valoración](assets/new_template.png)

### Menú Herramientas

1. En el menú **[!UICONTROL Herramientas]**, seleccione **[!UICONTROL Paneles de Analytics (aplicación móvil)]**.
1. En la pantalla siguiente, haga clic en **[!UICONTROL Crear nuevo informe de valoración]**.

## Configure el informe de valoración con datos y guárdelo {#configure}

Para implementar la plantilla del informe de valoración:

1. En **[!UICONTROL Propiedades]** (en el carril derecho), especifique un **[!UICONTROL grupo de informes de proyecto]** cuyos datos quiera utilizar. Los grupos de informes son vistas de datos en CJA.

   ![Selección del grupo de informes](assets/properties_save.png)

1. Para añadir un nuevo mosaico al informe de valoración, arrastre una métrica desde el panel izquierdo y suéltela en la zona **[!UICONTROL Arrastrar y soltar métricas aquí]**. También puede insertar una métrica entre dos mosaicos del mismo modo.

   ![Agregar mosaicos](assets/build_list.png)


1. Desde cada mosaico puede acceder a una vista detallada que muestra información adicional sobre la métrica, como los elementos principales de una lista de dimensiones relacionadas.

## Adición de dimensiones o métricas {#dimsmetrics}

Para agregar una dimensión relacionada a una métrica, arrastre una dimensión desde el panel izquierdo y suéltela en un mosaico.

Por ejemplo, puede añadir dimensiones adecuadas (como **[!DNL Marketing Channel]**, en este ejemplo) a la métrica **[!UICONTROL Visitantes únicos]** arrastrándolas y soltándolas en el mosaico. Los desgloses de dimensiones aparecen en la sección [!UICONTROL Profundizar en] (desglose) de las **[!UICONTROL Propiedades]** específicas del mosaico. Puede agregar varias dimensiones a cada mosaico.

![Agregar dimensiones](assets/layer_dimensions.png)

## Aplicar filtros {#filters}

Para aplicar filtros a mosaicos individuales, arrastre un filtro (los segmentos son filtros en CJA) desde el panel izquierdo y suéltelo directamente sobre el mosaico.

Si desea aplicar el filtro a todos los mosaicos del cuadro de resultados, suelte el mosaico encima del cuadro de resultados. O bien, también puede aplicar filtros seleccionando filtros en el menú de filtro debajo de los intervalos de fechas. Puede [configurar y aplicar filtros para sus informes de valoración](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=es) del mismo modo que lo haría en Adobe Analytics Workspace.

![Generar filtros](assets/segment_ui.png)

## Adición de intervalos de fechas {#dates}

Añada y quite combinaciones de intervalos de fechas que se puedan seleccionar en el cuadro de resultados seleccionando la lista desplegable de intervalo de fechas.

![Nuevo cuadro de resultados](assets/new_score_card.png)

Cada nuevo cuadro de resultados comienza con 6 combinaciones de intervalo de fechas que se centran en los datos de hoy y ayer. Puede quitar intervalos de fechas innecesarios haciendo clic en la x o puede editar cada combinación de intervalos de fechas haciendo clic en el lápiz.

![Nuevo cuadro de resultados2](assets/new_score_card2.png)

Para crear o cambiar una fecha principal, utilice la lista desplegable para seleccionar entre intervalos de fechas disponibles o arrastre y suelte un componente de fecha del carril derecho en la zona de colocación.

![Nuevo cuadro de resultados3](assets/new_score_card3.png)

Para crear una fecha de comparación, puede seleccionar entre cómodos preconjuntos para comparaciones de tiempo comunes en el menú desplegable. También puede arrastrar y soltar un componente de fecha desde el carril derecho.

![Nuevo cuadro de resultados4](assets/new_score_card4.png)

Si el intervalo de fechas que desea aún no se ha creado, puede crear uno nuevo haciendo clic en el icono de calendario.

![Nuevo cuadro de resultados5](assets/new_score_card5.png)

Esto le llevará al generador de intervalos de fechas, donde puede crear y guardar un nuevo componente de intervalo de fechas.

### Mostrar u ocultar intervalos de fechas de comparación {#show-comparison-dates}

Para incluir intervalos de fechas de comparación, cambie la configuración de **Incluir fechas de comparación**.

![Incluir fechas de comparación](assets/include-comparison-dates.png)

La configuración está *activa* de forma predeterminada. Cambie a *desactivado* si no desea ver las fechas de comparación.

![Configuración de fecha de comparación no seleccionada](assets/no-comparison-dates.png)

## Aplicación de visualizaciones {#viz}

Los paneles de Analytics ofrecen cuatro visualizaciones que le proporcionan buenos conocimientos de los elementos y las métricas de dimensión. Cambie a una visualización diferente al variar el [!UICONTROL tipo de gráfico] de las [!UICONTROL propiedades] de un mosaico. Seleccione el mosaico derecho y cambie el tipo de gráfico.

![Propiedades del mosaico](assets/properties.png)

O bien, haga clic en el botón [!UICONTROL Visualizaciones] en el carril izquierdo y arrastre y suelte la visualización derecha en el mosaico:

![Visualizaciones](assets/vizs.png)

### [!UICONTROL Número de resumen]

Utilice la visualización Número de resumen para resaltar un número elevado que es importante en un proyecto.

![Número de resumen](assets/summary-number.png)

### [!UICONTROL Anillo]

Similar a un gráfico circular, esta visualización muestra los datos como partes o filtros de un todo. Utilice un gráfico de anillo para comparar porcentajes de un total. Por ejemplo, supongamos que desea ver qué plataforma de publicidad contribuyó al número total de visitantes únicos:

![Visualización de anillo](assets/donut-viz.png)

### [!UICONTROL Líneas]

La visualización de línea representa las métricas con una línea para mostrar cómo cambian los valores con el paso del tiempo. Un gráfico de líneas muestra las dimensiones a lo largo del tiempo, pero funciona con cualquier visualización. En este ejemplo se visualiza la dimensión de la categoría del producto.

![Visualización de líneas](assets/line.png)

### [!UICONTROL Barra horizontal]

Esta visualización muestra las barras horizontales que representan los distintos valores de una o varias métricas. Por ejemplo, para ver fácilmente cuáles son sus productos principales, utilice las [!UICONTROL Barras horizontales] para su visualización preferida.

![Barras horizontales](assets/horizontal.png)

### Eliminar elemento de dimensión [!UICONTROL no especificado]

Si desea quitar elementos de dimensión [!UICONTROL No especificados] de los datos, haga lo siguiente:

1. Seleccione el mosaico correcto.
1. En el carril derecho, debajo de **[!UICONTROL Profundizar en]**, seleccione la flecha derecha junto al elemento de dimensión cuyos elementos **[!UICONTROL No especificados]** desea eliminar.

   ![no especificado](assets/unspecified.png)

1. Haga clic en el icono situado junto a **[!UICONTROL No especificado]** para eliminar los datos no especificados de los informes. También puede eliminar cualquier otro elemento de dimensión.

## Vista y configuración de propiedades de mosaico {#tiles}

Al hacer clic en un mosaico en el Generador de cuadros de resultados, el carril derecho muestra las propiedades y características asociadas a dicho mosaico y su dispositiva de detalle. En este carril, puede proporcionar un nuevo **Título** para el mosaico y, alternativamente, configurar el mosaico aplicando filtros. Los segmentos son filtros en CJA.

![Mosaico de propiedades](assets/properties-tile-new.png)

## Ver diapositivas de detalles {#view-detail-slides}

Cuando hace clic en un mosaico, la ventana emergente dinámica le muestra cómo aparece la diapositiva de detalle para el usuario ejecutivo en la aplicación. Puede agregar dimensiones para desglosar los datos según sus necesidades específicas. Si no se ha aplicado ninguna dimensión, la dimensión de desglose será **hora** o **días**, según el intervalo de fecha predeterminado.

Los desgloses afinan el análisis al desglosar las métricas por elementos de dimensión como los siguientes:

* Métrica Visitantes únicos desglosada por plataforma de publicidad (AMO ID)
* Visitas desglosadas por categoría de producto (venta minorista)
* Ingresos totales desglosados por nombre del producto

![Breakdown_view](assets/break_view.png)

Cada dimensión agregada al mosaico se mostrará en una lista desplegable de la vista detallada de la aplicación. El usuario ejecutivo puede elegir entre las opciones que se muestran en la lista desplegable.

## Personalización de diapositivas de detalle {#customize-detail-slide}

Las diapositivas de detalles personalizadas le permiten centrarse aún más en la información que comparte con su audiencia.

>[!VIDEO](https://video.tv.adobe.com/v/3410002)

Puede modificar el diseño de cada diapositiva de detalle y añadir texto para explicar mejor lo que el usuario final puede ver en los datos. También puede cambiar el tipo de gráfico mediante el menú desplegable.

![Diapositiva de detalle personalizada](assets/custom-detail-slide.png)

### Cambio del diseño de la diapositiva

Cambie el diseño de la diapositiva para centrarse en la información más importante. Por ejemplo, puede cambiar el diseño para mostrar solo un gráfico o una tabla. Para cambiar el diseño de la diapositiva, seleccione uno de los formatos prediseñados.

![Diseño de diapositivas](assets/layout.png)

También puede cambiar el diseño de la diapositiva arrastrando y soltando los componentes de visualización del carril izquierdo al lienzo. Cada diapositiva de detalle solo puede admitir dos visualizaciones a la vez.

![Cambio de diseño de diapositiva](assets/slide-layout-change.png)

### Adición de texto descriptivo a una diapositiva

Puede agregar texto para proporcionar información significativa acerca de lo que contienen los gráficos o matices sobre los datos.

Para agregar texto a una diapositiva de detalles, seleccione un diseño que muestre el símbolo `T` o arrastre y suelte el componente de visualización Texto desde el carril izquierdo. El editor de texto se abrirá automáticamente al agregar una nueva visualización de texto o al elegir un diseño de diapositiva con texto. El editor de texto proporciona todas las opciones estándar para dar formato al texto. Puede aplicar estilos de texto como párrafo, encabezados y subencabezados, y aplicar negrita y cursiva. Puede justificar el texto, agregar listas con números y viñetas y agregar vínculos. Cuando haya terminado de editar, seleccione el botón minimizar en la esquina superior derecha del editor de texto para cerrarlo. Para editar el texto que ya añadió, seleccione el icono de lápiz para abrir de nuevo el editor de texto.

![Cambio del diseño de diapositiva](assets/add-descriptive-text.png)

## Eliminación de componentes {#remove}

Del mismo modo, para eliminar un componente que se aplique a todo el cuadro de resultados, haga clic en cualquier lugar del cuadro de resultados de los mosaicos y, a continuación, elimínelo haciendo clic en la **x** que aparece al pasar el ratón sobre el componente, como se muestra a continuación para el filtro **Visitas por primera vez**:

![Remove_components](assets/new_remove.png)

## Creación de historias de datos {#create-data-story}

Una historia de datos es una colección de puntos de datos de soporte, contexto empresarial y métricas relacionadas creadas en torno a un tema o métrica central.

Por ejemplo: si se centra en el tráfico web, la métrica más importante pueden ser las visitas, pero también puede estar interesado en nuevos visitantes y visitantes únicos, y es posible que desee ver los datos desglosados por página web o por el tipo de dispositivo del que proviene el tráfico. Las historias de datos en los proyectos de cuadros de resultados móviles le permiten colocar las métricas más importantes en un lugar destacado y centrado, mientras cuenta toda la historia detrás de las métricas con varias diapositivas de detalle.

Vea el vídeo para obtener más información sobre la creación de historias de datos en proyectos de cuadros de resultados móviles en Analysis Workspace.

>[!VIDEO](https://video.tv.adobe.com/v/3416392/?quality=12&learn=on)

**Para crear una historia de datos** {#data-story-create}

Cree su historia de datos agregando varias diapositivas de detalle a un mosaico.

1. Comience con un proyecto de cuadro de resultados móvil.
1. Seleccione un mosaico en el que desee crear una historia.
   ![Crear una historia de datos](assets/data-story1.png)
   ![Crear iconos de historia de datos](assets/create-data-story.png){width=".50%"}
1. Agregue diapositivas para crear su historia de datos. La primera diapositiva se genera de forma predeterminada.
Para añadir nuevas diapositivas, pase el ratón sobre una diapositiva o haga clic en ella y, a continuación, seleccione una de las opciones disponibles:
   * Pulse el signo + para crear una nueva diapositiva.
   * Pulse el icono de duplicado para duplicar la diapositiva existente.
1. Si crea una diapositiva en blanco, arrastre y suelte los componentes desde el carril izquierdo o elija un diseño para rellenar automáticamente la diapositiva con los datos del mosaico.
   ![Crear una historia de datos](assets/data-story2.png)
Para eliminar una diapositiva, pulse el icono de papelera.

### Personalizar una historia de datos {#customize-data-story}

Las historias de datos le permiten personalizar todo para que pueda compartir información que desee compartir y excluir todo lo que no necesite. Puede personalizar mosaicos y diapositivas individuales para añadir filtros, mostrar desgloses, cambiar el diseño y cambiar las visualizaciones.

**Para personalizar mosaicos**

1. Pulse un mosaico. El mosaico seleccionado está delineado en azul y el panel derecho muestra las propiedades del mosaico.
1. Cambie el título, el tipo de gráfico y otras opciones de mosaico.
1. Arrastre un componente al mosaico.
   ![Crear una historia de datos](assets/data-story3.png)
Al arrastrar y soltar un componente, como una visualización, en un mosaico, el componente se aplica a todas las diapositivas de la historia de datos.
1. Para aplicar un cambio solo al título, mantenga pulsada la tecla Mayús para aplicar el cambio.
   ![Crear una historia de datos](assets/data-story4.png)

>[!NOTE]
>Las diapositivas heredan los componentes del mosaico, pero los mosaicos no heredan los componentes de las diapositivas.

**Para personalizar diapositivas individuales**

Puede cambiar la visualización de diapositivas individuales en un artículo de datos. Por ejemplo, puede cambiar una barra horizontal a un gráfico de anillos para una diapositiva específica. También puede cambiar el diseño. Consulte [Personalizar diapositivas de detalle](#customize-detail-slide).

### Previsualización de una historia de datos {#preview-data-story}

Después de crear una historia de datos, utilice el **Previsualizar** para ver e interactuar con una historia de datos como si fuera un usuario de la aplicación. Para obtener información sobre la vista previa del artículo de datos, consulte [Previsualización de un cuadro de resultados](#preview)

### Desplazamiento entre mosaicos y diapositivas {#navigate-tiles-slides}

La barra de navegación muestra iconos que representan lo que hay en cada diapositiva. La barra de exploración facilita el desplazamiento a una diapositiva específica si tiene muchas diapositivas.

Para desplazarse entre el mosaico y las diapositivas, pulse la barra de navegación.
![Crear una historia de datos](assets/data-story5.png)
![Crear una historia de datos](assets/data-story-nav.png){width="45%"}

También puede desplazarse hacia atrás y hacia adelante utilizando las flechas del teclado o seleccionando un componente y manteniéndolo a la izquierda o a la derecha de la pantalla para desplazarse.

## Previsualizar informes de valoración {#preview}

Puede obtener una vista previa del aspecto y el funcionamiento del cuadro de resultados una vez que se publique en la aplicación de paneles de Analytics.

1. Haga clic en **[!UICONTROL Vista previa]** en la esquina superior derecha de la pantalla.

   ![Preview_scorecards](assets/preview.png)

1. Para ver el aspecto que tendrá el cuadro de resultados en distintos dispositivos, seleccione un dispositivo del menú desplegable [!UICONTROL Vista previa del dispositivo].

   ![Device_preview](assets/device-preview.png)

1. Para interactuar con la vista previa, puede hacer lo siguiente:

   * Haga clic con el botón izquierdo para simular los toques en la pantalla del teléfono.

   * Utilice la función de desplazamiento del equipo para simular el desplazamiento por la pantalla del teléfono con el dedo.

   * Haga clic y mantenga presionado para simular el efecto del dedo en la pantalla del teléfono. Esto resulta útil para interactuar con las visualizaciones en la vista detallada.

## Nombrar cuadros de resultados {#name}

Para asignar un nombre al informe de valoración, haga clic en el área de nombres de la parte superior izquierda de la pantalla y escriba el nuevo nombre.

![Naming_Scorecards](assets/new_name.png)

## Compartir cuadros de resultados {#share}

Para compartir el informe de valoración con un usuario ejecutivo:

1. Haga clic en el menú **[!UICONTROL Compartir]** y seleccione **[!UICONTROL Compartir informe de valoración]**.

1. En el formulario **[!UICONTROL Compartir informe de valoración móvil]**, rellene los campos con:

   * Proporción del nombre del cuadro de resultados
   * Proporción de la descripción del cuadro de resultados
   * Añada las etiquetas relevantes
   * Especificación de los destinatarios del cuadro de resultados

1. Haga clic en **[!UICONTROL Compartir]**.

![Share_Scorecards](assets/new_share.png)

Una vez que haya compartido un cuadro de resultados, los destinatarios podrán acceder a él en sus paneles de Analytics. Si realiza cambios posteriores en el cuadro de resultados mediante el Generador de informes de valoración, estos se aplicarán automáticamente al informe compartido. Los usuarios ejecutivos verán los cambios después de actualizar el informe de valoración en su aplicación.

Si actualiza el cuadro de resultados con nuevos componentes, es posible que desee volver a compartirlo (marque la opción **[!UICONTROL Compartir componentes incrustados]**) para asegurarse de que los usuarios ejecutivos tengan acceso a estos cambios.
