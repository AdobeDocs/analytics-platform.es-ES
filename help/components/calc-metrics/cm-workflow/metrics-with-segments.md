---
description: Aprenda a segmentar métricas individuales, lo que le permite realizar comparaciones de métricas dentro de la misma visualización.
title: Métricas segmentadas
feature: Calculated Metrics
exl-id: 37cc93df-9f51-42b3-918f-ed5864991621
TQID: https://experienceleague.adobe.com/dOOOOGytHT-5IMC9LNcNlBKLufs9PUkvjBoAgw38bEI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 504
ht-degree: 1%

---

# Métricas segmentadas

En el [Creador de métricas calculadas](cm-build-metrics.md#definition-builder), puede aplicar segmentos dentro de su definición de métrica. La aplicación de segmentos resulta útil si desea utilizar métricas para un subconjunto de los datos en el análisis.

>[!NOTE]
>
>Las definiciones de segmentos se actualizan a través de [Generador de segmentos](/help/components/segments/seg-builder.md). Si realiza un cambio en un segmento, este se actualiza automáticamente en cualquier lugar donde se utilice, incluso si forma parte de una definición de métrica calculada.
>

Desea comparar las métricas de los alemanes que interactúan con su marca con las de otros fuera de Alemania. Por lo tanto, puede responder preguntas como:

1. ¿Cuántas personas alemanas o internacionales están visitando tus [páginas más populares](#popular-pages)?
1. ¿Cuántas personas alemanas versus internacionales en [total](#totals) han interactuado en línea con su marca este mes?
1. ¿Cuáles son los [porcentajes](#percentages) de alemanes y personas internacionales que han visitado tus páginas populares?

Consulte las secciones siguientes para ilustrar cómo las métricas segmentadas pueden ayudarle a responder a estas preguntas. Si procede, se hace referencia a documentación más detallada.

## Páginas populares

1. [Cree una métrica calculada](cm-workflow.md) a partir de un proyecto de Workspace, denominado `German people`.
1. Desde el [Creador de métricas calculadas](cm-build-metrics.md), [cree un segmento](/help/components/segments/seg-builder.md), con el título `Germany`, que use el campo País de CRM a partir de los datos de CRM para determinar de dónde proviene una persona.

   >[!TIP]
   >
   >En el Creador de métricas calculadas, puede crear un segmento directamente mediante el panel Componentes.
   >   

   El segmento podría tener el aspecto siguiente:.

   ![Segmento Alemania](assets/filter-germany.png)

1. En el Creador de métricas calculadas, utilice el segmento para actualizar la métrica calculada.

   ![Métrica calculada Alemania](assets/calculated-metric-germany.png)

Repita los pasos anteriores para la versión internacional de la métrica calculada.

1. Cree una métrica calculada a partir del proyecto de Workspace, con el título `International people`.
1. Desde el Creador de métricas calculadas, cree un segmento con el título `Not Germany` que esté usando el campo País de CRM a partir de los datos de CRM para determinar de dónde proviene una persona.

   El segmento debería tener el aspecto siguiente:.

   ![Segmento Alemania](assets/filter-not-germany.png)

1. En el Creador de métricas calculadas, utilice el segmento para actualizar la métrica calculada.

   ![Métrica calculada Alemania](assets/calculated-metric-notgermany.png)


1. Cree un proyecto en Analysis Workspace, donde vea las páginas visitadas por personas alemanas e internacionales.

   ![Visualización de tabla de forma libre de Workspace que muestra personas alemanas frente a internacionales](assets/workspace-german-vs-international.png)


## Totales

1. Cree dos nuevas métricas calculadas basadas en el Total general. Abra cada uno de los segmentos creados anteriormente, cambie el nombre del segmento, establezca el **[!UICONTROL Tipo de métrica]** para **[!UICONTROL Personas]** en **[!UICONTROL Total general]** y use **[!UICONTROL Guardar como]** para guardar el segmento con el nuevo nombre. Por ejemplo:

   ![Métrica total para Alemania](assets/calculated-metric-germany-total.png)

1. Agregue una nueva visualización de tabla de forma libre a su proyecto de Workspace, que muestra las páginas totales de este mes.

   ![Visualización de tabla de forma libre de Workspace que muestra personas en alemán frente a personas en total internacionales](assets/workspace-german-vs-international-totals.png)


## Porcentajes

1. Cree dos nuevas métricas calculadas que calculen un porcentaje a partir de las métricas calculadas creadas anteriormente.

   ![Visualización de tabla de forma libre de Workspace que muestra el porcentaje de personas en alemán frente al total internacional](assets/calculated-metric-germany-total-percentage.png)


1. Actualice el proyecto de Workspace.

   ![Visualización de tabla de forma libre de Workspace que muestra personas en alemán frente a personas en total internacionales](assets/workspace-german-vs-international-totals-percentage.png)



>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Use una métrica calculada segmentada como métrica sin implementación](https://experienceleague.adobe.com/es/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-segmented-metrics){target="_blank"} para ver un vídeo de demostración.

{{videoaa}}

>[!ENDSHADEBOX]

