---
title: Información general sobre el análisis guiado
description: Un método de análisis de datos en Customer Journey Analytics que permite a los equipos de productos obtener información de alta calidad rápidamente. También se denomina Product Analytics.
keywords: análisis de productos
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: feb7b6afc56398cffa1ef4d981512c09e977376a
workflow-type: tm+mt
source-wordcount: '1367'
ht-degree: 2%

---

# Información general sobre el análisis guiado

El análisis guiado permite a los usuarios ofrecer datos de alta calidad y perspectivas sobre el recorrido del cliente a través de flujos de trabajo guiados, basados en los datos de canales cruzados de Customer Journey Analytics. Los equipos interfuncionales, desde el marketing hasta el producto, pueden conectarse en tiempo real para utilizar y comprender estos informes.

>[!NOTE]
>
> Actualmente, el análisis guiado solo está disponible como parte de Adobe Product Analytics, que es un complemento de pago para Customer Journey Analytics. Si su organización desea empezar a utilizar este conjunto de funcionalidades, póngase en contacto con su equipo de cuenta de Adobe.

Al igual que los cuadros de resultados de Analysis Workspace y Mobile, el análisis guiado utiliza datos de un [Vista de datos](../data-views/data-views.md), que hace referencia a los datos en Adobe Experience Platform a través de una [Conexión](../connections/overview.md). Muchos informes creados en Guided analysis pueden transferirse sin problemas a Analysis Workspace para realizar investigaciones adicionales.

Las siguientes vistas de análisis guiado están disponibles:

| Tipo de análisis | Ver tipo | Descripción |
| --- | --- | --- |
| [!UICONTROL Embudo] | [Fricción](types/friction.md) | Compare las tasas de conversión entre pasos. |
| [!UICONTROL Embudo] | [Tendencias de conversión](types/conversion-trends.md) | Rastree los cambios en las tasas de conversión a lo largo del tiempo. |
| [!UICONTROL Impacto] | [Versión](types/release.md) | Compare el rendimiento en periodos iguales antes y después del lanzamiento. |
| [!UICONTROL Impacto] | [Primer uso](types/first-use.md) | Mida el impacto del uso de la primera función en los indicadores clave. |
| [!UICONTROL Retención] | [Tasas de retención](types/retention-rates.md) | Mida los hábitos de retorno continuos de los usuarios. |
| [!UICONTROL Tendencias] | [Uso](types/usage.md) | Mida la participación del usuario con el tiempo. |
| [!UICONTROL Tendencias] | [Frecuencia](types/frequency.md) | Mida la participación por frecuencia de uso. |
| [!UICONTROL Crecimiento de usuarios] | [Activo](types/active.md) | Identifique quién es nuevo, retenido, que regresa o está inactivo. |
| [!UICONTROL Crecimiento de usuarios] | [Crecimiento neto](types/net-growth.md) | ¿Está ganando o perdiendo usuarios? |
| [!UICONTROL Flujo de usuario] | [Cronología](types/timeline.md) | Explore los patrones de actividad de la sesión. |

{style="table-layout:auto"}

## Acceso

Si su organización está aprovisionada para el análisis guiado, puede acceder a ella desde la página principal del Customer Journey Analytics.

1. Clic **[!UICONTROL Análisis guiado]** desde la página de inicio, que le lleva directamente a [Vista de tendencias de uso](types/usage.md).

   ![Mosaico de página de aterrizaje](assets/landing-page-tile.png)

1. Clic **[!UICONTROL Crear nuevo]** para ver las distintas opciones de vista y elegir un punto de partida diferente para el análisis.

   ![Crear un nuevo modal](assets/create-new-modal.png)

Si su organización aún no se ha aprovisionado para el análisis guiado, póngase en contacto con el equipo de cuenta de Adobe.

## Interfaz

La interfaz para el análisis guiado sigue un formato de pregunta y respuesta. Forme su pregunta en el carril de consulta y, a continuación, obtenga una respuesta con una perspectiva escrita, un gráfico y una tabla. A continuación, puede hacer la siguiente pregunta con los tipos de vista y la configuración de visualización.

