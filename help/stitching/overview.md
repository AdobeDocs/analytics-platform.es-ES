---
title: Información general de vinculación
description: Información general sobre la vinculación
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: c27d5f44243e2cda252ac6a484a70964f0999dfc
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 15%

---

# Información general de vinculación

>[!NOTE]
>
>Debe tener el paquete **Select** o superior (para la vinculación basada en el campo [Prime](fbs.md)) o el paquete **** o superior (para la vinculación basada en gráficos [graph-based stitching](gbs.md)) para usar la funcionalidad descrita en esta sección. Póngase en contacto con el administrador si no sabe qué paquete de Customer Journey Analytics tiene.

La vinculación de identidad (o simplemente, la vinculación) es una práctica funcionalidad que aumenta la idoneidad de un conjunto de datos de evento para el análisis en canales múltiples. El análisis entre canales es un caso de uso principal que Customer Journey Analytics puede gestionar, lo que le permite combinar y ejecutar informes sin problemas en varios conjuntos de datos de diferentes canales, en función de un identificador común (ID de persona).

Cuando combina conjuntos de datos con ID de personas similares, la atribución se transfiere a través de dispositivos y canales. Por ejemplo: un usuario visita su sitio por primera vez a través de un anuncio en su equipo de escritorio. Ese usuario encuentra un problema con su pedido y, a continuación, llama a su equipo de servicio de atención al cliente para que le ayude a resolverlo. Con el análisis en canales múltiples, puede atribuir eventos del centro de llamadas a la publicidad en la que se hizo clic originalmente.

Lamentablemente, no todos los conjuntos de datos basados en eventos que forman parte de su conexión en Customer Journey Analytics están suficientemente rellenados con datos para admitir esta atribución de forma predeterminada. En especial, los conjuntos de datos de experiencias basados en la web o en dispositivos móviles a menudo no tienen una información de ID de persona real disponible en todos los eventos.

La configuración permite volver a incrustar identidades en las filas de un conjunto de datos, asegurándose de que el ID de persona (ID vinculado) esté disponible en cada evento. La vinculación busca los datos de usuario de las sesiones autenticadas y no autenticadas para determinar el valor de ID transitorio común (ID de persona) que se puede utilizar como ID vinculado. Esta regeneración de claves permite resolver registros dispares en un único ID vinculado para su análisis en el nivel de la persona, en lugar de en el nivel de dispositivo o cookie.

Customer Journey Analytics admite dos tipos de vinculación: [vinculación basada en el campo](fbs.md) y [vinculación basada en gráficos](gbs.md).

## Requisitos previos

>[!IMPORTANT]
>
>Si no se cumplen todos los requisitos previos, es posible que no se pueda realizar correctamente el análisis entre canales.

Antes de usar la vinculación, asegúrese de que su organización está preparada con lo siguiente:

- La vinculación incluye la combinación de datos de usuario autenticados y no autenticados. Asegúrese de cumplir las leyes y regulaciones aplicables, incluida la obtención de los permisos necesarios para el usuario final, antes de activar la vinculación en un conjunto de datos de evento. Consulte [Definición de campos de identidad en la IU](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/ui/fields/identity) para obtener más información.

- Importe los datos deseados en Adobe Experience Platform:

   - Para los datos de Adobe Analytics, consulte [Uso de los datos del grupo de informes de Adobe Analytics en Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - Para ver otros tipos de datos, consulte [Crear un esquema](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) y [Ingesta de datos](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home) en la documentación de Adobe Experience Platform.

Se beneficia del análisis en canales múltiples si combina uno o más de los conjuntos de datos enlazados con otros conjuntos de datos, como los datos del centro de llamadas, como parte de la definición de la conexión de Customer Journey Analytics. Esta configuración de conexión supone que esos otros conjuntos de datos ya contienen un ID de persona en cada fila, similar al ID vinculado.


## Limitaciones

>[!IMPORTANT]
>
>
>- Aplique cualquier cambio que realice en el esquema del conjunto de datos de evento de origen también al nuevo esquema del conjunto de datos vinculado; de lo contrario, este se romperá.
>
>- Si elimina el conjunto de datos de origen, el conjunto de datos enlazado detiene el procesamiento y el sistema lo elimina.
>
>- Las etiquetas de uso de datos no se propagan automáticamente al esquema del conjunto de datos vinculado. Si tiene etiquetas de uso de datos aplicadas al esquema del conjunto de datos de origen, debe aplicar estas etiquetas de uso de datos manualmente al esquema del conjunto de datos vinculado. Consulte [Administración de etiquetas de uso de datos en Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview) para obtener más información.

La vinculación es una característica innovadora y sólida, pero tiene limitaciones en cuanto a su uso.

- Solo se admiten conjuntos de datos de evento. No se admiten otros conjuntos de datos, como conjuntos de datos de búsqueda.
- La vinculación no transforma el campo que se utiliza para la vinculación de ninguna manera. La vinculación utiliza el valor del campo especificado tal como existe en el conjunto de datos no vinculado dentro del lago de datos.
- El proceso de vinculación distingue entre mayúsculas y minúsculas. Por ejemplo, si aparece unas veces la palabra &quot;Bob&quot; en el campo y otras la palabra &quot;BOB&quot;, estos identificadores se tratan como dos personas independientes.

Asegúrese de no confundir la vinculación con lo siguiente:

- La combinación de dos o más conjuntos de datos. La vinculación solo se aplica a un conjunto de datos. La combinación de conjuntos de datos se produce como resultado de la configuración de una conexión de Customer Journey Analytics y la selección del mismo ID de persona en los conjuntos de datos seleccionados en la conexión.

- La unión de dos conjuntos de datos. En Customer Journey Analytics, una unión se utiliza a menudo para búsquedas o clasificaciones en Analysis Workspace. Aunque la vinculación utiliza la funcionalidad de unión, el proceso en sí mismo implica más que uniones.

>[!MORELIKETHIS]
>
>[Vinculación basada en el campo](fbs.md)
>[Vinculación basada en gráficos ](gbs.md)
>[Usar vinculación ](use-stitching.md)
>[Preguntas frecuentes sobre la vinculación ](faq.md)

