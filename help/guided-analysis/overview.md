---
title: Información general sobre el análisis guiado
description: Un método de análisis de datos en Customer Journey Analytics que permite a los equipos de productos obtener información de alta calidad rápidamente.
keywords: Product Analytics
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: a7545c5a197bd318212328ef6344245b2026d401
workflow-type: tm+mt
source-wordcount: '1393'
ht-degree: 72%

---

# Información general sobre el análisis guiado

El análisis guiado permite a los usuarios, desde marketing hasta productos y analistas, ofrecer datos de alta calidad y perspectivas sobre el recorrido del cliente a través de flujos de trabajo guiados, basados en los datos de canales cruzados de Customer Journey Analytics. Al igual que Analysis Workspace y los cuadros de resultados para móviles, el análisis guiado utiliza datos de una [Vista de datos](/help/data-views/data-views.md), que hace referencia a los datos en Adobe Experience Platform a través de una [Conexión](../connections/overview.md). Muchos informes creados en análisis guiados se pueden transferir sin problemas a Analysis Workspace para realizar investigaciones adicionales.

Los siguientes análisis guiados están disponibles:

| Icono | Análisis | Descripción |
| :----:|--- | --- |
| ![GrupoPersonas](/help/assets/icons/PeopleGroup.svg) | [Crecimiento activo](types/active-growth.md) | Identifique quién es nuevo, retenido, retornado o inactivo. |
| ![Tendencias de conversión](/help/assets/icons/ConversionTrends.svg) | [Tendencias de conversión](types/conversion-trends.md) | Haga un seguimiento de los cambios en las tasas de conversión a lo largo del tiempo. |
| ![Gráfico de participación](/help/assets/icons/EngagementGraph.svg) | [Participación](types/engagement.md) | Comprenda la amplitud y profundidad de la participación de la característica. |
| ![PrimerUso](/help/assets/icons/FirstUse.svg) | [Impacto de primer uso](types/first-use-impact.md) | Mida el impacto del uso de funciones por primera vez en indicadores clave. |
| ![Histograma](/help/assets/icons/Histogram.svg) | [Frecuencia](types/frequency.md) | Mida la participación en función de la frecuencia de uso. |
| ![Canal de conversión](/help/assets/icons/ConversionFunnel.svg) | [Canal](types/funnel.md) | Compare las tasas de conversión entre pasos. |
| ![NetGrowth](/help/assets/icons/NetGrowth.svg) | [Crecimiento neto](types/net-growth.md) | ¿Está ganando o perdiendo usuarios? |
| ![Versión](/help/assets/icons/Release.svg) | [Impacto de la versión](types/release-impact.md) | Compare el rendimiento en períodos iguales antes y después de la publicación. |
| ![Retención](/help/assets/icons/Retention.svg) | [Retención](types/retention.md) | Mida los hábitos de retorno continuo de sus usuarios. |
| ![Cronología](/help/assets/icons/Timeline.svg) | [Cronología](types/timeline.md) | Explore patrones en la actividad de la sesión. |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [Tendencias](types/trends.md) | Medir la participación del usuario a lo largo del tiempo. |



## Acceso

Puede acceder al análisis guiado desde la página principal del Customer Journey Analytics.

1. Seleccione **[!UICONTROL Análisis guiado]** de la página principal, que lo lleva directamente a la [vista Tendencias de uso](types/trends.md).

   ![Mosaico de página de aterrizaje](assets/landing-page-tile.png){style="border:1px solid gray"}

1. Seleccione **[!UICONTROL Crear nuevo]** para ver las diferentes opciones de vista y elegir un punto de partida diferente para su análisis.

   ![Creación de un nuevo modal](assets/create-new-modal.png){style="border:1px solid gray"}

También puede acceder al análisis guiado desde un proyecto de Analysis Workspace.

1. Seleccione **[!UICONTROL Proyecto en blanco]** de la página principal para crear un proyecto de Workspace vacío.

   ![Crear proyecto en blanco](assets/blank-project.png){style="border:1px solid gray"}

1. Seleccione ![Análisis guiado](/help/assets/icons/GuidedAnalysis.svg) **[!UICONTROL Análisis guiado]** en el carril izquierdo.

   ![Carril izquierdo de Workspace](assets/workspace-left-rail.png){style="border:1px solid gray"}

1. Arrastre cualquier nuevo análisis al lienzo de Workspace y, a continuación, seleccione **[!UICONTROL Crear]** para generar el análisis deseado (por ejemplo: **[!UICONTROL Crear tendencias]**). También puede arrastrar un análisis existente al lienzo de Workspace desde la sección **[!UICONTROL Guardado]**.

   ![Crear panel](assets/create-guided-analysis-panel.gif)

