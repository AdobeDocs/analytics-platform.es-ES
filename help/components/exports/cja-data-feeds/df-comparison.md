---
description: Obtenga información sobre cómo comparar la funcionalidad de fuentes de datos en Customer Journey Analytics y Adobe Analytics
keywords: flujo de navegación;fuente de datos;fuente de datos;Fuente de datos
title: Comparación de la funcionalidad de las fuentes de datos en Customer Journey Analytics y Adobe Analytics
feature: Components
hide: true
exl-id: 32b71016-7c53-409f-9ce4-521a40e2eb96
autotag-review: '2026-05-19T08:44:26.806Z'
TQID: 'https://experienceleague.adobe.com/R7c5-VutwSkyghNvwC2gZv2KUEJoa263AN0Tkdg3w4o'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 82ccb1359540e5200641b33c3d4aef7f2447003f
workflow-type: tm+mt
source-wordcount: 1451
ht-degree: 1%

---

# Comparación de fuentes de datos en Customer Journey Analytics y Adobe Analytics

{{release-limited-testing}}

Las fuentes de datos tanto en Customer Journey Analytics como en Adobe Analytics permiten exportar datos sin procesar a plataformas de terceros.

Si anteriormente utilizaba fuentes de datos en Adobe Analytics, utilice la siguiente información para comprender las diferencias en las funciones y los conceptos disponibles:

## Funciones disponibles solo en fuentes de datos de Customer Journey Analytics

Si va a migrar desde Adobe Analytics, las siguientes funciones son nuevas en las fuentes de datos de Customer Journey Analytics:

* **Campos derivados**: Componentes personalizados creados a partir de transformaciones basadas en reglas que se pueden incluir en el esquema de fuentes.

* **Vinculación**: resolución de identidad entre dispositivos que vincula eventos entre dispositivos a una sola persona.

* **Modelo de datos estructurado**: las fuentes se crean y se entregan con datos estructurados en lugar de cadenas planas.

* **Carril del componente de Analysis Workspace**: seleccione dimensiones y métricas utilizando el mismo carril del componente que Analysis Workspace, en lugar de una lista estática de nombres de variables.

* **Segmentación**: los segmentos aplicados a la vista de datos se heredan automáticamente y los segmentos adicionales se pueden aplicar directamente a la fuente.

* **Zona horaria de la vista de datos**: las ventanas de entrega de fuentes se alinean con la zona horaria de la vista de datos.

* **Salida de parquet**: los archivos se entregan en formato parquet y admiten de forma nativa datos anidados y estructurados complejos.

* **Rutas de partición de estilo Hive**: los archivos de salida utilizan rutas de acceso de estilo Hive para realizar consultas eficientes en entornos de lago de datos.

* **Propagación de actualización de componentes**: los cambios en los componentes de la vista de datos se propagan automáticamente a la fuente.

<!-- * Web MCP when it's added -->

