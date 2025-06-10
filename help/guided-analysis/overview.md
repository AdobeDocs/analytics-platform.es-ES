---
title: Información general sobre el análisis guiado
description: 'Un método de análisis de datos en Customer Journey Analytics que permite a los equipos de productos obtener información de alta calidad rápidamente. '
keywords: Product Analytics
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '1849'
ht-degree: 97%

---

# Información general sobre el análisis guiado

El análisis guiado permite a los usuarios, desde el marketing hasta el producto, pasando por los analistas, autoabastecerse de datos e información de alta calidad sobre el recorrido del cliente mediante flujos de trabajo guiados, basados en los datos en canales múltiples de Customer Journey Analytics. Al igual que Analysis Workspace y los cuadros de resultados para móviles, el análisis guiado utiliza datos de una [Vista de datos](/help/data-views/data-views.md), que hace referencia a los datos en Adobe Experience Platform a través de una [Conexión](../connections/overview.md). Muchos informes creados en análisis guiados se pueden transferir sin problemas a Analysis Workspace para realizar investigaciones adicionales.

Están disponibles los siguientes análisis guiados: 

| Icono | Análisis | Descripción |
| :----:|--- | --- |
| ![GrupoPersonas](/help/assets/icons/PeopleGroup.svg) | [Crecimiento activo](types/active-growth.md) | Identifique quién es nuevo, retenido, retornado o inactivo. |
| ![TendenciasConversión](/help/assets/icons/ConversionTrends.svg) | [Tendencias de conversión](types/conversion-trends.md) | Haga un seguimiento de los cambios en las tasas de conversión a lo largo del tiempo. |
| ![GráficoParticipación](/help/assets/icons/EngagementGraph.svg) | [Participación](types/engagement.md) | Comprenda la amplitud y profundidad de la participación de la característica. |
| ![PrimerUso](/help/assets/icons/FirstUse.svg) | [Impacto del primer uso](types/first-use-impact.md) | Mida el impacto del uso de funciones por primera vez en indicadores clave. |
| ![Histograma](/help/assets/icons/Histogram.svg) | [Frecuencia](types/frequency.md) | Mida la participación en función de la frecuencia de uso. |
| ![Canal de conversión](/help/assets/icons/ConversionFunnel.svg) | [Canal](types/funnel.md) | Compare las tasas de conversión entre pasos. |
| ![CrecimientoNeto](/help/assets/icons/NetGrowth.svg) | [Crecimiento neto](types/net-growth.md) | ¿Está ganando o perdiendo usuarios? |
| ![Versión](/help/assets/icons/Release.svg) | [Impacto de versión](types/release-impact.md) | Compare el rendimiento en períodos iguales antes y después de la publicación. |
| ![Retención](/help/assets/icons/Retention.svg) | [Retención](types/retention.md) | Mida los hábitos de retorno continuo de sus usuarios. |
| ![Cronología](/help/assets/icons/Timeline.svg) | [Cronología](types/timeline.md) | Explore patrones en la actividad de la sesión. |
| ![TendenciaGráfico](/help/assets/icons/GraphTrend.svg) | [Tendencias](types/trends.md) | Mida la participación del usuario a lo largo del tiempo. |



## Acceso

Puede acceder al análisis guiado desde la página principal de Customer Journey Analytics.

1. Seleccione **[!UICONTROL Análisis guiado]** en la página de inicio, que le llevará directamente al [Análisis de tendencias](types/trends.md).

   ![Mosaico de página de aterrizaje](assets/landing-page-tile.png){style="border:1px solid gray"}

1. Haz clic en **[!UICONTROL Crear nuevo]** para ver las distintas opciones de vista y elegir un punto de partida diferente para tu análisis.

   ![Creación de un nuevo modal](assets/create-new-modal.png){style="border:1px solid gray"}

También puede acceder al análisis guiado desde un proyecto de Analysis Workspace.

1. Selecciona **[!UICONTROL Proyecto en blanco]** de la página principal para crear un proyecto de Workspace vacío.

   ![Crear un proyecto en blanco](assets/blank-project.png){style="border:1px solid gray"}

