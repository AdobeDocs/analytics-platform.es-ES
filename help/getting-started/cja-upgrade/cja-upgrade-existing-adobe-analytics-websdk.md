---
title: Configure la implementación de Adobe Analytics Web SDK existente para enviar datos a Platform
description: Obtenga información sobre cómo configurar la implementación de Adobe Analytics Web SDK existente
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 8fdc90ff3392b5d6884872d191a40a762cad6a3f
workflow-type: tm+mt
source-wordcount: '1011'
ht-degree: 52%

---

# Configure la implementación de Adobe Analytics Web SDK existente para enviar datos a Platform {#existing-websdk-implementation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-remove-aa-from-datastream"
>title="Quitar Adobe Analytics como servicio de la secuencia de datos"
>abstract="Con los datos de Web SDK completamente funcionales, colabore con el administrador de la plataforma para quitar Adobe Analytics como servicio del conjunto de datos. Antes de hacerlo, asegúrese de que los usuarios hayan realizado la transición del uso de Adobe Analytics a Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Si la implementación de Adobe Analytics ya está utilizando Adobe Experience Platform Web SDK, puede empezar a enviar datos a Platform configurando una secuencia de datos. O bien, si ya está enviando datos a Platform, solo tiene que crear una conexión entre los conjuntos de datos de Platform y Customer Journey Analytics.


## Ventajas y desventajas

Considere las siguientes ventajas y desventajas de configurar la implementación existente de Adobe Analytics Web SDK para enviar datos a Platform:

| Ventajas | Desventajas |
|----------|---------|
| Esta es la ruta de actualización preferida si la implementación de Adobe Analytics ya está utilizando Web SDK.<ul><li>**Ofrece todas las ventajas de alojar datos en Experience Edge Network**: <p>Estas ventajas son:</p><ul><li>Informes de alto rendimiento y disponibilidad de datos porque Adobe Experience Platform se ha creado para potenciar [casos de uso de personalización en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=es)</li><li>Consolidación de la implementación de la recopilación de datos de Adobe Experience Cloud entre otros productos de Experience Cloud (AJO, RTCDP, etc.)</li><li>No depende de la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)</li></ul><li>**Utiliza la implementación existente**: aunque este enfoque requiere algunos cambios de implementación, no requiere una implementación completamente nueva desde cero. Puede utilizar la capa de datos y el código existentes con cambios mínimos en la lógica de implementación sin que ello afecte a los informes de Adobe Analytics existentes.</li><li>**Proporciona una opción para utilizar un esquema XDM**: puede elegir utilizar el esquema de Adobe Analytics existente o crear un esquema XDM y asignar campos en el objeto de datos al esquema XDM. [Esquemas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas): son un esquema flexible para definir cualquier campo que necesite y solo aquellos campos que sean relevantes. <p>Consulte &quot;Uso de su propio esquema XDM&quot; a continuación para obtener más información sobre las ventajas de utilizar su propio esquema XDM.</p></li><li>**Conserva reglas y elementos de datos**: aunque requiere nuevas acciones de regla, puede reutilizar los elementos de datos y las condiciones de regla existentes con cambios mínimos.</li><li>**Preparación para el futuro**: si decide utilizar su propio esquema XDM, las futuras actualizaciones de implementación son más sencillas.</li></ul> | <ul><li>**Requiere asignación para enviar datos a Platform**: cuando su organización esté lista para utilizar Customer Journey Analytics, debe enviar los datos a un conjunto de datos en Adobe Experience Platform. Esta acción requiere que cada campo del objeto de datos sea una entrada en la herramienta de asignación de la secuencia de datos que lo asigna a un campo de esquema XDM. La asignación solo debe realizarse una vez para este flujo de trabajo y no implica realizar cambios de implementación. Sin embargo, es un paso adicional que no es necesario cuando se envían datos en un objeto XDM.</li><li>**Introduce una complejidad adicional con el tiempo**: cualquier campo que agregue en el futuro debe asignarse a XDM en el conjunto de datos.<p>Cada vez que se añade un nuevo campo a la implementación, puede realizar una de las siguientes acciones:</p><ul><li>**Opción 1:** Rellene una nueva eVar arbitraria o prop en el objeto de datos y, a continuación, asígnelo al campo XDM deseado.<p>Este proceso aporta coherencia a la implementación del lado del cliente, pero requiere asignación.</p></li><li>**Opción 2:** Deje el objeto de datos como una implementación heredada y empiece a rellenar solo el objeto XDM para todos los campos nuevos.<p>Este proceso no requiere asignación, pero significa que algunas de las variables solo se encuentran en un objeto de datos, mientras que otras variables solo se encuentran en un objeto XDM. Cada vez que necesite solucionar problemas de la implementación, debe ir a dos lugares. Asegúrese de que los flujos de trabajo internos se adaptan a esto.</p></li></ul> |

