---
title: Usar vinculación
description: Cómo usar la vinculación
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
source-git-commit: 5e25cb4d974ab85cca3aa2bb777675e12f63038b
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 9%

---

# Usar vinculación

Una vez que su organización cumpla todos los [requisitos previos](#prerequisites) y comprenda las [limitaciones](#limitations) comunes y las limitaciones ([basadas en campos](#limitations-1) y [basadas en gráficos](#limitations-2)) específicas del método de vinculación, puede seguir estos pasos para empezar a utilizar la vinculación en el Customer Journey Analytics.

## Seleccionar opciones

El paquete de Customer Journey Analytics al que está autorizado determina los métodos de vinculación disponibles, las opciones para la duración del relleno inicial, la ventana retrospectiva, la frecuencia de reproducción y el número máximo de conjuntos de datos permitidos para la vinculación. Consulte la [descripción del producto del Customer Journey Analytics](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html?lang=es) para obtener más información. Decida las opciones disponibles antes de solicitar asistencia.

| | Customer Journey Analytics<br/>Seleccionar | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Métodos de vinculación disponibles | <li>Vinculación basada en el campo</li> | <li>Vinculación basada en el campo</li><li>Identificación basada en gráficos</li> | <li>Vinculación basada en el campo</li><li>Identificación basada en gráficos</li> |
| Duración de relleno de vinculación única | 13 meses | 13 meses | 25 meses |
| Ventana retrospectiva y frecuencia de reproducción | <li>1 día, todos los días</li><li>hasta 7 días, semanales</li> | <li>1 día, todos los días</li><li>hasta 14 días, semanales</li> | <li>1 día, todos los días</li><li>hasta 30 días por semana</li> |
| Número máximo de conjuntos de datos permitidos para la vinculación | 5 | 10 | 50 |

## Solicitar asistencia

1. Póngase en contacto con Asistencia al cliente de Adobe con la siguiente información:

   - Una solicitud para habilitar la vinculación.
   - ID del conjunto de datos para el que desea volver a escribir.
   - El nombre de columna (ruta de identidad y área de nombres) del ID persistente del conjunto de datos deseado (el identificador que aparece en cada fila).
   - Para la vinculación basada en el campo, el nombre de columna del ID transitorio para el conjunto de datos deseado (el identificador personal, que también actúa como vínculo entre conjuntos de datos en el contexto de una conexión). Para la vinculación basada en gráficos, el área de nombres de identidad que se utilizará para consultar el gráfico de identidad.
   - Su preferencia de ventana retrospectiva y frecuencia de reproducción. Consulta con tu Customer Journey Analytics el paquete de [opciones](#options) disponibles.
   - Nombre de la zona protegida.


2. La Asistencia al cliente de Adobe trabaja con el personal de ingeniería de Adobes para habilitar la vinculación al recibir la solicitud. Una vez habilitado, aparecerá en Adobe Experience Platform un nuevo conjunto de datos con clave con una nueva columna de ID vinculada. La Asistencia al cliente de Adobe puede proporcionar el ID del nuevo conjunto de datos.

3. Cuando se activa por primera vez, el Adobe proporciona un relleno de datos vinculados. Consulte el paquete del Customer Journey Analytics para ver la [opción](#options) disponible.

4. Si desea utilizar el nuevo conjunto de datos vinculado en un análisis en canales múltiples, debe agregar el nuevo conjunto de datos vinculado a una [conexión](../connections/overview.md) en el Customer Journey Analytics. A continuación, añada cualquier otro conjunto de datos necesario para el análisis entre canales y seleccione el ID de persona correcto para cada conjunto de datos.

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