1. Selecciona ![Análisis guiado](/help/assets/icons/GuidedAnalysis.svg) **[!UICONTROL Análisis guiado]** en el panel izquierdo.

   ![Panel izquierdo de Workspace](assets/workspace-left-rail.png){style="border:1px solid gray"}

1. Arrastre cualquier nuevo análisis al lienzo de Workspace y, a continuación, seleccione **[!UICONTROL Crear]** para generar el análisis deseado (por ejemplo: **[!UICONTROL Crear tendencias]**). También puedes arrastrar un análisis existente al lienzo de Workspace desde la sección **[!UICONTROL Guardado]**.

   ![Crear panel](assets/create-guided-analysis-panel.gif)

## Interfaz

La interfaz para el análisis guiado sigue un formato de pregunta y respuesta. Formule su pregunta en el carril de consulta y, a continuación, obtenga una respuesta con una perspectiva escrita, un gráfico y una tabla. A continuación, puede hacer la siguiente pregunta con la configuración de análisis y visualización.

El análisis guiado utiliza los siguientes elementos de la interfaz de usuario:

| Vista previa de la interfaz | Elemento de la IU | Descripción |
| --- | --- | --- |
| ![Carril de consulta](assets/query-rail.png){style="border:1px solid gray"} | **[!UICONTROL Carril de consulta]** | Configure la *pregunta* seleccionando los componentes deseados (eventos, propiedades y segmentos) que componen un análisis. Las siguientes opciones están disponibles en todos los análisis, con ajustes adicionales disponibles para cada vista. <ul><li>**Vista**: seleccione entre las opciones para cambiar a un nuevo análisis. Las selecciones de la consulta se mantienen dentro de los límites permitidos para el nuevo análisis.</li><li>**Eventos**: los eventos que desea medir. Cada análisis impone límites diferentes en cuanto al número de eventos que se pueden configurar. Los eventos a veces se etiquetan como **[!UICONTROL Eventos start y return]**, **[!UICONTROL Pasos]** o **[!UICONTROL Indicadores clave]**. Los eventos se identifican en el análisis usando 1, 2, ...<br/>Seleccione ![Añadir](/help/assets/icons/Add.svg) **[!UICONTROL Añadir un evento]** para añadir nuevos eventos.</li><li>**[!UICONTROL Factores]**: si están disponibles, permiten especificar factores como la fecha desde y el primer evento.</li><li>**Contabilizado como**: método de contabilización que desea aplicar a los eventos seleccionados. Seleccione en el menú desplegable.</li><li>**Segmentos**: los segmentos que desea medir. Cada tipo de vista impone límites diferentes en cuanto al número de segmentos que se pueden configurar. Los segmentos se identifican en el análisis mediante A, B, ...<br/>Seleccione ![Añadir](/help/assets/icons/Add.svg) **[!UICONTROL Añadir un segmento]** para añadir nuevos segmentos.</li><li>**[!UICONTROL Desglose]**: si está disponible, el desglose que desee aplicar al análisis.</li></ul>En algunas de las opciones, hay disponible una configuración adicional.<ul><li>**Filtros**: Use ![Filtrar](assets/filter.png) para reducir eventos o segmentos por dimensiones específicas. Cuando se selecciona una propiedad, ambos criterios de filtro estándar (como **[!UICONTROL Igual a]**, **[!UICONTROL Contiene]** o **[!UICONTROL Termina con]**) y los 1000 valores de dimensión más altos están disponibles.<br/>Seleccione ![Filtro](/help/assets/icons/Filter.svg) para añadir filtros adicionales.<br/>Seleccione ![Quitar](/help/assets/icons/Remove.svg) para quitar un filtro.</li><li>**Más acciones**: use ![Más](/help/assets/icons/More.svg) para seleccionar acciones, como<ul><li>![Cambiar nombre](/help/assets/icons/Rename.svg) **[!UICONTROL Cambiar nombre]**: para cambiar el nombre de un evento o segmento.</li><li>![Duplicar](/help/assets/icons/Duplicate.svg) **[!UICONTROL Duplicar]**: para duplicar un evento o segmento.</li><li>![Eliminar](/help/assets/icons/Delete.svg) **[!UICONTROL Eliminar]**: para eliminar un evento, segmento o desglose.</li><li>![Editar segmento](/help/assets/icons/Edit.svg) **[!UICONTROL Editar segmento]**: para editar un segmento en el [Generador de segmentos](/help/components/segments/seg-builder.md).</li><li>![Estrella](/help/assets/icons/Star.svg) **[!UICONTROL Agregar a favoritos]**: para agregar el segmento a la lista de segmentos favoritos en el [Administrador de segmentos](/help/components/segments/seg-manage.md).</li><li>![SaveAsFloppy](/help/assets/icons/SaveAsFloppy.svg) **[!UICONTROL Guardar como]**: para guardar el segmento como un componente nuevo. En el cuadro de diálogo **[!UICONTROL Guardar segmentos en componentes]**, puede especificar un nombre de segmento y una descripción. Puede seleccionar ![StarOutline](/help/assets/icons/StarOutline.svg) para marcar el nuevo segmento como favorito. Seleccione **[!UICONTROL Guardar]** para guardar el segmento como un nuevo segmento.</li><li>![Vincular](/help/assets/icons/Link.svg) **[!UICONTROL Vincular eventos de inicio y retorno]**.: para vincular eventos de inicio y retorno en un análisis de [Retención](types/retention.md).</li><li>![Desvincular](/help/assets/icons/Unlink.svg) **[!UICONTROL Desvincular eventos de inicio y retorno]**: para desvincular eventos de inicio y retorno en un análisis de [Retención](types/retention.md).</li></ul></li></ul> |
| ![Gráfico](assets/chart.png){style="border:1px solid gray"} | **[!UICONTROL Gráfico]** | Una visualización de los datos devueltos en función de los datos que haya introducido desde el carril de consulta y la configuración. La visualización que vea depende de la vista y la configuración encima del gráfico. El gráfico también incluye: <ul><li>**Herramientas**: pase el puntero por encima de cualquier punto de los datos del gráfico para mostrar una herramienta con más información.</li><li>**Leyenda**: pase el puntero por encima de la serie de leyendas del gráfico para ver las definiciones donde estén disponibles, centrarse en esa serie y ocultar temporalmente otras series. Seleccione una serie de la leyenda para ocultarla.</li><li>**Anotaciones**: las [anotaciones](../components/annotations/overview.md) aplicables son visibles entre la visualización y la leyenda. Se muestra como un ![icono de anotación](assets/annotation.png) en el color configurado de la anotación. Los análisis que muestran datos a lo largo del tiempo colocan el ![icono de anotación](assets/annotation.png) bajo la fecha configurada o un intervalo de fechas. Los análisis que no muestran datos a lo largo del tiempo muestran el ![icono de anotación](assets/annotation.png) en la esquina inferior derecha del gráfico.</li><li>**Seleccionar acciones**: Exponga las siguientes acciones disponibles seleccionando cualquier punto de datos. Las opciones incluyen **Guardar segmento**.</li></ul> |
| ![Tabla](assets/table.png){style="border:1px solid gray"} | **[!UICONTROL Tabla]** | Una representación en tabla de los datos devueltos en función de los datos introducidos desde el carril de consulta y la configuración. Filas en la tabla que utilizan identificadores de evento (1, 2, ...) y de segmento (A, B, ...) como referencia. Las columnas de la tabla dependen del análisis encima del gráfico. La tabla también incluye para cada fila: <ul><li>**Seleccionar acciones**: alternar ![Mostrar icono de ocultar](assets/hide-in-chart.png) para ocultar o exponer una serie de gráficos para una fila. Seleccione ![Más](/help/assets/icons/More.svg) para realizar acciones adicionales. Las opciones incluyen **Guardar segmento**.</li></ul> |
| ![Configuración de visualización](assets/visualization-settings.png){style="border:1px solid gray"} | **[!UICONTROL Configuración de visualización]** | Opciones situadas encima del gráfico que le permiten formular la siguiente pregunta y personalizar la forma en que el gráfico y la tabla devuelven los datos. Las siguientes opciones están disponibles en todos los análisis, con ajustes adicionales disponibles para cada análisis. <ul><li>![Tendencia del gráfico](/help/assets/icons/GraphTrend.svg) **Configuración del gráfico**: Ajuste con precisión lo que muestran su gráfico y su tabla. Las opciones disponibles dependen del análisis seleccionado.</li><li>![Capa](/help/assets/icons/Layer.svg) **Configuración de superposición**: añadir una superposición. Las opciones disponibles dependen del análisis seleccionado.</li><li>![Cubo](/help/assets/icons/Bucket.svg) **[!UICONTROL Configuración del cubo]**: cubo automático o aplicar la configuración personalizada de cubo a los datos. Las opciones disponibles dependen del análisis seleccionado.<li>![DataCorrelated](/help/assets/icons/DataCorrelated.svg) **[!UICONTROL Comparar configuración]**: comparar datos con un intervalo de fechas específico. Las opciones disponibles dependen del análisis seleccionado.</li><li>![Pasos](/help/assets/icons/Footsteps.svg) **[!UICONTROL Configuración de visualización]**: seleccionar cómo mostrar los datos. Las opciones disponibles dependen del análisis seleccionado.<li>![Calendario](/help/assets/icons/Calendar.svg) **Intervalo de fechas**: un selector de calendario que le permite determinar el intervalo de fechas del análisis. También puede seleccionar un intervalo para los análisis de tendencias, como diario, semanal o mensual.</li><li>**Información** de ![LightBulb](/help/assets/icons/LightBulb.svg): información contextual según el análisis que visualice. Esta información proporciona observaciones para el análisis actual. Si hay varias informaciones disponibles, puede verlas con las flechas a la derecha. Puede alternar la visibilidad de este cuadro utilizando el icono de bombilla en la parte superior derecha.</li></ul> |
| ![Icono de menú](assets/menu.png){style="border:1px solid gray"} | **[!UICONTROL Menú]**<br/>Disponible en un proyecto de análisis guiado | Comandos en la parte superior derecha del proyecto de análisis guiado que proporcionan acciones generales para el análisis.<ul><li>![Icono de datos](/help/assets/icons/Data.svg) ***Nombre de la vista de datos***: cambie la vista de datos que el análisis utiliza. Al cambiar la vista de datos, también cambian los componentes disponibles en el carril de consulta.</li><li>![Icono de vínculo](/help/assets/icons/Link.svg) **Copiar vínculo**: copia un vínculo en el análisis en el portapapeles. Se le solicitará que guarde antes de compartir.</li><li>**Compartir**: abre el modal de uso compartido, con más opciones para compartir con usuarios o grupos individuales. Puede compartir un análisis con otros usuarios o generar un vínculo para compartirlo con cualquiera.</li><li>**Guardar**: guarda el análisis. Si guarda un nuevo análisis, aparece el cuadro de diálogo **[!UICONTROL Guardar análisis]** que solicita un nombre y una descripción. Una vez guardado, un cuadro de diálogo **[!UICONTROL Análisis guardado]** le permite compartir su análisis.</li><li>![Icono Añadir a Workspace](/help/assets/icons/MultipleAdd.svg) **[!UICONTROL Añadir a Workspace]**: muestra los proyectos de Workspace disponibles a los que puede añadir este análisis. Al seleccionar un proyecto de Workspace, se abre ese proyecto de Workspace en una nueva pestaña y se añade el análisis en la parte inferior del proyecto.</li></ul>Seleccione el icono ![Más](/help/assets/icons/More.svg) para obtener más acciones, como:<ul><li>**[!UICONTROL Guardar como]**: guarda el análisis de forma independiente del análisis actual y crea una copia. Aparece un cuadro de diálogo que solicita un nuevo nombre y una nueva descripción.</li><li>**[!UICONTROL Exportar a Workspace]**: Recrea la consulta de análisis guiado actual en Analysis Workspace. El proyecto de Workspace se crea en una nueva pestaña, lo que evita la interrupción mientras se trabaja dentro del análisis guiado. Es una copia del análisis y no permanece sincronizado con el análisis original una vez abierto. Utilice este comando cuando desee transferir datos a su equipo de analistas o profundizar en los datos más de lo que permite el análisis.</li><li>**[!UICONTROL Copiar gráfico en el portapapeles]**: copia el gráfico en el portapapeles para pegarlo en otras aplicaciones. El carril de consulta y la tabla no se incluyen en el gráfico.</li><li>**[!UICONTROL Descargar PNG]**: descarga el gráfico del gráfico como `.png`. El carril de consulta y la tabla no se incluyen en el gráfico.</li><li>**[!UICONTROL Descargar CSV]**: descarga los datos de tabla como un `.csv`. El carril de consulta y el gráfico no se incluyen en el archivo.</li></ul> |
| ![Visualización de menú](assets/menu-visualization.png){style="border:1px solid gray"} | **Menú**<br/> Disponible en una visualización de análisis guiado en Analysis Workspace. | Comandos en una visualización de análisis guiado en Analysis Workspace.<ul><li>**[!UICONTROL Gráfico]** de ![GraphScatter](/help/assets/icons/GraphScatter.svg): para mostrar solo el gráfico del análisis.</li><li>![Tabla](/help/assets/icons/Table.svg) **[!UICONTROL Tabla]**: para mostrar solamente la tabla del análisis.</li><li>![TableAndChart](/help/assets/icons/TableAndChart.svg) **[!UICONTROL Todo]**: para mostrar el gráfico y la tabla del análisis.</li><li>![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]**: para editar la configuración del análisis</li><li>![Calendario](/help/assets/icons/Calendar.svg) **[!UICONTROL *Intervalo de fechas *]**: para configurar el intervalo de fechas para el análisis.</li></ul> |


