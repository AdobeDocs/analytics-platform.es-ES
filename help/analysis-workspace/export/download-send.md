---
description: Puede descargar datos de Analysis Workspace copiándolos, o en los formatos PDF y CSV.
title: Descarga de datos de Customer Journey Analytics
feature: Curate and Share
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
role: User
source-git-commit: 0101986bb86c49776a044f754d912dc1bcb9422c
workflow-type: tm+mt
source-wordcount: '1194'
ht-degree: 98%

---

# Descarga de datos de Customer Journey Analytics

Puede descargar datos de Customer Journey Analytics en su estación de trabajo personal. Estos datos pueden tener forma de datos copiados, CSV o PDF. Normalmente, es preferible un archivo PDF si desea que las visualizaciones se incluyan en el archivo descargado. Se prefieren los datos CSV y copiados si simplemente desea datos de texto sin formato.

También están disponibles otros métodos de exportación de datos de Customer Journey Analytics, como se describe en [Información general sobre la exportación](/help/analysis-workspace/export/export-project-overview.md).

## Descargar como CSV o PDF {#download-project}

Tenga en cuenta lo siguiente a la hora de descargar proyectos:

* Cuando se descargan proyectos como un archivo CSV o PDF, el proyecto se puede guardar o no cuando solicita la descarga de un proyecto. Sin embargo, solo los proyectos guardados pueden [programarse](/help/analysis-workspace/export/t-schedule-report.md).

* Al descargar proyectos como un archivo PDF:
   * Las descargas pueden tardar varios minutos en exportarse, ya que el proyecto se vuelve a ejecutar en los servidores de Adobe antes de procesarse en formato PDF. Se recomienda no abandonar el proyecto hasta que el PDF se descargue en el explorador. Sin embargo, puede seguir realizando cambios en el proyecto mientras espera. Si un PDF tarda más de 5 minutos en procesarse, se le pedirá que lo envíe por correo electrónico.
   * Las descargas se representan como una sola página sin paginación.
   * Las representaciones en PDF contienen lo que está en la página en Workspace. Si un proyecto tiene paneles y visualizaciones de tamaño personalizado, deberá cambiarlos a tamaño automático (mediante el botón que hay en la esquina superior derecha) para que no se trunque el contenido.
   * Los [hipervínculos](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) que existen en las tablas de forma libre no funcionan en el PDF descargado.

Para descargar un proyecto como un archivo CSV o PDF:

1. Realice una de las siguientes acciones, en función del formato con el que desee descargar el proyecto:

   * **PDF:** Seleccione **[!UICONTROL Proyecto]** > **[!UICONTROL Descargar PDF]**.

     Elija esta opción si desea que el archivo descargado contenga todas las tablas y visualizaciones mostradas (visibles) en el proyecto.

   * **CSV:** Seleccione **[!UICONTROL Proyecto]** > **[!UICONTROL Descargar CSV]**.

     Elija esta opción si desea que el archivo descargado sea de texto sin formato.

   ![Menú desplegable Proyecto con las opciones Descargar CSV y Descargar PDF resaltadas.](assets/download-project.png)

1. (Condicional) Si elige descargar un PDF, se muestra un mensaje después de que el proyecto esté listo para descargarse. Seleccione [!UICONTROL **Descargar**].

## Copiar al portapapeles (tecla de acceso directo: Ctrl + C) {#copy-data}

La opción que aparece al hacer clic con el botón derecho del ratón **[!UICONTROL Copiar al portapapeles]**, le permite copiar datos rápidamente desde Workspace y pegarlo en una herramienta de terceros.

* Si desea que se copie la tabla mostrada, haga clic con el botón derecho en el encabezado de la tabla y seleccione **Copiar datos al portapapeles**.
* Si desea que se copie un subconjunto de datos, realice una selección en la tabla y, a continuación, haga clic con el botón derecho > **Copiar selección al portapapeles**.

>[!TIP]
>
>Puede utilizar la tecla de acceso directo `Ctrl+C` para copiar la selección en el portapapeles, después utilice `Ctrl+V` para pegarla en una herramienta de terceros.


![Opción Copiar selección al portapapeles. ](assets/copy-selection.png)

## Descargar como CSV {#download-data}

La opción **[!UICONTROL Descargar datos como CSV]** del botón secundario le permite descargar una tabla de datos de Customer Journey Analytics o la fuente de datos de cualquier visualización como un archivo CSV.

* Desde el encabezado de cualquier tabla o visualización, haga clic con el botón derecho y seleccione **[!UICONTROL Descargar datos como CSV]**. Se descargarán los datos visualizados de Customer Journey Analytics en la tabla o la fuente de datos subyacente para visualizarse como un archivo CSV. 

  >[!NOTE]
  >
  >  Nota: la visualización Mapa no admite esta opción.


* Dentro de una tabla, haga clic con el botón derecho y seleccione **[!UICONTROL Descargar selección como CSV]**. Solo la selección se descarga con esta opción, a diferencia de la tabla mostrada completa.

