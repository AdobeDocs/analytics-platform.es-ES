---
title: Elija la ruta de migración de Customer Journey Analytics
description: Conozca las ventajas y desventajas de las posibles rutas de migración al migrar a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 1c789264a9867279f58a3ad139207fec8db29c1b
workflow-type: tm+mt
source-wordcount: '2422'
ht-degree: 0%

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
| **Nueva implementación del SDK web de Experience Platform**</br> Aunque técnicamente no se trata de una migración, puede empezar a utilizar Customer Journey Analytics realizando una nueva implementación del SDK web de Experience Platform. Esto le permite empezar a enviar datos al Edge Network y al Customer Journey Analytics de Adobe Experience Platform. <p>Para organizaciones que aún no utilizan el SDK web, esta ruta de migración es quizás la más sencilla para obtener datos en Edge Network, ya que requiere el menor número de pasos; sin embargo, como todo el trabajo se realiza por adelantado (como la creación del esquema XDM), requiere un esfuerzo inicial mayor.</p><p>Los pasos básicos son:</p><ol><li>Cree un esquema XDM para su organización.</li><li>Implemente el SDK web.</li><li>Envíe datos a Platform.</li></ol> | Alto | Alto |
| **Migre su implementación de Adobe Analytics para utilizar el SDK web**</br> Si la implementación de Adobe Analytics es AppMeasurement para la extensión de Analytics, puede migrarla para utilizar el SDK web de Adobe Experience Platform y empezar a enviar datos a Edge Network y Adobe Analytics antes de enviarlos a Customer Journey Analytics.<p>Para las organizaciones que aún no utilizan el SDK web, esta es la forma más sencilla y sencilla de obtener datos para Edge Network; requiere más pasos, pero ofrece una transición más metódica de Adobe Analytics a Customer Journey Analytics, con hitos más tangibles.</p><p>Los pasos básicos son:</p><ol><li>Mueva la implementación de Adobe Analytics existente al SDK web y compruebe que todo funciona en Adobe Analytics.</li><li>Cree un esquema XDM para su organización a medida que tenga tiempo.</li><li>Utilice la asignación de secuencia de datos para asignar todos los campos del objeto de datos al esquema XDM.</li><li>Envíe datos a Platform.</li></ol> | Moderar | Alto |
| **Configuración de la implementación existente del SDK web de Adobe Analytics**</br> Si la implementación de Adobe Analytics ya está utilizando el SDK web de Adobe Experience Platform, puede empezar a enviar datos al Customer Journey Analytics con un esfuerzo mínimo.<p>Antes de enviar datos a Customer Journey Analytics, considere la posibilidad de actualizar el esquema de Adobe Analytics para las necesidades específicas de su organización y de cualquier otra aplicación de Platform que utilice.</p><p>Los pasos básicos son:</p><ol><li>Comience a enviar datos al Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Opcional) Cree un esquema XDM para su organización a medida que tenga tiempo.</li><li>(Condicional) Si ha creado un esquema XDM, utilice la asignación de secuencia de datos para asignar todos los campos del objeto de datos al esquema XDM.</li></ol> | Bajo | Alto |
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

#### Rutas de migración

+++Nueva implementación del SDK web de Experience Platform

| Ventajas | Desventajas |
|----------|---------|
| <ul><li>**Proporciona todas las ventajas de alojar datos en Experience Edge Network**: <p>Estas ventajas incluyen:</p><ul><li>Disponibilidad de datos y creación de informes de alto rendimiento gracias a que Adobe Experience Platform está diseñado para ofrecer potencia [casos de uso de personalización en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=es)</li><li>Consolide la implementación de la recopilación de datos de Adobe Experience Cloud entre otros productos de Experience Cloud (AJO, RTCDP, etc.).</li><li>No depende de la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)</li></ul></li><li>**Preparado para el futuro**: Las futuras actualizaciones de la implementación son más sencillas.</li></ul> | <ul><li>**Requiere una nueva implementación desde cero**: El requisito de realizar una nueva implementación desde cero significa las siguientes desventajas: </li><ul><li>**Lento**: Esta es la ruta de migración más lenta y exigente porque requiere que vuelva a empezar con una nueva implementación.</li><li>**Debe volver a crear el esquema completo en XDM**: para poder empezar a implementar el SDK web, debe volver a crear el esquema completo en XDM.</li><li>**Debe volver a crear reglas y elementos de datos**: Antes de poder empezar a implementar el SDK web, debe volver a crear cualquier condición de regla y elemento de datos a partir de la implementación de Adobe Analytics.</li></ul></ul> |

