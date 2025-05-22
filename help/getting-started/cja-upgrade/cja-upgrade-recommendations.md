---
title: Actualización de Adobe Analytics a Customer Journey Analytics
description: Más información sobre la ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: dfc9ba843fbddc135c0f8160fb672adb36e9146f
workflow-type: ht
source-wordcount: '3281'
ht-degree: 100%

---

# Actualización de Adobe Analytics a Customer Journey Analytics

Al actualizar de Adobe Analytics a Customer Journey Analytics, puede seguir los [pasos de actualización recomendados](#recommended-upgrade-steps-for-most-organizations). O bien puede [generar dinámicamente pasos de actualización](#dynamically-generate-upgrade-steps-for-your-organization) según las circunstancias únicas de su organización.

## Pasos de actualización recomendados para la mayoría de las organizaciones {#upgrade-process}

El proceso recomendado para actualizar de Adobe Analytics a Customer Journey Analytics es una nueva implementación del SDK web de Experience Platform, que es el método de recopilación de datos preferido para Customer Journey Analytics. Junto con el SDK web, Adobe también recomienda utilizar el conector de origen de Analytics para facilitar la transición a Customer Journey Analytics. Utilice el conector de origen de Analytics para conservar los datos históricos de Adobe Analytics y realizar comparaciones de datos en paralelo.

Cuando disponga de suficientes datos históricos mediante el SDK web de Experience Platform y haya realizado la transición completa a Customer Journey Analytics, el conector de origen de Analytics se podrá desactivar y el SDK web se podrá utilizar de forma exclusiva.

>[!NOTE]
>
>Si los pasos de actualización que se describen en esta sección no son prácticos para su organización, utilice la guía de actualización de Customer Journey Analytics para generar dinámicamente los pasos de actualización que se adapten a las circunstancias únicas de su organización. (Para acceder a la guía desde Customer Journey Analytics, seleccione la pestaña **[!UICONTROL espacio de trabajo]** y, a continuación, seleccione **[!UICONTROL Actualizar a Customer Journey Analytics]** en el panel izquierdo). Siga las instrucciones que aparecen en la pantalla).

### Proceso de actualización recomendado de alto nivel {#high-level-upgade-process}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-historical-data"
>title="Datos históricos de Adobe Analytics"
>abstract="Incorporar sus datos históricos del grupo de informes de Adobe Analytics a Adobe Experience Platform y Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

1. **Implemente el SDK web de Experience Platform (para la recopilación de datos continua)**

   Una nueva implementación del SDK web de Experience Platform es la mejor manera de recopilar datos para Customer Journey Analytics. Ofrece la mejor base para sacar el máximo partido de Customer Journey Analytics, ya que es el método con más rendimiento, sencillo y preparado para el futuro para implementar Customer Journey Analytics.

   * Creación de informes de alto rendimiento y disponibilidad de datos porque Adobe Experience Platform se ha diseñado para potenciar los casos de uso de personalización en tiempo real

   * Consolidación de la implementación de la recopilación de datos de Adobe Experience Cloud entre otros productos de Experience Cloud (AJO, RTCDP, etc.)

   * No depende de la nomenclatura de Adobe Analytics (prop, eVar, evento, etc.)

1. **Configure el conector de origen de Adobe Analytics (para transferir datos históricos)**

   Para facilitar una transición sin problemas al uso del SDK web de Experience Platform con Customer Journey Analytics, Adobe también recomienda utilizar el conector de origen de Adobe Analytics. Esto le permite conservar los datos históricos y ver los datos de su implementación de Adobe Analytics existente en Customer Journey Analytics, junto con los datos de su nueva implementación del SDK web de Experience Platform.

   El conector de origen de Analytics le permite:

   * Incorporar sus datos históricos del grupo de informes de Adobe Analytics a Adobe Experience Platform y Customer Journey Analytics.

     Puede mantener el conector de origen de Analytics en ejecución durante el tiempo que necesite para conservar los datos históricos de Adobe Analytics.

   * Ver los datos recopilados con la implementación original de Adobe Analytics (AppMeasurement, la extensión de Analytics o la extensión del SDK web) en Customer Journey Analytics. Puede comparar estos datos en paralelo con los de su nueva implementación del SDK web.

     Puede mantener el conector de origen de Analytics en ejecución hasta que se haya familiarizado y esté cómodo con las diferencias. <!--elaborate on what those differences are? -->

   El conector de origen de Analytics como implementación independiente no es el método recomendado a largo plazo para utilizar Customer Journey Analytics. Esto se debe a la elevada latencia, a los esquemas desordenados y complejos, a la dependencia de la nomenclatura de Adobe Analytics (prop, eVar, etc.) y a la dificultad para pasar finalmente del conector de origen de Analytics a la implementación del SDK web recomendada.

