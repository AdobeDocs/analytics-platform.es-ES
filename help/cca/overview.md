---
title: Información general sobre Análisis en canales múltiples
description: Vuelva a escribir los ID de persona de varios conjuntos de datos para vincular los visitantes.
exl-id: 69763313-de27-4487-8e32-8277f1f693d8
solution: Customer Journey Analytics
hide: true
hidefromtoc: true
source-git-commit: 98c0f2887789310dc387f1bf7ce5298722a0797e
workflow-type: ht
source-wordcount: '1166'
ht-degree: 100%

---


# Información general sobre Análisis en canales múltiples

**Journey IQ: Análisis en canales múltiples** es una función que le permite volver a escribir la ID personal de un conjunto de datos, lo cual ofrece una combinación perfecta de múltiples conjuntos de datos. CCA busca los datos de usuario de las sesiones autenticadas y no autenticadas para generar un ID vinculado. Con Análisis en canales múltiples, puede dar respuesta a preguntas como:

* ¿Cuántas personas comienzan su experiencia en un canal y luego la terminan en otro?
* ¿Cuántas personas interactúan con mi marca? ¿Cuántos y qué tipos de dispositivos utilizan? ¿Cómo se superponen?
* ¿Con qué frecuencia comienzan una tarea en un dispositivo móvil y luego se trasladan a un ordenador de escritorio para completarla? ¿Los clics de campaña que llegan a un dispositivo llevan a la conversión en otro dispositivo diferente?
* ¿Cómo cambia mi comprensión de la eficacia de la campaña si tengo en cuenta los recorridos entre dispositivos? ¿Cómo cambia mi análisis de embudo?
* ¿Cuáles son las rutas más comunes que los usuarios realizan de un dispositivo a otro? ¿En qué punto abandonan? ¿Dónde tienen éxito?
* ¿En qué se diferencia el comportamiento de los usuarios con varios dispositivos de los usuarios con un único dispositivo?

Cuando combina conjuntos de datos con ID de personas similares, la atribución se transfiere a través de dispositivos y canales. Por ejemplo: un usuario visita su sitio por primera vez a través de un anuncio en su equipo de escritorio. Ese usuario encuentra un problema con su pedido y, a continuación, llama a su equipo de servicio de atención al cliente para que le ayude a resolverlo. Con Análisis en canales múltiples, puede atribuir eventos del centro de llamadas a la publicidad en la que se hizo clic originalmente.

## Requisitos previos

>[!IMPORTANT]
>
>Si no se cumplen todos los requisitos previos, es posible que no se pueda crear una conexión de CCA o que se obtengan resultados deficientes al combinar conjuntos de datos.

Antes de usar Análisis en canales múltiples, asegúrese de que su organización está preparada con lo siguiente:

* Un conjunto de datos en Adobe Experience Platform debe tener dos columnas que ayuden a identificar a los visitantes:
   * Un **ID persistente**, un identificador presente en cada fila. Por ejemplo, un ID de persona generado por una biblioteca de AppMeasurement de Adobe Analytics.
   * Un **ID transitorio**, un identificador presente solo en algunas filas. Por ejemplo, un nombre de usuario o una dirección de correo electrónico con hash una vez que un visitante se autentica. Puede utilizar prácticamente cualquier identificador que desee, siempre y cuando esté presente al menos una vez en el mismo evento que un ID persistente determinado.
* Otro conjunto de datos, como los datos del centro de llamadas, que contiene un ID transitorio en cada fila. Este ID personal debe tener el mismo formato que el ID transitorio del otro conjunto de datos.
* Esta función le permite vincular conjuntos de datos que pueden incluir la combinación de datos de usuario autenticados y no autenticados. Asegúrese de cumplir las leyes y regulaciones aplicables, incluida la obtención de los permisos necesarios para el usuario final, antes de combinar conjuntos de datos.

## Limitaciones

>[!IMPORTANT]
>
>Cualquier cambio en el esquema del conjunto de datos de evento global debe aplicarse también en el nuevo esquema del conjunto de datos vinculado; de lo contrario, este se romperá.
>
>Además, si elimina el conjunto de datos de origen, el conjunto de datos enlazado detiene el procesamiento y el sistema lo elimina.

Análisis en canales múltiples es una función innovadora y sólida, pero tiene limitaciones en cuanto a su uso.

