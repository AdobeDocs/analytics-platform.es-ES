---
title: Solicitar vinculación
description: Obtenga información sobre cómo solicitar la vinculación.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
source-git-commit: cbb18e9d0990d5df64995c2dabe8362c7c37bb45
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 26%

---

# Solicitud de vinculación


>[!IMPORTANT]
>
>La vinculación de solicitudes a través de Adobe ya no es necesaria y este método está obsoleto. [Habilitar la vinculación en la interfaz de usuario de Conexiones](use-stitching-ui.md).
>

## Solicitar asistencia

1. Póngase en contacto con Asistencia al cliente de Adobe con la siguiente información:

   - Una solicitud para habilitar la vinculación.
   - ID del conjunto de datos para el que desea volver a escribir.
   - El nombre de columna (ruta de identidad y área de nombres) del ID persistente del conjunto de datos deseado (el identificador que aparece en cada fila).
   - Si el conjunto de datos admite `identityMap`:
      - Para la vinculación basada en el campo, especifique el área de nombres tanto para los ID persistentes como para los de persona.
      - Para la vinculación basada en gráficos, especifique el área de nombres del ID persistente y el área de nombres de identidad que se utilizará para consultar el gráfico de identidades.
   - Si el conjunto de datos no admite `identityMap`:
      - Para la vinculación basada en el campo, el nombre de columna del ID de persona para el conjunto de datos deseado (el identificador de persona, que también actúa como vínculo entre conjuntos de datos en el contexto de una conexión).
      - En el caso de la vinculación basada en gráficos, es el área de nombres de identidad que desea utilizar para consultar el gráfico de identidad.
   - Su preferencia de ventana retrospectiva y frecuencia de reproducción. Consulta tu paquete de Customer Journey Analytics para ver las [opciones](#options) disponibles.
   - Nombre de la zona protegida.


2. La Asistencia al cliente de Adobe trabaja con el personal de ingeniería de Adobe para habilitar la vinculación cuando reciba la solicitud. Una vez habilitado, aparecerá en Adobe Experience Platform un conjunto de datos con clave con una columna de ID vinculada. La Asistencia al cliente de Adobe puede proporcionar el ID del nuevo conjunto de datos.
3. Cuando se activa por primera vez, Adobe proporciona un relleno de datos vinculados. Consulta tu paquete de Customer Journey Analytics para ver la [opción](#options) disponible.

4. Si desea utilizar el conjunto de datos vinculado en un análisis en canales múltiples, debe agregar el conjunto de datos vinculado a una [conexión](../connections/overview.md) en Customer Journey Analytics. A continuación, añada cualquier otro conjunto de datos necesario para el análisis entre canales y seleccione el ID de persona correcto para cada conjunto de datos.

5. [Cree una vista de datos](/help/data-views/create-dataview.md) en función de la conexión.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Una vez configurada la vista de datos, puede ejecutar el análisis de informes de Customer Journey Analytics en varios canales y dispositivos.

## Limitaciones

- Aplique cualquier cambio que realice en el esquema del conjunto de datos de evento de origen también al nuevo esquema del conjunto de datos vinculado.

- Si elimina el conjunto de datos de origen, el conjunto de datos vinculado detiene el procesamiento y el sistema lo elimina.

- Las etiquetas del uso de datos no se propagan automáticamente al esquema del conjunto de datos vinculado. Si tiene etiquetas de uso de datos aplicadas al esquema del conjunto de datos de origen, debe aplicar estas etiquetas de uso de datos manualmente al esquema del conjunto de datos vinculado. Consulte [Administración de etiquetas de uso de datos en Experience Platform](https://experienceleague.adobe.com/es/docs/experience-platform/data-governance/labels/overview) para obtener más información.
