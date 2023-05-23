---
title: Interfaz de análisis guiada
description: Obtenga información acerca de la estructura general de la interfaz de usuario del proyecto de análisis guiado.
source-git-commit: d73dc0eb1740f28c0cd0b7b64fee86069c402b63
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 0%

---

# Interfaz de análisis de guía

{{release-limited-testing}}

La interfaz de un proyecto de análisis guiado, independientemente del tipo de análisis, consta de los siguientes elementos de la interfaz de usuario principal:

* **Carril de consulta**: utilice este carril de la izquierda del proyecto para crear el análisis.
* **Gráfico**: Una vez seleccionados los eventos, las personas o los pasos deseados, se muestra un gráfico a la derecha que visualiza los datos.
* **Tabla**: Una tabla debajo del gráfico que muestra los números utilizados en la visualización.
* **Configuración y perspectivas**: varios elementos de la interfaz de usuario encima del gráfico que permiten personalizar los datos devueltos.

[Captura de pantalla de IU]

## Carril de consulta

[Captura de pantalla del carril de consultas]

En el carril de consultas es donde se configuran los componentes deseados que conforman un informe. Los distintos tipos de análisis comparten varias opciones de consulta; si dos tipos de análisis comparten opciones de consulta, se transfieren al cambiar de tipo de análisis. Consulte [Tipos de análisis](analysis-types/overview.md) para obtener más información sobre las opciones de consulta de cada tipo de análisis respectivo.

## Gráfico

[Captura de pantalla del gráfico]

Una visualización de los datos devueltos en función de los datos que haya introducido desde el carril de consulta y la configuración. La visualización que vea depende del tipo de vista encima del gráfico. Los tipos de vista disponibles dependen de la variable [Tipo de análisis](analysis-types/overview.md) sobre el carril de consultas.

## Tabla

[Captura de pantalla de la tabla]

Una representación en tabla de los datos devueltos en función de los datos introducidos desde el carril de consulta y la configuración. Las columnas de la tabla dependen del tipo de vista encima del gráfico. Los tipos de vista disponibles dependen de la variable [Tipo de análisis](analysis-types/overview.md) sobre el carril de consultas.

## Configuración

[Captura de pantalla de configuración]

Hay varias opciones encima del gráfico que le permiten personalizar el modo en que el gráfico y la tabla devuelven los datos.

* **Tipo de vista**: Un selector desplegable que le permite presentar los datos de un [Tipo de análisis](analysis-types/overview.md) de una manera diferente. Cada tipo de análisis tiene al menos dos tipos de vista.
* **Configuración de gráfico**: Ajuste el aspecto del gráfico y los eventos que desea que utilice. Las opciones disponibles dependen del tipo de vista seleccionado.
* **Intervalo de fechas**: Selector de calendario que le permite determinar el intervalo de fechas del informe. Algunos tipos de análisis también permiten intervalos, como diario, semanal o mensual.
* **Insights**: proporciona perspectivas contextuales según el informe que vea. Puede mostrar u ocultar estas perspectivas usando el icono de la bombilla en la parte superior derecha.

## Menú Proyecto

[Captura de pantalla del menú del proyecto]

Comandos en la parte superior derecha del proyecto que proporcionan acciones generales.

* **Selector de vista de datos**: cambie la vista de datos que utiliza este proyecto. Al cambiar la vista de datos, también cambian los componentes disponibles en el carril de consulta.
* **Guardar**: guarda el proyecto. Si está guardando un nuevo proyecto, aparecerá una ventana modal que solicita un nombre y una descripción.
* **Guardar como**: guarda el proyecto independientemente del proyecto actual y crea una copia. Aparece una ventana modal que solicita un nuevo nombre y descripción.
* **Abrir en Workspace**: vuelve a crear el proyecto de análisis guiado actual en Analysis Workspace. El proyecto de Workspace se crea en una nueva pestaña, lo que evita interrupciones mientras se trabaja en el proyecto de Análisis guiado. Utilice este comando cuando el análisis guiado no le proporcione la flexibilidad o la perspectiva específica que está buscando. Por ejemplo, desea un [Tendencias](analysis-types/trends.md) que utiliza Sesiones para un segmento y Personas para otro segmento.
* **Descargar PNG**: descarga el gráfico del gráfico como `.png`. El carril de consulta y la tabla no se incluyen en el gráfico.
* **Descargar SVG**: descarga el gráfico del gráfico como `.svg`. El carril de consulta y la tabla no se incluyen en el gráfico.
