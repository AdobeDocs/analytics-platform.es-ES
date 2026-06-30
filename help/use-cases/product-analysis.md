---
title: Análisis de productos en Customer Journey Analytics
description: Descubra qué funciones puede utilizar dentro de Customer Journey Analytics para realizar análisis de productos de forma eficaz.
exl-id: b185a2ed-18c8-4fb3-8c69-693d5fee0e67
TQID: https://experienceleague.adobe.com/24OrFfxJY7XuqMYoTrmijM5xRfsdGhfA-aKe5tY-7xw
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bfa38d8a-4e93-4fd8-8cd8-e72c589e3af8
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
  - id: c91f8bd2-df97-4c6a-afcd-f1cde8221302
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
  - id: f3ca85c1-72de-4df2-97ed-05753cd77c47
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 28cfbe249f20361bf56f0a6216bc715dae5a6d3a
workflow-type: tm+mt
source-wordcount: 896
ht-degree: 4%

---

# Análisis de productos en Customer Journey Analytics

El análisis de productos es el proceso de comprender cómo los usuarios interactúan con el producto en cada fase de su recorrido. Implica analizar datos para descubrir perspectivas sobre el comportamiento del usuario, el rendimiento del producto y las oportunidades de crecimiento. Un análisis de producto eficaz ayuda a los equipos a tomar decisiones informadas para mejorar las experiencias de los usuarios, impulsar la participación y lograr los objetivos empresariales.

Customer Journey Analytics ofrece a los equipos las herramientas necesarias para analizar y optimizar las experiencias de los productos con las siguientes capacidades:

* **Administrar datos de productos a escala**: Ingeste, transforme y administre fácilmente datos de productos para satisfacer sus necesidades comerciales, lo que garantiza perspectivas confiables.
* **Adquisición y activación de medidas**: haga un seguimiento de cómo los nuevos usuarios descubren su producto y se relacionan con los primeros eventos que generan valor.
* **Medir la participación y la adopción**: comprenda cómo progresan los usuarios en el funnel del producto, identifique los puntos de fricción y rastree la adopción de características clave.
* **Medir la retención y la pérdida**: Analice la retención de usuarios a lo largo del tiempo, identifique los indicadores de pérdida y desarrolle estrategias para reducir la pérdida y aumentar la lealtad.
* **Perspectivas de productos de acción**: convierta las perspectivas basadas en datos en estrategias procesables para mejorar la experiencia del usuario e impulsar el crecimiento sostenible de los productos.
* **Comparta perspectivas con su organización**: comunique los hallazgos clave entre equipos para alinear esfuerzos, fomentar la colaboración y garantizar que todos trabajen en pos de objetivos empresariales y de productos compartidos.

Al aprovechar estas capacidades, Customer Journey Analytics le permite desbloquear todo el potencial de su producto y crear un enfoque fluido basado en datos para impulsar el éxito del usuario y la empresa.

## Administración de datos de productos a escala

Los datos precisos del producto son la piedra angular de un análisis eficaz del producto. La ingesta de datos se refiere al proceso de instrumentar y recopilar datos de productos, mientras que la administración de datos implica transformar y mantener estos datos para garantizar que cumplan con sus requisitos analíticos.

Las siguientes funciones de Adobe Experience Platform y Customer Journey Analytics le permiten introducir y administrar los datos de sus productos a escala:

