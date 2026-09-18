---
title: Customer Journey Analytics Export datasets
description: Describe cómo utilizar la opción Exportar conjuntos de datos para realizar copias de seguridad de los datos.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: b861f765-b18d-4be2-b4c7-c66186d37d99
autotag-review: '2026-05-19T09:38:40.111Z'
TQID: 'https://experienceleague.adobe.com/az0B0Gzzu0pbb0TbpiZjW0Y-GysEptIETtg2bBFl-Uw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: bf2b169f-d8b2-488a-97b9-f3bc9532e35c
    internal-label: Use cases, Use cases (CJA)
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '1185'
ht-degree: 3%
---
# Exportar conjuntos de datos

Este artículo describe cómo se puede usar [!DNL Customer Journey Analytics Export datasets] para implementar el siguiente [caso de uso de exportación de datos](overview.md):

- Backup de datos

## Introducción

Exportar datos mediante [!DNL Experience Platform Export datasets] le permite exportar datos de sus vistas de datos de Customer Journey Analytics a cualquier destino de almacenamiento en la nube.

A diferencia de otros métodos de exportación, Exportar conjuntos de datos no tiene un límite de fila fijo. La capacidad del destino de almacenamiento en la nube limita el tamaño de exportación, lo que convierte a esta en la funcionalidad preferida cuando necesita una copia completa y sin procesar de sus datos.

![extensión de BI](../assets/export-datasets.png)

## Más información

Para exportar conjuntos de datos sin procesar desde el lago de datos en Experience Platform, utilice destinos de almacenamiento en la nube. Esta exportación se denomina Destinos de exportación de conjuntos de datos en la terminología Destinos de Experience Platform. Para obtener una descripción general, consulte [Exportar conjuntos de datos a destinos de almacenamiento en la nube](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/ui/activate/export-datasets).

Se admiten los siguientes destinos de almacenamiento en la nube:

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [Zona de aterrizaje de datos](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Almacenamiento en la nube de Google](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3#changelog)
- [Azure Blob](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob#changelog)
- [SFTP](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/catalog/cloud-storage/sftp#changelog)


### IU de Experience Platform

Puede exportar y programar la exportación de sus conjuntos de datos a través de la interfaz de usuario de Experience Platform. En esta sección se describen los pasos que debe seguir.

#### Seleccionar destino

Cuando haya determinado el destino de almacenamiento en la nube al que desea exportar el conjunto de datos, [seleccione el destino](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). Cuando aún no haya configurado un destino para su almacenamiento en la nube preferido, debe [crear una nueva conexión de destino](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/ui/connect-destination).

Como parte de la configuración de un destino, puede definir:

- el tipo de archivo (JSON o Parquet),
- si el archivo resultante debe comprimirse o no, y
- si se debe incluir o no un archivo de manifiesto.


#### Seleccionar conjunto de datos

Cuando haya seleccionado el destino, en el siguiente paso **[!UICONTROL Seleccionar conjuntos de datos]** debe seleccionar el conjunto de datos de la lista de conjuntos de datos. Si ha creado varias consultas programadas y desea que los conjuntos de datos se envíen al mismo destino de almacenamiento en la nube, puede seleccionar los conjuntos de datos correspondientes. Consulte [Seleccionar sus conjuntos de datos](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets) para obtener más información.

#### Programación de exportación del conjunto de datos

Finalmente, programe la exportación del conjunto de datos como parte del paso **[!UICONTROL Programando]**. En ese paso, defina la programación y si la exportación del conjunto de datos es incremental. Consulte [Programar exportación del conjunto de datos](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling) para obtener más información.


#### Pasos finales

[Revise](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/ui/activate/export-datasets#review) su selección y, cuando sea correcta, comience a exportar su conjunto de datos al destino de almacenamiento en la nube.

En primer lugar, debe [verificar](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/ui/activate/export-datasets#verify) que la exportación de datos se haya realizado correctamente. Al exportar conjuntos de datos, Experience Platform crea uno o varios archivos de `.json` o `.parquet` en la ubicación de almacenamiento del destino. Se espera que los nuevos archivos se depositen en su ubicación de almacenamiento según la programación de exportación configurada. Experience Platform crea una estructura de carpetas en la ubicación de almacenamiento especificada como parte del destino seleccionado, donde deposita los archivos exportados. Se crea una carpeta nueva para cada tiempo de exportación, siguiendo el patrón: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. El nombre de archivo predeterminado se genera de forma aleatoria y garantiza que los nombres de archivo exportados sean únicos.

### API de Flow Service

También puede exportar y programar la exportación de conjuntos de datos mediante API. Los pasos involucrados están documentados en [Exportar conjuntos de datos mediante la API de Flow Service](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/api/export-datasets).

#### Introducción

Para exportar conjuntos de datos, asegúrese de que cuenta con los [permisos necesarios](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/api/export-datasets#permissions). Compruebe también que el destino admite la exportación de conjuntos de datos. Puede enviar el conjunto de datos a este destino. A continuación, debe [recopilar los valores de los encabezados obligatorios y opcionales](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) que utiliza en las llamadas a la API. También necesita [identificar las especificaciones de conexión y los ID de especificación de flujo del destino](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) al que desea exportar los conjuntos de datos.

#### Recuperar conjuntos de datos aptos

Puede [recuperar una lista de conjuntos de datos aptos](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) para la exportación y comprobar si el conjunto de datos forma parte de esa lista mediante la API [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/getDatasets).


#### Crear conexión de origen

A continuación, debe [crear una conexión de origen](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/api/export-datasets#create-source-connection) para el conjunto de datos, usando su ID único, que desea exportar al destino de almacenamiento en la nube. Utiliza la API [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/postSourceConnection).

#### Autenticar en el destino (crear conexión base)

Para autenticar y almacenar de forma segura las credenciales en su destino de almacenamiento en la nube, [cree una conexión base](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/api/export-datasets#create-base-connection) con la API [`POST /targetConnection`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/postTargetConnection).


#### Proporcionar parámetros de exportación

A continuación, debe [crear una conexión de destino adicional que almacene los parámetros de exportación](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/api/export-datasets#create-target-connection) para su conjunto de datos mediante la API [`POST /targetConnection`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/postTargetConnection). Estos parámetros de exportación incluyen ubicación, formato de archivo, compresión, etc.

#### Configurar flujo de datos

Para asegurarse de que el conjunto de datos se exporta a su destino de almacenamiento en la nube, [configure el flujo de datos](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/api/export-datasets#create-dataflow) mediante la API [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/postFlow). En este paso, puede definir la programación de la exportación mediante el parámetro `scheduleParams`.

#### Validar flujo de datos

Para [comprobar las ejecuciones correctas del flujo de datos](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs), utilice la API [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations#operation/getFlowRuns) y especifique el ID del flujo de datos como parámetro de consulta. Este ID de flujo de datos es un identificador que se devuelve al configurar el flujo de datos.

[Verificar](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/ui/activate/export-datasets#verify) que la exportación de datos se haya realizado correctamente. Al exportar conjuntos de datos, Experience Platform crea uno o varios archivos de `.json` o `.parquet` en la ubicación de almacenamiento del destino. Se espera que los nuevos archivos se depositen en su ubicación de almacenamiento según la programación de exportación configurada. Experience Platform crea una estructura de carpetas en la ubicación de almacenamiento especificada como parte del destino seleccionado, donde deposita los archivos exportados. Se crea una carpeta nueva para cada tiempo de exportación, siguiendo el patrón: `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. El nombre de archivo predeterminado se genera de forma aleatoria y garantiza que los nombres de archivo exportados sean únicos.
