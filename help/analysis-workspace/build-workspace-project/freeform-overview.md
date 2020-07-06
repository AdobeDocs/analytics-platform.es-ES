---
description: 'null'
keywords: Analysis Workspace
title: 'Creación de un proyecto: Resumen'
topic: Reports and analytics
uuid: a68be05d-f31e-4e6d-ad04-c784ecb0eb00
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 96%

---


# Creación de un proyecto: Resumen

>[!NOTE]
>
>Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

**[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**

Puede crear un proyecto de Analytics robusto basado en cualquier combinación de visualizaciones, componentes de informe y tablas de datos. Incorpora muchas de las características del generador de tablas de Ad Hoc Analysis en Analytics.

En Analysis Workspace, puede comparar y diseccionar datos de formas en las que anteriormente no era posible. Por ejemplo, configurar informes de clasificación y realizar cambios reiterados en las consultas de datos y, a continuación, acceder y manipular los valores en el nivel de informe.

La consulta va directamente al motor de búsqueda (puede realizar cambios en línea sin abrir otros informes para crear el análisis). Los resultados se devuelven de forma inmediata sin que se actualice el explorador.

## Página de lista de proyectos de Workspace {#section_39AA007D7C384F4E869F842F1C7B11F8}

La primera vez que acceda a **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**, la página muestra todos los proyectos que posee o a los que se le ha otorgado acceso. Puede establecer esta página como página de aterrizaje de Adobe Analytics. Para ello, haga clic en **[!UICONTROL Establecer como página de aterrizaje]**. (si no ve esta opción, como en la captura de pantalla que aparece a continuación, significa que ya es su página de aterrizaje).

![](assets/sample-project.png)

La lista de proyectos de Workspace contiene la siguiente información:

| Elemento | Descripción |
|---|---|
| Proyecto [Plantillas](/help/analysis-workspace/build-workspace-project/starter-projects.md) | Puede utilizar estas plantillas de proyecto rellenadas previamente tal cual, o puede adaptarlas a sus necesidades (mediante la adición o sustitución de métricas o visualizaciones, por ejemplo) y guardarlas con un nuevo nombre. |
| [Crear nuevo proyecto](/help/analysis-workspace/home.md) | Haga clic en este vínculo para iniciar un proyecto nuevo desde cero. |
| Administrar proyectos | Al hacer clic en este vínculo, accederá al administrador de componentes de proyectos ( **[!UICONTROL Analytics]** > **[!UICONTROL Componentes]** > **[!UICONTROL Proyectos]**), que muestra todos sus proyectos y le permite etiquetar, compartir, eliminar, cambiar el nombre, aprobar, copiar y exportar proyectos a CSV. |
| Ver tutoriales | Le permite acceder a los [vídeos en YouTube de Analysis Workspace](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS). |
| Nombre | Nombre del proyecto de Workspace. |
| Creado por | Persona que ha creado el proyecto (usted mismo o alguien que haya compartido su proyecto). |
| Etiquetas | Etiquetas aplicadas al proyecto, ya sea en el administrador de componentes de proyectos o en **[!UICONTROL Workspace]** > **[!UICONTROL Proyecto]** > **[!UICONTROL Información y configuración del proyecto]**. |
| Última modificación | Fecha y hora de última modificación del proyecto. |

## Info y configuración del proyecto {#section_63773D0B9E4543E88068ECECB9EEB4C6}

**[!UICONTROL Workspace]** > **[!UICONTROL Proyecto]** > **[!UICONTROL Información y configuración del proyecto]**

![](assets/projectinfo.png)

**[!UICONTROL Información y configuración del proyecto]** proporciona información del proyecto activo actualmente.

| Configuración | Descripción |
|---|---|
| Proyecto  Nombre | Nombre proporcionado al proyecto. Puede hacer doble clic en el nombre para editarlo. |
| Creado por | Nombre del propietario del proyecto. |
| Última modificación | Fecha de la última modificación del proyecto. |
| Etiquetas | Enumera cualquier etiqueta aplicada a un proyecto para una ordenación por categorías más sencilla. También puede etiquetar proyectos mientras los guarda. Puede ver las etiquetas de un proyecto en la página de aterrizaje de Workspace, en la columna [!UICONTROL Etiquetas]. |
| Descripción | Una descripción es útil para aclarar el propósito de un proyecto. Puede hacer doble clic en la descripción para editarla. |
| Contar instancias repetidas en el proyecto | Especifica si las instancias repetidas se cuentan en los informes. Si hay varios valores secuenciales para una misma variable, puede contarlos como una o como varias instancias de la variable. |
| Esquema de colores de visualización | Puede cambiar el esquema de colores que se utiliza en Workspace eligiendo una opción de una paleta de colores distinta o creando una paleta propia. Esta función afecta a muchos elementos del Workspace, incluidas la mayoría de visualizaciones. |
| Ver densidad | Le permite ver más datos en la pantalla al reducir el margen vertical del carril izquierdo, las tablas improvisada y las tablas de cohorte. |

## Menú Proyectos {#section_850CDFCB86A64EB0A0AD5B9E0FCB7013}

El menú Proyectos principal tiene esta apariencia:

![](assets/new-project-menus.png)

Los submenús contienen las siguientes opciones.

>[!NOTE]
>
>Las opciones marcadas con un asterisco (*) solo se muestran con los proyectos **guardados**.

| Proyecto | Editar | Insertar | Componentes | Compartir | Ayuda |
|---|---|---|---|---|---|
| Nuevo | Deshacer | Nuevo panel | Nuevo segmento | Compartir proyecto | Vídeos |
| Open | Borrar | Nuevo panel improvisado | Nueva métrica | Obtener vínculo del proyecto* | Teclas de acceso directo |
| Guardar | Borrar todo | Nuevo panel de comparación de segmentos | Nuevo intervalo de fechas | Enviar archivo ahora* | Foro de ayuda |
| Guardar como* |  | Nueva tabla improvisada | Nueva alerta | Enviar archivo según lo programado* |  |
| Establecer como página de aterrizaje* |  | Nueva línea | Actualizar componentes | Depurar datos de proyectos |  |
| Actualizar proyecto |  | Nueva barra |  |  |  |
| Descargar CSV |  |  |  |  |  |
| Descargar PDF* |  |  |  |  |  |
| Info y configuración del proyecto |  |  |  |  |  |

## Carril izquierdo {#section_271295C26EC840ABB2A8E7EC0498B60E}

El carril izquierdo tiene tres iconos que le permiten acceder a paneles, [visualizaciones](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) y [componentes](/help/components/overview.md) (dimensiones, métricas, segmentos e intervalos de fechas) con un clic:

![](assets/panels.png) ![](assets/visualizations.png) ![](assets/components.png)

Se ha añadido un **[!UICONTROL Panel en blanco]** a la lista de paneles accesibles desde el carril izquierdo. Para crear un **Panel de cohorte nuevo**, arrastre un Panel en blanco y una visualización de una Tabla de cohorte.