## Interfaz

La interfaz para el análisis guiado sigue un formato de pregunta y respuesta. Formule su pregunta en el carril de consulta y, a continuación, obtenga una respuesta con una perspectiva escrita, un gráfico y una tabla. A continuación, puede hacer la siguiente pregunta con los tipos de vista y la configuración de visualización.

El análisis guiado utiliza los siguientes elementos de la interfaz de usuario:

| Vista previa de la interfaz | Elemento de la IU | Descripción |
| --- | --- | --- |
| ![Carril de consulta](assets/query-rail.png){style="border:1px solid gray"} | Carril de consulta | Configure la &quot;pregunta&quot; seleccionando los componentes deseados (eventos, propiedades y segmentos) que componen un análisis. Las siguientes opciones están disponibles en todos los tipos de vista, con ajustes adicionales disponibles para cada vista. <ul><li>**Selector de análisis**: un menú desplegable que le permite cambiar a un nuevo tipo de análisis. Las selecciones de la consulta se mantienen dentro de los límites permitidos para el nuevo tipo de análisis.</li><li>**Eventos**: los eventos que desea medir. Cada tipo de vista impone límites diferentes en cuanto al número de eventos que se pueden configurar.</li><li>**Filtros**: Utilice el icono ![Filtro](assets/filter.png) de la sección Eventos o Segmentos para delimitar por dimensiones específicas. Cuando se selecciona una dimensión, están disponibles tanto los criterios de filtro estándar (como [!UICONTROL Es igual a], [!UICONTROL Contiene] o [!UICONTROL Termina con]) como los 1000 valores de dimensión principales.</li><li>**Contabilizado como**: método de contabilización que desea aplicar a los eventos seleccionados.</li><li>**Segmentos**: los segmentos que desea medir. Cada tipo de vista impone límites diferentes en cuanto al número de segmentos que se pueden configurar.</li></ul> |
| ![Gráfico](assets/chart.png){style="border:1px solid gray"} | Gráfico | Una visualización de los datos devueltos en función de los datos que haya introducido desde el carril de consulta y la configuración. La visualización que vea depende de la vista y la configuración encima del gráfico. El gráfico también incluye: <ul><li>**Herramientas**: pase el ratón sobre cualquier punto de los datos del gráfico para mostrar una herramienta con más información.</li><li>**Leyenda**: pase el ratón sobre la serie de leyendas del gráfico para ver las definiciones donde estén disponibles, centrarse en esa serie y ocultar temporalmente otras series. Oculte una serie de la leyenda haciendo clic en ella.</li><li>**Anotaciones**: las [anotaciones](../components/annotations/overview.md) aplicables son visibles entre la visualización y la leyenda. Se muestra como un ![icono de anotación](assets/annotation.png) en el color configurado de la anotación. Los tipos de vista que muestran datos a lo largo del tiempo colocan el ![icono de anotación](assets/annotation.png) bajo la fecha configurada o un intervalo de fechas. Los tipos de vista que no muestran datos a lo largo del tiempo muestran el ![icono de anotación](assets/annotation.png) en la esquina inferior derecha del gráfico.</li><li>**Seleccionar acciones**: expone las siguientes acciones disponibles al seleccionar cualquier punto de datos. Las opciones incluyen **Guardar segmento**.</li></ul> |
| ![Tabla](assets/table.png){style="border:1px solid gray"} | Tabla | Una representación en tabla de los datos devueltos en función de los datos introducidos desde el carril de consulta y la configuración. Las columnas de la tabla dependen del tipo de vista encima del gráfico. La tabla también incluye: <ul><li>**Seleccionar acciones**: oculta o expone una serie de gráficos alternando el icono ![Mostrar icono de ocultar](assets/hide-in-chart.png) en cada fila. Hay acciones adicionales disponibles al seleccionar el menú **[!UICONTROL Más]**. Las opciones incluyen **Guardar segmento**.</li></ul> |
| ![Configuración de visualización](assets/visualization-settings.png){style="border:1px solid gray"} | Configuración de visualización | Opciones situadas encima del gráfico que le permiten formular la siguiente pregunta y personalizar la forma en que el gráfico y la tabla devuelven los datos. Las siguientes opciones están disponibles en todos los tipos de vista, con ajustes adicionales disponibles para cada vista. <ul><li>**Configuración de gráfico**: ajuste lo que se muestra en el gráfico y en la tabla. Las opciones disponibles dependen de la vista seleccionada.</li><li>**Intervalo de fechas**: selector de calendario que le permite determinar el intervalo de fechas del análisis. También puede seleccionar un intervalo para las vistas de tendencias, como diario, semanal o mensual.</li><li>**Insights**: información contextual según el análisis que visualice. Esta información proporciona observaciones para el análisis actual. Si hay varias informaciones disponibles, puede verlas con las flechas a la derecha. Puede alternar la visibilidad de este cuadro utilizando el icono de bombilla en la parte superior derecha.</li></ul> |
| ![Menú](assets/menu.png){style="border:1px solid gray"} | Menú | Comandos en la parte superior derecha del análisis guiado que proporcionan acciones generales para el análisis.<ul><li>**Selector de vista de datos**: cambie la vista de datos que utiliza el análisis. Al cambiar la vista de datos, también cambian los componentes disponibles en el carril de consulta.</li><li>**Copiar vínculo**: copia un vínculo en el análisis del portapapeles. Se le solicitará que guarde antes de compartir.</li><li>**Compartir**: abre el modal de uso compartido, con más opciones para compartir con usuarios o grupos individuales. Puede compartir un análisis con otros usuarios o generar un vínculo para compartirlo con cualquiera.</li><li>**Guardar**: guarda el análisis. Si está guardando un nuevo análisis, aparecerá una ventana modal que solicita un nombre y una descripción.</li><li>**Guardar como**: guarda el análisis de forma independiente del análisis actual y crea una copia. Aparece una ventana modal que solicita un nuevo nombre y descripción.</li><li>**Exportar a Workspace**: vuelve a crear la consulta de análisis guiado actual en Analysis Workspace. El proyecto de Workspace se crea en una nueva pestaña, lo que evita la interrupción mientras se trabaja dentro del análisis guiado. Es una copia del análisis y no permanece sincronizado con el análisis guiado original una vez abierto. Utilice este comando cuando desee transferir datos a su equipo de analistas o profundizar en los datos más de lo que permite el análisis guiado.</li><li>**Copiar en el portapapeles**: copia el gráfico del gráfico en el portapapeles para pegarlo en otras aplicaciones. El carril de consulta y la tabla no se incluyen en el gráfico.</li><li>**Descargar PNG**: descarga el gráfico del gráfico como `.png`. El carril de consulta y la tabla no se incluyen en el gráfico.</li><li>**Descargar CSV**: descarga los datos de tabla como un `.csv`. El carril de consulta y el gráfico no se incluyen en el archivo.</li></ul> |