{style="table-layout:auto"}

## Pasos de implementación

1. Comience a enviar datos de Edge Network a Platform. Envíe todas las variables en formato AppMeasurement a través del objeto de datos.

   Para obtener más información, vea [Asignación de variables de objetos de datos a Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping).

1. Elija su esquema.

   Puede elegir si desea utilizar el esquema de Adobe Analytics existente o puede crear un esquema XDM para alinearse mejor con las necesidades de su organización a medida que comienza a utilizar otros servicios de Platform.

   Adobe recomienda crear un esquema XDM. Para obtener más información, consulte [Crear un esquema personalizado para utilizarlo con su implementación de Customer Journey Analytics Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   +++Usar el esquema de Adobe Analytics

   | Ventajas | Desventajas |
   |----------|---------|
   | <p>Las ventajas de utilizar el esquema de Adobe Analytics son:</p><ul><li>Facilidad de actualización<p>Si ya está enviando datos a Adobe Analytics con el SDK web de Adobe Experience Platform, puede añadir un servicio adicional a la secuencia de datos para que envíe los datos a Adobe Experience Platform (que luego se podrán utilizar en la configuración de Customer Journey Analytics).</p></li></ul> | <p>Las desventajas de utilizar el esquema de Adobe Analytics son:</p><ul><li>Aunque el uso del esquema de Adobe Analytics no le limita en términos de cómo se puede utilizar con otras aplicaciones de Platform, sí da lugar a un esquema más complejo de lo que podría ser. Esto se debe a que el esquema de Adobe Analytics contiene muchos objetos específicos de Adobe Analytics que es poco probable que su organización utilice.<p>Cuando es necesario realizar cambios en el esquema, hay que rebuscar entre miles de campos no utilizados para encontrar el campo que requiere actualización.</p></li></ul> |

+++

   +++Crear un esquema XDM

   | Ventajas | Desventajas |
   |----------|---------|
   | <ul><p>Las ventajas de actualizar a su propio esquema XDM son:</p><ul><li>Un esquema optimizado que se adapta a las necesidades de su organización y a las aplicaciones de Platform específicas que utiliza.</li><p>Cuando es necesario realizar cambios en el esquema, no es necesario rebuscar entre miles de campos no utilizados para encontrar el campo que requiere actualización.</p></ul> | <p>Las desventajas de actualizar a su propio esquema XDM son:</p><ul><li>La actualización del esquema es un proceso laborioso que es necesario realizar antes de empezar a enviar datos a Platform.</li></ul> |

+++

1. Utilice la asignación de secuencia de datos para asignar todos los campos del objeto de datos al esquema XDM.

   Para obtener más información, consulte [Asignación](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping) en [Preparación de datos para la recopilación de datos](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep) en la documentación de Experience Platform.

1. Siga los [pasos de actualización recomendados](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) o los [pasos de actualización generados dinámicamente](https://gigazelle.github.io/cja-ttv/).




