---
title: Elija la ruta de actualización del Customer Journey Analytics
description: Conozca las ventajas y desventajas de las posibles rutas de actualización al actualizar a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 6cceeaa3b57808a82012b124435aa1b7dbf1b3f2
workflow-type: tm+mt
source-wordcount: '2483'
ht-degree: 63%

---

# Paso 2: Elija la ruta de actualización

+++Expanda esta sección para ver dónde encaja la información de esta página en el proceso de actualización más amplio. Asegúrese de que se han completado todos los pasos de actualización anteriores.

Antes de continuar con esta sección, primero asegúrese de haber completado todas las tareas de actualización anteriores.

La información de esta página cubre el paso 2 del proceso de actualización, como se indica en la tabla siguiente:

| Actualizar tarea | Detalles |
|---------|----------|
| **Paso 1: [Introducción a la actualización](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Conozca las ventajas de actualizar a Customer Journey Analytics y el proceso de actualización básico. |
| <span class="preview">**Paso 2: Elija la ruta de actualización**</span> | <span class="preview">Hay varios métodos disponibles para actualizar a Customer Journey Analytics. Elija el método que mejor se adapte a su organización, en función del entorno de Adobe Analytics actual de su organización y los objetivos a largo plazo.</span> |
| **Paso 3: [Enviar datos a Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | El proceso de envío de datos a Adobe Experience Platform difiere según la ruta de actualización elegida en el paso 2. |
| **Paso 4: [Conservar los datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | La mayoría de las organizaciones necesitan conservar sus datos históricos de Adobe Analytics durante un periodo de tiempo determinado. Hay varias opciones disponibles para hacerlo. |
| **Paso 5: [Realizar tareas de implementación adicionales](/help/getting-started/cja-getting-started.md)** | En este punto del proceso de actualización, debe realizar varias tareas antes de que el entorno del Customer Journey Analytics esté listo para su uso.<p>Estas tareas adicionales se aplican a las actualizaciones desde Adobe Analytics, así como a las nuevas implementaciones de Customer Journey Analytics.</p><p>Esta tareas son:</p><ul><li>Incorporación de datos a Experience Platform</li><li>Creación de conexiones entre conjuntos de datos de Platform y Customer Journey Analytics</li><li>Creación de vistas de datos </li><li>Transferencia del uso de API de informes</li><li>Contabilidad de fuentes de datos y Data Warehouse</li><li>Migración de proyectos y componentes</li><li>Planificación de la incorporación del usuario</li></ul> <p>Para obtener más información, consulte [Introducción a Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Después de decidir actualizar a Customer Journey Analytics, debe determinar la ruta de actualización óptima para su organización.

La ruta que elija para actualizar de Adobe Analytics a Customer Journey Analytics depende de los siguientes factores:

* Su implementación de Adobe Analytics existente

* Sus metas para el futuro

Utilice la información de esta página para determinar qué ruta de actualización de Customer Journey Analytics se ajusta mejor a la implementación actual y a los objetivos futuros de su organización.

Para determinar la ruta de actualización óptima para su organización, las siguientes secciones deben leerse secuencialmente:

1. Primero, [comprender las rutas de actualización disponibles](#understand-upgrade-paths).

1. A continuación, [evaluar qué rutas de actualización están disponibles para usted](#assess-the-upgrade-paths-available-to-you-based-on-your-current-adobe-analytics-implementation).

1. Y finalmente, [sopesar las ventajas y desventajas de cada ruta de actualización](#weigh-the-advantages-and-disadvantages-of-the-upgrade-paths-available-to-you).

## Comprender las rutas de actualización

Existen varias rutas de actualización para actualizar de Adobe Analytics a Customer Journey Analytics.

En general, cada ruta de actualización difiere en el nivel de esfuerzo necesario para ejecutarla, así como en la viabilidad a largo plazo conseguida después de que se complete la actualización.

La siguiente tabla enumera cada ruta de actualización, su nivel de esfuerzo y su viabilidad a largo plazo:

| Ruta de actualización | Nivel de esfuerzo | Viabilidad a largo plazo |
|---------|----------|---------|
| **Nueva implementación del SDK web de Experience Platform**</br> Puede empezar a utilizar Customer Journey Analytics realizando una nueva implementación del SDK web de Experience Platform. Esto le permite empezar a enviar datos a Adobe Experience Platform Edge Network y a Customer Journey Analytics. <p>Para organizaciones que aún no utilizan el SDK web, esta ruta de actualización es quizás la más sencilla de obtener datos en Edge Network porque requiere el menor número de pasos; sin embargo, como todo el trabajo se realiza por adelantado (como la creación del esquema XDM), requiere un esfuerzo inicial mayor.</p><p>Los dos pasos básicos son:</p><ol><li>Cree un esquema XDM para su organización.</li><li>Implemente el SDK de Adobe.</li><li>Envíe datos a Platform.</li></ol> | Alto | Alto |
| **Migrar la implementación de Adobe Analytics para utilizar el SDK web**</br> Si la implementación de Adobe Analytics es AppMeasurement o la extensión de Analytics, puede migrarla para utilizar el SDK web de Adobe Experience Platform y empezar a enviar datos a Edge Network y Adobe Analytics antes de enviarlos a Customer Journey Analytics.<p>En el caso de las organizaciones que aún no utilizan el SDK web, esta es la forma más fácil y fluida de obtener datos para Edge Network; requiere más pasos, pero ofrece una transición más metódica de Adobe Analytics a Customer Journey Analytics, con resultados más tangibles.</p><p>Los dos pasos básicos son:</p><ol><li>Mueva la implementación de Adobe Analytics existente al SDK web y compruebe que todo funciona en Adobe Analytics.</li><li>Cree un esquema XDM para su organización si dispone de tiempo.</li><li>Utilice la asignación de secuencia de datos para asignar todos los campos del objeto de datos al esquema XDM.</li><li>Envíe datos a Platform.</li></ol> | Moderado | Alto |
| **Configuración de la implementación existente del SDK web de Adobe Analytics**</br> Si la implementación de Adobe Analytics ya está utilizando el SDK web de Adobe Experience Platform, puede empezar a enviar datos a Platform configurando una secuencia de datos. O bien, si ya está enviando datos a Platform, solo tiene que crear una conexión entre los conjuntos de datos de Platform y el Customer Journey Analytics.<p>Antes de enviar datos a Platform para utilizarlos en Customer Journey Analytics, considere la posibilidad de actualizar el esquema de Adobe Analytics para las necesidades específicas de su organización y de cualquier otra aplicación de Platform que utilice.</p><p>Los dos pasos básicos son:</p><ol><li>Comience a enviar datos a Platform.<p>Si ya está enviando datos a Platform con la implementación de Adobe Analytics, este paso no es obligatorio. Simplemente debe crear una conexión entre los conjuntos de datos de Platform y el Customer Journey Analytics, tal como se describe más adelante en este proceso.</p></li><li>(Opcional) Cree un esquema XDM para su organización si dispone de tiempo.</li><li>(Condicional) Si ha creado un esquema XDM, utilice la asignación de secuencia de datos para asignar todos los campos del objeto de datos al esquema XDM.</li></ol> | Bajo | Alto |
| **Uso del conector de origen de Analytics**</br> Si la implementación de Adobe Analytics es AppMeasurement para la extensión de Analytics, puede empezar a enviar datos a una vista de datos en Customer Journey Analytics.<p>Esta es la forma más sencilla de llevar los datos a Customer Journey Analytics, pero es el método menos viable a largo plazo.</p> | Bajo | Bajo |

{style="table-layout:auto"}

Utilice el siguiente diagrama para visualizar dónde se encuentra cada ruta de actualización en el espectro en términos de nivel de esfuerzo y viabilidad a largo plazo:

![rutas de actualización de cja](assets/cja-upgrade-path-chart.png)

## Evalúe las rutas de actualización disponibles en función de la implementación de Adobe Analytics actual

No todas las rutas de actualización están disponibles para cada tipo de implementación de Adobe Analytics.

Utilice la información siguiente para comprender mejor qué ruta de actualización es la más adecuada para su organización.

Póngase en contacto con el representante del Adobe si necesita asesoramiento, ayuda o asistencia más específicos.

| Implementación existente de Adobe Analytics | Rutas de actualización disponibles |
|---------|----------|
| AppMeasurement | <ul><li>Nueva implementación del SDK web de Experience Platform</li><li>Migración de Adobe Analytics al SDK web</li><li>Conector de origen de Analytics</li></ul> |
| Extensión de Adobe Analytics | <ul><li>Nueva implementación del SDK web de Experience Platform</li><li>Migración de Adobe Analytics al SDK web</li><li>Conector de origen de Analytics</li></ul> |
| SDK web | <ul><li>Configurar la implementación del SDK web de Adobe Analytics para enviar datos al Customer Journey Analytics</li></ul> |

{style="table-layout:auto"}

## Valore las ventajas y desventajas de las rutas de actualización disponibles para usted

Las ventajas y desventajas de una ruta de actualización determinada difieren según la implementación de Adobe Analytics existente.

Antes de usar la información siguiente para determinar qué ruta de actualización es la adecuada para usted, revise la información en [Comprender las rutas de actualización](#understand-migration-methods) si aún no lo ha hecho.

### Para implementaciones de Adobe Analytics que utilicen: AppMeasurement y extensión de Adobe Analytics

A continuación se indican las rutas de actualización disponibles para las organizaciones que han implementado Adobe Analytics con AppMeasurement o la extensión de Adobe Analytics. Expanda cada sección para ver las ventajas y desventajas de cada ruta de actualización.

#### Rutas de actualización

+++Nueva implementación del SDK web de Experience Platform

| Ventajas | Desventajas |
|----------|---------|
| <ul><li>**Ofrece todas las ventajas de alojar datos en Experience Edge Network**: <p>Estas ventajas son:</p><ul><li>Informes de alto rendimiento y disponibilidad de datos porque Adobe Experience Platform se ha creado para potenciar [casos de uso de personalización en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=es)</li><li>Consolidación de la implementación de la recopilación de datos de Adobe Experience Cloud entre otros productos de Experience Cloud (AJO, RTCDP, etc.)</li><li>No depende de la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)</li></ul></li><li>**Preparación para el futuro**: las futuras actualizaciones de la implementación son más sencillas.</li></ul> | <ul><li>**Requiere una nueva implementación desde cero**: el requisito de realizar una nueva implementación desde cero aporta las siguientes desventajas: </li><ul><li>**Lento**: Esta es la ruta de actualización más lenta y exigente porque requiere que comience de nuevo con una nueva implementación.</li><li>**Hay que volver a crear el esquema completo en XDM**: para poder empezar a implementar el SDK web, debe volver a crear el esquema completo en XDM.</li><li>**Hay que volver a crear reglas y elementos de datos**: para poder empezar a implementar el SDK web, debe volver a crear cualquier condición de regla y elemento de datos a partir de la implementación de Adobe Analytics.</li></ul></ul> |

{style="table-layout:auto"}

+++

+++Migrar Adobe Analytics al SDK web de Experience Platform

| Ventajas | Desventajas |
|----------|---------|
| <ul><li>**Ofrece todas las ventajas de alojar datos en Experience Edge Network**: <p>Estas ventajas son:</p><ul><li>Informes de alto rendimiento y disponibilidad de datos porque Adobe Experience Platform se ha creado para potenciar [casos de uso de personalización en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=es)</li><li>Consolidación de la implementación de la recopilación de datos de Adobe Experience Cloud entre otros productos de Experience Cloud (AJO, RTCDP, etc.)</li><li>No depende de la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)</li></ul><li>**Utiliza la implementación existente**: aunque este enfoque requiere algunos cambios de implementación, no requiere una implementación completamente nueva desde cero. Puede utilizar la capa de datos y el código existentes con cambios mínimos en la lógica de implementación sin que ello afecte a los informes de Adobe Analytics existentes.</li><li>**Ofrece flexibilidad para crear un esquema XDM para su organización más adelante**: puede migrar la implementación de Adobe Analytics existente para que utilice el SDK web y validar que todo funciona en Adobe Analytics y, a continuación, crear el esquema XDM. Esta flexibilidad permite una actualización más metódica y considerada a Customer Journey Analytics.</li></ul> | <ul><li>**Requiere asignación para enviar datos a Platform**: cuando su organización esté lista para utilizar Customer Journey Analytics, debe enviar los datos a un conjunto de datos en Adobe Experience Platform. Esta acción requiere que cada campo del objeto de datos sea una entrada en la herramienta de asignación de la secuencia de datos que lo asigna a un campo de esquema XDM. La asignación solo debe realizarse una vez para este flujo de trabajo y no implica realizar cambios de implementación. Sin embargo, es un paso adicional que no es necesario cuando se envían datos en un objeto XDM.</li><li>**Deuda técnica**: debido a que este enfoque utiliza una forma modificada de la implementación existente, puede resultar más difícil rastrear la lógica de implementación y realizar cambios en el futuro cuando sea necesario. </li></ul> |

{style="table-layout:auto"}

+++

+++Uso del conector de origen de Analytics

| Ventajas | Desventajas |
|----------|---------|
| <ul><li>Ruta de actualización menos laboriosa y exigente. <p>Los datos se migran rápidamente a Customer Journey Analytics con una inversión mínima</p></li></ul> | <ul><li>**Los datos no se envían a Edge Network**: <p>Como resultado se obtienen las siguientes desventajas:</p><ul><li>Nivel máximo de [latencia](/help/technotes/guardrails.md#latencies) en informes en todas las rutas de actualización; no optimizado para casos de uso de personalización en tiempo real.</li><li>Los datos no se pueden compartir con otras aplicaciones de Adobe Experience Platform; están restringidos únicamente a Customer Journey Analytics</li><li>Depende de la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)</li></ul><li>**Es difícil pasar al SDK web en el futuro**: </li><li>**Utiliza el grupo de campos de evento de experiencia de Analytics en el esquema**: este grupo de campos añade muchos eventos de Adobe Analytics que no son necesarios en el esquema de Customer Journey Analytics.  Esto puede dar lugar a un esquema más complejo y desordenado de lo que sería necesario para Customer Journey Analytics.</li></ul> |

{style="table-layout:auto"}

+++

### Para implementaciones de Adobe Analytics que usen: SDK web

La siguiente ruta de actualización está disponible para las organizaciones que han implementado Adobe Analytics con el SDK web de Experience Platform.

Al elegir esta ruta de actualización, también debe elegir el esquema.

#### Ruta de actualización

+++Configurar la implementación del SDK web de Adobe Analytics para enviar datos a Customer Journey Analytics

| Ventajas | Desventajas |
|----------|---------|
| Esta es la ruta de actualización preferida si la implementación de Adobe Analytics ya está utilizando el SDK web.<ul><li>**Ofrece todas las ventajas de alojar datos en Experience Edge Network**: <p>Estas ventajas son:</p><ul><li>Informes de alto rendimiento y disponibilidad de datos porque Adobe Experience Platform se ha creado para potenciar [casos de uso de personalización en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=es)</li><li>Consolidación de la implementación de la recopilación de datos de Adobe Experience Cloud entre otros productos de Experience Cloud (AJO, RTCDP, etc.)</li><li>No depende de la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)</li></ul><li>**Utiliza la implementación existente**: aunque este enfoque requiere algunos cambios de implementación, no requiere una implementación completamente nueva desde cero. Puede utilizar la capa de datos y el código existentes con cambios mínimos en la lógica de implementación sin que ello afecte a los informes de Adobe Analytics existentes.</li><li>**Proporciona una opción para utilizar un esquema XDM**: puede elegir utilizar el esquema de Adobe Analytics existente o crear un esquema XDM y asignar campos en el objeto de datos al esquema XDM. [Esquemas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas): son un esquema flexible para definir cualquier campo que necesite y solo aquellos campos que sean relevantes. <p>Consulte &quot;Uso de su propio esquema XDM&quot; a continuación para obtener más información sobre las ventajas de utilizar su propio esquema XDM.</p></li><li>**Conserva reglas y elementos de datos**: aunque requiere nuevas acciones de regla, puede reutilizar los elementos de datos y las condiciones de regla existentes con cambios mínimos.</li><li>**Preparación para el futuro**: si decide utilizar su propio esquema XDM, las futuras actualizaciones de implementación son más sencillas.</li></ul> | Ninguno |

{style="table-layout:auto"}

+++

#### Elección del esquema

Si elige la ruta de actualización que permite configurar la implementación del SDK web de Adobe Analytics para enviar datos a Customer Journey Analytics, puede elegir el esquema que desee utilizar.

Puede elegir si desea utilizar el esquema de Adobe Analytics existente o puede actualizar a su propio esquema XDM para que se ajuste mejor a las necesidades de su organización a cuando empiece a utilizar otros servicios de Platform.

+++Usar el esquema de Adobe Analytics con la implementación del SDK web de Adobe Analytics

| Ventajas | Desventajas |
|----------|---------|
| <p>Las ventajas de utilizar el esquema de Adobe Analytics son:</p><ul><li>Facilidad de actualización<p>Si ya está enviando datos a Adobe Analytics con el SDK web de Adobe Experience Platform, puede añadir un servicio adicional a la secuencia de datos para que envíe los datos a Adobe Experience Platform (que luego se podrán utilizar en la configuración de Customer Journey Analytics).</p></li></ul> | <p>Las desventajas de utilizar el esquema de Adobe Analytics son:</p><ul><li>Aunque el uso del esquema de Adobe Analytics no le limita en términos de cómo se puede utilizar con otras aplicaciones de Platform, sí da lugar a un esquema más complejo de lo que podría ser. Esto se debe a que el esquema de Adobe Analytics contiene muchos objetos específicos de Adobe Analytics que es poco probable que su organización utilice.<p>Cuando es necesario realizar cambios en el esquema, hay que rebuscar entre miles de campos no utilizados para encontrar el campo que requiere actualización.</p></li></ul> |

+++

+++Utilizar su propio esquema XDM con la implementación del SDK web de Adobe Analytics

| Ventajas | Desventajas |
|----------|---------|
| <ul><p>Las ventajas de actualizar a su propio esquema XDM son:</p><ul><li>Un esquema optimizado que se adapta a las necesidades de su organización y a las aplicaciones de Platform específicas que utiliza.</li><p>Cuando es necesario realizar cambios en el esquema, no es necesario rebuscar entre miles de campos no utilizados para encontrar el campo que requiere actualización.</p></ul> | <p>Las desventajas de actualizar a su propio esquema XDM son:</p><ul><li>Actualizar el esquema es un proceso que lleva tiempo y que es necesario antes de empezar a enviar datos a Customer Journey Analytics.</li></ul> |

+++

## A continuación, envíe datos a Adobe Experience Platform

Después de usar la información anterior para elegir una ruta de actualización, aprenda a [envío de datos a Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md) según la ruta de actualización elegida.
