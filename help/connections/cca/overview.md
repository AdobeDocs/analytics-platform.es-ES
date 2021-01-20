---
title: Información general de Análisis de Canales cruzados
description: Vuelva a escribir los ID de visitante de varios conjuntos de datos para unir visitantes.
translation-type: tm+mt
source-git-commit: dca995fc271b02a26568ed8d4a672b96f10b0a18
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 19%

---


# Información general de Análisis de Canales cruzados

**IQ de recorrido: El** análisis entre Canales es una función que le permite volver a escribir la ID de persona de un conjunto de datos, lo que permite una combinación sin fisuras de varios conjuntos de datos. CCA busca los datos de usuario de las sesiones autenticadas y no autenticadas para generar un ID vinculado. Con Análisis de Canales cruzados, puede responder preguntas como:

* ¿Cuántas personas comienzan su experiencia en un canal y luego la terminan en otro?
* ¿Cuántas personas interactúan con mi marca? ¿Cuántos y qué tipos de dispositivos utilizan? ¿Cómo se superponen?
* ¿Con qué frecuencia comienzan una tarea en un dispositivo móvil y luego se trasladan a un ordenador de escritorio para completarla? ¿Los clics de campaña que llegan a un dispositivo llevan a la conversión en otro dispositivo diferente?
* ¿Cómo cambia mi comprensión de la eficacia de la campaña si tengo en cuenta los recorridos entre dispositivos? ¿Cómo cambia mi análisis de embudo?
* ¿Cuáles son las rutas más comunes que los usuarios realizan de un dispositivo a otro? ¿En qué punto abandonan? ¿Dónde tienen éxito?
* ¿En qué se diferencia el comportamiento de los usuarios con varios dispositivos de los usuarios con un único dispositivo?

Cuando combina conjuntos de datos con ID de personas similares, la atribución se transfiere a través de dispositivos y canales. Por ejemplo: un usuario visita su sitio por primera vez a través de un anuncio en su equipo de escritorio. Ese usuario encuentra un problema con su pedido y, a continuación, llama a su equipo de servicio al cliente para ayudarle a resolverlo. Con Análisis de Canales cruzados, puede atribuir eventos del centro de llamadas a la publicidad en la que hicieron clic originalmente.

## Requisitos previos

>[!IMPORTANT]
>
>Si no se cumplen todos los requisitos previos, es posible que no se pueda crear una conexión CCA o que se obtengan resultados deficientes al combinar conjuntos de datos.

Antes de usar Análisis de Canal cruzado, asegúrese de que su organización está preparada con lo siguiente:

* Un conjunto de datos en Adobe Experience Platform debe tener dos columnas que ayuden a identificar visitantes:
   * Un **ID persistente**, identificador presente en cada fila. Por ejemplo, un ID de visitante generado por una biblioteca de Adobe Analytics AppMeasurement.
   * Un **ID transitorio**, identificador presente sólo en algunas filas. Por ejemplo, un nombre de usuario o una dirección de correo electrónico con hash una vez que un visitante se autentica. Puede utilizar prácticamente cualquier identificador que desee, siempre y cuando esté presente al menos una vez en el mismo evento que un ID persistente determinado.
* Otro conjunto de datos, como los datos del centro de llamadas, que contiene una ID transitoria en cada fila. Este ID de persona debe tener el mismo formato que el ID transitorio del otro conjunto de datos.
* Esta función le permite unir conjuntos de datos que pueden incluir la combinación de datos de usuario autenticados y no autenticados. Asegúrese de cumplir con las leyes y regulaciones aplicables, incluida la obtención de los permisos necesarios para el usuario final, antes de combinar conjuntos de datos.

## Limitaciones

El análisis de Canal cruzado es una característica innovadora y sólida, pero tiene limitaciones en cuanto a cómo se puede usar.

* Las capacidades actuales de rekeying están limitadas a un paso (ID persistente a ID transitorio). No se admite la reclaves de varios pasos (por ejemplo, el ID persistente a un ID transitorio y, a continuación, a otro ID transitorio).
* Solo se admiten conjuntos de datos de evento. No se admiten otros conjuntos de datos, como conjuntos de datos de búsqueda.
* No se admiten los mapas de ID personalizados utilizados en su organización.
* No se admiten el gráfico de cooperación entre Adobes ni el gráfico privado.

## Habilitar análisis de Canal cruzado

Una vez que su organización cumpla todos los requisitos previos y comprenda sus limitaciones, puede seguir estos pasos para inicio de su uso en CJA.

1. Importe los datos deseados en Adobe Experience Platform. Consulte [Creación de un esquema](https://docs.adobe.com/content/help/es-ES/experience-platform/xdm/tutorials/create-schema-ui.html) y [Ingesta de datos](https://docs.adobe.com/content/help/es-ES/experience-platform/ingestion/home.html) en la documentación de Adobe Experience Platform.
1. Póngase en contacto con el administrador de cuentas de Adobe, el cual incluye lo siguiente:
   * Una solicitud para habilitar el análisis entre Canales
   * ID del conjunto de datos para el conjunto de datos que desea volver a escribir
   * El nombre de columna del ID persistente para el conjunto de datos deseado (identificador que aparece en cada fila)
   * El nombre de la columna del ID transitorio del conjunto de datos deseado (vínculo del identificador de persona entre conjuntos de datos)
   * Su preferencia de [repetición](replay.md) frecuencia y longitud de retrospectiva. Las opciones incluyen una reproducción una vez a la semana con una ventana retrospectiva de 7 días o una reproducción cada día con una ventana retrospectiva de 1 día.
1. El Administrador de cuentas de Adobe habilita Análisis de Canales cruzados al recibir la solicitud. Una vez activado, aparece un nuevo conjunto de datos con clave en Adobe Experience Platform que contiene una nueva columna de ID de persona. El administrador de cuentas de Adobe puede proporcionar el nuevo ID del conjunto de datos y el nombre de la columna ID de la persona.
1. [Cree una ](../create-connection.md) conexión CJA utilizando el conjunto de datos recién generado y cualquier otro conjunto de datos que desee incluir. Elija la ID de persona correcta para cada conjunto de datos.
1. [Cree una ](/help/data-views/create-dataview.md) vista de datos basada en la conexión.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Una vez configurada la vista de datos, la Análisis en CJA es igual que cualquier otra análisis en CJA, excepto que ahora los datos funcionan a través de canales y dispositivos.
