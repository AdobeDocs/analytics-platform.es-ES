---
title: La sesión de métrica cuántica de tiempo se reproduce en los datos de Customer Journey Analytics
description: La sesión de Métrica cuántica de vínculos se reproduce con datos de CJA para comprender mejor el por qué del qué.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 9f954709a3dde01b4e01581e34aece07fe0256b1
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 1%

---

# La sesión de métrica cuántica de tiempo se reproduce en los datos de Customer Journey Analytics

Al vincular las reproducciones de sesiones de métricas cuánticas con los datos de CJA, los clientes pueden comprender mejor &quot;el por qué&quot; detrás de &quot;el qué&quot;.  Workspace se puede utilizar para detectar sesiones con fricción. A continuación, puede hacer clic en los ID de sesión con hipervínculos para explorar la reproducción de la sesión en la métrica cuántica.  Estos datos permiten ver el comportamiento dentro de una sesión y comprender mejor qué es lo que impulsa la fricción del consumidor.  A través de las reproducciones de sesión vinculadas con CJA, puede capturar el contexto crítico en torno al comportamiento de los clientes en su experiencia.

## Requisitos previos

En estos pasos se da por hecho que utiliza etiquetas en la recopilación de datos de Adobe Experience Platform. Puede adaptar estos métodos de recopilación de datos a una implementación manual de Web SDK si su organización no utiliza etiquetas.

Consulte la documentación de la [extensión de etiqueta de métrica cuántica](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric) para obtener más información.

## Paso 1: Recopilar el ID de sesión de métrica cuántica con la extensión de etiquetas de métrica cuántica

Siga estos pasos para anexar el ID de sesión de métrica cuántica a los datos que envía a Adobe Experience Platform.

1. Utilice la extensión de métrica cuántica en la interfaz de usuario de etiquetas para enviar datos a la métrica cuántica.
1. Cree cuatro elementos de datos:
   1. Uno que captura el identificador de sesión de la métrica cuántica de la cookie de métrica cuántica llamada `QuantumMetricSessionID`
   1. Una que extrae el identificador de sesión de métrica cuántica de `localStorage`. A veces, este elemento de datos se carga más rápido que la cookie establecida en el otro elemento de datos.
   1. Utilice el asistente de elementos de datos o JavaScript personalizado para extraer el nodo `s` del elemento de datos `localStorage`.
   1. Una que utilice la lógica para buscar primero el elemento de datos de cookie y devolverlo a una ruta de objeto XDM si se encuentra. Si no está definido, intente buscar en el elemento de datos de objeto `localStorage` extraído.
1. Envíe el elemento de datos final ID de sesión de métrica cuántica al objeto XDM enviado en cada evento.

>[!NOTE]
>A veces, Web SDK se ejecuta más rápido que el código de métrica cuántica. En estos casos, el ID de sesión se envía en la visita posterior. Si un visitante regresa, el ID de sesión no se recopila en estas instancias.

## Paso 2: Confirmar los campos del conjunto de datos incluidos

Confirme que los conjuntos de datos de la conexión ahora tienen el ID de sesión de métrica cuántica en el conjunto de datos deseado.

## Paso 3: Añadir el ID de sesión de métrica cuántica como dimensión disponible

Edite la vista de datos existente para añadir el ID de sesión como una dimensión disponible en Customer Journey Analytics.

1. Inicie sesión en [experience.adobe.com](https://experience.adobe.com).
1. Vaya a Customer Journey Analytics y seleccione **[!UICONTROL Vistas de datos]** en el menú superior.
1. Seleccione la vista de datos existente que desee.
1. Busque la lista ID de sesión de métrica cuántica a la izquierda y arrástrela al área de dimensiones en el centro.
1. En el panel derecho, establezca la configuración [persistencia](/help/data-views/component-settings/persistence.md) en &#39;Sesión&#39;.
1. Haga clic en **[!UICONTROL Guardar]**.

## Paso 4: Configuración de Workspace para que se ajuste a la dimensión de ID de sesión

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

## Paso 5: Ver sesiones desde Customer Journey Analytics

Una vez que haya encontrado un segmento interesante que desee explorar en las repeticiones de sesión, puede aplicarlo al panel que incluye los vínculos del ID de sesión y el segmento. La tabla devuelve todas las sesiones de ese segmento y puede hacer clic en cualquiera de ellas para explorarlas más en Métrica cuántica.

Consulte [La guía empresarial para la reproducción de sesión](https://www.quantummetric.com/resources/ebook/the-enterprise-guide-to-session-replay) en Métrica cuántica para obtener más información. También puede ponerse en contacto con el representante de atención al cliente de la métrica cuántica o enviar una solicitud a través del [Portal de solicitudes de clientes de la métrica cuántica](https://community.quantummetric.com/s/public-support-page).
