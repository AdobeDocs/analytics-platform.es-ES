---
title: Analizar Audiencias De Experience Platform En Customer Journey Analytics
description: Obtenga información sobre cómo analizar audiencias de Experience Platform en Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
exl-id: 095cae34-1337-464a-9682-3c899295c0a8
autotag-review: '2026-05-19T10:44:54.802Z'
TQID: 'https://experienceleague.adobe.com/ljj9CIUW58m27w8Mo9HlRJ0kgYXGIgqwuarPR2wNUjw'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2: id: d3fb138f-79e4-4a81-aedb-76dd93560085
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 503
ht-degree: 0%

---

# Analizar audiencias de Experience Platform en Customer Journey Analytics {#analyze-audiences-RTCDP}

Después de [crear una configuración de análisis de audiencia](/help/connections/audience-analysis/audience-analysis-configure.md), los datos de audiencia estarán disponibles como nuevas dimensiones en las vistas de datos donde los configure para que se creen. Puede utilizar las nuevas dimensiones de audiencia en cualquier lugar de Analysis Workspace si tiene acceso a una vista de datos en la que se añadieron las dimensiones de análisis de audiencia.

## Uso de la plantilla Información general de audiencia

Hay disponible una plantilla Información general de audiencia en Customer Journey Analytics.

<!-- Can you also use the new audience dimensions in any project, regardless of whether it's a template? I assume so -->

<!-- What are the names of the new dimensions? Are they customized to whatever your audience names are in AEP, or are they always the same? Are they the dimensions available in the Audience overview template? (Audience Name, Audience Origin, Exited Audience Name, Exited Audience Origin; Audience Description, Exited Audience Description). Metrics included (Distinct Audiences) -->

Para obtener información acerca de cómo obtener acceso a la plantilla de información general de Audiencia, vea [Obtener acceso y ejecutar una plantilla](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template) en [Usar plantillas](/help/analysis-workspace/templates/use-templates.md).

La plantilla Información general de audiencia contiene los siguientes paneles:

## Panel de información general de uso

Muestra datos de todas las audiencias con eventos de uso asociados con la vista de datos seleccionada. Los datos de pertenencia a audiencias se actualizan diariamente desde Experience Platform. Los datos siempre se muestran para ayer, por lo que al cambiar el intervalo de fechas del panel, se generan datos inexactos.

Utilice la tabla de este panel para comprender mejor el comportamiento de la audiencia. Arrastre la dimensión Descripción de audiencia desde la vista de datos seleccionada y agréguela como un desglose. También puede utilizar cualquier otra dimensión de interacción (como Página, Acción, etc.) como desglose.

## Panel de orígenes de audiencia principales

Muestra dónde se creó la audiencia, ya sea en RTCDP, Customer Journey Analytics, etc.

Utilice la tabla de este panel para comprender mejor cómo el origen de la audiencia puede afectar a otros factores. Arrastre la dimensión Nombre de audiencia desde la vista de datos seleccionada y agréguela como un desglose. También puede utilizar cualquier otra dimensión de interacción (como Página, Acción, etc.) como desglose.

## Panel de superposición de audiencia

Muestra datos de todas las audiencias con eventos de uso asociados con la vista de datos seleccionada. Los datos siempre se muestran para ayer, por lo que al cambiar el intervalo de fechas del panel, se generan datos inexactos.

Seleccione hasta tres audiencias en la tabla de este panel para ver cómo se superponen en el diagrama de Venn correspondiente.

## Panel de uso de audiencia cerrado

Muestra datos de todas las audiencias de salida con eventos de uso asociados con la vista de datos seleccionada. Los datos siempre se muestran para ayer, por lo que al cambiar el intervalo de fechas del panel, se generan datos inexactos. &quot;Audiencias salientes&quot; son audiencias en las que personas con eventos de uso abandonaron o abandonaron el día anterior.

Utilice la tabla de este panel para comprender mejor el comportamiento de la audiencia. Arrastre la dimensión Descripción de audiencia de salida desde la vista de datos seleccionada y agréguela como un desglose. También puede utilizar cualquier otra dimensión o métrica de interacción (como Página, Acción, etc.) como desglose.

## Panel de orígenes de audiencia principales salientes

Muestra dónde se creó originalmente cada audiencia que salió, ya sea en RTCDP, Customer Journey Analytics, etc.

Utilice la tabla de este panel para comprender mejor cómo el origen de la audiencia puede afectar a otros factores. Arrastre la dimensión Nombre de audiencia de salida desde la vista de datos seleccionada y agréguela como un desglose. También puede utilizar cualquier otra dimensión o métrica de interacción (como Página, Acción, etc.) como desglose.
