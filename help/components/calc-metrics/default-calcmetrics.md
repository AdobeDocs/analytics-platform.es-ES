---
description: Adobe proporciona varias métricas calculadas que puede utilizar. Esta página enumera dichas métricas y los usos a los que están destinadas.
title: Plantillas de métricas calculadas
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: d37734ae415722fc609715868c37a36f2becdbf6
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 8%

---

# Plantillas de métricas calculadas

Customer Journey Analytics proporciona las siguientes plantillas de métricas calculadas para cubrir los casos de uso más comunes. Estas métricas calculadas definidas por el Adobe se identifican con un pequeño logotipo de ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg). Para filtrar rápidamente estas métricas, seleccione ![Etiqueta](/help/assets/icons/Label.svg) **[!UICONTROL Plantilla de Adobe]** en el filtro [Componentes](/help/components/overview.md#filter).

| Nombre de métrica calculada | Descripción<br/>Fórmula |
|---------|----------|
| **[!UICONTROL Tasa de inicio de sesión]** | El porcentaje en el que se produjo cualquier elemento de dimensión en el primer evento de una sesión.<p>Esta métrica calculada se agrega automáticamente a Workspace al incluir [!UICONTROL Inicio de sesión] [componente estándar](/help/data-views/component-reference.md) en su [vista de datos](/help/data-views/create-dataview.md).</p>Resumen: **(** ![Evento](/help/assets/icons/Event.svg) **Inicio de sesión** ![Dividir](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Sesiones** **)** |
| **[!UICONTROL Tiempo empleado por persona]** | Promedio de tiempo que una persona ha invertido en un elemento de dimensión determinado.<p>Esta métrica calculada se agrega automáticamente a Workspace cuando se incluye el [!UICONTROL Tiempo empleado (segundos)] [componente estándar](/help/data-views/component-reference.md) en la [vista de datos](/help/data-views/create-dataview.md). El filtro Excluir el último evento de la sesión se aplica a la métrica Personas. El filtro excluye el último evento de cada sesión en un conjunto de datos. Esta exclusión puede ayudarle a analizar el comportamiento del usuario antes de un evento o una acción, como una compra o un envío de formulario, mientras excluye la acción final en sí.</p>Resumen: **(** ![Evento](/help/assets/icons/Event.svg) **Tiempo empleado (segundos)** ![Dividir](/help/assets/icons/Divide.svg) ![Segmentación](/help/assets/icons/Segmentation.svg) **Excluir el último evento de la sesión(** ![Evento](/help/assets/icons/Event.svg) **Personas )** |
| **[!UICONTROL Sesiones por persona]** | Número promedio de sesiones por persona.<p>Resumen: **(** ![Evento](/help/assets/icons/Event.svg) **Sesiones** ![Dividir](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Personas** **)** |
| **[!UICONTROL Tiempo empleado por sesión]** | Promedio de tiempo que una persona ha invertido por sesión en un elemento de dimensión determinado.<p>Esta métrica calculada se agrega automáticamente a Workspace cuando se incluye el [!UICONTROL Tiempo empleado (segundos)] [componente estándar](/help/data-views/component-reference.md) en la [vista de datos](/help/data-views/create-dataview.md). El filtro Excluir el último evento de la sesión se aplica a la métrica Sesiones. El filtro excluye el último evento de cada sesión en un conjunto de datos. Esta exclusión puede ayudarle a analizar el comportamiento del usuario antes de un evento o una acción, como una compra o un envío de formulario, mientras excluye la acción final en sí.</p>Resumen: **(** ![Evento](/help/assets/icons/Event.svg) **Tiempo empleado (segundos)** ![Dividir](/help/assets/icons/Divide.svg) ![Segmentación](/help/assets/icons/Segmentation.svg) **Excluir el último evento de la sesión(** ![Evento](/help/assets/icons/Event.svg) **Sesiones )** |
| **[!UICONTROL Tasa de finalización de la sesión]** | El porcentaje en el que se produjo cualquier elemento de dimensión en el último evento de una sesión. <p>Esta métrica calculada se agrega automáticamente a Workspace cuando se incluye [!UICONTROL Fin de sesión] [componente estándar](/help/data-views/component-reference.md) en la [vista de datos](/help/data-views/create-dataview.md).</p>Resumen: **(** ![Evento](/help/assets/icons/Event.svg) **Fin de sesión** ![Dividir](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Sesiones** **)** |

{style="table-layout:auto"}