{style="table-layout:auto"}

+++

+++Migrar Adobe Analytics al SDK web de Experience Platform

| Ventajas | Desventajas |
|----------|---------|
| <ul><li>**Proporciona todas las ventajas de alojar datos en Experience Edge Network**: <p>Estas ventajas incluyen:</p><ul><li>Disponibilidad de datos y creación de informes de alto rendimiento gracias a que Adobe Experience Platform está diseñado para ofrecer potencia [casos de uso de personalización en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=es)</li><li>Consolide la implementación de la recopilación de datos de Adobe Experience Cloud entre otros productos de Experience Cloud (AJO, RTCDP, etc.).</li><li>No depende de la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)</li></ul><li>**Utiliza la implementación existente**: Aunque este enfoque requiere algunos cambios de implementación, no requiere una implementación completamente nueva desde cero. Puede utilizar la capa de datos y el código existentes con cambios mínimos en la lógica de implementación sin afectar a los informes de Adobe Analytics existentes.</li><li>**Proporciona flexibilidad para crear un esquema XDM para su organización más adelante**: Puede migrar la implementación de Adobe Analytics existente para utilizar el SDK web y validar que todo funciona en Adobe Analytics y, a continuación, crear el esquema XDM. Esta flexibilidad permite una migración más metódica y reflexiva.</li></ul> | <ul><li>**Requiere asignación para enviar datos a Platform**: Cuando su organización esté lista para utilizar Customer Journey Analytics, debe enviar datos a un conjunto de datos en Adobe Experience Platform. Esta acción requiere que cada campo del objeto de datos sea una entrada en la herramienta de asignación de flujos de datos que lo asigne a un campo de esquema XDM. La asignación solo debe realizarse una vez para este flujo de trabajo y no implica realizar cambios de implementación. Sin embargo, es un paso adicional que no es necesario al enviar datos en un objeto XDM.</li><li>**Deuda técnica**: Debido a que este enfoque utiliza una forma modificada de la implementación existente, puede resultar más difícil rastrear la lógica de implementación y realizar cambios en el futuro cuando sea necesario. </li></ul> |

{style="table-layout:auto"}

+++

+++Uso del conector de origen de Analytics

| Ventajas | Desventajas |
|----------|---------|
| <ul><li>Ruta de migración menos laboriosa y exigente. <p>Los datos se migran rápidamente al Customer Journey Analytics con una inversión mínima</p></li></ul> | <ul><li>**Los datos no se envían al Edge Network**: <p>Esto causa las siguientes desventajas:</p><ul><li>Nivel máximo de [latencia](/help/admin/guardrails.md#latencies) en informes en todas las rutas de migración; no optimizado para casos de uso de personalización en tiempo real.</li><li>Los datos no se pueden compartir con otras aplicaciones de Adobe Experience Platform; están restringidos únicamente al Customer Journey Analytics</li><li>Se basa en la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)</li></ul><li>**Es difícil pasar al SDK web en el futuro**: </li><li>**Utiliza el grupo de campos Evento de experiencia de Analytics en el esquema**: Este grupo de campos añade muchos eventos de Adobe Analytics que no son necesarios en el esquema del Customer Journey Analytics.  Esto puede generar un esquema más complejo y desordenado que lo que se necesita de otro modo para Customer Journey Analytics.</li></ul> |

{style="table-layout:auto"}

+++

### Para implementaciones de Adobe Analytics mediante: SDK web

La siguiente ruta de migración está disponible para las organizaciones que han implementado Adobe Analytics con el SDK web de Experience Platform.

Al elegir esta ruta de migración, también debe elegir el esquema.

#### Ruta de migración

+++Configure la implementación del SDK web de Adobe Analytics para enviar datos al Customer Journey Analytics

| Ventajas | Desventajas |
|----------|---------|
| Esta es la ruta de migración preferida si la implementación de Adobe Analytics ya está utilizando el SDK web.<ul><li>**Proporciona todas las ventajas de alojar datos en Experience Edge Network**: <p>Estas ventajas incluyen:</p><ul><li>Disponibilidad de datos y creación de informes de alto rendimiento gracias a que Adobe Experience Platform está diseñado para ofrecer potencia [casos de uso de personalización en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=es)</li><li>Consolide la implementación de la recopilación de datos de Adobe Experience Cloud entre otros productos de Experience Cloud (AJO, RTCDP, etc.).</li><li>No depende de la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)</li></ul><li>**Utiliza la implementación existente**: Aunque este enfoque requiere algunos cambios de implementación, no requiere una implementación completamente nueva desde cero. Puede utilizar la capa de datos y el código existentes con cambios mínimos en la lógica de implementación sin afectar a los informes de Adobe Analytics existentes.</li><li>**Proporciona una opción para utilizar un esquema XDM**: puede elegir utilizar el esquema de Adobe Analytics existente o crear un esquema XDM y asignar campos en el objeto de datos al esquema XDM. [Esquemas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) son un esquema flexible para definir cualquier campo que necesite y solo aquellos campos que sean relevantes. <p>Consulte &quot;Uso de su propio esquema XDM&quot; a continuación para obtener más información sobre las ventajas de utilizar su propio esquema XDM.</p></li><li>**Conserva reglas y elementos de datos**: Aunque requiere nuevas acciones de regla, puede reutilizar los elementos de datos y las condiciones de regla existentes con cambios mínimos.</li><li>**Preparado para el futuro**: Si decide utilizar su propio esquema XDM, las futuras actualizaciones de implementación serán más sencillas.</li></ul> | Ninguno |

