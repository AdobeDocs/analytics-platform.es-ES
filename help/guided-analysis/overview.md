---
title: Información general sobre el análisis guiado
description: Un método de análisis de datos en Customer Journey Analytics que permite a los equipos de productos obtener información de alta calidad rápidamente. También conocido como Product Analytics.
keywords: Product Analytics
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: a8ead81a8de8dcab4c12cbbe9cba56c4ce8417a3
workflow-type: ht
source-wordcount: '1360'
ht-degree: 100%

---

# Información general sobre el análisis guiado

El análisis guiado permite a los usuarios autogestionar los datos y las perspectivas de alta calidad sobre el recorrido del cliente mediante flujos de trabajo guiados, basados en los mismos datos entre canales de Customer Journey Analytics. Los equipos interfuncionales, desde el marketing hasta el producto, pueden conectarse en tiempo real para utilizar y comprender estos informes.

>[!NOTE]
>
> El análisis guiado solo está disponible actualmente como parte de Adobe Product Analytics, un complemento de pago de Customer Journey Analytics. Si su organización desea empezar a utilizar este conjunto de funciones, póngase en contacto con el equipo de cuentas de Adobe.

Al igual que Analysis Workspace y los cuadros de resultados para móviles, el análisis guiado utiliza datos de una [Vista de datos](../data-views/data-views.md), que hace referencia a los datos en Adobe Experience Platform a través de una [Conexión](../connections/overview.md). Muchos informes creados en análisis guiados se pueden transferir sin problemas a Analysis Workspace para realizar investigaciones adicionales.

Están disponibles las siguientes vistas de análisis guiado: 

| Tipo de análisis | Ver tipo | Descripción |
| --- | --- | --- |
| [!UICONTROL Canal] | [Fricción](types/friction.md) | Compare las tasas de conversión entre pasos. |
| [!UICONTROL Embudo] | [Tendencias de conversión](types/conversion-trends.md) | Haga un seguimiento de los cambios en las tasas de conversión a lo largo del tiempo. |
| [!UICONTROL Impacto] | [Versión](types/release.md) | Compare el rendimiento en períodos iguales antes y después de la publicación. |
| [!UICONTROL Impacto] | [Primer uso](types/first-use.md) | Mida el impacto del uso de funciones por primera vez en indicadores clave. |
| [!UICONTROL Retención] | [Tasas de retención](types/retention-rates.md) | Mida los hábitos de retorno continuo de sus usuarios. |
| [!UICONTROL Tendencias] | [Uso](types/usage.md) | Medir la participación del usuario a lo largo del tiempo. |
| [!UICONTROL Tendencias] | [Frecuencia](types/frequency.md) | Mida la participación en función de la frecuencia de uso. |
| [!UICONTROL Crecimiento de usuarios] | [Activo](types/active.md) | Identifique quién es nuevo, retenido, retornado o inactivo. |
| [!UICONTROL Crecimiento de usuarios] | [Crecimiento neto](types/net-growth.md) | ¿Está ganando o perdiendo usuarios? |
| [!UICONTROL Flujo de usuarios] | [Cronología](types/timeline.md) | Explore patrones en la actividad de la sesión. |

{style="table-layout:auto"}

## Acceso

Si su organización está aprovisionada para el análisis guiado, puede acceder a ella desde la página de inicio de Customer Journey Analytics.

1. Haga clic en **[!UICONTROL Análisis guiado]** en la página de inicio, que le lleva directamente a la [vista de tendencias de uso](types/usage.md).

   ![Mosaico de página de aterrizaje](assets/landing-page-tile.png){style="border:1px solid gray"}

1. Haga clic en **[!UICONTROL Crear nuevo]** para ver las distintas opciones de vista y elegir un punto de partida diferente para el análisis.

   ![Creación de un nuevo modal](assets/create-new-modal.png){style="border:1px solid gray"}

Si su organización aún no se ha aprovisionado para el análisis guiado, póngase en contacto con el equipo de cuentas de Adobe.

## Interfaz

La interfaz para el análisis guiado sigue un formato de pregunta y respuesta. Formule su pregunta en el carril de consulta y, a continuación, obtenga una respuesta con una perspectiva escrita, un gráfico y una tabla. A continuación, puede hacer la siguiente pregunta con los tipos de vista y la configuración de visualización.

