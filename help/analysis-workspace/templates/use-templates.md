---
description: Información general sobre el uso de plantillas predeterminadas en Analysis Workspace.
title: Uso de plantillas
feature: Workspace Basics
role: User, Admin
exl-id: d61f215d-9089-4014-9c5a-97f5d7134f34
source-git-commit: 49e0327b2c67ed12fa316f74f6d6a8ce39e3c87a
workflow-type: tm+mt
source-wordcount: '19829'
ht-degree: 99%

---

# Uso de plantillas

Las plantillas (o plantillas de la compañía) de Analysis Workspace proporcionan información rápida de los escenarios más habituales de creación de informes.  A continuación, se muestran algunos ejemplos de preguntas a las que se puede responder con las plantillas:

* La cantidad de personas que visitan el sitio
* La cantidad de los visitantes únicos (se cuentan solo una vez)
* La forma en la que llegaron al sitio (si siguieron un vínculo o llegaron directamente)
* Las palabras clave utilizadas por los visitantes para buscar el contenido del sitio
* El tiempo que los visitantes permanecieron en una página determinada o en todo el sitio
* Los vínculos en los que hicieron clic los visitantes y en qué momento salieron del sitio
* Los canales de marketing que son más eficaces para generar ingresos o eventos de conversión
* Cuánto tiempo emplearon en ver un vídeo
* Qué exploradores y dispositivos utilizaron para visitar el sitio

En la siguiente información se describe cómo acceder a las plantillas y utilizarlas en la pestaña [!UICONTROL Plantillas] en Analysis Workspace.

## Acceso y ejecución de una plantilla

1. En Analysis Workspace, seleccione la pestaña [!UICONTROL **Espacio de trabajo**].

   ![Pestañas de plantillas](assets/view-prebuilt-templates-full.png)

1. En la sección [!UICONTROL **Plantillas**], seleccione cualquiera de las siguientes pestañas:

   * **[!UICONTROL Plantillas de Adobe]**: muestra todas las plantillas proporcionadas por Adobe.

   * **[!UICONTROL _nombre_compañía_inicio_sesión _plantillas]**: muestra todas las plantillas de la compañía que se han creado para su organización. 

     Los administradores son los únicos que pueden crear plantillas de la compañía. Para obtener información sobre cómo crear una plantilla de la compañía, consulte [Creación y administración de plantillas](/help/analysis-workspace/templates/create-templates.md).

1. Utilice cualquiera de las siguientes opciones para cambiar el formato de visualización de las plantillas disponibles:

   * Elija si desea ver las plantillas en una vista de columna o de tarjeta seleccionando la vista de la columna ![ViewColumn](/help/assets/icons/ViewColumn.svg) o el icono ![Tarjeta](/help/assets/icons/Card.svg) de la vista de tarjeta.

   * Al usar la vista de tarjeta ![Tarjeta](/help/assets/icons/Card.svg), elija entre los siguientes órdenes de clasificación: **[!UICONTROL Usado más recientemente]**, **[!UICONTROL El más popular]**, **[!UICONTROL Alfabético]**, **[!UICONTROL Categórico]**.

