---
title: Importación de datos web y de centros de llamadas
description: Aprenda a crear conjuntos de datos que vinculen los datos de sitios web y de centros de llamadas.
exl-id: 48546227-029c-4cf9-9b7e-66d547769270
source-git-commit: a6c6620a4f4118755509e534d7d6a12bf08b4b67
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 86%

---

# Importación de datos web y de centros de llamadas

Customer Journey Analytics dispone de una función robusta y muy útil que permite combinar conjuntos de datos de diferentes fuentes en un único proyecto de Workspace. Utilice esta guía para comprender cómo su organización puede combinar los datos del sitio web con los datos del centro de llamadas. Por ejemplo, puede comprender qué acciones realiza un cliente, qué contenido ve y qué términos busca antes de ponerse en contacto con el servicio de atención al cliente. A continuación, puede determinar el contenido y las herramientas de autoservicio para mejorar, de modo que los clientes puedan resolver los problemas por sí mismos sin necesidad de llamar a .

## Requisitos previos

* El componente más importante para combinar estos dos conjuntos de datos es disponer de un identificador común entre cada fuente de datos. Algunos ejemplos son un ID de cliente, un correo electrónico con hash, un nombre de usuario de inicio de sesión o un número de teléfono.
* Acceso a Adobe Experience Platform y Customer Journey Analytics
* Si el conjunto de datos incluye registros de un sistema de respuesta de voz interactivo, Adobe recomienda procesar los datos para incluir únicamente interacciones rápidas antes de importarlos a Platform.
* Si el conjunto de datos incluye registros de llamadas, Adobe recomienda incluir las columnas siguientes:
   * Fecha y hora en que se inició la llamada
   * Motivo de la llamada
   * ID del centro de llamadas
   * ID del agente del centro de llamadas
   * Duración de la llamada
   * Resultado de la llamada
   * Coste de la llamada (si está disponible)
   * Cualquier metadato adicional de la llamada que su organización desee incluir

## Importación de datos web y de centros de llamadas en Platform

Importe los datos que desee en Adobe Experience Platform. Consulte [Crear un esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=es) e [Introducir datos](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=es) en la documentación de Adobe Experience Platform.

Al importar datos en Platform, estas sugerencias pueden ayudar a aumentar la perspectiva de los informes resultantes:

* Asegúrese de que el identificador utilizado para vincular el centro de llamadas y los datos web tenga un formato similar.
* Incluya la fuente de datos en cada conjunto de datos. Por ejemplo, incluya una columna `data_source` en cada esquema y establezca el valor de cada evento en `"Web"` o `"Call center"`, respectivamente. <!--mapper-->

## Vinculación del ID de la persona

CJA requiere un identificador común para poder generar un [conjunto de datos combinado](../connections/combined-dataset.md).

* Si los conjuntos de datos ya tienen un identificador común en cada evento de ambos conjuntos de datos, puede omitir este paso y continuar con la creación de una conexión.
* Si alguno de los conjuntos de datos tiene un identificador común solo en algunos eventos, puede unir los datos con Análisis entre canales. Consulte [Información general de Análisis entre canales](/help/connections/cca/overview.md) para ver los pasos que debe seguir para habilitar AEC para estos dos conjuntos de datos.

## Creación de una conexión en CJA

[Cree una conexión](/help/connections/create-connection.md) en CJA.

* Si se utiliza AEC, encontrará un nuevo conjunto de datos vinculado disponible para el uso. Utilice el campo de ID de vinculación recién creado como ID de persona.
* De lo contrario, puede seleccionar los conjuntos de datos originales del sitio web y el centro de llamadas para utilizarlos en la conexión.

## Creación de una vista de datos

Después de crear una conexión, puede [Crear una vista de datos](/help/data-views/create-dataview.md) para utilizarla en Analysis Workspace. Los componentes útiles incluyen:

* Dimensión de página con último contacto y persistencia de sesión. Puede conectar las métricas del centro de llamadas con la última página que vio un cliente antes de llamar a .
* Una métrica de llamadas que utiliza un campo de esquema &quot;Motivo del centro de llamadas&quot; para aumentar las ocurrencias. Utilice [Deduplicación de métricas](/help/data-views/component-settings/metric-deduplication.md) para que aumente solo una vez por sesión.

## Creación de visualizaciones

Las siguientes visualizaciones se pueden utilizar para obtener información de su conjunto de datos vinculado.

### Superposición de conjuntos de datos

Esta visualización le ayuda a conocer el rendimiento de AEC a la hora de vincular los datos.

1. Cree dos filtros. La variable que se utiliza en estos dos filtros es la misma variable que la que se menciona anteriormente y que refleja el origen de datos de cada evento. Consulte [Crear un filtro](/help/components/filters/create-filters.md) para obtener más información.
   * Contenedor personal en el que el ID del conjunto de datos es igual a los datos del sitio web
   * Contenedor personal en el que el ID del conjunto de datos es igual a los datos del centro de llamadas
2. En Analysis Workspace, arrastre una visualización [Venn](/help/analysis-workspace/visualizations/venn.md) al lienzo del área de trabajo.
3. Arrastre los dos filtros recién creados al área **[!UICONTROL Añadir filtro]** y la métrica Personas al área **[!UICONTROL Añadir métrica]**.

La visualización Venn resultante muestra el número de personas del conjunto de datos que contienen datos del sitio web y del centro de llamadas. Cuanto mayor sea la superposición, más personas se habrán vinculado correctamente. Las áreas que no se superponen representan a las personas que residen exclusivamente en un conjunto de datos u otro.

### Atribución de eventos del centro de llamadas a páginas web

Esta tabla de formato libre le permite ver las páginas principales que contribuyen a los eventos del centro de llamadas. En primer lugar, asegúrese de que las dimensiones y métricas deseadas tienen el modelo de atribución correcto:

1. Arrastre la dimensión que contiene los nombres de su página web a una visualización de tabla de formato libre.
1. Reemplace la métrica por la métrica del centro de llamadas de la que desee medir la conversión.
1. Haga clic en el icono de engranaje que se encuentra cerca del encabezado de la métrica. Haga clic en **[!UICONTROL Utilizar modelo de atribución no predeterminado]**.
1. Configure el [modelo de atribución](/help/data-views/create-dataview.md) deseado.

El informe resultante muestra la métrica principal de los datos del centro de llamadas.

<!-- ### Flow between web data and call center

call reason as an exit dimension, web page name for previous pages

### Histogram

### Fallout

step 1: all sessions
step 2: purchase step 1
step 3: call

another good one

step 1: all sessions
step 2: 

Orrr we could also use dataset ID

### Site sections that result in a call within 30 minutes

Slide 4

Create a bunch of filters - facets to their business. Filters were used because they didn't have all of these in the same dimension, so they could create everything in this report as a single dimension (really filters)

wanted to understand when someone interacts with a facet, whats the highest percentage of people that abandon that channel to call them. not from volume perspective, but percentage perspective.

use sequential filters, but you lose the ability to use attribution IQ

## What to do when you've found insight -->
