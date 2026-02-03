---
title: Información general de vinculación
description: Obtenga información acerca de los conceptos, beneficios, requisitos previos y limitaciones de la vinculación de identidad.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 9bebfaf7e10762bc7382d8b0d55148ee23698dd9
workflow-type: tm+mt
source-wordcount: '965'
ht-degree: 60%

---

# Información general de vinculación

>[!NOTE]
>
>Debe tener el paquete de Customer Journey Analytics **Select** o superior (para la vinculación basada en el campo [Prime](fbs.md)) o el paquete de Customer Journey Analytics **&#x200B;**&#x200B;o superior (para la vinculación basada en gráficos [graph-based stitching](gbs.md)) para utilizar la funcionalidad descrita en esta sección. Póngase en contacto con el administrador si no sabe qué paquete de Customer Journey Analytics tiene.

Vinculación de identidad (o simplemente, vinculación) es una potente función que aumenta la idoneidad de un conjunto de datos de evento para el análisis en canales múltiples. El análisis en canales múltiples es un caso de uso principal de Customer Journey Analytics. Esta característica le permite combinar y ejecutar informes sin problemas en varios conjuntos de datos de diferentes canales, según un identificador común (ID de persona).

Cuando combina conjuntos de datos con ID de personas similares, la atribución se transfiere a través de dispositivos y canales. Por ejemplo: un usuario visita su sitio a través de un anuncio en su equipo de escritorio. El usuario compra un producto, pero luego encuentra un problema con el pedido. A continuación, llama a su equipo del servicio de atención al cliente para que le ayude a resolver el problema. Con el análisis en canales múltiples, puede atribuir eventos del centro de llamadas al anuncio en el que se hizo clic originalmente.

Lamentablemente, no todos los conjuntos de datos basados en eventos que forman parte de su conexión en Customer Journey Analytics están suficientemente rellenados con datos para admitir esta atribución de forma predeterminada. En especial, los conjuntos de datos de experiencias basados en la web o en dispositivos móviles a menudo no tienen una información de ID de persona real disponible en todos los eventos.

La configuración vuelve a incrustar las identidades dentro de las filas de un conjunto de datos para garantizar que el ID de persona (ID vinculado) esté disponible en cada evento. La vinculación examina los datos de usuario de las sesiones autenticadas y las no autenticadas para determinar el valor de ID de persona común que se puede utilizar como ID vinculado. Esta regeneración de claves resuelve registros dispares en un único ID vinculado para su análisis en el nivel de la persona, en lugar de en el nivel de dispositivo o cookie.

Customer Journey Analytics admite dos tipos de vinculación: [vinculación basada en el campo](fbs.md) y [vinculación basada en gráficos](gbs.md).

## Requisitos previos

>[!IMPORTANT]
>
>Si no se cumplen todos los requisitos previos, es posible que no se pueda realizar correctamente el análisis en canales múltiples.

Antes de usar la vinculación, asegúrese de que su organización está preparada con lo siguiente:

- La vinculación incluye la combinación de datos de usuario autenticados y no autenticados. Asegúrese de cumplir las leyes y regulaciones aplicables, incluida la obtención de los permisos necesarios para el usuario final, antes de activar la vinculación en un conjunto de datos de evento.

