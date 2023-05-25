---
title: Información general sobre el análisis guiado
description: Un método de análisis de datos en Customer Journey Analytics que permite a los equipos de productos generar fácilmente informes y perspectivas.
source-git-commit: 03f6b0cef6fa4259041a82173acda852d91e06b5
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 1%

---

# Información general sobre el análisis guiado

{{release-limited-testing}}

El análisis guiado es un formato de informes que permite a los equipos de productos autoabastecer rápidamente sus necesidades de datos para que puedan tomar más decisiones de productos basadas en datos. Los equipos interfuncionales pueden conectarse en tiempo real para utilizar y comprender estos informes.

Al igual que los cuadros de resultados de Analysis Workspace y Mobile, un informe de análisis guiado utiliza datos de una [Vista de datos](../data-views/data-views.md), que hace referencia a los datos en Adobe Experience Platform a través de una [Conexión](../connections/overview.md). Todos los informes creados en Guided analysis pueden transferirse sin problemas a Analysis Workspace para realizar investigaciones adicionales.

Actualmente, los informes de análisis guiados presentan tres tipos de análisis: [Canal](analysis-types/funnel.md), [Tendencias](analysis-types/trends.md), y [Crecimiento de usuarios](analysis-types/user-growth.md). Cada uno de estos tipos de análisis tiene varios tipos de vista, que proporcionan información adicional a cada uno de estos informes.

## Aprovisionamiento

El análisis guiado es un complemento de pago para Customer Journey Analytics. Si su organización desea empezar a utilizar esta función, póngase en contacto con el equipo de cuenta de Adobe.

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
| [Captura de pantalla del carril de consultas] | Carril de consulta | Configure los componentes que desee que formen un informe. Los distintos tipos de análisis comparten varias opciones de consulta; si dos tipos de análisis comparten opciones de consulta, se transfieren al cambiar de tipo de análisis. Consulte [Tipos de análisis](analysis-types/overview.md) para obtener más información sobre las opciones de consulta de cada tipo de análisis respectivo. |
| [Captura de pantalla del gráfico] | Gráfico | Una visualización de los datos devueltos en función de los datos que haya introducido desde el carril de consulta y la configuración. La visualización que vea depende del tipo de vista encima del gráfico. Los tipos de vista disponibles dependen de la variable [Tipo de análisis](analysis-types/overview.md) sobre el carril de consultas. |
| [Captura de pantalla de la tabla] | Tabla | Una representación en tabla de los datos devueltos en función de los datos introducidos desde el carril de consulta y la configuración. Las columnas de la tabla dependen del tipo de vista encima del gráfico. Los tipos de vista disponibles dependen de la variable [Tipo de análisis](analysis-types/overview.md) sobre el carril de consultas. |
| [Captura de pantalla de configuración] | Configuración | Hay varias opciones encima del gráfico que le permiten personalizar el modo en que el gráfico y la tabla devuelven los datos.<ul><li>**Tipo de vista**: Un selector desplegable que le permite presentar los datos de un [Tipo de análisis](analysis-types/overview.md) de una manera diferente. Cada tipo de análisis tiene al menos dos tipos de vista.</li><li>**Configuración de gráfico**: Ajuste el aspecto del gráfico y los eventos que desea que utilice. Las opciones disponibles dependen del tipo de vista seleccionado.</li><li>**Intervalo de fechas**: Selector de calendario que le permite determinar el intervalo de fechas del informe. Algunos tipos de análisis también permiten intervalos, como diario, semanal o mensual.</li><li>**Insights**: proporciona perspectivas contextuales según el informe que vea. Puede mostrar u ocultar estas perspectivas usando el icono de la bombilla en la parte superior derecha.</li></ul> |
| [Captura de pantalla del menú de análisis] | Menú Análisis | Comandos en la parte superior derecha de Análisis guiado que proporcionan acciones generales.<ul><li>**Selector de vista de datos**: cambie la vista de datos que utiliza este análisis. Al cambiar la vista de datos, también cambian los componentes disponibles en el carril de consulta.</li><li>**Guardar**: guarda el análisis. Si está guardando un nuevo análisis, aparecerá una ventana modal que solicita un nombre y una descripción.</li><li>**Guardar como**: Guarda el análisis de forma independiente del análisis actual y crea una copia. Aparece una ventana modal que solicita un nuevo nombre y descripción.</li><li>**Abrir en Workspace**: vuelve a crear el análisis guiado actual en Analysis Workspace. El proyecto del Espacio de trabajo se crea en una nueva pestaña, lo que evita interrupciones mientras se trabaja dentro del análisis guiado. Utilice este comando cuando el análisis guiado no le proporcione la flexibilidad o la perspectiva específica que está buscando. Por ejemplo, desea un [Tendencias](analysis-types/trends.md) que utiliza Sesiones para un segmento y Personas para otro segmento.</li><li>**Descargar PNG**: descarga el gráfico del gráfico como `.png`. El carril de consulta y la tabla no se incluyen en el gráfico.</li><li>**Descargar SVG**: descarga el gráfico del gráfico como `.svg`. El carril de consulta y la tabla no se incluyen en el gráfico.</li></ul> |

{style="table-layout:auto"}

## Permisos

Adobe planea proporcionar permisos específicos para el análisis guiado en el futuro.

<!-- Once your organization is provisioned to use Guided analysis, product profile administrators can grant access to it in the Adobe Admin Console.

1. Log in to the [Adobe admin console](https://adminconsole.adobe.com).
1. Select **[!UICONTROL Customer Journey Analytics]** in the list of products.
1. Select the desired product profile to edit permissions.
1. Click the **[!UICONTROL Permissions]** tab, then click **[!UICONTROL Edit]** under [!UICONTROL Reporting Tools].
1. Drag **[!UICONTROL Guided analysis]** from the list of [!UICONTROL Available Permission Items] to the list of [!UICONTROL Included Permission Items].
1. Click **[!UICONTROL Save]**. -->
