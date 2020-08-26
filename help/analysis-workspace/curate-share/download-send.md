---
description: Puede descargar datos de Analysis Workspace copiándolos o en formatos PDF y CSV.
title: Descarga de archivos PDF o CSV
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
translation-type: tm+mt
source-git-commit: 814e02648607b6f06e2743cd054c14c892200b44
workflow-type: tm+mt
source-wordcount: '1028'
ht-degree: 7%

---


# Descarga de archivos PDF o CSV desde Workspace

Existen varias maneras de exportar datos desde Analysis Workspace, según el conjunto de datos que desee analizar fuera de la herramienta y quién necesite recibir la información. Los datos exportados pueden tener la forma de datos copiados, archivos CSV o archivos PDF. Normalmente, se prefiere un PDF si desea incluir visualizaciones en el archivo, mientras que un CSV (o datos copiados) es preferible si simplemente desea datos de texto sin formato.

>[!IMPORTANT]
>
> Algunas de las opciones a las que se hace referencia en esta página, como **Descargar elementos como CSV**, están actualmente en pruebas limitadas. [Más información](https://docs.adobe.com/content/help/es-ES/analytics/landing/an-releases.html)

## Descargar proyecto como CSV o PDF {#download-project}

Para descargar un proyecto completo, vaya a **[!UICONTROL Proyecto > Descargar como PDF (o como CSV)]**. El archivo descargado contiene todas las tablas y visualizaciones mostradas (visibles) en el proyecto. Normalmente se prefiere un PDF si desea incluir visualizaciones en el archivo, mientras que un CSV se prefiere si simplemente desea datos de texto sin formato.

![](assets/download-project.png)

Para las descargas de proyectos, tenga en cuenta:

* El proyecto se puede guardar o no guardar cuando se solicita una descarga del proyecto. Sin embargo, solo los proyectos guardados pueden [programado](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/t-schedule-report.html).
* Los archivos PDF descargados en el navegador pueden tardar varios minutos en exportarse, ya que el proyecto se vuelve a ejecutar en servidores de Adobe antes de procesarse en formato PDF. Se recomienda no abandonar el proyecto hasta que el PDF se descargue en el explorador. Sin embargo, puede seguir realizando cambios en el proyecto mientras espera. Si un PDF tarda más de 5 minutos en procesarse, se le pedirá que lo envíe por correo electrónico.
* Las descargas de PDF se representan como una sola página sin ninguna paginación aplicada.
* Cuando se procesa un proyecto en PDF, se procesa lo que hay en la página. Si un proyecto tiene paneles y visualizaciones de tamaño personalizado, deberá cambiarlos a tamaño automático (mediante el botón que hay en la esquina superior derecha) para que no se trunque el contenido.

## Copiar datos en el portapapeles (tecla de acceso directo: Ctrl+C) {#copy-data}

Opción de clic con el botón derecho **[!UICONTROL Copiar al portapapeles]** le permite copiar datos de Workspace rápidamente y pegarlos en otro lugar.

* Si desea que se copie la tabla mostrada, haga clic con el botón derecho en el encabezado de la tabla y elija **Copiar los datos mostrados en el portapapeles**.
* Si desea copiar un subconjunto de datos, realice una selección en la tabla y, a continuación, haga clic con el botón secundario > **Copiar selección al portapapeles**.

Además, la tecla de acceso directo `Ctrl+C` copia la selección en el portapapeles. Una vez copiado, puede ir a otra herramienta y pegar la información (o la visita `Ctrl+V`).

![](assets/copy-selection.png)

## Descargue los datos como CSV {#download-data}

Opción de clic con el botón derecho **[!UICONTROL Descargar datos como CSV]** permite descargar una tabla de datos o la fuente de datos de cualquier visualización como CSV.

* En el encabezado de cualquier tabla, haga clic con el botón derecho **[!UICONTROL Descargar datos mostrados como CSV]**. Esto descarga los datos mostrados en la tabla como un CSV.
* Si se realiza una selección en la tabla, la opción dirá **[!UICONTROL Descargar selección como CSV]**. Solo la selección se descarga con esta opción, en oposición a la tabla mostrada completa.
* En el encabezado de cualquier visualización, haga clic con el botón derecho **[!UICONTROL Descargar datos como CSV]**. Esto descarga la tabla de fuente de datos para una visualización como un CSV. Nota: la visualización Mapa no admite esta opción.

![](assets/download-data-viz.png)

## Descargar elementos como CSV {#download-items}

Si desea analizar más de las 400 filas de datos visibles en una tabla, haga clic con el botón derecho en el encabezado de tabla o en cualquier fila y seleccione **Descargar elementos como CSV (nombre del Dimension)**. Esta opción exportará hasta 50.000 elementos de dimensión para la dimensión seleccionada (según el orden de tabla), con filtros y segmentos aplicados. Si elige esta opción desde la parte superior de la tabla, se exportará la primera dimensión de la tabla. Aunque no se aplican límites en la tabla improvisada, se recomienda utilizar la opción Descargar elementos en tablas con menos de 20 columnas para garantizar un rendimiento óptimo.

>[!TIP]
>
> Si la dimensión supera los 50.000 elementos, descargue el archivo con distintas métricas de ordenación aplicadas o aplique un filtro. Por ejemplo: ordene según las visitas en una descarga y luego aumente según las visitas en una segunda descarga. Esta sugerencia puede ayudarle a recuperar elementos de larga cola.

Puede realizar varias tareas dentro del proyecto e incluso desplazarse a un nuevo proyecto de Workspace en la misma ficha mientras la descarga está en curso. La descarga se detendrá si abre una nueva ficha del explorador. La descarga se cancelará si deja Workspace completamente o cierra la ficha del explorador.

![](assets/download-items.png)

### Archivo de elementos descargados

Las funciones de la tabla se aplicarán al archivo descargado de la siguiente manera:

* Todos los segmentos del panel se aplican como filtros.
* Desgloses **anterior** la dimensión seleccionada en la tabla se aplica como filtros sobre cada columna.
* Desgloses **below** se eliminará la dimensión seleccionada en la tabla.

En el ejemplo anterior, los elementos de página se descargan con el segmento del panel (Clientes de nuevos Visitantes) y los componentes anteriores (Canal de marketing = Correo electrónico) aplicados como filtros, y los componentes siguientes (Tipo de dispositivo móvil) se eliminan del CSV descargado.

![](assets/downloaded-file.png)

### Descargar notificaciones

A medida que se descarga el archivo, verá una notificación informativa con el progreso. En cualquier momento, puede cancelar la descarga haciendo clic en **[!UICONTROL Cancelar descarga]**. Cerrando el brindis **will not** cancele la descarga.

Una vez que el archivo se complete, verá una notificación de finalización y el archivo se descargará en su explorador.

Si solicita más de una descarga a la vez, recibirá una notificación de que cada descarga adicional se colocará en la cola hasta que se complete la descarga anterior.

![](assets/toast.png)

## Preguntas más frecuentes {#faq}

| Pregunta | Respuesta |
| --- | --- |
| ¿Por qué el PDF descargado es una página? | Workspace no pagina los archivos PDF descargados en este momento. |
| ¿Puedo exportar más de 50.000 elementos con la opción &quot;Descargar elementos como CSV&quot;? | Aunque cada descarga puede contener hasta 50.000 elementos de dimensión, puede cambiar el tipo de tabla para recuperar elementos de cola más largos o aplicar un filtro para descargar elementos más específicos. |
| ¿Qué hace? **[!UICONTROL Copiar visualización]** do? | **[!UICONTROL Copiar visualización]** no es una opción de exportación. Permite copiar una visualización o un panel de un lugar de Workspace a otro. Por ejemplo, de un panel a otro en el mismo proyecto o de un proyecto a otro. [Vea el video](https://www.youtube.com/watch?v=lvmAdKNfWQw) |

