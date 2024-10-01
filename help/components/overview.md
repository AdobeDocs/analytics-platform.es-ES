---
title: ¿Qué son los componentes de Customer Journey Analytics?
description: Aprenda qué componentes ofrece Customer Journey Analytics y cómo puede utilizarlos en el sistema de informes.
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
role: User
source-git-commit: e07197325e992cd85b852899c2f7cef60637f532
workflow-type: tm+mt
source-wordcount: '923'
ht-degree: 33%

---

# Información general de componentes

Los componentes son funciones de Customer Journey Analytics que se pueden utilizar en visualizaciones (como la tabla de forma libre) o para complementar las funciones de creación de informes.

Para administrar componentes desde la interfaz de Customer Journey Analytics principal:

1. Seleccione **[!UICONTROL Componentes]** en la barra superior.
1. Seleccione **[!UICONTROL Componentes]** para ver una descripción general de los componentes que puede administrar o seleccione directamente el componente que desee administrar en el menú.

Puede administrar los siguientes componentes:

* [Filtros](filters/filters-overview.md): cree, gestione, comparta y aplique filtros de público eficaces y centrados a sus informes de Analytics. Los filtros le permiten identificar subconjuntos de personas basándose en sus características o en las interacciones.
* [Métricas calculadas:](calc-metrics/calc-metr-overview.md) usar las métricas y fórmulas como componentes nuevos para utilizarlas en sistemas de informes
* [Intervalos de fechas:](date-ranges/create.md) personalice y especifique las ofertas de Analysis Workspace en los intervalos de fechas.
* [Anotaciones](/help/components/annotations/overview.md): comunicar matices y perspectivas de datos contextuales a su organización.
* [Alertas inteligentes](/help/components/c-intelligent-alerts/intelligent-alerts.md): permiten recibir notificaciones basadas en porcentajes modificados o puntos de datos específicos.
* [Proyectos programados](/help/analysis-workspace/export/t-schedule-report.md#scheduled-projects-manager): administre sus proyectos programados.
* [Preferencias](/help/analysis-workspace/user-preferences.md): administre las preferencias de Analysis Workspace.
* [Audiencias](/help/components/audiences/audiences-overview.md): cree y publique audiencias del Customer Journey Analytics a [Real-time Customer Data Platform](https://experienceleague.adobe.com/en/docs/experience-platform/profile/home) en el Experience Platform para segmentar y personalizar.
* [Exportaciones](/help/components/exports/manage-export-locations.md): administre su cuenta y ubicaciones de exportación.


## Componentes de Analysis Workspace

Los componentes de Analysis Workspace están formados por métricas, dimensiones, filtros e intervalos de fechas que puede arrastrar y soltar en paneles y visualizaciones de su proyecto de Workspace. Los componentes personalizados que crea se añaden a estos paneles como, por ejemplo, una métrica calculada o un intervalo de fechas personalizado.

Para acceder al panel Componentes, seleccione ![Depurar](/help/assets/icons/Curate.svg) **[!UICONTROL Componentes]** en el panel de botones.

![Panel de Workspace que resalta el icono Componentes en el carril izquierdo](assets/components.png)

Consulte [Crear un proyecto](/help/analysis-workspace/home.md) para obtener información sobre cómo usar componentes en un proyecto.


+++ Vea un vídeo que muestra las posibilidades de los componentes:

>[!VIDEO](https://video.tv.adobe.com/v/23979)

+++

## Administrar componentes {#actions}

Puede crear rápidamente un nuevo componente con el menú **[!UICONTROL Componentes]** de Analysis Workspace. Consulte el [menú de Analysis Workspace](/help/analysis-workspace/home.md#menu) para obtener más información.

Puede administrar componentes (de forma individual o seleccionando más de uno).

1. Seleccione uno o varios componentes.

1. En el menú contextual o en el botón de acciones del componente ![MásVertical](/help/assets/icons/MoreVertical.svg) (en la parte superior de Componentes), seleccione una de las siguientes acciones.


   >[!TIP]
   >
   >Para seleccionar varios componentes, mantenga presionada la tecla **[!UICONTROL Mayús]**, mantenga presionada la tecla **[!UICONTROL Comando]** (en macOS) o la tecla **[!UICONTROL Ctrl]** (en Windows).


   ![Lista de acciones de componente que muestra Etiquetar, Favorito, aprobar, Compartir y Eliminar.](assets/component-menu.gif){width=100%}

   | Acción de componente | Descripción |
   |--- |--- |
   | ![Etiqueta](/help/assets/icons/Label.svg) [!UICONTROL **Etiqueta**] | Organizar o administrar componentes aplicándoles etiquetas. Luego puede buscar por etiqueta en el panel izquierdo seleccionando el filtro ![Filter](/help/assets/icons/Filter.svg) o escribiendo `#`. Las etiquetas también actúan como filtros en los administradores de componentes. |
   | ![Estrella](/help/assets/icons/Star.svg) [!UICONTROL **Favorita**] | Añadir el componente a la lista de favoritos. Al igual que las etiquetas, puede buscar por Favoritos en el panel izquierdo y filtrar con este criterio en los administradores de componentes. |
   | ![EsquemaEstrella](/help/assets/icons/StarOutline.svg) **[!UICONTROL No favorito]** | Elimine el componente de la lista de favoritos. |
   | ![Marca de verificación](/help/assets/icons/Checkmark.svg) [!UICONTROL **Aprobar**] | Marque los componentes como aprobados para indicar a los usuarios que el componente lo ha aprobado la organización. Al igual que las etiquetas, puede buscar y filtrar por Aprobado en el panel izquierdo. Una ![marca de verificación](/help/assets/icons/Checkmark.svg) identifica los componentes aprobados. |
   | ![Compartir](/help/assets/icons/ShareLight.svg) [!UICONTROL **Compartir**] | Comparta componentes con usuarios de su organización. Esta opción solo está disponible para componentes personalizados, como filtros o métricas calculadas. |
   | ![Eliminar](/help/assets/icons/Delete.svg) [!UICONTROL **Eliminar**] | Elimine los componentes que ya no necesite. Esta opción solo está disponible para componentes personalizados, como filtros o métricas calculadas. |

Los componentes personalizados también se pueden administrar a través de sus respectivos administradores de componentes. Por ejemplo, vea [Administrar filtros](/help/components/filters/manage-filters.md).

## Administrar la lista de componentes

Puede buscar, filtrar y ordenar la lista de componentes en el panel izquierdo de Analysis Workspace para localizar un componente en particular.

### Buscar

1. Seleccione **Componentes** ![Icono de componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) en el panel izquierdo.

2. En el campo de búsqueda, empiece a escribir el nombre del componente que desea utilizar en el proyecto.

   El color y el icono identifican el tipo de componente. **Icono de Dimension** ![Dimension](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) es naranja, **Filtros** ![Icono de filtro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) es azul, **Intervalos de fecha** ![Icono de intervalo de fecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) es púrpura y **Métricas** ![Icono de métrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) es verde.<br/>El icono de Adobe ![AdobeLogo](/help/assets/icons/AdobeLogoSmall.svg) indica una plantilla de métrica calculada o una plantilla de filtro. El icono de la calculadora ![Icono de la calculadora](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indica una métrica calculada que ha creado un administrador de su organización.

3. Seleccione el componente en la lista desplegable.

### Filtro

1. Seleccione el icono **Componentes** ![Icono de componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) en el panel izquierdo.

2. Seleccione **Filtro** ![icono del filtro del diccionario de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) o escriba `#` en el campo de búsqueda.

3. Seleccione cualquiera de las siguientes opciones de filtro para filtrar la lista de componentes:

   | Icono | Opción de filtro | Descripción |
   |---------|---|----------|
   | ![Marca de verificación](/help/assets/icons/Checkmark.svg) | **[!UICONTROL Aprobado]** | Mostrar solo los componentes marcados como Aprobado por un administrador. |
   | ![Estrella](/help/assets/icons/Star.svg) | **[!UICONTROL Favoritos]** | Mostrar solo los componentes que se encuentran en la lista de Favoritos. <br/>Para obtener información sobre cómo agregar componentes a su lista de favoritos, consulte [Administrar componentes](#manage-components). |
   | ![Dimensiones](/help/assets/icons/Dimensions.svg) | **[!UICONTROL Dimensiones]** | Mostrar solo los componentes que son dimensiones. |
   | ![Evento](/help/assets/icons/Event.svg) | **[!UICONTROL Métricas]** | Mostrar solo los componentes que son métricas. |
   | ![Segmentación](/help/assets/icons/Segmentation.svg) | **[!UICONTROL Filtros]** | Mostrar solo los componentes que son filtros.  |
   | ![Calendario](/help/assets/icons/Calendar.svg) | **[!UICONTROL Intervalos de fechas]** | Mostrar solo los componentes que son intervalos de fechas. |
   | ![Etiqueta](/help/assets/icons/Label.svg) | **[!UICONTROL *Nombre de etiqueta *]** | Mostrar solo los componentes con las etiquetas seleccionadas específicas. Hay disponible una etiqueta específica para la plantilla de Adobe, que son las [métricas calculadas predeterminadas](/help/components/calc-metrics/default-calcmetrics.md) de la Adobe. |

   Seleccione ![CrossSize75](/help/assets/icons/CrossSize75.svg) en un filtro para quitar el filtro.

4. Si lo desea, puede ordenar la lista de componentes, tal como se describe en [Ordenar la lista de componentes](#sort-the-component-list).

### Ordenar

<!-- {{release-limited-testing-section}}-->

1. (Opcional) Aplique cualquier filtro a la lista de componentes, tal como se describe en [Filtrado de la lista de componentes](#filter-the-component-list).

2. Seleccione **Componentes** ![Icono de componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) en el panel izquierdo.

3. Seleccione **Ordenar** ![Icono de ordenar componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) y, a continuación, seleccione cualquiera de las siguientes opciones de filtro para ordenar la lista de componentes.

Estas son las opciones de ordenación disponibles:

{{components-sort-options}}

## Permisos de acceso

En Analysis Workspace, los administradores pueden [revisar](/help/analysis-workspace/curate-share/curate.md) qué componentes se exponen a los usuarios en los informes.
