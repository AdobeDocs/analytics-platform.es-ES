---
title: ¿Qué son los componentes de Customer Journey Analytics?
description: Descubra qué componentes son las ofertas de los Customer Journey Analytics y cómo puede utilizarlas en el sistema de informes.
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1068'
ht-degree: 75%

---

# Resumen de componentes

Los componentes son funciones de Customer Journey Analytics que se pueden utilizar en los informes o pueden complementar las funciones de la creación de informes. Puede administrar estos componentes siguiendo estos pasos:

1. Inicie sesión en [analytics.adobe.com](https://analytics.adobe.com) con sus credenciales de Adobe ID.
2. Vaya a [!UICONTROL Componentes] > [!UICONTROL Componentes] en el menú del encabezado.

Puede administrar los siguientes componentes:

* [**Anotaciones**](/help/components/annotations/overview.md): comunicar matices y perspectivas de datos contextuales a su organización.
* [**Audiencias**](/help/components/audiences/audiences-overview.md): Cree y publique audiencias detectadas en Customer Journey Analytics a [Perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=es) (RTCDP) en Adobe Experience Platform para la segmentación y personalización de clientes.
* [**Filtros**](filters/filters-overview.md): Cree, administre, comparta y aplique filtros de audiencia poderosos y centrados a sus informes. Los filtros le permiten identificar subconjuntos de personas en función de sus características o interacciones.
* [**Métricas calculadas:**](calc-metrics/calc-metr-overview.md) usar las métricas y fórmulas como componentes nuevos para utilizarlas en sistemas de informes
* [**Diccionario de datos**](/help/components/data-dictionary/data-dictionary-overview.md): ayuda a los usuarios y administradores a realizar un seguimiento de los componentes de su entorno de Analytics y a comprenderlos mejor.
* [**Intervalos de fechas**](date-ranges/create.md): personalice y perfeccione los intervalos de fechas que ofrece Analysis Workspace.
* [**Dimension**](/help/components/dimensions/view-dimensions.md): los Dimension son variables que generalmente contienen valores de cadena. Las dimensiones comunes incluyen Página y Dominio de referencia.
* [**Métricas**](/help/components/apply-create-metrics.md): le permite cuantificar los puntos de datos en Analysis Workspace.
* [**Proyectos**](/help/analysis-workspace/home.md): organice y mantenga sus proyectos en Analysis Workspace.

## Componentes de Analysis Workspace

Los componentes de Analysis Workspace están formados por métricas, dimensiones, filtros y granularidades de tiempo que puede arrastrar y soltar en un proyecto. Los componentes personalizados que crea se añaden a estos paneles como, por ejemplo, los intervalos de fecha personalizados.

Para acceder al panel Componentes, haga clic en el icono **[!UICONTROL Componentes]** del carril izquierdo. Puede alternar entre paneles (Panel en blanco, [Panel de forma libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md), [Información rápida](/help/analysis-workspace/c-panels/quickinsight.md), o [Attribution IQ](/help/analysis-workspace/c-panels/attribution.md) panel), [Visualizaciones](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md), y Componentes con los iconos del carril izquierdo o con [métodos abreviados de teclado](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![Panel de Workspace que resalta el icono Componentes en el carril izquierdo](assets/components.png)

Consulte [Crear un proyecto](/help/analysis-workspace/home.md) para obtener información sobre el uso de Componentes en un proyecto.

## Acciones de componente

Puede administrar componentes (de uno en uno o seleccionando más de uno) de diferentes formas. Haga clic con el botón secundario en un componente o haga clic en **[!UICONTROL Acciones]** en la parte superior de la lista de componentes.

>[!NOTE]
>
>Estas acciones no se aplican a los componentes de tiempo.

| Acción de componente | Descripción |
| --- | --- |
| Etiqueta | Organizar o administrar componentes aplicándoles etiquetas. A continuación, se muestra en el administrador de componentes pertinente, como [!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Filtros], o [!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Proyectos] |
| Favorito | Añadir el componente a la lista de favoritos. A continuación, se muestra en el administrador de componentes pertinente, como [!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Filtros], o [!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Proyectos]. |
| Aprobar | Aprobar el componente para hacerlo canónico. A continuación, se muestra en el administrador de componentes pertinente, como [!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Filtros], o [!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Proyectos] |
| Compartir | Solo se aplica a los filtros. |
| Eliminar | Solo se aplica a los filtros. |

Vea el vídeo sobre la creación de métricas, filtros y fechas:

>[!VIDEO](https://video.tv.adobe.com/v/23979)

## Administrar componentes {#actions}

Puede administrar componentes directamente en el carril izquierdo.

1. Haga clic con el botón derecho en un componente.

   o

   Seleccione un componente y a continuación, seleccione el icono de **Acción** (tres puntos) en la parte superior de la lista de componentes.

   >[!TIP]
   >
   >   Para seleccionar varios componentes, mantenga pulsada la tecla Mayús o Comando (en Mac) o Ctrl (en Windows).


   ![Lista de acciones de componente que muestra Etiquetar, Favorito, aprobar, Compartir y Eliminar.](assets/component-actions.png)

   | Acción de componente | Descripción |
   |--- |--- |
   | [!UICONTROL **Etiqueta**] | Organizar o administrar componentes aplicándoles etiquetas. A continuación, puede buscar por etiqueta en el carril izquierdo haciendo clic en el filtro o escribiendo #. Las etiquetas también actúan como filtros en los administradores de componentes. |
   | [!UICONTROL **Favorito**] | Añadir el componente a la lista de favoritos. Al igual que las etiquetas, puede buscar por Favoritos en el carril izquierdo y filtrar con este criterio en los administradores de componentes. |
   | [!UICONTROL **Aprobar**] | Marque los componentes como aprobados para indicar a los usuarios que el componente lo ha aprobado la organización. Al igual que las etiquetas, puede buscar por Aprobado en el carril izquierdo y filtrar con este criterio en los administradores de componentes. |
   | [!UICONTROL **Compartir**] | Comparta componentes con usuarios de su organización. Esta opción solo está disponible para componentes personalizados, como filtros o métricas calculadas. |
   | [!UICONTROL **Eliminar**] | Elimine los componentes que ya no necesite. Esta opción solo está disponible para componentes personalizados, como filtros o métricas calculadas. |

Los componentes personalizados también se pueden administrar a través de sus respectivos administradores de componentes. Por ejemplo, la variable [Administrar filtros](/help/components/filters/manage-filters.md).

## Búsqueda, filtrado y ordenación de la lista de componentes

Puede buscar, filtrar y ordenar la lista de componentes en el carril izquierdo de Analysis Workspace para localizar rápidamente un componente en particular.

### Búsqueda en la lista de componentes

1. Seleccione el icono de **Componentes** ![icono de Componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) en el carril izquierdo.

2. En el campo de búsqueda, empiece a escribir el nombre del componente que desea utilizar en el proyecto.

   El tipo de componente se puede identificar por el color y el icono. **Dimension** ![Icono de Dimension](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) son naranjas, **Filtros** ![Icono de filtro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) son azules, **Intervalos de fechas** ![Icono de intervalo de fecha](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) son morados y **Métricas** ![Icono de métrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) son verdes. El icono Adobe ![Icono de Adobe](assets/default-calc-metric-icon.png) indica una plantilla de métrica calculada o de filtro, y el icono de la calculadora ![Icono Calculadora](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indicó una métrica calculada que creó un administrador de Analytics en su organización.

3. Seleccione el componente cuando aparezca en la lista desplegable.

### Filtrado de la lista de componentes

1. Seleccione el icono de **Componentes** ![icono de Componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) en el carril izquierdo.

2. Seleccione el **Filtrar** icono ![Icono Filtro de diccionario de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)).

   o

   Escriba el símbolo de almohadilla (#) en el campo de búsqueda.

3. Seleccione cualquiera de las siguientes opciones de filtro para filtrar la lista de componentes:

   | Opción | Función |
   |---------|----------|
   | [!UICONTROL **Aprobado**] | Mostrar solo los componentes marcados como Aprobado por un administrador. |
   | [!UICONTROL **Favoritos**] | Mostrar solo los componentes que se encuentran en la lista de Favoritos. Para obtener información sobre cómo agregar componentes a la lista de favoritos, consulte [Administrar componentes](#manage-components). |
   | [!UICONTROL **Dimensiones**] | Mostrar solo los componentes que son dimensiones. |
   | [!UICONTROL **Métricas**] | Mostrar solo los componentes que son métricas. |
   | [!UICONTROL **Filtros**] | Mostrar solo los componentes que son filtros. |
   | [!UICONTROL **Intervalos de fechas**] | Mostrar solo los componentes que son intervalos de fechas. |
   | [!UICONTROL **Mostrar todo**] | Mostrar todos los componentes. Esta opción solo está disponible para administradores. |
   | [!UICONTROL **No aprobado**] | Mostrar solo los componentes que aún no están marcados como Aprobado por un administrador. Como administrador, resulta útil a la hora de identificar los componentes que requieren su revisión y aprobación. Esta opción solo está disponible para administradores. |

4. (Opcional) Para perfeccionar aún más la lista, puede ordenarla, tal como se describe en [Ordenación de la lista de componentes](#sort-the-component-list).

### Ordenación de la lista de componentes

{{release-limited-testing-section}}

1. (Opcional) Aplique cualquier filtro a la lista de componentes, tal como se describe en [Filtrado de la lista de componentes](#filter-the-component-list).

2. Seleccione el icono de **Componentes** ![icono de Componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) en el carril izquierdo.

3. Seleccione el icono de **Ordenar** ![icono de Ordenar componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) y a continuación, seleccione cualquiera de las siguientes opciones de filtro para ordenar la lista de componentes:

   {{components-sort-options}}

## Permisos de acceso a los componentes

En Analysis Workspace, los administradores pueden [revisar](/help/analysis-workspace/curate-share/curate.md) qué componentes se exponen a los usuarios en la creación de informes.
