---
description: Exportar un proyecto de Analysis Workspace a una ubicación de la nube.
keywords: Analysis Workspace
title: Exportar informes de Customer Journey Analytics a la nube
feature: Curate and Share
hide: true
hidefromtoc: true
source-git-commit: eb7ba8dd7809164bdcddb0d484754376d5b7ca9e
workflow-type: tm+mt
source-wordcount: '1612'
ht-degree: 4%

---

# Exportar informes de Customer Journey Analytics a la nube

Puede exportar tablas completas de Workspace desde Customer Journey Analytics y enviar exportaciones a destinos de nube designados.

También hay disponibles otros métodos para exportar informes de Customer Journey Analytics, como se describe en [Información general de exportación](/help/analysis-workspace/export/export-project-overview.md).

## Exportar tablas completas desde Analysis Workspace

>[!NOTE]
>
>Antes de exportar los datos como se describe en esta sección, asegúrese de que la tabla cumpla los requisitos siguientes [Requisitos de exportación](#export-requirements).

Para exportar tablas completas desde Analysis Workspace:

1. Si aún no lo ha hecho, configure una cuenta y una ubicación de exportación como se describe en [Configuración de cuentas de exportación en la nube](/help/components/exports/cloud-export-accounts.md).

1. En Analysis Workspace, haga clic con el botón secundario en la tabla de forma libre que contiene los datos que desea exportar.

1. Seleccionar [!UICONTROL **Exportar tabla completa**].

   ![exportar tabla completa](assets/export-full-table.png)

1. En el [!UICONTROL **Nueva exportación de tabla completa**] , especifique la siguiente información:

   | Nombre del campo | Función |
   |---------|----------|
   | Nombre | Especifique un nombre para la exportación. Este nombre se muestra en la lista de exportaciones. |
   | Etiquetas | Puede aplicar una etiqueta existente a la exportación o crear una nueva y aplicarla. <p>Para aplicar una etiqueta existente a la exportación, seleccione cualquier etiqueta del menú desplegable. Puede aplicar cualquier etiqueta de su empresa<!-- double-check this -->.</p> <p>Para crear una etiqueta nueva, escriba el nombre de la etiqueta nueva y pulse Entrar.</p><p>Tenga en cuenta lo siguiente al aplicar etiquetas a una exportación: <ul><li>Las etiquetas que aplique se pueden filtrar o buscar en la tabla de exportaciones.</li> <li>Las etiquetas aplicadas a un proyecto no se aplican automáticamente al exportar una tabla completa, como se describe en &quot;Configurar columnas en la página de exportaciones&quot; en [Administración de exportaciones](/help/components/exports/manage-exports.md). (Como alternativa, cuando [programar un proyecto completo para su exportación](/help/analysis-workspace/export/t-schedule-report.md), todas las etiquetas aplicadas al proyecto se aplicarán automáticamente a la exportación).  <!-- Right now we don't have a column for them on the exports table, so this isn't true. Jaden is adding the column. --></li></ul> |
   | Descripción | Añada una descripción a la exportación. Puede elegir ver las descripciones como una columna en la [Página Exportaciones](/help/components/exports/manage-exports.md) al ver exportaciones. |
   | Vista de datos | Seleccione la vista de datos que contiene los componentes que desea incluir en la exportación. El menú desplegable Vista de datos se encuentra en la esquina superior izquierda del cuadro de diálogo y se puede identificar mediante el icono de vista de datos![icono de vista de datos](assets/data-view-icon.png).  <p>**Nota:** Si elige una vista de datos a la que le faltan componentes que ya están incluidos en la tabla de datos, se le pedirá que borre la tabla de datos y que la vuelva a crear utilizando los componentes incluidos en la vista de datos seleccionada. </p> |
   | Ventana retroactiva | Seleccione el lapso de tiempo de la creación de informes que se incluirá en cada archivo de exportación. Las opciones incluyen [!UICONTROL **Hoy**], [!UICONTROL **Ayer**], [!UICONTROL **Últimos 7 días**], [!UICONTROL **Últimos 30 días**], [!UICONTROL **Esta semana**], y [!UICONTROL **Este mes**]. |
   | Borrar | Borra el contenido de la tabla de datos. Esto le permite empezar a crear una nueva tabla directamente dentro del cuadro de diálogo de exportación Nueva tabla completa. |
   | Frecuencia de exportación | Establezca la programación de la frecuencia con la que debe producirse la exportación. <p>Puede elegir [!UICONTROL **Enviar ahora (una vez)**] para enviar la exportación solo una vez. Al seleccionar esta opción, la exportación se inicia inmediatamente.<p>O bien, puede elegir enviar la exportación según una programación definida. Al enviar una programación, las opciones incluyen [!UICONTROL **Diario**], [!UICONTROL **Semanalmente**], [!UICONTROL **Mensual por día de la semana**], [!UICONTROL **Mensual por día del mes**], [!UICONTROL **Anualmente por día del mes**], y [!UICONTROL **Anualmente por fecha específica**]. </p><p>Al seleccionar una frecuencia de exportación, tenga en cuenta lo siguiente:</p><ul><li>Las opciones de la [!UICONTROL **Ventana retroactiva**] El campo cambia según lo que seleccione aquí.<!-- if they're doing Daily, then we might not let them look back to the last year... --></li><li>Los campos de configuración adicionales se muestran según la opción elegida.</li></ul> |
   | Comienza el | El día y la hora en que debe comenzar la exportación programada. <p>Esta opción solo está disponible al elegir una frecuencia de exportación programada.</p> |
   | Finaliza el | El día y la hora en que caduca la exportación programada. La exportación programada ya no se ejecuta después de la fecha y la hora establecidas. <p>Esta opción solo está disponible al elegir una frecuencia de exportación programada.</p> |
   | Formato de archivo | Elija si los datos exportados deben estar en formato .csv o .json. |
   | Cuenta | Seleccione la cuenta de exportación de nube a la que desea enviar los datos. <p>Para obtener más información, consulte [Configuración de cuentas de exportación en la nube](/help/components/exports/cloud-export-accounts.md).</p> |
   | Nombre de la ubicación | Seleccione la ubicación de la cuenta a la que desea enviar los datos de exportación. <p>Para obtener más información, consulte [Configuración de ubicaciones de exportación de nube](/help/components/exports/cloud-export-locations.md).</p><p>Puede seleccionar el [!UICONTROL **Añadir nueva ubicación**] para crear una nueva ubicación para una cuenta de exportación existente. |

   {style="table-layout:auto"}

1. Seleccionar [!UICONTROL **Guardar**] para guardar la exportación.

   Los datos se envían a la cuenta de la nube especificada con la frecuencia especificada.

1. (Opcional) Una vez creada la exportación, tanto si elige enviarla ahora como en una programación definida, puede verla y administrarla en el [Página Exportaciones](/help/components/exports/manage-exports.md) y visualícelo en el [Exportar registros](/help/components/exports/manage-export-logs.md).</p>

## Ventajas de exportar a la nube

Exportar los datos del Customer Journey Analytics a la nube le permite:

* Exporte a una ubicación compartida, como Adobe Experience Platform Data Landing Zone, Google Cloud Platform, Microsoft Azure, Amazon S3 o Snowflake.

* Almacene grandes cantidades de datos históricos.

  Este tipo de datos se puede utilizar para detectar tendencias a largo plazo con el fin de obtener inteligencia empresarial y, en última instancia, conducir a una mejor toma de decisiones empresariales.

* Exportar tablas completas que contengan miles o millones de filas. Otros métodos de exportación permiten un máximo de 50 000 filas.

* Incluya métricas calculadas en los datos de Customer Journey Analytics exportados.

* Estructurar la salida de datos como valores concatenados.

* Exportación ad hoc o según una programación. (También disponible con [otras opciones de exportación](/help/analysis-workspace/export/export-project-overview.md).)

* Exporte archivos en formato CSV o JSON. (También disponible con [otras opciones de exportación](/help/analysis-workspace/export/export-project-overview.md).)

* Exporte tablas que incluyan varias dimensiones.

## Requisitos de exportación {#export-requirements}

### Requisitos mínimos

Las tablas deben incluir al menos una dimensión en la fila y una métrica en cada columna para ser compatibles con una exportación de tabla completa.

Los administradores deben asegurarse de que las direcciones IP enumeradas en [Direcciones IP utilizadas por el Customer Journey Analytics](/help/admin/ip-addresses.md) se incluyen en la lista de permitidos del cortafuegos.

### Funciones no admitidas

Las siguientes funciones no son compatibles y se eliminan automáticamente de las exportaciones de tabla completa:

* Porcentajes
* Totales
* Filtrado de búsqueda
* Filas estáticas
* Alineación de fechas
* Dimensiones dinámicas

  Para obtener más información, consulte [Elementos de dimensión dinámicos o estáticos en tablas de forma libre](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).
* Los Dimension del primer desglose se convierten y añaden como dimensión secundaria en la fila de la tabla exportada; cualquier otro desglose no se incluye en la tabla
* La mayoría de los conjuntos de datos no admiten la ordenación; es posible que los datos se ordenen para conjuntos de datos pequeños

### Componentes no compatibles

Los siguientes componentes no son compatibles y Analysis Workspace le pide que los elimine de la tabla al realizar una exportación de tabla completa:

* Métricas calculadas que utilizan funciones avanzadas en la definición de la métrica (consulte [Funciones avanzadas](/help/components/calc-metrics/cm-adv-functions.md) para obtener más información)
* Componentes que un administrador ha restringido para que no se exporten (consulte la *Filtro en políticas de gobernanza de datos en vistas de datos* sección en [Etiquetas y políticas](/help/data-views/data-governance.md) para obtener más información)
* Más de 5 dimensiones y 5 métricas por informe (se admiten hasta 5 dimensiones y 5 métricas)
* En columnas de la tabla:
   * Intervalos de fechas
   * Dimensiones
* En filas de la tabla:
   * Métricas calculadas 
   * Métricas
   * Intervalos de fechas
   * Filtros

### Comportamiento de atribución

La exportación de tabla completa admite métricas calculadas que utilizan un modelo de atribución no predeterminado (como se describe en la sección *Uso de modelos de atribución no predeterminados* sección en [Configuración de columna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)).

Si se utiliza un modelo de atribución no predeterminado en un informe, el modelo de asignación que se utiliza en el informe se ignora o se conserva, en función de si el informe tiene una o varias dimensiones:

* **Para informes que incluyen atribución de métricas en una sola dimensión:** [Atribución de métrica](/help/data-views/component-settings/attribution.md) anula los [modelo de asignación](/help/data-views/component-settings/persistence.md) como se hace normalmente al utilizar atribución de métrica.

  Por ejemplo, una atribución de métrica de &quot;primer contacto&quot; anula una asignación de dimensión &quot;más reciente&quot;.

* **Para informes que incluyen atribución de métricas en varias dimensiones al mismo tiempo:** [Atribución de métrica](/help/data-views/component-settings/attribution.md) se aplica además de la dimensión [modelo de asignación](/help/data-views/component-settings/persistence.md).

  Por ejemplo, se aplica una atribución de métrica de &quot;primer contacto&quot; además de una asignación de dimensión &quot;más reciente&quot;. Además, la atribución de métricas se aplicará a los pares de elementos de dimensión posasignados como si fueran elementos de dimensión únicos, en lugar de a cada elemento de dimensión de forma independiente, como se hace normalmente en una tabla de forma libre.

  >[!NOTE]
  >
  >Los informes multidimensionales solo son compatibles al exportar datos a la nube, tal como se describe en este artículo.

## Administración de exportaciones

Una vez exportados los datos desde Analysis Workspace, puede editarlos, volver a exportarlos, duplicarlos, etiquetarlos o eliminar los existentes, tal como se describe en [Administración de exportaciones](/help/components/exports/manage-exports.md).

## Ver datos exportados y archivo de manifiesto

### Datos exportados

Los datos exportados están disponibles como archivo comprimido en el destino de nube que configuró, tal como se describe en [Configuración de cuentas de exportación en la nube](/help/components/exports/cloud-export-accounts.md) y [Configuración de ubicaciones de exportación de nube](/help/components/exports/cloud-export-locations.md).

El nombre del archivo comprimido es el siguiente, en función de si eligió CSV o JSON como formato de archivo:

* `cja-export-{reportInstanceId}-{idx}.csv.gz`

* `cja-export-{reportInstanceId}-{idx}.json.gz`

>[!NOTE]
>
>Elija el formato de archivo en la [!UICONTROL **Formato de archivo**] al exportar la tabla, tal como se describe en [Exportar tablas completas desde Analysis Workspace](#export-full-tables-from-analysis-workspace).

### Archivo de manifiesto

Un archivo de manifiesto con un nombre de archivo de `cja-export-{reportInstanceId}-{idx}.json.gz` se incluye con cualquier envío de exportación correcto que contenga al menos un archivo. El archivo de manifiesto le permite confirmar que todos los archivos se entregaron correctamente. Incluye la siguiente información:

* Una lista de todos los archivos entregados

* El tamaño de cada archivo

* La marca de tiempo de cada archivo

<!-- add in  what the file name, structure, and file format will be -->

## Comparación de la exportación de tabla completa (en Customer Journey Analytics) con la Data Warehouse (en Adobe Analytics)

Si anteriormente ha utilizado Data Warehouse para exportar datos de Adobe Analytics, la siguiente tabla puede ayudarle a comprender las diferencias entre exportar tablas completas en Customer Journey Analytics y exportar datos con Data Warehouse en Adobe Analytics.


| Funcionalidad | Exportación de tabla completa en Customer Journey Analytics | Data Warehouse en Adobe Analytics |
|---------|----------|---------|
| Creación de un informe personalizado | Sí | Sí |
| Métricas calculadas  | Sí | No |
| Segmentos  | Sí | Limitado |
| Dimensiones | Límite de 5 | Sin límite |
| Métricas | Límite de 5 | Sin límite |
| Creación de informes de filas | Límite de 3 millones, 30 millones, 150 millones o 300 millones, según el nivel | Sin límite |
| Número de informes | Sin límite | Sin límite |
| Envío ad hoc | Sí | Sí |
| Programar envío recurrente | Sí | Sí |
| Envío de correo electrónico | No | Sí |
| FTP/SFTP | No | Compatibilidad con versiones anteriores |
| Azure | Sí | Sí |
| Amazon S3 | Sí | Sí |
| Google Cloud Platform | Sí | Sí |
| Snowflake | Sí | No |
| Frecuencia de entrega | Diario | Por hora |