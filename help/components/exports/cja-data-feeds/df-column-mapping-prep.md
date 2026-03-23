---
description: Obtenga información sobre cómo prepararse para asignar columnas de fuentes de datos de Adobe Analytics a Customer Journey Analytics.
keywords: flujo de navegación;fuente de datos;fuente de datos;Fuente de datos
title: Preparación para asignar columnas de fuentes de datos de Adobe Analytics a Customer Journey Analytics
feature: Components
hide: true
hidefromtoc: true
source-git-commit: 5dada1744a479cd4736c9fb7f3c807471e8da226
workflow-type: tm+mt
source-wordcount: '948'
ht-degree: 2%

---

# Preparación para asignar columnas de fuentes de datos de Adobe Analytics a Customer Journey Analytics

Al realizar la transición de fuentes de datos de Adobe Analytics a fuentes de datos de Customer Journey Analytics, es natural querer asignar cada columna de fuente de datos de Adobe Analytics a una columna de fuente de datos en Customer Journey Analytics.

Sin embargo, la asignación de columnas de fuentes de datos de Adobe Analytics a Customer Journey Analytics no suele ser una asignación individual. Esto se debe a los siguientes factores:

* **[Arquitectura de esquema](#schema-architecture)**: las columnas de fuentes de datos de Adobe Analytics derivan de variables de Analytics, mientras que las columnas de fuentes de datos de Customer Journey Analytics derivan de campos de esquema XDM en Experience Platform y de componentes de vista de datos en Customer Journey Analytics.

* **[Tipo de implementación](#implementation-type)**: Adobe Analytics y Customer Journey Analytics admiten varias configuraciones de implementación. Los pasos necesarios para asignar campos individuales dependen de estas implementaciones.

* **[Procesamiento de datos](#data-processing)**: existen diferencias fundamentales de procesamiento de datos entre Adobe Analytics y Customer Journey Analytics.

* **[Columnas sin usar](#unused-columns)**: Adobe Analytics contiene más de 1.100 columnas de fuentes de datos. Identifique cuál de estas columnas utiliza su organización para poder planificar la asignación de solo las columnas necesarias.

Antes de empezar a asignar columnas de fuentes de datos de Adobe Analytics a columnas de fuentes de datos de Customer Journey Analytics, revise las secciones siguientes para comprender mejor estos factores clave que afectan a la asignación.

Después de revisar esta información, siga las instrucciones de asignación de cada columna de fuente de datos de Adobe Analytics que planee mantener en Customer Journey Analytics, tal como se describe en [Referencia de columna de datos](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

## Arquitectura de esquemas

El esquema del modelo de datos de experiencia (XDM), junto con las vistas de datos utilizadas en Customer Journey Analytics, es más flexible que el modelo basado en variables de Adobe Analytics. Como tal, es probable que el esquema XDM de su organización no contenga campos que se traduzcan en asignaciones de columnas de fuente de datos de uno a uno.

Tenga en cuenta los siguientes puntos sobre la arquitectura de esquema:

* La falta de asignaciones de columna uno a uno no significa que el esquema XDM de Customer Journey Analytics sea insuficiente. En su lugar, significa que primero debe determinar qué columnas de fuentes de datos de Adobe Analytics utiliza actualmente y luego asignar solo esas columnas a fuentes de datos de Customer Journey Analytics.

* El esquema XDM de Customer Journey Analytics admite datos de canales cruzados (como los datos del centro de llamadas), que no están disponibles en Adobe Analytics. Estos campos multicanal son ejemplos de nuevas columnas que se pueden incluir en fuentes de datos de Customer Journey Analytics no compatibles con Adobe Analytics.

* Los campos solo pueden incluirse en una fuente de datos de Customer Journey Analytics después de incluirse en el esquema XDM en Experience Platform y, a continuación, depurarse para su uso en la vista de datos en Customer Journey Analytics.

  Para obtener información detallada sobre este proceso para cada posible columna de fuente de datos de Adobe Analytics, consulte [Referencia de columna de datos](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

>[!TIP]
>
>Si es posible, consulte al equipo o a la persona que creó el esquema XDM para la implementación de Customer Journey Analytics de su organización. Muchas de las decisiones sobre los campos Adobe Analytics que se necesitaban en Customer Journey Analytics se tomaban cuando se creaba el esquema XDM. Para obtener más información, consulte [Arquitectura del esquema para su uso con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

## Tipo de implementación

<!--  tons of different AA implementations + tons of different CJA schemas -->

El número de campos disponibles para asignar en el esquema XDM de Customer Journey Analytics puede variar según la forma en que se recopilen los datos para la implementación de Customer Journey Analytics, de la siguiente manera:

* **Nuevas implementaciones de Web SDK**: Si su implementación de Customer Journey Analytics usa un esquema personalizado, es probable que muchas columnas que existen en las fuentes de datos de Adobe Analytics no existan en Customer Journey Analytics. Del mismo modo, Customer Journey Analytics puede contener campos que no existen en las fuentes de datos de Adobe Analytics.

* **Implementaciones del conector de Source de Analytics**: Existen asignaciones de campo uno a uno de forma predeterminada para muchas columnas de fuentes de datos porque el conector de Source de Analytics utiliza el grupo de campos Evento de experiencia de Analytics en el esquema XDM. Para obtener información sobre qué campos de Adobe Analytics se asignan a campos de este grupo de campos, consulte [Asignaciones de campos de Analytics](https://experienceleague.adobe.com/es/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics) en la documentación de Experience Platform.

<!-- **Data layer**: ??? -->

## Procesamiento de datos

El procesamiento de datos difiere entre Adobe Analytics y Customer Journey Analytics del siguiente modo:

**Adobe Analytics**: muchos campos de fuente de datos se exportan como dos columnas independientes: una que contiene datos preprocesados y otra que contiene datos posprocesados. (Los datos posprocesados incluyen lógica del lado del servidor, reglas de procesamiento, reglas de VISTA, reglas de persistencia de dimensiones, etc.).

Dado que Adobe Analytics exporta datos para algunos campos en dos columnas independientes (una para los datos preprocesados y otra para los datos posprocesados), Adobe Analytics contiene más columnas de fuentes de datos que Customer Journey Analytics. Tenga esto en cuenta al asignar campos.

**Customer Journey Analytics**: los campos están disponibles para las fuentes de datos una vez creados en la vista de datos. Normalmente, los campos de las vistas de datos de Customer Journey Analytics solo incluyen datos posteriores al procesamiento. Sin embargo, normalmente se puede aproximar la versión preprocesada de Adobe Analytics de un campo creando una segunda versión del campo en la vista de datos de Customer Journey Analytics y configurándolo para que caduque en la visita.

## Columnas no utilizadas

Hay más de 1100 columnas de fuentes de datos disponibles para exportar en Adobe Analytics. De estas columnas, no todas se utilizarán en las fuentes de datos de Customer Journey Analytics.

Para determinar qué columnas utilizar:

* **Identificar campos que solo se aplican a Adobe Analytics**: Algunas columnas de las fuentes de datos de Adobe Analytics son específicas del motor de procesamiento de datos para Adobe Analytics y, por lo tanto, no se aplican a Customer Journey Analytics. Algunos ejemplos de estas columnas son `exclude_hit` y `hit_source`.

* **Identifique los campos que se aplican a su organización**: aunque no todos los clientes de Adobe Analytics exportan todas las columnas disponibles, muchos exportan más de lo que realmente utilizan.

  Antes de empezar a asignar columnas de fuentes de datos, identifique qué campos se están utilizando en toda la organización. Para recopilar esta información, póngase en contacto con los equipos o las personas que consumen contenido de fuentes de datos para Adobe Analytics.



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