La tabla [Comparación de funcionalidades](#functionality-comparison) que aparece a continuación trata cada una de estas características en detalle, junto con las diferencias en las características que existen en ambos productos.


## Comparación de funcionalidades

| **Conceptos y opciones de configuración** | **Customer Journey Analytics** | **Adobe Analytics** |
|---------|----------|---------|
| **Entrada de datos**<br/> Tipo de datos que se pueden recopilar e incluir en las fuentes de datos. | Admite entrada de datos en canales múltiples, incluidos datos web, datos del centro de llamadas, datos del punto de venta, etc. | Admite principalmente la entrada de datos web y móviles. Se pueden introducir otros tipos de datos (como datos del centro de llamadas o del punto de venta) mediante fuentes de datos, pero con capacidades de procesamiento muy limitadas. |
| **Procesamiento de datos**<br/> Los datos se procesan en diferentes etapas, según el producto que esté usando. | Los datos se procesan a las **horas del informe** y, por lo tanto, se pueden usar muchas características de informes para cambiar los datos históricos, como la vinculación, los campos derivados y la segmentación. | Los datos se procesan a las **horas de recopilación** y, por lo tanto, las características de los informes como las reglas de procesamiento y las reglas de VISTA no afectan los datos históricos. |
| **Vinculación**<br/> Resolución de identidad en canales múltiples y entre dispositivos que vincula eventos a una sola persona. | Compatible. Las identidades vinculadas se pueden incluir en las exportaciones de fuentes de datos cuando se configura la vinculación en la conexión. | No compatible. La identidad del visitante se determina en el momento de la recopilación a partir de las cookies de ID del visitante; no está disponible la resolución entre dispositivos posterior a la recopilación. |
| **Frecuencia de envío**<br/> Determina la frecuencia con la que se envía la fuente de datos y el período de tiempo incluido en la fuente. | **Diario** (de medianoche a medianoche en el huso horario de la vista de datos) o **Por hora**. | **Diario** (de medianoche a medianoche en el huso horario del grupo de informes) o **Por hora**. <p>Las fuentes de 15 minutos son posibles, pero no están disponibles de forma predeterminada.</p> |
| **Visitas que llegan tarde**<br/> Las visitas cuyas marcas de tiempo pertenecen a una ventana de frecuencia de envío anterior pero llegan después de que esa ventana ya haya transcurrido. <p>Por ejemplo, las visitas que llegan tarde podrían proceder de una aplicación móvil que almacena en búfer los eventos sin conexión y los envía cuando se vuelve a conectar.</p> | La configuración **Demora del procesamiento** controla cuánto tiempo espera el sistema después de que se cierre la ventana de frecuencia antes de activar la exportación, lo que le da tiempo adicional para que lleguen los datos retrasados. | Las visitas que llegan tarde pueden ser **incluidas o excluidas** mediante la opción de configuración **Visitas que llegan tarde**. <p>La configuración de la ventana retrospectiva **1} controla hasta dónde llega el sistema para incluir datos retrasados.**</p> |
| **Visitas desordenadas**<br/> Visitas cuyas marcas de tiempo no coinciden con el orden en que se recibieron. | Como Customer Journey Analytics acepta datos de flujo continuo y por lotes, no hay garantías de que los eventos de una persona determinada lleguen en orden de marca de hora. Aunque Customer Journey Analytics realiza nuevos pedidos por marca de tiempo por persona, solo puede exportar los datos que han llegado. Esto significa que las visitas que llegan tarde pueden exportarse después de las visitas con una marca de tiempo posterior.<p>La configuración **Demora el procesamiento** ayuda a reducir los eventos desordenados en la salida de la fuente de datos, ya que concede más tiempo para que los datos por lotes lleguen antes de la exportación. No se garantiza el orden de los eventos en la entrega.</p><p>**Importante**: el consumidor final de los datos de la fuente de datos debe poder controlar las marcas de tiempo desordenadas por persona, ya que no se garantiza el orden de visitas en la entrega de la fuente de datos.</p> | Adobe Analytics requiere que los datos lleguen en orden por visitante en el momento de la recopilación, pero no se garantiza la ordenación de visitas en la entrega de fuentes de datos.</p> |
| **Ventana de relleno**<br/> Exporta datos históricos entre dos fechas pasadas. | Limitado a la ventana de datos móviles de la conexión. | Limitado al límite de retención de datos del grupo de informes: **25 meses** de forma predeterminada. |
| **Esquema**<br/> El esquema de la fuente de datos determina qué columnas están disponibles para incluirlas en una fuente de datos. | El esquema de fuente de datos se basa en la configuración de vista de datos.  Los componentes disponibles para incluir en el esquema de fuente de datos son un subconjunto de los componentes disponibles en la configuración de vista de datos. | Una lista estática predefinida de más de 1100 variables. Muchas columnas se exportan como **pares preprocesados y posprocesados** (por ejemplo, `eVar1` / `post_eVar1`), lo que representa gran parte del recuento de columnas. |
| **Creador de fuentes de datos**<br/> La interfaz utilizada para configurar qué columnas se incluyen en una fuente de datos. | Utiliza un carril de componentes con el mismo nombre de dimensiones y métricas disponibles en la vista de datos, que coincide con la experiencia de Analysis Workspace. | Utiliza una lista plana de nombres de variables sin procesar (como `eVar1`, `prop5`) seleccionados de un conjunto predefinido de ~1,100+ columnas. Los componentes no se denominan ni se describen más allá de su identificador de variable. |
| **Campos derivados**<br/> Componentes personalizados definidos mediante transformaciones basadas en reglas aplicadas en el tiempo del informe. | Compatible. Los componentes de campo derivados se pueden incluir en el esquema de fuente de datos junto con las dimensiones y métricas estándar. | No compatible. |
| **Actualizaciones de componentes**<br/> Si los cambios en la configuración de los componentes se reflejarán en los resultados futuros de las fuentes de datos. | Los cambios en los componentes de la vista de datos (como cambiar el nombre o eliminar una dimensión) se propagan automáticamente a futuras fuentes de datos. | No aplicable. El esquema de columna está predefinido y es estático; no hay componentes de nivel de vista de datos que actualizar. |
| **Búsquedas**<br/> Las búsquedas dinámicas permiten recibir archivos de búsqueda adicionales en la fuente de datos; de lo contrario, no estarán disponibles. | No es necesario, ya que las búsquedas y las clasificaciones están disponibles como dimensiones depuradas directamente en la vista de datos. Cuando se depura una búsqueda o clasificación como una dimensión en la vista de datos, los valores resueltos aparecen como columnas normales en la salida de Parquet, en línea con los datos de evento, no como archivos de referencia independientes. | Se utiliza para hacer coincidir un número de una columna de fuente de datos con un valor real. Específico para un determinado conjunto de elementos (explorador, sistema operativo, dispositivo móvil y se aplican como un archivo independiente que viene con la fuente de datos). |
| **Definición de sesión**<br/> Cómo se define el límite de una visita o sesión, lo cual afecta a la forma en que se agrupan y atribuyen los eventos. | Definido en la vista de datos. | Definido en el momento de la colección. |
| **Segmentación**<br/> Capacidad para filtrar el resultado de las fuentes de datos mediante segmentos. | La fuente de datos hereda automáticamente los segmentos aplicados a la vista de datos. Los segmentos adicionales también se pueden aplicar directamente a una fuente de datos individual. | No compatible. Las fuentes de datos exportan todos los datos recopilados sin filtrar los segmentos. |
| **Métricas calculadas**<br/> Métricas personalizadas que puede crear a partir de métricas existentes. | No disponible | No disponible |
| **Modelo de persistencia**<br/> Cómo persisten los valores de dimensión de un evento a otro, o si lo hacen. | Flexible. La configuración de persistencia de la vista de datos (asignación y caducidad) se aplica en el momento del informe cuando se genera la fuente. Admite todas las configuraciones de asignación disponibles en una vista de datos: **Original**, **Más reciente**, **Todos**, **Primero conocido** y **Último conocido**. | Solo se representan los modelos de atribución **más reciente (último contacto)** y **valor original (primer contacto)**. La asignación lineal se gestiona del mismo modo que el último contacto. |
| **Formato del archivo de salida**<br/> El formato usado para los archivos de salida de fuentes de datos enviados a su destino de nube. | Parquet<p>Admite de forma nativa datos anidados y estructurados complejos. Las listas de productos se representan como matrices estructuradas u objetos anidados. </p><p>Requiere una herramienta compatible con Parquet para leer, como BigQuery, Snowflake o Apache Spark.</p> | TSV<p>Filas planas legibles por humanos. No admite de forma nativa los datos estructurados; los campos complejos, como las listas de productos, deben codificarse como cadenas delimitadas por propiedad que requieran una lógica de análisis personalizada.</p> |
| **Rutas de archivo de salida**<br/> La estructura de directorio utilizada para los archivos de salida enviados. | Utiliza **rutas de partición de estilo Hive** (por ejemplo, `year=2024/month=01/day=15/`), lo que permite una eliminación eficiente de particiones al consultar datos en entornos de lago de datos como Databricks o Apache Spark. | Utiliza una estructura de directorio plana. No se admiten rutas de estilo Hive. |
| **Destinos de envío**<br/> Ubicaciones de almacenamiento en la nube a las que se pueden enviar archivos de salida de fuentes de datos. | Amazon S3, Azure RBAC, Azure SAS, Google Cloud Platform. | Amazon S3, Azure RBAC, Azure SAS, Google Cloud Platform. <p>También admite **SFTP**.</p> |

{style="table-layout:auto"}

