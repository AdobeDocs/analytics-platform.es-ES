---
description: Obtenga información sobre cómo exportar una tabla completa a una ubicación de la nube.
keywords: Analysis Workspace
title: Exportar Tablas Completas A La Nube
feature: Curate and Share
exl-id: 072eadcc-43ff-42e3-86ee-82062fa02eba
role: User
source-git-commit: c4a7884ae05d9290b2974483474ba8326492d014
workflow-type: tm+mt
source-wordcount: '3234'
ht-degree: 56%

---

# Exportar tablas completas a la nube {#full-table-export}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-full-table-export"
>title="Crear exportaciones de tablas completas similares a la de Data Warehouse"
>abstract="Las exportaciones de tabla completa están disponibles en cuanto se ven los datos en Analysis Workspace. Puede crear o programar exportaciones de tabla completas según sea necesario.<br><br>Puede crear exportaciones de tabla completas en solo unos minutos si ya sabe qué datos incluir en la exportación."

<!-- markdownlint-enable MD034 -->

En Customer Journey Analytics, puede exportar tablas completas desde Analysis Workspace a destinos de nube designados.

También hay disponibles otros métodos para exportar informes de Customer Journey Analytics, como se describe en [Información general sobre la exportación](/help/analysis-workspace/export/export-project-overview.md).

## Información sobre la exportación de tablas completas

Puede exportar tablas completas desde Analysis Workspace a proveedores de servicios en la nube como Google, Azure, Amazon y Adobe.