{style="table-layout:auto"}

## Aprovisionamiento

Los análisis guiados se incluyen en los paquetes de Customer Journey Analytics de la siguiente manera:

| Paquete | Análisis disponibles |
| --- | --- |
| [!UICONTROL complementos de Customer Journey Analytics] | Crecimiento activo, Tendencias de conversión, Frecuencia, Canal, Crecimiento neto, Retención, Tendencias |
| [!UICONTROL Fundamento de Customer Journey Analytics] | Tendencias |
| [!UICONTROL Selección de Customer Journey Analytics] | Vistas de base + Crecimiento activo, Tendencias de conversión, Frecuencia, Canal, Crecimiento neto, Retención |
| [!UICONTROL Customer Journey Analytics Prime] | Seleccionar vistas + Participación, Impacto del primer uso, Impacto de la versión, Cronología |
| [!UICONTROL Customer Journey Analytics Ultimate] | Vistas de Prime |

{style="table-layout:auto"}

Los administradores del perfil del producto pueden añadir o quitar el acceso al análisis guiado en Adobe Admin Console.

1. Inicie sesión en [Adobe Admin Console](https://adminconsole.adobe.com).
1. Seleccione **[!UICONTROL Customer Journey Analytics]** en la lista de productos.
1. Seleccione el perfil de producto que desee para los permisos que desee editar.
1. Seleccione la ficha **[!UICONTROL Permisos]** y haga clic en **[!UICONTROL Editar]** en [!UICONTROL Herramientas de informes].
1. Seleccione ![AddCircle](/help/assets/icons/AddCircle.svg) junto a **[!UICONTROL Acceso guiado al análisis]** en la lista de [!UICONTROL Elementos de permisos disponibles], que lo agrega a la lista de [!UICONTROL Elementos de permisos incluidos].
1. Seleccione **[!UICONTROL Guardar]**.

Consulte [Acceso de nivel de usuario](/help/technotes/access-control.md#user-level-access) para obtener más información.

>[!TIP]
>
>Algunos administradores prefieren habilitar el análisis guiado y deshabilitar Analysis Workspace para nuevos usuarios en Customer Journey Analytics. Una vez que estos usuarios hayan madurado con el producto y los datos de su organización, puede habilitar el acceso a Analysis Workspace.