![Opción Descargar datos como CSV.](assets/download-data-viz.png)

## Descargar elementos como CSV {#download-items}

Si desea analizar más de las 400 filas de datos visibles en una tabla, haga clic con el botón derecho en cualquier encabezado de tabla o fila y seleccione **Descargar elementos como CSV (_Nombre de la dimensión_)**.  Esta opción exporta hasta 50 000 elementos de dimensión (según la clasificación de la tabla) para la dimensión seleccionada, con opciones de clasificación y filtros aplicados. Si elige esta opción en la parte superior de la tabla, se exporta la primera dimensión de la tabla. Aunque no se aplican límites en la tabla de forma libre, se recomienda utilizar la opción Descargar elementos en tablas con menos de 20 columnas para garantizar un rendimiento óptimo.

>[!TIP]
>
> Si la dimensión supera los 50 000 elementos, descargue el archivo con diferentes métricas de ordenación aplicadas o aplique un segmento. Por ejemplo, ordenar de forma descendente por Visitas en una descarga y, a continuación, ascendente por Visitas en una segunda descarga. Esta sugerencia puede ayudarle a recuperar elementos de mayor longitud.

Puede realizar varias tareas dentro del proyecto e incluso desplazarse a un nuevo proyecto de Workspace en la misma pestaña mientras la descarga está en curso. La descarga se detendrá si abre una nueva pestaña del explorador. La descarga se cancelará si deja Workspace por completo o si cierra la pestaña del explorador.

![Opción Descargar elementos como CSV (página).](assets/download-items.png)

### Archivo de elementos descargados {#items-file}

Las funciones de la tabla se aplicarán al archivo descargado de la siguiente manera:

* Todos los segmentos del panel se aplican como filtros.
* Los desgloses **superiores** a la dimensión seleccionada en la tabla se aplican como filtros encima de cada columna.
* Los desgloses **inferiores** a las dimensiones seleccionadas en la tabla se eliminan.

En el ejemplo anterior, los elementos de página se descargan con el filtro de panel (Clientes de nuevos visitantes) y los componentes anteriores (Canal de marketing = Correo electrónico) aplicados como filtros, y los componentes siguientes (Tipo de dispositivo móvil) se eliminan del CSV descargado.

![El archivo .csv descargado se ha abierto en Excel.](assets/downloaded-file.png)

### Descarga de notificaciones {#notifications}

A medida que el archivo se descarga, verá una notificación informativa con el progreso. En cualquier momento, puede cancelar la descarga haciendo clic en **[!UICONTROL Cancelar descarga]**. Al cerrar el mensaje **no se** cancelará la descarga.

Una vez que el archivo se complete, verá una notificación de finalización y el archivo se descargará en el explorador.

Si solicita más de una descarga a la vez, recibirá una notificación avisando que cada descarga adicional se colocará en cola hasta que finalice la descarga anterior.

![Notificación del estado de descarga que muestra el porcentaje completado y un vínculo Cancelar descarga.](assets/toast.png)

## Descarga de datos confidenciales {#sensitive}

Si la [directiva de gobernanza de datos](/help/data-views/data-governance.md) **[!UICONTROL Aplicar descarga]** está activada en la vista de datos sobre la que crea un informe, cualquier descarga (como el envío por correo electrónico o el uso compartido de PDF) de proyectos de Workspace bloqueará los campos de datos etiquetados como confidenciales. Puede seguir analizando estos campos en el espacio de trabajo, pero, si intenta enviar un correo electrónico o compartir un proyecto de otro modo, los campos bloqueados aparecerán como vacíos en el archivo .pdf o .csv.

Si algún campo de datos etiquetado como confidencial se incluye en la [!UICONTROL vista de datos], la opción para seleccionar y copiar datos de la pantalla está restringida para todos los datos de la [!UICONTROL vista de datos].

## Preguntas más frecuentes {#faq}

| Pregunta | Respuesta |
| --- | --- |
| ¿Por qué el PDF descargado es una página? | Workspace no pagina los PDF descargados en este momento. |
| ¿Puedo exportar más de 50 000 elementos con la opción “Descargar elementos como CSV”? | Aunque cada descarga puede contener hasta 50 000 elementos de dimensión, puede cambiar el tipo de tabla para recuperar elementos de cola más largos o aplicar un filtro para descargar elementos más específicos. |
| ¿Qué hace **[!UICONTROL Copiar visualización]**? | A diferencia de [!UICONTROL **Copiar datos al portapapeles**] o [!UICONTROL **Copiar selección al portapapeles**], la opción **[!UICONTROL Copiar visualización]** del botón derecho del ratón no es una opción de exportación. Permite copiar una visualización o un panel de un lugar de Workspace a otro. Por ejemplo, de un panel a otro en el mismo proyecto o de un proyecto a otro. [Intravínculos de vídeo](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html?lang=es) |
