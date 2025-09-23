---
title: Configuración de soluciones nativas de Data Warehouse
description: Obtenga información sobre cómo configurar las soluciones nativas de Data Warehouse para Experience Platform Data Mirror para Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta"
exl-id: 92cffcc5-d7a7-47f5-869d-1fc665594bf4
source-git-commit: b585187f112c2081a8e51bd84d9f95e75ceebdc3
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Configuración de soluciones nativas de Data Warehouse

{{release-limited-testing}}

Para admitir Experience Platform Data Mirror para Customer Journey Analytics, los datos que desea utilizar de las tres soluciones nativas de Data Warehouse admitidas ([[!DNL Azure Databricks]](#azure-databricks), [[!DNL Google BigQuery]](#google-bigquery), [[!DNL Snowflake]](#snowflake)) deben habilitarse para cambiar la captura de datos.


## [!DNL Azure Databricks]

Habilite **cambiar fuente de datos** en las tablas de [!DNL Azure Databricks] para usar la captura de datos modificados en la conexión de origen.

Utilice los siguientes comandos para habilitar el cambio de fuente de datos en las tablas:

**Nueva tabla**

Para aplicar el cambio de fuente de datos a una nueva tabla, debe establecer la propiedad de tabla `delta.enableChangeDataFeed` en `TRUE` en el comando `CREATE TABLE`.

```sql
CREATE TABLE student (id INT, name STRING, age INT) TBLPROPERTIES (delta.enableChangeDataFeed = true)
```

**Tabla existente**

Para aplicar el cambio de fuente de datos a una tabla existente, debe establecer la propiedad de tabla `delta.enableChangeDataFeed` en `TRUE` en el comando `ALTER TABLE`.

```sql
ALTER TABLE myDeltaTable SET TBLPROPERTIES (delta.enableChangeDataFeed = true)
```

**Todas las tablas nuevas**

Para aplicar el cambio de fuente de datos a todas las tablas nuevas, debe establecer las propiedades predeterminadas en `TRUE`.

```sql
set spark.databricks.delta.properties.defaults.enableChangeDataFeed = true;
```

Para obtener más información, lea la [[!DNL Azure Databricks] guía sobre cómo habilitar la fuente de datos para cambios](https://docs.databricks.com/aws/en/delta/delta-change-data-feed#enable-change-data-feed).

Lea la siguiente documentación para ver los pasos que debe seguir para habilitar la captura de datos modificados para la conexión de origen de [!DNL Azure Databricks]:

* [Crear una [!DNL Azure Databricks] conexión base](https://experienceleague.adobe.com/es/docs/experience-platform/sources/api-tutorials/create/databases/databricks).
* [Crear una conexión de origen para una base de datos](https://experienceleague.adobe.com/es/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).

## [!DNL Google BigQuery]

Para usar la captura de datos modificados en su conexión de origen de [!DNL Google BigQuery], vaya a la página de [!DNL Google BigQuery] en la consola de [!DNL Google Cloud] y establezca `enable_change_history` en `TRUE`. Esta propiedad habilita el historial de cambios para la tabla de datos.

Para obtener más información, lea la guía de [instrucciones de lenguaje de definición de datos en [!DNL GoogleSQL]](https://cloud.google.com/bigquery/docs/reference/standard-sql/data-definition-language#table_option_list).

Lea la siguiente documentación para ver los pasos que debe seguir para habilitar la captura de datos modificados para la conexión de origen de [!DNL Google BigQuery]:

* [Crear una [!DNL Google BigQuery] conexión base](https://experienceleague.adobe.com/es/docs/experience-platform/sources/api-tutorials/create/databases/bigquery).
* [Crear una conexión de origen para una base de datos](https://experienceleague.adobe.com/es/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).

## [!DNL Snowflake]

Habilite **seguimiento de cambios** en sus tablas [!DNL Snowflake] para usar la captura de datos de cambios en sus conexiones de origen.

En [!DNL Snowflake], habilite el seguimiento de cambios usando `ALTER TABLE` y estableciendo `CHANGE_TRACKING` en `TRUE`.

```sql
ALTER TABLE mytable SET CHANGE_TRACKING = TRUE
```

Para obtener más información, lea la [[!DNL Snowflake] guía sobre el uso de la cláusula de cambios](https://docs.snowflake.com/en/sql-reference/constructs/changes#usage-notes).

Lea la siguiente documentación para ver los pasos que debe seguir para habilitar la captura de datos modificados para la conexión de origen de [!DNL Snowflake]:

* [Crear una [!DNL Snowflake] conexión base](https://experienceleague.adobe.com/es/docs/experience-platform/sources/api-tutorials/create/databases/snowflake).
* [Crear una conexión de origen para una base de datos](https://experienceleague.adobe.com/es/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection).


>[!MORELIKETHIS]
>
>[Guía de inicio rápido de Data Mirror: crear reflejos y utilizar datos basados en modelos](model-based.md)
>
