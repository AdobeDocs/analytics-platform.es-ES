---
description: Aprenda a crear métricas calculadas.
title: Crear métricas calculadas
feature: Calculated Metrics
exl-id: 55ed36c1-99ca-400a-bc2b-661994cbf720
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 13%

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


## Flujo de trabajo

Antes de crear métricas calculadas, tenga en cuenta cuidadosamente el siguiente flujo de trabajo:

| Tarea de flujo de trabajo | Descripción |
| --- | --- |
| Planificar métricas calculadas | Especialmente para las métricas que se van a aprobar oficialmente, la planificación tiene sentido para delinear qué métricas calculadas se utilizarán ampliamente y cómo se definirán. |
| [Generar](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) métricas calculadas | Cree y edite métricas calculadas y métricas calculadas avanzadas para utilizarlas en componentes de [!DNL Customer Journey Analytics].   |
| [Etiquetar](cm-tagging.md) métricas calculadas | Etiquete métricas calculadas para que sea más fácil organizar y compartir. Consulte cómo planificar y asignar etiquetas para la organización y las búsquedas simples y avanzadas. |
| [Aprobar](cm-approving.md) métricas calculadas | Apruebe métricas calculadas para convertirlas en canónicas. |
| Uso de métricas calculadas | Utilice las métricas calculadas en sus proyectos. |
| [Compartir](cm-sharing.md) métricas calculadas | Comparta sus métricas calculadas con otras personas, grupos u organizaciones. |
| [Filtrar](cm-filter.md) métricas calculadas | Filtre las métricas calculadas por etiquetas, propietarios y otros filtros (Mostrar todo, Míos, Compartidos conmigo, Favoritos y Aprobados). |
| Marcar métricas calculadas como [favoritos](cm-finding.md) | Marcar las métricas como favoritas es otra manera de organizarlas para que su uso sea más sencillo. |