[Las ventajas de la exportación de tabla completa](#advantages-of-full-table-export) incluyen la capacidad de exportar millones de filas, incluidas las métricas calculadas, la salida de datos de estructura en valores concatenados y mucho más.

Al exportar tablas completas, tenga en cuenta lo siguiente:

* Antes de exportar a la nube, asegúrese de que las tablas, el entorno y los permisos cumplan los [requisitos mínimos de exportación](#minimum-requirements).

* Algunas [características](#unsupported-features) y [componentes](#unsupported-components) no son compatibles al exportar tablas completas a la nube.

Utilice el siguiente proceso al exportar tablas completas a la nube:

1. [Configure una cuenta en la nube](/help/components/exports/cloud-export-accounts.md)

1. [Configure una ubicación en la cuenta](/help/components/exports/cloud-export-locations.md)

1. [Exporte una tabla completa desde Workspace](#export-full-tables)

1. Acceda a datos en la nube desde su cuenta de la nube y [administre exportaciones en Adobe](/help/components/exports/manage-exports.md)

![Proceso de exportación de tabla completo que se describe en los pasos 1 a 4.](assets/export-full-table-process.png)

## Exportar tablas completas  {#export-from-workspace}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-details"
>title="Detalles"
>abstract="Especifique un nombre para la exportación. También puede añadir una descripción y cualquier etiqueta. Esta información ayuda a identificar la exportación en la tabla de exportaciones y en las notificaciones por correo electrónico."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-data-structure"
>title="Estructura de datos"
>abstract="Es la tabla de forma libre que está exportando. Puede modificar la estructura de datos arrastrando los componentes del panel izquierdo a la tabla. Puede aplicar un filtro arrastrando un componente al área de filtro. La tabla se actualiza dinámicamente a medida que se añaden componentes al lienzo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="export-manifest"
>title="Incluir el archivo de manifiesto"
>abstract="Cuando se selecciona, se incluye un archivo de manifiesto con cualquier envío de exportación correcto. El archivo de manifiesto le permite confirmar que todos los archivos se enviaron correctamente."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-schedule"
>title="Programación"
>abstract="Seleccione la frecuencia con la que debe producirse la exportación. Elija Enviar ahora (solo una vez) para iniciar la exportación inmediatamente. Las exportaciones programadas se inician en la fecha y la hora especificadas."

<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-destination"
>title="Destino"
>abstract="Seleccione la cuenta en la nube y la ubicación a la que desea enviar los datos. Puede elegir una cuenta y una ubicación existentes o seleccionar &#39;Añadir nuevo&#39; para crearlas. Especifique los usuarios y grupos a los que desea notificar las exportaciones que fallan o caducan."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-file-format"
>title="Formato del archivo"
>abstract="Al elegir el formato de archivo Parquet, algunos caracteres especiales incluidos en los nombres de componentes se sustituyen por guiones bajos (_). Consulte el siguiente vínculo para obtener una lista completa de los caracteres que se reemplazan."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-notifications"
>title="Notificaciones"
>abstract="Agregue usuarios y grupos a los que desee que reciban notificaciones cuando esta exportación falle o esté a punto de caducar."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>Antes de exportar los datos como se describe en esta sección, obtenga más información sobre la exportación de tabla completa en la anterior sección [Información sobre la exportación de tablas completas](#understand-full-table-export).

Para exportar tablas completas desde Analysis Workspace:

1. Si aún no lo ha hecho, configure una cuenta y una ubicación de exportación, tal como se describe en [Configurar cuentas de exportación en la nube](/help/components/exports/cloud-export-accounts.md) y [Configurar ubicaciones de exportación](/help/components/exports/cloud-export-locations.md).

1. En Analysis Workspace, haga clic con el botón derecho en el encabezado de una tabla de forma libre para mostrar el menú contextual y, a continuación, seleccione [!UICONTROL **Exportar tabla completa**].

   ![Menú contextual de tabla de forma libre con Exportar tabla completa resaltada.](assets/export-full-table.png)

1. En el cuadro de diálogo [!UICONTROL **Nueva exportación de tabla completa**], especifique la siguiente información:

   | Nombre de campo | Función |
   |---------|----------|
   | Nombre | Especifique un nombre para la exportación. Este nombre se muestra en la lista de exportaciones. |
   | Etiquetas | Puede aplicar una etiqueta existente a la exportación o crear una nueva y aplicarla. <p>Para aplicar una etiqueta existente a la exportación, seleccione cualquier etiqueta en el menú desplegable. Puede aplicar cualquier etiqueta de su empresa.</p> <p>Para crear una etiqueta nueva, escriba el nombre de la etiqueta nueva y pulse Entrar.</p><p>Tenga en cuenta lo siguiente al aplicar etiquetas a una exportación: <ul><li>Las etiquetas que aplique se pueden filtrar o buscar en la tabla de exportaciones.</li> <li>Las etiquetas aplicadas a un proyecto no se aplican automáticamente al exportar una tabla completa, como se describe en &quot;Configurar columnas en la página de exportaciones&quot; en [Administración de exportaciones](/help/components/exports/manage-exports.md). (Como alternativa, al [programar un proyecto completo para la exportación](/help/analysis-workspace/export/t-schedule-report.md), las etiquetas aplicadas al proyecto se aplican automáticamente a la exportación). </li></ul> |
   | Descripción | Añada una descripción a la exportación. Puede elegir ver las descripciones como una columna en la [página Exportaciones](/help/components/exports/manage-exports.md) al ver las exportaciones. |
   | Vista de datos | Seleccione la vista de datos que contiene los componentes que desea incluir en la exportación. El menú desplegable ![Datos](/help/assets/icons/Data.svg) Vista de datos se encuentra en la esquina superior izquierda del cuadro de diálogo.  <p>**Nota:** Si selecciona una vista de datos a la que le faltan componentes que ya están incluidos en la tabla de datos, se le pedirá que borre y vuelva a crear el panel utilizando componentes incluidos en la vista de datos seleccionada. </p> |
   | Estructura de datos | Muestra la tabla de forma libre que está exportando. Puede modificar la estructura de datos arrastrando los componentes del panel izquierdo a la tabla. Puede aplicar un filtro arrastrando un componente al área de filtro. La tabla se actualiza dinámicamente a medida que se añaden componentes al lienzo. Se pueden incluir hasta 10 columnas.<p>Cualquier segmento que se haya aplicado a toda la tabla del proyecto aparecerá encima de la tabla. Puede aplicar un segmento o un grupo de segmentos a una exportación.</p> |
   | Ventana de informe | Seleccione el lapso de tiempo de creación de informes que desea incluir en cada archivo de exportación. Las opciones incluyen [!UICONTROL **Hoy**], **[!UICONTROL Ayer]**, **[!UICONTROL Últimos 7 días]**, **[!UICONTROL Últimos 30 días]**, **[!UICONTROL Esta semana]** y **[!UICONTROL Este mes]**. <p>Esta opción no se muestra cuando la **[!UICONTROL Frecuencia de exportación]** está establecida en **[!UICONTROL Enviar ahora (una vez)]**.</p> |
   | Borrar todo | Borra el contenido de la tabla de datos. Esto le permite empezar a crear una nueva tabla directamente dentro del cuadro de diálogo Exportación de nueva tabla completa. |
   | Formato del archivo | Elija si los datos exportados deben tener el formato .csv, .json o .parquet. <p>Al elegir el formato de archivo Parquet, cualquiera de los siguientes caracteres incluidos en los nombres de componentes se reemplazarán con un guion bajo (_): <ul><li>&#39; &#39; - espacio ASCII</li><li>&#39;,&#39; - coma ASCII</li><li>&#39;;&#39; - dos puntos ASCII</li><li>&#39;{&#39; o &#39;}&#39; - llave de apertura/cierre ASCII</li><li>&#39;(&#39; o &#39;)&#39; - paréntesis ASCII de apertura/cierre</li><li>&#39;\n&#39; - nueva línea ASCII</li><li>&#39;\t&#39; - ficha ASCII</li><li>&#39;=&#39; - ASCII es igual a</li></ul></p> |
   | Incluir el archivo de manifiesto | Cuando se habilita, se incluye un archivo de manifiesto con cualquier entrega de exportación correcta. <p>El archivo de manifiesto le permite confirmar que todos los archivos se enviaron correctamente. Incluye la siguiente información:</p> <ul><li>Una lista de todos los archivos enviados</li><li>La suma de comprobación MD5 de cada archivo</li></ul><p>Los datos exportados están disponibles como un archivo comprimido en el destino en la nube que configuró, tal como se describe en [Configuración de cuentas de exportación en la nube](/help/components/exports/cloud-export-accounts.md) y [Configuración de ubicaciones de exportación en la nube](/help/components/exports/cloud-export-locations.md).</p><p>El nombre de archivo del archivo comprimido es el siguiente, dependiendo de si eligió **[!UICONTROL csv]**, **[!UICONTROL json]** o **[!UICONTROL parquet]** como formato de archivo:</p><ul> <li>`cja-export-{reportInstanceId}-{idx}.csv.gz`</li><li>`cja-export-{reportInstanceId}-{idx}.json.gz`</li><li>`cja-export-<instanceId>-<idx>.snappy.parquet`<p>Cada columna del archivo de parquet está comprimida.</p></li></ul><p>Elija el formato de archivo en el campo **[!UICONTROL Formato de archivo]** anterior.</p> |
   | Frecuencia | Establezca la programación de la frecuencia con la que debe realizarse la exportación. <p>Puede elegir [!UICONTROL **Enviar ahora (una vez)**] para enviar la exportación solo una vez. Al seleccionar esta opción, la exportación se inicia inmediatamente.</p><p>O bien, puede elegir enviar la exportación según una programación definida. Al enviar una programación, las opciones incluyen **[!UICONTROL Diario]**, **[!UICONTROL Semanal]**, **[!UICONTROL Mensual por día de la semana]**, **[!UICONTROL Mensual por día del mes]**, **[!UICONTROL Anual por día del mes]** y **[!UICONTROL Anual por fecha específica]**. </p> <p>Al seleccionar una frecuencia de exportación, tenga en cuenta lo siguiente:</p><ul><li>Las opciones del campo **[!UICONTROL Ventana retrospectiva]** cambian según lo que seleccione aquí.</li><li>Los campos de configuración adicionales se muestran según la opción elegida.</li></ul> |
   | Comienza el  | El día y la hora de inicio de la exportación programada. <p>Esta opción solo está disponible cuando se elige una frecuencia de exportación programada.</p> |
   | Finaliza el | El día y la hora de caducidad de la exportación programada. La exportación programada ya no se ejecuta después de la fecha y hora establecidas. <p>Esta opción solo está disponible cuando se elige una frecuencia de exportación programada.</p> |
   | Ver los destinos de todos los usuarios | Los administradores del sistema pueden seleccionar esta opción para ver todas las cuentas y ubicaciones, independientemente de quién las haya creado. |
   | Cuenta | Seleccione la cuenta de exportación a la nube a la que desea enviar los datos. <p>O bien, si aún no ha configurado una cuenta en la nube que desee utilizar, puede configurar una nueva cuenta:<ol><li>En el menú desplegable **[!UICONTROL Cuenta]**, seleccione **[!UICONTROL Agregar cuenta]** y, a continuación, especifique la siguiente información:<ul><li>**[!UICONTROL Nombre de la cuenta de ubicación]**: especifique un nombre para la cuenta de ubicación. Este nombre aparece al crear una ubicación  </li><li>**[!UICONTROL Descripción de la ubicación de la cuenta]**: proporcione una breve descripción de la cuenta para diferenciarla de otras cuentas del mismo tipo de cuenta.</li><li>**Poner la cuenta a disposición de todos los usuarios de su organización**: seleccione esta opción si desea permitir que otros usuarios de su organización utilicen la cuenta.</li><li>**[!UICONTROL Tipo de cuenta]**: seleccione el tipo de cuenta en la nube a la que está exportando. Los tipos de cuenta disponibles son ARN de la función Amazon S3, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake y Zona de aterrizaje de datos de AEP.</li></ul><li>Para finalizar la configuración de la cuenta, continúe con el vínculo siguiente que corresponde al **[!UICONTROL tipo de cuenta]** que ha seleccionado:<ul><li>[Zona de aterrizaje de datos de AEP](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)</li><li>[ARN de la función Amazon S3](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-accounts.md#snowflake)</li></ul></ol> |
   | Ubicación | Seleccione la ubicación de la cuenta a la que desea enviar los datos de exportación.<p>O bien, si aún no ha configurado una cuenta en la nube que desee utilizar, puede configurar una nueva cuenta:<ol><li>En el menú desplegable **[!UICONTROL Ubicación]**, seleccione **[!UICONTROL Agregar ubicación]** y, a continuación, especifique la siguiente información:<ul><li>**[!UICONTROL Nombre]**: nombre de la ubicación.</li><li>**[!UICONTROL Descripción]**: proporcione una breve descripción de la ubicación para diferenciarla de otras ubicaciones del mismo tipo de ubicación.</li><li>**Poner la ubicación a disposición de todos los usuarios de su organización**: seleccione esta opción si desea permitir que otros usuarios de su organización utilicen la ubicación.</li><li>**[!UICONTROL Ubicación de la cuenta]**: seleccione la cuenta en la que desea crear la ubicación.</li></ul><li>Para finalizar la configuración de la ubicación, continúe con el vínculo de abajo que corresponde al tipo de cuenta que seleccionó en el campo **[!UICONTROL Cuenta de ubicación]**:<ul><li>[Zona de aterrizaje de datos de AEP](/help/components/exports/cloud-export-locations.md#aep-data-landing-zone).</li><li>[ARN de función de Amazon S3](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-locations.md#snowflake)</li></ul> |
   | Notificaciones | Agregue usuarios y grupos a los que desee que reciban notificaciones cuando esta exportación falle o esté a punto de caducar. Empiece a escribir el nombre o la dirección de correo electrónico de un usuario o empiece a escribir el nombre de un grupo y, a continuación, selecciónelo cuando aparezca en la lista desplegable. |

   {style="table-layout:auto"}

1. Seleccione [!UICONTROL **Guardar**] para guardar la exportación.

   Los datos se envían a la cuenta en la nube especificada con la frecuencia especificada.

1. (Opcional) Una vez creada la exportación, tanto si decide enviarla ahora como en una programación definida, puede verla y administrarla en la [página Exportaciones](/help/components/exports/manage-exports.md) y verla en los [Registros de exportación](/help/components/exports/manage-export-logs.md).

## Administración de exportaciones

Una vez exportados los datos desde Analysis Workspace, puede editar, volver a exportar, duplicar, etiquetar o eliminar las exportaciones existentes, tal como se describe en [Administración de exportaciones](/help/components/exports/manage-exports.md).

## Ventajas de la exportación de tabla completa {#advantages}

Exportar los datos de Customer Journey Analytics a la nube le permite:

* Exportar a una ubicación compartida, como Adobe Experience Platform Data Landing Zone, Google Cloud Platform, Microsoft Azure, Amazon S3 o Snowflake.

* Almacenar grandes cantidades de datos históricos.

  Este tipo de datos se puede utilizar para detectar tendencias a largo plazo para obtener inteligencia empresarial y, en última instancia, conducir a una mejor toma de decisiones empresariales.

* Exportar tablas completas que contengan miles o millones de filas (3 millones, 30 millones, 150 millones o 300 millones de filas, según el tipo de licencia). Otros métodos de exportación permiten un máximo de 50 000 filas.

* Incluir métricas calculadas en los datos de Customer Journey Analytics exportados.

* Estructurar la salida de datos como valores concatenados.

* Exportar de una sola vez o según una programación. (También disponible con [otras opciones de exportación](/help/analysis-workspace/export/export-project-overview.md)).

* Exporte archivos en formato CSV, JSON o Parquet. (También disponible con [otras opciones de exportación](/help/analysis-workspace/export/export-project-overview.md).)

* Exportar tablas que incluyan varias dimensiones.

## Requisitos mínimos

Asegúrese de que las tablas, el entorno y los permisos cumplan los siguientes requisitos:

* **Tablas:** Todas las tablas deben incluir al menos una dimensión en la fila y una métrica en cada columna para ser compatibles con una exportación de tabla completa.

* **Entorno:** asegúrese de que las [direcciones IP](/help/technotes/ip-addresses.md) y los [dominios](/help/technotes/domains.md) utilizados por Customer Journey Analytics tengan permiso para pasar a través del firewall de su organización.

* **Permisos:** En Adobe Admin Console, los usuarios deben tener asignado un perfil de producto que tenga el permiso **[!UICONTROL Exportación de tabla completa]** asignado para exportar tablas completas. Para obtener información sobre cómo asignar un permiso a un perfil de producto en Admin Console, consulte [Permiso de Customer Journey Analytics en Admin Console](/help/technotes/access-control.md).

  >[!NOTE]
  >
  >  Los usuarios que tienen asignada la [función de administrador de productos](/help/technotes/access-control.md#product-admin-role) siempre tienen acceso para exportar tablas completas; no es necesario asignar a estos usuarios el permiso de **[!UICONTROL Exportación de tabla completa]**.


## Funciones no compatibles

Las siguientes funciones no son compatibles y se eliminarán automáticamente de las exportaciones de tabla completa:

* Porcentajes
* Totales
* Filtrado de búsqueda
* Filas estáticas
* Alineación de fechas
* Métricas de conjuntos de datos de resumen
* Elementos de dimensión dinámicos

  Los elementos de dimensión dinámicos se crean al soltar una dimensión en el encabezado de una columna en una tabla de forma libre, lo que da como resultado que la columna se filtre dinámicamente por los 5 elementos de dimensión principales. En Analysis Workspace, estos 5 elementos de dimensión principales se actualizan cada vez que se carga el proyecto. En una exportación de tabla completa, estos elementos de dimensión se vuelven estáticos. Para obtener más información, consulte [Elementos de dimensión dinámicos o estáticos en tablas de forma libre](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).
* Las dimensiones del primer desglose se convierten y añaden como dimensiones secundarias en la fila de la tabla exportada. Cualquier otro desglose no se incluye en la tabla.
* La mayoría de los conjuntos de datos no admiten la ordenación; es posible que los datos se ordenen para conjuntos de datos pequeños.

## Componentes no compatibles

Los siguientes componentes no son compatibles y Analysis Workspace le pide que los quite de la tabla cuando realice una exportación de tabla completa:

* Métricas calculadas que utilizan funciones no admitidas en la definición de la métrica (consulte [Funciones de métrica calculadas no admitidas](#unsupported-calculated-metric-functions) para obtener más información)
* Componentes que un administrador ha restringido para que no se exporten (consulte la sección *Segmento sobre políticas de control de datos en vistas de datos* en [Etiquetas y políticas](/help/data-views/data-governance.md) para obtener más información)
* Cualquier dimensión que cumpla todos los criterios siguientes:
   * Se crea a partir de un campo que forma parte de una [matriz de objetos](/help/use-cases/object-arrays.md) (similar a las variables de varios valores en Adobe Analytics).
   * Tiene [habilitada la persistencia](/help/data-views/component-settings/persistence.md).
   * No usa [dimensión de enlace](/help/use-cases/data-views/binding-dimensions-metrics.md).
* Varias dimensiones que proceden de campos que hacen referencia a diferentes [matrices de objetos](/help/use-cases/object-arrays.md). (Se permiten varias dimensiones que hagan referencia a la misma matriz de objetos).
* Más de 10 dimensiones y 10 métricas por informe (se admiten hasta 10 dimensiones y 10 métricas)
* En columnas de la tabla:
   * Intervalos de fechas
   * Dimensiones
* En filas de la tabla:
   * Métricas calculadas
   * Métricas
   * Intervalos de fechas
   * Segmentos

## Compatibilidad con funciones de métricas calculadas

Las siguientes secciones básicas y avanzadas enumeran qué funciones de métricas calculadas se admiten al exportar tablas completas:

### Compatibilidad con funciones básicas


| Función básica | Estado de soporte |
|---------|----------|
| Valor absoluto | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Máximo de columna | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Mínimo de columna | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Suma de columna | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Recuento | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Exponente | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Media | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Mediana | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Módulo | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Percentil | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Operador de potencia | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Cuartil | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Recuento de filas | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Máximo de fila | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Mínimo de fila | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Suma de fila | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Redondeo | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Raíz cuadrada | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Desviación estándar | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Varianza | ![StatusBlue](/help/assets/icons/StatusBlue.svg) planificado |

### Compatibilidad con funciones avanzadas

#### Funciones de álgebra

| Función avanzada | Estado de soporte |
|---------|----------|
| Logaritmo decimal (álgebra exponencial) | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Raíz cúbica (álgebra exponencial) | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Logaritmo natural (álgebra exponencial) | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Suelo (álgebra de ajuste numérico) | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |

#### Funciones lógicas

| Función avanzada | Estado de soporte |
|---------|----------|
| If (Lógica) | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |

#### Funciones booleanas

| Función avanzada | Estado de soporte |
|---------|----------|
| Not (lógica de operador booleana) | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| O (Lógica De Operador Booleana) | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Y (Lógica De Operador Booleano) | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |

#### Funciones de comparación

| Función avanzada | Estado de soporte |
|---------|----------|
| Menor que (lógica de comparación) | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Menor o igual que (lógica de comparación) | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Equal (Lógica de comparación) | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Mayor o igual que (lógica de comparación) | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Mayor que (lógica de comparación) | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| No es igual a (lógica de comparación) | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |


#### Funciones trigonométricas

| Función avanzada | Estado de soporte |
|---------|----------|
| Pi | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Seno (estándar) | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Coseno (estándar) | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Tangente (estándar) | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Arcoseno (estándar) | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Arcocoseno (Estándar) | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Arcotangente (estándar) | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |

#### Funciones hiperbólicas

| Función avanzada | Estado de soporte |
|---------|----------|
| Coseno hiperbólico | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Seno hiperbólico | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Tangente hiperbólica | Se admite ![StatusGreen](/help/assets/icons/StatusGreen.svg) |

#### Funciones WASKR

| Función avanzada | Estado de soporte |
|---------|----------|
| Confianza (WASKR) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Confianza (inferior) (WASKR) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Confianza (superior) (WASKR) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |

#### Funciones de distribución

| Función avanzada | Estado de soporte |
|---------|----------|
| Puntuación T (distribución T de estudiantes) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Prueba T (Distribución T De Estudiantes) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| CDF-T (distribución T de estudiantes) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Variable estandarizada (distribución normal) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Prueba Z (Distribución normal) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| CDF-Z (distribución normal) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |

#### Funciones de regresión

| Función avanzada | Estado de soporte |
|---------|----------|
| Coeficiente de correlación (regresión exponencial) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Intersección (regresión exponencial) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Y predicha (regresión exponencial) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Pendiente (Regresión exponencial) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Coeficiente de correlación (regresión lineal) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Intersección (regresión lineal) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Y predicha (regresión lineal) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Pendiente (regresión lineal) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Coeficiente de correlación (regresión logarítmica) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Intersección (regresión logarítmica) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Y predicha (regresión logarítmica) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Pendiente (regresión logarítmica) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Coeficiente de correlación (regresión potencial) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Intersección (regresión de potencia) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Y predicha (regresión potencial) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Pendiente (Regresión de potencia) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Coeficiente de correlación (regresión cuadrática) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Intersección (regresión cuadrática) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Y predicha (regresión cuadrática) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Pendiente (Regresión cuadrática) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Coeficiente de correlación (regresión recíproca) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Intersección (regresión recíproca) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Y predicha (regresión recíproca) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |
| Pendiente (Regresión recíproca) | ![StatusRed](/help/assets/icons/StatusRed.svg) no admitido |

#### Otras funciones avanzadas

| Función avanzada | Estado de soporte |
|---------|----------|
| Recuento aproximado distinto | ![StatusBlue](/help/assets/icons/StatusBlue.svg) planificado |
| Acumulativo | ![StatusBlue](/help/assets/icons/StatusBlue.svg) planificado |
| Media acumulada | ![StatusBlue](/help/assets/icons/StatusBlue.svg) planificado |
| Lift | ![StatusBlue](/help/assets/icons/StatusBlue.svg) planificado |
| Varianza de muestra | ![StatusBlue](/help/assets/icons/StatusBlue.svg) planificado |

## Comportamiento de la atribución

La exportación de tabla completa admite métricas calculadas que utilizan un modelo de atribución no predeterminado (como se describe en la sección *Uso de modelos de atribución no predeterminados* en [Configuración de columna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)).

Si se utiliza un modelo de atribución no predeterminado en un informe, el modelo de asignación que se utiliza en el informe se ignora o se conserva, en función de si el informe tiene una sola dimensión o varias:

* **En el caso de los informes que incluyen la atribución de métricas en una sola dimensión:** [la atribución de métricas](/help/data-views/component-settings/attribution.md) anula el [modelo de asignación](/help/data-views/component-settings/persistence.md) como se hace normalmente cuando se utiliza la atribución de métricas.

  Por ejemplo, una atribución de métrica de &quot;primer contacto&quot; anula una asignación de dimensión &quot;más reciente&quot;.

* **En el caso de los informes que incluyen la atribución de métricas en varias dimensiones al mismo tiempo:** [la atribución de métricas](/help/data-views/component-settings/attribution.md) se aplica además del modelo de asignación de dimensión [&#128279;](/help/data-views/component-settings/persistence.md).

  Por ejemplo, se aplica una atribución de métrica de &quot;primer contacto&quot; además de una asignación de dimensión &quot;más reciente&quot;. Además, la atribución de métricas se aplica a pares de elementos de dimensión posasignados como si fueran elementos de dimensión únicos, en lugar de a cada elemento de dimensión de forma independiente, como se hace normalmente en una tabla de forma libre.

  >[!NOTE]
  >
  >Los informes multidimensionales solo son compatibles cuando se exportan datos a la nube, tal como se describe en este artículo.

## Comparación con Data Warehouse

Si anteriormente utilizó Data Warehouse para exportar datos de Adobe Analytics, la siguiente tabla puede ayudarle a comprender las diferencias entre exportar tablas completas en Customer Journey Analytics y exportar datos con Data Warehouse en Adobe Analytics.

| Función | Exportación de tablas completas en Customer Journey Analytics | Data Warehouse en Adobe Analytics |
|---------|----------|---------|
| Crear un informe personalizado | Sí | Sí |
| Métricas calculadas | Sí | No |
| Segmentos | Sí | Limitado |
| Dimensiones | Límite de 10 | Ilimitado |
| Métricas | Límite de 10 | Ilimitado |
| Filas de informes | Límite de 3 millones, 30 millones, 150 millones o 300 millones, según el nivel | Ilimitado |
| Número de informes | Ilimitado | Ilimitado |
| Envío ad hoc (único) | Sí | Sí |
| Programar envío recurrente | Sí | Sí |
| Envío de correo electrónico | No | Sí |
| FTP / SFTP | No | Compatibilidad con versiones anteriores |
| Azure | Sí | Sí |
| Amazon S3 | Sí | Sí |
| Google Cloud Platform | Sí | Sí |
| Snowflake | Sí | No |
| Frecuencia de entrega | Diario | Por hora |
