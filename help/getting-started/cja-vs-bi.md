---
title: Comparar soluciones de CJA con las soluciones de BI
description: Comparar soluciones de Customer Journey Analytics con las soluciones de BI
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: ae66cd06-7ec1-4174-a3cf-939c3a66b840
source-git-commit: c21eb39e0af36ad54fd675c147e2f50b6b00711a
workflow-type: tm+mt
source-wordcount: '1588'
ht-degree: 98%

---

# Comparar soluciones de CJA con las soluciones de BI

Con el enfoque actual en la experiencia del cliente, las marcas necesitan soluciones avanzadas para comprender mejor el recorrido integral del cliente. Comprender este recorrido completo del cliente le permite analizar y obtener perspectivas valiosas sobre cómo los canales en línea y sin conexión consiguen la participación de los clientes y conducen a un aumento de la conversión, la retención y la fidelidad. Un recorrido del cliente en este contexto puede ser el simple pedido en línea de una comida en una cadena de sushi. O la compra de un nuevo coche, donde el cliente combina la investigación en línea con visitas al concesionario y una compra final en persona.

Muchas organizaciones han consolidado sus datos omnicanal en un lago de datos o almacén de datos. Las herramientas de Business Intelligence (BI) se utilizan sobre estos almacenes de datos para proporcionar los informes, visualizaciones y perspectivas que la empresa necesita para comprender el recorrido del cliente. Esta combinación de soluciones y herramientas suele tener un propósito general por naturaleza y diseño, y no se centra explícitamente en el cliente. Customer Journey Analytics (CJA) se centra en potenciar a los responsables de la experiencia del cliente, como los especialistas en marketing, los analistas de datos y los científicos de datos. La herramienta permite visualizar el recorrido del cliente en todo su contexto, a través de todos los canales y en tiempo real, sin las limitaciones que presentan muchas otras herramientas de BI.

En esta sección de la documentación se explican las diferencias fundamentales entre CJA y las herramientas de BI más utilizadas, analizando en primer lugar el flujo de trabajo general utilizado para lograr el objetivo mencionado anteriormente: comprender ese recorrido del cliente. A continuación, proporciona más detalles sobre cómo se almacenan, recopilan y consultan los datos de forma diferente entre las herramientas de CJA y de BI. Finalmente, explica las diferencias en las funcionalidades de visualización.

## Flujo de trabajo de BI tradicional

Un obstáculo frecuente con los enfoques tradicionales para analizar los recorridos de los clientes es que no están centrados en el cliente. Cada equipo recopila datos en silos, analizando y optimizando las experiencias en función de los datos a los que tiene acceso.

![Flujo de trabajo de BI típico](./assets/biworkflow.png)

Si desea comprender cómo una campaña digital específica afecta a una acción sin conexión almacenada en un silo de datos diferente, envíe una solicitud a la cola del equipo de BI. El equipo de BI escribe la consulta necesaria para adquirir y transformar los datos. Una vez recuperados los datos sin procesar, el equipo de BI crea la visualización. Los datos se le comparten y usted invierte tiempo examinando las perspectivas y extrayendo datos para activarlos en otros sistemas.

Cada uno de estos pasos puede llevar horas, días o incluso semanas. Si hay preguntas de seguimiento o problemas con los datos consultados, se puede tardar aún más tiempo en abordar esas cuestiones y el ciclo continúa. Para el análisis, la exploración y la comprensión continuos del recorrido del cliente, este proceso es ineficiente y no escalable. Además, los equipos de BI suelen ocuparse de más cuestiones que las relacionadas con el recorrido del cliente.

## CJA: flujo de trabajo democratizado para datos en línea y sin conexión

CJA proporciona un entorno para conectar datos de canales múltiples en línea y sin conexión a nivel de cliente global con el único propósito de comprender el recorrido del cliente. Requiere una configuración inicial para [connect](/help/connections/overview.md) y [definir vistas](/help/data-views/data-views.md) a los datos que usted califique como relevantes. No obstante, una vez completados, esos datos están fácilmente accesibles para su análisis y exploración continuos. Puede obtener perspectivas y comprender los recorridos de los clientes de forma progresiva. Al democratizar los datos combinados en línea y sin conexión, puede responder en cuestión de segundos a las preguntas relacionadas con el recorrido del cliente.