## Aprovisionamiento

Los análisis guiados se incluyen en los paquetes de Customer Journey Analytics de la siguiente manera:

| Paquete | Análisis disponibles |
| --- | --- |
| [!UICONTROL Complementos de Customer Journey Analytics] | Crecimiento activo, Tendencias de conversión, Frecuencia, Canal, Crecimiento neto, Retención, Tendencias |
| [!UICONTROL Customer Journey Analytics Foundation] | Tendencias |
| [!UICONTROL Customer Journey Analytics Select] | Vistas de base + Crecimiento activo, Tendencias de conversión, Frecuencia, Canal, Crecimiento neto, Retención |
| [!UICONTROL Customer Journey Analytics Prime] | Seleccionar vistas + Participación, Impacto del primer uso, Impacto de la versión, Cronología |
| [!UICONTROL Customer Journey Analytics Ultimate] | Vistas de Prime |

{style="table-layout:auto"}

Los administradores del perfil del producto pueden añadir o quitar el acceso al análisis guiado en Adobe Admin Console.

1. Inicie sesión en [Adobe Admin Console](https://adminconsole.adobe.com).
1. Seleccione **[!UICONTROL Customer Journey Analytics]** en la lista de productos.
1. Seleccione el perfil de producto que desee para los permisos que desee editar.
1. Seleccione la pestaña **[!UICONTROL Permisos]** y, a continuación, haga clic en **[!UICONTROL Editar]** dentro de [!UICONTROL Herramientas de informe].
1. Seleccione ![AddCircle](/help/assets/icons/AddCircle.svg) junto a **[!UICONTROL Acceso guiado a análisis]** en la lista de [!UICONTROL Permisos disponibles], lo que lo añade a la lista de [!UICONTROL Permisos incluidos].
1. Seleccione **[!UICONTROL Guardar]**.

Consulte [Acceso a nivel de usuario](/help/technotes/access-control.md#user-level-access) para obtener más información.

>[!TIP]
>
>Algunos administradores prefieren habilitar el análisis guiado y deshabilitar Analysis Workspace para nuevos usuarios en Customer Journey Analytics. Una vez que estos usuarios hayan madurado con el producto y los datos de su organización, puede habilitar el acceso a Analysis Workspace.
