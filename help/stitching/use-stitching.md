---
title: Solicitar vinculación
description: Obtenga información sobre cómo solicitar la vinculación.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
source-git-commit: a94f3fe6821d96c76b759efa3e7eedc212252c5f
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 20%

---

# Solicitud de vinculación


>[!IMPORTANT]
>
>La vinculación de solicitudes a través de Adobe ya no es necesaria y este método está obsoleto. [Habilitar la vinculación en la interfaz de usuario de Conexiones](use-stitching-ui.md).
>

Una vez que su organización cumpla [requisitos previos](overview.md#prerequisites) genéricos, comprenda las [limitaciones](overview.md#limitations) comunes y también los requisitos previos y limitaciones específicos del método de vinculación ([basados en el campo](fbs.md) y [basados en gráficos](gbs.md)), puede seguir estos pasos para solicitar y empezar a utilizar la vinculación en Customer Journey Analytics.

## Seleccionar opciones

El paquete de Customer Journey Analytics al que está autorizado determina los métodos de vinculación disponibles, las opciones para la duración inicial del relleno, la ventana retrospectiva, la frecuencia de reproducción y el número máximo de conjuntos de datos permitidos para la vinculación. Consulte la [descripción del producto de Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html?lang=es) para obtener más información. Decida las opciones disponibles antes de solicitar asistencia.

| | Customer Journey Analytics<br/>Seleccionar | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Métodos de vinculación disponibles | Vinculación basada en el campo | Vinculación basada en el campo<br/>Vinculación basada en gráficos | Vinculación basada en el campo<br>Vinculación basada en gráficos</li> |
| Duración de relleno de vinculación única | 13 meses | 13 meses | 25 meses |
| Ventana retrospectiva y frecuencia de reproducción | 1 día, todos los días<br/>hasta 7 días, semanalmente | 1 día, todos los días<br/>hasta 14 días, semanalmente | 1 día, todos los días<br/>hasta 30 días, semanalmente |
| Número máximo de conjuntos de datos permitidos para la vinculación | 5 | 15 | 50 |

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