### Pasos de actualización recomendados detallados

Los siguientes pasos describen el proceso recomendado para actualizar de Adobe Analytics a Customer Journey Analytics.

Cada paso ofrece una explicación de alto nivel de un proceso más detallado. Siga el vínculo de cada paso y complete las tareas asociadas; a continuación, vuelva a esta página y continúe con el siguiente paso del proceso.

1. [Planifique la arquitectura de su esquema XDM](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

1. [Cree su esquema personalizado deseado en Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   Tenga en cuenta las siguientes opciones al crear el esquema:

   * Si desea integrar Customer Journey Analytics con RTCDP, debe habilitar la opción **[!UICONTROL Perfil]** en su esquema, tal como se describe en [Creación de un esquema XDM para utilizarlo con Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md). Con esta opción habilitada, cuando los datos se introducen en conjuntos de datos basados en este esquema, los datos se combinan con el perfil del cliente en tiempo real.

   * Si desea incluir datos de medios de streaming, debe [configurar su esquema para ingerir y utilizar datos de streaming](/help/data-ingestion/streaming.md).

1. [Cree un conjunto de datos en Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md).

1. (Opcional) Si utiliza datos de clasificación en Adobe Analytics, puede añadir datos de clasificación al conjunto de datos en Customer Journey Analytics.

   Para ello, [cree un conjunto de datos de consulta para cada dimensión que contenga datos de clasificación](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. En el caso de las implementaciones de Adobe Analytics que usan AppMeasurement o la extensión de Analytics (etiquetas), [cree una secuencia de datos en Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md). <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   En el caso de las implementaciones de Adobe Analytics que utilizan el SDK web, ya existe una secuencia de datos. Para más información, consulte [Configurar la implementación existente del SDK web de Adobe Analytics para enviar datos a Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md).

1. [Añada Adobe Experience Platform como servicio a la secuencia de datos](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md).

1. (Opcional) Si desea integrar Customer Journey Analytics con Adobe Journey Optimizer, utilice el objeto de personalización en su implementación para utilizarlo en Adobe Journey Optimizer.

1. Expanda la sección que describe cómo desea implementar el SDK web de Experience Platform para la implementación de Customer Journey Analytics y, a continuación, complete los pasos asociados:

   +++Implementación manual (archivo JS)

   1. [Añada alloy.js a su sitio](https://experienceleague.adobe.com/es/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22)

   1. Rellene un objeto XDM y envíelo a la secuencia de datos.

+++

   +++Etiquetas

   1. [Cree una propiedad de etiqueta y añada la extensión del SDK web de Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md).

   1. [Añada la extensión de SDK web de Adobe Experience Platform a su propiedad de etiqueta](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)

   1. [Implemente la etiqueta del cargador en su sitio](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md).

   1. [Añada la lógica de recopilación de datos XDM a su etiqueta](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md).

+++

+++ API

   1. Utilice la API de Edge Network para enviar datos a la secuencia de datos deseada.

+++

1. [Valide que su implementación del SDK web está enviando datos a un conjunto de datos](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md).

1. [Cree una conexión en Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. (Opcional) Asocie datos web a datos de otros canales, como los datos del centro de llamadas.

   Para ello añada conjuntos de datos adicionales a la conexión de Customer Journey Analytics, como se describe en [Importación de datos web y de centros de llamadas](/help/use-cases/cross-channel/call-center.md).

1. [Cree una vista de datos en Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

1. [Valide que los datos fluyen hacia la vista de datos en Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md).

1. En su entorno de Adobe Analytics, [use el inventario de Analytics](https://experienceleague.adobe.com/es/docs/analytics/admin/admin-tools/analytics-inventory) para ver una descripción general completa de su entorno de Adobe Analytics, que incluya el número de proyectos y componentes, grupos de informes, usuarios y más.

1. [Migre proyectos y componentes](https://experienceleague.adobe.com/es/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration).

   <!-- You might not want to do this, based on the schema? Ask Zach. Will it work if you have all new schema fields? What would you want to just build from scratch. Maybe everything? -->

1. (Opcional) Si usa canales de marketing en Adobe Analytics, puede [crear un campo derivado del canal de marketing en Customer Journey Analytics](/help/data-views/derived-fields/derived-fields.md#marketing-channels).

   Los campos derivados son un aspecto importante de los informes en tiempo real de Customer Journey Analytics. Un campo derivado permite definir manipulaciones de datos (a menudo complejas) sobre la marcha, mediante un generador de reglas personalizable. 

   Un uso de los campos derivados es definir un campo de canal de marketing derivado que determine el canal de marketing adecuado en función de una o varias condiciones (por ejemplo, parámetro de URL, dirección URL de página o nombre de página).

   Utilice [la plantilla de función de canales de marketing](/help/data-views/derived-fields/derived-fields.md#marketing-channels) en los campos derivados para crear rápidamente un campo derivado para los canales de marketing.

1. Compare los datos de la antigua implementación de Adobe Analytics con los datos de Customer Journey Analytics de su nueva implementación y asegúrese de que entiende las diferencias y por qué existen. <!-- Expound on this. Link to somewhere? There will be a lot of differences. -->

1. Obtenga datos históricos de Adobe Analytics mediante el conector de origen de Analytics:

   >[!NOTE]
   >
   >Siga estos pasos si no ha creado anteriormente un conector de origen de Analytics.
   >
   >Si ya está usando el conector de origen de Analytics con Customer Journey Analytics, siga los pasos que se indican en [Transición del conector de origen de Analytics al SDK web para Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

   1. [Crear un esquema XDM para el conector de origen de Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

   1. Si aún no tiene un conector de origen de Analytics, [cree uno y asigne campos al esquema XDM](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).

      O bien

      Si ya tiene un conector de origen de Analytics, [asigne campos del conector de origen a su esquema XDM](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md).

   1. [Añada el conjunto de datos del conector de origen de Analytics a la conexión](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. Planifique la incorporación del usuario.

   Al igual que en Adobe Analytics, Analysis Workspace es la principal herramienta de cara al usuario en Customer Journey Analytics. Sin embargo, existen algunas diferencias clave al utilizar Analysis Workspace en Customer Journey Analytics que los usuarios deben tener en cuenta.

   Debe dar a los usuarios tiempo suficiente (de 3 a 6 meses) para familiarizarse con las diferencias clave de Analysis Workspace en Customer Journey Analytics.

   Para obtener información sobre algunas de las diferencias clave entre Adobe Analytics y Customer Journey Analytics, consulte [Guía del usuario para usuarios de Adobe Analytics](/help/getting-started/aa-to-cja-user.md).

1. Obtenga información sobre la [compatibilidad de funciones en Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md). La mayoría de las funciones de Adobe Analytics son compatibles con Customer Journey Analytics y hay muchas funciones adicionales disponibles en Customer Journey Analytics.

1. Deshabilite Adobe Analytics cuando la implementación del SDK web de Customer Journey Analytics haya finalizado y esté cómodo con los datos que está recopilando.

   Adobe le recomienda mantener el entorno de Adobe Analytics en ejecución durante un período de tiempo después de implementar Customer Journey Analytics.

   Para obtener más información sobre los usos de Adobe Analytics durante una actualización y después de ella, así como el momento sugerido para deshabilitar Adobe Analytics, consulte [Evaluar cuánto tiempo necesita Adobe Analytics después de actualizar a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md).

## Creación dinámica de pasos de actualización para su organización

Según varios factores, como la cronología y las restricciones de recursos, los pasos de actualización recomendados que se describen en [Conocer los pasos de actualización recomendados](#recommended-upgrade-steps-for-most-organizations) podrían no ser prácticos para su organización. En este caso, puede crear dinámicamente los pasos de actualización en función de las circunstancias únicas de su organización. El proceso de generación de estos pasos difiere en función de si ya tiene acceso a Customer Journey Analytics.

### Para clientes que tienen acceso a Customer Journey Analytics

Para crear dinámicamente los pasos de actualización en función de las circunstancias únicas de su organización:

1. Guía de actualización de Customer Journey Analytics.

   En Customer Journey Analytics, seleccione la pestaña **[!UICONTROL espacio de trabajo]** y, a continuación, seleccione **[!UICONTROL Actualizar a Customer Journey Analytics]** en el panel izquierdo. Siga las instrucciones que aparecen en la pantalla.

   Después de completar esta guía de actualización, se proporcionan instrucciones paso a paso, que describen los pasos de actualización óptimos que son exclusivos de los requisitos de su organización. Estos pasos de actualización son los que mejor se adaptan a su entorno de Adobe Analytics existente y a sus metas para Customer Journey Analytics. Los pasos de actualización están disponibles como vínculo compartible o como archivo descargable .csv.

1. Siga las instrucciones paso a paso generadas para actualizar a Customer Journey Analytics.

### Para clientes que aún no tienen acceso a Customer Journey Analytics

Para crear dinámicamente los pasos de actualización en función de las circunstancias únicas de su organización:

1. Póngase en contacto con el equipo de cuentas de Adobe para completar la Guía de actualización de Customer Journey Analytics.

   El equipo de cuentas de Adobe puede guiarle a través de la guía de actualización y proporcionarle un archivo .csv que contenga las preguntas, sus respuestas y los pasos de actualización generados dinámicamente que son únicos para su organización.

   Antes de ponerse en contacto con el equipo de cuentas de Adobe, familiarícese con las preguntas que se incluyen en la Guía de actualización de Customer Journey Analytics y determine sus respuestas. La Guía de actualización de Customer Journey Analytics contiene las siguientes preguntas y posibles respuestas:


   | Pregunta | Respuestas disponibles | Información adicional |
   |---------|----------|---------|
   | Seleccione la opción que describa su implementación actual de Adobe Analytics. Esta información puede afectar a las opciones de actualización alternativas que podrían estar a su disposición al actualizar a Customer Journey Analytics. | Seleccione una: <ul><li>**AppMeasurement:**<br/> Una implementación de JavaScript que carga AppMeasurement.js en una página y envía datos a Adobe mediante el objeto s (por ejemplo, s.eVar 1).</li><li>**Extensión de Adobe Analytics (etiquetas):** <br/>una implementación de etiquetas que carga la recopilación de datos de Adobe Experience Platform (anteriormente conocida como Launch). La etiqueta tiene instalada la extensión de Adobe Analytics.</li><li>**Extensión de Experience Platform Web SDK (etiquetas):**<br/> Implementación de etiquetas que carga la recopilación de datos de Adobe Experience Platform (anteriormente conocida como Launch). La etiqueta tiene instalada la extensión del SDK web.</li><li>**Experience Platform Web SDK (alloy.js):** Una implementación de JavaScript que carga la biblioteca del SDK web (alloy.js) en una página y envía datos a Adobe mediante una carga útil JSON.</li><li>**Bulk Data Insertion API:**<br/> Una implementación que utiliza la API de inserción de datos o la API de inserción de datos en lote.</li><li>**Experience Platform Mobile SDK:**<br/> Una mplementación que utiliza Adobe Experience Platform Mobile SDK.</li><li>**AppMeasurement con una herramienta de administración de etiquetas de terceros:**<br/> Implementación que usa una herramienta de administración de etiquetas de terceros.</li><li>**Un producto que no sea Adobe Analytics:**<br/> Una implementación que recopila datos para un producto distinto de Adobe Analytics, como Google Analytics. Al seleccionar esta opción, se desactivan varias opciones de la guía de actualización que no se aplican cuando actualiza a Customer Journey Analytics desde un producto distinto de Adobe Analytics. </li><li>**No lo sé:**<br/> Si no es usted la persona que administra la implementación, puede seleccionar temporalmente esta opción.</li></ul><p>Seleccionar si procede:<ul><li>**Nuestra implementación utiliza actualmente el conector de origen de Analytics:**<br/> el conector de origen de Analytics permite obtener fácilmente valor con Customer Journey Analytics, pero requiere que se pague tanto por Adobe Analytics como por Customer Journey Analytics. Esta guía puede ayudarle a avanzar hacia una implementación independiente del SDK web.</li></ul></p> | <ul><li>[Conozca su implementación de Adobe Analytics y cómo afecta a la actualización a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md#understand-your-adobe-analytics-implementation-and-how-it-affects-your-upgrade-to-customer-journey-analytics)</li><li>[Transición del conector de origen de Analytics al SDK web para Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)</li></ul> |
   | La mayoría de las funciones de Adobe Analytics están disponibles en Customer Journey Analytics. Sin embargo, las siguientes funciones deben tenerse en cuenta durante el proceso de actualización. Seleccione las que tenga previsto utilizar. | Seleccionar todo lo que corresponda:<ul><li>**Datos históricos de Adobe Analytics:**</br> incorpore sus datos históricos del grupo de informes de Adobe Analytics a Adobe Experience Platform y Customer Journey Analytics.</li><li>**Componentes y proyectos de Adobe Analytics:**</br> Los componentes de Adobe Analytics incluyen: proyectos (con sus tablas y visualizaciones de forma libre asociadas), segmentos y métricas calculadas.</li><li>**Superposición de mapas Acivity y seguimiento de vínculos:**</br> Una extensión del explorador que permite ver los datos de seguimiento de vínculos como una superposición en el sitio.</li><li>**Datos de clasificación:**</br> Agrupe o clasifique los datos como dimensiones independientes.</li><li>**Canales de marketing:**</br> Cree reglas que clasifiquen la forma en que los clientes llegan al sitio.</li><li>**Almacén de datos:**</br> Exporte datos procesados de Adobe Analytics en formato de hoja de cálculo.</li><li>**Fuentes de datos:**Aún no hay disponible un reemplazo exacto de las fuentes de datos en Customer Journey Analytics. Sin embargo, se puede lograr una funcionalidad similar con capacidades como la exportación de tabla completa, la exportación de conjuntos de datos de Platform, la integración de herramientas de BI y la API de creación de informes.</br></li><li>**Transmisión de datos multimedia:**</br> Un complemento de Adobe Analytics y Customer Journey Analytics que está especializado en la recopilación de datos de medios, como audio, vídeo o contenido transmitido.</li></ul> | <ul><li>[Comprender la compatibilidad con funciones de Adobe Analytics al actualizar a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)</li></ul> |
   | La mayoría de las nuevas funciones ya están disponibles en Customer Journey Analytics. Sin embargo, las siguientes funciones deben tenerse en cuenta durante el proceso de actualización. Seleccione las que tenga previsto utilizar. | Seleccionar todo lo que corresponda:<ul><li>**Asocie datos recopilados con datos de otras fuentes (por ejemplo, datos del centro de contacto):**</br>(Recomendado) Asocie datos de varias propiedades web, móviles y sin conexión para crear una única vista consolidada del comportamiento de los clientes. La posibilidad de combinar datos de análisis de otros canales es el caso de uso principal de Customer Journey Analytics.</li><li>**Unir resultados de otros conjuntos de datos mediante una dimensión personalizada:**<br/> Si alguno de los conjuntos de datos no comparte un identificador principal (como un ID de Experience Cloud), aún puede unir esos datos mediante otra dimensión, como el nombre de usuario de inicio de sesión o la dirección de correo electrónico.</li><li>**Integrar con Adobe Journey Optimizer:**<br/> Ofrecer experiencias conectadas, contextuales y personalizadas a sus clientes.</li><li>**Integración con Adobe Real-Time CDP:**<br/> Combine datos de perfil de varias fuentes para generar audiencias y segmentos basados en los rasgos de los usuarios.</li><li>**Integrar con Adobe Target (A4T):**<br/> Adobe recomienda integrar con Adobe Journey Optimizer para casos de uso de personalización. La integración con Adobe Target es posible, pero es una solución temporal.</li><li>**Integrar con Adobe Audience Manager:**<br/> Adobe recomienda integrar con Adobe Real-time CDP para casos de uso basados en audiencias. La integración con Audience Manager es posible, pero es una solución temporal.</li></ul> | [Descripción de las funciones exclusivas de Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-customer-journey-analytics-features.md) |
   | Seleccione cómo tiene previsto utilizar Adobe Analytics y Customer Journey Analytics: | Seleccione una: <ul><li>**Tengo la intención de pasar completamente a Customer Journey Analytics desde Adobe Analytics:**<br/>(Recomendado) Adobe recomienda que realice la transición completa de Adobe Analytics a Customer Journey Analytics. Durante el período de transición, debe planificar la ejecución de Adobe Analytics junto con Customer Journey Analytics para realizar comparaciones de datos en paralelo. Cuando se sienta cómodo con los datos, puede deshabilitar Adobe Analytics.</li><li>**Tengo la intención de mantener ambos productos de Analytics:**<br/>(No recomendado) Si selecciona esta opción, el contrato con Adobe incluye tanto Adobe Analytics como Customer Journey Analytics, lo que puede resultar más caro para su organización con el tiempo.</li></ul> | [Evalúe cuándo deshabilitar Adobe Analytics después de actualizar a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md) |
   | Seleccione cómo desea configurar su esquema de Customer Journey Analytics: | Seleccione una: <ul><li>**Deseo usar un esquema adaptado a mi organización:**</br>(Recomendado) La personalización del esquema permite a su organización realizar un seguimiento de lo que necesita y evitar la sobrecarga asociada a campos confusos e innecesarios. Esta opción incluye grupos de campos añadidos por el SDK web y grupos de campos personalizados para su organización.</li><li>**Deseo usar el esquema predeterminado de Adobe Analytics:**</br>(No recomendado) El esquema de Adobe Analytics contiene más de mil campos, lo que puede generar un esquema desordenado y complejo. Su organización se vería obligada a seguir utilizando el concepto de props y eVars, que es un concepto heredado que no se usa en Customer Journey Analytics. La integración con otros servicios de Adobe Experience Platform es más difícil.</li></ul> | [Elija su esquema para Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) |
   | Seleccione su forma preferida de implementar Customer Journey Analytics: | <ul><li>**Implementación manual (alloy.js):**<br/> Incluya la biblioteca del SDK web (alloy.js) en todas las páginas del sitio.</li><li>**Etiquetas:**<br/>(Recomendado) Si aún no utiliza Etiquetas, instale el cargador de etiquetas en su sitio. Si ya está utilizando etiquetas, puede añadir la extensión del SDK web a la propiedad de su etiqueta. Esta opción incluye implementaciones que utilizan etiquetas en la recopilación de datos de Adobe Experience Platform y sistemas de administración de etiquetas de terceros.</li><li>**API:**<br/> Utilice la API de recopilación de datos para enviar datos directamente a una secuencia de datos. Se admiten los tipos no autenticados (cliente a servidor) y autenticados (servidor a servidor).</li></ul> | [Conocer las opciones de implementación del SDK web al actualizar a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-websdk-implementation.md) |
   | (Opcional) Seleccione un método de actualización alternativo | <ul><li>**Utilice únicamente el conector de origen de Analytics**<br/>(no recomendado): puede utilizar el conector de origen de Analytics como la única ruta de implementación para Customer Journey Analytics. <p>Esta opción ahorra tiempo de implementación al enviar datos rápidamente a Customer Journey Analytics. Sin embargo, incluye varias deficiencias, como una mayor latencia y dificultades para salir de Adobe Analytics en el futuro.</p></li><li>**Quiero usar mi lógica de AppMeasurement con Web SDK:**<br/> En lugar de enviar datos a través de un objeto XDM, envíe todas las variables en formato AppMeasurement a través del objeto de datos.<p>Esta opción ahorra tiempo de implementación al permitirle asignar la lógica de AppMeasurement a XDM, en lugar de rellenar un objeto XDM desde cero. Sin embargo, aumenta la complejidad con el tiempo, ya que cualquier campo que añada en el futuro debe asignarse a XDM en la secuencia de datos.</p></li><li>**Deseo enviar mi capa de datos a Adobe sin configuración adicional:**<br/> En lugar de enviar datos a través de un objeto XDM, puede enviar toda su capa de datos a Adobe a través del objeto de datos.<p>Esta opción ahorra tiempo de implementación al permitirle asignar la capa de datos a XDM, en lugar de rellenar un objeto XDM desde cero. Sin embargo, esta asignación supone una gran cantidad de trabajo porque habrá una cantidad significativa de datos que Adobe no puede interpretar fácilmente. Esta opción también introduce una complejidad adicional a lo largo del tiempo, ya que cualquier campo que añada a los datos más adelante debe asignarse a XDM en la secuencia de datos.</p></li></ul> | <ul><li>[Alternativa de actualización: uso exclusivo del conector de origen de Analytics para actualizar a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li><li>[Alternativa de actualización: utilice la recopilación de datos de AppMeasurement con Experience Platform Web SDK y Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Alternativa de actualización: envíe la capa de datos a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-data-layer.md)</li></ul> |

   Después de completar esta guía de actualización con su equipo de cuenta de Adobe, se le proporcionará un archivo .csv que contiene las preguntas, sus respuestas y los pasos de actualización generados dinámicamente que mejor se ajustan a su entorno de Adobe Analytics existente y a sus objetivos para Customer Journey Analytics.

1. Siga las instrucciones paso a paso generadas en el archivo .csv para actualizar a Customer Journey Analytics.

<!--

Customer Journey Analytics is the next generation of analytics. It allows multi-channel data collection (both online and offline data), combined with powerful report-time processing functionality (through the definition of components and derived fields in data views). 



When upgrading from Adobe Analytics to Customer Journey Analytics, no single set of upgrade steps exist that are optimal for every organization.

Adobe recommends using the dynamically generated upgrade steps that are unique to your organization. These upgrade steps are generated after you complete an upgrade questionnaire, which helps you understand the best way for your organization to upgrade to Customer Journey Analytics. 

Generic upgrade steps are also available.

1. **Implement the Experience Platform Web SDK**

   A new implementation of the Experience Platform Web SDK provides the best foundation to get the most out of Customer Journey Analytics. 
   
   It is the most performant, straightforward, and future-proof method for implementing Customer Journey Analytics:

   * Highly performant reporting and data availability because Adobe Experience Platform is built to power real-time personalization use cases

   * Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)

   * Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)

1. **Set up the Adobe Analytics source connector**

   The Analytics source connector is a recommended part of the piece when upgrading to Customer Journey Analytics. 

   The Analytics source connector allows you to:

   * Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics. 
   
     You can keep the Analytics source connector running for as long as you need to retain the historical Adobe Analytics data. 
   
   * View the data collected with your original Adobe Analytics implementation (either AppMeasurement, the Analytics Extension, or the Web SDK Extension) within Customer Journey Analytics. You can compare this data side-by-side with that of your new Web SDK implementation. 
   
     You can keep the Analytics source connector running until you are familiar and comfortable with the differences. <!--elaborate on what those differences are? -->

<!--

   When you no longer need the Analytics source connector because you have enough historical data from your new implementation and you are familiar with the reporting differences in Customer Journey Analytics, you should turn off the Analytics source connector. With the Experience Platform Web SDK implementation, the Analytics source connector is not needed.  
   
   The Analytics source connector as a stand-alone implementation is not a recommended long-term method for using Customer Journey Analytics. This is because of high latency, cluttered and complex schemas, reliance on Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in eventually moving from the source connector to the recommended Web SDK implementation. 
   
-->