{style="table-layout:auto"}

+++

#### Elija su esquema

Si elige la ruta de migración que permite configurar la implementación del SDK web de Adobe Analytics para enviar datos a Customer Journey Analytics, puede elegir el esquema que desee utilizar.

Puede elegir si desea utilizar el esquema de Adobe Analytics existente o puede actualizar a su propio esquema XDM para alinearse mejor con las necesidades de su organización a medida que comienza a utilizar otros servicios de Platform.

+++Usar el esquema de Adobe Analytics con la implementación del SDK web de Adobe Analytics

| Ventajas | Desventajas |
|----------|---------|
| <p>Las ventajas de utilizar el esquema de Adobe Analytics incluyen:</p><ul><li>Facilidad de migración<p>Si ya está enviando datos a Adobe Analytics con el SDK web de Adobe Experience Platform, puede agregar un servicio adicional al conjunto de datos para enviar datos a Adobe Experience Platform (que luego se puede utilizar en la configuración de Customer Journey Analytics).</p></li></ul> | <p>Las desventajas de utilizar el esquema de Adobe Analytics incluyen:</p><ul><li>Aunque el uso del esquema de Adobe Analytics no le limita en términos de cómo se puede utilizar con otras aplicaciones de Platform, sí que resulta en un esquema más complejo de lo que podría ser de otra manera. Esto se debe a que el esquema de Adobe Analytics contiene muchos objetos específicos de Adobe Analytics que es poco probable que su organización utilice.<p>Cuando es necesario realizar cambios en el esquema, debe revisar miles de campos no utilizados para encontrar el campo que requiere actualización.</p></li></ul> |

+++

+++Utilice su propio esquema XDM con la implementación del SDK web de Adobe Analytics

| Ventajas | Desventajas |
|----------|---------|
| <ul><p>Las ventajas de actualizar a su propio esquema XDM incluyen:</p><ul><li>Un esquema optimizado que se adapta a las necesidades de su organización y a las aplicaciones de Platform específicas que utiliza.</li><p>Cuando es necesario realizar cambios en el esquema, no es necesario revisar miles de campos no utilizados para encontrar el campo que requiere actualización.</p></ul> | <p>Las desventajas de actualizar a su propio esquema XDM incluyen:</p><ul><li>La actualización del esquema es un proceso laborioso que es necesario antes de empezar a enviar datos al Customer Journey Analytics.</li></ul> |

+++

## A continuación, envíe datos a Adobe Experience Platform

Después de utilizar la información anterior para elegir una ruta de migración, aprenda a [envío de datos a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) según la ruta de migración elegida.
