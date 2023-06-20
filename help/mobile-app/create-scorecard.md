---
description: Cómo crear y compartir cuadros de resultados de paneles de Adobe Analytics
title: Crear y compartir cuadros de resultados
feature: Analytics Dashboards
role: User, Admin
exl-id: 12531600-7e88-4d56-a2a5-e5b346f91937
solution: Customer Journey Analytics
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '2529'
ht-degree: 76%

---

# Creación de un cuadro de resultados móvil

La siguiente información enseña a los depuradores de datos de Adobe Analytics sobre cómo configurar y presentar paneles para los usuarios ejecutivos. Para empezar, puede ver el vídeo del generador del cuadro de resultados de los paneles de Adobe Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/343458)

>[!NOTE]
>Las capturas de pantalla del cuadro de resultados de esta página se tomaron en la interfaz de usuario de Adobe Analytics, no del Customer Journey Analytics. Las IU son casi idénticas.

Un cuadro de resultados de Adobe Analytics muestra visualizaciones de datos clave para los usuarios ejecutivos en un diseño en mosaico, tal y como se muestra a continuación:

![Ejemplo de informe de valoración](assets/intro_scorecard.png)

Como gestor de datos del cuadro de resultados, puede utilizar el generador del cuadro de resultados para configurar los mosaicos que aparecerán en el cuadro de resultados de su consumidor ejecutivo. También puede configurar cómo se pueden ajustar las vistas detalladas o los desgloses cuando se pulsen los mosaicos. A continuación, se muestra la interfaz del generador de cuadros de resultados:

![Generador de informes de valoración](assets/scorecard_builder.png)

Para crear el informe de valoración, debe hacer lo siguiente:

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

1. En **[!UICONTROL Propiedades]** (en el carril derecho), especifique una **[!UICONTROL Vista de datos de proyecto]**, cuyos datos quiera utilizar.

   ![selección de vista de datos](assets/properties_save.png)

1. Para agregar un nuevo mosaico al cuadro de resultados, arrastre una métrica desde el panel izquierdo y suéltela en el **[!UICONTROL Arrastre y suelte las métricas aquí]** zona. También puede insertar una métrica entre dos mosaicos del mismo modo.

   ![Agregar mosaicos](assets/build_list.png)


1. Desde cada mosaico puede acceder a una vista detallada que muestra información adicional sobre la métrica, como los elementos principales de una lista de dimensiones relacionadas.

## Adición de dimensiones o métricas {#dimsmetrics}

Para agregar una dimensión relacionada a una métrica, arrastre una dimensión desde el panel izquierdo y suéltela en un mosaico.

Por ejemplo, puede añadir dimensiones adecuadas (como **[!DNL Marketing Channel]**, en este ejemplo) a la métrica **[!UICONTROL Visitantes únicos]** arrastrándolas y soltándolas en el mosaico. Los desgloses de dimensiones aparecen en la sección [!UICONTROL Profundizar en] (desglose) de las **[!UICONTROL Propiedades]** específicas del mosaico. Puede agregar varias dimensiones a cada mosaico.

![Agregar dimensiones](assets/layer_dimensions.png)

## Aplicar filtros {#filters}

Para aplicar filtros a mosaicos individuales, arrastre un filtro (los segmentos son filtros en Customer Journey Analytics) desde el panel izquierdo y suéltelo directamente sobre el mosaico.

Si desea aplicar el filtro a todos los mosaicos del cuadro de resultados, suelte el mosaico encima del cuadro de resultados. O bien, también puede aplicar filtros seleccionando filtros en el menú de filtro debajo de los intervalos de fechas. Usted [configuración y aplicación de filtros para los cuadros de resultados](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=es) del mismo modo que en Adobe Analytics Workspace.

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

Similar a un gráfico circular, esta visualización muestra los datos como partes o filtros de un todo. Utilice un gráfico de anillo para comparar porcentajes de un total. Por ejemplo, supongamos que desea ver qué plataforma de publicidad contribuyó al número total de personas únicas:

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