![Flujo de trabajo de CJA](./assets/cjaworkflow.png)

Puede utilizar CJA para formular preguntas a través del entorno visual de Analysis Workspace y obtener perspectivas de forma casi instantánea. Los datos multicanal y los informes están disponibles de inmediato, sin necesidad de código SQL. Se pueden realizar consultas y análisis adicionales con una simple operación de arrastrar y soltar en la interfaz de usuario, con datos totalmente correlacionados. Puede seguir formulando preguntas, explorando progresivamente más detalles según sus necesidades. A continuación, puede tomar medidas inmediatas en función de las perspectivas que descubra, como distribuir audiencias para su activación y orquestación.

## El potente motor de creación de informes de CJA

CJA utiliza una potente arquitectura propietaria que distribuye los análisis entre cientos o incluso miles de servidores para mostrar los datos en Analysis Workspace en cuestión de segundos. Algunas propiedades destacables de esta arquitectura de procesamiento son:

* **Optimizado para consultas individuales relacionadas con el cliente**: técnicamente, CJA almacena los datos en un motor de creación de informes distribuido que hace un amplio uso del almacenamiento en caché. Ese motor está bien adaptado para consultas adaptables sobre datos de eventos a nivel individual y, como tal, está perfectamente optimizado para consultas relacionadas con el cliente. El motor de creación de informes almacena los datos en índices de mapa de bits orientados a columnas que permiten un rápido cálculo sobre la marcha de las métricas agregadas. Dispone de un amplio motor de filtrado que permite una potente segmentación/análisis de audiencia. Además, tiene un conocimiento básico de la secuencia entre puntos de datos que resulta útil para analizar el comportamiento en esos puntos de datos (el orden en que ocurrieron las cosas) y para asignar atribuciones mediante diversos modelos complejos.

* **Aplicación rápida de rutas y filtros complejos**: el motor de creación de informes trabaja sobre conjuntos de datos jerárquicos parcialmente ordenados (por ejemplo, persona -> sesiones -> eventos). Todos los datos de un objeto de nivel superior (perfiles individuales) residen en un único nodo de procesamiento para que los resultados sean precisos. Esta partición permite la aplicación rápida de rutas y filtros complejos. Las operaciones complejas, como la sesionización, la atribución, la persistencia de atributos de datos con estado y las opciones complejas de manipulación de datos, se ejecutan a escala con un tiempo de creación de informes rápido. En el mundo de BI, ese tipo de operaciones generalmente requieren la creación de nuevos cubos OLAP para cada caso de uso. El motor de creación de informes de CJA permite acceder sin restricciones a todo el conjunto de datos en cada consulta, lo que da como resultado datos totalmente correlacionados sin necesidad de realizar ninguna cubicación previa.

* **Consulta eficiente de flujos de datos complejos**: una de las mayores diferencias del motor de creación de informes con respecto a las bases de datos SQL y NoSQL tradicionales es su capacidad para determinar predicados basados en relaciones orientadas a secuencias a un nivel fundamental. Estas operaciones fundamentales de consulta pueden examinar el flujo de registros, que está formado por muchas secuencias intercaladas (e incluso anidadas). Realizan una consulta con todos estos flujos de datos entrelazados con la eficacia de una única operación de secuencia contigua.

* **Diseñado para responder rápidamente a consultas grandes**: el motor de creación de informes no tiene un propósito tan general como los sistemas tradicionales de big data. No obstante, está diseñado específicamente para responder a consultas que abarcan millones o incluso miles de millones de registros (datos de eventos / eventos de experiencia), generalmente en menos de un segundo. A diferencia de otros sistemas de big data, no lo hace muestreando los datos o precalculando las respuestas a todas las preguntas que cree que se le pueden plantear. En su lugar, es capaz de calcular las respuestas lo suficientemente rápido como para soportar casos de uso de consultas interactivas. Este diseño específico del motor de creación de informes de CJA facilita la disponibilidad inmediata de los datos a alta velocidad para su análisis y exploración continuos, lo que le permite obtener perspectivas y una comprensión progresiva de los recorridos de los clientes.

* **Actúa como una solución de BI desatendida**: puede definir sus dimensiones, métricas y filtros en un solo lugar y, a continuación, cualquier cliente de CJA (incluida nuestra API pública de CJA) puede acceder a esos componentes. Esto permite abstraer las consultas complejas de los usuarios finales y garantiza que los resultados sean los mismos, independientemente del cliente de creación de informes o visualización que se utilice.

