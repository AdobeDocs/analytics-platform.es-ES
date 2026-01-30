---
title: Solicitud de vinculación
description: Cómo solicitar la vinculación
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
source-git-commit: 9ace0679796c3a813b1fbd97c62c20faf64db211
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 7%

---

# Solicitud de vinculación


>[!IMPORTANT]
>
>La vinculación de solicitudes a través de Adobe ya no es necesaria y este método está obsoleto. [Habilitar la vinculación en la interfaz de usuario de Conexiones](use-stitching-ui.md).
>



Una vez que su organización cumpla todos los [requisitos previos](overview.md#prerequisites) y comprenda las [limitaciones](overview.md#limitations) comunes y las limitaciones ([basadas en campos](fbs.md#limitations) y [basadas en gráficos](gbs.md#limitations)) específicas del método de vinculación, puede seguir estos pasos para solicitar y empezar a utilizar la vinculación en Customer Journey Analytics.

## Seleccionar opciones

El paquete de Customer Journey Analytics al que está autorizado determina los métodos de vinculación disponibles, las opciones para la duración del relleno inicial, la ventana retrospectiva, la frecuencia de reproducción y el número máximo de conjuntos de datos permitidos para la vinculación. Consulte la [descripción del producto de Customer Journey Analytics](https://helpx.adobe.com/es/legal/product-descriptions/customer-journey-analytics.html?lang=es) para obtener más información. Decida las opciones disponibles antes de solicitar asistencia.

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
      - Para la vinculación basada en gráficos, el área de nombres de identidad que se utilizará para consultar el gráfico de identidad.
   - Su preferencia de ventana retrospectiva y frecuencia de reproducción. Consulta tu paquete de Customer Journey Analytics para ver las [opciones](#options) disponibles.
   - Nombre de la zona protegida.


2. La Asistencia al cliente de Adobe trabaja con el personal de ingeniería de Adobe para habilitar la vinculación cuando reciba la solicitud. Una vez habilitado, aparecerá en Adobe Experience Platform un conjunto de datos con clave con una columna de ID vinculada. La Asistencia al cliente de Adobe puede proporcionar el ID del nuevo conjunto de datos.
3. Cuando se activa por primera vez, Adobe proporciona un relleno de datos vinculados. Consulta tu paquete de Customer Journey Analytics para ver la [opción](#options) disponible.

4. Si desea utilizar el conjunto de datos vinculado en un análisis en canales múltiples, debe agregar el conjunto de datos vinculado a una [conexión](../connections/overview.md) en Customer Journey Analytics. A continuación, añada cualquier otro conjunto de datos necesario para el análisis entre canales y seleccione el ID de persona correcto para cada conjunto de datos.

5. [Cree una vista de datos](/help/data-views/create-dataview.md) en función de la conexión.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Una vez configurada la vista de datos, puede ejecutar el análisis de informes de Customer Journey Analytics en varios canales y dispositivos.
