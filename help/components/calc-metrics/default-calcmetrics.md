---
description: Adobe proporciona varias métricas calculadas que puede utilizar. Esta página enumera dichas métricas y los usos a los que están destinadas.
title: Métricas calculadas predeterminadas
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
source-git-commit: 5e69b1aceb767343882b9cc85c0011bb1593f4af
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 25%

---

# Métricas calculadas predeterminadas

Customer Journey Analytics proporciona las siguientes métricas calculadas para cubrir los casos de uso más comunes:

| Nombre de métrica calculada | Descripción | Fórmula |
|---------|----------|---------|
| Tasa de inicio de sesión | El porcentaje en el que se produjo cualquier elemento de dimensión en el primer evento de una sesión.<p>Esta métrica calculada se añade automáticamente al espacio de trabajo al incluir el `[Session Starts]` [componente estándar](/help/data-views/component-reference.md) en su [vista de datos](/help/data-views/create-dataview.md).</p> | `[Session Starts] / [Sessions]` |
| Tiempo empleado por persona | Promedio de tiempo que una persona ha invertido en un elemento de dimensión determinado.<p>Esta métrica calculada se añade automáticamente al espacio de trabajo al incluir el `[Time Spent (seconds)]` [componente estándar](/help/data-views/component-reference.md) en su [vista de datos](/help/data-views/create-dataview.md).</p> | `[Time Spent (seconds)] / [Users]` |
| Sesiones por persona | Número promedio de sesiones por persona. | `[Sessions] / [Users]` |
| Tiempo empleado por sesión | Promedio de tiempo que una persona ha invertido por sesión en un elemento de dimensión determinado.<p>Esta métrica calculada se añade automáticamente al espacio de trabajo al incluir el `[Time Spent (seconds)]` [componente estándar](/help/data-views/component-reference.md) en su [vista de datos](/help/data-views/create-dataview.md).</p> | `[Time Spent (seconds)] / [Sessions]` |
| Tasa de finalización de sesión | El porcentaje en el que se produjo cualquier elemento de dimensión en el último evento de una sesión. <p>Esta métrica calculada se añade automáticamente al espacio de trabajo al incluir el `[Session Ends]` [componente estándar](/help/data-views/component-reference.md) en su [vista de datos](/help/data-views/create-dataview.md).</p> | `[Session Ends] / [Sessions]` |

{style="table-layout:auto"}
