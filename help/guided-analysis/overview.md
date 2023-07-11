---
title: Información general sobre el análisis guiado
description: Un método de análisis de datos en Customer Journey Analytics que permite a los equipos de productos generar fácilmente informes y perspectivas.
exl-id: 6a8a92db-f030-424e-af9b-f8f6502084f6
feature: Guided Analysis
source-git-commit: f48d17cf975ce7d069ac90f9685b96669a29eaff
workflow-type: tm+mt
source-wordcount: '912'
ht-degree: 9%

---

# Información general sobre el análisis guiado

{{release-limited-testing}}

El análisis guiado es un formato de informes que permite a los equipos de productos autoabastecer rápidamente sus necesidades de datos para que puedan tomar más decisiones de productos basadas en datos. Los equipos interfuncionales pueden conectarse en tiempo real para utilizar y comprender estos informes.

Al igual que los cuadros de resultados de Analysis Workspace y Mobile, un informe de análisis guiado utiliza datos de una [Vista de datos](../data-views/data-views.md), que hace referencia a los datos en Adobe Experience Platform a través de una [Conexión](../connections/overview.md). Todos los informes creados en Guided analysis pueden transferirse sin problemas a Analysis Workspace para realizar investigaciones adicionales.

El análisis guiado proporciona varias formas de analizar los datos. Estos tipos de vista pueden mostrar los mismos datos de diferentes maneras, lo que conduce a diferentes perspectivas utilizando los mismos eventos y segmentos. Puede obtener diferentes carriles de consulta y opciones de visualización en función del tipo de vista que elija. Puede cambiar libremente entre tipos de vista, y cualquier componente del carril de consulta aplicable se transferirá si el tipo de vista los admite.

El análisis guiado clasifica los tipos de vista en **Tipos de análisis**. Están disponibles los siguientes tipos de análisis y vistas:

| Tipo de análisis | Ver tipo | Descripción |
| --- | --- | --- |
| Impacto | [Versión](types/release.md) | Comparar los resultados en periodos iguales antes y después de la liberación. |
| Impacto | [Primer uso](types/first-use.md) | Medir el impacto del uso de funciones por primera vez en indicadores clave. |
| Canal | [Fricción](types/friction.md) | Comparar tasas de conversión entre los pasos. |
| Canal | [Tendencias de conversión](types/conversion-trends.md) | Realizar un seguimiento de los cambios en las tasas de conversión a lo largo del tiempo. |
| Crecimiento de usuarios | [Activo](types/active.md) | Medir el crecimiento de la base de usuarios. |
| Crecimiento de usuarios | [Crecimiento neto](types/net-growth.md) | Balance de pérdidas y ganancias del usuario. |
| Tendencias | [Uso](types/usage.md) | Medir la participación del usuario a lo largo del tiempo. |

{style="table-layout:auto"}

## Interfaz

La interfaz para el análisis guiado, independientemente del tipo de análisis, consta de los siguientes elementos de la interfaz de usuario principal:

1. **Carril de consulta**: utilice este carril de la izquierda para crear el análisis.
1. **Gráfico**: Una vez seleccionados los eventos, las personas o los pasos deseados, se muestra un gráfico a la derecha que visualiza los datos.
1. **Tabla**: Una tabla debajo del gráfico que muestra los números utilizados en la visualización.
1. **Configuración y perspectivas**: varios elementos de la interfaz de usuario encima del gráfico que permiten personalizar los datos devueltos.

[Captura de pantalla de IU]

El análisis guiado contiene las siguientes partes de la interfaz:

