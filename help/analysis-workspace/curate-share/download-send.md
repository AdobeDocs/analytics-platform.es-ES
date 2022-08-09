---
description: Puede descargar datos de Analysis Workspace copiándolos, o en los formatos PDF y CSV.
title: Descarga de archivos PDF o CSV
feature: Curate and Share
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
source-git-commit: 3f0051868ef559d331fa9e5c4648f9bab7fc8d34
workflow-type: tm+mt
source-wordcount: '1048'
ht-degree: 93%

---

# Descarga de archivos PDF o CSV

Existen varias formas de exportar datos desde Analysis Workspace, en función del conjunto de datos que desee analizar fuera de la herramienta y de quién deba recibir la información. Los datos exportados pueden estar en forma de datos copiados, archivos CSV o archivos PDF. Normalmente, se prefiere un PDF si desea que las visualizaciones se incluyan en el archivo, mientras que un CSV (o datos copiados) es preferible si simplemente desea que los datos sean de texto sin formato.

## Descarga de un proyecto como CSV o PDF {#download-project}

Para descargar un proyecto completo, vaya a **[!UICONTROL Proyecto > Descargar como PDF (o como CSV)]**. El archivo descargado contiene todas las tablas y visualizaciones mostradas (visibles) en el proyecto. Normalmente, se prefiere un PDF si desea que las visualizaciones se incluyan en el archivo, mientras que un CSV es preferible si simplemente desea que los datos de texto sin formato.

![](assets/download-project.png)

Para las descargas de proyectos, tenga en cuenta:

* El proyecto se puede guardar o no guardar cuando se solicita una descarga del proyecto. Sin embargo, solo los proyectos guardados pueden [programarse](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/t-schedule-report.html?lang=es).
* Los archivos PDF descargados en el explorador pueden tardar varios minutos en exportarse, ya que el proyecto se vuelve a ejecutar en los servidores de Adobe antes de procesarse en formato PDF. Se recomienda no abandonar el proyecto hasta que el PDF se descargue en el explorador. Sin embargo, puede seguir realizando cambios en el proyecto mientras espera. Si un PDF tarda más de 5 minutos en procesarse, se le pedirá que lo envíe por correo electrónico.
* Las descargas de PDF se representan como una sola página sin paginación aplicada.
* Cuando se procesa un proyecto en PDF, se procesa lo que figura en la página. Si un proyecto tiene paneles y visualizaciones de tamaño personalizado, deberá cambiarlos a tamaño automático (mediante el botón que hay en la esquina superior derecha) para que no se trunque el contenido.

## Copiado de datos en el portapapeles (tecla de acceso directo: Ctrl + C) {#copy-data}

La opción **[!UICONTROL Copiar al portapapeles]**, que aparece al hacer clic con el botón derecho, permite copiar datos rápidamente desde Workspace y pegarlos en otro sitio.

* Si desea que se copie la tabla mostrada, haga clic con el botón derecho en el encabezado de la tabla y seleccione **Copiar datos al portapapeles**.
* Si desea que se copie un subconjunto de datos, realice una selección en la tabla y, a continuación, haga clic con el botón derecho > **Copiar selección al portapapeles**.

Además, la tecla de acceso directo `Ctrl+C` copia la selección en el portapapeles. Una vez copiado, puede ir a otra herramienta y pegar la información (o pulsar `Ctrl+V`).

![](assets/copy-selection.png)

## Descargue los datos como CSV {#download-data}

La opción **[!UICONTROL Descargar datos como CSV]** del botón secundario le permite descargar una tabla de datos o la fuente de datos de cualquier visualización como CSV.

* Desde el encabezado de cualquier tabla o visualización, haga clic con el botón derecho en **[!UICONTROL Descargar datos como CSV]**. Esto descarga los datos mostrados en la tabla o la fuente de datos subyacente para una visualización como CSV. Nota: la visualización Mapa no admite esta opción.
* Si se realiza una selección en la tabla, la opción dirá **[!UICONTROL Descargar selección como CSV]**. Solo la selección se descarga con esta opción, a diferencia de la tabla mostrada completa.