* Adobe Experience Platform
   * [Conjuntos de datos](https://experienceleague.adobe.com/es/docs/experience-platform/catalog/datasets/overview)
   * [Preparación de datos](https://experienceleague.adobe.com/es/docs/experience-platform/data-prep/home)
   * [Data Distiller](https://experienceleague.adobe.com/es/docs/experience-platform/query/data-distiller/overview)
* Customer Journey Analytics
   * [Conexiones](/help/connections/overview.md)
   * [Vistas de datos](/help/data-views/data-views.md), incluidos [campos derivados&#x200B;](/help/data-views/derived-fields/derived-fields.md)
   * [Segmentos](/help/components/segments/seg-overview.md)
   * [Métricas calculadas](/help/components/calc-metrics/calc-metr-overview.md)
   * [Análisis guiado: línea de tiempo](/help/guided-analysis/types/timeline.md)

## Medir adquisición y activación

El crecimiento del producto depende de perspectivas procesables de funnel que atraigan a nuevos usuarios, revelen las rutas de conversión y eliminen la fricción a lo largo del recorrido.

* La adquisición realiza un seguimiento de los nuevos usuarios que llegan a su producto, incluido cómo llegan y qué esfuerzos son los más o menos efectivos.
* Activation supervisa a los nuevos usuarios que se relacionan con su primer evento de valor, definido según sus objetivos específicos.

![Crecimiento activo](/help/guided-analysis/assets/active.png)

Las siguientes funciones de Customer Journey Analytics le permiten medir tanto la adquisición como la activación de forma eficaz:

* [Análisis guiado: crecimiento activo](/help/guided-analysis/types/active-growth.md)
* [Análisis guiado: crecimiento neto](/help/guided-analysis/types/net-growth.md)
* [Análisis guiado: tendencias](/help/guided-analysis//types/trends.md)
* [Panel de atribución](/help/analysis-workspace/c-panels/attribution.md)
* [Tabla de forma libre](/help/analysis-workspace/c-panels/freeform-panel.md) que incluye la dimensión de canal de marketing (creando mediante un [campo derivado](/help/data-views/derived-fields/derived-fields.md))

## Medir la participación y la adopción

La adquisición de nuevos usuarios amplía la parte superior de su funnel de productos. La participación se centra en guiar a estos usuarios más abajo en funnel y en eliminar los obstáculos a su éxito. Su éxito impulsa directamente el éxito de su negocio.

![Análisis de participación](/help/guided-analysis/assets/feature-matrix.png)

Las siguientes funciones de Customer Journey Analytics le ayudan a realizar un seguimiento de la participación y adopción de productos:

* [Análisis guiado: participación](/help/guided-analysis/types/engagement.md)
* [Análisis guiado: tendencias](/help/guided-analysis/types/trends.md)
* [Análisis guiado: frecuencia](/help/guided-analysis/types/frequency.md)
* [Análisis guiado: Funnel](/help/guided-analysis/types/funnel.md)
* [Análisis guiado: Tendencias de conversión](/help/guided-analysis/types/conversion-trends.md)
* [Análisis guiado: Impacto de la versión](/help/guided-analysis/types/release-impact.md)
* [Análisis guiado: Impacto del primer uso](/help/guided-analysis/types/first-use-impact.md)
* [Análisis guiado: línea de tiempo](/help/guided-analysis/types/timeline.md)
* [Tablas improvisadas](/help/analysis-workspace/c-panels/freeform-panel.md)
* [Flujo](/help/analysis-workspace/visualizations/c-flow/flow.md)

## Medir la retención y la pérdida

La retención mide cuántos usuarios siguen interactuando con el producto después de su adquisición y activación iniciales. Los productos de alto rendimiento mantienen una base de usuarios estable y leal al maximizar la interacción con las funciones que más se correlacionan con el uso continuo. Un usuario retenido regresa e interactúa con el producto a lo largo del tiempo, mientras que un usuario perdido no lo hace. Los equipos de productos hacen un seguimiento de la retención para identificar las funciones que impulsan la participación continua y diseñar intervenciones que desplazan a los usuarios perdidos hacia un comportamiento del usuario retenido.

![Análisis de retención](/help/guided-analysis/assets/retention.png)

Las siguientes funciones de Customer Journey Analytics le ayudan a realizar un seguimiento de la retención y la pérdida de forma eficaz:

* [Análisis guiado: Retención](/help/guided-analysis/types/retention.md)
* [Análisis guiado: crecimiento activo](/help/guided-analysis/types/active-growth.md)
* [Análisis guiado: crecimiento neto](/help/guided-analysis/types/net-growth.md)
* [Tabla de cohortes](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)

## Perspectivas de productos procesables

Las perspectivas solo proporcionan valor cuando impulsan la acción. Convierta los resultados de los análisis en acciones que mejoren la experiencia del usuario y apoyen el crecimiento de productos a largo plazo.

Las siguientes funciones de CX Enterprise le permiten actuar con información de forma eficaz:

* [Crear y publicar audiencias](/help/components/audiences/publish.md) para la activación desde Customer Journey Analytics
* Activar audiencias a través de productos de CX Enterprise:
   * [Ejecute experimentos](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/content-management/content-experiment/get-started-experiment) en AJO y Adobe Target y mida el impacto de las variaciones en Customer Journey Analytics mediante el [panel Experimentación](/help/analysis-workspace/c-panels/experimentation.md)
   * [Entregue participaciones en la aplicación](https://experienceleague.adobe.com/es/docs/journey-optimizer/using/channels/in-app/get-started-in-app) a los usuarios de AJO.
* [Activar audiencias](https://experienceleague.adobe.com/es/docs/experience-platform/destinations/ui/activate/activation-overview) en destinos externos con Adobe Real-time CDP.

## Compartir perspectivas con la organización

Comunique los resultados clave entre los equipos para alinear los esfuerzos, fomentar la colaboración y garantizar que todos trabajen en pos de objetivos empresariales y de productos compartidos.

![Análisis guiado en Workspace](assets/guided-analysis-workspace.png)

Las siguientes funciones de Customer Journey Analytics le ayudan a compartir perspectivas de forma eficaz:

* [Compartir](/help/analysis-workspace/curate-share/share-projects.md) vistas de análisis guiadas adaptadas a preguntas comerciales específicas, lo que permite a los consumidores responder automáticamente a su siguiente pregunta
* Combine análisis guiados, paneles y visualizaciones en un tablero completo en [Analysis Workspace](/help/analysis-workspace/home.md)
* Cree una [tarjeta de puntuación móvil](/help/mobile-app/home.md) con información clave del producto para ejecutivos y otros consumidores en sus desplazamientos
