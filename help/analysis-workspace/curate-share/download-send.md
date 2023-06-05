---
description: Puede descargar datos de Analysis Workspace copiándolos, o en los formatos PDF y CSV.
title: Descarga de archivos PDF o CSV
feature: Curate and Share
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
source-git-commit: ebdbfcb4a512c8810364693fc3c2504f958bc986
workflow-type: tm+mt
source-wordcount: '1082'
ht-degree: 68%

---

# Descarga de archivos PDF o CSV

Existen varias formas de exportar datos desde Analysis Workspace. El método que elija dependerá del conjunto de datos que desee analizar y de quién deba acceder a ellos.

Los datos exportados pueden estar en forma de datos copiados, CSV o PDF. Normalmente, se prefiere un PDF si desea que las visualizaciones se incluyan en el archivo. Se prefieren los datos CSV y copiados si simplemente desea datos de texto sin formato.

## Descargar un proyecto como CSV o como PDF {#download-project}


1. Realice una de las siguientes acciones, en función del formato en el que desee descargar el proyecto:

   * **PDF:** Seleccionar **[!UICONTROL Proyecto]** > **[!UICONTROL Descargar PDF]**.

      Elija esta opción si desea que el archivo descargado contenga todas las tablas y visualizaciones mostradas (visibles) en el proyecto.

   * **CSV:** Seleccionar **[!UICONTROL Proyecto]** > **[!UICONTROL Descargar CSV]**.

      Elija esta opción si desea datos de texto sin formato.
   ![](assets/download-project.png)

1. (Condicional) Si elige descargar un PDF, se muestra un mensaje después de que el proyecto esté listo para descargarse. Haga clic en [!UICONTROL **Descargar**].

Para las descargas de proyectos, tenga en cuenta:

* El proyecto se puede guardar o no guardar cuando se solicita una descarga del proyecto. Sin embargo, solo los proyectos guardados pueden [programarse](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/t-schedule-report.html?lang=es).
* Los archivos PDF descargados en el explorador pueden tardar varios minutos en exportarse, ya que el proyecto se vuelve a ejecutar en los servidores de Adobe antes de procesarse en formato PDF. Se recomienda no abandonar el proyecto hasta que el PDF se descargue en el explorador. Sin embargo, puede seguir realizando cambios en el proyecto mientras espera. Si un PDF tarda más de 5 minutos en procesarse, se le pedirá que lo envíe por correo electrónico.
* Las descargas de PDF se representan como una sola página sin paginación aplicada.
* Cuando se procesa un proyecto en PDF, se procesa lo que figura en la página. Si un proyecto tiene paneles y visualizaciones de tamaño personalizado, deberá cambiarlos a tamaño automático (mediante el botón que hay en la esquina superior derecha) para que no se trunque el contenido.

## Copiado de datos en el portapapeles (tecla de acceso directo: Ctrl + C) {#copy-data}

La opción del botón derecho **[!UICONTROL Copiar al portapapeles]** permite copiar rápidamente datos de Workspace y pegarlos en una herramienta de terceros.

* Si desea que se copie la tabla mostrada, haga clic con el botón derecho en el encabezado de tabla y elija **Copiar datos al portapapeles**.
* Si desea que se copie un subconjunto de datos, realice una selección en la tabla y, a continuación, haga clic con el botón derecho > **Copiar selección al portapapeles**.

>[!TIP]
>
>Puede utilizar la tecla de acceso directo `Ctrl+C` para copiar la selección en el portapapeles, utilice `Ctrl+V` para pegarlo en una herramienta de terceros.


![](assets/copy-selection.png)

## Descargue los datos como CSV {#download-data}

La opción **[!UICONTROL Descargar datos como CSV]** del botón secundario le permite descargar una tabla de datos o la fuente de datos de cualquier visualización como CSV.

* Desde el encabezado de cualquier tabla o visualización, haga clic con el botón derecho y elija **[!UICONTROL Descarga de datos como CSV]**. Esto descarga los datos mostrados en la tabla o la fuente de datos subyacente para una visualización como CSV.

   >[!NOTE]
   >
   >  Nota: la visualización Mapa no admite esta opción.


* Dentro de una tabla, haga clic con el botón derecho y elija **[!UICONTROL Descargar selección como CSV]**. Solo la selección se descarga con esta opción, a diferencia de la tabla mostrada completa.

![](assets/download-data-viz.png)

## Descargar elementos como CSV {#download-items}

Si desea analizar más de las 400 filas de datos visibles en una tabla, haga clic con el botón derecho en el encabezado de tabla o en cualquier fila y seleccione **Descargar elementos como CSV (_nombre del Dimension_)**. Esta opción exporta hasta 50 000 elementos de dimensión (según el orden de tabla) para la dimensión seleccionada, con opciones de ordenación y filtros aplicados. Si elige esta opción en la parte superior de la tabla, se exporta la primera dimensión de la tabla. Aunque no se aplican límites en la tabla de forma libre, se recomienda utilizar la opción Descargar elementos en tablas con menos de 20 columnas para garantizar un rendimiento óptimo.

>[!TIP]
>
> Si la dimensión supera los 50 000 elementos, descargue el archivo con diferentes métricas de ordenación aplicadas o aplique un filtro. Por ejemplo, ordenar de forma descendente por Visitas en una descarga y, a continuación, ascendente por Visitas en una segunda descarga. Esta sugerencia puede ayudarle a recuperar elementos de mayor longitud.

Puede realizar varias tareas dentro del proyecto e incluso desplazarse a un nuevo proyecto de Workspace en la misma pestaña mientras la descarga está en curso. La descarga se detiene si abre una nueva pestaña del explorador. La descarga se cancela si deja Workspace por completo o si cierra la pestaña del explorador.

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

## Descarga de datos confidenciales {#sensitive}

Si la [política de gobernanza de datos](/help/data-views/data-governance.md) **[!UICONTROL Aplicar descarga]** está activada en la vista de datos sobre la que crea informes, cualquier descarga (como el envío por correo electrónico o el uso compartido de PDF) de los proyectos del espacio de trabajo hará un hash de los campos de datos etiquetados como confidenciales. Puede seguir analizando estos campos en el espacio de trabajo, pero, si intenta enviar un correo electrónico o compartir un proyecto de otro modo, los campos bloqueados aparecerán como vacíos en el archivo .pdf o .csv.

## Preguntas más frecuentes {#faq}

| Pregunta | Respuesta |
| --- | --- |
| ¿Por qué el PDF descargado es una página? | Workspace no pagina los PDF descargados en este momento. |
| ¿Puedo exportar más de 50 000 elementos con la opción Descargar elementos como CSV? | Aunque cada descarga puede contener hasta 50 000 elementos de dimensión, puede cambiar el tipo de tabla para recuperar elementos de cola más largos o aplicar un filtro para descargar elementos más específicos. |
| ¿Qué hace **[!UICONTROL Copiar visualización]**? | Diferente [!UICONTROL **Copiar datos al portapapeles**] o [!UICONTROL **Copiar selección al portapapeles**], el **[!UICONTROL Copiar visualización]** la opción del botón derecho no es una opción de exportación. Permite copiar una visualización o un panel de un lugar de Workspace a otro. Por ejemplo, de un panel a otro en el mismo proyecto o de un proyecto a otro. [Intravínculos de vídeo](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html?lang=es) |