El análisis guiado utiliza los siguientes elementos de la interfaz de usuario:

| Previsualización de interfaz | Elemento de la IU | Descripción |
| --- | --- | --- |
| ![Carril de consulta](assets/query-rail.png) | Carril de consulta | Configure la &quot;pregunta&quot; seleccionando los componentes deseados (eventos, propiedades y segmentos) que componen un análisis. Las siguientes opciones están disponibles en todos los tipos de vista, con ajustes adicionales disponibles por vista. <ul><li>**Selector de análisis**: Un menú desplegable que le permite cambiar a un nuevo tipo de análisis. Las selecciones de consulta se mantienen dentro de los límites permitidos para el nuevo tipo de análisis.</li><li>**Selector de vista**: Una lista desplegable que le permite cambiar a una nueva vista (&quot;respuesta&quot;) para la consulta que ha formado. Las selecciones de consulta se mantienen dentro de los límites permitidos para el nuevo tipo de vista.</li><li>**Eventos**: los eventos que desea medir. Cada tipo de vista impone límites diferentes al número de eventos que se pueden configurar.</li><li>**Filtros**: utilice el icono de filtro de la sección Eventos o Segmentos para delimitar por propiedades específicas. Una vez seleccionada una propiedad, además de los criterios de filtro estándar como es igual a, contiene y termina con, hay disponible una lista de los 1000 valores de propiedad principales para filtrar rápidamente.</li><li>**Contabilizado como**: método de contabilización que desea aplicar a los eventos seleccionados.</li><li>**Segmentos**: Los segmentos que desea medir. Cada tipo de vista impone límites diferentes al número de segmentos que se pueden configurar.</li></ul> |
| ![Gráfico](assets/chart.png) | Gráfico | Una visualización de los datos devueltos en función de los datos que haya introducido desde el carril de consulta y la configuración. La visualización que vea depende de la vista y la configuración encima del gráfico. El gráfico también incluye: <ul><li>**Tooltips**: Pase el ratón sobre cualquier punto de datos del gráfico para exponer una información del objeto con más información.</li><li>**Leyenda**: Pase el ratón sobre la serie de leyendas del gráfico para ver las definiciones donde estén disponibles, centrarse en esa serie y ocultar temporalmente otras series. Oculte una serie de la leyenda haciendo clic en ella.</li><li>**Anotaciones**: aplicable [anotaciones](../components/annotations/overview.md) son visibles entre la visualización y la leyenda. Se muestra como una ![Icono de anotación](assets/annotation.png) en el color configurado de la anotación. Los tipos de vista que muestran datos a lo largo del tiempo colocan la variable ![Icono de anotación](assets/annotation.png) bajo la fecha configurada o el intervalo de fechas. Los tipos de vista que no muestran datos a lo largo del tiempo muestran la variable ![Icono de anotación](assets/annotation.png) en la esquina inferior derecha del gráfico.</li><li>**Acciones de clic**: Exponga las acciones siguientes disponibles haciendo clic con el botón izquierdo en cualquier punto de datos. Las opciones incluyen **Guardar segmento**.</li></ul> |
| ![Tabla](assets/table.png) | Tabla | Una representación en tabla de los datos devueltos en función de los datos introducidos desde el carril de consulta y la configuración. Las columnas de la tabla dependen del tipo de vista encima del gráfico. La tabla también incluye: <ul><li>**Acciones de clic**: oculte o exponga una serie de gráficos alternando el ![Mostrar icono de ocultar](assets/hide-in-chart.png) en cada fila. Para realizar acciones adicionales, haga clic en **[!UICONTROL Más]** menú. Las opciones incluyen **Guardar segmento**.</li></ul> |
| ![Configuración de visualización](assets/visualization-settings.png) | Configuración de visualización | Opciones encima del gráfico que le permiten hacer la siguiente pregunta y personalizar cómo devuelven datos el gráfico y la tabla. Las siguientes opciones están disponibles en todos los tipos de vista, con ajustes adicionales disponibles por vista. <ul><li>**Configuración de gráfico**: Ajuste lo que se muestra en el gráfico y en la tabla. Las opciones disponibles dependen de la vista seleccionada.</li><li>**Intervalo de fechas**: Selector de calendario que le permite determinar el intervalo de fechas del análisis. También puede seleccionar un intervalo para las vistas de tendencias, como diaria, semanal o mensual.</li><li>**Insights**: Perspectivas contextuales según el análisis que visualice. Puede acceder a perspectivas adicionales mediante las flechas o mostrar u ocultar estas perspectivas mediante el icono de la bombilla en la parte superior derecha.</li></ul> |
| ![Menú](assets/menu.png) | Menú | Comandos en la parte superior derecha del análisis guiado que proporcionan acciones generales para el análisis.<ul><li>**Selector de vista de datos**: cambie la vista de datos que utiliza el análisis. Al cambiar la vista de datos, también cambian los componentes disponibles en el carril de consulta.</li><li>**Copiar vínculo**: copia un vínculo al análisis en el portapapeles. Se le pedirá que guarde antes de compartir.</li><li>**Compartir**: abre el modal de uso compartido, con más opciones para compartir con usuarios o grupos individuales. Se le pedirá que guarde antes de compartir.</li><li>**Guardar**: guarda el análisis. Si está guardando un nuevo análisis, aparecerá una ventana modal que solicita un nombre y una descripción.</li><li>**Guardar como**: Guarda el análisis de forma independiente del análisis actual y crea una copia. Aparece una ventana modal que solicita un nuevo nombre y descripción.</li><li>**Abrir en Workspace**: vuelve a crear el análisis guiado actual en Analysis Workspace. El proyecto del Espacio de trabajo se crea en una nueva pestaña, lo que evita interrupciones mientras se trabaja dentro del análisis guiado. Es una copia del análisis y no permanece sincronizado con el análisis guiado original una vez abierto. Utilice este comando cuando desee transferir datos a su equipo de analistas o profundizar en los datos más de lo que permite el análisis guiado.</li><li>**Copiar al portapapeles**: copia el gráfico del gráfico en el portapapeles para pegarlo en otras aplicaciones. El carril de consulta y la tabla no se incluyen en el gráfico.</li><li>**Descargar PNG**: descarga el gráfico del gráfico como `.png`. El carril de consulta y la tabla no se incluyen en el gráfico.</li><li>**Descargar CSV**: descarga los datos de tabla como un `.csv`. El carril de consulta y el gráfico no se incluyen en el archivo.</li></ul> |