* Las capacidades actuales de regeneración de claves están limitadas a un paso (ID persistente a ID transitorio). No se admite la regeneración de claves de varios pasos (por ejemplo, ID persistente a ID transitorio y, a continuación, a otro ID transitorio).
* Solo se admiten conjuntos de datos de evento. No se admiten otros conjuntos de datos, como conjuntos de datos de búsqueda.
* No se admiten los mapas de ID personalizados utilizados en su organización.
* No se admite el gráfico privado entre dispositivos.
* Análisis en canales múltiples no transforma el campo que se utiliza para la identificación de ninguna manera. La identificación basada en campos utiliza el valor del campo especificado tal como existe en el conjunto de datos no identificado del lago de datos. El proceso de identificación distingue entre mayúsculas y minúsculas. Por ejemplo, si aparece unas veces la palabra “Bob” en el campo y otras la palabra “BOB”, estas se tratarán como dos personas independientes.
* Como la vinculación basada en campos distingue entre mayúsculas y minúsculas, en el caso de los conjuntos de datos de Analytics generados mediante el conector de origen de Analytics, Adobe recomienda revisar cualquier regla VISTA o de procesamiento que se aplique al campo de ID transitorio para garantizar que ninguna de estas reglas introduzca formularios nuevos con el mismo ID. Por ejemplo, debe asegurarse de que ninguna regla VISTA o de procesamiento introduce minúsculas en el campo ID transitorio en solo en una parte de los eventos.
* La identificación basada en campos no combina ni concatena campos.
* El campo de ID transitorio debe contener un solo tipo de ID (es decir, ID de un solo espacio de nombres). Por ejemplo, el campo de ID transitorio no debe contener una combinación de ID de inicio de sesión e ID de correo electrónico.
* Si se producen varios eventos con la misma marca de tiempo en relación con el mismo ID persistente, pero con valores diferentes en el campo de ID transitorio, la identificación basada en campos decidirá en función del orden alfabético. Por lo tanto, si el ID persistente A tiene dos eventos con la misma marca de tiempo y uno de los eventos especifica Bob y el otro Ann, la identificación basada en campos elegirá Ann.
* Si varias personas comparten un dispositivo y el número total de transiciones entre usuarios supera las 50 000, CCA deja de vincular datos para ese dispositivo.

## Habilitación de Análisis en canales múltiples

Una vez que su organización cumpla todos los requisitos previos y comprenda sus limitaciones, puede seguir estos pasos para comenzar a usarlo en Customer Journey Analytics.

1. Importe los datos deseados en Adobe Experience Platform. Para obtener datos de Adobe Analytics, consulte [Uso de los datos de grupos de informes de Adobe Analytics en Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md). Para ver otros tipos de datos, consulte [Crear un esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=es) y [Ingesta de datos](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=es) en la documentación de Adobe Experience Platform.
1. Póngase en contacto con Asistencia al cliente de Adobe con la siguiente información:
   * Una solicitud para habilitar Análisis en canales múltiples
   * El ID del conjunto de datos del conjunto de datos para el cual desea volver a generar la clave
   * El nombre de columna del ID persistente del conjunto de datos deseado (identificador que aparece en cada fila)
   * El nombre de la columna del ID transitorio del conjunto de datos deseado (vínculo del identificador personal entre conjuntos de datos)
   * Su preferencia de frecuencia de [repetición](replay.md) y longitud de retrospectiva. Las opciones incluyen una reproducción una vez a la semana con una ventana retrospectiva de 7 días o una reproducción cada día con una ventana retrospectiva de 1 día
   * Nombre de la zona protegida.
1. La Asistencia al cliente de Adobe trabajará con el personal de ingeniería de Adobe para habilitar Análisis en canales múltiples cuando reciba la solicitud. Una vez habilitado, aparecerá en Adobe Experience Platform un nuevo conjunto de datos con clave con una nueva columna de ID de persona. La Asistencia al cliente de Adobe puede proporcionar el nuevo ID del conjunto de datos y el nombre de la columna de ID personal.
1. Cuando se active por primera vez, Adobe proporcionará un relleno de datos identificados que se remontarán hasta el comienzo del mes anterior (hasta 60 días). Para poder rellenar este campo, el ID efímero debe existir en los datos no identificados en ese momento.
1. [Cree una conexión](/help/connections/create-connection.md) en Customer Journey Analytics usando el nuevo conjunto de datos recientemente generado y otros conjuntos de datos que desea incluir. Elija el ID personal correcto para cada conjunto de datos.
1. [Cree una vista de datos](/help/data-views/create-dataview.md) en función de la conexión.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Una vez configurada la vista de datos, el análisis en Customer Journey Analytics es igual que cualquier otro análisis en Customer Journey Analytics, excepto que ahora los datos se gestionan a través de varios canales y dispositivos.
