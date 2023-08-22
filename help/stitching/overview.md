---
title: Información general de vinculación
description: Información general sobre la vinculación.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
source-git-commit: 52d47e777e8c9f7e1e73f4131f19d7df280cb2a3
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 24%

---

# Información general de vinculación

La vinculación de identidad (o simplemente, la vinculación) es una práctica funcionalidad que aumenta la idoneidad de un conjunto de datos de evento para el análisis en canales múltiples. El análisis entre canales es un caso de uso principal que Customer Journey Analytics puede gestionar, lo que le permite combinar y ejecutar informes de varios conjuntos de datos de diferentes canales sin problemas, en función de un identificador común (ID de persona).

Cuando combina conjuntos de datos con ID de personas similares, la atribución se transfiere a través de dispositivos y canales. Por ejemplo: un usuario visita su sitio por primera vez a través de un anuncio en su equipo de escritorio. Ese usuario encuentra un problema con su pedido y, a continuación, llama a su equipo de servicio de atención al cliente para que le ayude a resolverlo. Con el análisis en canales múltiples, puede atribuir eventos del centro de llamadas a la publicidad en la que se hizo clic originalmente.

Lamentablemente, no todos los conjuntos de datos basados en eventos que forman parte de la conexión en Customer Journey Analytics están suficientemente rellenados con datos para admitir esta atribución de forma predeterminada. En especial, los conjuntos de datos de experiencias basados en la web o en dispositivos móviles a menudo no tienen una información de ID de persona real disponible en todos los eventos.

La configuración permite volver a incrustar identidades en las filas de un conjunto de datos, asegurándose de que el ID de persona (ID vinculado) esté disponible en cada evento. La vinculación busca los datos de usuario de las sesiones autenticadas y no autenticadas para determinar el valor de ID transitorio común que se puede utilizar como ID vinculado. Esta regeneración de claves permite resolver registros dispares en un único ID vinculado para su análisis en el nivel de la persona, en lugar de en el nivel de dispositivo o cookie.

Se beneficia del análisis en canales múltiples si combina uno o más de los conjuntos de datos enlazados con otros conjuntos de datos, como los datos del centro de llamadas, como parte de la definición de la conexión de Customer Journey Analytics. Esto supone que esos otros conjuntos de datos ya contienen un ID de persona en cada fila, similar al ID vinculado.


## Requisitos previos

{{select-package}}

>[!IMPORTANT]
>
>Si no se cumplen todos los requisitos previos, es posible que no se pueda realizar correctamente el análisis entre canales.

Antes de usar la vinculación, asegúrese de que su organización está preparada con lo siguiente:

* Importe los datos deseados en Adobe Experience Platform:

   * Para ver los datos de Adobe Analytics, consulte [Uso de los datos de grupos de informes de Adobe Analytics en Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   * Para ver otros tipos de datos, consulte [Crear un esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=es) y [Ingesta de datos](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=es) en la documentación de Adobe Experience Platform.

* El conjunto de datos de evento de Adobe Experience Platform al que desee aplicar la vinculación debe tener dos columnas que ayuden a identificar a los visitantes:

   * Un **ID persistente**, un identificador presente en cada fila. Por ejemplo, un ID de visitante generado por una biblioteca de AppMeasurement de Adobe Analytics o un ECID generado por el servicio de identidad de Adobe Experience Cloud.
   * Un **ID transitorio**, un identificador presente solo en algunas filas. Por ejemplo, un nombre de usuario o una dirección de correo electrónico con hash una vez que un visitante se autentica. Puede utilizar prácticamente cualquier identificador que desee. La configuración tendrá en cuenta este campo para contener la información de ID de persona real. Para obtener los mejores resultados de vinculación, se debe enviar un ID transitorio dentro de los eventos del conjunto de datos al menos una vez para cada ID persistente.
Si planea incluir este conjunto de datos dentro de una conexión de Customer Journey Analytics, es preferible que los demás conjuntos de datos también tengan un identificador común similar.

* La vinculación incluye la combinación de datos de usuario autenticados y no autenticados. Asegúrese de cumplir las leyes y regulaciones aplicables, incluida la obtención de los permisos necesarios para el usuario final, antes de activar la vinculación en un conjunto de datos de evento.


## Usar vinculación

Una vez que su organización cumpla todos los requisitos previos y comprenda los [limitaciones](#limitations)Sin embargo, puede seguir estos pasos para empezar a utilizar la vinculación en Customer Journey Analytics:

### Solicitar asistencia

1. Póngase en contacto con Asistencia al cliente de Adobe con la siguiente información:

   * Una solicitud para habilitar la vinculación.
   * El ID del conjunto de datos del conjunto de datos para el cual desea volver a generar la clave.
   * El nombre de columna del ID persistente del conjunto de datos deseado (identificador que aparece en cada fila).
   * El nombre de columna del ID transitorio del conjunto de datos deseado (el identificador de persona, que también actúa como vínculo entre conjuntos de datos en el contexto de una conexión).
   * Su preferencia de frecuencia de [repetición](explained.md) y longitud de retrospectiva. Las opciones incluyen una reproducción una vez a la semana con una ventana retrospectiva de 7 días o una reproducción cada día con una ventana retrospectiva de 1 día.
   * Nombre de la zona protegida.


2. La Asistencia al cliente de Adobe trabaja con el personal de ingeniería de Adobes para habilitar la vinculación al recibir la solicitud. Una vez habilitado, aparecerá en Adobe Experience Platform un nuevo conjunto de datos con clave con una nueva columna de ID con título. La Asistencia al cliente de Adobe puede proporcionar el ID del nuevo conjunto de datos.

3. Cuando se activa por primera vez, el Adobe proporciona un relleno de datos vinculados que se remontan 60 días.

4. Si desea utilizar el nuevo conjunto de datos vinculado en un análisis en canales múltiples, debe agregarlo a un [conexión](../connections/overview.md) en el Customer Journey Analytics junto con cualquier otro conjunto de datos necesario. Elija el ID personal correcto para cada conjunto de datos.

5. [Cree una vista de datos](/help/data-views/create-dataview.md) en función de la conexión.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Una vez configurada la vista de datos, puede ejecutar el análisis de creación de informes de Customer Journey Analytics en varios canales y dispositivos.

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->


## Limitaciones

>[!IMPORTANT]
>
>* Aplique cualquier cambio que realice en el esquema del conjunto de datos de evento global también al nuevo esquema del conjunto de datos vinculado; de lo contrario, este se romperá.
>
>* Si elimina el conjunto de datos de origen, el conjunto de datos enlazado detiene el procesamiento y el sistema lo elimina.
>
>* Las etiquetas de uso de datos no se propagan automáticamente al esquema del conjunto de datos vinculado. Si tiene etiquetas de uso de datos aplicadas al esquema del conjunto de datos de origen, debe aplicar manualmente estas etiquetas de uso de datos al esquema del conjunto de datos vinculado. Consulte [Administración de etiquetas de uso de datos en Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html?lang=es) para obtener más información.

La vinculación es una característica innovadora y sólida, pero tiene limitaciones en cuanto a su uso.

* Las capacidades actuales de regeneración de claves están limitadas a un paso (ID persistente a ID transitorio). No se admite la regeneración de claves de varios pasos (por ejemplo, ID persistente a ID transitorio y, a continuación, a otro ID transitorio).
* Solo se admiten conjuntos de datos de evento. No se admiten otros conjuntos de datos, como conjuntos de datos de búsqueda.
* No se admiten los mapas de ID personalizados utilizados en su organización.
* La vinculación no transforma el campo que se utiliza para la vinculación de ninguna manera. La vinculación utiliza el valor del campo especificado tal como existe en el conjunto de datos no vinculado dentro del lago de datos. El proceso de vinculación distingue entre mayúsculas y minúsculas. Por ejemplo, si aparece unas veces la palabra &quot;Bob&quot; en el campo y otras la palabra &quot;BOB&quot;, estos identificadores se tratan como dos personas independientes.
* La vinculación distingue entre mayúsculas y minúsculas. Para los conjuntos de datos generados mediante el conector de origen de Analytics, el Adobe recomienda revisar cualquier regla VISTA o de procesamiento que se aplique al campo de ID transitorio. Esta revisión garantiza que ninguna de estas reglas introduzca nuevos formularios del mismo ID. Por ejemplo, debe asegurarse de que ninguna regla VISTA o de procesamiento introduce minúsculas en el campo ID transitorio en solo en una parte de los eventos.
* La configuración no combina ni concatena campos.
* El campo de ID transitorio debe contener un solo tipo de ID ( ID de un solo área de nombres). Por ejemplo, el campo de ID transitorio no debe contener una combinación de ID de inicio de sesión e ID de correo electrónico.
* Si se producen varios eventos con la misma marca de tiempo para el mismo ID persistente, pero con valores diferentes en el campo de ID transitorio, la identificación se selecciona en función del orden alfabético. Por lo tanto, si el ID persistente A tiene dos eventos con la misma marca de tiempo y uno de los eventos especifica Bob y el otro Ann, al vincular se selecciona Ann.
* Si varias personas comparten un dispositivo y el número total de transiciones entre usuarios supera las 50 000, el Customer Journey Analytics deja de vincular datos para ese dispositivo.
* Tenga cuidado con los escenarios en los que los ID transitorios contienen valores de marcador de posición, por ejemplo, &quot;Sin definir&quot;. Consulte [FAQ](faq.md) para obtener más información.

No confunda la vinculación con:

* La combinación de dos o más conjuntos de datos. La vinculación solo se aplica a un conjunto de datos. La combinación de conjuntos de datos se produce como resultado de la configuración de una conexión de Customer Journey Analytics y la selección del mismo ID de persona en los conjuntos de datos seleccionados en la conexión.

* La unión de dos conjuntos de datos. En Customer Journey Analytics, una unión se utiliza a menudo para búsquedas o clasificaciones en Analysis Workspace. Aunque la vinculación utiliza la funcionalidad de unión, el proceso en sí mismo implica más que uniones.




