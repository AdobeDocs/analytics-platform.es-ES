---
title: Información general de componentes
description: Aprenda qué componentes ofrece Adobe Analytics y cómo puede utilizarlos en Analysis Workspace.
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
role: User
TQID: https://experienceleague.adobe.com/91yF4rq5CqbAtgfY9X31FmgiCynSJFHaNF1KKsKDycg
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
  - id: df28738e-9c71-4aa8-929e-edde22340cc6
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
  - id: e4a0bad2-b448-47f1-9fa6-222ebdb3b5b0
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 972
ht-degree: 100%

---

# Información general de componentes

Los componentes son funciones de Customer Journey Analytics que se pueden utilizar en las visualizaciones (como tabla de forma libre) o pueden complementar las funciones de informes.

Para administrar componentes desde la interfaz principal de Customer Journey Analytics.

1. Seleccione **[!UICONTROL Credenciales]** en la barra superior.
1. Seleccione **[!UICONTROL Componentes]** para ver una descripción general de los componentes que puede administrar o seleccionar directamente el componente que desea administrar en el menú.

Puede administrar los siguientes componentes:

* [Segmentos](segments/seg-overview.md): cree, gestione, comparta y aplique segmentos de público potentes y específicos a sus informes. Los segmentos le permiten identificar subconjuntos de personas basándose en sus características o en las interacciones.
* [Métricas calculadas:](calc-metrics/calc-metr-overview.md) usar las métricas y fórmulas como componentes nuevos para utilizarlas en sistemas de informes
* [Intervalos de fechas:](date-ranges/create.md) personalice y especifique las ofertas de Analysis Workspace en los intervalos de fechas.
* [Anotaciones](/help/components/annotations/overview.md): comunicar matices y perspectivas de datos contextuales a su organización.
* Las [alertas inteligentes](/help/components/c-intelligent-alerts/intelligent-alerts.md) permiten recibir notificaciones basadas en porcentajes modificados o puntos de datos específicos.
* [Proyectos programados](/help/analysis-workspace/export/t-schedule-report.md#scheduled-projects-manager): administre sus proyectos programados.
* [Preferencias](/help/analysis-workspace/user-preferences.md): administre las preferencias de Analysis Workspace.
* [Públicos](/help/components/audiences/audiences-overview.md): crea y publica públicos que hayas descubierto en Customer Journey Analytics para el [Perfil del cliente en tiempo real](https://experienceleague.adobe.com/es/docs/experience-platform/profile/home) en Adobe Experience Platform para la segmentación y personalización de clientes.
* [Exportaciones](/help/components/exports/manage-export-locations.md): administra tu cuenta de exportación y ubicaciones.


## Componentes de Analysis Workspace

Los componentes de Analysis Workspace están formados por métricas, dimensiones, segmentos y granularidades de tiempo que puedes arrastrar y soltar en un proyecto del espacio de trabajo. Los componentes personalizados que creas se añaden a estos paneles como, por ejemplo, la métrica calculada o los intervalos de fecha personalizados.

Para acceder al panel Componentes, selecciona ![Depurar](/help/assets/icons/Curate.svg) **[!UICONTROL Componentes]** en el panel Botón.

![Panel de Workspace que resalta el icono Componentes en el carril izquierdo](assets/components.png)

Consulta [Crear un proyecto](/help/analysis-workspace/home.md) para obtener información sobre el uso de Componentes en un proyecto.


## Administrar componentes {#actions}

Puedes crear rápidamente un nuevo componente con el menú **[!UICONTROL Componentes]** de Analysis Workspace. Consulta el [menú de Analysis Workspace](/help/analysis-workspace/home.md#menu) para obtener más información.

Puedes administrar componentes (de forma individual o seleccionando más de uno).

1. Selecciona uno o más componentes.

1. En el menú contextual o en el botón de acciones del componente ![MoreVertical](/help/assets/icons/MoreVertical.svg) (en la parte superior de Componentes), selecciona una de las siguientes acciones.


   >[!TIP]
   >
   >Para seleccionar varios componentes, mantén pulsada **[!UICONTROL Mayús]**, o manteniendo pulsado **[!UICONTROL Comando]** (en macOS) o **[!UICONTROL Ctrl]** (en Windows).


   ![Lista de acciones del componente que muestra Etiquetar, Favorito, aprobar, Compartir y Eliminar.](assets/component-menu.gif){width=100%}

   | Acción de componente | Descripción |
   |--- |--- |
   | ![Etiqueta](/help/assets/icons/Label.svg) [!UICONTROL **Etiqueta**] | Organizar o administrar componentes aplicándoles etiquetas. A continuación, puedes buscar por etiqueta en el panel izquierdo haciendo clic en ![Filtro](/help/assets/icons/Filter.svg) o escribiendo `#`. Las etiquetas también actúan como filtros en los administradores de componentes. |
   | ![Estrella](/help/assets/icons/Star.svg) [!UICONTROL **Favorito**] | Añadir el componente a la lista de favoritos. Al igual que las etiquetas, puedes buscar por Favoritos en el panel izquierdo y filtrar con este criterio en los administradores de componentes. |
   | ![EsquemaEstrella](/help/assets/icons/StarOutline.svg) **[!UICONTROL No favorito]** | Eliminar el componente de la lista de favoritos. |
   | ![Marca de verificación](/help/assets/icons/Checkmark.svg) [!UICONTROL **Aprobar**] | Marque los componentes como aprobados para indicar a los usuarios que el componente lo ha aprobado la organización. Al igual que las etiquetas, puedes buscar y filtrar por Aprobado en el panel izquierdo. Una ![marca de verificación](/help/assets/icons/Checkmark.svg) identifica los componentes aprobados. |
   | ![Compartir](/help/assets/icons/ShareAlt.svg) [!UICONTROL **Compartir**] | Comparta componentes con usuarios de su organización. Esta opción solo está disponible para componentes personalizados, como segmentos o métricas calculadas. |
   | ![Eliminar](/help/assets/icons/Delete.svg) [!UICONTROL **Eliminar**] | Elimine los componentes que ya no necesite. Esta opción solo está disponible para componentes personalizados, como segmentos o métricas calculadas. |

Los componentes personalizados también se pueden administrar a través de sus respectivos administradores de componentes. Por ejemplo, consulte [Administrar segmentos](/help/components/segments/seg-manage.md).

## Administrar la lista de componentes

Puedes buscar, filtrar y ordenar la lista de componentes en el panel izquierdo de Analysis Workspace para localizar rápidamente un componente en particular.

### Buscar

1. Selecciona **Componentes** ![icono de Componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) en el panel izquierdo.

2. En el campo de búsqueda, empiece a escribir el nombre del componente que desea utilizar en el proyecto.

   Un color y el icono identifican el tipo de componente. Las **dimensiones** ![icono de Dimensión](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) son de color naranja, los **segmentos** ![icono de Segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) son azules, los **intervalos de fechas** ![icono de Intervalo de fechas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) son morados y las **métricas** ![icono de Métrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) son verdes.<br/>El icono de Adobe ![AdobeLogo](/help/assets/icons/AdobeLogoSmall.svg) indica una plantilla de métrica calculada o una plantilla de segmento. El icono de la calculadora ![Icono de la calculadora](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indica una métrica calculada que ha creado un administrador de tu organización.

3. Seleccione el componente en el menú desplegable.

### Filtro

1. Selecciona el icono de **Componentes** ![icono de Componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) en el panel izquierdo.

2. Selecciona el **Filtro** ![icono del filtro del diccionario de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) o escribe `#` en el campo de búsqueda.

3. Seleccione cualquiera de las siguientes opciones de filtro para filtrar la lista de componentes:

   | Icono | Opción de filtro | Descripción |
   |---------|---|----------|
   | ![Marca de verificación](/help/assets/icons/Checkmark.svg) | **[!UICONTROL Aprobado]** | Mostrar solo los componentes marcados como Aprobado por un administrador. |
   | ![Star](/help/assets/icons/Star.svg) | **[!UICONTROL Favoritos]** | Mostrar solo los componentes que se encuentran en la lista de Favoritos. <br/>Para obtener información sobre cómo añadir componentes a la lista de favoritos, consulta[Información general sobre componentes](#manage-components). |
   | ![Dimensiones](/help/assets/icons/Dimensions.svg) | **[!UICONTROL Dimensiones]** | Mostrar solo los componentes que son dimensiones. |
   | ![Evento](/help/assets/icons/Event.svg) | **[!UICONTROL Métricas]** | Mostrar solo los componentes que son métricas. |
   | ![Segmentación](/help/assets/icons/Segmentation.svg) | **[!UICONTROL Segmentos]** | Mostrar solo los componentes que son segmentos. |
   | ![Calendario](/help/assets/icons/Calendar.svg) | **[!UICONTROL Intervalos de fechas]** | Mostrar solo los componentes que son intervalos de fechas. |
   | ![Etiqueta](/help/assets/icons/Label.svg) | **[!UICONTROL *Nombre de etiqueta *]** | Mostrar solo los componentes con las etiquetas seleccionadas específicas. Hay disponible una etiqueta específica para la plantilla de Adobe, que son las [métricas calculadas predeterminadas](/help/components/calc-metrics/default-calcmetrics.md) de Adobe. |

   Selecciona ![CrossSize75](/help/assets/icons/CrossSize75.svg) en un filtro para quitar el filtro.

4. Si lo deseas, puedes ordenar la lista de componentes, tal como se describe en [Ordenar la lista de componentes](#sort-the-component-list).

### Ordenar

<!-- {{release-limited-testing-section}}-->

1. (Opcional) Aplique cualquier filtro a la lista de componentes, tal como se describe en [Filtrado de la lista de componentes](#filter-the-component-list).

2. Selecciona el icono de **Componentes** ![icono de Componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) en el panel izquierdo.

3. Selecciona el icono de **Ordenar** ![icono de Ordenar componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), y a continuación, selecciona cualquiera de las siguientes opciones de filtro para ordenar la lista de componentes.

Las opciones de clasificación disponibles son las siguientes:

{{components-sort-options}}

## Acceder a permisos

En Analysis Workspace, los administradores pueden[depurar](/help/analysis-workspace/curate-share/curate.md) qué componentes se exponen a los usuarios en la creación de informes.
