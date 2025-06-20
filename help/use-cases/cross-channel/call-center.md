---
title: Importación de datos web y de centros de llamadas
description: Aprenda a crear conjuntos de datos que vinculen los datos de sitios web y de centros de llamadas.
exl-id: 48546227-029c-4cf9-9b7e-66d547769270
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '1141'
ht-degree: 88%

---

# Importación de datos web y de centros de llamadas

Customer Journey Analytics dispone de una función robusta y muy útil que permite combinar conjuntos de datos de diferentes fuentes en un único proyecto del Espacio de trabajo. Utilice esta guía para comprender cómo su organización puede combinar los datos del sitio web con los datos del centro de llamadas. Por ejemplo, puede comprender qué acciones realiza un cliente, qué contenido ve y qué términos busca antes de ponerse en contacto con la asistencia al cliente. Puede determinar el contenido y las herramientas de autoservicio para mejorar, de modo que los clientes puedan resolver los problemas por sí mismos sin necesidad de llamar.

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

Customer Journey Analytics requiere un identificador común para generar un [conjunto de datos combinado](/help/connections/combined-dataset.md).

* Si los conjuntos de datos ya tienen un identificador común en cada evento de ambos conjuntos de datos, puede omitir este paso y continuar con la creación de una conexión.
* Si alguno de los conjuntos de datos tiene un identificador común solo en algunos eventos, puede unir los datos mediante [Vinculación](/help/stitching/overview.md) para ver los pasos que permiten el análisis en canales múltiples para estos dos conjuntos de datos.

## Crear una conexión en Customer Journey Analytics

[Crear una conexión](/help/connections/create-connection.md) en Customer Journey Analytics.

* Si se utiliza AEC, encontrará un nuevo conjunto de datos vinculado disponible para el uso. Utilice el campo de ID de vinculación recién creado como ID de persona.
* De lo contrario, puede seleccionar los conjuntos de datos originales del sitio web y el centro de llamadas para utilizarlos en la conexión.

## Creación de una vista de datos

Después de crear una conexión, puede [Crear una vista de datos](/help/data-views/create-dataview.md) para utilizarla en Analysis Workspace. Los componentes útiles incluyen:

* Dimensión de página con último contacto y persistencia de sesión. Puede conectar las métricas del centro de llamadas con la última página que vio un cliente antes de llamar.
* Una métrica de llamadas que utiliza un campo de esquema Motivo del centro de llamadas para aumentar las ocurrencias. Utilice [la anulación de deduplicación de métricas](/help/data-views/component-settings/metric-deduplication.md) para que aumente solo una vez por sesión.

## Creación de visualizaciones

Las siguientes visualizaciones se pueden utilizar para obtener información de su conjunto de datos vinculado.

### Superposición de conjuntos de datos

Esta visualización le ayuda a conocer el rendimiento de AEC a la hora de vincular los datos.

1. Cree dos segmentos. La variable utilizada en estos dos segmentos es la misma variable mencionada anteriormente que refleja el origen de los datos de cada evento. Consulte [Crear un segmento](/help/components/segments/seg-create.md) para obtener más información.
   * Contenedor personal en el que el ID del conjunto de datos es igual a los datos del sitio web
   * Contenedor personal en el que el ID del conjunto de datos es igual a los datos del centro de llamadas
2. En Analysis Workspace, arrastre una visualización [Venn](/help/analysis-workspace/visualizations/venn.md) al lienzo del área de trabajo.
3. Arrastre los dos segmentos recién creados al área **[!UICONTROL Agregar segmento]** y la métrica Personas al área **[!UICONTROL Agregar métrica]**.

La visualización Venn resultante muestra el número de personas del conjunto de datos que contienen datos del sitio web y del centro de llamadas. Cuanto mayor sea la superposición, más personas se habrán vinculado correctamente. Las áreas que no se superponen representan a las personas que residen exclusivamente en un conjunto de datos u otro.

### Atribución de eventos del centro de llamadas a páginas web

Esta tabla de forma libre le permite ver las páginas principales que contribuyen a los eventos del centro de llamadas. En primer lugar, asegúrese de que las dimensiones y métricas deseadas tienen el modelo de atribución correcto:

