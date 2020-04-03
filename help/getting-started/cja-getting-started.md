---
title: Introducción a Análisis de Viaje del Cliente
description: Introducción a Análisis de Viaje del Cliente.
translation-type: tm+mt
source-git-commit: fb2b5868db69bfff3345abcd69b0b70112fdcf3c

---


# Introducción a Análisis de Viaje del Cliente

Para implementar el análisis de viajes del cliente, debe seguir este flujo de trabajo. Algunas tareas iniciales se realizan en Adobe Experience Platform y otras en Customer Journey Analytics.

| Tarea | Dónde se realiza | Detalles |
|---|---|---|
| **Paso 1: Obtener sus datos en Adobe Experience Platform** | Adobe Experience Platform | Existen varias formas de ingerir datos para casos de uso por flujo continuo y por lotes, incluidas las API y una interfaz gráfica para la carga de datos. La plataforma de experiencia puede traer datos de cosas como:<ul><li>almacenamiento S3</li><li>Almacenamiento de blob de Azure</li><li>Kafka Streams</li><li>Transferencias SFTP</li><li>Cargas de archivos CSV</li><li>Cargas de archivos JSON</li></ul> |
| **Paso 2: Preparar el esquema de datos** | Adobe Experience Platform | Utilice el Modelo de datos de [Adobe Experience (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) para estandarizar los datos de experiencia del cliente y definir esquemas para la gestión de la experiencia del cliente. |
| **Paso 3: Crear un conjunto de datos basado en el esquema** | Adobe Experience Platform | Los datos de la plataforma constan de conjuntos de datos, como conjuntos de datos de correo electrónico, conjuntos de datos de CRM, conjuntos de datos de POS, conjunto de datos de Adobe Analytics, etc. Cada conjunto de datos consta de un esquema y lotes de datos. Puede crear un conjunto de datos [en la plataforma](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md)de experiencias.<br>Aunque el esquema para conjuntos de datos que se puede importar en el análisis de viajes del cliente es flexible, debe cumplir algunas reglas básicas. Es mejor asegurarse de que los datos cumplen estos requisitos antes de cargarlos en la plataforma. (Tenga en cuenta que el esquema incluye métricas y dimensiones).<br>Existen tres tipos de datos que son compatibles con el análisis del viaje del cliente:<ul><li>**Datos** de Evento: Datos que representan eventos en el tiempo (por ejemplo, visitas web, interacciones, transacciones, datos de PDV, datos de encuesta, datos de impresiones de publicidad, etc.). Estos son datos típicos del flujo de navegación, con un ID de cliente o una ID de cookie y una marca de tiempo. Con los datos de Evento, le permitimos utilizar cualquier ID que desee.</li><li>**Datos** de búsqueda: Estos datos se utilizan para buscar valores o claves encontrados en los datos de Evento o Perfil. Por ejemplo, puede cargar datos de búsqueda que asignen ID numéricos en los datos de evento a nombres de producto.</li><li>**Datos** de Perfil: Datos que se aplican a sus visitantes, usuarios o clientes en los datos de Evento. Por ejemplo, le permite cargar datos de CRM sobre sus clientes.</li></ul> |
| **Paso 4: Creación de conexiones entre conjuntos de datos de plataforma y Análisis del viaje del cliente** | Análisis de Recorrido del cliente | See [Create a connection](/help/connections/create-connection.md). |
| **Paso 5: Crear vistas de datos** | Análisis de Recorrido del cliente | See [Create a data view](/help/data-views/create-dataview.md). |
| **Paso 6: Informar sobre los datos de canales cruzados en Workspace** | Análisis de Recorrido del cliente | Consulte [Realizar análisis](/help/projects/perform-basic-analysis.md) básica y [Realizar análisis](/help/projects/perform-adv-analysis.md)avanzada. |

## Requisitos previos

El análisis de viajes del cliente está disponible para los clientes que

* Son clientes [de Adobe Analytics Select, Prime o Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) , y
* Están aprovisionados para la plataforma [de](https://www.adobe.com/experience-platform.html)Adobe Experience y
* Ha adquirido la SKU de Análisis de viajes del cliente

## Preparar el esquema de datos

[Creación de un esquema con el Editor de Esquemas](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)

## Paso 1: Obtener sus datos en Adobe Experience Platform

Para poder aprovechar los datos de la plataforma de experiencia en CJA, debe ingerirlos en la plataforma. Existen varias formas de hacerlo:

* Si desea introducir los datos existentes de Adobe Analytics, utilice el conector de plataforma de Adobe Analytics.
* Para ingerir otros datos, utilice formatos como: Almacenamiento S3, Almacenamiento Blob de Azure, Flujos Kafka, Transferencias SFTP, Cargas de archivos CSV, Cargas de archivos JSON

### Paso 1a: Incorporar los datos de Analytics existentes en Adobe Experience Platform

Utilice el conector de plataforma de Adobe Analytics incorporado para incorporar datos tradicionales de Adobe Analytics a la plataforma. Puede crear una conexión de origen por grupo de informes. Consulte [Creación de una conexión de origen con Adobe Analytics](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) en la documentación de Adobe Experience Platform.

Una vez creada la conexión, se crea automáticamente un esquema de destinatario y un conjunto de datos para contener los datos entrantes. Además, se rellenan los datos de forma retroactiva y se ingieren hasta 13 meses de datos históricos. Cuando se complete la ingestión inicial, puede continuar con `Step 4` la creación de una conexión entre este conjunto de datos de Analytics y el análisis de viajes del cliente.

### Paso 1b: Ingestar otros tipos de datos

[La ingestión](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md) por lotes permite ingerir datos en la plataforma de experiencias como archivos por lotes. Los lotes son unidades de datos que consisten en uno o más archivos que se van a ingerir como una sola unidad. Una vez ingeridos, los lotes proporcionan metadatos que describen el número de registros que se han ingestado correctamente, así como los registros con errores y los mensajes de error asociados. Los archivos de datos cargados manualmente, como archivos .CSV planos (asignados a esquemas XDM) y marcos de datos de parquet, se deben ingerir mediante este método.

[La ingestión](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md) por flujo continuo le permite enviar datos desde dispositivos cliente y servidor a la plataforma de experiencias en tiempo real.

[Otros conectores](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md) de origen le permiten ingestar datos de fuentes externas, al tiempo que le brindan la capacidad de estructurar, etiquetar y mejorar los datos entrantes mediante los servicios de plataforma. Puede ingestar datos de una variedad de fuentes, como aplicaciones de Adobe (Adobe Analytics, Administrador de Audiencias, Experience Platform Launch, Destinatario), almacenamiento basado en la nube (Azure Blob, Amazon S3, FTP/SFTP, Almacenamiento de Google Cloud), software de terceros y CRM (Microsoft Dynamics 365, Salesforce).

## Paso 2: Preparar el esquema de datos

bnbnbnbn