El análisis guiado utiliza los siguientes elementos de la interfaz de usuario:

| Vista previa de la interfaz | Elemento de la IU | Descripción |
| --- | --- | --- |
| ![Carril de consulta](assets/query-rail.png){style="border:1px solid gray"} | Carril de consulta | Configure la &quot;pregunta&quot; seleccionando los componentes deseados (eventos, propiedades y segmentos) que componen un análisis. Las siguientes opciones están disponibles en todos los tipos de vista, con ajustes adicionales disponibles para cada vista. <ul><li>**Selector de análisis**: un menú desplegable que le permite cambiar a un nuevo tipo de análisis. Las selecciones de la consulta se mantienen dentro de los límites permitidos para el nuevo tipo de análisis.</li><li>**Selector de vista**: una lista desplegable que le permite cambiar a una nueva vista (“respuesta”) para la consulta que ha formado. Las selecciones de la consulta se mantienen dentro de los límites permitidos para el nuevo tipo de vista.</li><li>**Eventos**: los eventos que desea medir. Cada tipo de vista impone límites diferentes en cuanto al número de eventos que se pueden configurar.</li><li>**Filtros**: utilice el icono ![Filtrar](assets/filter.png) en la sección Eventos o Segmentos para delimitar por propiedades específicas. Cuando se selecciona una propiedad, ambos criterios de filtro estándar (como [!UICONTROL Es igual que], [!UICONTROL Contiene] o [!UICONTROL Termina por]) y los 1000 valores de propiedad principales están disponibles.</li><li>**Contabilizado como**: método de contabilización que desea aplicar a los eventos seleccionados.</li><li>**Segmentos**: los segmentos que desea medir. Cada tipo de vista impone límites diferentes en cuanto al número de segmentos que se pueden configurar.</li></ul> |
| ![Gráfico](assets/chart.png){style="border:1px solid gray"} | Gráfico | Una visualización de los datos devueltos en función de los datos que haya introducido desde el carril de consulta y la configuración. La visualización que vea depende de la vista y la configuración encima del gráfico. El gráfico también incluye: <ul><li>**Herramientas**: pase el ratón sobre cualquier punto de los datos del gráfico para mostrar una herramienta con más información.</li><li>**Leyenda**: pase el ratón sobre la serie de leyendas del gráfico para ver las definiciones donde estén disponibles, centrarse en esa serie y ocultar temporalmente otras series. Oculte una serie de la leyenda haciendo clic en ella.</li><li>**Anotaciones**: las [anotaciones](../components/annotations/overview.md) aplicables son visibles entre la visualización y la leyenda. Se muestra como un ![icono de anotación](assets/annotation.png) en el color configurado de la anotación. Los tipos de vista que muestran datos a lo largo del tiempo colocan el ![icono de anotación](assets/annotation.png) bajo la fecha configurada o un intervalo de fechas. Los tipos de vista que no muestran datos a lo largo del tiempo muestran el ![icono de anotación](assets/annotation.png) en la esquina inferior derecha del gráfico.</li><li>**Acciones de clic**: exponga las acciones siguientes disponibles haciendo clic con el botón izquierdo en cualquier punto de datos. Las opciones incluyen **Guardar segmento**.</li></ul> |
| ![Tabla](assets/table.png){style="border:1px solid gray"} | Tabla | Una representación en tabla de los datos devueltos en función de los datos introducidos desde el carril de consulta y la configuración. Las columnas de la tabla dependen del tipo de vista encima del gráfico. La tabla también incluye: <ul><li>**Acciones de clic**: oculte o exponga una serie de gráficos alternando el icono ![Mostrar/ocultar icono](assets/hide-in-chart.png) en cada fila. Para realizar más acciones, haga clic en el menú **[!UICONTROL Más]**. Las opciones incluyen **Guardar segmento**.</li></ul> |
| ![Configuración de visualización](assets/visualization-settings.png){style="border:1px solid gray"} | Configuración de visualización | Opciones situadas encima del gráfico que le permiten formular la siguiente pregunta y personalizar la forma en que el gráfico y la tabla devuelven los datos. Las siguientes opciones están disponibles en todos los tipos de vista, con ajustes adicionales disponibles para cada vista. <ul><li>**Configuración de gráfico**: ajuste lo que se muestra en el gráfico y en la tabla. Las opciones disponibles dependen de la vista seleccionada.</li><li>**Intervalo de fechas**: selector de calendario que le permite determinar el intervalo de fechas del análisis. También puede seleccionar un intervalo para las vistas de tendencias, como diario, semanal o mensual.</li><li>**Información**: información contextual según el análisis que visualice. Puede acceder a información adicional mediante las flechas o mostrar u ocultar esta información mediante el icono de bombilla en la parte superior derecha.</li></ul> |
| ![Menú](assets/menu.png){style="border:1px solid gray"} | Menú | Comandos en la parte superior derecha del análisis guiado que proporcionan acciones generales para el análisis.<ul><li>**Selector de vista de datos**: cambie la vista de datos que utiliza el análisis. Al cambiar la vista de datos, también cambian los componentes disponibles en el carril de consulta.</li><li>**Copiar vínculo**: copia un vínculo en el análisis del portapapeles. Se le solicitará que lo guarde antes de compartir.</li><li>**Compartir**: abre el modal de uso compartido, con más opciones para compartir con usuarios o grupos individuales. Se le solicitará que lo guarde antes de compartir.</li><li>**Guardar**: guarda el análisis. Si está guardando un nuevo análisis, aparecerá una ventana modal que solicita un nombre y una descripción.</li><li>**Guardar como**: guarda el análisis de forma independiente del análisis actual y crea una copia. Aparece una ventana modal que solicita un nuevo nombre y descripción.</li><li>**Abrir en Workspace**: vuelve a crear el análisis guiado actual en Analysis Workspace. El proyecto de Workspace se crea en una nueva pestaña, lo que evita la interrupción mientras se trabaja dentro del análisis guiado. Es una copia del análisis y no permanece sincronizado con el análisis guiado original una vez abierto. Utilice este comando cuando desee transferir datos a su equipo de analistas o profundizar en los datos más de lo que permite el análisis guiado.</li><li>**Copiar en el portapapeles**: copia el gráfico del gráfico en el portapapeles para pegarlo en otras aplicaciones. El carril de consulta y la tabla no se incluyen en el gráfico.</li><li>**Descargar PNG**: descarga el gráfico del gráfico como `.png`. El carril de consulta y la tabla no se incluyen en el gráfico.</li><li>**Descargar CSV**: descarga los datos de tabla como un `.csv`. El carril de consulta y el gráfico no se incluyen en el archivo.</li></ul> |

