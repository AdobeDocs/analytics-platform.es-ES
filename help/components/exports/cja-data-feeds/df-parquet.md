---
title: Uso de archivos de Parquet desde fuentes de datos de Customer Journey Analytics
description: Descubra por qué las fuentes de datos de Customer Journey Analytics proporcionan archivos de Parquet, cómo se compara Parquet con CSV, TSV y JSON, y cómo consultar o cargar los archivos.
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: f77f416ad958b28a8489d7a6eb13100ba699236e
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 0%
---
# Trabajo con archivos de Parquet en fuentes de datos

{{release-limited-testing}}

Las fuentes de datos de Customer Journey Analytics entregan archivos en formato Parquet. La mayoría de los almacenes de datos modernos pueden leer archivos de Parquet directamente, por lo que no suele ser necesario convertir los archivos antes de utilizarlos.

Utilice la siguiente información para comprender por qué las fuentes de datos utilizan Parquet, cómo se compara Parquet con otros formatos de archivo y cómo consultar o cargar archivos de Parquet en su almacén de datos.

## Ventajas de utilizar Parquet para fuentes de datos

Parquet se adapta mejor a la salida de fuente de datos que CSV, TSV o JSON por los siguientes motivos:

* **Fuentes anchas**: las fuentes de datos pueden tener cientos de columnas. Parquet permite que una consulta lea solo las columnas que necesita.

* **Campos anidados**: Parquet representa de forma nativa los campos anidados, como una lista de productos. CSV y TSV solo pueden representarlos mediante su codificación en cadenas. Para obtener más información, consulte [Componentes de subevento en las fuentes de datos](/help/components/exports/cja-data-feeds/df-sub-event.md).

* **Esquema integrado**: cada archivo de Parquet almacena su propio esquema, incluidos nombres de columna, tipos de datos y estructuras anidadas. Como el esquema está en el archivo, el almacén de datos puede crear tablas directamente a partir de los archivos. No es necesario proporcionar un archivo de encabezado o una definición de esquema independientes, y Data Warehouse no necesita deducir los tipos de datos.

* **Grandes exportaciones**: El parquet generalmente reduce los costos de almacenamiento y transferencia. También evita el análisis de texto al cargar los datos.

## Cómo se compara Parquet con CSV, TSV y JSON

CSV, TSV y JSON son formatos de archivo basados en texto comunes:

* **CSV y TSV**: Cada fila de datos es una línea de texto sin formato, con valores separados por comas (CSV) o tabulaciones (TSV). Las fuentes de datos de Adobe Analytics entregan archivos TSV. Para ver otras diferencias entre fuentes de datos en Customer Journey Analytics y Adobe Analytics, consulte [Comparar fuentes de datos en Customer Journey Analytics y Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md).

* **JSON**: cada registro se almacena como texto con campos con nombre y puede incluir matrices y objetos anidados.

La siguiente tabla detalla las diferencias entre Parquet, CSV, TSV y JSON:

| Característico | Parquet | CSV o TSV | JSON |
| --- | --- | --- | --- |
| **Velocidad de consulta** | Rápido. Una consulta solo lee las columnas que necesita. | Más lento. Se deben leer y analizar filas completas. | Más lento. Se deben leer y analizar filas completas. |
| **Tipos de datos** | Escritos. El esquema está incrustado en el archivo. | Sin tipo. Todos los valores son texto y los tipos se infieren al cargar los datos. | Escrito a máquina. |
| **Datos anidados** | Las matrices y los objetos son compatibles de forma nativa. | No compatible. Las matrices y los objetos deben aplanarse o codificarse como cadenas. | Las matrices y los objetos son compatibles de forma nativa. |
| **Legibilidad** | Requiere una herramienta como Data Warehouse, DuckDB o Python. | Se abre en un editor de texto o en una hoja de cálculo. | Se abre en un editor de texto. |

## Consultar o cargar archivos de Parquet

Los archivos de fuente de datos se entregan en formato Parquet a la ubicación de almacenamiento en la nube que seleccionó al [crear la fuente de datos](/help/components/exports/cja-data-feeds/create-feed.md).

En lugar de descargar los archivos, suele conectar el almacén de datos a la ubicación de almacenamiento. A continuación, puede utilizar los archivos de Parquet de cualquiera de las siguientes maneras:

### Consultar los archivos en contexto

Defina una tabla externa que apunte a los archivos del almacenamiento en la nube. Data Warehouse lee los archivos cuando ejecuta una consulta.

* **Snowflake**: tablas externas o consultas en una etapa externa
* **Databricks**: tablas externas a través de Amazon S3, Azure Data Lake Storage (ADLS) o Google Cloud Storage
* **BigQuery**: tablas externas a través de Google Cloud Storage
* **Amazon Redshift**: espectro Redshift sobre Amazon S3

### Cargar los archivos en tablas administradas

La carga de archivos en tablas administradas es una opción común para las cargas de trabajo recurrentes. Por ejemplo:

* **Snowflake**: `COPY INTO`
* **BigQuery**: cargar trabajos
* **Databricks**: `COPY INTO` o cargador automático

## Convertir datos de Parquet a CSV o JSON

Si los procesos descendentes requieren archivos CSV o JSON, la mayoría de los almacenes y herramientas de datos pueden exportar datos de Parquet a cualquier formato después de cargarlos. Por ejemplo, en Snowflake, puede descargar los resultados de la consulta como CSV o JSON con `COPY INTO`.
