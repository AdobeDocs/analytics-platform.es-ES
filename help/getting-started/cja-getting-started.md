---
title: Introducción a Análisis de Viaje del Cliente
description: Introducción a Análisis de Viaje del Cliente.
translation-type: tm+mt
source-git-commit: 12ab54b09caea3b7bb5fbc345ba5e396c198a36c

---


# Introducción a Análisis de Viaje del Cliente

Para implementar el análisis de viajes del cliente, debe seguir este flujo de trabajo. Algunas tareas iniciales se realizan en Adobe Experience Platform y otras en Customer Journey Analytics.

| Tarea | Dónde se realiza | Detalles |
|---|---|---|
| **Paso 1: Obtener sus datos en Adobe Experience Platform** | Adobe Experience Platform |  |
| **Paso 2: Preparación del esquema de datos** | Adobe Experience Platform | Utilice el Modelo de datos de [Adobe Experience (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) para estandarizar los datos de experiencia del cliente y definir esquemas para la gestión de la experiencia del cliente. |
| **Paso 3: Crear un conjunto de datos basado en el esquema** | Adobe Experience Platform | Los datos de la plataforma constan de conjuntos de datos, como conjuntos de datos de correo electrónico, conjuntos de datos de CRM, conjuntos de datos de POS, conjunto de datos de Adobe Analytics, etc. Cada conjunto de datos consta de un esquema y lotes de datos. Puede crear un conjunto de datos [en la plataforma](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md)de experiencias.<br>Aunque el esquema de conjuntos de datos que se puede importar en el análisis de viajes del cliente es flexible, debe cumplir algunas reglas básicas. Es mejor asegurarse de que los datos cumplen estos requisitos antes de cargarlos en la plataforma. (Tenga en cuenta que el esquema incluye métricas y dimensiones).<br>Existen tres tipos de datos que son compatibles con el análisis del viaje del cliente:<ul><li>**Datos** del evento: Datos que representan eventos a tiempo (por ejemplo, visitas web, interacciones, transacciones, datos de POS, datos de encuestas, datos de impresiones de publicidad, etc.). Estos son datos típicos del flujo de navegación, con un ID de cliente o una ID de cookie y una marca de tiempo. Con los datos del evento, le permitimos utilizar el ID que desee.</li><li>**Datos** de búsqueda: Estos datos se utilizan para buscar valores o claves encontrados en los datos de evento o perfil. Por ejemplo, puede cargar datos de búsqueda que asignen ID numéricos en los datos del evento a nombres de producto.</li><li>**Datos** de perfil: Datos que se aplican a los visitantes, usuarios o clientes en los datos del evento. Por ejemplo, le permite cargar datos de CRM sobre sus clientes.</li></ul> |
| **Paso 3: Creación de conexiones entre conjuntos de datos de plataforma y Análisis del viaje del cliente** | Análisis de Recorrido del cliente | Consulte [Creación de una conexión](/help/connections/create-connection.md). |
| **Paso 4: Creación de vistas de datos** | Análisis de Recorrido del cliente | See [Create a data view](/help/data-views/create-dataview.md). |
| **Paso 5: Informar sobre los datos multicanal en Workspace** | Análisis de Recorrido del cliente | Consulte [Realizar análisis](/help/projects/perform-basic-analysis.md) básicos y [Realizar análisis](/help/projects/perform-adv-analysis.md)avanzados. |

## Requisitos previos

El análisis de viajes del cliente está disponible para los clientes que

* Son clientes [de Adobe Analytics Select, Prime o Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) , y
* Están aprovisionados para la plataforma [de](https://www.adobe.com/experience-platform.html)Adobe Experience y
* Ha adquirido la SKU de Análisis de viajes del cliente

## Preparación del esquema de datos

[Creación de un esquema mediante el Editor de esquemas](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)

## Paso 1: Obtener sus datos en Adobe Experience Platform

Para poder aprovechar los datos de la plataforma de experiencia en CJA, debe ingerirlos en la plataforma. Existen varias formas de hacerlo:

* Si desea introducir los datos existentes de Adobe Analytics, utilice el conector de plataforma de Adobe Analytics.
* Para introducir otros datos, utilice archivos en formato .csv o Parquet para


## Paso 1 a: Incorporar los datos de Analytics existentes en Adobe Experience Platform

Utilice el conector de plataforma de Adobe Analytics para incluir datos tradicionales de Analytics en la plataforma. Puede crear una conexión de origen por grupo de informes. Consulte [Creación de una conexión de origen con Adobe Analytics](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) en la documentación de Adobe Experience Platform.

Una vez creada la conexión, se crea automáticamente un esquema de destino y un conjunto de datos para contener los datos entrantes. Además, se rellenan los datos de forma retroactiva y se ingieren hasta 13 meses de datos históricos. Cuando se complete la ingestión inicial, puede continuar con el paso x para crear una conexión entre este conjunto de datos de Analytics y el análisis de viajes del cliente.

## Paso 1 b: Crear un esquema