{style="table-layout:auto"}

## Aprovisionamiento

El análisis guiado forma parte de Adobe Product Analytics, que es un complemento de pago de Customer Journey Analytics. Si su organización desea empezar a utilizar este conjunto de funciones, póngase en contacto con el equipo de cuentas de Adobe.

Una vez que la organización esté aprovisionada para utilizar el análisis guiado, los administradores de perfil de producto pueden añadir o eliminar el acceso a él en Adobe Admin Console.

1. Inicie sesión en [Adobe Admin Console](https://adminconsole.adobe.com).
1. Seleccione **[!UICONTROL Customer Journey Analytics]** en la lista de productos.
1. Seleccione el perfil de producto que desee para los permisos que desee editar.
1. Haga clic en la pestaña **[!UICONTROL Permisos]**, a continuación haga clic en **[!UICONTROL Editar]** bajo [!UICONTROL Herramientas de creación de informes].
1. Haga clic en el icono de signo más situado junto al **[!UICONTROL Acceso a análisis guiado]** en la lista de [!UICONTROL Elementos de permiso disponibles], que lo añade a la lista de [!UICONTROL Elementos de permiso incluidos].
1. Haga clic en **[!UICONTROL Guardar]**.

>[!TIP]
>
>Algunos administradores prefieren habilitar el análisis guiado y deshabilitar Analysis Workspace para nuevos usuarios en Customer Journey Analytics. Una vez que estos usuarios hayan madurado con el producto y los datos de su organización, puede habilitar el acceso a Analysis Workspace.