1. En el campo de búsqueda, empiece a escribir el nombre de la plantilla que desea buscar y, a continuación, selecciónela en la lista de plantillas. 

   O bien

   Seleccione la categoría de la plantilla que desea ver y, a continuación, seleccione la plantilla en la lista de plantillas.

   >[!TIP]
   >
   >Para desplazarse por el menú con las teclas de dirección, presione la tecla de barra diagonal (/) y, a continuación, presione la tecla de flecha hacia abajo.  Pulse Entrar para cargar la plantilla seleccionada.

   Para obtener una lista de las plantillas disponibles, consulte la sección [Plantillas disponibles](#available-templates) más abajo.

1. (Opcional) Puede ver las plantillas que contienen componentes que no están disponibles en la vista de datos. (De forma predeterminada, las plantillas solo se muestran si utilizan componentes disponibles en la vista de datos).

   >[!NOTE]
   >
   >Para poder utilizar estas plantillas, un administrador debe añadir primero a la vista de datos las etiquetas de contexto necesarias de estos componentes que faltan. Para obtener más información, consulte [Añadir componentes que faltan a la vista de datos para una plantilla determinada](/help/analysis-workspace/templates/create-templates.md#add-missing-components-to-the-data-view-for-a-given-template) en el artículo [Uso de plantillas](/help/analysis-workspace/templates/create-templates.md).
   >
   >Para obtener más información sobre las etiquetas de contexto, consulte [Configuración de componentes](/help/data-views/component-settings/overview.md).

   1. Seleccione el icono del segmento.

   1. Seleccione **[!UICONTROL No está listo para su uso]** para mostrar las plantillas que requieren componentes adicionales.

      ![Usar una plantilla a la que le faltan componentes](assets/template-not-ready.png)

1. Seleccione la plantilla para crear un informe basado en la plantilla elegida.

1. (Condicional) Si la plantilla contiene componentes que no están disponibles en la vista de datos, se muestra el cuadro de diálogo Vista de datos incompatible, que indica que la vista de datos es incompatible con la plantilla y muestra qué componentes faltan.

   Realice cualquiera de los siguientes pasos:

   * Elija otra vista de datos en el menú desplegable **[!UICONTROL Cambiar vista de datos]**.

   * Seleccione **[!UICONTROL Continuar igualmente]** para ver la plantilla con los componentes que faltan.

## Creación de un proyecto basado en una plantilla {#use-reports}

Puede que una plantilla no se ajuste exactamente a sus necesidades, pero puede acercarle. En estos casos, puede utilizar la plantilla como punto de partida para el proyecto y, a continuación, personalizarla para adaptarla mejor a sus fines específicos.

Si sale de una plantilla después de realizar cambios, se le solicitará que guarde o descarte los cambios. Al guardar los cambios en una plantilla, se guardará la plantilla como un proyecto nuevo. 

Para personalizar una plantilla y guardarla como un proyecto:

1. En Customer Journey Analytics, seleccione la pestaña [!UICONTROL **Workspace**].

1. Seleccione la pestaña [!UICONTROL **Plantillas**].

1. Seleccione la plantilla que desea ver.  Por ejemplo, en [!UICONTROL **El más popular**], seleccione la plantilla [!UICONTROL **Páginas**].

   La plantilla Páginas, tal como se muestra en Analysis Workspace, muestra dos [visualizaciones](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ([Gráfico de barras](/help/analysis-workspace/visualizations/bar.md) y [Número de resumen](/help/analysis-workspace/visualizations/summary-number-change.md)) y una [Tabla de forma libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md). La métrica utilizada es Ocurrencias.

   <!--update screenshot. The following is AA -->

   ![Plantilla de páginas](assets/pages-report.png)

1. Realice una de las siguientes acciones:

   * Vea la plantilla.
   * Puede arrastrar uno o más segmentos a la zona de colocación de Segmento en la parte superior. Por ejemplo, arrastre el segmento [!UICONTROL **Clientes móviles**] y vea los resultados.
   * Para cambiar el intervalo de fecha, vaya al calendario en la parte superior derecha.
   * Añada desgloses de dimensión, arrastre otras métricas y, por lo general, personalice la plantilla según sus necesidades.

1. (Opcional) Guarde la plantilla como un proyecto seleccionando [!UICONTROL **Proyecto**] > [!UICONTROL **Guardar**].

   La plantilla se guarda como un proyecto nuevo, pero no se modifica la plantilla existente.  Para obtener más información sobre cómo guardar proyectos, consulte [Guardar proyectos](/help/analysis-workspace/build-workspace-project/save-projects.md).

## Plantillas disponibles

Para acceder a todas las plantillas creadas previamente que están disponibles:

1. En Adobe Analytics, seleccione la pestaña [!UICONTROL **Workspace**] y, a continuación, seleccione la pestaña [!UICONTROL **Plantillas**]

   Las plantillas creadas previamente se organizan por categoría.

   <!--add screenshot-->

1. Seleccione una categoría para ver las plantillas que contiene.

   Las siguientes secciones corresponden a las categorías disponibles y proporcionan información sobre cada plantilla.

   * **[[!UICONTROL El más popular]](#most-popular)**

   * **[[!UICONTROL Web]** > **[!UICONTROL Participación]](#engagement)**

   * **[[!UICONTROL Web]** > **[!UICONTROL Conversión]](#web-conversion)**

   * **[[!UICONTROL Web]** > **[!UICONTROL Audiencia]](#web-audience)**

   * **[[!UICONTROL Web]** > **[!UICONTROL Adquisición]](#web-acquisition)**

   * **[[!UICONTROL Móvil]** > **[!UICONTROL Aplicación móvil]](#mobile-mobile-app)**

   * **[[!UICONTROL Móvil]** > **[!UICONTROL Información de dispositivo móvil]](#mobile-mobile-device-information)**

   * **[[!UICONTROL Partición de tiempo]](#time-parting)**

   * **[[!UICONTROL Canal cruzado]](#cross-channel)**

   * **[[!UICONTROL Otros canales]](#other-channels)**

   * **[[!UICONTROL AJO]](#ajo)**

### Más popular {#most-popular}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--unitsOvertimeReport"
>title="Ver el número total de unidades compradas dentro de todos los pedidos. Los datos se muestran a lo largo de un período de tiempo y se comparan con los períodos anteriores."
>abstract="**Esto puede ayudarle** a comprender mejor cómo los ingresos aumentan o disminuyen con el tiempo. Puede aplicar un segmento para conocer qué clientes o regiones geográficas compran más unidades y cómo evolucionan las ventas de esas unidades a lo largo del tiempo.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar la eficacia de una campaña de marketing lanzada recientemente comparando ventas de unidades antes y después del lanzamiento de la campaña. O podría comparar las ventas de unidades año tras año durante los días festivos.<br/>Esta plantilla usa la dimensión Día y la métrica Unidades."

<!-- markdownlint-enable MD034 -->

<!--both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--training"
>title="Plantilla del tutorial de formación"
>abstract="Conozca la terminología común de Analysis Workspace y los pasos para crear su primer análisis."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--pagesRankedReport"
>title="Identificar las páginas más populares y menos populares."
>abstract="**Esto puede ayudarle** a entender mejor a su audiencia y el tipo de información que más les interesa.<br/>**En función de lo que aprenda, puede** hacer cualquier cosa, como ajustar los metadatos de la página para aumentar la visibilidad en páginas menos vistas o dedicar tiempo a mejorar el contenido de sus páginas más vistas.<br/>Esta plantilla usa la dimensión Página y la métrica Vistas de página."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--pageViewsOvertimeReport"
>title="Ver el número total de vistas de la página. Los datos se muestran a lo largo de un período de tiempo y se comparan con los períodos anteriores. "
>abstract="**Esto puede ayudarle** a comprender mejor cómo el tráfico del sitio puede aumentar o disminuir con el tiempo.<br/>**Según lo que aprenda, podría** hacer muchas cosas, como evaluar la eficacia de una campaña de marketing lanzada recientemente comparando el tráfico del sitio antes y después del lanzamiento de la campaña. O puede comparar el tráfico de los días festivos año tras año.<br/>Esta plantilla usa la dimensión Día y la métrica Vistas de página."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--visitsOvertimeReport"
>title="Ver la cantidad total de visitas. Los datos se muestran a lo largo de un período de tiempo y se comparan con los períodos anteriores."
>abstract="**Esto puede ayudarle** a comprender mejor cómo el tráfico del sitio puede aumentar o disminuir con el tiempo.<br/>**Según lo que aprenda, podría** hacer muchas cosas, como evaluar la eficacia de una campaña de marketing lanzada recientemente comparando el tráfico del sitio antes y después del lanzamiento de la campaña. O puede comparar el tráfico de los días festivos año tras año.<br/>Esta plantilla usa la dimensión Día y la métrica Visitas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--visitorsOvertimeReport"
>title="Ver la cantidad total de visitantes únicos. Los datos se muestran a lo largo de un período de tiempo y se comparan con los períodos anteriores. "
>abstract="**Esto puede ayudarle** a comprender mejor cómo el alcance y el tamaño de la audiencia del sitio aumentan o disminuyen con el tiempo o en comparación con un período anterior.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar si una campaña de marketing lanzada recientemente logró atraer a nuevas personas al sitio comparando visitantes únicos antes y después del lanzamiento de la campaña. O puede comparar la cantidad de personas que visitan el sitio durante los días festivos año tras año.<br/>Esta plantilla usa la dimensión Día y la métrica Visitantes únicos. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--keyMetricsReport"
>title="Consultar un informe que muestra en paralelo las métricas de vistas de página, visitas y visitantes únicos. Los datos se muestran a lo largo de un período de tiempo y se comparan con los períodos anteriores."
>abstract="**Esto puede ayudarle** a comparar estas métricas importantes para obtener una imagen más completa del número de personas únicas que visitan el sitio, el número de veces que se visitaron las páginas y la cantidad de sesiones.<br/>**En función de lo que aprenda, podría** hacer cualquier cosa, como evaluar el número promedio de páginas que vio cada persona al visitar el sitio en una semana o mes determinados, y cómo cambió eso durante ciertas épocas del año o antes y después de ejecutar las campañas de marketing. <br/>Esta plantilla usa la dimensión Día, la métrica Vistas de página, la métrica Visitas y la métrica Visitantes únicos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--siteSectionRankedReport"
>title="Consulte las secciones más populares o de mayor rendimiento del sitio."
>abstract="**Esto puede ayudarle** a comprender mejor qué secciones del sitio son las más visitadas.<br>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar qué productos o servicios facilitados generan el mayor interés.<br/>Esta plantilla usa la dimensión Sección del sitio y la métrica Visitas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--next-page-report"
>title="Ver los lugares más comunes a los que acceden las personas inmediatamente después o inmediatamente antes de visitar un lugar determinado."
>abstract="**Esto puede ayudarle** a comprender mejor el comportamiento del usuario después de visitar una página determinada.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar si el diseño de la página podría optimizarse para dirigir a las personas a páginas más deseables, como una página para hacer una compra o realizar un comentario.<br/>Esta plantilla usa la dimensión de Página y la métrica Eventos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--previous-page-report"
>title="Ver los lugares más comunes a los que acceden las personas inmediatamente después o inmediatamente antes de visitar un lugar determinado."
>abstract="**Esto puede ayudarle** a comprender mejor qué páginas dirigen la mayor cantidad de tráfico a una determinada página.<br/>**En función de lo que sepa, podría** hacer muchas cosas, como evaluar si las páginas que no aparecen como páginas anteriores necesitan vínculos más destacados a la página actual."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--campaignRankedReport"
>title="Ver los vínculos que generaron más tráfico en su sitio."
>abstract="**Esto puede ayudarle** a comprender mejor qué códigos de seguimiento (y los vínculos con los que están asociados) se utilizaron para obtener acceso al sitio.<br/>**Según lo que aprenda, podría** hacer muchas cosas, como ajustar su estrategia para agregar vínculos a su sitio.<br/>Esta plantilla usa la dimensión Código de seguimiento y la métrica Visitas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--productsRankedReport"
>title="Ver el número de pedidos por producto. Los datos se muestran durante un período de tiempo."
>abstract="**Esto puede ayudarle** a comprender qué productos tienen la demanda más alta o más baja.<br/>**Según lo que aprenda, podría** hacer muchas cosas, como ajustar sus estrategias de marketing para promocionar productos de alto rendimiento o para mejorar o dejar de utilizar productos de bajo rendimiento. También puede ajustar el inventario de productos en función de su análisis de datos.<br/>Esta plantilla usa la dimensión Producto y la métrica Pedidos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--lastTouchChannelRankedReport"
>title="Consulte los canales de marketing más recientes con los que coinciden los visitantes durante su período de participación (de forma predeterminada, cada 30 días)."
>abstract="**Esto puede ayudarle** a comprender qué canales de marketing fueron los más eficaces para atraer a usuarios a un sitio y generar así conversiones.<br/>**Según lo que aprenda, podría** hacer muchas cosas, como asignar más recursos a canales de alto rendimiento o menos a los de bajo rendimiento.<br/>Esta plantilla usa la dimensión Canal de último contacto y la métrica Visitantes únicos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--lastTouchChannelDetailRankedReport"
>title="Consulte los detalles sobre los canales de marketing más recientes con los que coinciden los visitantes durante período de participación (de forma predeterminada, cada 30 días)."
>abstract="**Esto puede ayudarle** a comprender no solo qué canales de marketing fueron los más eficaces para atraer a usuarios a un sitio con conversiones, sino también los detalles sobre esos canales de marketing. Por ejemplo: si un visitante llegó a su sitio y coincidió con el canal de marketing de “Búsqueda de pago”, puede utilizar el detalle de canal para ver qué motor de búsqueda se utilizó o qué palabra clave buscó.<br/>**Según lo que aprenda, podría** hacer muchas cosas, como asignar más recursos a canales de alto rendimiento o asignar menos recursos a canales de bajo rendimiento.<br/>Esta plantilla usa la dimensión Detalle del canal de último contacto y la métrica Visitantes únicos. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--revenueOvertimeReport"
>title="Vea el importe monetario de los productos comprados dentro de todos los pedidos. Los datos se muestran a lo largo de un período de tiempo y se comparan con los períodos anteriores."
>abstract="**Esto puede ayudarle** a comprender cómo los ingresos aumentan o disminuyen con el tiempo. Puede combinar esta métrica con cualquier dimensión para ver qué elementos de la dimensión contribuyeron a los ingresos. <br/>**Según lo que aprenda, podría** hacer muchas cosas, como generar ingresos futuros basados en tendencias anteriores. También puede agregar otra dimensión, como la dimensión Código de seguimiento, para conocer qué campañas generan la mayor cantidad de ingresos.<br/>Esta plantilla usa la dimensión Día y la métrica Ingresos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--ordersOvertimeReport"
>title="Ver el número total de eventos de compra. Los datos se muestran a lo largo de un período de tiempo y se comparan con los períodos anteriores."
>abstract="**Esto puede ayudarle** a comprender mejor cómo el interés en sus productos y servicios aumenta o disminuye con el tiempo. Puede aplicar un segmento para conocer qué clientes o regiones geográficas realizan la mayor cantidad de pedidos y cómo son las tendencias de dichos pedidos a lo largo del tiempo.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar la eficacia de una campaña de marketing lanzada recientemente comparando pedidos antes y después del lanzamiento de la campaña. O puede comparar los pedidos de los días festivos año tras año.<br/>Esta plantilla usa la dimensión Día y la métrica Pedidos."

<!-- markdownlint-enable MD034 -->

Las plantillas disponibles son las siguientes:

| Nombre de plantilla | Por qué utilizar esta plantilla<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Tutorial de formación**] | Conozca la terminología común de Analysis Workspace y los pasos para crear su primer análisis |
| [!UICONTROL **Páginas**] | <!--duplicated in Engagement section--> Identificar las páginas más populares y menos populares. <p>**Esto puede ayudarle** a entender mejor a su audiencia y el tipo de información que más les interesa.</p><p>**En función de lo que aprenda, puede** hacer cualquier cosa, como ajustar los metadatos de la página para aumentar la visibilidad en páginas menos vistas o dedicar tiempo a mejorar el contenido de sus páginas más vistas.</p><p>Esta plantilla usa la dimensión Página y la métrica Vistas de página.</p> |
| [!UICONTROL **Vistas de páginas**] | <!--duplicated in Engagement section--> Ver el número total de vistas de la página. Los datos se muestran a lo largo de un período de tiempo y se comparan con los períodos anteriores. <p>**Esto puede ayudarle** a comprender mejor cómo el tráfico del sitio puede aumentar o disminuir con el tiempo.</p><p>**Según lo que aprenda, podría** hacer muchas cosas, como evaluar la eficacia de una campaña de marketing lanzada recientemente comparando el tráfico del sitio antes y después del lanzamiento de la campaña. O puede comparar el tráfico de los días festivos año tras año.</p><p>Esta plantilla usa la dimensión Día y la métrica Vistas de página.</p> |
| [!UICONTROL **Visitas a sitios web**] | <!--duplicated in Engagement section--> Ver la cantidad total de visitas. Los datos se muestran a lo largo de un período de tiempo y se comparan con los períodos anteriores. <p>**Esto puede ayudarle** a comprender mejor cómo el tráfico del sitio puede aumentar o disminuir con el tiempo.</p><p>**Según lo que aprenda, podría** hacer muchas cosas, como evaluar la eficacia de una campaña de marketing lanzada recientemente comparando el tráfico del sitio antes y después del lanzamiento de la campaña. O puede comparar el tráfico de los días festivos año tras año.</p><p>Esta plantilla usa la dimensión Día y la métrica Visitas.</p> |
| [!UICONTROL **Visitantes a sitios web**] | <!--duplicated in Engagement section--> Ver la cantidad total de visitantes únicos. Los datos se muestran a lo largo de un período de tiempo y se comparan con los períodos anteriores. <p>**Esto puede ayudarle** a comprender mejor cómo el alcance y el tamaño de la audiencia del sitio aumentan o disminuyen con el tiempo o en comparación con un período anterior.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar si una campaña de marketing lanzada recientemente logró atraer a nuevas personas al sitio comparando visitantes únicos antes y después del lanzamiento de la campaña. O puede comparar la cantidad de personas que visitan el sitio durante los días festivos año tras año.</p><p>Esta plantilla usa la dimensión Día y la métrica Visitantes únicos.</p> |
| [!UICONTROL **Métricas clave**] | <!--duplicated in Engagement section--> Consultar un informe que muestra en paralelo las métricas de vistas de página, visitas y visitantes únicos. Los datos se muestran a lo largo de un período de tiempo y se comparan con los períodos anteriores. <p>**Esto puede ayudarle** a comparar estas métricas importantes para obtener una imagen más completa del número de personas únicas que visitan el sitio, el número de veces que se visitaron las páginas y la cantidad de sesiones.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar el promedio de páginas que vio cada persona al visitar el sitio en una semana o mes determinados, y cómo eso cambió durante determinadas épocas del año o antes y después de que se ejecutaran las campañas de marketing. </p><p>Esta plantilla usa la dimensión Día, la métrica Vistas de página, la métrica Visitas y la métrica Visitantes únicos.</p> |
| [!UICONTROL **Secciones del sitio**] | Consulte las secciones más populares o de mayor rendimiento del sitio. <p>**Esto puede ayudarle** a comprender mejor qué secciones del sitio son las más visitadas.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar qué productos o servicios facilitados generan el mayor interés.</p> <p>Esta plantilla usa la dimensión Sección del sitio y la métrica Visitas.</p> |
| [!UICONTROL **Página siguiente**] | Ver los lugares más comunes a los que acceden las personas inmediatamente después o inmediatamente antes de visitar un lugar determinado. <p>**Esto puede ayudarle** a comprender mejor el comportamiento del usuario después de visitar una página determinada.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar si el diseño de la página podría optimizarse para dirigir a las personas a páginas más deseables, como una página para hacer una compra o realizar un comentario.</p> <p>Esta plantilla usa la dimensión Página y la métrica Eventos.</p> |
| [!UICONTROL **Página anterior**] | Ver los lugares más comunes a los que acceden las personas inmediatamente después o inmediatamente antes de visitar un lugar determinado. <p>**Esto puede ayudarle** a comprender mejor qué páginas dirigen la mayor cantidad de tráfico a una determinada página.</p><p>**En función de lo que sepa, podría** hacer muchas cosas, como evaluar si las páginas que no aparecen como páginas anteriores necesitan vínculos más destacados a la página actual.</p><p>Esta plantilla usa la dimensión Página y la métrica Eventos.</p> |
| [!UICONTROL **Código de seguimiento**] | Ver los vínculos que generaron más tráfico en su sitio. <p>**Esto puede ayudarle** a comprender mejor qué códigos de seguimiento (y los vínculos con los que están asociados) se utilizaron para obtener acceso al sitio.</p><p>**Según lo que aprenda, podría** hacer muchas cosas, como ajustar su estrategia para agregar vínculos a su sitio.</p><p>Esta plantilla usa la dimensión Código de seguimiento y la métrica Visitas.</p> |
| [!UICONTROL **Productos**] | Ver el número de pedidos por producto. Los datos se muestran durante un período de tiempo. <p>**Esto puede ayudarle** a comprender qué productos tienen la demanda más alta o más baja.</p><p>**Según lo que aprenda, podría** hacer muchas cosas, como ajustar sus estrategias de marketing para promocionar productos de alto rendimiento o para mejorar o dejar de utilizar productos de bajo rendimiento. También puede ajustar el inventario de productos en función de su análisis de datos.</p><p>Esta plantilla usa la dimensión Producto y la métrica Pedidos.</p> |
| [!UICONTROL **Canal de último contacto**] | Consulte los canales de marketing más recientes con los que coinciden los visitantes durante su período de participación (de forma predeterminada, cada 30 días).<p>**Esto puede ayudarle** a comprender qué canales de marketing fueron los más eficaces para atraer a usuarios a un sitio y generar así conversiones.</p><p>**Según lo que aprenda, podría** hacer muchas cosas, como asignar más recursos a canales de alto rendimiento o menos a los de bajo rendimiento.</p><p>Esta plantilla usa la dimensión Canal de último contacto y la métrica Visitantes únicos.</p> |
| [!UICONTROL **Detalles de canal de último contacto**] | Consulte los detalles sobre los canales de marketing más recientes con los que coinciden los visitantes durante período de participación (de forma predeterminada, cada 30 días).<p>**Esto puede ayudarle** a comprender no solo qué canales de marketing fueron los más eficaces para atraer a usuarios a un sitio con conversiones, sino también los detalles sobre esos canales de marketing. Por ejemplo: si un visitante llegó a su sitio y coincidió con el canal de marketing de “Búsqueda de pago”, puede utilizar el detalle de canal para ver qué motor de búsqueda se utilizó o qué palabra clave buscó.</p><p>**Según lo que aprenda, podría** hacer muchas cosas, como asignar más recursos a canales de alto rendimiento o asignar menos recursos a canales de bajo rendimiento.</p><p>Esta plantilla usa la dimensión Detalle del canal de último contacto y la métrica Visitantes únicos.</p> |
| [!UICONTROL **Ingresos**] | <!--duplicated in Web Conversion section-->Vea el importe monetario de los productos comprados dentro de todos los pedidos. Los datos se muestran a lo largo de un período de tiempo y se comparan con los períodos anteriores.<p>**Esto puede ayudarle** a comprender cómo los ingresos aumentan o disminuyen con el tiempo. Puede combinar esta métrica con cualquier dimensión para ver qué elementos de la dimensión contribuyeron a los ingresos. </p><p>**Según lo que aprenda, podría** hacer muchas cosas, como generar ingresos futuros basados en tendencias anteriores. También puede agregar otra dimensión, como la dimensión Código de seguimiento, para conocer qué campañas generan la mayor cantidad de ingresos.</p><p>Esta plantilla usa la dimensión Día y la métrica Ingresos.</p> |
| [!UICONTROL **Pedidos**] | <!--duplicated in Web Conversion section-->Ver el número total de eventos de compra. Los datos se muestran a lo largo de un período de tiempo y se comparan con los períodos anteriores. <p>**Esto puede ayudarle** a comprender mejor cómo el interés en sus productos y servicios aumenta o disminuye con el tiempo. Puede aplicar un segmento para conocer qué clientes o regiones geográficas realizan la mayor cantidad de pedidos y cómo son las tendencias de dichos pedidos a lo largo del tiempo.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar la eficacia de una campaña de marketing lanzada recientemente comparando pedidos antes y después del lanzamiento de la campaña. O puede comparar los pedidos de los días festivos año tras año.</p><p>Esta plantilla usa la dimensión Día y la métrica Pedidos.</p> |

### Web: participación {#web-engagement}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--real-time"
>title="Ver las dimensiones y métricas que se están recopilando actualmente en el sitio."
>abstract="**Esto puede ayudarle** a comprender mejor las tendencias en su sitio.<br/>**En función de lo que sepa, podría** hacer muchas cosas, como responder y administrar de forma activa el rendimiento del contenido y las campañas de marketing actuales."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentVisitOvertimeReport"
>title="Ver el tiempo medio que pasan los visitantes en su sitio durante cada visita. Los datos se muestran a lo largo de un período de tiempo y se comparan con los períodos anteriores."
>abstract="**Esto puede ayudarle** a comprender mejor los niveles de participación de los visitantes y cuánto tiempo pasan los visitantes en el sitio.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar si los cambios en su sitio hacen que los visitantes pasen más tiempo en él.<br/>Esta plantilla usa la dimensión Día y la métrica Tiempo empleado por visita (segundos)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timePriorRankedReport"
>title="Ver el tiempo medio que los usuarios pasan antes de un evento de éxito."
>abstract="**Esto puede ayudarle** a comprender mejor cuánto tiempo tardan los visitantes en realizar una acción deseada, como realizar una compra.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar si los cambios en el sitio mejoran la capacidad de los visitantes para llegar rápidamente a un evento de éxito.<br/>Esta plantilla usa la dimensión Tiempo antes del evento y la métrica Visitantes únicos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--falloutReport"
>title="Ver dónde abandonan o continúan las personas a través de una secuencia de páginas predefinidas."
>abstract="**Esto puede ayudarle** a comprender mejor en qué punto del recorrido del usuario abandonan las personas.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como analizar las tasas de conversión a través de procesos específicos en el sitio (como un proceso de compra o registro), o analizar las correlaciones entre los eventos del sitio. (Por ejemplo, qué porcentaje de personas que leyeron su política de privacidad fueron a comprar un producto). También puede utilizar esta plantilla para realizar comparaciones paralelas de dos segmentos diferentes en el mismo informe.<br/>Esta plantilla usa la visualización de visitas en el orden previsto."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cross-device-analysis"
>title="Ver qué dispositivos han utilizado las personas en todos los puntos del recorrido."
>abstract="**Esto puede ayudarle** a comprender mejor cuántas personas interactúan con su marca, los tipos de dispositivos que usan y cómo afecta a su experiencia el uso de múltiples dispositivos. Por ejemplo, ¿con qué frecuencia comienzan una tarea en un dispositivo móvil y luego se pasan a un ordenador de escritorio para completarla? ¿Cuáles son las rutas más comunes que los usuarios realizan de un dispositivo a otro? ¿En qué punto abandonan? ¿Dónde tienen éxito? Y así sucesivamente.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como optimizar determinadas partes del recorrido del usuario para una experiencia móvil.<br/>Esta plantilla utiliza la visualización de flujo, la visualización de visitas en el orden previsto, el análisis Cohorte, la métrica Personas y la métrica Dispositivos únicos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--web-retention"
>title="Vea quiénes son sus clientes más fieles y qué hacen en su sitio."
>abstract="**Esto puede ayudarle** a comprender mejor la cantidad de veces que la persona media visita su sitio, la frecuencia con la que las personas vuelven al sitio y la cantidad de días entre visitas de retorno.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como analizar qué contenido es el más eficaz para que las personas regresen al sitio.<br/>Esta plantilla usa la dimensión Día y la métrica Visitantes únicos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--audio-consumption-template"
>title="Ver las tendencias y las principales métricas del consumo de audio de medios en todos los dispositivos digitales."
>abstract="**Esto puede ayudarle** a comprender mejor cómo los visitantes consumen contenido de audio en su sitio.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como analizar qué contenido se consume más.<br/>Esta plantilla utiliza la métrica Visitas y la métrica Visitantes únicos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--media-recency-frequency-loyalty"
>title="Ver las tendencias y las métricas principales de consumo de medios en todos los dispositivos digitales. "
>abstract="**Esto puede ayudarle** a comprender mejor la cantidad de veces que la persona media visita su sitio, la frecuencia con la que las personas vuelven al sitio y la cantidad de días entre visitas de retorno.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como analizar qué contenido es el más eficaz para que las personas regresen al sitio.<br/>Esta plantilla usa la dimensión Día y la métrica Visitantes únicos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--reloadsRankedReport"
>title="Ver el número de veces que un elemento de dimensión estuvo presente durante una recarga. La forma más común de activar una recarga es a través de un visitante que actualiza su explorador."
>abstract="**Esto puede ayudarle** a identificar los problemas que pueden estar ocurriendo en una página determinada y que pueden hacer que un visitante tenga que volver a cargar la página. <br/>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar qué páginas tienen problemas que deben solucionarse.<br/>Esta plantilla usa la métrica Recargas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentPageRankedReport"
>title="Ver el tiempo medio que pasan los visitantes en su sitio durante cada visita. Los datos se muestran a lo largo de un período de tiempo y se comparan con los períodos anteriores."
>abstract="**Esto puede ayudarle** a comprender mejor los niveles de participación de los visitantes y cuánto tiempo pasan los visitantes en el sitio.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar si los cambios en su sitio hacen que los visitantes pasen más tiempo en él.<br/>Esta plantilla usa la dimensión Día y la métrica Tiempo empleado por visita (segundos)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--entryPageOriginalRankedReport"
>title="Ver las páginas principales a las que acceden las personas al visitar el sitio durante la vida útil de un visitante."
>abstract="**Esto puede ayudarle** a comprender mejor qué páginas dirigen la mayor cantidad de tráfico al sitio o a comprender mejor las primeras impresiones que los visitantes tienen en el sitio.<br/>**Según lo que aprenda, podría** hacer muchas cosas, como optimizar la experiencia inicial que obtienen los usuarios en el sitio o asegurarse de que las páginas que ven los usuarios por primera vez al entrar en el sitio sean acogedoras y proporcionen los vínculos necesarios a otras áreas del sitio.<br/>Esta plantilla usa la métrica Sesiones. También utiliza la visualización Barra y la visualización Tabla de forma libre."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--singlePageVisitsRankedReport"
>title="Ver el número de visitas que consistían en una sola página única."
>abstract="**Esto puede ayudarle** a comprender mejor los niveles de participación de los visitantes y cuánto tiempo pasan en el sitio.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar si los cambios en su sitio hacen que los visitantes pasen más tiempo en él.<br/>Esta plantilla utiliza la dimensión Visitas en una sola página."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--sitePerformanceOverview"
>title="Ver los datos de rendimiento del sitio de Adobe Experience Manager."
>abstract="**Esto puede ayudarle** a comprender mejor la obtención de valor de Adobe Experience Manager.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como optimizar la configuración de Experience Manager."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--formsPerformanceOverview"
>title="Ver los datos de rendimiento de Adobe Experience Manager Forms."
>abstract="**Esto puede ayudarle** a comprender mejor la obtención de valor de Adobe Experience Manager.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como optimizar la configuración de Experience Manager."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--itp-impact"
>title="Ver y analizar los efectos de la prevención inteligente del seguimiento (ITP) en la recopilación de datos y la creación de informes."
>abstract="**Esto puede ayudarle** a comprender mejor la posible pérdida de datos debido a las restricciones de cookies impuestas por ITP.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como adaptar la configuración del análisis para minimizar el impacto de ITP."

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template_time_spent"
>title="Ver el tiempo promedio que los visitantes pasan en el sitio durante cada visita, así como el tiempo promedio que los usuarios pasan antes de un evento de éxito. Los datos se muestran a lo largo de un período de tiempo y se comparan con los períodos anteriores."
>abstract="**Esto puede ayudarle** a comprender mejor los niveles de participación de los visitantes y cuánto tiempo tardan los visitantes en realizar una acción deseada, como realizar una compra.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar si los cambios en el sitio mejoran la capacidad de los visitantes para llegar rápidamente a un evento de éxito.<br/>Esta plantilla usa la dimensión Día y la métrica Tiempo empleado por visita (segundos), la dimensión Día y la métrica Tiempo empleado por visita (segundos)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--web-content-consumption"
>title="Consulta el consumo de contenido web que se consume más y resulta más atractivo para los usuarios."
>abstract="**Esto puede ayudarle** a comprender mejor a dónde van las personas al entrar por primera vez al sitio, qué secciones del sitio visitan con mayor frecuencia y qué páginas tienen más probabilidades de expulsar a personas del sitio.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar qué rutas del sitio llevan a los usuarios a las páginas más importantes y qué páginas tienen más probabilidades de sacar a los usuarios del sitio.<br/>Esta plantilla usa las métricas dimensión de Página y Vistas de página, Visitas, Visitantes únicos, Tasa de entrada, Tasa de salida, Tasa de salida hacia otro sitio y la Velocidad del contenido. También utiliza visualizaciones de flujo para las secciones de entrada, salida y principalesr."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--media-content-consumption"
>title="Consulta el consumo de contenido web que se consume más y resulta más atractivo para los usuarios."
>abstract="**Esto puede ayudarle** a comprender mejor a dónde van las personas al entrar por primera vez al sitio, qué secciones del sitio visitan con mayor frecuencia y qué páginas tienen más probabilidades de expulsar a personas del sitio.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar qué rutas del sitio llevan a los usuarios a las páginas más importantes y qué páginas tienen más probabilidades de sacar a los usuarios del sitio.<br/>Esta plantilla usa las métricas dimensión de Página y Vistas de página, Visitas, Visitantes únicos, Tasa de entrada, Tasa de salida, Tasa de salida hacia otro sitio y la Velocidad del contenido. También utiliza visualizaciones de flujo para las secciones de entrada, salida y principales; una visualización de diagrama de puntos que muestra las vistas de página de las páginas más comunes; una visualización de barra que muestra las vistas de página por el tiempo agrupado; y una visualización de línea que muestra una vista de tendencias del tiempo promedio empleado en el sitio."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--flowreport"
>title="Ver los lugares más comunes a los que van las personas inmediatamente después o inmediatamente antes de visitar un lugar determinado."
>abstract="**Esto puede ayudarle** a comprender cómo se mueve el tráfico de una página determinada a otras partes del sitio, así como las rutas que siguen los usuarios para llegar a una página determinada.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar si el diseño de la página podría optimizarse para dirigir a las personas a páginas más deseables, como una página para hacer una compra o dejar una revisión. O evalúe si es probable que la información de la página actual proporciona la dirección o las acciones que las personas buscan a medida que llegan desde páginas anteriores. O puede evaluar si las páginas que no aparecen como páginas anteriores necesitan vínculos más destacados a la página actual.<br/>Esta plantilla usa el panel Elemento siguiente o anterior."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--page-summary-report"
>title="Ver información clave sobre cualquier página de sus propiedades. Muestra vistas de página, la línea de tendencia, la visualización de flujo y mucho más."
>abstract="**Esto puede ayudarle** a comprender mejor cómo interactúan las personas con una página determinada.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como analizar el rendimiento de la página durante un período de tiempo o comprender mejor qué genera tráfico en la página.<br/>Esta plantilla usa la métrica Vistas de página. También utiliza la visualización Línea y la visualización Flujo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--entryPageRankedReport"
>title="Ver las páginas principales a las que acceden los usuarios al visitar el sitio por primera vez."
>abstract="**Esto puede ayudarle** a comprender mejor qué páginas dirigen la mayor cantidad de tráfico al sitio o a comprender mejor las primeras impresiones que los visitantes tienen en el sitio.<br/>**Según lo que aprenda, podría** hacer muchas cosas, como optimizar la experiencia inicial que obtienen los usuarios en el sitio o asegurarse de que las páginas que ven los usuarios por primera vez al entrar en el sitio sean acogedoras y proporcionen los vínculos necesarios a otras áreas del sitio.<br/>Esta plantilla usa la métrica Sesiones. También utiliza la visualización Barra y la visualización Tabla de forma libre."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--exitPageRankedReport"
>title="Vea las páginas principales a las que los usuarios acceden inmediatamente antes de abandonar el sitio."
>abstract="**Esto puede ayudarle** a comprender mejor qué páginas están alejando a la gente del sitio. <br/>**En función de lo que aprenda, podría** hacer muchas cosas, como actualizar las páginas de salida comunes para optimizar la experiencia que obtienen las personas antes de irse, o incluir contenido o vínculos para animar a las personas a que permanezcan en su sitio.<br/>Esta plantilla usa la métrica Sesiones. También utiliza la visualización Barra y la visualización Tabla de forma libre."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--productUsageOverviewReport"
>title="Vea cómo se utiliza el producto de Customer Journey Analytics en su organización."
>abstract="**Esto puede ayudarle** a comprender mejor cuántas personas utilizan Customer Journey Analytics, con qué frecuencia lo usan y las tendencias de uso a lo largo del tiempo. También puede ver el número de proyectos que se crean y los detalles sobre esos proyectos (como qué componentes, visualizaciones y paneles se utilizan más habitualmente), así como muchas otras estadísticas sobre el uso.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como eliminar proyectos o componentes que no use, o proporcionar formación al usuario para las funciones más populares."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--content-analytics"
>title="Descubra qué contenido y atributos de contenido tienen el mejor rendimiento."
>abstract="**Esto puede ayudarle** a conocer el rendimiento de su contenido a nivel granular. Puede examinar el rendimiento de recursos individuales o atributos específicos. Content Analytics utiliza la IA para generar atributos automáticamente y etiquetar el contenido con ellos. [Más información](https://experienceleague.adobe.com/es/docs/analytics-platform/using/content-analytics/content-analytics)<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como promocionar recursos de alto rendimiento en su página de inicio, personalizar contenido para segmentos específicos para incluir atributos de alto rendimiento o rotar el contenido que haya empezado a quedarse obsoleto."

<!-- markdownlint-enable MD034 -->


Las plantillas disponibles son las siguientes:

| Nombre de plantilla | Por qué utilizar esta plantilla<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Métricas clave**] | <!--duplicated in Most popular section--> Consultar un informe que muestra en paralelo las métricas de vistas de página, visitas y visitantes únicos. Los datos se muestran a lo largo de un período de tiempo y se comparan con los períodos anteriores. <p>**Esto puede ayudarle** a comparar estas métricas importantes para obtener una imagen más completa del número de personas únicas que visitan el sitio, el número de veces que se visitaron las páginas y la cantidad de sesiones.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar el promedio de páginas que vio cada persona al visitar el sitio en una semana o mes determinados, y cómo eso cambió durante determinadas épocas del año o antes y después de que se ejecutaran las campañas de marketing. </p><p>Esta plantilla usa la dimensión Día, la métrica Vistas de página, la métrica Visitas y la métrica Visitantes únicos.</p> |
| [!UICONTROL **Vistas de páginas**] | <!--duplicated in Most popular section-->Ver el número total de vistas de la página. Los datos se muestran a lo largo de un período de tiempo y se comparan con los períodos anteriores. <p>**Esto puede ayudarle** a comprender mejor cómo el tráfico del sitio puede aumentar o disminuir con el tiempo.</p><p>**Según lo que aprenda, podría** hacer muchas cosas, como evaluar la eficacia de una campaña de marketing lanzada recientemente comparando el tráfico del sitio antes y después del lanzamiento de la campaña. O puede comparar el tráfico de los días festivos año tras año.</p><p>Esta plantilla usa la dimensión Día y la métrica Vistas de página.</p> |
| [!UICONTROL **Páginas**] | <!--duplicated in Most popular section-->Identificar las páginas más populares y menos populares. <p>**Esto puede ayudarle** a entender mejor a su audiencia y el tipo de información que más les interesa.</p><p>**En función de lo que aprenda, puede** hacer cualquier cosa, como ajustar los metadatos de la página para aumentar la visibilidad en páginas menos vistas o dedicar tiempo a mejorar el contenido de sus páginas más vistas.</p><p>Esta plantilla usa la dimensión Página y la métrica Vistas de página.</p> |
| [!UICONTROL **Visitas**] | <!--duplicated in Most popular section-->Ver la cantidad total de visitas. Los datos se muestran a lo largo de un período de tiempo y se comparan con los períodos anteriores. <p>**Esto puede ayudarle** a comprender mejor cómo el tráfico del sitio puede aumentar o disminuir con el tiempo.</p><p>**Según lo que aprenda, podría** hacer muchas cosas, como evaluar la eficacia de una campaña de marketing lanzada recientemente comparando el tráfico del sitio antes y después del lanzamiento de la campaña. O puede comparar el tráfico de los días festivos año tras año.</p><p>Esta plantilla usa la dimensión Día y la métrica Visitas.</p> |
| [!UICONTROL **Visitantes**] | <!--duplicated in Most popular section-->Ver la cantidad total de visitantes únicos. Los datos se muestran a lo largo de un período de tiempo y se comparan con los períodos anteriores. <p>**Esto puede ayudarle** a comprender mejor cómo el alcance y el tamaño de la audiencia del sitio aumentan o disminuyen con el tiempo o en comparación con un período anterior.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar si una campaña de marketing lanzada recientemente logró atraer a nuevas personas al sitio comparando visitantes únicos antes y después del lanzamiento de la campaña. O puede comparar la cantidad de personas que visitan el sitio durante los días festivos año tras año.</p><p>Esta plantilla usa la dimensión Día y la métrica Visitantes únicos.</p> |
| [!UICONTROL **Tiempo empleado**] | Ver el tiempo promedio que los visitantes pasan en el sitio durante cada visita, así como el tiempo promedio que los usuarios pasan antes de un evento de éxito. Los datos se muestran a lo largo de un período de tiempo y se comparan con los períodos anteriores. <p>**Esto puede ayudarle** a comprender mejor los niveles de participación de los visitantes y cuánto tiempo tardan los visitantes en realizar una acción deseada, como realizar una compra.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar si los cambios en el sitio mejoran la capacidad de los visitantes para llegar rápidamente a un evento de éxito.</p><p>Esta plantilla usa la dimensión Día y la métrica Tiempo empleado por visita (segundos), la dimensión Día y la métrica Tiempo empleado por visita (segundos).</p> |
| [!UICONTROL **Secciones del sitio**] | <!--duplicated in Most popular section-->Consulte las secciones más populares o de mayor rendimiento del sitio. <p>**Esto puede ayudarle** a comprender mejor qué secciones del sitio son las más visitadas.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar qué productos o servicios facilitados generan el mayor interés.</p> <p>Esta plantilla usa la dimensión Sección del sitio y la métrica Visitas.</p> |
| [!UICONTROL **Consumo del contenido web**] | Consulta el consumo de contenido web que se consume más y resulta más atractivo para los usuarios.<p>**Esto puede ayudarle** a comprender mejor a dónde van las personas al entrar por primera vez al sitio, qué secciones del sitio visitan con mayor frecuencia y qué páginas tienen más probabilidades de expulsar a personas del sitio.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar qué rutas del sitio llevan a los usuarios a las páginas más importantes y qué páginas tienen más probabilidades de sacar a los usuarios del sitio.</p> <p>Esta plantilla usa la dimensión de Página y la métrica Vistas de página, la métrica Visitas, la métrica Visitantes únicos, la métrica Tasa de entrada, la métrica de Tasa de salida hacia otro sitio, la métrica Tasa de salida y la métrica Velocidad del contenido. También utiliza visualizaciones de flujo para las secciones de entrada, salida y principalesr.</p> |
| [!UICONTROL **Consumo de contenido de medios**] | Consulta el consumo de contenido web que se consume más y resulta más atractivo para los usuarios.<p>**Esto puede ayudarle** a comprender mejor a dónde van las personas al entrar por primera vez al sitio, qué secciones del sitio visitan con mayor frecuencia y qué páginas tienen más probabilidades de expulsar a personas del sitio.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar qué rutas del sitio llevan a los usuarios a las páginas más importantes y qué páginas tienen más probabilidades de alejar a los usuarios del sitio.<!-- not sure about these takeaways... --></p> <p>Esta plantilla usa la dimensión de Página y la métrica Vistas de página, la métrica Visitas, la métrica Visitantes únicos, la métrica Tasa de entrada, la métrica de Tasa de salida hacia otro sitio, la métrica Tasa de salida y la métrica Velocidad del contenido. También utiliza visualizaciones de flujo para las secciones de entrada, salida y principales; una visualización de diagrama de puntos que muestra las vistas de página de las páginas más comunes; una visualización de barra que muestra las vistas de página por el tiempo agrupado; y una visualización de línea que muestra una vista de tendencias del tiempo promedio empleado en el sitio.</p> |
| [!UICONTROL **Flujo de la página siguiente y anterior**] | Vea una visualización de los lugares más habituales a los que acceden las personas inmediatamente después o inmediatamente antes de visitar una página determinada. <p>**Esto puede ayudarle** a comprender cómo se mueve el tráfico de una página determinada a otras partes del sitio, así como las rutas que siguen los usuarios para llegar a una página determinada.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar si el diseño de la página podría optimizarse para dirigir a las personas a páginas más deseables, como una página para hacer una compra o dejar una revisión. O evalúe si es probable que la información de la página actual proporciona la dirección o las acciones que las personas buscan a medida que llegan desde páginas anteriores. O puede evaluar si las páginas que no aparecen como páginas anteriores necesitan vínculos más destacados a la página actual.</p><p>Esta plantilla usa el panel de elemento siguiente o anterior.</p> |
| **Resumen de la página** | Ver información clave sobre cualquier página de sus propiedades. Muestra vistas de página, la línea de tendencia, la visualización de flujo y mucho más.  <p>**Esto puede ayudarle** a comprender mejor cómo interactúan las personas con una página determinada.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como analizar el rendimiento de la página durante un período de tiempo o comprender mejor qué genera tráfico en la página.</p><p>Esta plantilla usa la métrica Vistas de página. También utiliza la visualización Línea y la visualización Flujo.</p> |
| **Páginas de entrada** | Ver las páginas principales a las que acceden los usuarios al visitar el sitio por primera vez. <p>**Esto puede ayudarle** a comprender mejor qué páginas dirigen la mayor cantidad de tráfico al sitio o a comprender mejor las primeras impresiones que los visitantes tienen en el sitio.</p><p>**Según lo que aprenda, podría** hacer muchas cosas, como optimizar la experiencia inicial que obtienen los usuarios en el sitio o asegurarse de que las páginas que ven los usuarios por primera vez al entrar en el sitio sean acogedoras y proporcionen los vínculos necesarios a otras áreas del sitio.</p><p>Esta plantilla usa la métrica Sesiones. También utiliza la visualización Barra y la visualización Tabla de forma libre.</p> |
| **Páginas de salida** | Vea las páginas principales a las que los usuarios acceden inmediatamente antes de abandonar el sitio.<p>**Esto puede ayudarle** a comprender mejor qué páginas están alejando a las personas del sitio.  </p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como actualizar las páginas de salida comunes para optimizar la experiencia que obtienen las personas antes de irse, o incluir contenido o vínculos para animar a las personas a que permanezcan en su sitio.</p><p>Esta plantilla usa la métrica Sesiones. También utiliza la visualización Barra y la visualización Tabla de forma libre.</p> |
| **Información general sobre el uso del producto** | Vea cómo se utiliza el producto de Customer Journey Analytics en su organización. <p>**Esto puede ayudarle** a comprender mejor cuántas personas utilizan Customer Journey Analytics, con qué frecuencia lo usan y las tendencias de uso a lo largo del tiempo. También puede ver el número de proyectos que se crean y los detalles sobre esos proyectos (como qué componentes, visualizaciones y paneles se utilizan más habitualmente), así como muchas otras estadísticas sobre el uso.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como eliminar proyectos o componentes que no use, o proporcionar formación al usuario para las funciones más populares.</p> |
| **Análisis de contenido** | Descubra qué contenido y atributos de contenido tienen el mejor rendimiento.<p>**Esto puede ayudarle** a conocer el rendimiento de su contenido a nivel granular. Puede examinar el rendimiento de recursos individuales o atributos específicos. Content Analytics utiliza la IA para generar atributos automáticamente y etiquetar el contenido con ellos. [Más información](/help/content-analytics/content-analytics.md)</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como promocionar recursos de alto rendimiento en su página de inicio, personalizar contenido para segmentos específicos para incluir atributos de alto rendimiento o rotar el contenido que haya empezado a quedar obsoleto.</p> |

### Web: conversión {#web-conversion}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--categoryRankedReport"
>title="Ver el número de visitas asociadas con cada categoría de producto en el sitio. Esto resulta útil en implementaciones que utilizan la variable de productos y desean ver métricas sobre la categoría de productos. La dimensión que cumplimenta esta plantilla puede estar intencionadamente en blanco si no tiene ningún producto en su sitio."
>abstract="**Esto puede ayudarle** a comprender mejor los productos más vendidos o más vistos. &lt;/br/>**En función de lo que aprenda, podría** hacer muchas cosas, como medir la eficacia de una campaña de marketing de un producto determinado.<br/>Esta plantilla usa la dimensión de Categoría y la métrica Visitas. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--commerce-and-marketing-management"
>title="Ver información creada previamente para los minoristas de sus actividades comerciales que le ayudarán a mejorar sus ventas. Está pensada para usuarios de Adobe Commerce, pero también es útil para cualquier minorista en línea. "
>abstract="**Esto puede ayudarle** a comprender mejor cómo sus actividades comerciales contribuyen a las cifras de ventas.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como ajustar los presupuestos a las actividades que obtienen el máximo retorno de la inversión."

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--productConversionReport"
>title="Ver la conversión del producto en una visualización de canal que muestra carros de compras, cierres de compra y pedidos. También puede ver porcentajes de conversión, promedios de ingresos, promedios unitarios y promedios de pedidos."
>abstract="**Esto puede ayudarle** a comprender mejor cómo avanzan y abandonan las personas durante el proceso de conversión.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como mejorar el sitio web para facilitar un proceso de cierre de compra más fluido."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--retail-products-template"
>title="Ver qué productos tienen el mayor rendimiento."
>abstract="**Esto puede ayudarle** a comprender mejor qué productos tienen más éxito.<br/>**Según lo que aprenda, podría** hacer muchas cosas, como aumentar los fondos para productos exitosos y disminuirlos para productos menos exitosos.<br/>Esta plantilla usa las métricas Vistas del producto, Adiciones al carro de compras, Pedidos, Ingresos y Unidades. También utiliza la dimensión Producto."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartConversionReport"
>title="Ver la cantidad de veces que las personas realizaron eventos clave de cierre de compra, como agregar artículos al carro de compras, ver el carro de compras, quitar artículos del carro de compras y cerrar la compra."
>abstract="**Esto puede ayudarle** a comprender mejor qué partes del canal del proceso de cierre de compra generan conversión y cuáles son las más propensas al abandono del carro de compras.<br/>**Según lo que aprenda, podría** hacer muchas cosas, como reducir la fricción en ciertos pasos del proceso de cierre de compra.<br/>Esta plantilla usa el"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartsOvertimeReport"
>title="Ver el número de personas que agregaron un producto al carro de compras."
>abstract="**Esto puede ayudarle** a comprender mejor el número de personas que agregan un producto al carro de compras, a diferencia del número total de productos que se agregan al carro de compras.<br/>**Según lo que aprenda, podría** hacer muchas cosas, como medir la efectividad de las páginas de productos.<br/>Esta plantilla usa la métrica Carros de compras."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartViewsOvertimeReport"
>title="Ver la cantidad de veces que las personas vieron el carro de compras."
>abstract="**Esto puede ayudarle** a comprender mejor la experiencia de cierre de compra en un esfuerzo por reducir las tasas de abandono del carro de compras o a analizar el tiempo entre adiciones al carro de compras y cierres de compras entre diferentes productos.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como ofrecer promociones de productos que permanezcan en los carros durante más tiempo y que corran el mayor riesgo de ser abandonados.<br/>Esta plantilla usa la métrica Vistas del carro de compras."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartAdditionsOvertimeReport"
>title="Ver la cantidad de veces que las personas agregaron algo al carro de compras."
>abstract="**Esto puede ayudarle** a comprender mejor la parte del canal de conversión en la que el interés del cliente en un producto es lo suficientemente alto como para agregarlo al carro de compras.<br/>**Según lo que aprenda, podría** hacer muchas cosas, como mejorar las recomendaciones de los productos para todos los clientes. Esto se puede hacer analizando qué productos se añaden con frecuencia a los mismos carros de compras y sugiriendo productos relacionados en función de los artículos que ya están en el carro de compras."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartRemovalsOvertimeReport"
>title="Ver la cantidad de veces que las personas han eliminado algo del carro de compras."
>abstract="**Esto puede ayudarle** a entender mejor la parte del canal de conversión en la que los clientes ya no están interesados en un producto o dónde pueden existir problemas en el proceso de cierre de compra.<br/>**Según lo que aprenda, podría** hacer cualquier cosa, como eliminar cualquier posible barrera que pueda existir en el proceso de cierre de compra, como una experiencia del usuario complicada.<br/>Esta plantilla usa la métrica Eliminaciones del carro de compras."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--purchaseConversionReport"
>title="Ver la conversión de compras en una visualización de canal que muestra sesiones, carros de compras y pedidos. También puede ver porcentajes de conversión, promedios de ingresos, promedios unitarios y promedios de pedidos."
>abstract="**Esto puede ayudarle** a comprender mejor cómo avanzan y abandonan las personas durante el proceso de conversión.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como mejorar el sitio web para facilitar un proceso de cierre de compra más fluido."

<!-- markdownlint-enable MD034 -->

Las plantillas disponibles son las siguientes:

| Nombre de plantilla | Por qué utilizar esta plantilla<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Canal de conversión de productos**] | Ver la conversión del producto en una visualización de canal que muestra carros de compras, cierres de compra y pedidos. También puede ver porcentajes de conversión, promedios de ingresos, promedios unitarios y promedios de pedidos.<p>**Esto puede ayudarle** a comprender mejor cómo avanzan y abandonan las personas durante el proceso de conversión.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como mejorar el sitio web para facilitar un proceso de cierre de compra más fluido.</p> |
| **Productos** | Ver qué productos están impulsando las métricas clave, como los más vendidos o los más vistos. <p>**Esto puede ayudarle** a comprender mejor qué productos tienen más éxito.</p><p>**Según lo que aprenda, podría** hacer muchas cosas, como aumentar los fondos para productos exitosos y disminuirlos para productos menos exitosos.</p><p>Esta plantilla utiliza la métrica Pedidos y la dimensión Producto. |
| **Rendimiento de los productos** | Ver qué productos tienen el mayor rendimiento.<p>**Esto puede ayudarle** a comprender mejor qué productos tienen más éxito.</p><p>**Según lo que aprenda, podría** hacer muchas cosas, como aumentar los fondos para productos exitosos y disminuirlos para productos menos exitosos.</p><p>Esta plantilla usa las métricas Vistas del producto, Adiciones al carro de compras, Pedidos, Ingresos y Unidades. También utiliza la dimensión Producto. |
| **Canales de conversión del carro de compras** | Ver la cantidad de veces que las personas realizaron eventos clave de cierre de compra, como agregar artículos al carro de compras, ver el carro de compras, quitar artículos del carro de compras y cerrar la compra. <p>**Esto puede ayudarle** a comprender mejor qué partes del canal del proceso de cierre de compra generan conversión y cuáles son las más propensas al abandono del carro de compras.</p><p>**Según lo que aprenda, podría** hacer muchas cosas, como reducir la fricción en ciertos pasos del proceso de cierre de compra.</p> |
| **Carros de compras** | Ver el número de personas que agregaron un producto al carro de compras.<p>**Esto puede ayudarle** a comprender mejor el número de personas que agregan un producto al carro de compras, a diferencia del número total de productos que se agregan al carro de compras.</p><p>**Según lo que aprenda, podría** hacer muchas cosas, como medir la efectividad de las páginas de productos.</p><p>Esta plantilla usa la métrica Carros de compras. |
| **Vistas del carro de compras** | Ver la cantidad de veces que las personas vieron el carro de compras. <p>**Esto puede ayudarle** a comprender mejor la experiencia de cierre de compra en un esfuerzo por reducir las tasas de abandono del carro de compras o a analizar el tiempo entre adiciones al carro de compras y cierres de compras entre diferentes productos.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como ofrecer promociones de productos que permanezcan en los carros durante más tiempo y que corran el mayor riesgo de ser abandonados.</p><p>Esta plantilla usa la métrica Vistas del carro de compras. |
| **Adiciones al carro de compras** | Ver la cantidad de veces que las personas agregaron algo al carro de compras. <p>**Esto puede ayudarle** a comprender mejor la parte del canal de conversión en la que el interés del cliente en un producto es lo suficientemente alto como para agregarlo al carro de compras.</p><p>**Según lo que aprenda, podría** hacer muchas cosas, como mejorar las recomendaciones de los productos para todos los clientes. Esto se puede hacer analizando qué productos se agregan con frecuencia a los mismos carros de compras y sugiriendo productos relacionados en función de los artículos que ya están en el carro de compras. |
| **Eliminaciones del carro de compras** | Ver la cantidad de veces que las personas han eliminado algo del carro de compras.<p>**Esto puede ayudarle** a entender mejor la parte del canal de conversión en la que los clientes ya no están interesados en un producto o dónde pueden existir problemas en el proceso de cierre de compra.</p><p>**Según lo que aprenda, podría** hacer cualquier cosa, como eliminar cualquier posible barrera que pueda existir en el proceso de cierre de compra, como una experiencia del usuario complicada.</p><p>Esta plantilla usa la métrica Eliminaciones del carro de compras. |
| **Canal de conversión de compra** | Ver la conversión de compras en una visualización de canal que muestra sesiones, carros de compras y pedidos. También puede ver porcentajes de conversión, promedios de ingresos, promedios unitarios y promedios de pedidos.<p>**Esto puede ayudarle** a comprender mejor cómo avanzan y abandonan las personas durante el proceso de conversión.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como mejorar el sitio web para facilitar un proceso de cierre de compra más fluido.</p> |
| **Ingresos** | <!--duplicated in Most popular section-->Ver el número monetario de productos comprados dentro de todos los pedidos.<p>**Esto puede ayudarle** a comprender mejor qué elementos de dimensión contribuyeron a los ingresos, combinando la métrica Ingresos con cualquier dimensión. Por ejemplo, podría ver las campañas principales (usando la dimensión Código de seguimiento ) que contribuyeron a los ingresos. </p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como ajustar las campañas que no cumplen los objetivos de ingresos previstos.</p><p>Esta plantilla usa la métrica Ingresos.  |
| **Pedidos** | <!--duplicated in Most popular section-->Ver el número total de eventos de compra realizados en el sitio.  <p>**Esto puede ayudarle** a comprender mejor qué elementos de dimensión contribuyeron a un pedido, combinando la métrica Pedidos con cualquier dimensión. Por ejemplo, podría ver las campañas principales (usando la dimensión Código de seguimiento) que contribuyeron a las compras.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como ajustar las campañas que no cumplen los objetivos de compra previstos. </p><p>Esta plantilla usa la métrica Pedidos. |

### Web: público {#web-audience}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--people"
>title="Ver el número de personas que están interactuando con su marca."
>abstract="**Esto puede ayudarle** a comprender mejor las tendencias de uso de su sitio.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como medir la eficacia de los recientes esfuerzos de marketing para generar nuevos visitantes para su sitio."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--bots"
>title="Ver las vistas de página y las tendencias relativas al tráfico de bots en el sitio."
>abstract="**Esto puede ayudarle** a comprender mejor la cantidad de tráfico de bots que se filtra desde la creación de informes, según las reglas de bots que haya configurado.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como continuar supervisando la actividad de los bots para poder identificar nuevos patrones."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--firstvsrepeatvisitors"
>title="Ver una comparación de los visitantes nuevos que repiten visita."
>abstract="**Esto puede ayudarle** a comprender mejor la eficacia de su sitio para conservar la lealtad de sus clientes o la velocidad a la que está adquiriendo nuevos clientes.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como ofrecer incentivos para futuras compras a los visitantes nuevos con el fin de animarlos a que regresen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--personid"
>title="Ver el comportamiento de cada usuario en varios canales."
>abstract="**Esto puede ayudarle** a comprender mejor el recorrido completo del cliente y las interacciones entre varios puntos de contacto.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como personalizar los esfuerzos de marketing para atender mejor las preferencias de los usuarios."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeZoneRankedReport"
>title="Ver las principales zonas horarias de los visitantes que acceden al sitio."
>abstract="**Esto puede ayudarle** a comprender mejor en qué zonas horarias viven sus visitantes.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como ajustar el mantenimiento del sitio en momentos en que afecte al menor número de personas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--location"
>title="Vea la información general de la ubicación de los visitantes en una visualización de mapa."
>abstract="**Esto puede ayudarle** a comprender mejor dónde se encuentran los visitantes que visitan su sitio. <br/>**En función de lo que aprenda, podría** hacer muchas cosas, como enfocar los recursos de marketing en los lugares en los que vea que hay más interés y oportunidades."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--domainRankedReport"
>title="Ver los dominios principales de los visitantes que acceden al sitio."
>abstract="**Esto puede ayudarle** a comprender mejor de qué organizaciones proceden sus visitantes.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como dirigir su contenido a los clientes más importantes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--topLevelDomainRankedReport"
>title="Ver los dominios principales de los visitantes que acceden al sitio."
>abstract="**Esto puede ayudarle** a comprender mejor de qué organizaciones proceden sus visitantes.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como dirigir su contenido a los clientes más importantes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--browserWidthRankedReport"
>title="Ver las principales anchuras de explorador que utilizan los usuarios para acceder al sitio."
>abstract="**Esto puede ayudarle** a comprender mejor cómo se muestra el contenido a los visitantes.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como mejorar la calidad del sitio probando nuevas versiones del sitio con las anchuras de explorador más comunes. De este modo se pueden maximizar los esfuerzos de control de calidad.<br/>Esta plantilla usa la dimensión Explorador."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--browserHeightRankedReport"
>title="Ver las principales alturas de explorador que usan los usuarios para acceder al sitio."
>abstract="**Esto puede ayudarle** a comprender mejor cómo se muestra el contenido a los visitantes.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como mejorar la calidad del sitio probando nuevas versiones del sitio con las alturas de explorador más comunes. De este modo se pueden maximizar los esfuerzos de control de calidad.<br/>Esta plantilla usa la dimensión Explorador. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemRankedReport"
>title="Ver el nombre de los sistemas operativos y la versión que usan los usuarios para acceder al sitio."
>abstract="**Esto puede ayudarle** a comprender mejor los sistemas operativos y las versiones más comunes que usan los visitantes.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como mejorar la calidad del sitio probando nuevas versiones del mismo con los mejores sistemas operativos y versiones. De este modo se pueden maximizar los esfuerzos de control de calidad."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemTypeRankedReport"
>title="Ver el nombre de los sistemas operativos que usan las personas para acceder al sitio."
>abstract="**Esto puede ayudarle** a comprender mejor los exploradores más comunes que usan los visitantes.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como mejorar la calidad del sitio probando nuevas versiones del sitio con los mejores sistemas operativos. De este modo se pueden maximizar los esfuerzos de control de calidad."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--returnFrequencyRankedReport"
>title="Ver la compañía de telecomunicaciones que proporciona conectividad de red celular a los dispositivos móviles que los usuarios utilizan para acceder al sitio."
>abstract="**Esto puede ayudarle** a comprender mejor qué operadores de telefonía móvil son los más populares entre su base de usuarios.<br/>**En función de lo que aprenda, podría** hacer cualquier cosa, como adaptar la entrega de contenido en función de las capacidades de red de diferentes operadores para garantizar una experiencia de usuario sin problemas.<br/>Esta plantilla usa la dimensión Operador de telefonía móvil."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--returnVisitorsOvertimeReport"
>title="Ver la compañía de telecomunicaciones que proporciona conectividad de red celular a los dispositivos móviles que los usuarios utilizan para acceder al sitio."
>abstract="**Esto puede ayudarle** a comprender mejor qué operadores de telefonía móvil son los más populares entre su base de usuarios.<br/>**En función de lo que aprenda, podría** hacer cualquier cosa, como adaptar la entrega de contenido en función de las capacidades de red de diferentes operadores para garantizar una experiencia de usuario sin problemas.<br/>Esta plantilla usa la dimensión Operador de telefonía móvil."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--visitNumberRankedReport"
>title="Ver cuántas veces ha visitado un visitante el sitio."
>abstract="**Esto puede ayudarle** a comprender mejor el grado de participación de los visitantes cuando regresan a su sitio. Esto es aplicable a la vida útil del visitante, independientemente del intervalo de fechas del proyecto.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como ajustar los esfuerzos de marketing para los visitantes frecuentes.<br/>Esta plantilla utiliza la dimensión Número de visitas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--customerLoyaltyRankedReport"
>title="Vea el número de visitantes al sitio que hayan realizado 0 compras anteriores, 1 compra anterior, 2 compras anteriores o más de 3 compras anteriores. "
>abstract="**Esto puede ayudarle** a comprender mejor cómo el sitio afecta al comportamiento de compra. <br/>**En función de lo que aprenda, podría** hacer muchas cosas, como centrarse en los visitantes que regresan para hacer una compra, para así poder fomentar un comportamiento similar para los nuevos visitantes.<br/>Esta plantilla utiliza la dimensión Lealtad del cliente."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--daysBeforeFirstPurchaseRankedReport"
>title="Vea la cantidad de días que transcurren entre la primera vez que un visitante accede al sitio y el momento en el que realizan una compra. Por ejemplo, si un visitante realiza una compra un día después de la primera visita, cualquier visita o evento posterior pertenece al elemento de dimensión Día 1."
>abstract="**Esto puede ayudarle** a comprender mejor cuánto tiempo tardan los visitantes en realizar una compra.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como actualizar el sitio para fomentar una adquisición más rápida.<br/>Esta plantilla usa la dimensión Días antes de la primera compra."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--daysSinceLastPurchaseRankedReport"
>title="Ver la cantidad de tiempo transcurrido entre la visita actual del visitante y su compra más reciente en ese momento. "
>abstract="**Esto puede ayudarle** a comprender mejor el comportamiento de los visitantes después de comprar algo en su sitio.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como actualizar el sitio para fomentar compras sucesivas.<br/>Esta plantilla usa la dimensión Días desde la última compra."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenSizeRankedReport"
>title="Ver los tamaños principales de pantalla móvil que usan los usuarios para acceder al sitio."
>abstract="**Esto puede ayudarle** a comprender mejor cómo se muestra el contenido a los visitantes.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como mejorar la calidad del sitio probando nuevas versiones del sitio con los tamaños de pantalla móvil más comunes. De este modo se pueden maximizar los esfuerzos de control de calidad."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenHeightRankedReport"
>title="Ver las principales alturas de pantalla móvil que usan los usuarios para acceder al sitio."
>abstract="**Esto puede ayudarle** a comprender mejor cómo se muestra el contenido a los visitantes.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como mejorar la calidad del sitio probando nuevas versiones del sitio con las alturas de pantalla móvil más comunes. De este modo se pueden maximizar los esfuerzos de control de calidad."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenWidthRankedReport"
>title="Ver las anchuras de pantalla móvil principales que las personas utilizan para acceder al sitio."
>abstract="**Esto puede ayudarle** a comprender mejor cómo se muestra el contenido a los visitantes.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como mejorar la calidad del sitio probando nuevas versiones del sitio con las anchuras de pantalla móvil más comunes. De este modo se pueden maximizar los esfuerzos de control de calidad."

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--countryGeoReport"
>title="Ver el país desde el que las personas visitaron el sitio."
>abstract="**Esto puede ayudarle** a comprender mejor de qué países provienen los visitantes más populares del sitio.<br/>**En función de lo que aprenda, podría** hacer cualquier cosa, como usar los datos para centrarse en las actividades de marketing en estos países o asegurarse de que la experiencia del sitio sea óptima en países que tienen diferentes idiomas principales.<br/>Esta plantilla usa la dimensión Países."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--stateGeoReport"
>title="Ver el estado (en los Estados Unidos) desde el que se originaron las personas que visitaron el sitio. Es similar a la dimensión Regiones geográficas, pero esta dimensión es específica de los Estados Unidos. "
>abstract="**Esto puede ayudarle** a comprender mejor los estados de los EE. UU. más populares de los que proceden los visitantes que visitan el sitio.<br/>**En función de lo que aprenda, podría** hacer cualquier cosa, como usar los datos para centrarse en los esfuerzos de marketing en estos estados.<br/>Esta plantilla utiliza la dimensión de los EE. UU."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--regionGeoReport"
>title="Ver la región geográfica desde la que las personas visitaron el sitio. Una región es una zona geográfica más pequeña que un país, pero más grande que una ciudad. En algunos países, una región es un estado, una provincia o una prefectura. En otras zonas, se trata de un país constituyente, departamento o región metropolitana.  "
>abstract="**Esto puede ayudarle** a entender mejor las regiones más populares de las que proceden los visitantes que visitan el sitio.<br/>**En función de lo que aprenda, podría** hacer cualquier cosa, como usar los datos para centrarse en los esfuerzos de marketing en estas regiones o asegurarse de que la experiencia del sitio sea óptima en regiones que tienen diferentes idiomas principales. <br/>Esta plantilla usa las dimensiones de ID (variables/país geográfico) y Regiones. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cityGeoReport"
>title="Ver la ciudad desde la que proceden las personas que visitaron el sitio."
>abstract="**Esto puede ayudarle** a entender mejor las ciudades más populares de las que proceden los visitantes que visitan el sitio.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como usar los datos para centrarse en los esfuerzos de marketing en estas ciudades. <br/>Esta plantilla usa la dimensión Ciudades"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--dmaGeoReport"
>title="Ver las áreas de marketing designadas (DMA) dentro de los Estados Unidos desde las que proceden las personas que visitaron el sitio."
>abstract="**Esto puede ayudarle** a entender mejor las regiones más populares de las que proceden los visitantes que visitan el sitio.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como usar los datos para centrarse en los esfuerzos de marketing en las regiones de mayor éxito. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--languageRankedReport"
>title="Ver los idiomas principales en los que los visitantes prefieren ver el contenido. "
>abstract="**Esto puede ayudarle** a comprender mejor los idiomas que los visitantes prefieren con más frecuencia.<br/>**En función de lo que aprenda, puede** hacer muchas cosas, como enfocar los esfuerzos de localización o de marketing en los idiomas más populares.<br/>Esta plantilla usa la dimensión Idioma."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--web-technology-template"
>title="Ver información relacionada con la tecnología que usan los usuarios para acceder al sitio, como los sistemas operativos, los exploradores y los dispositivos."
>abstract="**Esto puede ayudarle** a comprender mejor qué tecnologías se utilizan con más frecuencia para acceder al sitio.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como optimizar el sitio para las tecnologías que se usan."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--browserRankedReport"
>title="Ver el nombre y la versión de los exploradores principales que usan los visitantes para acceder al sitio."
>abstract="**Esto puede ayudarle** a comprender mejor los exploradores más comunes que usan los visitantes.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como mejorar la calidad del sitio probando nuevas versiones del sitio con los exploradores principales. De este modo se pueden maximizar los esfuerzos de control de calidad.<br/>Esta plantilla usa la dimensión Explorador."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--browserTypeRankedReport"
>title="Ver los nombres de las organizaciones que crearon los exploradores principales que los usuarios utilizaron para acceder al sitio. Esto se diferencia de la plantilla Explorador en que no enumera diferentes versiones del mismo explorador como elementos de dimensión separados."
>abstract="**Esto puede ayudarle** a comprender mejor los exploradores más comunes que usan los visitantes <br/>**Según lo que aprenda, puede** hacer muchas cosas, como mejorar la calidad del sitio probando nuevas versiones del sitio usando los exploradores principales. Al hacerlo, se pueden maximizar los esfuerzos de control de calidad. <br/>Esta plantilla utiliza la dimensión tipo de navegador. "

<!-- markdownlint-enable MD034 -->

Las plantillas disponibles son las siguientes:

| Nombre de plantilla | Por qué utilizar esta plantilla<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Visitantes por primera vez frente a visitantes recurrentes**] | Ver una comparación de los visitantes nuevos que repiten visita. <p>**Esto puede ayudarle** a comprender mejor la eficacia de su sitio para conservar la lealtad de sus clientes o la velocidad a la que está adquiriendo nuevos clientes.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como ofrecer incentivos para futuras compras a los visitantes nuevos con el fin de animarlos a que regresen.</p><!-- This template uses the --> |
| **ID de la persona** | Ver el comportamiento de cada usuario en varios canales.<p>**Esto puede ayudarle** a comprender mejor el recorrido completo del cliente y las interacciones entre varios puntos de contacto.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como personalizar los esfuerzos de marketing para atender mejor las preferencias de los usuarios.</p><!-- This template uses the --> |
| **Países geográficos** | Ver el país desde el que las personas visitaron el sitio.<p>**Esto puede ayudarle** a comprender mejor de qué países provienen los visitantes más populares del sitio.</p><p>**En función de lo que aprenda, podría** hacer cualquier cosa, como usar los datos para centrarse en las actividades de marketing en estos países o asegurarse de que la experiencia del sitio sea óptima en países que tienen diferentes idiomas principales.</p><p>Esta plantilla usa la dimensión Países. </p> |
| **Estados geográficos de EE. UU.** | Ver el estado (en los Estados Unidos) desde el que se originaron las personas que visitaron el sitio. Es similar a la dimensión Regiones geográficas, pero esta dimensión es específica de los Estados Unidos. <p>**Esto puede ayudarle** a comprender mejor los estados de los EE. UU. más populares de los que proceden los visitantes que visitan el sitio.</p><p>**En función de lo que aprenda, podría** hacer cualquier cosa, como usar los datos para centrarse en los esfuerzos de marketing en estos estados.</p><p>Esta plantilla utiliza la dimensión de los EE. UU. </p> |
| **Regiones geográficas** | Ver la región geográfica desde la que las personas visitaron el sitio. Una región es una zona geográfica más pequeña que un país, pero más grande que una ciudad. En algunos países, una región es un estado, una provincia o una prefectura. En otras zonas, se trata de un país constituyente, departamento o región metropolitana.  <p>**Esto puede ayudarle** a entender mejor las regiones más populares de las que proceden los visitantes que visitan el sitio.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como usar los datos para centrarse en los esfuerzos de marketing en estas regiones o asegurarse de que la experiencia del sitio sea óptima en regiones que tienen diferentes idiomas principales.  </p><p>Esta plantilla usa las dimensiones de ID (variables/país geográfico) y Regiones. </p> |
| **Ciudades geográficas** | Ver la ciudad desde la que proceden las personas que visitaron el sitio. <p>**Esto puede ayudarle** a entender mejor las ciudades más populares de las que proceden los visitantes que visitan el sitio.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como usar los datos para centrarse en los esfuerzos de marketing en estas ciudades.  </p><p>Esta plantilla usa la dimensión Ciudades </p> |
| **DMA geográficas en EE. UU.** | Ver las áreas de marketing designadas (DMA) dentro de los Estados Unidos desde las que proceden las personas que visitaron el sitio.<p>**Esto puede ayudarle** a entender mejor las regiones más populares de las que proceden los visitantes que visitan el sitio.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como usar los datos para centrarse en los esfuerzos de marketing en las regiones de mayor éxito. </p><!-- This template uses the --> |
| **Idiomas** | Ver los idiomas principales en los que los visitantes prefieren ver el contenido.  <p>**Esto puede ayudarle** a comprender mejor los idiomas que los visitantes prefieren con más frecuencia.</p><p>**En función de lo que aprenda, puede** hacer muchas cosas, como enfocar los esfuerzos de localización o de marketing en los idiomas más populares.</p><p>Esta plantilla usa la dimensión Idioma.</p> |
| **Información general sobre la tecnología** | Ver información relacionada con la tecnología que usan los usuarios para acceder al sitio, como los sistemas operativos, los exploradores y los dispositivos. <p>**Esto puede ayudarle** a comprender mejor qué tecnologías se utilizan con más frecuencia para acceder al sitio.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como optimizar el sitio para las tecnologías que se usan.</p> |
| **Exploradores** | Ver el nombre y la versión de los exploradores principales que usan los visitantes para acceder al sitio.<p>**Esto puede ayudarle** a comprender mejor los exploradores más comunes que usan los visitantes.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como mejorar la calidad del sitio probando nuevas versiones del sitio con los exploradores principales. De este modo se pueden maximizar los esfuerzos de control de calidad.</p><p>Esta plantilla usa la dimensión Explorador. </p> |
| **Tipos de explorador** | Ver los nombres de las organizaciones que crearon los exploradores principales que los usuarios utilizaron para acceder al sitio. Esto se diferencia de la plantilla Explorador en que no enumera diferentes versiones del mismo explorador como elementos de dimensión separados.<p>**Esto puede ayudarle** a comprender mejor los exploradores más comunes que usan los visitantes.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como mejorar la calidad del sitio probando nuevas versiones del sitio con los exploradores principales. De este modo se pueden maximizar los esfuerzos de control de calidad. </p><p>Esta plantilla utiliza la dimensión de tipo de explorador. </p> |

### Web: adquisición {#web-acquisition}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-acquisition-template"
>title="Ver cómo el sitio web obtiene visitantes en dispositivos móviles."
>abstract="**Esto puede ayudarle** a comprender mejor los distintos factores que llevan a la adquisición, como palabras clave de búsqueda, dominio de referencia, etc.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como enfocar los esfuerzos de marketing en los canales más efectivos.<br/>Esta plantilla usa las métricas Tasa de salida hacia otro sitio y Devoluciones. También utiliza las dimensiones Motor de búsqueda, Palabra clave de búsqueda, Página de entrada, Dominio de referencia, Código de seguimiento y Referente."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--advertisingAnalyticsPaidSearch"
>title="Ver todos los datos de búsqueda de pago de Google y Bing uno al lado del otro. "
>abstract="**Esto puede ayudarle** a comprender mejor la cantidad de tráfico que se envía a su sitio y si los clientes están realizando conversiones.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como calcular la rentabilidad de una campaña de publicidad."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--searchEngineRankRankedReport"
>title="Ver en qué página de resultados de búsqueda hizo clic un visitante en su sitio. Por ejemplo, si su sitio aparece en la segunda página de resultados de búsqueda de un motor de búsqueda, el elemento de dimensión de esta variable es “Página de búsqueda 2”."
>abstract="**Esto puede ayudarle** a comprender mejor la posición que ocupan sus páginas en los resultados de búsqueda.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como mejorar su estrategia de optimización de los motores de búsqueda para asegurarse de que el contenido se muestre en la primera página de resultados de búsqueda."

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--marketing-channel-overview-template"
>title="Al utilizar la atribución personalizada, esta plantilla muestra cómo llegan los visitantes al sitio."
>abstract="**Esto puede ayudarle** a entender mejor cuáles de sus canales de marketing son los más efectivos.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como invertir más en canales de marketing efectivos y desinvertir en canales de marketing menos eficaces.<br/>Esta plantilla usa la dimensión ID (variables/canal de mercadotecnia) y la métrica Ingresos."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--firstouchChannelRankedReport"
>title="Consulte el primer canal de marketing con el que un visitante coincide durante el período de participación de ese visitante (de forma predeterminada, 30 días)."
>abstract="**Esto puede ayudarle** a comprender mejor qué canales de marketing dirigen el tráfico inicial a su sitio.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como enfocar los esfuerzos de marketing en las áreas más efectivas.<br/>Esta plantilla usa la dimensión de Canal de primer contacto."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--firstouchChannelDetailRankedReport"
>title="Ver detalles sobre el primer canal de marketing con el que un visitante coincide durante el período de participación de ese visitante (30 días de forma predeterminada)."
>abstract=" **Esto puede ayudarle** a comprender qué contribuyó a que la visita coincidiera con un canal de marketing. Por ejemplo: si un visitante llegó a su sitio y coincidió con el canal de marketing de “Búsqueda de pago”, puede utilizar el detalle de canal para ver qué motor de búsqueda se utilizó o qué palabra clave buscó.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como enfocar los esfuerzos de marketing en las áreas más efectivas.<br/>Esta plantilla usa la dimensión Detalle de canal de primer toque."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--campaignConversionReport"
>title="Ver la cantidad de clics y cierres de compra de sus campañas."
>abstract="**Esto puede ayudarle** a comprender mejor cómo las campañas de marketing generan conversiones.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como determinar qué campañas de marketing generan el máximo retorno de la inversión."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--retail-campaign-performance-template"
>title="Ver detalles sobre el rendimiento de sus campañas de marketing."
>abstract="**Esto puede ayudarle** a comprender mejor los distintos indicadores de éxito asociados con las campañas, como los ingresos, las vistas de productos, los pedidos, etc.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como enfocar los esfuerzos de marketing en las campañas que generan la mayor cantidad de ingresos. <br/>Esta plantilla usa las métricas Ingresos, Vistas del producto, Adiciones al carro de compras, Pedidos y Unidades. También utiliza la dimensión Código de seguimiento y la dimensión Dominio de referencia."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--web-acquisition-template"
>title="Ver cómo su sitio web obtiene visitantes."
>abstract="**Esto puede ayudarle** a comprender mejor los distintos factores que llevan a la adquisición, como palabras clave de búsqueda, dominio de referencia, etc.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como enfocar los esfuerzos de marketing en los canales más efectivos.<br/>Esta plantilla usa las métricas Tasa de salida hacia otro sitio y Devoluciones. También utiliza las dimensiones Motor de búsqueda, Palabra clave de búsqueda, Página de entrada, Dominio de referencia, Código de seguimiento y Referente."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchKeywordRankedReport"
>title="Vea las palabras clave de búsqueda que los visitantes utilizan para llegar al sitio, independientemente de si son de pago o no."
>abstract="**Esto puede ayudarle** a comprender mejor las palabras clave que usan los visitantes en las búsquedas que generan tráfico en el sitio. <br/>**En función de lo que aprenda, podría** hacer muchas cosas, como identificar y rellenar las lagunas de optimización de los motores de búsqueda entre las palabras clave que se usan y las que impulsan el tráfico del sitio.<br/>Esta plantilla usa la dimensión Palabra clave de búsqueda."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchPaidKeywordRankedReport"
>title="Ver las palabras clave de búsqueda que los visitantes utilizan para llegar al sitio, que coincidieron con la detección de búsquedas de pago."
>abstract="**Esto puede ayudarle** a comprender mejor las palabras clave que usan los visitantes en las búsquedas que generan tráfico en el sitio.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como identificar y rellenar las lagunas de optimización de los motores de búsqueda entre las palabras clave que se usan y las que impulsan el tráfico del sitio. <br/>Esta plantilla usa la dimensión Palabra clave de búsqueda: de pago. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchNaturalKeywordRankedReport"
>title="Ver las palabras clave de búsqueda que los visitantes utilizan para llegar al sitio, que no coinciden con la detección de búsquedas de pago."
>abstract="**Esto puede ayudarle** a comprender mejor las palabras clave que usan los visitantes en las búsquedas que generan tráfico en el sitio.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como identificar y rellenar las lagunas de optimización de los motores de búsqueda entre las palabras clave que se usan y las que impulsan el tráfico del sitio.<br/>Esta plantilla usa la Palabra clave de búsqueda: dimensión natural. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchRankedReport"
>title="Ver los motores de búsqueda que los visitantes utilizan para llegar al sitio, independientemente de si es de pago o natural."
>abstract="**Esto puede ayudarle** a comprender mejor los motores de búsqueda que usan los usuarios para generar tráfico en el sitio. <br/>**Según lo que aprenda, podría** hacer muchas cosas, como enfocar sus esfuerzos de SEO en los motores de búsqueda que generan la mayor cantidad de tráfico en el sitio.<br/>Esta plantilla usa la dimensión Motor de búsqueda. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchPaidRankedReport"
>title="Ver los motores de búsqueda que los visitantes utilizan para llegar al sitio, que coincidieron con la detección de búsquedas de pago."
>abstract="**Esto puede ayudarle** a comprender mejor los motores de búsqueda que usan los usuarios para generar tráfico en el sitio.<br/>**Según lo que aprendas, podría** hacer muchas cosas, como enfocar sus esfuerzos de SEO en los motores de búsqueda que generan la mayor cantidad de tráfico en el sitio. <br/>Esta plantilla usa la dimensión Motor de búsqueda: de pago."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchNaturalRankedReport"
>title="Ver las palabras clave de búsqueda que los visitantes utilizan para llegar al sitio, que no coinciden con la detección de búsquedas de pago."
>abstract="**Esto puede ayudarle** a comprender mejor los motores de búsqueda que usan los usuarios para generar tráfico en el sitio.<br/>**Según lo que aprenda, podría** hacer muchas cosas, como enfocar sus esfuerzos de SEO en los motores de búsqueda que generan la mayor cantidad de tráfico en el sitio.<br/>Esta plantilla usa la dimensión Motor de búsqueda: natural."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referringDomainRankedReport"
>title="Ver los dominios en los que los visitantes hacen clic para llegar a su sitio."
>abstract="**Esto puede ayudarle** a comprender qué sitios de terceros generan la mayor cantidad de tráfico en el suyo. (Debe existir un vínculo en el sitio externo y un visitante debe hacer clic en él para que se muestre el elemento de la dimensión).<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como crear o ajustar contenido para que se ajuste mejor a los intereses de los visitantes que provienen de los dominios de referencia principales. <br/>Esta plantilla usa la dimensión Dominio de referencia."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referringDomainOriginalRankedReport"
>title="Ver el primer dominio de referencia en el que los visitantes hicieron clic para llegar a su sitio. (Una vez configurado, contiene el mismo valor para toda la duración de ese ID de visitante)."
>abstract="**Esto puede ayudarle a comprender** qué sitios de terceros originalmente generan tráfico a su sitio.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como crear o ajustar contenido para que se alinee mejor a los intereses de los visitantes que provienen de los principales dominios de referencia originales. <br/>Esta plantilla usa la dimensión Dominio de referencia original."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referrerRankedReport"
>title="Ver en qué direcciones URL se encontraban los visitantes al hacer clic para llegar al sitio. (Debe existir un vínculo en la dirección URL externa y un visitante debe hacer clic en él para que se muestre el elemento de dimensión)."
>abstract="**Esto puede ayudarle** a comprender qué direcciones URL específicas generan la mayor cantidad de tráfico en el sitio. <br/>**En función de lo que aprenda, podría** hacer muchas cosas, como crear o ajustar contenido para que se ajuste mejor a los intereses de los visitantes que provienen de las principales direcciones URL. <br/>Esta plantilla usa la dimensión Dominio de referencia.</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referrerTypeRankedReport"
>title="Ver en qué canales genéricos hicieron clic los visitantes para llegar al sitio. Adobe mantiene las reglas para cada canal. Los posibles canales incluyen motores de búsqueda, redes sociales, otros sitios web, discos duros o correo electrónico."
>abstract="**Esto puede ayudarle** a comprender mejor qué tipo de referentes generan la mayor cantidad de tráfico en el sitio.<br/>**En función de lo que aprenda, puede** hacer muchas cosas, como crear o ajustar contenido para que se ajuste mejor a los intereses de los visitantes que vienen de un canal determinado.<br/>Esta plantilla usa la dimensión Tipo de referente."

<!-- markdownlint-enable MD034 -->

Las plantillas disponibles son las siguientes:

| Nombre de plantilla | Por qué utilizar esta plantilla<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Canales de marketing**] > [!UICONTROL **Informe de información general sobre los canales**] | Al utilizar la atribución personalizada, esta plantilla muestra cómo llegan los visitantes al sitio.<p>**Esto puede ayudarle** a entender mejor cuáles de sus canales de marketing son los más efectivos.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como invertir más en canales de marketing efectivos y desinvertir en canales de marketing menos eficaces.</p><p>Esta plantilla usa la dimensión ID (variables/canal de mercadotecnia) y la métrica Ingresos.</p> |
| [!UICONTROL **Canales de marketing**] > [!UICONTROL **Canal de primer contacto**] | Consulte el primer canal de marketing con el que un visitante coincide durante el período de participación de ese visitante (de forma predeterminada, 30 días). <p>**Esto puede ayudarle** a comprender mejor qué canales de marketing dirigen el tráfico inicial a su sitio.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como enfocar los esfuerzos de marketing en las áreas más efectivas.</p><p>Esta plantilla usa la dimensión Canal de primer contacto.</p> |
| [!UICONTROL **Canales de marketing**] > [!UICONTROL **Detalle del canal de primer contacto**] | Ver detalles sobre el primer canal de marketing con el que un visitante coincide durante el período de participación de ese visitante (30 días de forma predeterminada).<p> **Esto puede ayudarle** a comprender qué contribuyó a que la visita coincidiera con un canal de marketing. Por ejemplo: si un visitante llegó a su sitio y coincidió con el canal de marketing de “Búsqueda de pago”, puede utilizar el detalle de canal para ver qué motor de búsqueda se utilizó o qué palabra clave buscó.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como enfocar los esfuerzos de marketing en las áreas más efectivas.</p><p>Esta plantilla usa la dimensión Detalle de canal de primer contacto.</p> |
| [!UICONTROL **Canales de marketing**] > [!UICONTROL **Canal de último contacto**] | Ver el canal de marketing más reciente con el que un visitante coincide durante el período de participación de ese visitante (de forma predeterminada, 30 días).<p>**Esto puede ayudarle** a comprender mejor qué canales de marketing dirigen el tráfico inicial a su sitio.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como enfocar los esfuerzos de marketing en las áreas más efectivas.</p><p>Esta plantilla usa la dimensión Canal de primer contacto.  </p> |
| [!UICONTROL **Canales de marketing**] > [!UICONTROL **Detalle del canal de último contacto**] | Ver detalles sobre el primer canal de marketing con el que un visitante coincide durante el período de participación de ese visitante (30 días de forma predeterminada).<p> **Esto puede ayudarle** a comprender qué contribuyó a que la visita coincidiera con un canal de marketing. Por ejemplo: si un visitante llegó a su sitio y coincidió con el canal de marketing de “Búsqueda de pago”, puede utilizar el detalle de canal para ver qué motor de búsqueda se utilizó o qué palabra clave buscó.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como enfocar los esfuerzos de marketing en las áreas más efectivas. </p><p>Esta plantilla usa la dimensión Detalle del canal de último toque. </p> |
| &lbrace;[!UICONTROL **Campañas**] > [!UICONTROL **Código de seguimiento**] | Ver los nombres de los códigos de seguimiento en su sitio. Puede colocar vínculos con diferentes valores de parámetro de cadena de consulta en diferentes lugares de Internet. <p>**Estoi puede ayudarle** a conocer mejor qué vínculos fueron los más exitosos a la hora de impulsar el tráfico al sitio. Añadir cadenas de consulta de código de seguimiento es habitual en los correos electrónicos, anuncios de medios sociales y otros esfuerzos de marketing que utiliza su organización</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como centrar los esfuerzos de marketing en las campañas que generan la mayor cantidad de ingresos.</p><p>Esta plantilla utiliza la dimensión Código de seguimiento. </p> |
| [!UICONTROL **Campañas**] > [!UICONTROL **Canal de conversión de campaña**] | Ver la cantidad de clics y cierres de compra de sus campañas. <p>**Esto puede ayudarle** a comprender mejor cómo las campañas de marketing generan conversiones.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como determinar qué campañas de marketing generan el máximo retorno de la inversión.</p> |
| [!UICONTROL **Campañas**] > [!UICONTROL **Rendimiento de la campaña**] | Ver detalles sobre el rendimiento de sus campañas de marketing.<p>**Esto puede ayudarle** a comprender mejor los distintos indicadores de éxito asociados con las campañas, como los ingresos, las vistas de productos, los pedidos, etc.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como centrar los esfuerzos de marketing en las campañas que generan la mayor cantidad de ingresos. </p><p>Esta plantilla usa las métricas Ingresos, Vistas del producto, Adiciones al carro de compras, Pedidos y Unidades. También utiliza la dimensión Código de seguimiento y Dominio de referencia. </p> |
| **Adquisición web** | Ver cómo su sitio web obtiene visitantes.<p>**Esto puede ayudarle** a comprender mejor los distintos factores que llevan a la adquisición, como palabras clave de búsqueda, dominio de referencia, etc.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como enfocar los esfuerzos de marketing en los canales más efectivos.</p><p>Esta plantilla usa las métricas de Tasa de salida hacia otro sitio y Rechazos. También utiliza las dimensiones Motor de búsqueda, Palabra clave de búsqueda, Página de entrada, Dominio de referencia, Código de seguimiento y Referente.  </p> |
| **Palabras clave de búsqueda: todo** | Ver las palabras clave de búsqueda que los visitantes utilizan para llegar al sitio, independientemente de si son de pago o no. <p>**Esto puede ayudarle** a comprender mejor las palabras clave que usan los visitantes en las búsquedas que generan tráfico en el sitio. </p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como identificar y rellenar las lagunas de optimización de los motores de búsqueda entre las palabras clave que se usan y las que impulsan el tráfico del sitio.</p><p>Esta plantilla usa la dimensión Palabra clave de búsqueda. </p> |
| **Palabras clave de búsqueda: de pago** | Ver las palabras clave de búsqueda que los visitantes utilizan para llegar al sitio, que coincidieron con la detección de búsquedas de pago.<p>**Esto puede ayudarle** a comprender mejor las palabras clave que usan los visitantes en las búsquedas que generan tráfico en el sitio.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como identificar y rellenar las lagunas de optimización de los motores de búsqueda entre las palabras clave que se usan y las que impulsan el tráfico del sitio. </p><p>Esta plantilla usa la dimensión Palabra clave de búsqueda: de pago. </p> |
| **Palabras clave de búsqueda: natural** | Ver las palabras clave de búsqueda que los visitantes utilizan para llegar al sitio, que no coinciden con la detección de búsquedas de pago.<p>**Esto puede ayudarle** a comprender mejor las palabras clave que usan los visitantes en las búsquedas que generan tráfico en el sitio.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como identificar y rellenar las lagunas de optimización de los motores de búsqueda entre las palabras clave que se usan y las que impulsan el tráfico del sitio.</p><p>Esta plantilla usa la dimensión Palabra clave de búsqueda: natural. </p> |
| **Motores de búsqueda: todo** | Ver los motores de búsqueda que los visitantes utilizan para llegar al sitio, independientemente de si es de pago o natural. <p>**Esto puede ayudarle** a comprender mejor los motores de búsqueda que usan los usuarios para generar tráfico en el sitio. </p><p>**Según lo que aprenda, podría** hacer muchas cosas, como enfocar sus esfuerzos de SEO en los motores de búsqueda que generan la mayor cantidad de tráfico en el sitio.</p><p>Esta plantilla usa la dimensión Motor de búsqueda. </p> |
| **Motores de búsqueda: de pago** | Ver los motores de búsqueda que los visitantes utilizan para llegar al sitio, que coincidieron con la detección de búsquedas de pago.<p>**Esto puede ayudarle** a comprender mejor los motores de búsqueda que usan los usuarios para generar tráfico en el sitio.</p><p>**Según lo que aprenda, podría** hacer muchas cosas, como enfocar sus esfuerzos de SEO en los motores de búsqueda que generan la mayor cantidad de tráfico en el sitio. </p><p>Esta plantilla usa la dimensión Motor de búsqueda: de pago. </p> |
| **Motores de búsqueda: natural** | Ver las palabras clave de búsqueda que los visitantes utilizan para llegar al sitio, que no coinciden con la detección de búsquedas de pago.<p>**Esto puede ayudarle** a comprender mejor los motores de búsqueda que usan los usuarios para generar tráfico en el sitio.</p><p>**Según lo que aprenda, podría** hacer muchas cosas, como enfocar sus esfuerzos de SEO en los motores de búsqueda que generan la mayor cantidad de tráfico en el sitio.</p><p>Esta plantilla usa la dimensión Motor de búsqueda: natural. </p> |
| **Dominios de referencia** | Ver los dominios en los que los visitantes hacen clic para llegar a su sitio.<p>**Esto puede ayudarle** a comprender qué sitios de terceros generan la mayor cantidad de tráfico en el suyo. (Debe existir un vínculo en el sitio externo y un visitante debe hacer clic en él para que se muestre el elemento de la dimensión).</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como crear o ajustar contenido para que se ajuste mejor a los intereses de los visitantes que provienen de los dominios de referencia principales. </p><p>Esta plantilla usa la dimensión Dominio de referencia. </p> |
| **Dominios de referencia originales** | Ver el primer dominio de referencia en el que los visitantes hicieron clic para llegar a su sitio. (Una vez configurado, contiene el mismo valor para toda la duración de ese ID de visitante).<p>**Esto puede ayudarle a comprender** qué sitios de terceros originalmente generan tráfico a su sitio.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como crear o ajustar contenido para que se alinee mejor a los intereses de los visitantes que provienen de los principales dominios de referencia originales. </p><p>Esta plantilla usa la dimensión Dominio de referencia original. </p> |
| **Referentes** | Ver en qué direcciones URL se encontraban los visitantes al hacer clic para llegar al sitio. (Debe existir un vínculo en la dirección URL externa y un visitante debe hacer clic en él para que se muestre el elemento de dimensión).  <p>**Esto puede ayudarle** a comprender qué direcciones URL específicas generan la mayor cantidad de tráfico en el sitio. </p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como crear o ajustar contenido para que se ajuste mejor a los intereses de los visitantes que provienen de las principales direcciones URL. </p><p>Esta plantilla usa la dimensión Dominio de referencia. </p><p>Esta plantilla usa la dimensión Referente. </p> |
| **Tipos de referente** | Ver en qué canales genéricos hicieron clic los visitantes para llegar al sitio. Adobe mantiene las reglas para cada canal. Los posibles canales incluyen motores de búsqueda, redes sociales, otros sitios web, discos duros o correo electrónico.<p>**Esto puede ayudarle** a comprender mejor qué tipo de referentes generan la mayor cantidad de tráfico en el sitio.</p><p>**En función de lo que aprenda, puede** hacer muchas cosas, como crear o ajustar contenido para que se ajuste mejor a los intereses de los visitantes que vienen de un canal determinado.</p><p>Esta plantilla usa la dimensión Tipo de referente.</p> |

### Móvil: aplicación móvil. {#mobile-app}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileappscreens"
>title="Ver el número de eventos, sesiones y personas asociadas con cada pantalla en la aplicación móvil."
>abstract="**Esto puede ayudarle** a comprender mejor qué pantallas del sitio son las más populares.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como mejorar el contenido en las pantallas más populares."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileappactions"
>title="Vea las acciones que realizan las personas en la aplicación móvil."
>abstract="**Esto puede ayudarle** a comprender mejor cómo usan su aplicación las personas y el valor que obtienen de ella.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como desarrollar características que complementen o mejoren las que sean más populares."

<!-- markdownlint-enable MD034 -->

<!--CJA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-lifecycle-metrics-app-usage-template"
>title="Ver la cantidad de usuarios, inicios y primeros inicios en la aplicación, así como la longitud promedio de sesión."
>abstract="**Esto puede ayudarle** a comprender mejor el grado de utilización de su aplicación. <br/>**A partir de lo que aprenda, puede** hacer muchas cosas, como mejorar el rendimiento de la aplicación para que se pueda escalar según la cantidad de uso."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-journeys"
>title="Ver los patrones de uso más destacados de su aplicación móvil."
>abstract="**Esto puede ayudarle** a comprender mejor cómo utilizan su aplicación los usuarios. <br/>**A partir de lo que aprenda, puede** hacer muchas cosas, como mejorar la forma en que las personas pueden pasar de una pantalla a otra para dirigirse a los flujos de trabajo más comunes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-key-metrics"
>title="Ver algunas de las métricas más comunes de las aplicaciones móviles."
>abstract="**Esto puede ayudarle** a comprender mejor el rendimiento básico de su aplicación móvil.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar el estado general y el rendimiento de su aplicación."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-messaging"
>title="Vea los datos de rendimiento de la mensajería en la aplicación y la mensajería push para su aplicación."
>abstract="**Esto puede ayudarle** a comprender mejor cómo usan las personas las funcionalidades de mensajería en la aplicación, así como la eficacia de las notificaciones push para dirigir el tráfico a su aplicación.<br/>**A partir de lo que aprenda, puede** hacer muchas cosas, como mejorar la experiencia de la notificación push en la mensajería en la aplicación."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-performance-template"
>title="Ver el rendimiento de su aplicación y dónde experimentan problemas los usuarios."
>abstract="**Esto puede ayudarle** a comprender mejor si las personas que utilizan su aplicación experimentan lentitud o un rendimiento degradado. <br/>**A partir de lo que aprenda, puede** hacer muchas cosas, como solucionar los problemas existentes o mejorar el rendimiento de su aplicación antes de que estos se produzcan."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-retention"
>title="Vea qué usuarios son los clientes más fieles de su aplicación y qué hacen dentro de ella."
>abstract="**Esto puede ayudarle** a comprender mejor cómo utilizan su aplicación los clientes más fieles. <br/>**A partir de lo que aprenda, podría** hacer muchas cosas, como mejorar sus esfuerzos de marketing para las funciones que utilizan sus clientes más fieles."

<!-- markdownlint-enable MD034 -->

Las plantillas disponibles son las siguientes:

| Nombre de plantilla | Por qué utilizar esta plantilla<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Pantallas de aplicaciones móviles**] | Ver el número de eventos, sesiones y personas asociadas con cada pantalla en la aplicación móvil.<p>**Esto puede ayudarle** a comprender mejor qué pantallas del sitio son las más populares.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como mejorar el contenido en las pantallas más populares.</p><p>Esta plantilla utiliza las métricas Eventos, Sesiones, Personas y Porcentaje de cambio. También utiliza la dimensión Mosaico de página.</p> |
| **Acciones de la aplicación móvil** | Vea las acciones que realizan las personas en la aplicación móvil. <p>**Esto puede ayudarte** a comprender mejor cómo usan tu aplicación las personas y el valor que obtienen de ella.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como desarrollar funciones que complementen o mejoren las que sean más populares.</p><p>Esta plantilla utiliza las métricas Eventos, Sesiones, Personas y Porcentaje de cambio. |
| **Uso de aplicaciones móviles** | Ver la cantidad de usuarios, inicios y primeros inicios en la aplicación, así como la longitud promedio de sesión.<p>**Esto puede ayudarte** a comprender mejor cuánto se usa tu aplicación. </p><p>**A partir de lo que aprenda, puede** hacer muchas cosas, como mejorar el rendimiento de la aplicación para que se pueda escalar según la cantidad de uso.</p><!-- This template uses the --> |
| **Recorridos de las aplicaciones móviles** | Ver los patrones de uso más destacados de su aplicación móvil. <p>**Esto puede ayudarte** a comprender mejor cómo usan tu aplicación las personas. </p><p>**A partir de lo que aprenda, puede** hacer muchas cosas, como mejorar la forma en que las personas pueden pasar de una pantalla a otra para dirigirse a los flujos de trabajo más comunes. </p><!-- This template uses the --> |
| **Métricas de las aplicaciones móviles** | Ver algunas de las métricas más comunes de las aplicaciones móviles. <p>**Esto puede ayudarle** a comprender mejor el rendimiento básico de su aplicación móvil.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como evaluar el estado general y el rendimiento de su aplicación.</p><!-- This template uses the --> |
| **Mensajería de la aplicación móvil** | Vea los datos de rendimiento de la mensajería en la aplicación y la mensajería push para su aplicación.<p>**Esto puede ayudarle** a comprender mejor cómo usan las personas las funcionalidades de mensajería en la aplicación, así como la eficacia de las notificaciones push para dirigir el tráfico a su aplicación.</p><p>**A partir de lo que aprenda, puede** hacer muchas cosas, como mejorar la experiencia de la notificación push en la mensajería en la aplicación.</p><!-- This template uses the --> |
| **Rendimiento de la aplicación móvil** | Ver el rendimiento de su aplicación y dónde experimentan problemas los usuarios. <p>**Esto puede ayudarle** a comprender mejor si las personas que utilizan su aplicación experimentan lentitud o un rendimiento degradado. </p><p>**A partir de lo que aprenda, puede** hacer muchas cosas, como solucionar los problemas existentes o mejorar el rendimiento de su aplicación antes de que estos se produzcan.</p><!-- This template uses the --> |
| **Retención de la aplicación móvil** | Vea qué usuarios son los clientes más fieles de su aplicación y qué hacen dentro de ella. <p>**Esto puede ayudarle** a comprender mejor cómo utilizan su aplicación los clientes más fieles. </p><p>**A partir de lo que aprenda, podría** hacer muchas cosas, como mejorar sus esfuerzos de marketing para las funciones que utilizan sus clientes más fieles.</p><!-- This template uses the --> |

### Móvil: información del dispositivo móvil {#mobile-devices}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileCarrierRankedReport"
>title="Ver la compañía de telecomunicaciones que proporciona conectividad de red celular a los dispositivos móviles que los usuarios utilizan para acceder al sitio."
>abstract="**Esto puede ayudarle** a comprender mejor qué operadores de telefonía móvil son los más populares entre su base de usuarios.<br/>**En función de lo que aprenda, podría** hacer cualquier cosa, como adaptar la entrega de contenido en función de las capacidades de red de diferentes operadores para garantizar una experiencia de usuario sin problemas.<br/>Esta plantilla usa la dimensión Operador de telefonía móvil."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileDeviceNameRankedReport"
>title="Ver la marca y el modelo de dispositivos móviles que los usuarios utilizan para acceder al sitio."
>abstract="**Esto puede ayudarle** a comprender mejor qué dispositivos móviles son los más populares entre su base de usuarios.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como optimizar la representación del sitio para los dispositivos móviles más comunes.<br/>Esta plantilla usa la dimensión Nombre del dispositivo móvil."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileDeviceTypeRankedReport"
>title="Vea los tipos de dispositivos móviles que usan los usuarios para acceder al sitio, como teléfonos y tabletas."
>abstract="**Esto puede ayudarle** a comprender mejor los distintos tipos de dispositivos móviles que se usan para acceder al sitio.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como optimizar el sitio para los tipos de dispositivos móviles que más se usan.<br/>Esta plantilla utiliza la dimensión Tipo de dispositivo móvil."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileManufacturerRankedReport"
>title="Ver qué fabricantes producen los dispositivos móviles que usan los usuarios para acceder al sitio, como Apple y Samsung."
>abstract="**Esto puede ayudarle** a entender mejor qué fabricantes son los más populares entre su base de usuarios.<br/>**En función de lo que aprenda, puede** hacer cualquier cosa, como adaptar su entrega de contenido en función de las capacidades de diferentes fabricantes para garantizar una experiencia de usuario sin problemas.<br/>Esta plantilla usa la dimensión Fabricante del móvil."

<!-- markdownlint-enable MD034 -->

Las plantillas disponibles son las siguientes:

| Nombre de plantilla | Por qué utilizar esta plantilla<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Operador de telefonía móvil**] | Ver la compañía de telecomunicaciones que proporciona conectividad de red celular a los dispositivos móviles que los usuarios utilizan para acceder al sitio.<p>**Esto puede ayudarle** a comprender mejor qué operadores de telefonía móvil son los más populares entre su base de usuarios.</p><p>**En función de lo que aprenda, podría** hacer cualquier cosa, como adaptar la entrega de contenido en función de las capacidades de red de diferentes operadores para garantizar una experiencia de usuario sin problemas.</p><p>Esta plantilla usa la dimensión Operador de telefonía móvil.</p> |
| **Dispositivos** | Ver la marca y el modelo de dispositivos móviles que los usuarios utilizan para acceder al sitio.<p>**Esto puede ayudarle** a comprender mejor qué dispositivos móviles son los más populares entre su base de usuarios.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como optimizar la representación del sitio para los dispositivos móviles más comunes.</p><p>Esta plantilla usa la dimensión Nombre de dispositivo móvil.</p> |
| **Tipo de dispositivo** | Vea los tipos de dispositivos móviles que usan los usuarios para acceder al sitio, como teléfonos y tabletas.<p>**Esto puede ayudarle** a comprender mejor los distintos tipos de dispositivos móviles que se usan para acceder al sitio.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como optimizar el sitio para los tipos de dispositivos móviles que más se usan.</p><p>Esta plantilla utiliza la dimensión Tipo de dispositivo móvil.</p> |
| **Fabricante** | Ver qué fabricantes producen los dispositivos móviles que usan los usuarios para acceder al sitio, como Apple y Samsung.<p>**Esto puede ayudarle** a entender mejor qué fabricantes son los más populares entre su base de usuarios.</p><p>**En función de lo que aprenda, puede** hacer cualquier cosa, como adaptar su entrega de contenido en función de las capacidades de diferentes fabricantes para garantizar una experiencia de usuario sin problemas.</p><p>Esta plantilla usa la dimensión Fabricante del móvil.</p> |

### Partición del tiempo {#time-parting}

<!--CJA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--minuteOfHour"
>title="Ver el número de eventos, sesiones y personas del sitio, desglosado por minuto. Por ejemplo, si tiene un informe con un periodo de tiempo de creación de informes de un solo día, el primer minuto de cada hora del día se agrupa en el mismo elemento de dimensión."
>abstract="**Esto puede ayudarle** a comprender mejor las tendencias a nivel granular.<br/>**A partir de lo que aprenda, puede** hacer muchas cosas, como optimizar los recursos para las horas punta al minuto.<br/>Esta plantilla utiliza la dimensión Minuto de hora."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--hourOfDay"
>title="Ver eventos, sesiones y personas del sitio, desglosados por la hora del día. Por ejemplo, si tiene un informe que abarca del 1 de enero al 7 de enero, la primera hora de cada día se agrupa en el mismo elemento de dimensión."
>abstract="**Esto puede ayudarle** a comprender mejor a qué hora del día se visita el sitio con mayor y menor frecuencia.<br/>**A partir de lo que aprenda, puede** hacer muchas cosas, como asignar más recursos informáticos al sitio durante las horas de mayor tráfico.<br/>Esta plantilla utiliza la dimensión Hora del día."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--am-pm"
>title="Vea eventos, sesiones y personas del sitio, desglosados por AM y PM. Por ejemplo, si tiene un informe que abarca del 1 de enero al 7 de enero, las horas AM de cada día se agrupan en el mismo elemento de dimensión."
>abstract="***Esto puede ayudarle** a comprender mejor a qué hora del día se visita el sitio con mayor y menor frecuencia.<br/>**A partir de lo que aprenda, puede** hacer muchas cosas, como asignar más recursos informáticos al sitio durante las horas de mayor tráfico.<br/>Esta plantilla utiliza la dimensión AM/PM."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dayOfWeek"
>title="Ver eventos, sesiones y personas del sitio, desglosados por el día de la semana. Por ejemplo, si tiene un informe que abarca el mes de enero, cada día de la semana se agrupa en el mismo elemento de dimensión."
>abstract="**Esto puede ayudarle** a comprender mejor qué días de la semana se visita el sitio con mayor frecuencia y con menor frecuencia.<br/>**En función de lo que aprenda, puede** hacer muchas cosas, como dotar a su centro de llamadas de personal más adecuado para los días de mayor tráfico.<br/>Esta plantilla utiliza la dimensión Día de la semana."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dayOfMonth"
>title="Vea eventos, sesiones y personas del sitio, desglosados por día del mes. Por ejemplo, si tiene un informe que abarca un año completo, cada día del mes se agrupa en el mismo elemento de dimensión."
>abstract="**Esto puede ayudarle** a comprender mejor qué días del mes se visita el sitio con mayor y menor frecuencia.<br/>**En función de lo que aprenda, puede** hacer muchas cosas, como dotar a su centro de llamadas de personal más adecuado para los días de mayor tráfico.<br/>Esta plantilla utiliza la dimensión Día del mes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dayOfYear"
>title="Vea eventos, sesiones y personas del sitio, desglosados por día del año. Por ejemplo, si tiene un informe que abarca varios años, cada día del año se agrupa en el mismo elemento de dimensión."
>abstract="**Esto puede ayudarle** a comprender mejor qué días de cada año se visita el sitio con mayor y menor frecuencia.<br/>**En función de lo que aprenda, puede** hacer muchas cosas, como dotar a su centro de llamadas de personal más adecuado para los días de mayor tráfico.<br/>Esta plantilla utiliza la dimensión Día del año."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--weekdayWeekend"
>title="Vea eventos, sesiones y personas del sitio, desglosados por días entre semana y fines de semana. Por ejemplo, si tiene un informe que abarca el mes de enero, los días de la semana y los fines de semana se agrupan en elementos de dimensión independientes."
>abstract="**Esto puede ayudarle** a comprender mejor las diferencias en el tráfico del sitio entre semana en comparación con los fines de semana.<br/>**En función de lo que aprenda, puede** hacer muchas cosas, como dotar a su centro de llamadas de más personal los fines de semana, si el informe indica que los fines de semana son más ajetreados que los días laborables.<br/>Esta plantilla utiliza la dimensión Día de la semana/Fin de semana."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--weekOfYear"
>title="Vea eventos, sesiones y personas del sitio, desglosados por semana del año. Por ejemplo, si tiene un informe que abarca varios años, cada semana se agrupa en el mismo elemento de dimensión."
>abstract="**Esto puede ayudarle** a comprender mejor qué semanas del año se visita el sitio con mayor y menor frecuencia.<br/>**En función de lo que aprenda, puede** hacer muchas cosas, como dotar a su centro de llamadas de personal más adecuado para las semanas de mayor tráfico, como las vacaciones.<br/>Esta plantilla utiliza la dimensión Semana del año."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--monthOfYear"
>title="Vea eventos, sesiones y personas del sitio, desglosados por mes del año. Por ejemplo, si tiene un informe que abarca varios años, cada mes se agrupa en el mismo elemento de dimensión."
>abstract="**Esto puede ayudarle** a comprender mejor qué meses se visita el sitio con mayor y menor frecuencia.<br/>**En función de lo que aprenda, puede** hacer muchas cosas, como dotar a su centro de llamadas de personal más adecuado para las semanas de mayor tráfico, como las vacaciones.<br/>Esta plantilla utiliza la dimensión Mes del año."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--quarterOfYear"
>title="Vea eventos, sesiones y personas del sitio, desglosados por trimestre del año. Por ejemplo, si tiene un informe que abarca varios años, cada trimestre se agrupa en el mismo elemento de dimensión."
>abstract="**Esto puede ayudarle** a comprender mejor qué trimestres del sitio se visitan con mayor y menor frecuencia.<br/>**A partir de lo que aprenda, puede** hacer muchas cosas, como tiempo para el lanzamiento de productos para impulsar trimestres de tráfico históricamente bajo.<br/>Esta plantilla utiliza la dimensión Trimestre del año."

<!-- markdownlint-enable MD034 -->

Las plantillas disponibles son las siguientes:

| Nombre de plantilla | Por qué utilizar esta plantilla<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Minuto de la hora**] | Ver el número de eventos, sesiones y personas del sitio, desglosado por minuto. Por ejemplo, si tiene un informe con un periodo de tiempo de creación de informes de un solo día, el primer minuto de cada hora del día se agrupa en el mismo elemento de dimensión.<p>**Esto puede ayudarle** a comprender mejor las tendencias a nivel granular.</p><p>**A partir de lo que aprenda, puede** hacer muchas cosas, como optimizar los recursos para las horas punta al minuto.</p><p>Esta plantilla utiliza la dimensión Minuto de la hora.</p> |
| **Hora del día** | Vea eventos, sesiones y personas del sitio, desglosados por hora del día. Por ejemplo, si tiene un informe que abarca del 1 de enero al 7 de enero, la primera hora de cada día se agrupa en el mismo elemento de dimensión.<p>**Esto puede ayudarle** a comprender mejor a qué hora del día se visita el sitio con mayor y menor frecuencia.</p><p>**A partir de lo que aprenda, puede** hacer muchas cosas, como asignar más recursos informáticos al sitio durante las horas de mayor tráfico.</p><p>Esta plantilla utiliza la dimensión Hora del día.</p> |
| **a. m./p. m.** | Vea eventos, sesiones y personas del sitio, desglosados por AM y PM. Por ejemplo, si tiene un informe que abarca del 1 de enero al 7 de enero, las horas AM de cada día se agrupan en el mismo elemento de dimensión.<p>**Esto puede ayudarle** a comprender mejor a qué hora del día se visita el sitio con mayor y menor frecuencia.</p><p>**A partir de lo que aprenda, puede** hacer muchas cosas, como asignar más recursos informáticos al sitio durante las horas de mayor tráfico.</p><p>Esta plantilla utiliza la dimensión AM/PM.</p> |
| **Día de la semana** | Vea eventos, sesiones y personas del sitio, desglosados por día de la semana. Por ejemplo, si tiene un informe que abarca el mes de enero, cada día de la semana se agrupa en el mismo elemento de dimensión. <p>**Esto puede ayudarle** a comprender mejor qué días de la semana se visita el sitio con mayor frecuencia y con menor frecuencia.</p><p>**En función de lo que aprenda, puede** hacer muchas cosas, como dotar a su centro de llamadas de personal más adecuado para los días de mayor tráfico.</p><p>Esta plantilla utiliza la dimensión Día de la semana.</p> |
| **Día del mes** | Vea eventos, sesiones y personas del sitio, desglosados por día del mes. Por ejemplo, si tiene un informe que abarca un año completo, cada día del mes se agrupa en el mismo elemento de dimensión. <p>**Esto puede ayudarle** a comprender mejor qué días del mes se visita el sitio con mayor y menor frecuencia.</p><p>**En función de lo que aprenda, puede** hacer muchas cosas, como dotar a su centro de llamadas de personal más adecuado para los días de mayor tráfico.</p><p>Esta plantilla utiliza la dimensión Día del mes.</p> |
| **Día del año** | Vea eventos, sesiones y personas del sitio, desglosados por día del año. Por ejemplo, si tiene un informe que abarca varios años, cada día del año se agrupa en el mismo elemento de dimensión. <p>**Esto puede ayudarle** a comprender mejor qué días de cada año se visita el sitio con mayor y menor frecuencia.</p><p>**En función de lo que aprenda, puede** hacer muchas cosas, como dotar a su centro de llamadas de personal más adecuado para los días de mayor tráfico.</p><p>Esta plantilla utiliza la dimensión Día del año.&lt;/> |
| **Día de la semana/Fin de semana** | Vea eventos, sesiones y personas del sitio, desglosados por días entre semana y fines de semana. Por ejemplo, si tiene un informe que abarca el mes de enero, los días de la semana y los fines de semana se agrupan en elementos de dimensión independientes. <p>**Esto puede ayudarle** a comprender mejor las diferencias en el tráfico del sitio entre semana en comparación con los fines de semana.</p><p>**En función de lo que aprenda, puede** hacer muchas cosas, como dotar a su centro de llamadas de más personal los fines de semana, si el informe indica que los fines de semana son más ajetreados que los días laborables.</p><p>Esta plantilla utiliza la dimensión Día de la semana/Fin de semana.</p> |
| **Semana del año** | Vea eventos, sesiones y personas del sitio, desglosados por semana del año. Por ejemplo, si tiene un informe que abarca varios años, cada semana se agrupa en el mismo elemento de dimensión.<p>**Esto puede ayudarle** a comprender mejor qué semanas del año se visita el sitio con mayor y menor frecuencia.</p><p>**En función de lo que aprenda, puede** hacer muchas cosas, como dotar a su centro de llamadas de personal más adecuado para las semanas de mayor tráfico, como las vacaciones.</p><p>Esta plantilla utiliza la dimensión Semana del año.</p> |
| **Mes del año** | Vea eventos, sesiones y personas del sitio, desglosados por mes del año. Por ejemplo, si tiene un informe que abarca varios años, cada mes se agrupa en el mismo elemento de dimensión.<p>**Esto puede ayudarle** a comprender mejor qué meses se visita el sitio con mayor y menor frecuencia.</p><p>**En función de lo que aprenda, puede** hacer muchas cosas, como dotar a su centro de llamadas de personal más adecuado para las semanas de mayor tráfico, como las vacaciones.</p><p>Esta plantilla utiliza la dimensión Mes del año.</p> |
| **Trimestre del año** | Vea eventos, sesiones y personas del sitio, desglosados por trimestre del año. Por ejemplo, si tiene un informe que abarca varios años, cada trimestre se agrupa en el mismo elemento de dimensión.<p>**Esto puede ayudarle** a comprender mejor qué trimestres del sitio se visitan con mayor y menor frecuencia.</p><p>**A partir de lo que aprenda, puede** hacer muchas cosas, como tiempo para el lanzamiento de productos para impulsar trimestres de tráfico históricamente bajo.</p><p>Esta plantilla utiliza la dimensión Trimestre del año.</p> |

### Canales múltiples {#cross-channel}

<!--CJA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--multiChannelOverview"
>title="Ver la distribución del tráfico en múltiples canales."
>abstract="**Esto puede ayudarle** a comprender mejor qué canales están impulsando el tráfico y la participación con más éxito. <br/>**En función de lo que aprenda, podría** hacer muchas cosas, como centrar los esfuerzos de marketing en los canales que están logrando el mayor retorno de la inversión.<br/>Esta plantilla utiliza las métricas de usuario, sesión y evento."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--callCenterDeflection"
>title="Vea cómo afecta el tráfico web al tráfico del centro de llamadas."
>abstract="**Esto puede ayudarle** a comprender mejor el éxito con que el contenido de autoservicio de su sitio web está desviando el tráfico a su centro de llamadas.<br/>**A partir de lo que aprenda, puede** hacer muchas cosas, como mejorar el contenido de autoservicio para reducir el tráfico al centro de llamadas o medir el retorno de la inversión del contenido de autoservicio calculando la cantidad ahorrada mediante menos llamadas de asistencia.<br/>Esta plantilla utiliza las métricas Sesiones web, Sesiones de aplicación móvil y Sesiones en canales múltiples web+aplicación."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--webAppTemplate"
>title="Vea conjuntamente el tráfico web y el tráfico móvil."
>abstract="**Esto puede ayudarle** a comprender mejor la distribución del tráfico web y móvil a su sitio.<br/>**A partir de lo que aprenda, puede** hacer muchas cosas, como asignar más recursos a su experiencia de aplicación móvil cuando alcanza un determinado nivel de tráfico.<br/>Esta plantilla utiliza las métricas Sesiones web, Sesiones de aplicación móvil y Sesiones en canales múltiples web+aplicación."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--onlineOffline"
>title="Vea conjuntamente el tráfico en línea y sin conexión."
>abstract="**Esto puede ayudarle** a comprender mejor la distribución del tráfico en línea y sin conexión a su sitio.<br/>**A partir de lo que aprenda, puede** hacer muchas cosas, como asignar más recursos a su experiencia en línea cuando alcanza un determinado nivel de tráfico."

<!-- markdownlint-enable MD034 -->

Las plantillas disponibles son las siguientes:

| Nombre de plantilla | Por qué utilizar esta plantilla<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Información general multicanal**] | Ver la distribución del tráfico en múltiples canales. <p>**Esto puede ayudarle** a comprender mejor qué canales están impulsando el tráfico y la participación con más éxito.  </p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como centrar los esfuerzos de marketing en los canales que están logrando el mayor retorno de la inversión.</p><p>Esta plantilla utiliza las métricas de usuario, sesión y evento.</p> |
| **Web+aplicación** | Vea conjuntamente el tráfico web y el tráfico móvil.<p>**Esto puede ayudarle** a comprender mejor la distribución del tráfico web y móvil a su sitio.</p><p>**A partir de lo que aprenda, puede** hacer muchas cosas, como asignar más recursos a su experiencia de aplicación móvil cuando alcanza un determinado nivel de tráfico.</p><p>Esta plantilla utiliza las métricas Sesiones web, Sesiones de aplicación móvil y Sesiones en canales múltiples web+aplicación.</p> |
| **En línea/sin conexión** | Vea conjuntamente el tráfico en línea y sin conexión.<p>**Esto puede ayudarle** a comprender mejor la distribución del tráfico en línea y sin conexión a su sitio.</p><p>**A partir de lo que aprenda, puede** hacer muchas cosas, como asignar más recursos a su experiencia en línea cuando alcanza un determinado nivel de tráfico.</p><!-- This template uses the ... --> |
| **Desviación de centro de llamadas** | Vea cómo afecta el tráfico web al tráfico del centro de llamadas.<p>**Esto puede ayudarle** a comprender mejor el éxito con que el contenido de autoservicio de su sitio web está desviando el tráfico a su centro de llamadas.</p><p>**A partir de lo que aprenda, puede** hacer muchas cosas, como mejorar el contenido de autoservicio para reducir el tráfico al centro de llamadas o medir el retorno de la inversión del contenido de autoservicio calculando la cantidad ahorrada mediante menos llamadas de asistencia.</p><p>Esta plantilla utiliza las métricas Sesiones web, Sesiones de aplicación móvil y Sesiones en canales múltiples web+aplicación.</p> |

### Otros canales {#other-channels}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--callcenterdashboard"
>title="Ver los datos del centro de llamadas, incluido el motivo por el que los clientes han llamado y la cantidad de veces."
>abstract="**Esto puede ayudarle** a comprender mejor dónde están experimentando los clientes los problemas y dónde se están gastando los recursos del centro de llamadas.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como solucionar problemas de productos que aumentan el tráfico del centro de llamadas y que, en última instancia, mejoran la rentabilidad de los productos."

>[!CONTEXTUALHELP]
>id="cja-template--pointOfSale"
>title="Ver datos de transacciones del punto de venta (TPV), incluidos los ingresos obtenidos, los pedidos realizados y las unidades vendidas. Esta plantilla también incluye visualizaciones que muestran información sobre las principales tiendas, los principales productos y las principales categorías de productos, así como las ventas en línea frente a las ventas sin conexión."
>abstract="**Esto puede ayudarle** a comprender mejor cuáles son sus productos más vendidos en las tiendas y en línea.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como asignar más recursos de marketing a los productos y canales de mayor rendimiento."

>[!CONTEXTUALHELP]
>id="cja-template--ajo-email"
>title="Ver cómo los correos electrónicos que diseña y envía mediante Adobe Journey Optimizer generan nuevas suscripciones, miembros fieles y oportunidades de venta cruzada."
>abstract="**Esto puede ayudarle** a comprender mejor la eficacia de los correos electrónicos que diseña y envía mediante Adobe Journey Optimizer.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como ajustar su estrategia de correo electrónico a una campaña de correo electrónico determinada."

>[!CONTEXTUALHELP]
>id="cja-template--survey"
>title="Ver la participación del usuario en sus encuestas. Ver el número de inicios y finalizaciones, las preguntas y respuestas principales y el número de primeros participantes frente a los repetidos."
>abstract="**Esto puede ayudarle** a comprender mejor los niveles de participación y la tasa de éxito de sus encuestas.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como ajustar las futuras encuestas para obtener una mejor participación."

>[!CONTEXTUALHELP]
>id="cja-template--product-usage"
>title="Vea cómo utiliza su organización Customer Journey Analytics. "
>abstract="**Esto puede ayudarle** a comprender mejor cuántas personas de su organización usan Customer Journey Analytics, con qué frecuencia lo usan y las tendencias de uso a lo largo del tiempo. También puede ver el número de proyectos creados y los detalles sobre esos proyectos. Vea qué componentes, visualizaciones y paneles se utilizan con mayor frecuencia, entre otras estadísticas de uso.<br/>**En función de lo que aprenda, podría** hacer muchas cosas, como eliminar proyectos o componentes que no use, o proporcionar formación al usuario para las funciones más populares."

<!-- markdownlint-enable MD034 -->

Las plantillas disponibles son las siguientes:

| Nombre de plantilla | Por qué utilizar esta plantilla<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Panel del centro de llamadas**] | Ver los datos del centro de llamadas, incluido el motivo por el que los clientes han llamado y la cantidad de veces. <p>**Esto puede ayudarle** a comprender mejor dónde están experimentando los clientes los problemas y dónde se están gastando los recursos del centro de llamadas.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como solucionar problemas de productos que aumentan el tráfico del centro de llamadas y que, en última instancia, mejoran la rentabilidad de los productos.</p> |
| **Punto de venta** | Ver datos de transacciones del punto de venta (TPV), incluidos los ingresos obtenidos, los pedidos realizados y las unidades vendidas. Esta plantilla también incluye visualizaciones que muestran información sobre las principales tiendas, los principales productos y las principales categorías de productos, así como las ventas en línea frente a las ventas sin conexión. <p>**Esto puede ayudarle** a comprender mejor cuáles son sus productos más vendidos en las tiendas y en línea.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como asignar más recursos de marketing a los productos y canales de mayor rendimiento.</p><p>Esta plantilla utiliza las métricas Usuarios, Ingresos y Pedidos.</p> |
| **análisis de correo electrónico de Journey Optimizer** | Ver cómo los correos electrónicos que diseña y envía mediante Adobe Journey Optimizer generan nuevas suscripciones, miembros fieles y oportunidades de venta cruzada. <p>**Esto puede ayudarle** a comprender mejor la eficacia de los correos electrónicos que diseña y envía mediante Adobe Journey Optimizer.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como ajustar su estrategia de correo electrónico a una campaña de correo electrónico determinada.</p> |
| **Encuesta** | Ver la participación del usuario en sus encuestas. Ver el número de inicios y finalizaciones, las preguntas y respuestas principales y el número de primeros participantes frente a los repetidos.<p>**Esto puede ayudarle** a comprender mejor los niveles de participación y la tasa de éxito de sus encuestas.</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como ajustar las futuras encuestas para obtener una mejor participación.</p><p>Esta plantilla utiliza las métricas Usuarios, Eventos, Inicios de encuesta, Finalizaciones de encuesta y Tasa de finalización de encuesta.</p> |
| **Información general sobre el uso del producto** | Vea cómo utiliza su organización Customer Journey Analytics. <p>**Esto puede ayudarle** a comprender mejor cuántas personas de su organización usan Customer Journey Analytics, con qué frecuencia lo usan y las tendencias de uso a lo largo del tiempo. También puede ver el número de proyectos creados y los detalles sobre esos proyectos. Vea qué componentes, visualizaciones y paneles se utilizan con mayor frecuencia, entre otras estadísticas de uso. [Más información](/help/tools/product-usage/usage-overview.md)</p><p>**En función de lo que aprenda, podría** hacer muchas cosas, como eliminar proyectos o componentes que no use, o proporcionar formación al usuario para las funciones más populares.</p> |

### Journey Optimizer {#AJO-templates}

<!--CJA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-campaign"
>title="Vea métricas esenciales para sus campañas de Journey Optimizer, incluidas campañas de correo electrónico, experimentación, in-app, SMS y más."
>abstract="**Esto puede ayudarle** a comprender mejor detalles como el recuento de clics y la cantidad de mensajes enviados, lo que ofrece una perspectiva completa de la eficacia y del nivel de participación de su campaña.<br/>**A partir de lo que aprenda, puede** hacer muchas cosas, como ajustar sus campañas en función de los niveles de participación de su público destinatario."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-journey"
>title="Vea métricas esenciales para sus recorridos de Journey Optimizer, incluidos recorridos de correo electrónico, experimentación, in-app, SMS y más."
>abstract="**Esto puede ayudarle** a comprender mejor detalles como el recuento de clics y la cantidad de mensajes enviados, lo que ofrece una perspectiva completa de la efectividad y del nivel de participación de su recorrido.<br/>**A partir de lo que aprenda, puede** hacer muchas cosas, como ajustar sus campañas en función de los niveles de participación de su público destinatario."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-landing-page"
>title="Ver el comportamiento del usuario, los patrones de participación, las tasas de conversión y otras métricas clave."
>abstract="**Esto puede ayudarle** a comprender mejor la efectividad de su página de destino. <br/>**A partir de lo que aprenda, puede** hacer muchas cosas, como optimizar el rendimiento de su página de destino."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-channel"
>title="Ver un resumen completo de las métricas de tráfico y participación de todas las campañas y recorridos dentro de su entorno."
>abstract="**Esto puede ayudarle** a comprender mejor la efectividad a alto nivel de sus campañas y recorridos. <br/>**A partir de lo que aprenda, puede** hacer muchas cosas, como ajustar sus campañas y recorridos en función de los niveles de participación de su público destinatario."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-subscription"
>title="Vea las suscripciones y bajas de perfiles asociadas a listas concretas."
>abstract="**Esto puede ayudarle** a comprender mejor la efectividad de las diferentes campañas e iniciativas de suscripción para impulsar la participación y las conversiones.<br/>**A partir de lo que aprenda, puede** hacer muchas cosas, como ajustar sus campañas de suscripción en función de los niveles de participación de su público destinatario."

<!-- markdownlint-enable MD034 -->

Las plantillas disponibles son las siguientes:

| Nombre de plantilla | Por qué utilizar esta plantilla<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **Campañas de Journey Optimizer**] | Vea métricas esenciales para sus campañas de Journey Optimizer, incluidas campañas de correo electrónico, experimentación, in-app, SMS y más.<p>**Esto puede ayudarle** a comprender mejor detalles como el recuento de clics y la cantidad de mensajes enviados, lo que ofrece una perspectiva completa de la eficacia y del nivel de participación de su campaña.</p><p>**A partir de lo que aprenda, puede** hacer muchas cosas, como ajustar sus campañas en función de los niveles de participación de su público destinatario.</p> |
| **Recorridos de Journey Optimizer** | Vea métricas esenciales para sus recorridos de Journey Optimizer, incluidos recorridos de correo electrónico, experimentación, in-app, SMS y más.<p>**Esto puede ayudarle** a comprender mejor detalles como el recuento de clics y la cantidad de mensajes enviados, lo que ofrece una perspectiva completa de la efectividad y del nivel de participación de su recorrido.</p><p>**A partir de lo que aprenda, puede** hacer muchas cosas, como ajustar sus campañas en función de los niveles de participación de su público destinatario.</p> |
| **Páginas de destino de Journey Optimizer** | Ver el comportamiento del usuario, los patrones de participación, las tasas de conversión y otras métricas clave.<p>**Esto puede ayudarle** a comprender mejor la eficacia de su página de destino.  </p><p>**A partir de lo que aprenda, puede** hacer muchas cosas, como optimizar el rendimiento de su página de destino.</p> |
| **Informe de información general de Journey Optimizer** | Ver un resumen completo de las métricas de tráfico y participación de todas las campañas y recorridos dentro de su entorno.<p>**Esto puede ayudarle** a comprender mejor la eficacia a alto nivel de sus campañas y recorridos.  </p><p>**A partir de lo que aprenda, puede** hacer muchas cosas, como ajustar sus campañas y recorridos en función de los niveles de participación de su público destinatario.</p> |
| **Suscripciones de Journey Optimizer** | Vea las suscripciones y bajas de perfiles asociadas a listas concretas.<p>**Esto puede ayudarle** a comprender mejor la efectividad de las diferentes campañas e iniciativas de suscripción para impulsar la participación y las conversiones.</p><p>**A partir de lo que aprenda, puede** hacer muchas cosas, como ajustar sus campañas de suscripción en función de los niveles de participación de su público destinatario.</p> |
