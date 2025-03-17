---
title: La sesión de métrica cuántica de tiempo se reproduce en los datos de Customer Journey Analytics
description: La sesión de Métrica cuántica de vínculos se reproduce con datos de CJA para comprender mejor el por qué del qué.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 94dad68426a08ffa34ded7905567fbea307b1de4
workflow-type: tm+mt
source-wordcount: '359'
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

Ahora, cada ID de sesión es un vínculo en el que puede hacer clic. Estos vínculos le llevan a Métrica cuántica en una nueva pestaña, lo que le permite analizar esa sesión en particular con más detalle. Consulte [Crear hipervínculos en una tabla de forma libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) para obtener más información sobre cómo agregar hipervínculos a elementos de dimensión de Analysis Workspace.

## Paso 2: Visualización de sesiones de Customer Journey Analytics

Una vez creado el informe de Workspace con vínculos en los que se puede hacer clic, puede utilizar Filtros en Customer Journey Analytics para identificar sesiones interesantes que pueda analizar más a fondo en Métricas cuánticas.
La tabla muestra todas las sesiones de ese segmento y puede hacer clic en cualquiera de ellas para explorarlas más en QM.  Obtenga más información acerca de la reproducción de la sesión de la métrica cuántica en [https://www.quantummetric.com/platform/session-replay](https://www.quantummetric.com/platform/session-replay)

