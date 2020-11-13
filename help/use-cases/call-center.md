---
title: Importación de datos de centro de llamadas y web
description: Aprenda a crear un conjunto de datos que vincule los datos del centro de llamadas y del sitio web.
translation-type: tm+mt
source-git-commit: 8d2f70ad47dcf9b97808da3a04d32d3412a1f0c8
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 3%

---


# Importación de datos de centro de llamadas y web

Customer Journey Analytics ofrece la valiosa y sólida capacidad de combinar conjuntos de datos de diferentes fuentes en un único proyecto de Workspace. Utilice esta guía para comprender de qué manera su organización puede unir los datos del sitio Web a los datos que se originan en el centro de llamadas.

## Requisitos previos

* El componente más importante para combinar estos dos conjuntos de datos es un identificador común entre cada fuente de datos. Algunos ejemplos son un ID de cliente, un correo electrónico con hash, un nombre de usuario de inicio de sesión o un número de teléfono.
* Acceso a Adobe Experience Platform y Customer Journey Analytics
* Si el conjunto de datos incluye registros de un sistema interactivo de respuesta de voz, Adobe recomienda procesar los datos para incluir únicamente interacciones rápidas antes de importarlos a la plataforma.
* Si el conjunto de datos incluye registros de llamadas, Adobe recomienda incluir las siguientes columnas:
   * La fecha y hora en que se inició la llamada
   * Motivo de la llamada
   * ID del centro de llamadas
   * ID del agente del centro de llamadas
   * Duración de la llamada
   * Resultado de la llamada
   * Costo de la llamada (si está disponible)
   * Cualquier meta de llamada adicional que su organización desee incluir

## Importación de datos de centros de llamadas y Web en la plataforma

Empiece a importar datos en Adobe Experience Platform. Consulte [Creación de un esquema](https://docs.adobe.com/content/help/es-ES/experience-platform/xdm/tutorials/create-schema-ui.html) y [Ingesta de datos](https://docs.adobe.com/content/help/es-ES/experience-platform/ingestion/home.html) en la documentación de Adobe Experience Platform.

Al importar datos en la plataforma, estas sugerencias pueden ayudar a aumentar la perspectiva en los informes resultantes:

* Asegúrese de que el identificador utilizado para vincular el centro de llamadas y los datos web de forma conjunta tenga un formato similar.
* Incluya la fuente de datos en cada conjunto de datos. Por ejemplo, incluya una columna `data_source` en cada esquema y establezca el valor de cada evento en `"Web"` o `"Call center"`, respectivamente. <!--mapper-->

## Unir el ID de la persona

CJA requiere un identificador común para generar un [conjunto de datos combinado](../connections/combined-dataset.md).

* Si los conjuntos de datos ya tienen un identificador común en cada evento de ambos conjuntos de datos, puede omitir este paso y continuar con la creación de una conexión.
* Si alguno de los conjuntos de datos tiene un identificador común solo en algunos eventos, puede unir los datos mediante Análisis de canales cruzados. Consulte [Información general de Análisis de canal cruzado](/help/connections/cca/overview.md) para ver los pasos para habilitar la CCA para estos dos conjuntos de datos.

## Crear una conexión en CJA

[Cree una ](/help/connections/create-connection.md) conexión en CJA.

* Si se utiliza CCA, hay un nuevo conjunto de datos enlazado disponible para su uso. Utilice el campo de ID de vinculación recién creado como ID de persona.
* De lo contrario, puede seleccionar los conjuntos de datos originales de la Web y del centro de llamadas para utilizarlos en la conexión.

## Creación de una vista de datos

Después de crear una conexión, puede [Crear una vista de datos](/help/data-views/create-dataview.md) para utilizarla en Analysis Workspace. <!-- page dimension last touch, session persistence -->
<!-- create calls metric using call center reason (requires data views 2.0). any column that triggers once per call -->

## Creación de visualizaciones

Las visualizaciones siguientes se pueden utilizar para obtener perspectivas de su conjunto de datos enlazado.

### Superposición de conjunto de datos

Esta visualización le ayuda a comprender cuán bien CCA une los datos.

1. Cree dos filtros. La variable utilizada en estos dos filtros es la misma variable mencionada anteriormente que refleja la fuente de datos de cada evento. Consulte [Crear un filtro](/help/components/filters/create-filters.md) para obtener más información.
   * Contenedor personal donde el ID de conjunto de datos es igual a los datos web
   * Contenedor personal donde el ID de conjunto de datos es igual a los datos del centro de llamadas
2. En Analysis Workspace, arrastre una visualización [Venn](/help/analysis-workspace/visualizations/venn.md) al lienzo del área de trabajo.
3. Arrastre los dos filtros recién creados al área **[!UICONTROL Añadir filtro]** y la métrica Personas al área **[!UICONTROL Añadir métrica]**.

La visualización Venn resultante muestra el número de personas en el conjunto de datos que contienen datos de la Web y del centro de llamadas. Cuanto mayor sea el solapamiento, más personas se vincularon con éxito. Las áreas que no se superponen representan personas que residen exclusivamente en un conjunto de datos u otro.

### Eventos del centro de llamadas de atributos a páginas web

Esta tabla improvisada le permite ver las páginas principales que contribuyen a los eventos del centro de llamadas. En primer lugar, asegúrese de que las dimensiones y métricas deseadas tienen el modelo de atribución correcto:

1. Arrastre la dimensión que contiene los nombres de las páginas web a una visualización de tabla improvisada.
1. Reemplace la métrica con la métrica del centro de llamadas que desee que mida la conversión.
1. Haga clic en el icono de engranaje cerca del encabezado de la métrica. Haga clic en **[!UICONTROL Usar modelo de atribución no predeterminado]**.
1. Configure el [modelo de atribución](/help/data-views/configure-dataviews.md#Attribution-model) que desee.

El informe resultante muestra la métrica principal de los datos del centro de llamadas. <!-- Complement with donut visualization -->

<!-- ### Flow between web data and call center

call reason as an exit dimension, web page name for previous pages

### Histogram


### Fallout

step 1: all sessions
step 2: purchase step 1
step 3: call

another good one

step 1: all sessions
step 2: -->

<!--  use target (AB testing) to test new versions of these pages so they reduce calls (using an eVar to determine A/B?)
  filter by specific call reason using workspace dropdowns
  visualize flow of pages > call reason 
-->