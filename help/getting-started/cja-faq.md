---
title: Preguntas frecuentes de Customer Journey Analytics
description: 'Customer Journey Analytics: Preguntas frecuentes.'
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
solution: Customer Journey Analytics
feature: FAQ
role: User
source-git-commit: 220ebd7dbc3fa75d221690cd6e5828bd94395434
workflow-type: tm+mt
source-wordcount: '2580'
ht-degree: 99%

---

# Preguntas frecuentes

Adobe Customer Journey Analytics es nuestro producto de análisis de próxima generación. Este artículo proporciona respuestas a las preguntas frecuentes sobre Customer Journey Analytics. Para obtener más información, consulte [Compatibilidad con funciones de Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

## &#x200B;1. Requisitos previos {#prerequisites}

+++**¿Necesito [!UICONTROL Private Device Graph] o [!UICONTROL Device Coop] para [!UICONTROL Customer Journey Analytics]?**

No, [!UICONTROL Private Device Graph] y [!UICONTROL Device Coop] no son necesarios para [!UICONTROL Customer Journey Analytics]. De hecho, todavía no son compatibles.

+++


+++**¿Necesito un [!UICONTROL Experience Cloud ID] (ECID) para [!UICONTROL Customer Journey Analytics]?**

No, [!UICONTROL Customer Journey Analytics] admite cualquier ID de un conjunto de datos, ya sea [!UICONTROL ECID] o cualquier otro ID de su elección.

+++


+++**¿Qué sucede si necesito extraer, transformar o cargar datos antes de utilizar [!UICONTROL Customer Journey Analytics]?**

Customer Journey Analytics incluye capacidades de [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html?lang=es) para ayudar a transformar los datos antes de colocarlos en el lago de datos de Adobe Experience Platform. Si necesita extraer, transformar o cargar los datos después de haberlos ingerido, [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=es#queries) proporciona algunas opciones limitadas, aunque puede haber costes adicionales implicados.

+++


## &#x200B;2. Vinculación de datos {#stitching}

+++**¿Puede [!UICONTROL Customer Journey Analytics] “unir” varios dispositivos o conjuntos de datos?**

Sí. [!UICONTROL Customer Journey Analytics] tiene la funcionalidad [Vinculación](../stitching/overview.md) que funciona en eventos autenticados y no autenticados dentro de un conjunto de datos. Esta vinculación permite resolver registros dispares en un único ID vinculado para el análisis entre dispositivos en el nivel de persona.
Además, cuando se utiliza un ID de área de nombres común (ID de persona) en conjuntos de datos dentro de una [Conexión](/help/connections/overview.md), podrá ejecutar el análisis en una combinación perfecta de varios conjuntos de datos, “vinculados” al nivel de la persona.

+++


+++**¿Se admite la unión del comportamiento anónimo al comportamiento autenticado?**

Sí. La [vinculación](../stitching/overview.md) busca los datos de usuario de las sesiones autenticadas y no autenticadas para generar un ID vinculado.

+++


+++**¿Cómo funciona la “repetición” en la vinculación?**

La vinculación “reproduce” los datos en función de los identificadores únicos que ha aprendido. Reproducir pretende vincular eventos inicialmente no autenticados de dispositivos que se han identificado mientras tanto. [Más información](../stitching/overview.md)

+++


+++**¿Cómo funciona la vinculación de datos históricos (relleno)?**

Cuando se activa por primera vez, Adobe proporciona un relleno de datos vinculados que se remontan hasta el momento que seleccione (hasta un máximo de 25 meses, según el paquete de Customer Journey Analytics que le hayan asignado). Para poder rellenar este campo, los datos no vinculados en aquel momento deben tener un tipo de ID efímero. [Más información](../stitching/overview.md)

+++


+++**¿Cuál es el comportamiento esperado para los registros de conjuntos de datos de perfil no vinculados?**

**Escenario de ejemplo**: para unir dos conjuntos de datos en una conexión de Customer Journey Analytics utilizando `CRMid` como ID de la persona. Uno es un conjunto de datos de eventos web con `CRMid` en todos los registros. El otro conjunto de datos es un conjunto de datos de perfil CRM. El 40 % del conjunto de datos CRM tiene `CRMid` presentes en el conjunto de datos de evento web. El otro 60 % no está presente en el conjunto de datos de evento web. ¿Aparecen estos registros en los informes de Analysis Workspace?<p> **Respuesta**: las filas de perfil que no tienen eventos vinculados a ellas se almacenan en Customer Journey Analytics. Sin embargo, no puede verlos en Analysis Workspace hasta que aparezca un evento vinculado a ese ID.

+++

## &#x200B;3. Introducción de datos en [!UICONTROL Customer Journey Analytics] {#ingest}

+++**¿Puedo combinar datos de diferentes zonas protegidas de [!UICONTROL Adobe Experience Platform] en una conexión de [!UICONTROL Customer Journey Analytics]?**

No. No puede acceder a los datos de zonas protegidas. Solo se pueden combinar conjuntos de datos ubicados en la misma zona protegida. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=es#select-sandbox-and-datasets)

+++


+++**¿Cómo puede conectar datos en línea con datos sin conexión en [!UICONTROL Customer Journey Analytics]?**

Siempre que el ID de la persona coincida entre conjuntos de datos, [!UICONTROL Customer Journey Analytics] puede conectar segmentos, atribuciones, flujos, abandonos, etc., entre conjuntos de datos.

+++


+++**¿Cómo puedo llevar mis datos sin conexión a [!UICONTROL Customer Journey Analytics]?**

Su asignación de derechos en Customer Journey Analytics le permite ingerir datos en Experience Platform. A continuación, puede crear conexiones a esos datos y vistas de datos en [!UICONTROL Customer Journey Analytics] para crear informes en Analysis Workspace. El equipo de incorporación de datos de Experience Platform puede ofrecer recomendaciones o asesoría a los clientes si lo necesitan.

+++


+++**¿Cómo puedo obtener datos de [!UICONTROL Adobe Analytics] en [!UICONTROL Customer Journey Analytics]?**

Los datos de [!UICONTROL Adobe Analytics] se pueden conectar a Experience Platform mediante el [conector de origen de Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=es). La mayoría de los campos de [!UICONTROL Adobe Analytics] se transfieren en formato XDM, pero otros campos todavía no están disponibles.

+++


+++**¿Cuánto tiempo se tarda en ensamblar elementos de conjuntos de datos a una vista de datos?**

Tarda unas pocas horas en empezar y unos días en rellenar los últimos 13 meses de datos.

+++


+++**¿Es necesario introducir datos PII para establecer conexiones entre ellos?**

No, puede utilizar cualquier ID, incluido un hash de un ID de cliente, que no es PII.

+++


+++**¿Cuáles son los límites para la ingesta de fechas/marcas de tiempo pasadas o futuras en conjuntos de datos de eventos de Customer Journey Analytics?**

* Con respecto a las fechas y marcas de tiempo anteriores: datos de eventos de hasta diez años.
* Con respecto a las fechas y marcas de hora futuras: datos de eventos (predictivos) hasta un mes en el futuro.

+++


## &#x200B;4. Consideraciones sobre la latencia {#latency}

>[!NOTE]
>
>No hay un tamaño de datos fijo en Customer Journey Analytics y, por lo tanto, Adobe no puede comprometerse con un tiempo de ingesta estándar. Adobe está trabajando activamente para reducir estas latencias a través de las nuevas actualizaciones y la optimización de la ingesta.

* Eventos o datos activos: procesados e ingeridos en un plazo de 90 minutos, una vez que los datos estén disponibles en Adobe Experience Platform. (Tamaño del lote > 50 millones de filas: más de 90 minutos.) Si la identificación está habilitada, la ingesta puede tardar hasta 4 horas. Consulte los [mecanismos de protección](https://experienceleague.adobe.com/es/docs/analytics-platform/using/technotes/guardrails) para obtener más información. 
* Rellenos secundarios pequeños: en un plazo de siete días
* Rellenos de fondo grandes: en 30 días

Adobe ha cambiado recientemente la forma en que procesa los datos en Customer Journey Analytics:

* Los datos de evento del día “actual” se transmiten como datos activos. Cualquier dato con una hora de evento anterior a las 11:59:59 pm (23:59:59) del día anterior se trata como un relleno.
* Cualquier dato de evento con una marca de tiempo de más de 24 horas (incluso si está en el mismo lote que los datos más recientes) se considera relleno y se ingiere con una prioridad inferior.

## &#x200B;5. Configurar la ventana móvil para la retención de datos de [!UICONTROL Conexión] {#data-retention}

La configuración [**[!UICONTROL Habilitar la ventana de datos móvil ]**](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=es#create-connection) permite definir la retención de datos de Customer Journey Analytics como un período de tiempo variable en meses (tres o seis meses, etc). Se configura en un nivel de [!UICONTROL conexión], no de [!UICONTROL conjunto de datos]. La retención de datos se basa en marcas de hora de conjuntos de datos de evento y se aplica solo a conjuntos de datos de evento. No existe ninguna configuración de retención de datos para conjuntos de datos de búsqueda o perfil, ya que no hay marcas de tiempo aplicables.

La principal ventaja es que solo almacena o genera informes sobre datos que son aplicables y útiles, y elimina los datos más antiguos que ya no son útiles. Le ayuda a mantenerse por debajo de los límites del contrato y reduce el riesgo de costes adicionales.

## &#x200B;6. Implicaciones de la eliminación de componentes de datos {#deletion}

Para la eliminación de datos, debe preocuparse por seis tipos de componentes: zona protegida, esquema, conjunto de datos, conexión, vista de datos y proyectos de Workspace. Estos son algunos de los escenarios posibles en los que puede ser necesario eliminar cualquiera de estos componentes:

| Si usted... | Esto sucede... |
| --- | --- |
| Eliminar una zona protegida en [!UICONTROL Adobe Experience Platform] | Al eliminar una zona protegida, se detendrá el flujo de datos a cualquier conexión de [!UICONTROL Customer Journey Analytics] a conjuntos de datos de dicha zona protegida. También se eliminarán conexiones, vistas de datos, métricas y dimensiones relacionadas con esta zona protegida eliminada. | |
| Elimina un esquema en [!UICONTROL Adobe Experience Platform], pero no los conjuntos de datos asociados a dicho esquema | [!UICONTROL Adobe Experience Platform] no permite la eliminación de [!UICONTROL esquemas] que tienen uno o varios [!UICONTROL conjuntos de datos] asociados. Sin embargo, un administrador que tenga el conjunto de derechos adecuado podrá eliminar primero los conjuntos de datos y, a continuación, el esquema. |
| Eliminar un conjunto de datos en el lago de datos de [!UICONTROL Adobe Experience Platform] | Al eliminar un conjunto de datos en el lago de datos de Adobe Experience Platform, se detiene el flujo de datos desde dicho conjunto de datos a cualquier conexión de Customer Journey Analytics que incluya el conjunto de datos. Los datos de ese conjunto de datos no se eliminan automáticamente de las conexiones con Customer Journey Analytics asociadas. |
| Eliminar un conjunto de datos en [!UICONTROL Customer Journey Analytics] | Póngase en contacto con el equipo de cuentas de Adobe para poner en marcha el proceso de eliminación de un conjunto de datos dentro de una conexión que se ha guardado. |
| Eliminar un lote de un conjunto de datos (en [!UICONTROL Adobe Experience Platform]) | Si se elimina un lote de un conjunto de datos de [!UICONTROL Adobe Experience Platform], se eliminará el mismo lote de cualquier conexión de Customer Journey Analytics que contenga ese lote específico. Customer Journey Analytics recibirá una notificación de las eliminaciones de lotes que se produzcan en [!UICONTROL Adobe Experience Platform]. |
| Eliminar un lote **mientras se está ingiriendo** en [!UICONTROL Customer Journey Analytics] | Si solo hay un lote en el conjunto de datos, no aparecerán datos ni datos parciales de dicho lote en [!UICONTROL Customer Journey Analytics]. La ingesta se revierte. Si, por ejemplo, hay cinco lotes en el conjunto de datos y tres de ellos ya se han introducido cuando se eliminó el conjunto de datos, los datos de esos 3 lotes aparecen en [!UICONTROL Customer Journey Analytics]. |
| Eliminar una conexión en [!UICONTROL Customer Journey Analytics] | El mensaje de error indica lo siguiente:<ul><li>Las vistas de datos creadas para la conexión eliminada ya no funcionarán.</li><li> Del mismo modo, los proyectos del Espacio de trabajo que dependan de vistas de datos en la conexión eliminada dejarán de funcionar.</li></ul> |
| Eliminar una vista de datos en [!UICONTROL Customer Journey Analytics] | El mensaje de error indica que dejarán de funcionar todos los proyectos del Espacio de trabajo que dependan de esta vista de datos eliminada. |

## &#x200B;7. Consideraciones al combinar grupos de informes en Customer Journey Analytics {#merge-reportsuite}

Si tiene pensado incorporar datos de Adobe Analytics a través del [Conector de origen de Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=es), tenga en cuenta estas ramificaciones al combinar dos o más grupos de informes de Adobe Analytics.

| Problema | Consideración |
| --- | --- |
| Variables | Es posible que las variables como [!UICONTROL eVars] no se alineen entre grupos de informes. Por ejemplo, eVar1 en el grupo de informes 1 puede apuntar a **[!UICONTROL Página]**. En el grupo de informes 2, eVar1 puede señalar a **[!UICONTROL Campaña interna]**, lo que produce informes mixtos e inexactos. |
| Recuentos de [!UICONTROL Sesiones] y [!UICONTROL Personas] | Se deduplican en los grupos de informes. Como resultado, es posible que los recuentos no coincidan. |
| Anulación de duplicación métrica | Anula la deduplicación de instancias de una métrica (por ejemplo, [!UICONTROL Pedidos]) si varias filas tienen el mismo ID de transacción (por ejemplo, [!UICONTROL ID de compra]). Esto evita el recuento excesivo de las métricas clave. Como resultado, es posible que las métricas como [!UICONTROL Pedidos] no se sumen teniendo en cuenta varios grupos de informes. |
| Moneda | Customer Journey Analytics aún no admite la conversión de moneda. Si los grupos de informes que intenta combinar utilizan distintas monedas base, pueden surgir problemas. |
| [!UICONTROL Persistencia] | La [Persistencia](../data-views/component-settings/persistence.md) se extiende a los grupos de informes, lo que afecta a los [!UICONTROL segmentos], la [!UICONTROL atribución], etc. Los números pueden no sumarse correctamente. |
| [!UICONTROL Clasificaciones] | Las [!UICONTROL clasificaciones] no se deduplican automáticamente al combinar grupos de informes. Al combinar varios archivos de clasificaciones en un único conjunto de datos de [!UICONTROL búsqueda], puede encontrar problemas. |

## &#x200B;8. Componentes de [!UICONTROL Adobe Analytics]

+++**¿Puedo compartir/publicar [!UICONTROL públicos] de [!DNL Customer Journey Analytics] en Real-Time CDP de Experience Platform, o en otras aplicaciones de Experience Cloud?**

Ahora puede [crear y publicar los públicos](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-components/audiences/publish) que haya identificado en Customer Journey Analytics (CJA) en el Perfil del cliente en tiempo real (RTCP) de Adobe Experience Platform para la segmentación y personalización de clientes. 

+++

+++**¿Qué ha pasado con mi antigua configuración de [!UICONTROL eVar]?**

Las [!UICONTROL eVars], [!UICONTROL props] y los [!UICONTROL eventos] en el sentido de Adobe Analytics ya no existen en [!UICONTROL Customer Journey Analytics]. Tiene un número ilimitado de elementos de esquema (dimensiones, métricas, campos de lista). De modo que todos los ajustes de atribución que se aplicaron durante el proceso de recopilación de datos se aplican ahora en tiempo de consulta.

+++

+++**¿Dónde están ahora todas las configuraciones de persistencia de la variable y sesiones?**

[!UICONTROL Customer Journey Analytics] aplica todas estas configuraciones en el momento del informe y estas se encuentran ahora en Vistas de datos. Los cambios en esta configuración ahora son retroactivos y puede tener varias versiones con varias Vistas de datos.

+++

+++**¿Qué les sucede a los segmentos o métricas calculadas existentes?**

[!UICONTROL Customer Journey Analytics] ya no utiliza eVars, props ni eventos y, en su lugar, utiliza cualquier esquema de Experience Platform. Esto significa que ninguno de los segmentos existentes ni las métricas de cálculo son compatibles con [!UICONTROL Customer Journey Analytics].

+++

+++**¿Cómo gestiona [!UICONTROL Customer Journey Analytics] las `Uniques Exceeded` limitaciones?**

[!UICONTROL Customer Journey Analytics] no tiene limitaciones de valor único, por lo que no es necesario preocuparse por ellas.

+++

+++**Si soy un cliente de [!DNL Data Workbench], ¿puedo pasar a [!UICONTROL Customer Journey Analytics] ahora mismo?**

Depende de su caso práctico; consúltelo con su equipo de cuentas de Adobe. Puede que su caso práctico actual ya sea adecuado para Customer Journey Analytics.

+++

## &#x200B;9. Cálculo del tamaño de la conexión {#estimate-size}

Consulte el [Uso de conexiones](/help/connections/manage-connections.md#usage).

## &#x200B;10. Con respecto a los excedentes de uso {#overage}

Adobe supervisa y aplica los límites de uso con regularidad. “Filas de datos” hace referencia a las filas medias diarias de datos disponibles para su análisis dentro de Customer Journey Analytics.

Por ejemplo, supongamos que tu contrato te da derecho a un millón de filas de datos. Supongamos que en el día 1 del uso de Customer Journey Analytics se cargan dos millones de filas de datos. El día 2, usted elimina 1 millón de filas y mantiene el uso en el máximo comprometido (es decir, un millón de filas de datos) durante el resto del Término de licencia. Según las condiciones contractuales, es posible que siga incurriendo en cargos por sobreutilización prorrateados para el día 1, ya que ha superado el derecho de licencia de “filas de datos”.

## &#x200B;11. Diagnóstico de discrepancias de datos {#discrepancies}

En algunos casos, es posible que observe que el número total de eventos que ha ingerido su conexión es diferente del número de filas del conjunto de datos en [!UICONTROL Adobe Experience Platform]. En este ejemplo, el conjunto de datos Impresión B2B tiene 7650 filas, pero el conjunto de datos contiene 3830 filas en [!UICONTROL Adobe Experience Platform]. Existen varias razones por las que pueden producirse discrepancias y se pueden realizar los siguientes pasos para el diagnóstico:

1. Desglose esta dimensión por **[!UICONTROL ID de conjunto de datos de Platform]** y verá dos conjuntos de datos del mismo tamaño, pero con diferentes **[!UICONTROL ID de conjunto de datos de Platform]**. Cada conjunto de datos tiene 3825 registros. Esto significa que [!UICONTROL Customer Journey Analytics] ha omitido cinco registros debido a la falta de ID de persona o la falta de marcas de hora:

   ![Desglose](assets/data-size2.png)

1. Además, si comprobamos [!UICONTROL Adobe Experience Platform], no hay ningún conjunto de datos con el ID “5f21c12b732044194bffc1d0”, por lo que alguien eliminó este conjunto de datos concreto de [!UICONTROL Adobe Experience Platform] cuando se creaba la conexión inicial. Más adelante se volvió a añadir a Customer Journey Analytics, pero se generó un [!UICONTROL ID de conjunto de datos de Platform] mediante [!UICONTROL Adobe Experience Platform].

Obtenga más información sobre las [implicaciones de la eliminación de conjuntos de datos y conexiones](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=es#implications-of-deleting-data-components) en [!UICONTROL Customer Journey Analytics] y [!UICONTROL Adobe Experience Platform].


## &#x200B;12. Recopilación de datos regionales

Adobe Experience Cloud utiliza la recopilación de datos regionales (RDC) para que las interacciones entre los visitantes y las soluciones de Adobe y ajenas a Adobe se produzcan lo más cerca posible de los visitantes. Una vez que los datos se recopilan a nivel regional en un centro de recopilación de datos (DCC, también conocido como sitio perimetral, parte de la red de Platform Edge), se reenvían a través de una conexión segura a las soluciones relevantes en función de su secuencia de datos y/o el reenvío de eventos.

![Flujo de datos mediante redes perimetrales](https://experienceleague.adobe.com/docs/experience-platform/assets/collection.png)

El proceso de recopilación de datos regionales sigue los siguientes pasos:

1. El DNS resuelve automáticamente la recopilación del nombre del host a la dirección IP del centro de recopilación de datos más cercano al visitante.
1. El visitante envía los datos a esa ubicación.
1. Los datos se reenvían inmediatamente a través de una conexión segura a las soluciones definidas por la configuración de la secuencia de datos o del reenvío de eventos.

El uso de la recopilación de datos regionales ofrece varias ventajas:

* **Rendimiento**: Con la recopilación de datos regionales, los visitantes se conectan al centro de recogida de datos más cercano. Esto proporciona el tiempo de respuesta más rápido, lo que da como resultado un seguimiento más preciso y tiempos de carga más rápidos.
* **Redundancia**: En caso de que se interrumpa la comunicación entre el centro de recogida de datos y el centro de procesamiento de datos, la infraestructura de recopilación de datos regionales de Adobe guarda los datos localmente y los reenvía al centro de procesamiento de datos cuando se restauran las comunicaciones.

Actualmente, la recopilación de datos regionales incluye las siguientes ubicaciones (sujetas a cambios):


| Tipo de RDC | Centros de recopilación de datos |
| --- | --- |
| Global (predeterminado) | Oregón, Virginia, Irlanda, París, Mumbai, Singapur, Tokio, Sydney |
| Solo para América del Norte y América del Sur | Oregón, Virginia |
| Solo Europa | Irlanda, París |
| Solo Asia-Pacífico | Mumbai, Singapur, Tokio, Sydney |

{style="table-layout:auto"}

Cuando los datos llegan al centro de datos regional, la configuración de la secuencia de datos determina cómo se dirigen los datos más lejos.

Customer Journey Analytics requiere conjuntos de datos de Adobe Experience Platform, por lo que su configuración de secuencia de datos/reenvío de eventos requiere que el servicio de Adobe Experience Platform enrute los datos desde el centro de datos regional al centro de datos donde se encuentra su instancia de Adobe Experience Platform. Customer Journey Analytics y sus servicios e infraestructura de soporte se implementan en la misma instancia de Adobe Experience Platform.


Consulte [Información general de recopilación de datos](https://experienceleague.adobe.com/docs/experience-platform/collection/home.html?lang=es) para obtener más información sobre el proceso de recopilación de datos fuera de Adobe Experience Platform Edge Network y sus centros de datos regionales.