1. Arrastre la dimensión que contiene los nombres de su página web a una visualización de tabla de forma libre.
1. Reemplace la métrica por la métrica del centro de llamadas de la que desee medir.
1. Haga clic en el icono de engranaje que se encuentra cerca del encabezado de la métrica. Haga clic en **[!UICONTROL Utilizar modelo de atribución no predeterminado]**.
1. Configure el [modelo de atribución](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md) deseado. Por ejemplo, un modelo de decadencia de tiempo con una semivida de 15 minutos y una ventana retrospectiva de sesión. Este modelo de atribución da crédito a las páginas que preceden a la llamada a su centro de llamadas.

El informe resultante muestra las páginas principales que dirigen las llamadas al centro de llamadas. <!-- use case behind what we use these pages for -->

<!-- Complement with donut visualization -->

Puede aumentar aún más la perspectiva con esta tabla dividiendo las llamadas por motivo o categoría.

1. Haga clic en el corchete derecho debajo de la dimensión Razón de la llamada en la lista de componentes. Esta acción revela valores de dimensión individuales.
2. Arrastre los valores de dimensión deseados en la métrica Llamadas, que segmenta esa métrica por cada motivo de llamada respectivo.
3. Repita el proceso por cada motivo de llamada en el que desee profundizar. Utilice el segmento &quot;Todas las sesiones&quot; para ver el total acumulado.

<!-- screenshot -->

### Visualización de flujo

Puede obtener información sobre lo que un cliente intentaba hacer antes de utilizar el canal del centro de llamadas. Esta visualización de flujo le ayuda a comprender los recorridos más frecuentes que un cliente emplea para llegar a su centro de llamadas. Esta perspectiva le permite determinar las mejoras más efectivas que puede realizar en el sitio, de modo que es menos probable que los clientes llamen.

1. Haga clic en la pestaña **[!UICONTROL Visualizaciones]** de la izquierda y arrastre la visualización deseada al lienzo del espacio de trabajo.
2. Haga clic en la pestaña **[!UICONTROL Componentes]** a la izquierda y busque la dimensión Razón de la llamada.
3. Haga clic en corchete derecho junto a esta dimensión. Esta acción revela valores de dimensión individuales.
4. Arrastre el elemento de dimensión del motivo de la llamada deseado a la ubicación central de la visualización del flujo.
5. La visualización de flujo rellena automáticamente los motivos de llamada anterior y siguiente. Reemplace el motivo de la llamada anterior por la dimensión de página del sitio web.
6. Haga clic en el icono de engranaje en la parte superior derecha de la visualización de flujo y cambie el contenedor de flujo a **[!UICONTROL Sesión]**.

### Histograma

¿Cuántos clientes han llamado una vez, han llamado dos veces o han llamado más de 6 veces? Algunas de estas personas nunca visitan el sitio web. Utilice la visualización del histograma para determinar cuántas personas entran en cada bloque. Para las personas que nunca visitan el sitio web, ver cómo podemos animarlos a que se sirvan a sí mismos.

1. Haga clic en la pestaña **[!UICONTROL Visualizaciones]** de la izquierda y arrastre la visualización del histograma deseada al lienzo del espacio de trabajo.
2. Haga clic en la pestaña **[!UICONTROL Componentes]** a la izquierda y arrastre la métrica de llamadas a la visualización del histograma.
3. Haga clic en **[!UICONTROL Mostrar configuración avanzada]** en el centro de la visualización y personalice los bloques deseados.
4. Haga clic en **[!UICONTROL Generar]**.

<!--
### Web to call, call to web

### Fallout

Fallout sessions - session

All sessions > page views metric > calls metric

All sessions > calls metric > page views

Orrr we could also use dataset ID

step 1: all sessions
step 2: 


### Site sections that result in a call within 30 minutes

Slide 4

Create a bunch of segments - facets to their business. Segments were used because they didn't have all of these in the same dimension, so they could create everything in this report as a single dimension (really segments)

wanted to understand when someone interacts with a facet, whats the highest percentage of people that abandon that channel to call them. not from volume perspective, but percentage perspective.

use sequential segments, but you lose the ability to use attribution IQ

## What to do when you've found insight -->
