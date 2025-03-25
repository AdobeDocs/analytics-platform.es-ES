---
title: La sesión de métrica cuántica de tiempo se reproduce en los datos de Customer Journey Analytics
description: La sesión de Métrica cuántica de vínculos se reproduce con datos de CJA para comprender mejor el por qué del qué.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 752e8564c341cf02b5378a12a820f52ca6164a3d
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 1%

---

# La sesión de métrica cuántica de tiempo se reproduce en los datos de Customer Journey Analytics

Al vincular las reproducciones de sesiones de métricas cuánticas con los datos de CJA, los clientes pueden comprender mejor &quot;el por qué&quot; detrás de &quot;el qué&quot;.  Workspace se puede utilizar para detectar sesiones con fricción. A continuación, puede hacer clic en los ID de sesión con hipervínculos para explorar la reproducción de la sesión en la métrica cuántica.  Estos datos permiten ver el comportamiento dentro de una sesión y comprender mejor qué es lo que impulsa la fricción del consumidor.  A través de las reproducciones de sesión vinculadas con CJA, puede capturar el contexto crítico en torno al comportamiento de los clientes en su experiencia.

## Requisitos previos

Este caso de uso requiere que recopile el ID de sesión de la métrica cuántica junto con el resto de la implementación. Consulte [Recopilar ID de sesión de métricas cuánticas en Customer Journey Analytics](collect-session-id.md) para obtener información sobre cómo modificar la implementación.

## Paso 1: Configuración de Workspace para que se ajuste a la dimensión de ID de sesión

Cree una tabla de forma libre en Workspace y configúrela para que los valores de ID de sesión sean vínculos directamente a la métrica cuántica.

1. Inicie sesión en [experience.adobe.com](https://experience.adobe.com).
1. Vaya a Customer Journey Analytics y seleccione **[!UICONTROL Workspace]** en el menú superior.
1. Seleccione un proyecto existente o cree un proyecto.
1. Crear [tabla de forma libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Arrastre la dimensión ID de sesión al lienzo de Workspace.
1. Haga clic con el botón secundario en el encabezado de columna de dimensión y, a continuación, seleccione **[!UICONTROL Crear hipervínculos para todos los elementos de dimensión]**.
1. Seleccione **[!UICONTROL Crear una dirección URL personalizada]**.
1. Pegue la siguiente estructura de URL:

   ```
   https://adobe.quantummetric.com/#/replay/cookie:$value
   ```

1. Haga clic en **[!UICONTROL Crear]**.

Ahora, cada ID de sesión es un vínculo en el que puede hacer clic. Consulte [Crear hipervínculos en una tabla de forma libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) para obtener más información sobre cómo agregar hipervínculos a elementos de dimensión de Analysis Workspace.

## Paso 2: Visualización de sesiones de Customer Journey Analytics

Una vez que haya encontrado un segmento interesante para el que desee explorar las repeticiones de sesión, puede aplicarlo al panel que incluye los vínculos del ID de sesión y filtrar por segmento. La tabla devuelve todas las sesiones de ese segmento y puede hacer clic en cualquiera de ellas para explorarlas más detalladamente en Métrica cuántica.

Obtenga más información acerca de la reproducción de la sesión de la métrica cuántica en [https://www.quantummetric.com/platform/session-replay](https://www.quantummetric.com/platform/session-replay). Para obtener recursos adicionales, comuníquese con el representante de atención al cliente de Quantum Metric o envíe una solicitud a través del [Portal de solicitudes de clientes](https://community.quantummetric.com/s/public-support-page) de Quantum Metric.

