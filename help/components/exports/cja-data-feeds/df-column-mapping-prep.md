---
description: Obtenga información sobre cómo prepararse para asignar columnas de fuentes de datos de Adobe Analytics a Customer Journey Analytics.
keywords: flujo de navegación;fuente de datos;fuente de datos;Fuente de datos
title: Preparación para asignar columnas de fuentes de datos de Adobe Analytics a Customer Journey Analytics
feature: Components
hide: true
hidefromtoc: true
exl-id: d0a9e697-1e48-4cfb-8613-2f932bf5015b
source-git-commit: b9efb621523f8bbfbb3afe7db4db2e60fcddd34c
workflow-type: tm+mt
source-wordcount: '1060'
ht-degree: 2%

---

# Preparación para asignar columnas de fuentes de datos de Adobe Analytics a Customer Journey Analytics

Customer Journey Analytics proporciona una arquitectura más flexible que Adobe Analytics para determinar las columnas que están disponibles para incluirlas en una fuente de datos. La mayoría de las organizaciones deberían esperar exportar desde Customer Journey Analytics columnas de fuentes de datos diferentes a las exportadas desde Adobe Analytics. Estas diferencias se deben a los siguientes factores:

* **[Arquitectura de esquema](#schema-architecture)**: las columnas de fuentes de datos de Adobe Analytics derivan de variables de Analytics, mientras que las columnas de fuentes de datos de Customer Journey Analytics derivan del esquema de vista de datos.

* **[Procesamiento de datos](#data-processing)**: existen diferencias fundamentales de procesamiento de datos entre Adobe Analytics y Customer Journey Analytics, especialmente la existencia de columnas preprocesadas y posprocesadas para muchas columnas de Adobe Analytics.

* **[Columnas sin usar](#unused-columns)**: Adobe Analytics contiene más de 1.100 columnas de fuentes de datos. La mayoría de las organizaciones no utilizan los datos de todas las columnas que se exportan.

* **[Columnas en canales múltiples](#cross-channel-columns)**: Customer Journey Analytics admite datos en canales múltiples (como los datos del centro de llamadas), que no están disponibles en Adobe Analytics.

Antes de empezar a asignar columnas de fuentes de datos de Adobe Analytics a columnas de fuentes de datos de Customer Journey Analytics, revise las secciones siguientes para comprender mejor estos factores clave que afectan a la asignación.

Después de revisar esta información, siga las instrucciones de asignación de cada columna de fuente de datos de Adobe Analytics que planee mantener en Customer Journey Analytics, tal como se describe en [Referencia de columna de datos](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

## Arquitectura de esquemas

Customer Journey Analytics proporciona una arquitectura más flexible que Adobe Analytics para determinar qué columnas están disponibles para incluir en una fuente de datos:

### Arquitectura de Adobe Analytics

Hay disponible una lista estática predefinida de variables que se pueden incluir como columnas de fuentes de datos.

Es fácil incluir todas las columnas y muchos clientes lo hacen, incluso cuando los datos contenidos en esas columnas no se utilizan en toda la organización.

### Arquitectura de Customer Journey Analytics

Cualquier componente que se incluya en el esquema de vista de datos se puede incluir como columnas de fuente de datos. Para obtener información detallada sobre este proceso para cada posible columna de fuente de datos de Adobe Analytics, consulte [Referencia de columna de datos](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

Los componentes se incluyen en el esquema de vista de datos de cualquiera de las formas descritas en la siguiente tabla:

| Método para la inclusión en el esquema de vista de datos | Información adicional |
|---------|----------|
| Los campos de esquema XDM se depuran como componentes en la vista de datos | Los campos que existen en el esquema XDM pasan a formar parte del esquema de vista de datos en Customer Journey Analytics después de depurarse como componentes en la vista de datos. <p>El número de campos disponibles de forma predeterminada en el esquema XDM de Customer Journey Analytics puede variar según la forma en que se recopilen los datos para la implementación de Customer Journey Analytics, de la siguiente manera:</p><ul><li>**Nuevas implementaciones de Web SDK**: Si su implementación de Customer Journey Analytics usa un esquema personalizado, es probable que muchas columnas que existen en las fuentes de datos de Adobe Analytics no existan en Customer Journey Analytics. Del mismo modo, Customer Journey Analytics puede contener campos que no existen en las fuentes de datos de Adobe Analytics.<p>Si es posible, consulte al equipo o a la persona que creó el esquema XDM para la implementación de Customer Journey Analytics de su organización. Muchas de las decisiones sobre los campos Adobe Analytics que se necesitaban en Customer Journey Analytics se tomaban cuando se creaba el esquema XDM. Para obtener más información, consulte [Arquitectura del esquema para su uso con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).</p></li><li>**Implementaciones del conector de Source de Analytics**: Existen asignaciones de campo uno a uno de forma predeterminada para muchas columnas de fuentes de datos porque el conector de Source de Analytics utiliza el grupo de campos Evento de experiencia de Analytics en el esquema XDM. Para obtener información sobre qué campos de Adobe Analytics se asignan a campos de este grupo de campos, consulte [Asignaciones de campos de Analytics](https://experienceleague.adobe.com/es/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics) en la documentación de Experience Platform.</li></ul> |
| Los componentes se crean en la vista de datos utilizando campos derivados | Puede crear componentes directamente dentro de una vista de datos, creando así columnas de fuente de datos que no están disponibles en el esquema XDM. |

## Procesamiento de datos

Las diferencias de procesamiento de datos entre Adobe Analytics y Customer Journey Analytics afectan a las columnas de fuentes de datos que están disponibles para exportar, como se indica a continuación:

* **Adobe Analytics**: muchos campos de fuente de datos se exportan como dos columnas independientes: una que contiene datos preprocesados y otra que contiene datos posprocesados. (Los datos posprocesados incluyen lógica del lado del servidor, reglas de procesamiento, reglas de VISTA, reglas de persistencia de dimensiones, etc.).

  Dado que Adobe Analytics exporta datos para algunos campos en dos columnas independientes (una para los datos preprocesados y otra para los datos posprocesados), Adobe Analytics contiene más columnas de fuentes de datos que Customer Journey Analytics. Tenga esto en cuenta al asignar campos.

* **Customer Journey Analytics**: los campos están disponibles para las fuentes de datos una vez creados en la vista de datos. Normalmente, los campos de las vistas de datos de Customer Journey Analytics solo incluyen datos posteriores al procesamiento. Sin embargo, normalmente se puede aproximar la versión preprocesada de Adobe Analytics de un campo creando una segunda versión del campo en la vista de datos de Customer Journey Analytics y configurándolo para que caduque en la visita.

## Columnas no utilizadas

Hay más de 1100 columnas de fuentes de datos disponibles para exportar en Adobe Analytics. De estas columnas, no todas se utilizarán en las fuentes de datos de Customer Journey Analytics. Esta discrepancia no indica que las columnas de la fuente de datos de Customer Journey Analytics sean insuficientes.

Identifique qué columnas de fuentes de datos de Adobe Analytics utiliza su organización. Al hacerlo, se informa de qué columnas son necesarias en las fuentes de datos de Customer Journey Analytics. Para determinar qué columnas utilizar:

* **Identificar campos que solo se aplican a Adobe Analytics**: Algunas columnas de las fuentes de datos de Adobe Analytics son específicas del motor de procesamiento de datos para Adobe Analytics y, por lo tanto, no se aplican a Customer Journey Analytics. Algunos ejemplos de estas columnas son `exclude_hit` y `hit_source`.

* **Identificar campos que se aplican a su organización**: aunque no todos los clientes de Adobe Analytics exportan todas las columnas disponibles, muchos exportan más de lo que realmente utilizan.

  Antes de empezar a exportar fuentes de datos desde Customer Journey Analytics, primero debe determinar qué columnas de fuentes de datos de Adobe Analytics utiliza su organización actualmente y, a continuación, asegurarse de que esos componentes existan en el esquema de vista de datos de Customer Journey Analytics. Para recopilar esta información, póngase en contacto con los equipos o las personas de su organización que consumen contenido de fuentes de datos para Adobe Analytics.

## Columnas en canales múltiples

Customer Journey Analytics admite datos de canales cruzados (como los datos del centro de llamadas), que no están disponibles en Adobe Analytics. Estos campos multicanal son ejemplos de nuevas columnas que se pueden incluir en las fuentes de datos de Customer Journey Analytics y que no son compatibles con Adobe Analytics.

<!--

1. View the data views throughout your organization to make sure that corresponding dimensions are available. If a corresponding dimension does not exist in the data view, create it.

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view.

   

1. For each Adobe Analytics data feed field that is being used, ensure that a similar field exists in the XDM schema.

1. Verify that and that corresponding dimensions are available in the data view. If not, you need to create them. 

1. View the data views throughout your organization to see which dimensions are available. 

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view. 

## Map data feed columns from Adobe Analytics to Customer Journey Analytics

### Step 1 - Map the default columns included in Customer Journey Analytics

There are roughly 20 default fields included in all WebSDK implementations. 

Before you can map these default columns, make sure that your Customer Journey Analytics environment meets the following prerequisites:

* It uses a WebSDK implementation.

* The appropriate field groups that contain the default WebSDK fields are added to your XDM schema.If the field is not added to your schema, it is included in the payload, but ultimately dropped.

* Each default field must be curated as a component in a Customer Journey Analytics data view.

* The component settings in the data view must be equivalent to how Analytics treats it (Visit persistence or hit-level persistence).

To map the default dimensions:

1. ...

1. ...

+++ View the Adobe Analytics data feed columns that are included by default

| Adobe Analytics column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |

+++

### Step 2: Discover which additional data feed columns your consumers use

There are over 1,100 data feed columns available to be exported in Adobe Analytics. While not all Adobe Analytics customers export all of the available columns, many customers export more than they actually use. 

Before you begin mapping data feed columns, you should first:

1. Contact the teams or individuals who consume data feed content and determine which data feed columns they use.

1. View the data views throughout your organization to see which dimensions are available. 

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view. 


### Step 3 - Map each additional column

1. ...

1. ...

+++ View the Adobe Analytics data feed columns that could be mapped if they are included in your schema and data views

| Adobe Analytics column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |

+++

Notes below here. Ignore:

Do we group these columns by if you're using the WebSDK, or if you're using specific field groups.

Here's what is in Analytics, and here's what it maps to in CJA. Customers want us to "give them the mappings."

Some of these fields there is probably something like it that you could get in WebSDK. There will be some fields that aren't. Or some that are in AEP that aren't in here (like call center data).

We have an XDM field mappings to Analytics variables. "Adobe analytics XDM Var - first hit on Google." If you set your XDM payload to the given field on the left, it will automatically be associated to the Analytics variable on the right. But we're looking for a reverse mapping of this. 









If you're using ADC, you'll have the AA column name in there. We also have an ADC mapping doc page. (Analytics field mappings doc page maps the fields)



Make a table (or a section) that talks about fields that are new to CJA, like cross-channel fields (call center, etc.) 

The number of AA columns that they can map is not going to be that big (maybe 100). The number of columns that don't map will be huge.

## Data feed column reference

### Adobe Analytics data feed columns that are included by default in Customer Journey Analytics WebSDK implementations

### Adobe Analytics data feed columns that can be included in Customer Journey Analytics data feed

### Adobe Analytics data feed columns that don't apply to Customer Journey Analytics


### Columns, descriptions, and data types

Use this section to learn what data is contained in each column. Most implementations don't use every column, so this section can be referenced when determining which columns to include in a data feed export.

-->