- Importe los datos deseados en Adobe Experience Platform:

   - Para obtener datos de Adobe Analytics, consulte [Uso de los datos de grupos de informes de Adobe Analytics en Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md). 
   - Para ver otros tipos de datos, consulte [Crear un esquema](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/tutorials/create-schema-ui) y [Ingesta de datos](https://experienceleague.adobe.com/es/docs/experience-platform/ingestion/home) en la documentación de Adobe Experience Platform.

Se beneficia del análisis en canales múltiples si combina uno o más de los conjuntos de datos enlazados con otros conjuntos de datos, como los datos del centro de llamadas, como parte de la definición de la conexión de Customer Journey Analytics. Esta configuración de conexión supone que esos otros conjuntos de datos ya contienen un ID de persona en cada fila, similar al ID vinculado.

Una vez que su organización cumpla [requisitos previos](overview.md#prerequisites) genéricos, comprenda las [limitaciones](overview.md#limitations) comunes y también los requisitos previos y limitaciones específicos del método de vinculación ([basados en el campo](fbs.md) y [basados en gráficos](gbs.md)), puede seguir estos pasos para solicitar y empezar a utilizar la vinculación en Customer Journey Analytics.


## Limitaciones

La vinculación es una función innovadora y sólida, pero tiene limitaciones en cuanto a su uso.

- Solo se admiten conjuntos de datos de evento. No se admiten otros conjuntos de datos, como conjuntos de datos de búsqueda.
- La vinculación no transforma el campo que se utiliza para la misma de ninguna manera. La vinculación utiliza el valor del campo especificado tal como existe en el conjunto de datos no identificado del lago de datos. 
- El proceso de vinculación distingue entre mayúsculas y minúsculas. Por ejemplo, los valores de identidad `Bob` y `BOB` se tratan como dos personas independientes.

Asegúrese de no confundir la vinculación con lo siguiente:

- La combinación de dos o más conjuntos de datos. La vinculación solo se aplica a un conjunto de datos. La combinación de conjuntos de datos se produce como resultado de la configuración de una conexión de Customer Journey Analytics y la selección del mismo ID de persona en los conjuntos de datos seleccionados en la conexión.

- La unión de dos conjuntos de datos. En Customer Journey Analytics, una unión se utiliza a menudo para búsquedas o clasificaciones en Analysis Workspace. Aunque la vinculación utiliza la funcionalidad de unión, el proceso en sí mismo implica más que uniones.


## Opciones

El paquete de Customer Journey Analytics al que está autorizado determina los métodos de vinculación disponibles, las opciones para la duración inicial del relleno, la ventana retrospectiva, la frecuencia de reproducción y el número máximo de conjuntos de datos permitidos para la vinculación. Consulte la [descripción del producto de Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html?lang=es) para obtener más información. Decida las opciones disponibles antes de habilitar la vinculación.

| | Customer Journey Analytics<br/>Seleccionar | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Métodos de vinculación disponibles | Vinculación basada en el campo | Vinculación basada en el campo<br/>Vinculación basada en gráficos | Vinculación basada en el campo<br>Vinculación basada en gráficos</li> |
| Duración de relleno de vinculación única | 13 meses | 13 meses | 25 meses |
| Ventana retrospectiva y frecuencia de reproducción | 1 día, todos los días<br/>hasta 7 días, semanalmente | 1 día, todos los días<br/>hasta 14 días, semanalmente | 1 día, todos los días<br/>hasta 30 días, semanalmente |
| Número máximo de conjuntos de datos permitidos para la vinculación | 5 | 15 | 50 |

## Habilitación de la vinculación

Puede habilitar la vinculación de dos formas:

- [Solicitud para habilitar la vinculación](/help/stitching/use-stitching.md) (obsoleto). Una vez aprobado, se crea un conjunto de datos duplicado para el conjunto de datos para el que ha solicitado la vinculación. Este conjunto de datos duplicado contiene una columna adicional con el identificador vinculado. Debe crear una conexión nueva o editar una existente que incluya el conjunto de datos enlazado para utilizar los datos enlazados en Customer Journey Analytics.
- [Habilitar la vinculación en la interfaz de Conexiones](/help/stitching/use-stitching-ui.md). Al configurar la vinculación de un conjunto de datos en la interfaz Conexiones, la vinculación se produce sobre la marcha, durante la ingesta de datos de ese conjunto de datos en Customer Journey Analytics.


## Conjuntos de datos de Journey Optimizer

La vinculación admite los siguientes conjuntos de datos de Journey Optimizer generados automáticamente:

- Eventos de paso de recorrido de AJO
- Conjunto de datos de evento de actividad entrante de AJO
- Conjunto de datos de superficies de AJO
- Conjunto de datos de evento de comentarios de mensajes* de AJO Conjunto de datos de evento de experiencia de seguimiento push de AJO
- Conjunto de datos de evento de experiencia de seguimiento de correo electrónico de AJO
- Conjunto de datos de evento de comentarios BCC de AJO
- Conjunto de datos de evento de comentarios de actividades en vivo de AJO
- Conjunto de datos de evento de decisión ExD de AJO

>[!MORELIKETHIS]
>
>[Vinculación basada en el campo](fbs.md)
>[Vinculación basada en gráficos](gbs.md)
>[Uso de la vinculación](use-stitching.md)
>[Validación de la vinculación](validate.md)
>[Preguntas frecuentes sobre la vinculación](faq.md)

