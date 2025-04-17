---
description: Adobe proporciona varias métricas calculadas que puede utilizar. En esta página se enumeran dichas métricas y los usos previstos.
title: Plantillas de métricas calculadas
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: d13f980d1fbae3f608bf64587f59dc22c3fac9ce
workflow-type: ht
source-wordcount: '547'
ht-degree: 100%

---

# Plantillas de métricas calculadas

Customer Journey Analytics proporciona las siguientes plantillas de métricas calculadas para cubrir los casos de uso más habituales Estas métricas calculadas definidas por Adobe se identifican con un pequeño logotipo ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg). Para filtrar rápidamente estas métricas, seleccione ![Etiqueta](/help/assets/icons/Label.svg) **[!UICONTROL Plantilla de Adobe]** en el [filtro Componentes](/help/components/overview.md#filter).

| Nombre de métrica calculada | Descripción<br/>Fórmula |
|---------|----------|
| **[!UICONTROL Tasa de inicio de sesión]** | Porcentaje con el que se produjo cualquier elemento de dimensión en el primer evento de una sesión.<p>Esta métrica calculada se añade automáticamente a Workspace al incluir [!UICONTROL Inicios de sesión] [componente estándar](/help/data-views/component-reference.md) en su [vista de datos](/help/data-views/create-dataview.md).</p>Resumen: **(** ![Evento](/help/assets/icons/Event.svg) **Inicios de sesión** ![Dividir](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Sesiones** **)** |
| **[!UICONTROL Tiempo empleado por persona]** | Promedio de tiempo que una persona ha invertido en un elemento de dimensión determinado.<p>Esta métrica calculada se añade automáticamente a Workspace cuando se incluye el [!UICONTROL Tiempo empleado (segundos)] [componente estándar](/help/data-views/component-reference.md) en la [vista de datos](/help/data-views/create-dataview.md). El filtro Excluir el último evento de la sesión se aplica a la métrica Personas. El filtro excluye el último evento de cada sesión en un conjunto de datos. Esta exclusión puede ayudarle a analizar el comportamiento del usuario previo a un evento o acción, como una compra o el envío de formulario, al tiempo que excluye la acción final en sí.</p>Resumen: **(** ![Evento](/help/assets/icons/Event.svg) **Tiempo empleado (segundos)** ![Dividir](/help/assets/icons/Divide.svg) ![Segmentación](/help/assets/icons/Segmentation.svg) **Excluir el último evento de la sesión(** ![Evento](/help/assets/icons/Event.svg) **Personas**)) |
| **[!UICONTROL Sesiones por persona]** | Número medio de sesiones por persona.<p>Resumen: **(** ![Evento](/help/assets/icons/Event.svg) **Sesiones** ![Dividir](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Personas** **)** |
| **[!UICONTROL Tiempo empleado por sesión]** | Promedio de tiempo que una persona ha invertido por sesión en un elemento de dimensión determinado.<p>Esta métrica calculada se añade automáticamente a Workspace cuando se incluye el [!UICONTROL Tiempo empleado (segundos)] [componente estándar](/help/data-views/component-reference.md) en la [vista de datos](/help/data-views/create-dataview.md). El filtro Excluir el último evento de la sesión se aplica a la métrica Sesiones. El filtro excluye el último evento de cada sesión en un conjunto de datos. Esta exclusión puede ayudarle a analizar el comportamiento del usuario previo a un evento o acción, como una compra o el envío de formulario, al tiempo que excluye la acción final en sí.</p>Resumen: **(** ![Evento](/help/assets/icons/Event.svg) **Tiempo empleado (segundos)** ![Dividir](/help/assets/icons/Divide.svg) ![Segmentación](/help/assets/icons/Segmentation.svg) **Excluir el último evento de la sesión(** ![Evento](/help/assets/icons/Event.svg) **Sesiones**)) |
| **[!UICONTROL Tasa de finalización de sesión]** | Porcentaje con el que se produjo cualquier elemento de dimensión en el último evento de una sesión. <p>Esta métrica calculada se añade automáticamente a Workspace cuando se incluye [!UICONTROL Finalizaciones de de sesión] [componente estándar](/help/data-views/component-reference.md) en la [vista de datos](/help/data-views/create-dataview.md).</p>Resumen: **(** ![Evento](/help/assets/icons/Event.svg) **Finalizaciones de sesión** ![Dividir](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **Sesiones** **)** |
| **[!UICONTROL Sesiones web]** | El número de sesiones que se han producido en el sitio web. |
| **[!UICONTROL Tasa de finalización de encuesta]** | Con qué frecuencia las personas han completado una encuesta después de iniciarla. |
| **[!UICONTROL Tasa de sesión multicanal]** | La proporción de sesiones que se produjeron y que incluían varios canales (como tráfico web y tráfico móvil) frente a las que incluían un solo canal. |
| **[!UICONTROL Tasa por persona multicanal]** | La proporción de personas que han participado en varios canales, en comparación con aquellas que solo han participado en un único canal. |
| **[!UICONTROL Sesiones de la aplicación móvil]** | El número de sesiones que se produjeron en la aplicación móvil. |
| **[!UICONTROL Sesiones en canales múltiples web+aplicación]** | El número de sesiones que se produjeron y que incluían tráfico web y tráfico móvil. |
| **[!UICONTROL Coste de las llamadas]** | El coste total de las llamadas al centro de llamadas. <!-- <p>Summary: Call length</p> --> |
| **[!UICONTROL Duración media de las llamadas]** | Duración media de las llamadas realizadas al centro de llamadas. |
| **[!UICONTROL Coste medio por llamada]** | El coste medio de las llamadas realizadas al centro de llamadas. |
| **[!UICONTROL Puntuación de la encuesta dsobre llamadas]** | Puntuación media de la encuesta sobre las llamadas realizadas al centro de llamadas. |

{style="table-layout:auto"}
