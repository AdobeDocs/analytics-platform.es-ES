---
title: Tabla improvisada
description: Obtenga información sobre las tablas improvisadas y el generador de tablas improvisadas
translation-type: tm+mt
source-git-commit: 1759bbf965e6b8d07e5a25867b73c3242dc49005
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 100%

---


# Tabla improvisada

>[!NOTE]
>
>Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

En Analysis Workspace, una tabla improvisada no es solamente una tabla de datos, sino también una visualización interactiva. Puede arrastrar y soltar una combinación de [componentes](/help/components/overview.md) en las filas y columnas para crear una tabla personalizada para el análisis. A medida que se suelta cada componente, la tabla se actualiza inmediatamente para que pueda realizar un análisis rápido.

Puede personalizar la tabla de varias formas:

* **Filas**
   * Cada fila de dimensión puede mostrar hasta 400 filas antes de que se produzca la paginación. Puede visualizar más filas en una sola pantalla ajustando la [densidad de vista](/help/analysis-workspace/build-workspace-project/view-density.md) del proyecto.
   * Las filas se pueden desglosar en componentes adicionales. Para desglosar muchas filas a la vez solo tiene que seleccionar varias filas y arrastrar el siguiente componente sobre las filas seleccionadas. Obtenga más información sobre los [desgloses](/help/components/dimensions/t-breakdown-fa.md).
   * Las filas se pueden [filtrar](/help/analysis-workspace/visualizations/freeform-table/pagination-filtering-sorting.md) para mostrar un conjunto reducido de elementos. Hay opciones de configuración adicionales disponibles en [Configuración de fila](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md).

* **Columnas**
   * Los componentes se pueden apilar en columnas para crear métricas segmentadas, análisis entre fichas, etcétera.
   * La vista de cada columna se ajusta en la [configuración de columna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).
   * Hay varias acciones disponibles a través del [menú accesible mediante el botón secundario](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html). El menú proporciona diferentes acciones en función de si se hace clic en el encabezado de tabla, en las filas o en las columnas.

## Generador de tablas improvisadas

Si prefiere primero agregar varios componentes a la tabla y luego procesar los datos, puede habilitar el Generador de tablas improvisadas. Con el Generador de tablas improvisadas, puede arrastrar y soltar varias dimensiones, desgloses, métricas y segmentos para crear tablas que respondan a preguntas más complejas. Los datos no se actualizarán sobre la marcha, sino una vez que haga clic en **[!UICONTROL Generar]**.

El Generador de tablas es una opción que ahorra tiempo cuando tiene una pregunta compleja que hacer sobre los datos y tiene una idea de qué tabla desea crear para responder a su pregunta. Otras ventajas del generador de tablas incluyen la capacidad de:

* Organizar la tabla en el formato que necesite, sin tener que esperar a que se procese cada acción.
* Realizar rápidamente hasta 4 niveles de desgloses.
* Definir la configuración de Fila y Desglose para cada fila de tabla y columna de dimensión.
* **[!UICONTROL Desglose por posición]** para cada nivel de la tabla de forma predeterminada (en las tablas improvisadas tradicionales, el valor predeterminado es **[!UICONTROL Desglosar por elemento]**).
* Ordenar manualmente filas estáticas en la tabla. Por ejemplo, si desea que las filas de métricas aparezcan en un orden determinado.
* Previsualizar el formato de la tabla antes de procesar datos reales.

Observe cómo funciona el Generador de tablas improvisadas [aquí](https://youtu.be/GUMWiJAmMGI).

## Exportar datos de tabla improvisada

Los datos de una tabla improvisada se pueden copiar desde Analysis Workspace de varias formas:

* Haga clic con el botón derecho en el encabezado de tabla y seleccione **[!UICONTROL Copiar al portapapeles]**. Esto exportará la tabla completa (visible).
* Resalte celdas específicas en la tabla, haga clic con el botón secundario y seleccione **[!UICONTROL Copiar al portapapeles]** o utilice la tecla de acceso directo Ctrl + C.
* **[!UICONTROL Proyecto > Descargar CSV]**. Esto exportará todas las tablas visibles del proyecto en formato CSV.