## Funcionalidades de visualización únicas de CJA

El motor de creación de informes es fundamental para que CJA le permita interactuar de forma progresiva con todos los datos de recorrido del cliente de ese motor de creación de informes y actuar en consecuencia. CJA incorpora un amplio conjunto de componentes que le permiten hacerlo visualmente y mediante la operación de arrastrar y soltar. Las herramientas de visualización de BI le permiten explorar dentro de los límites de los datos preparados por SQL (según lo definido por TI). CJA le permite desglosar y segmentar todo lo que quiera, sin tener que volver a TI para crear otra vista SQL.

“Progresivamente” es un concepto clave aquí: al contrario que la mayoría de las visualizaciones de las herramientas de BI, la IU visual de arrastrar y soltar de CJA le permite desglosar continuamente sus datos para sus necesidades específicas: puede generar consultas visuales de forma interactiva utilizando métricas, dimensiones, filtros (segmentos), cálculos, líneas temporales, anotaciones y otros valores de análisis relevantes.

Estos componentes de visualización incluyen funcionalidades inteligentes como:

* **Funciones de analista virtual** como [Detección de anomalías](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) que utilizan algoritmos predictivos y aprendizaje automático para ofrecer perspectivas sobre lo que está provocando comportamientos inusuales en sus datos.

* **Funciones de análisis avanzado** que se centran específicamente en las perspectivas de recorrido de los clientes, como [diagramas de flujo](/help/analysis-workspace/visualizations/c-flow/flow.md), [Panel Atribución](/help/analysis-workspace/c-panels/attribution.md), [diagramas de visitas en el orden previsto](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)y [desgloses de dimensión](/help/components/dimensions/t-breakdown-fa.md). Algunos ejemplos de visualizaciones listas para usar son:

   * [Análisis de retención de clientes a través de tablas de cohortes / latencia](/help/analysis-workspace/visualizations/cohort-table/cohort-use-cases.md), donde simplemente tiene que arrastrar y soltar métricas / dimensiones en un generador y estará listo en menos de 30 segundos,

   * Visualizaciones de [visita en orden previsto](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md) / [flujo](/help/analysis-workspace/visualizations/c-flow/create-flow.md). Se configura en menos de un minuto.

* **Capacidad de segmentación en cada paso de su exploración progresiva**: siempre que crea que tiene sentido, puede volver a publicar la audiencia en Experience Platform y desde allí a cualquiera de los destinos compatibles.

* **Sesionización** que es totalmente [personalizable](/help/data-views/component-settings/persistence.md): usted determina cuándo una sesión, como parte de un canal en el recorrido del cliente, comienza y termina.

* **Depuración y democratización**: los paneles creados en CJA pueden ser:

   * [Depurados](/help/analysis-workspace/curate-share/curate.md) a otras personas de la organización para la exploración continua,
   * Exportados a Excel mediante [Report Builder](/help/report-builder/report-buider-overview.md) (un complemento dedicado),
   * [Compartidos](/help/analysis-workspace/curate-share/share-projects.md) en varios formatos, incluyendo [PDF](/help/analysis-workspace/curate-share/download-send.md), [CSV](/help/analysis-workspace/curate-share/download-send.md) y a través de una [aplicación móvil dedicada](/help/mobile-app/home.md), para aquellos que estén interesados en los informes finales o en las visualizaciones.

Comparar las funcionalidades de visualización de CJA con lo que ofrecen las herramientas de BI es difícil debido a la variedad de visualizaciones disponibles. Algunas herramientas de BI cuentan con visualizaciones más avanzadas, pero CJA se centra en visualizaciones interactivas e interoperables del recorrido del cliente que le permiten desglosar los datos en cuestión de segundos sin “cobrarle” por cada consulta adicional.


## Resumen

CJA se diferencia de las herramientas de BI en la forma en que integra a la perfección un motor de creación de informes altamente optimizado y centrado en el recorrido del cliente con herramientas y componentes fáciles de usar para realizar análisis y generar informes y visualizaciones avanzadas. Todo desde una única IU, sin tener que moverse de un lado a otro entre el motor de consulta y el entorno de visualización.