![](assets/download-data-viz.png)

## Descargar elementos como CSV {#download-items}

Si desea analizar más de las 400 filas de datos visibles en una tabla, haga clic con el botón derecho en cualquier encabezado de tabla o fila y seleccione **Descargar elementos como CSV (nombre de la dimensión)**. Esta opción exportará hasta 50 000 elementos de dimensión (según el orden de tabla) para la dimensión seleccionada, con filtros aplicados. Si elige esta opción en la parte superior de la tabla, se exporta la primera dimensión de la tabla. Aunque no se aplican límites en la tabla improvisada, se recomienda utilizar la opción Descargar elementos en tablas con menos de 20 columnas para garantizar un rendimiento óptimo.

>[!TIP]
>
> Si la dimensión supera los 50 000 elementos, descargue el archivo con diferentes métricas de ordenación aplicadas o aplique un filtro. Por ejemplo, ordenar de forma descendente por Visitas en una descarga y, a continuación, ascendente por Visitas en una segunda descarga. Esta sugerencia puede ayudarle a recuperar elementos de mayor longitud.

Puede realizar varias tareas dentro del proyecto e incluso desplazarse a un nuevo proyecto de Workspace en la misma pestaña mientras la descarga está en curso. La descarga se detendrá si abre una nueva pestaña del explorador. La descarga se cancelará si deja Workspace por completo o si cierra la pestaña del explorador.

![](assets/download-items.png)

### Archivo de elementos descargados {#items-file}

Las funciones de la tabla se aplicarán al archivo descargado de la siguiente manera:

* Todos los filtros del panel se aplican como filtros.
* Los desgloses **superiores** a la dimensión seleccionada en la tabla se aplican como filtros encima de cada columna.
* Los desgloses **inferiores** a las dimensiones seleccionadas en la tabla se eliminan.

En el ejemplo anterior, los elementos de página se descargan con el filtro de panel (Clientes de nuevos visitantes) y los componentes anteriores (Canal de marketing = Correo electrónico) aplicados como filtros, y los componentes siguientes (Tipo de dispositivo móvil) se eliminan del CSV descargado.

![](assets/downloaded-file.png)

### Descarga de notificaciones {#notifications}

A medida que el archivo se descarga, verá una notificación informativa con el progreso. En cualquier momento, puede cancelar la descarga haciendo clic en **[!UICONTROL Cancelar descarga]**. Al cerrar el mensaje **no se** cancelará la descarga.

Una vez que el archivo se complete, verá una notificación de finalización y el archivo se descargará en el explorador.

Si solicita más de una descarga a la vez, recibirá una notificación avisando que cada descarga adicional se colocará en cola hasta que finalice la descarga anterior.

![](assets/toast.png)

## Descargar datos confidenciales {#sensitive}

Si la directiva Aplicar administración de datos de descarga está activada, cualquier descarga (como correos electrónicos o archivos pdfs compartidos) de proyectos de Workspace hash de los campos de datos etiquetados como confidenciales. Puede seguir realizando análisis de estos campos en Workspace, pero si intenta enviar un correo electrónico o compartir un proyecto de otro modo, los campos bloqueados aparecerán como elementos con hash en el archivo .pdf.

## Preguntas más frecuentes {#faq}

| Pregunta | Respuesta |
| --- | --- |
| ¿Por qué el PDF descargado es una página? | Workspace no pagina los PDF descargados en este momento. |
| ¿Puedo exportar más de 50 000 elementos con la opción Descargar elementos como CSV? | Aunque cada descarga puede contener hasta 50 000 elementos de dimensión, puede cambiar el tipo de tabla para recuperar elementos de cola más largos o aplicar un filtro para descargar elementos más específicos. |
| ¿Qué hace **[!UICONTROL Copiar visualización]**? | **[!UICONTROL Copiar visualización]** no es una opción de exportación. Permite copiar una visualización o un panel de un lugar de Workspace a otro. Por ejemplo, de un panel a otro en el mismo proyecto o de un proyecto a otro. [Intravínculos de vídeo](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html?lang=es) |
