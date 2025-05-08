---
description: Aprenda a crear métricas calculadas.
title: Crear métricas calculadas
feature: Calculated Metrics
exl-id: 55ed36c1-99ca-400a-bc2b-661994cbf720
source-git-commit: c183a5013cbc5ff3765cc4926a308d0c4563a097
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 43%

---

# Crear métricas calculadas

De forma predeterminada, solo los administradores pueden crear métricas calculadas. Los usuarios tienen derechos para ver las métricas calculadas, de forma similar a como ven otros componentes (como segmentos, anotaciones, etc.).

Sin embargo, los administradores pueden dar permiso a **[!UICONTROL Creación de métricas calculadas]** para **[!UICONTROL Herramientas de informes]** en **[!UICONTROL Editar permisos para CJA Workspace Access]** a los usuarios a través de [Admin Console](/help/technotes/access-control.md#user-level-access).


Puede crear una métrica calculada de las siguientes maneras:

![Formas de crear una métrica](assets/create-metric.png)

* **A**. En la interfaz principal, seleccione **[!UICONTROL Componentes]** y seleccione **[!UICONTROL Métricas calculadas]**. Seleccione ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**] del administrador de [[!UICONTROL métricas calculadas]](/help/components/calc-metrics/cm-workflow/cm-manager.md).
* **B**. En un proyecto de Workspace, en el panel izquierdo Componentes, seleccione ![Agregar](/help/assets/icons/Add.svg) en ![Evento](/help/assets/icons/Event.svg) **Métricas**.
* **C**. En un proyecto de Workspace, en el menú contextual del encabezado de la columna Métricas, seleccione **[!UICONTROL Crear métrica a partir de la selección]**. En el submenú, puede seleccionar una función o seleccionar **[!UICONTROL Abrir en el creador de métricas calculadas]**. <br/>Si selecciona una función, la métrica calculada se define como métrica solo de proyecto. Cuando edite posteriormente esta métrica, a través de la ventana emergente [Información del componente](/help/components/use-components-in-workspace.md#component-info), verá una notificación en el [Creador de métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
* **D**. En un proyecto de Workspace, seleccione **[!UICONTROL Componentes]** en el menú y seleccione **[!UICONTROL Crear métrica]**.
* **E**. En un proyecto de Workspace, use el acceso directo **[!UICONTROL mayús+cmd+c]** (macOS) o **[!UICONTROL mayús+ctrl+c]** (Windows).

Para definir la nueva métrica calculada, usa el [Creador de métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

Obtenga información sobre los pasos a seguir para crear métricas calculadas.

| Tarea del flujo de trabajo | Descripción |
| --- | --- |
| Planificar métricas calculadas | Especialmente en el caso de las métricas que se “aprobarán” oficialmente, tiene sentido detallar qué métricas calculadas se utilizarán de forma generalizada y cómo se definirán. |
| [Crear](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) métricas calculadas | Cree y edite métricas calculadas y métricas calculadas avanzadas para utilizarlas en componentes de [!DNL Customer Journey Analytics].   |
| [Etiquetar](cm-tagging.md) métricas calculadas | Etiquete métricas calculadas para que sea más fácil organizar y compartir. Consulte cómo planificar y asignar etiquetas para la organización y las búsquedas simples y avanzadas. |
| [Aprobar](cm-approving.md) métricas calculadas | Apruebe métricas calculadas para hacerlas canónicas. |
| Aplicar métricas calculadas | Puede aplicar métricas directamente desde un informe, desde el Selector de métricas (para acceder a él, haga clic en [!UICONTROL Mostrar métricas]). |
| Filtrar métricas calculadas | En el selector de métricas, haga clic en [!UICONTROL Selección avanzada] y filtre por etiquetas, propietarios y otros filtros (Mostrar todo, Mío, Compartido conmigo, Favoritos y Aprobado). |
| Marcar una métrica calculada como [favorita](cm-finding.md) | Marcar las métricas como favoritas es otra manera de organizarlas para que su uso sea más sencillo. |

