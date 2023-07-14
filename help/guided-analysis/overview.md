---
title: Información general sobre el análisis guiado
description: Un método de análisis de datos en Customer Journey Analytics que permite a los equipos de productos obtener información de alta calidad rápidamente.
exl-id: 6a8a92db-f030-424e-af9b-f8f6502084f6
feature: Guided Analysis
source-git-commit: cc76b4c3b03647f6e90f0b57f4d8c819caa8823f
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 8%

---

# Información general sobre el análisis guiado

{{release-limited-testing}}

El análisis guiado es un formato de informes que permite a los equipos de productos autoabastecer rápidamente sus necesidades de datos para que puedan obtener perspectivas de alta calidad rápidamente y tomar más decisiones de productos basadas en datos. Los equipos interfuncionales pueden conectarse en tiempo real para utilizar y comprender estos informes.

Al igual que los cuadros de resultados de Analysis Workspace y Mobile, un informe de análisis guiado utiliza datos de una [Vista de datos](../data-views/data-views.md), que hace referencia a los datos en Adobe Experience Platform a través de una [Conexión](../connections/overview.md). Todos los informes creados en Guided analysis pueden transferirse sin problemas a Analysis Workspace para realizar investigaciones adicionales.

El análisis guiado proporciona varias formas de analizar y ver datos. Los tipos de vista pueden mostrar los mismos datos de diferentes maneras, lo que conduce a perspectivas diferentes utilizando los mismos eventos y segmentos. Puede obtener diferentes carriles de consulta y configuraciones de visualización en función de la vista que elija. Puede alternar libremente entre vistas y cualquier componente del carril de consulta aplicable se transferirá si la vista los admite.

El análisis guiado clasifica los tipos de vista en **Tipos de análisis**. Están disponibles los siguientes tipos de análisis y vistas:

| Tipo de análisis | Ver tipo | Descripción |
| --- | --- | --- |
| Impacto | [Versión](types/release.md) | Comparar los resultados en periodos iguales antes y después de la liberación. |
| Impacto | [Primer uso](types/first-use.md) | Medir el impacto del uso de funciones por primera vez en indicadores clave. |
| Canal | [Fricción](types/friction.md) | Comparar tasas de conversión entre los pasos. |
| Canal | [Tendencias de conversión](types/conversion-trends.md) | Realizar un seguimiento de los cambios en las tasas de conversión a lo largo del tiempo. |
| Crecimiento de usuarios | [Activo](types/active.md) | Identifique quién es nuevo, retenido, que regresa o está inactivo. |
| Crecimiento de usuarios | [Crecimiento neto](types/net-growth.md) | ¿Está ganando o perdiendo usuarios? |
| Tendencias | [Uso](types/usage.md) | Medir la participación del usuario a lo largo del tiempo. |

{style="table-layout:auto"}

## Acceso

Si su organización está aprovisionada para el análisis guiado, se puede acceder a ella desde la página principal del Customer Journey Analytics.

Clic **Análisis guiado** desde la página de inicio para saltar directamente a [Vista de tendencias de uso](types/usage.md).

Clic **Crear nuevo** para ver las distintas opciones de vista y elegir un punto de partida diferente para el análisis.

## Interfaz

La interfaz para el análisis guiado, independientemente del tipo de análisis, consta de los siguientes elementos de la interfaz de usuario principal:

| Previsualización de interfaz | Elemento de la IU | Descripción |
| --- | --- | --- |
| ![Carril de consulta](assets/query-rail.png) | Carril de consulta | Configure los componentes deseados (eventos, propiedades y segmentos) que componen un análisis. Cada tipo de análisis impone límites diferentes al número de eventos y segmentos que se pueden configurar. Si cambia a un nuevo tipo de análisis, las selecciones de consulta se mantienen dentro de los límites permitidos para ese tipo de análisis. |
| ![Gráfico](assets/chart.png) | Gráfico | Una visualización de los datos devueltos en función de los datos que haya introducido desde el carril de consulta y la configuración. La visualización que vea depende de la vista y la configuración encima del gráfico. Las vistas disponibles dependen del tipo de análisis situado encima del carril de consulta. El gráfico también incluye: <ul><li>**Tooltips**: Pase el ratón sobre cualquier punto de datos del gráfico para exponer una información del objeto con más información.</li><li>**Leyenda**: Pase el ratón sobre la leyenda del gráfico para exponer las definiciones de series, cuando estén disponibles.</li><li>**Acciones de clic**: Exponga las acciones siguientes disponibles haciendo clic con el botón izquierdo en cualquier punto de datos. Las opciones incluyen **Guardar segmento**.</li></ul> |
| ![Tabla](assets/table.png) | Tabla | Una representación en tabla de los datos devueltos en función de los datos introducidos desde el carril de consulta y la configuración. Las columnas de la tabla dependen del tipo de vista encima del gráfico. Las vistas disponibles dependen del tipo de análisis situado encima del carril de consulta. La tabla también incluye: <ul><li>**Acciones de clic**: Exponga las acciones siguientes disponibles haciendo clic en **[!UICONTROL Más]** menú. Las opciones incluyen **Guardar segmento**.</li></ul> |
| ![Configuración de visualización](assets/visualization-settings.png) | Configuración de visualización | Hay varias opciones encima del gráfico que le permiten personalizar el modo en que el gráfico y la tabla devuelven los datos.<ul><li>**Tipo de vista**: Selector desplegable que permite presentar los datos de un tipo de análisis determinado de una manera diferente.</li><li>**Configuración de gráfico**: Ajuste lo que se muestra en el gráfico y en la tabla. Las opciones disponibles dependen de la vista seleccionada.</li><li>**Intervalo de fechas**: Selector de calendario que le permite determinar el intervalo de fechas del análisis. También puede seleccionar un intervalo para las vistas de tendencias, como diaria, semanal o mensual.</li><li>**Insights**: Perspectivas contextuales según el análisis que visualice. Puede acceder a perspectivas adicionales mediante las flechas o mostrar u ocultar estas perspectivas mediante el icono de la bombilla en la parte superior derecha.</li></ul> |
| ![Menú](assets/menu.png) | Menú | Comandos en la parte superior derecha de Análisis guiado que proporcionan acciones generales para el análisis.<ul><li>**Selector de vista de datos**: cambie la vista de datos que utiliza el análisis. Al cambiar la vista de datos, también cambian los componentes disponibles en el carril de consulta.</li><li>**Guardar**: guarda el análisis. Si está guardando un nuevo análisis, aparecerá una ventana modal que solicita un nombre y una descripción.</li><li>**Guardar como**: Guarda el análisis de forma independiente del análisis actual y crea una copia. Aparece una ventana modal que solicita un nuevo nombre y descripción.</li><li>**Abrir en Workspace**: vuelve a crear el análisis guiado actual en Analysis Workspace. El proyecto del Espacio de trabajo se crea en una nueva pestaña, lo que evita interrupciones mientras se trabaja dentro del análisis guiado. Es una copia del análisis y no permanece sincronizado con el análisis guiado original una vez abierto. Utilice este comando cuando desee transferir datos a su equipo de analistas o profundizar en los datos más de lo que permite el análisis guiado.</li><li>**Copiar al portapapeles**: copia el gráfico del gráfico en el portapapeles para pegarlo en otras aplicaciones. El carril de consulta y la tabla no se incluyen en el gráfico.</li><li>**Descargar PNG**: descarga el gráfico del gráfico como `.png`. El carril de consulta y la tabla no se incluyen en el gráfico.</li><li>**Descargar CSV**: descarga los datos de tabla como un `.csv`. El carril de consulta y el gráfico no se incluyen en el archivo.</li></ul> |

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