Al hacer clic en un mosaico en el Generador de cuadros de resultados, el carril derecho muestra las propiedades y características asociadas a dicho mosaico y su diapositiva de detalle. En este carril, puede proporcionar un nuevo **Título** para el mosaico y, alternativamente, configurar el mosaico aplicando filtros. Los segmentos son filtros en el Customer Journey Analytics.

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

Del mismo modo, para quitar un componente que se aplica a todo el cuadro de resultados, haga clic en cualquier lugar del cuadro de resultados de los mosaicos y, a continuación, quítelo haciendo clic en **x** que aparece al pasar el ratón por encima del componente, como se muestra a continuación para la variable **Visitas por primera vez**:

![Remove_components](assets/new_remove.png)

## Creación de historias de datos {#create-data-story}

Una historia basada en datos es una colección de puntos de datos de apoyo, contexto empresarial y métricas relacionadas creada en torno a un tema o métrica central.

Por ejemplo: si se centra en el tráfico web, la métrica más importante pueden ser las visitas, pero también puede estar interesado en nuevas personas, personas únicas y es posible que desee ver los datos desglosados por página web o por el tipo de dispositivo del que proviene el tráfico. Las historias basadas en datos en proyectos de cuadros de resultados móviles le permiten poner sus métricas más importantes en primer plano y, al mismo tiempo, contar toda la historia que hay detrás con múltiples diapositivas detalladas.

Vea el vídeo para obtener más información acerca de la creación de historias basadas en datos en los proyectos de cuadro de resultados móviles en Analysis Workspace.

