---
title: Elija la ruta de migración de Customer Journey Analytics
description: Conozca las ventajas y desventajas de las posibles rutas de migración al migrar a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 6d4fdb464775967074547f8401de679f181d29d7
workflow-type: tm+mt
source-wordcount: '1965'
ht-degree: 2%

---

# Paso 2: Elija la ruta de migración

+++Expanda esta sección para ver dónde encaja la información de esta página en el proceso de migración más amplio. Asegúrese de que se han completado todos los pasos de migración anteriores.

Antes de continuar con esta sección, primero asegúrese de haber completado todas las tareas de migración anteriores.

La información de esta página cubre el paso 2 de la migración, como se indica en la tabla siguiente:

| Tarea de migración | Detalles |
|---------|----------|
| **Paso 1: [Introducción a la migración](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Conozca las ventajas de migrar a Adobe Analytics y el proceso de migración básico. |
| <span class="preview">**Paso 2: Elija la ruta de migración**</span> | <span class="preview">Hay varios métodos disponibles para migrar a Customer Journey Analytics. Elija el método que mejor se adapte a su organización, según el entorno de Adobe Analytics actual de su organización y los objetivos a largo plazo.</span> |
| **Paso 3: [Envío de datos a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | El proceso de envío de datos a Adobe Experience Platform difiere según la ruta de migración elegida en el paso 2. |
| **Paso 4: [Conservar datos históricos](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La mayoría de las organizaciones necesitan conservar sus datos históricos de Adobe Analytics durante un periodo de tiempo determinado. Hay varias opciones disponibles para hacerlo. |
| **Paso 5: [Realizar tareas de implementación adicionales](/help/getting-started/cja-getting-started.md)** | En este punto del proceso de migración, debe realizar varias tareas antes de que el entorno del Customer Journey Analytics esté listo para su uso.<p>Estas tareas adicionales se aplican a las migraciones desde Adobe Analytics, así como a las implementaciones de nuevos Customer Journey Analytics.</p><p>Estas tareas incluyen:</p><ul><li>Introducción de otros datos en Experience Platform</li><li>Creación de conexiones entre conjuntos de datos de Platform y el Customer Journey Analytics</li><li>Creación de vistas de datos</li><li>Transferencia del uso de API de informes</li><li>Contabilidad de fuentes de datos y Data Warehouse</li><li>Migración de proyectos y componentes</li><li>Planificación de la incorporación del usuario</li></ul> <p>Para obtener más información, consulte [Introducción al Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Después de decidir migrar a Customer Journey Analytics, debe determinar la ruta de migración óptima para su organización.

La ruta que elija para migrar de Adobe Analytics a Customer Journey Analytics depende de los siguientes factores:

* Su implementación de Adobe Analytics existente

* Sus metas para el futuro

Utilice la información de esta página para determinar qué ruta de migración de Customer Journey Analytics se ajusta mejor a la implementación actual y a los objetivos futuros de su organización.

Para determinar la ruta de migración óptima para su organización, las siguientes secciones deben leerse secuencialmente:

1. Primero, [comprender las rutas de migración disponibles](#understand-migration-methods).

1. A continuación, [evalúe qué rutas de migración están disponibles para usted](#assess-the-migration-methods-available-to-you-based-on-your-current-adobe-analytics-implementation).

1. Y finalmente, [sopesar las ventajas y desventajas de cada ruta de migración](#weigh-the-advantages-and-disadvantages-of-the-migration-methods-available-to-you).

## Comprender las rutas de migración

Existen varias rutas de migración para migrar de Adobe Analytics a Customer Journey Analytics.

En general, cada ruta de migración difiere en el nivel de esfuerzo necesario para ejecutar la migración, así como en la viabilidad a largo plazo alcanzada después de que se complete la migración.

En la tabla siguiente se enumera cada ruta de migración, su nivel de esfuerzo y su viabilidad a largo plazo:

| Ruta de migración | Nivel de esfuerzo | Viabilidad a largo plazo |
|---------|----------|---------|
| **Nueva implementación del SDK web de Experience Platform**</br> Aunque técnicamente no se trata de una migración, puede empezar a utilizar Customer Journey Analytics realizando una nueva implementación del SDK web de Experience Platform para empezar a enviar datos a Adobe Experience Platform Edge Network. <p>Para organizaciones que aún no utilizan el SDK web, esta ruta de migración es quizás la más sencilla para obtener datos en Edge Network, ya que requiere el menor número de pasos; sin embargo, como todo el trabajo se realiza por adelantado (como la creación del esquema XDM), requiere un esfuerzo inicial mayor.</p><p>Los pasos básicos son:</p><ol><li>Cree un esquema XDM para su organización.</li><li>Implemente el SDK web.</li><li>Envíe datos a Platform.</li></ol> | Alto | Alto |
| **Migre su implementación de Adobe Analytics para utilizar el SDK web**</br> Si la implementación de Adobe Analytics es AppMeasurement para la extensión de Analytics, puede migrarla para utilizar el SDK web de Adobe Experience Platform y empezar a enviar datos a Edge Network y Adobe Analytics antes de enviarlos a Customer Journey Analytics.<p>Esta es la forma más sencilla y fluida de llevar los datos a Edge Network; requiere más pasos, pero ofrece una transición más metódica de Adobe Analytics a Customer Journey Analytics, con hitos más tangibles.</p><p>Los pasos básicos son:</p><ol><li>Mueva la implementación de Adobe Analytics existente al SDK web y compruebe que todo funciona en Adobe Analytics.</li><li>Cree un esquema XDM para su organización a medida que tenga tiempo.</li><li>Utilice la asignación de secuencia de datos para asignar todos los campos del objeto de datos al esquema XDM.</li><li>Envíe datos a Platform.</li></ol> | Moderar | Alto |
| **Configuración de la implementación existente del SDK web de Adobe Analytics**</br> Si la implementación de Adobe Analytics ya está utilizando el SDK web de Adobe Experience Platform, puede empezar a enviar datos al Customer Journey Analytics con un esfuerzo mínimo.<p>Antes de enviar datos a Customer Journey Analytics, considere la posibilidad de actualizar el esquema de Adobe Analytics para las necesidades específicas de su organización y de cualquier otra aplicación de Platform que vaya a utilizar.</p><p>Los pasos básicos son:</p><ol><li>Comience a enviar datos al Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Opcional) Cree un esquema XDM para su organización a medida que tenga tiempo.</li><li>(Condicional) Si ha creado un esquema XDM, utilice la asignación de secuencia de datos para asignar todos los campos del objeto de datos al esquema XDM.</li></ol> | Bajo | Alto |
| **Uso del conector de origen de Analytics**</br> Si la implementación de Adobe Analytics es AppMeasurement para la extensión de Analytics, puede empezar a enviar datos a una vista de datos en Customer Journey Analytics.<p>Esta es la forma más sencilla de obtener datos para Customer Journey Analytics, pero es el método menos viable a largo plazo.</p> | Bajo | Bajo |

{style="table-layout:auto"}

Utilice el siguiente diagrama para visualizar dónde se encuentra cada ruta de migración en el espectro en términos de nivel de esfuerzo y viabilidad a largo plazo:

![rutas de migración de cja](assets/cja-migration-methods.png)

## Evalúe las rutas de migración disponibles en función de la implementación de Adobe Analytics actual

No todas las rutas de migración están disponibles para cada tipo de implementación de Adobe Analytics.

Utilice la siguiente información para comprender mejor qué ruta de migración es la más adecuada para su organización.

Póngase en contacto con el representante del Adobe si necesita asesoramiento, orientación o asistencia más específicos.

| Implementación de Adobe Analytics existente | Rutas de migración disponibles |
|---------|----------|
| AppMeasurement | <ul><li>Nueva implementación del SDK web de Experience Platform</li><li>Migración de Adobe Analytics al SDK web</li><li>Conector de origen de Analytics</li></ul> |
| Extensión de Adobe Analytics | <ul><li>Nueva implementación del SDK web de Experience Platform</li><li>Migración de Adobe Analytics al SDK web</li><li>Conector de origen de Analytics</li></ul> |
| SDK web | <ul><li>Configuración de la implementación del SDK web de Adobe Analytics para enviar datos al Customer Journey Analytics</li></ul> |

{style="table-layout:auto"}

## Valore las ventajas y desventajas de las rutas de migración disponibles

Las ventajas y desventajas de una ruta de migración determinada difieren según la implementación de Adobe Analytics existente.

Antes de usar la información siguiente para determinar qué ruta de migración es la adecuada para usted, revise la información en [Comprender las rutas de migración](#understand-migration-methods) si aún no lo ha hecho.

### Para implementaciones de Adobe Analytics que utilizan: Extensión de AppMeasurement y Adobe Analytics

A continuación se indican las rutas de migración disponibles para las organizaciones que han implementado Adobe Analytics con AppMeasurement o la extensión de Adobe Analytics. Expanda cada sección para ver las ventajas y desventajas de cada ruta de migración.

**Rutas de migración:**

+++Nueva implementación del SDK web de Experience Platform

| Ventajas | Desventajas |
|----------|---------|
| <ul><li>Utiliza un esquema XDM, un esquema flexible para definir cualquier campo que necesite y solo aquellos campos que sean relevantes (le permite alejarse del grupo Campo de evento de experiencia de Adobe Analytics)</li><li>No depende de la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)</li><li>No existen limitaciones de caracteres (100 caracteres para props)</li><li>Disponibilidad de datos y creación de informes de alto rendimiento gracias a que Adobe Experience Platform está diseñado para ofrecer potencia [casos de uso de personalización en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=es)</li><li>Preparado para el futuro (recibirá las últimas funciones y características)</li><li>Consolide las etiquetas para la recopilación de datos de Adobe Experience Cloud entre otros productos de Experience Cloud (AJO, RTCDP, etc.)</li><li>[ID de dispositivos de origen](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=es) para mejorar la precisión de la identificación del visitante</li></ul> | <ul><li>La ruta de migración más lenta y exigente<p>Debe volver a crear el esquema completo en XDM para poder iniciar la implementación del SDK web</p></li></ul> |

{style="table-layout:auto"}

+++

+++Migrar Adobe Analytics al SDK web | Ventajas | Desventajas | |----------|---------| | <ul><li>Permite pasar al SDK web sin afectar a los informes de Adobe Analytics existentes.</li><li>Conserva las reglas y los elementos de datos ya configurados en la implementación de Adobe Analytics (para organizaciones que utilizan la extensión de Analytics).</li><li>Proporciona flexibilidad para crear un esquema XDM para su organización más adelante: un esquema flexible para definir los campos que necesite y solo los campos relevantes.</br>No requiere el grupo Campo de evento de Adobe Analytics Experience en Adobe Experience Platform. <!-- With the new implementation, you're double-counting with 2 implementation; with the migration, you're double-counting, but both of them are through Edge Network. --></li><li>No depende de la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)</li><li>No existen limitaciones de caracteres (100 caracteres para props)</li><li>Disponibilidad de datos y creación de informes de alto rendimiento gracias a que Adobe Experience Platform está diseñado para ofrecer potencia [casos de uso de personalización en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=es)</li><li>Preparado para el futuro (recibirá las últimas funciones y características)</li><li>Consolide las etiquetas para la recopilación de datos de Adobe Experience Cloud entre otros productos de Experience Cloud (AJO, RTCDP, etc.)</li><li>[ID de dispositivos de origen](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=es) para mejorar la precisión de la identificación del visitante</li></ul> | <ul><li>Debe ajustarse a un esquema XDM en algún momento futuro, utilizando la asignación de flujos de datos.</li><li>Incurre en alguna deuda técnica. Por ejemplo, el AppMeasurement heredado o el código de extensión de Analytics pueden permanecer. </li></ul> |

{style="table-layout:auto"}

+++

+++Uso del conector de origen de Analytics | Ventajas | Desventajas | |----------|---------| | <ul><li>Ruta de migración menos laboriosa y exigente. <p>Los datos se migran rápidamente al Customer Journey Analytics con una inversión mínima</p></li></ul> | <ul><li>Los datos no se envían al Edge Network y no se pueden compartir con otras aplicaciones de Adobe Experience Platform; solo se limitan al Customer Journey Analytics<li>Es difícil pasar al SDK web en el futuro</li><li>Utiliza el grupo de campos Evento de experiencia de Analytics en el esquema.</br>Este grupo de campos añade muchos eventos de Adobe Analytics que no son necesarios en el esquema del Customer Journey Analytics.  Esto puede generar un esquema más complejo y desordenado que lo que se necesita de otro modo para Customer Journey Analytics.</li><li>Nivel máximo de [latencia](/help/admin/guardrails.md#latencies) en todos los métodos de implementación</li></ul> |

{style="table-layout:auto"}

+++

### Para implementaciones de Adobe Analytics mediante: SDK web

La siguiente ruta de migración está disponible para las organizaciones que han implementado Adobe Analytics con el SDK web de Experience Platform:

**Ruta de migración:**

+++Configure la implementación del SDK web de Adobe Analytics para enviar datos al Customer Journey Analytics

| Ventajas | Desventajas |
|----------|---------|
| Esta es la ruta de migración preferida si la implementación de Adobe Analytics ya está utilizando el SDK web. <p>Al utilizar este método de implementación, puede elegir si desea utilizar el esquema de Adobe Analytics existente o puede actualizar al esquema XDM para alinearse mejor con las necesidades de su organización a medida que comienza a utilizar otras aplicaciones de Platform.</p><p>**Uso del esquema de Adobe Analytics**</p><p>Las ventajas de utilizar el esquema de Adobe Analytics incluyen:</p><ul><li>Facilidad de migración<p>Si ya está enviando datos a Adobe Analytics con el SDK web de Adobe Experience Platform, puede agregar un servicio adicional al conjunto de datos para enviar datos a Adobe Experience Platform (que luego se puede utilizar en la configuración de Customer Journey Analytics).</p></li></ul><p>Las desventajas de utilizar el esquema de Adobe Analytics incluyen:</p><ul><li>Aunque el uso del esquema de Adobe Analytics no le limita en términos de cómo se puede utilizar con otras aplicaciones de Platform, sí que resulta en un esquema más complejo de lo que podría ser de otra manera. Esto se debe a que el esquema de Adobe Analytics contiene muchos objetos específicos de Adobe Analytics que probablemente su organización no vaya a utilizar.<p>Cuando es necesario realizar cambios en el esquema, debe revisar miles de campos no utilizados para encontrar el campo que requiere actualización.</p></li></ul><p>**Uso del esquema XDM**</p><p>Las ventajas de actualizar el esquema XDM incluyen:</p><ul><li>Un esquema optimizado que se adapta a las necesidades de su organización y a las aplicaciones de Platform específicas que utiliza.</li><p>Cuando es necesario realizar cambios en el esquema, no es necesario revisar miles de campos no utilizados para encontrar el campo que requiere actualización.</p></ul><p>Las desventajas de actualizar el esquema XDM incluyen:</p><ul><li>La actualización del esquema es un proceso laborioso que es necesario antes de empezar a enviar datos al Customer Journey Analytics.</li></ul> | Ninguno |

{style="table-layout:auto"}

+++

## A continuación, envíe datos a Adobe Experience Platform

Después de utilizar la información anterior para elegir una ruta de migración, aprenda a [envío de datos a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) según la ruta de migración elegida.
