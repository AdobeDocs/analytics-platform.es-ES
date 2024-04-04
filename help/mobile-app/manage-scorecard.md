---
description: Visualización y administración de los cuadros de resultados de los paneles de Analytics
title: Administrar cuadros de resultados
feature: Analytics Dashboards
role: User, Admin
solution: Customer Journey Analytics
source-git-commit: c5f4ddd2f0a2840e7c0d456475f95d891863666e
workflow-type: tm+mt
source-wordcount: '1648'
ht-degree: 72%

---


# Administrar cuadros de resultados

En este tema se enseña a los depuradores de datos de Customer Journey Analytics cómo ver y administrar elementos del cuadro de resultados.

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

**Para crear una historia de datos** {#data-story-create}

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

Puede obtener una vista previa del aspecto y el funcionamiento del cuadro de resultados una vez que se publique en la aplicación de paneles de Adobe Analytics.

1. Haga clic en **[!UICONTROL Vista previa]** en la esquina superior derecha de la pantalla.

   ![Preview_scorecards](assets/preview.png)

1. Para ver el aspecto que tendrá el cuadro de resultados en distintos dispositivos, seleccione un dispositivo del menú desplegable [!UICONTROL Vista previa del dispositivo].

   ![Device_preview](assets/device-preview.png)

1. Para interactuar con la vista previa, puede hacer lo siguiente:

   * Haga clic con el botón izquierdo para simular los toques en la pantalla del teléfono.

   * Utilice la función de desplazamiento del equipo para simular el desplazamiento por la pantalla del teléfono con el dedo.

   * Haga clic y mantenga presionado para simular el efecto del dedo en la pantalla del teléfono. Esto resulta útil para interactuar con las visualizaciones en la vista detallada.

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

   Cuando un destinatario abre el vínculo en un dispositivo móvil, el cuadro de resultados se abre directamente en la aplicación de paneles de Adobe Analytics.

   Si un destinatario no ha descargado la aplicación móvil, se le redirigirá a la lista de aplicaciones de la tienda de App Store o Google Play donde pueda descargarla.


## Eliminar elemento de dimensión [!UICONTROL no especificado] {#remove-dims}

Si desea quitar elementos de dimensión [!UICONTROL No especificados] de los datos, haga lo siguiente:

1. Seleccione el mosaico correcto.
1. En el carril derecho, debajo de **[!UICONTROL Profundizar en]**, seleccione la flecha derecha junto al elemento de dimensión cuyos elementos **[!UICONTROL No especificados]** desea eliminar.

   ![Propiedades con una flecha que señala a la flecha derecha junto al nombre de la dimensión.](assets/unspecified.png)

1. Haga clic en el icono situado junto a **[!UICONTROL No especificado]** para eliminar los datos no especificados de los informes. También puede eliminar cualquier otro elemento de dimensión.

## Ver subtítulos inteligentes en cuadros de resultados

Los subtítulos inteligentes pueden ayudar a los no analistas a dar mejor sentido a sus datos sin la ayuda de los analistas. Los subtítulos inteligentes utilizan aprendizaje automático avanzado e IA generativa para proporcionar información valiosa en lenguaje natural para las visualizaciones.

Para ver subtítulos inteligentes:

1. Haga clic en un mosaico.

1. more