>[!VIDEO](https://video.tv.adobe.com/v/3416392/?quality=12&learn=on)

**Para crear una historia basada en datos** {#data-story-create}

Cree su historia basada en datos al agregar varias diapositivas de detalles a un mosaico.

1. Comience con un proyecto de cuadro de resultados móvil.
1. Seleccione un mosaico desde el que desee crear una historia.
   ![Creación de una historia basada en datos](assets/data-story1.png)
   ![Creación de iconos de historia basada en datos](assets/create-data-story.png){width=".50%"}
1. Agregue diapositivas para generar la historia basada en datos. La primera diapositiva se genera de forma predeterminada.
Para agregar nuevas diapositivas, pase el ratón sobre una o haga clic en ella y, a continuación, seleccione una de las opciones disponibles:
   * Pulse el signo + para crear una nueva diapositiva.
   * Pulse el icono de duplicado para duplicar la diapositiva existente.
1. Si crea una diapositiva en blanco, arrastre y suelte los componentes desde el carril izquierdo o elija un diseño para llenarla automáticamente con los datos del mosaico.
   ![Creación de una historia basada en datos](assets/data-story2.png)
Para eliminar una diapositiva, pulse el icono de papelera.

### Personalización de una historia basada en datos {#customize-data-story}

Las historias basadas en datos le permiten personalizar todos los elementos para que pueda compartir la información que desee y excluir lo que no necesite. Puede personalizar mosaicos y diapositivas individuales para agregar filtros, mostrar desgloses, cambiar el diseño y modificar las visualizaciones.

**Para personalizar mosaicos**

1. Toque un mosaico. El mosaico seleccionado se resalta en azul y el panel derecho muestra las propiedades.
1. Cambie el título, el tipo de gráfico y otras opciones del mosaico.
1. Arrastre un componente al mosaico.
   ![Creación de una historia basada en datos](assets/data-story3.png)
Cuando arrastra y suelta un componente como una visualización en un mosaico, este se aplica a todas las diapositivas de historias basada en datos.
1. Para aplicar un cambio solo al título, mantenga pulsada la tecla Mayús.
   ![Creación de una historia basada en datos](assets/data-story4.png)

>[!NOTE]
>Las diapositivas heredan los componentes del mosaico, pero los mosaicos no heredan los componentes de las diapositivas.

**Para personalizar las diapositivas individuales**

Puede cambiar la visualización de diapositivas individuales en una historia basada en datos. Por ejemplo, puede cambiar una barra horizontal por un gráfico de anillos para una diapositiva específica. También puede cambiar el diseño. Consulte [los detalles de personalización de diapositivas](#customize-detail-slide).

### Vista previa de una historia basada en datos {#preview-data-story}

Después de crear una historia basada en datos, use el botón **Vista previa** para verla e interactuar con ella como si fuera un usuario de la aplicación. Para obtener información acerca de la vista previa de la historia basada en datos, consulte [Vista previa del cuadro de resultados](#preview)

### Navegación entre mosaicos y diapositivas {#navigate-tiles-slides}

La barra de navegación muestra iconos que representan lo que hay en cada diapositiva. Si hay muchas, la barra de navegación facilita el desplazamiento a una diapositiva específica.

Para moverse entre los mosaicos y las diapositivas, pulse la barra de navegación.
![Creación de una historia de datos](assets/data-story5.png)
![Creación de una historia de datos](assets/data-story-nav.png){width="45%"}

También puede navegar hacia atrás y hacia adelante utilizando las flechas del teclado o seleccionando un componente y manteniéndolo a la izquierda o a la derecha de la pantalla para desplazarse.

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

Para asignar un nombre al cuadro de mandos, haga clic en el área de nombres de la parte superior izquierda de la pantalla y escriba el nuevo nombre.

![Naming_Scorecards](assets/new_name.png)

## Compartir cuadros de resultados {#share}

Para compartir el informe de valoración con un usuario ejecutivo:

1. Haga clic en el menú **[!UICONTROL Compartir]** y seleccione **[!UICONTROL Compartir informe de valoración]**.

1. En el **[!UICONTROL Compartir informe de valoración móvil]** , rellene los campos de la siguiente manera:

   * Proporción del nombre del cuadro de resultados
   * Proporción de la descripción del cuadro de resultados
   * Añada las etiquetas relevantes
   * Especificación de los destinatarios del cuadro de resultados

1. Haga clic en **[!UICONTROL Compartir]**.

![Share_Scorecards](assets/new_share.png)

Una vez que haya compartido un cuadro de resultados, los destinatarios podrán acceder a él en sus paneles de Analytics. Si realiza cambios posteriores en el cuadro de resultados mediante el Generador de cuadros de resultados, estos se actualizarán automáticamente en el cuadro de resultados compartido. Los usuarios ejecutivos verán los cambios después de actualizar el cuadro de resultados en su aplicación.

Si actualiza el cuadro de resultados con nuevos componentes, es posible que desee volver a compartirlo (marque la opción **[!UICONTROL Compartir componentes incrustados]**) para asegurarse de que los usuarios ejecutivos tengan acceso a estos cambios.

### Compartir informes de valoración mediante un vínculo que se puede compartir

El uso de un vínculo que se puede compartir facilita el uso de un cuadro de resultados en una aplicación de correo electrónico, documento o mensaje de texto. El vínculo que se puede compartir permite a los destinatarios abrir el cuadro de resultados en su escritorio o en la aplicación móvil de los paneles. La vinculación profunda compartible facilita aún más el uso compartido de proyectos y la participación con las partes interesadas.

Para compartir un cuadro de resultados mediante un vínculo que se puede compartir

1. Haga clic en el menú **[!UICONTROL Compartir]** y seleccione **[!UICONTROL Compartir informe de valoración]**.

   ![Share_Scorecards](assets/share-scorecard.png)

1. Copie el vínculo y péguelo en un correo electrónico, documento o aplicación de mensajería instantánea.

   Cuando un destinatario utiliza una aplicación de escritorio o un explorador para abrir el vínculo, el proyecto de cuadro de resultados móvil se abrirá en Workspace.

   Cuando un destinatario abre el vínculo en un dispositivo móvil, el cuadro de resultados se abre directamente en la aplicación de paneles de Analytics.

   Si un destinatario no ha descargado la aplicación móvil, se le redirigirá a la lista de aplicaciones de la tienda de App Store o Google Play donde pueda descargarla.