| Previsualización de interfaz | Elemento de la IU | Descripción |
| --- | --- | --- |
| [Captura de pantalla del carril de consultas] | Carril de consulta | Configure los componentes que desee que formen un informe. Los distintos tipos de análisis comparten varias opciones de consulta; si dos tipos de análisis comparten opciones de consulta, se transfieren al cambiar de tipo de análisis. |
| [Captura de pantalla del gráfico] | Gráfico | Una visualización de los datos devueltos en función de los datos que haya introducido desde el carril de consulta y la configuración. La visualización que vea depende del tipo de vista encima del gráfico. Los tipos de vista disponibles dependen del tipo de análisis situado encima del carril de consulta. |
| [Captura de pantalla de la tabla] | Tabla | Una representación en tabla de los datos devueltos en función de los datos introducidos desde el carril de consulta y la configuración. Las columnas de la tabla dependen del tipo de vista encima del gráfico. Los tipos de vista disponibles dependen del tipo de análisis situado encima del carril de consulta. |
| [Captura de pantalla de configuración] | Configuración | Hay varias opciones encima del gráfico que le permiten personalizar el modo en que el gráfico y la tabla devuelven los datos.<ul><li>**Tipo de vista**: Selector desplegable que permite presentar los datos de un tipo de análisis determinado de una manera diferente. Cada tipo de análisis tiene al menos dos tipos de vista.</li><li>**Configuración de gráfico**: Ajuste el aspecto del gráfico y los eventos que desea que utilice. Las opciones disponibles dependen del tipo de vista seleccionado.</li><li>**Intervalo de fechas**: Selector de calendario que le permite determinar el intervalo de fechas del informe. Algunos tipos de análisis también permiten intervalos, como diario, semanal o mensual.</li><li>**Insights**: proporciona perspectivas contextuales según el informe que vea. Puede mostrar u ocultar estas perspectivas usando el icono de la bombilla en la parte superior derecha.</li></ul> |
| [Captura de pantalla del menú de análisis] | Menú Análisis | Comandos en la parte superior derecha de Análisis guiado que proporcionan acciones generales.<ul><li>**Selector de vista de datos**: cambie la vista de datos que utiliza este análisis. Al cambiar la vista de datos, también cambian los componentes disponibles en el carril de consulta.</li><li>**Guardar**: guarda el análisis. Si está guardando un nuevo análisis, aparecerá una ventana modal que solicita un nombre y una descripción.</li><li>**Guardar como**: Guarda el análisis de forma independiente del análisis actual y crea una copia. Aparece una ventana modal que solicita un nuevo nombre y descripción.</li><li>**Abrir en Workspace**: vuelve a crear el análisis guiado actual en Analysis Workspace. El proyecto del Espacio de trabajo se crea en una nueva pestaña, lo que evita interrupciones mientras se trabaja dentro del análisis guiado. Utilice este comando cuando el análisis guiado no le proporcione la flexibilidad o la perspectiva específica que está buscando. Por ejemplo, desea un [Uso](types/usage.md) que utiliza Sesiones para un segmento y Personas para otro segmento.</li><li>**Descargar PNG**: descarga el gráfico del gráfico como `.png`. El carril de consulta y la tabla no se incluyen en el gráfico.</li><li>**Descargar SVG**: descarga el gráfico del gráfico como `.svg`. El carril de consulta y la tabla no se incluyen en el gráfico.</li></ul> |

{style="table-layout:auto"}

## Aprovisionamiento

El análisis guiado forma parte de Adobe Product Analytics, que es un complemento de pago para Customer Journey Analytics. Si su organización desea empezar a utilizar esta función, póngase en contacto con el equipo de cuenta de Adobe.

Una vez que su organización esté aprovisionada para utilizar el análisis guiado, los administradores de perfil de producto pueden conceder acceso a él en Adobe Admin Console.

1. Inicie sesión en [Adobe admin console](https://adminconsole.adobe.com).
1. Seleccionar **[!UICONTROL Customer Journey Analytics]** en la lista de productos.
1. Seleccione el perfil de producto que desee para editar permisos.
1. Haga clic en **[!UICONTROL Permisos]** y haga clic en **[!UICONTROL Editar]** bajo [!UICONTROL Herramientas de informes].
1. Haga clic en el icono de signo más situado junto a **[!UICONTROL Acceso guiado a análisis]** en lista de [!UICONTROL Elementos de permisos disponibles] para añadirlo a la lista de [!UICONTROL Elementos de permisos incluidos].
1. Haga clic en **[!UICONTROL Guardar]**.
