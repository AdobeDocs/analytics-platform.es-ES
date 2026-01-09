---
title: Configuración de Experience Platform
description: Obtenga información sobre cómo configurar esquemas y conjuntos de datos para Experience Platform Data Mirror para Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: 87593d7d-9456-48f8-8d39-5c3d95fe51ec
source-git-commit: cd3baec708f1811a7cbc37dfe0a9c3af75eb97c3
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 2%

---

# Configuración de Experience Platform

{{release-limited-testing}}

Experience Platform Data Mirror para Customer Journey Analytics requiere la configuración adecuada de varios componentes de Experience Platform:

* esquema
* conjunto de datos
* conector de origen

A continuación, encontrará los detalles que debe tener en cuenta al configurar cada uno de estos componentes.

## Esquema

Debe crear un [esquema relacional](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/schema/relational){target="_blank"} que sea la tabla nativa del almacén de datos que desea reflejar. Cuando construya el esquema relacional, asegúrese de que se cumplan los siguientes requisitos:

* Cuando se le pida el tipo de esquema relacional, asegúrese de seleccionar la opción manual.
* Seleccione el esquema adecuado para el tipo de datos. Tenga en cuenta que Experience Platform Data Mirror se utiliza principalmente para datos de series temporales (por ejemplo, datos de eventos), pero también se puede utilizar para datos basados en registros (búsqueda y perfil).

* Defina los campos del esquema y sus atributos
* Configure los atributos necesarios para los campos de un esquema relacional:

   * **Clave principal**.
   * **Descriptor de versión**, que debe configurarse como número secuencial (tipo de campo de tipo entero) o como tipo de campo de fecha y hora. Cuando se utiliza un tipo de campo DateTime, el descriptor de versión define la marca de tiempo de una modificación de los datos, por ejemplo, para contener la última marca de tiempo modificada.
   * **Descriptor de marca de tiempo** (para datos de series de tiempo), que define la marca de tiempo inmutable en el momento en que se captura un evento. El descriptor de marca de tiempo no es necesario para un esquema relacional basado en registros.



## Conjunto de datos

Puede configurar un conjunto de datos para el esquema por adelantado o crear un conjunto de datos al configurar el conector de origen.
Cuando cree un conjunto de datos por adelantado o seleccione un conjunto de datos, asegúrese de que los datos utilizan un [esquema](#schema) relacional que creó anteriormente.


## Conector de fuente

Para configurar el conector de origen de las soluciones nativas del almacén de datos admitidas, utilice el flujo de trabajo Fuentes que le guiará a través de la configuración. Ese flujo de trabajo consta de los siguientes pasos:

### Autenticación

Para obtener información sobre la autenticación con la solución nativa del almacén de datos admitida, consulte la documentación de Experience Platform correspondiente:

* [Databricks de Azure](https://experienceleague.adobe.com/es/docs/experience-platform/sources/connectors/databases/databricks)
* [Google BigQuery](https://experienceleague.adobe.com/es/docs/experience-platform/sources/connectors/databases/bigquery)
* [Snowflake](https://experienceleague.adobe.com/es/docs/experience-platform/sources/connectors/databases/snowflake)


### Seleccionar datos

Una vez que se haya conectado correctamente a la solución nativa del almacén de datos, seleccione la tabla de la solución nativa del almacén de datos que desee utilizar para la duplicación de datos. Una vez seleccionado, se muestra una previsualización del contenido de los datos.


### Detalles del flujo de datos

Asegúrese de habilitar la captura de datos modificados. Verá un panel de información que explica los requisitos para la captura de datos modificados.

Especifique un conjunto de datos nuevo o existente basado en el esquema relacional que creó anteriormente. Especifique y seleccione otras opciones en la interfaz de detalles del flujo de datos.


### Asignación

Asigne los campos de la tabla en la solución nativa del almacén de datos a los campos que ha especificado para el esquema relacional.


### Programación

Defina una programación para reflejar los datos de la tabla en la solución nativa del almacén de datos con el conjunto de datos en Experience Platform.


### Revisar

Revise la configuración del conector de origen a la solución nativa del almacén de datos que admite la duplicación de datos y cambie la captura de datos.


Una vez que haya terminado la configuración del conector de origen, se crea un flujo de datos. A partir de ese momento, los cambios de datos (inserciones, actualizaciones y eliminaciones) en la solución nativa del almacén de datos se reflejarán en el conjunto de datos especificado.


>[!MORELIKETHIS]
>
>[Guía de inicio rápido de Data Mirror: crear reflejos y utilizar datos relacionales](relational.md)
>[Data Mirror (documentación de Experience Platform)](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/data-mirror/overview)
>[Esquemas relacionales (documentación de Experience Platform)](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/schema/relational)
