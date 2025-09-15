---
title: Información general de vinculación
description: Información general sobre la vinculación
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 9774e0e3af024823a03dbcd8d6766877f55e95d8
workflow-type: ht
source-wordcount: '792'
ht-degree: 100%

---

# Información general de vinculación

>[!NOTE]
>
>Debe disponer del paquete **Select** o superior (para [vinculación basada en campos](fbs.md)) o del paquete **Prime** o superior (para [vinculación basada en gráficos](gbs.md)) para utilizar la funcionalidad descrita en esta sección. Póngase en contacto con el administrador si no sabe qué paquete de Customer Journey Analytics tiene.

Vinculación de identidad (o simplemente, vinculación) es una potente función que aumenta la idoneidad de un conjunto de datos de evento para el análisis en canales múltiples. El análisis en canales múltiples es un caso de uso principal que Customer Journey Analytics puede gestionar, lo que le permite combinar y ejecutar informes de varios conjuntos de datos de diferentes canales sin problemas, en función de un identificador común (ID de persona).

Cuando combina conjuntos de datos con ID de personas similares, la atribución se transfiere a través de dispositivos y canales. Por ejemplo: un usuario visita su sitio por primera vez a través de un anuncio en su equipo de escritorio. Ese usuario encuentra un problema con su pedido y, a continuación, llama a su equipo de servicio de atención al cliente para que le ayude a resolverlo. Con el análisis en canales múltiples, puede atribuir eventos del centro de llamadas a la publicidad en la que se hizo clic originalmente.

Lamentablemente, no todos los conjuntos de datos basados en eventos que forman parte de su conexión en Customer Journey Analytics están suficientemente rellenados con datos para admitir esta atribución de forma predeterminada. En especial, los conjuntos de datos de experiencias basados en la web o en dispositivos móviles a menudo no tienen una información de ID de persona real disponible en todos los eventos.

La vinculación permite volver a incrustar identidades en las filas de un conjunto de datos, asegurándose de que el ID de persona (ID vinculado) esté disponible en cada evento. La vinculación busca los datos de usuario de las sesiones autenticadas y no autenticadas para determinar el valor de ID transitorio común (ID de persona) que se puede utilizar como ID vinculado. Esta nueva incrustación permite resolver registros dispares en un único ID vinculado para su análisis en el nivel de la persona, en lugar de en el nivel de dispositivo o cookie.

Customer Journey Analytics admite dos tipos de vinculación: [vinculación basada en el campo](fbs.md) y [vinculación basada en gráficos](gbs.md).

## Requisitos previos

>[!IMPORTANT]
>
>Si no se cumplen todos los requisitos previos, es posible que no se pueda realizar correctamente el análisis en canales múltiples.

Antes de usar la vinculación, asegúrese de que su organización está preparada con lo siguiente:

- La vinculación incluye la combinación de datos de usuario autenticados y no autenticados. Asegúrese de cumplir las leyes y regulaciones aplicables, incluida la obtención de los permisos necesarios para el usuario final, antes de activar la vinculación en un conjunto de datos de evento. Consulte [Definición de campos de identidad en la IU](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/ui/fields/identity) para obtener más información.

- Importe los datos deseados en Adobe Experience Platform:

   - Para obtener datos de Adobe Analytics, consulte [Uso de los datos de grupos de informes de Adobe Analytics en Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md). 
   - Para ver otros tipos de datos, consulte [Crear un esquema](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/tutorials/create-schema-ui) y [Ingesta de datos](https://experienceleague.adobe.com/es/docs/experience-platform/ingestion/home) en la documentación de Adobe Experience Platform.

Se beneficia del análisis en canales múltiples si combina uno o más de los conjuntos de datos enlazados con otros conjuntos de datos, como los datos del centro de llamadas, como parte de la definición de la conexión de Customer Journey Analytics. Esta configuración de conexión supone que esos otros conjuntos de datos ya contienen un ID de persona en cada fila, similar al ID vinculado.


## Limitaciones

>[!IMPORTANT]
>
>
>- Aplique cualquier cambio que realice en el esquema del conjunto de datos de evento de origen también al nuevo esquema del conjunto de datos vinculado.
>
>- Si elimina el conjunto de datos de origen, el conjunto de datos vinculado detiene el procesamiento y el sistema lo elimina.
>
>- Las etiquetas del uso de datos no se propagan automáticamente al esquema del conjunto de datos vinculado. Si tiene etiquetas de uso de datos aplicadas al esquema del conjunto de datos de origen, debe aplicar estas etiquetas de uso de datos manualmente al esquema del conjunto de datos vinculado. Consulte [Administración de etiquetas de uso de datos en Experience Platform](https://experienceleague.adobe.com/es/docs/experience-platform/data-governance/labels/overview) para obtener más información.

La vinculación es una función innovadora y sólida, pero tiene limitaciones en cuanto a su uso.

- Solo se admiten conjuntos de datos de evento. No se admiten otros conjuntos de datos, como conjuntos de datos de búsqueda.
- La vinculación no transforma el campo que se utiliza para la misma de ninguna manera. La vinculación utiliza el valor del campo especificado tal como existe en el conjunto de datos no identificado del lago de datos. 
- El proceso de vinculación distingue entre mayúsculas y minúsculas. Por ejemplo, si aparece unas veces la palabra &quot;Bob&quot; en el campo y otras la palabra &quot;BOB&quot;, estas se tratarán como dos personas independientes.

Asegúrese de no confundir la vinculación con lo siguiente:

- La combinación de dos o más conjuntos de datos. La vinculación solo se aplica a un conjunto de datos. La combinación de conjuntos de datos se produce como resultado de la configuración de una conexión de Customer Journey Analytics y la selección del mismo ID de persona en los conjuntos de datos seleccionados en la conexión.

- La unión de dos conjuntos de datos. En Customer Journey Analytics, una unión se utiliza a menudo para búsquedas o clasificaciones en Analysis Workspace. Aunque la vinculación utiliza la funcionalidad de unión, el proceso en sí mismo implica más que uniones.


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
>[Vinculación basada en campos](fbs.md)
>>[Vinculación basada en gráficos](gbs.md)
>>[Uso de la vinculación](use-stitching.md)
>>[Validación de la vinculación](validate.md)
>>[Preguntas frecuentes sobre la vinculación](faq.md)

