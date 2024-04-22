---
title: Elija el método de migración de Customer Journey Analytics
description: Conozca las ventajas y desventajas de los posibles métodos de migración al migrar a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 923dfac33fcde368392fe29c6530069cc0d8fb9d
workflow-type: tm+mt
source-wordcount: '1914'
ht-degree: 4%

---

# Paso 2: Elija el método de migración de Customer Journey Analytics

+++Expanda esta sección para ver dónde encaja la información de esta página en el proceso de migración más amplio. Asegúrese de que se han completado todos los pasos de migración anteriores.

Antes de continuar con esta sección, primero asegúrese de haber completado todas las tareas de migración anteriores.

La información de esta página cubre el paso 2, como se indica en la tabla siguiente:

| Tarea de migración | Detalles |
|---------|----------|
| **Paso 1: [Introducción a la migración](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Conozca las ventajas de migrar a Adobe Analytics y el proceso de migración básico. |
| <span class="preview">**Paso 2: [Elija el método de migración.](/help/getting-started/cja-migration/cja-migration-method.md)**</span> | <span class="preview">Hay varios métodos disponibles para migrar a Customer Journey Analytics. Elija el método que mejor se adapte a su organización, según el entorno de Adobe Analytics actual de su organización y los objetivos a largo plazo.</span> |
| **Paso 3: [Envío de datos a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | El proceso de envío de datos a Adobe Experience Platform difiere según el método de migración elegido en el paso 1. |
| **Paso 4: [Asignación de datos al esquema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Esquemas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) se utilizan en Adobe Experience Platform para describir la estructura de los datos de una manera uniforme y reutilizable. Al definir los datos de forma coherente en todos los sistemas, resulta más fácil conservar el significado y, por lo tanto, obtener valor de los datos.<p>La mayoría de los métodos de migración requieren que cree un nuevo esquema XDM o que asigne el esquema de Adobe Analytics existente a XDM mediante la asignación de flujos de datos.</p> |
| **Paso 5: [Conservar datos históricos](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La mayoría de las organizaciones necesitan conservar sus datos históricos de Adobe Analytics durante un periodo de tiempo determinado. Hay varias opciones disponibles para hacerlo. |
| **Paso 6: [Planificar la incorporación del usuario](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Debe dar a los usuarios tiempo suficiente (de 3 a 6 meses) para familiarizarse con las diferencias clave de Analysis Workspace en Customer Journey Analytics. |
| **Paso 7: [Puerto del uso de API de informes](/help/getting-started/cja-migration/cja-migration-api.md)** | La API de informes de Customer Journey Analytics tiene el mismo formato, pero utiliza un punto de conexión diferente. Publique el uso de la API de informes desde la API de informes de Adobe Analytics a la API de informes de Customer Journey Analytics. |
| **Paso 8: [Reemplazar fuentes de datos y Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decida cómo utilizará las opciones de exportación disponibles en Customer Journey Analytics para reemplazar las fuentes de datos y las funciones de Data Warehouse que utilizaba en Adobe Analytics. |
| **Paso 9: [Migrar proyectos y componentes](/help/getting-started/cja-migration/cja-migration-projects.md)** | El área Migración de componentes en Adobe Analytics le permite migrar proyectos y sus componentes asociados de Adobe Analytics a Customer Journey Analytics. |

{style="table-layout:auto"}

+++

Después de decidir migrar a Customer Journey Analytics, debe determinar el método de migración óptimo para su organización.

El método que elija para migrar de Adobe Analytics a Customer Journey Analytics depende de los siguientes factores:

* Su implementación de Adobe Analytics existente

* Sus metas para el futuro

Utilice las siguientes secciones para determinar qué método de migración de Customer Journey Analytics es el más adecuado para la implementación actual y los objetivos futuros de su organización:

## Comprender los métodos de migración

Existen varios métodos de migración para migrar de Adobe Analytics a Customer Journey Analytics.

En general, cada método de migración difiere en el nivel de esfuerzo necesario para ejecutar la migración, así como en la viabilidad a largo plazo alcanzada después de que se complete la migración.

En la siguiente tabla se enumera cada método de migración, su nivel de esfuerzo y su viabilidad a largo plazo:

| Método de migración | Nivel de esfuerzo | Viabilidad a largo plazo |
|---------|----------|---------|
| **Nueva implementación del SDK web**</br> Puede realizar una nueva implementación del SDK web de Adobe Experience Platform para empezar a enviar datos al Edge Network de Adobe Experience Platform <!-- what is the correct branding -->. <p>Para organizaciones que aún no utilizan el SDK web, este método de migración es quizás el más sencillo para obtener datos en Edge Network (que requiere el menor número de pasos), pero todo el trabajo se realiza por adelantado, como la creación del esquema XDM.</p><p>Los pasos básicos son:</p><ol><li>Creación de un esquema XDM para su organización</li><li>Implementación del SDK web</li><li>Envío de datos a Platform</li></ol> | Alto | Alto |
| **Migre su implementación de Adobe Analytics para utilizar el SDK web**</br> Si la implementación de Adobe Analytics es AppMeasurement para la extensión de Analytics, puede migrarla para utilizar el SDK web de Adobe Experience Platform y comenzar a enviar datos al Edge Network antes de enviarlos al Customer Journey Analytics. <!-- what else? --><p>Esta es la forma más sencilla y fluida de llevar los datos a Edge Network; requiere más pasos, pero ofrece una transición más metódica con hitos más tangibles.</p><p>Los pasos básicos son:</p><ol><li>Mueva la implementación de Adobe Analytics existente al SDK web y compruebe que todo funciona allí.</li><li>Cree un esquema XDM para su organización a medida que tenga tiempo.</li><li>Utilice la asignación de flujo de datos para asignar todos los campos del objeto de datos al esquema XDM.</li><li>Envío de datos a Platform</li></ol> | Moderar | Alto |
| **Configure la implementación existente del SDK web de Adobe Analytics para enviar datos al Customer Journey Analytics**</br> Si la implementación de Adobe Analytics ya está utilizando el SDK web, puede empezar a enviar datos al Customer Journey Analytics.<p>Antes de enviar datos a Customer Journey Analytics, considere la posibilidad de actualizar el esquema de Adobe Analytics para las necesidades específicas de su organización y de cualquier otra aplicación de Platform que vaya a utilizar.</p><p>Los pasos básicos son:</p><ol><li>Comience a enviar datos al Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Opcional) Cree un esquema XDM para su organización a medida que tenga tiempo.</li><li>Utilice la asignación de flujo de datos para asignar todos los campos del objeto de datos al esquema XDM.</li></ol> | Bajo | Alto |
| **Conector de origen de Analytics**</br> Si la implementación de Adobe Analytics es AppMeasurement para la extensión de Analytics, puede empezar a enviar datos a una vista de datos en Customer Journey Analytics.<p>Esta es la forma más sencilla de obtener datos para Customer Journey Analytics, pero es el método menos viable a largo plazo.</p> | Bajo | Bajo |

{style="table-layout:auto"}

Utilice el siguiente diagrama para visualizar dónde se encuentra cada método de migración en el espectro en términos de nivel de esfuerzo, así como la viabilidad a largo plazo que cada uno logra:

![métodos de migración de cja](assets/cja-migration-methods.png)

## Evalúe los métodos de migración disponibles en función de la implementación de Adobe Analytics actual

No todos los métodos de migración están disponibles para cada tipo de implementación de Adobe Analytics.

Utilice la información siguiente como directrices generales para comprender mejor qué método de migración es el más adecuado para su organización.

Póngase en contacto con el representante del Adobe si necesita asesoramiento, orientación o asistencia más específicos.

| Implementación de Adobe Analytics | Métodos de migración disponibles |
|---------|----------|
| AppMeasurement | <ul><li>Nueva implementación del SDK web</li><li>Migración de Adobe Analytics al SDK web</li><li>Conector de origen de Analytics</li></ul> |
| Extensión de Adobe Analytics | <ul><li>Nueva implementación del SDK web</li><li>Migración de Adobe Analytics al SDK web</li><li>Conector de origen de Analytics</li></ul> |
| SDK web | <ul><li>Configuración de la implementación del SDK web de Adobe Analytics para enviar datos al Customer Journey Analytics</li></ul> |

{style="table-layout:auto"}

## Valore las ventajas y desventajas de los métodos de migración disponibles

Las ventajas y desventajas de un método de migración determinado difieren según la implementación de Adobe Analytics existente.

Antes de usar la información siguiente para determinar qué método de migración es el adecuado para usted, revise la información en [Comprender los métodos de migración](#understand-migration-methods) si aún no lo ha hecho.

### Extensión de AppMeasurement y Adobe Analytics

La siguiente tabla muestra los métodos de migración disponibles para las organizaciones que han implementado Adobe Analytics con AppMeasurement o la extensión de Adobe Analytics:

| Método de migración | Ventajas | Desventajas |
|---------|----------|---------|
| **Nueva implementación del SDK web** | <ul><li>Utiliza un esquema XDM, un esquema flexible para definir los campos que necesite</li><li>No depende de la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)</li><li>No existen limitaciones de caracteres (100 caracteres para props)</li><li>Disponibilidad de datos y creación de informes de alto rendimiento gracias a que Adobe Experience Platform está diseñado para ofrecer potencia [casos de uso de personalización en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=es)</li><li>Preparado para el futuro (recibirá las últimas funciones y características)</li><li>Consolide las etiquetas para la recopilación de datos de Adobe Experience Cloud entre otros productos de Experience Cloud (AJO, RTCDP, etc.)</li><li>[ID de dispositivos de origen](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=es) para mejorar la precisión de la identificación del visitante</li></ul> | <ul><li>El método de migración más lento y exigente<p>Debe volver a crear el esquema completo en XDM para poder iniciar la implementación del SDK web</p></li></ul> |
| **Migración de Adobe Analytics al SDK web** | <ul><li>Conserva las reglas y los elementos de datos ya configurados en la implementación de Adobe Analytics.</li><li>Permite pasar al SDK web sin afectar a los informes de Adobe Analytics existentes.</li><li>Proporciona flexibilidad para crear un esquema XDM para su organización más adelante.</br>No requiere el grupo Campo de evento de Adobe Analytics Experience en Customer Journey Analytics. <!-- With the new implementation, you're double-counting with 2 implementation; with the migration, you're double-counting, but both of them are through Edge Network. --></li><li>No depende de la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)</li><li>No existen limitaciones de caracteres (100 caracteres para props)</li><li>Disponibilidad de datos y creación de informes de alto rendimiento gracias a que Adobe Experience Platform está diseñado para ofrecer potencia [casos de uso de personalización en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=es)</li><li>Preparado para el futuro (recibirá las últimas funciones y características)</li><li>Consolide las etiquetas para la recopilación de datos de Adobe Experience Cloud entre otros productos de Experience Cloud (AJO, RTCDP, etc.)</li><li>[ID de dispositivos de origen](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=es) para mejorar la precisión de la identificación del visitante</li></ul> | <ul><li>Debe ajustarse a un esquema XDM en algún momento futuro, utilizando la asignación de flujos de datos.</li><li>Incurre en alguna deuda técnica. Por ejemplo, el AppMeasurement heredado o el código de extensión de Analytics pueden permanecer. </li></ul> |
| **Conector de origen de Analytics** | <ul><li>Método de migración menos laborioso y exigente. <p>Los datos se migran rápidamente al Customer Journey Analytics con una inversión mínima</p></li></ul> | <ul><li>Los datos no se envían al Edge Network y no se pueden compartir con otras aplicaciones de Adobe Experience Platform; solo se limitan al Customer Journey Analytics<li>Es difícil pasar al SDK web en el futuro</li><li>Utiliza el grupo de campos Evento de experiencia de Analytics en el esquema.</br>Este grupo de campos añade muchos eventos de Adobe Analytics que no son necesarios en el esquema del Customer Journey Analytics.  Esto puede generar un esquema más complejo y desordenado que lo que se necesita de otro modo para Customer Journey Analytics.</li><li>Nivel máximo de [latencia](/help/admin/guardrails.md#latencies) en todos los métodos de implementación</li></ul> |

{style="table-layout:auto"}

### SDK web

En la tabla siguiente se muestran los métodos de migración disponibles para las organizaciones que han implementado Adobe Analytics con el SDK web:

| Método de migración | Ventajas | Desventajas |
|---------|----------|---------|
| **Configuración de la implementación del SDK web de Adobe Analytics para enviar datos al Customer Journey Analytics** | Este es el método de migración preferido si su implementación de Adobe Analytics ya está utilizando el SDK web. <p>Al utilizar este método de implementación, puede elegir si desea utilizar el esquema de Adobe Analytics existente o puede actualizar al esquema XDM para alinearse mejor con las necesidades de su organización a medida que comienza a utilizar otras aplicaciones de Platform.</p><p>**Uso del esquema de Adobe Analytics**</p><p>Las ventajas de utilizar el esquema de Adobe Analytics incluyen:</p><ul><li>Facilidad de migración<p>Si ya está enviando datos a Adobe Analytics con el SDK web de Adobe Experience Platform, puede agregar un servicio adicional al conjunto de datos para enviar datos a Adobe Experience Platform (que luego se puede utilizar en la configuración de Customer Journey Analytics).</p></li></ul><p>Las desventajas de utilizar el esquema de Adobe Analytics incluyen:</p><ul><li>Aunque el uso del esquema de Adobe Analytics no le limita en términos de cómo se puede utilizar con otras aplicaciones de Platform, sí que resulta en un esquema más complejo de lo que podría ser de otra manera. Esto se debe a que el esquema de Adobe Analytics contiene muchos objetos específicos de Adobe Analytics que probablemente su organización no vaya a utilizar.<p>Cuando es necesario realizar cambios en el esquema, debe revisar miles de campos no utilizados para encontrar el campo que requiere actualización.</p></li></ul><p>**Uso del esquema XDM**</p><p>Las ventajas de actualizar el esquema XDM incluyen:</p><ul><li>Un esquema optimizado que se adapta a las necesidades de su organización y a las aplicaciones de Platform específicas que utiliza.</li><p>Cuando es necesario realizar cambios en el esquema, no es necesario revisar miles de campos no utilizados para encontrar el campo que requiere actualización.</p></ul><p>Las desventajas de actualizar el esquema XDM incluyen:</p><ul><li>La actualización del esquema es un proceso laborioso que es necesario antes de empezar a enviar datos al Customer Journey Analytics.</li></ul> | Ninguno |

{style="table-layout:auto"}

## A continuación, envíe datos a Adobe Experience Platform

Después de utilizar la información anterior para elegir un método de migración, aprenda a [envío de datos a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) según el método de migración elegido.
