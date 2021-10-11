---
title: Preguntas frecuentes de Customer Journey Analytics
description: 'Customer Journey Analytics: Preguntas frecuentes.'
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
source-git-commit: 2412b2b3d6c0abf29c2d265ba60668c3e4a12936
workflow-type: tm+mt
source-wordcount: '1611'
ht-degree: 83%

---

# Preguntas frecuentes

[!UICONTROL Customer Journey Analytics] (CJA) es nuestro producto de análisis de nueva generación. A continuación, encontrará respuestas a las preguntas más frecuentes acerca de CJA. Para obtener más información, consulte [Compatibilidad con funciones de Customer Journey Analytics](/help/getting-started/cja-aa.md).

## 1. Requisitos previos

| Pregunta | Respuesta |
| --- | --- |
| ¿Necesito [!UICONTROL Private Device Graph] o [!UICONTROL Device Coop] para [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Private Device Graph] y [!UICONTROL Device Coop] no son necesarios para [!UICONTROL Customer Journey Analytics]. De hecho, todavía no son compatibles. |
| ¿Necesito un [!UICONTROL Experience Cloud ID] (ECID) para [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Customer Journey Analytics] admite cualquier ID de un conjunto de datos, ya sea [!UICONTROL ECID] o cualquier otro ID de su elección. |
| ¿Qué sucede si necesito extraer, transformar o cargar datos antes de utilizar [!UICONTROL Customer Journey Analytics]? | Customer Journey Analytics incluye capacidades de [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html?lang=es) para ayudar a transformar los datos antes de colocarlos en el lago de datos de Adobe Experience Platform. Si necesita extraer, transformar o cargar los datos después de haberlos introducido, [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=es#queries) proporciona algunas opciones limitadas, aunque puede haber costes adicionales implicados. |

{style=&quot;table-layout:auto&quot;}

## 2. Unión de datos (análisis entre canales múltiples)

| Pregunta | Respuesta |
| --- | --- |
| ¿Puede [!UICONTROL Customer Journey Analytics] “unir” varios dispositivos o conjuntos de datos? | Sí. [!UICONTROL Customer Journey Analytics] tiene una solución de vinculación llamada [Análisis entre canales múltiples](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=es) (CCA). Permite volver a escribir el ID de la persona de un conjunto de datos, lo que ofrece una combinación perfecta de varios conjuntos de datos. |
| ¿Se admite la unión del comportamiento anónimo al comportamiento autenticado? | Sí. [Análisis entre canales múltiples](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html) busca los datos de usuario de las sesiones autenticadas y no autenticadas para generar un ID vinculado. |
| ¿Cómo funciona la &quot;repetición&quot; en CCA? | CCA &quot;reproduce&quot; los datos en función de los identificadores únicos que ha aprendido. Reproducir hace que los nuevos dispositivos de la conexión se vinculen. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/replay.html?lang=es#paso-1%3A-vinculaci%C3%B3n-en-tiempo-real) |
| ¿Cómo funciona la vinculación de datos históricos (relleno) en CCA? | Cuando se active por primera vez, Adobe proporcionará un relleno de datos vinculados que se remontarán hasta el comienzo del mes anterior (hasta 60 días). Para poder rellenar este campo, los datos no vinculados en aquel momento deben tener un tipo de ID efímero. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=es#habilitaci%C3%B3n-de-an%C3%A1lisis-entre-canales) |

{style=&quot;table-layout:auto&quot;}

## 3. Introducción de datos en [!UICONTROL Customer Journey Analytics]

| Pregunta | Respuesta |
| --- | --- |
| ¿Puedo combinar datos de diferentes simuladores de pruebas de [!UICONTROL Adobe Experience Platform] en una conexión de [!UICONTROL Customer Journey Analytics]? | No. No puede acceder a los datos de entornos limitados. Solo se pueden combinar conjuntos de datos ubicados en el mismo entorno limitado. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=es#select-sandbox-and-datasets) |
| ¿Cómo puede conectar datos en línea con datos sin conexión en [!UICONTROL Customer Journey Analytics]? | Siempre que el ID de usuario coincida entre conjuntos de datos, [!UICONTROL Customer Journey Analytics] puede conectar filtros, atribuciones, flujos, visitas en orden previsto, etc. entre conjuntos de datos. |
| ¿Cómo puedo llevar mis datos sin conexión a [!UICONTROL Customer Journey Analytics]? | Su asignación de derechos en Customer Journey Analytics le permite introducir datos en Experience Platform. A continuación, puede crear conexiones a esos datos y vistas de datos en [!UICONTROL Customer Journey Analytics] para crear informes en Analysis Workspace. El equipo de incorporación de datos de Experience Platform puede ofrecer recomendaciones o asesoría a los clientes si lo necesitan. |
| ¿Cómo puedo obtener datos de [!UICONTROL Adobe Analytics] en [!UICONTROL Customer Journey Analytics]? | Los datos de [!UICONTROL Adobe Analytics] se pueden conectar a Experience Platform mediante el [conector de origen de Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=es). La mayoría de los campos de [!UICONTROL Adobe Analytics] se transfieren en formato XDM, pero otros campos todavía no están disponibles. |
| ¿Cuánto tiempo se tarda en ensamblar elementos de conjuntos de datos a una vista de datos? | Tarda unas pocas horas en empezar y unos días en rellenar los últimos 13 meses de datos. |
| ¿Es necesario introducir datos PII para establecer conexiones entre ellos? | No, puede utilizar cualquier ID, incluido un hash de un ID de cliente, que no es PII. |

{style=&quot;table-layout:auto&quot;}

## 4. Consideraciones de latencia

>[!NOTE]
>No hay un tamaño de datos fijo en CJA y, por lo tanto, el Adobe no puede comprometerse con un tiempo de ingesta estándar. Estamos trabajando activamente para reducir estas latencias a través de nuevas actualizaciones y optimización de la ingesta.

| Pregunta | Respuesta |
| --- | --- |
| ¿Cuál es la latencia esperada para [!UICONTROL Customer Journey Analytics] en [!UICONTROL Adobe Experience Platform]? | <ul><li>Eventos o datos activos: Procesado e ingestado en un plazo de 90 minutos, una vez que los datos estén disponibles en AEP.</li><li>Tamaño del lote > 50 millones de filas: más de 90 minutos.</li><li>Rellenos secundarios pequeños : por ejemplo, un conjunto de datos de consulta de 10 millones de filas: en un plazo de 24 horas<li>Rellenos de fondo grandes: por ejemplo, 500 000 millones de filas: 30 días</li></ul> |


## 5. Componentes tradicionales de [!UICONTROL Adobe Analytics]

| Pregunta | Respuesta |
| --- | --- |
| ¿Puedo compartir/publicar filtros (segmentos) de Customer Journey Analytics en el perfil unificado de Experience Platform o en otras aplicaciones de Experience Cloud? | Aún no, pero estamos trabajando activamente para ofrecer esta capacidad. |
| ¿Qué ha pasado con mi antigua configuración de eVar? | Los eVars, las propiedades y los eventos en el sentido tradicional de Adobe Analytics ya no existen en [!UICONTROL Customer Journey Analytics]. Tiene un número ilimitado de elementos de esquema (dimensiones, métricas, campos de lista). De modo que todos los ajustes de atribución que se aplicaron durante el proceso de recopilación de datos se aplican ahora en tiempo de consulta. |
| ¿Dónde están ahora todas las configuraciones de persistencia de la variable y sesiones? | [!UICONTROL Customer Journey Analytics] aplica todas estas configuraciones en el momento del informe y estas se encuentran ahora en Vistas de datos. Los cambios en esta configuración ahora son retroactivos y puede tener varias versiones con varias Vistas de datos. |
| ¿Qué les sucede a nuestros segmentos o métricas calculadas existentes? | [!UICONTROL Customer Journey Analytics] ya no utiliza eVars, props ni eventos y, en su lugar, utiliza cualquier esquema de AEP. Esto significa que ninguno de los segmentos existentes ni las métricas de cálculo son compatibles con [!UICONTROL Customer Journey Analytics]. |
| ¿Cómo gestiona [!UICONTROL Customer Journey Analytics] las `Uniques Exceeded` limitaciones? | [!UICONTROL Customer Journey Analytics] no tiene limitaciones de valor único, por lo que no es necesario preocuparse por ellas. |
| Si soy un cliente de [!DNL Data Workbench], ¿puedo pasar a [!UICONTROL Customer Journey Analytics] ahora mismo? | Depende de su caso práctico; consúltelo con su equipo de cuenta de Adobe. Puede que sus casos prácticos actuales ya sean adecuados para Customer Journey Analytics. |

{style=&quot;table-layout:auto&quot;}

## 6. Implicaciones de la eliminación de componentes de datos

En cuanto a la eliminación de datos, nos interesan 6 tipos de componentes: simulación de pruebas, esquema, conjunto de datos, conexión, vista de datos y proyectos de Workspace. Estos son algunos de los escenarios posibles en los que puede ser necesario eliminar cualquiera de estos componentes:

| Si usted... | Esto sucede... |
| --- | --- |
| Eliminar un simulador de pruebas en [!UICONTROL Adobe Experience Platform] | Al eliminar un simulador de pruebas, se detendrá el flujo de datos a cualquier conexión de [!UICONTROL Customer Journey Analytics] a conjuntos de datos de dicho simulador de pruebas. Actualmente, las conexiones en CJA vinculadas a dicho simulador de pruebas no se eliminarán automáticamente. |
| Eliminar un esquema en [!UICONTROL Adobe Experience Platform], pero no los conjuntos de datos asociados a dicho esquema | [!UICONTROL Adobe Experience Platform] no permite la eliminación de esquemas que tienen uno o varios conjuntos de datos asociados. Sin embargo, un administrador que tenga el conjunto de derechos adecuado podrá eliminar primero los conjuntos de datos y, a continuación, el esquema. |
| Eliminar un conjunto de datos en el lago de datos de [!UICONTROL Adobe Experience Platform] | La eliminación de un conjunto de datos en el lago de datos de AEP detendrá el flujo de datos de ese conjunto de datos a cualquier conexión de CJA que incluya ese conjunto de datos. Los datos de ese conjunto de datos no se eliminan automáticamente de las conexiones con CJA asociadas. |
| Eliminar un conjunto de datos en [!UICONTROL Customer Journey Analytics] | Actualmente, no se puede eliminar un conjunto de datos de una conexión que se haya guardado. Tendría que eliminar toda la conexión y comenzar de nuevo. (Sin embargo, los clientes que hayan adquirido la SKU de CJA pueden eliminar un conjunto de datos en la interfaz de usuario de [!UICONTROL Adobe Experience Platform]). |
| Eliminar un lote de un conjunto de datos (en [!UICONTROL Adobe Experience Platform]) | Si se elimina un lote de un conjunto de datos de [!UICONTROL Adobe Experience Platform], se eliminará el mismo lote de cualquier conexión de CJA que contenga dicho lote específico. CJA recibirá una notificación de las eliminaciones de lotes que se produzcan en [!UICONTROL Adobe Experience Platform]. |
| Eliminar un lote **mientras se está introduciendo** en [!UICONTROL Customer Journey Analytics] | Si solo hay un lote en el conjunto de datos, no aparecerán datos ni datos parciales de dicho lote en [!UICONTROL Customer Journey Analytics]. La introducción se revertirá. Si, por ejemplo, hay 5 lotes en el conjunto de datos y 3 de ellos ya se han introducido cuando se elimine el conjunto de datos, los datos de esos 3 lotes aparecerán en [!UICONTROL Customer Journey Analytics]. |
| Eliminar una conexión en [!UICONTROL Customer Journey Analytics] | Aparecerá un mensaje de error para indicar lo siguiente:<ul><li>Las vistas de datos creadas para la conexión eliminada ya no funcionarán.</li><li> Del mismo modo, los proyectos de Workspace que dependan de vistas de datos en la conexión eliminada dejarán de funcionar.</li></ul> |
| Eliminar una vista de datos en [!UICONTROL Customer Journey Analytics] | Un mensaje de error indicará que dejarán de funcionar todos los proyectos de Workspace que dependan de esta vista de datos eliminada. |

## 7. Consideraciones al combinar grupos de informes en CJA

Si planea introducir datos de Adobe Analytics a través del [Conector de origen de Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=es), tenga en cuenta estas ramificaciones al combinar dos o más grupos de informes de Adobe Analytics.

| Problema | Consideración |
| --- | --- |
| Variables | Es posible que las variables como [!UICONTROL eVars] no se alineen entre grupos de informes. Por ejemplo, eVar1 en el grupo de informes 1 puede apuntar a **[!UICONTROL Página]**. En el grupo de informes 2, eVar1 puede señalar a **[!UICONTROL Campaña interna]**, lo que produce informes mixtos e inexactos. |
|  Sesiones y   recuentos de personas | Se deduplican en los grupos de informes. Como resultado, es posible que los recuentos no coincidan. |
| Anulación de duplicación métrica | Anula la duplicación de instancias de una métrica (por ejemplo, [!UICONTROL Pedidos]) si varias filas tienen el mismo ID de transacción (por ejemplo, [!UICONTROL ID de compra]). Esto evita el recuento excesivo de las métricas clave. Como resultado, es posible que las métricas como [!UICONTROL Pedidos] no se sumen en los grupos de informes. |
| Moneda | La conversión de moneda aún no es compatible con CJA. Si los grupos de informes que intenta combinar utilizan distintas monedas base, pueden surgir problemas. |
| [!UICONTROL Persistencia] | [](../data-views/component-settings/persistence.md) La persistencia se extiende a los grupos de informes, lo que afecta a los  [!UICONTROL filtros], la  [!UICONTROL atribución], etc. Los números pueden no sumarse correctamente. |
| [!UICONTROL Clasificaciones] |  Las clasificaciones no se deduplican automáticamente al combinar grupos de informes. Al combinar varios archivos de clasificaciones en un único conjunto de datos [!UICONTROL lookup], puede encontrar problemas. |