{style="table-layout:auto"}

## Aprovisionamiento

El análisis guiado forma parte de Adobe Product Analytics, que es un complemento de pago para Customer Journey Analytics. Si su organización desea empezar a utilizar este conjunto de funcionalidades, póngase en contacto con su equipo de cuenta de Adobe.

Una vez que su organización esté aprovisionada para utilizar el análisis guiado, los administradores de perfil de producto pueden agregar o eliminar el acceso a él en Adobe Admin Console.

1. Inicie sesión en [Adobe Admin Console](https://adminconsole.adobe.com).
1. Seleccionar **[!UICONTROL Customer Journey Analytics]** en la lista de productos.
1. Seleccione el perfil de producto que desee para los permisos que desee editar.
1. Haga clic en **[!UICONTROL Permisos]** y haga clic en **[!UICONTROL Editar]** bajo [!UICONTROL Herramientas de informes].
1. Haga clic en el icono de signo más situado junto a **[!UICONTROL Acceso guiado a análisis]** en lista de [!UICONTROL Elementos de permisos disponibles], que lo añade a la lista de [!UICONTROL Elementos de permisos incluidos].
1. Haga clic en **[!UICONTROL Guardar]**.

>[!TIP]
>
>Algunos administradores prefieren habilitar el análisis guiado y deshabilitar Analysis Workspace para los nuevos usuarios en Customer Journey Analytics. Una vez que estos usuarios hayan madurado con el producto y los datos de su organización, puede habilitar el acceso a Analysis Workspace.
