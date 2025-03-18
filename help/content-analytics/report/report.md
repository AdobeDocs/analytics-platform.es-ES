---
title: Informes de Content Analytics
description: Creación de informes sobre Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: User
hide: true
hidefromtoc: true
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: 62491fcbf37961d33be92d209e5710bf9696c223
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 0%

---

# Resumen de informes de Content Analytics

>[!WARNING]
>
>Este artículo es una versión preliminar no oficial del borrador de una próxima versión final y forma parte de la documentación de Content Analytics. Todo el contenido está sujeto a cambios y no se puede derivar ninguna obligación legal de la versión actual de este artículo.
>

{{release-limited-testing}}

Los informes sobre Content Analytics se realizan en Analysis Workspace. Hay disponible una [plantilla](#template) de Workspace específica para que pueda acceder inmediatamente a un proyecto de Workspace previamente completado con información de contenido relevante.

Para empezar a crear informes en Content Analytics desde cero:

1. [Cree un nuevo](/help/analysis-workspace/build-workspace-project/create-projects.md) o [abra un proyecto existente](/help/analysis-workspace/build-workspace-project/open-projects.md) en Workspace.
1. Asegúrese de [seleccionar una vista de datos](/help/analysis-workspace/c-panels/panels.md#data-view) para los informes de Content Analytics. Los informes de Content Analytics solo están disponibles para las vistas de datos [configuradas](/help/content-analytics/config/configuration.md) para Content Analytics.
1. Arrastre una visualización ![Tabla](/help/assets/icons/Table.svg) [Tabla de forma libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) al lienzo.
1. Use [componentes específicos de Content Analytics](components.md) y otros [componentes](/help/components/overview.md) genéricos (como filtros, intervalos de fechas, anotaciones) para generar sus datos de análisis de contenido. También puede utilizar la plantilla de Content Analytics.

## Miniaturas

En función de las dimensiones específicas de Content Analytics que utilice en el proyecto, se muestran miniaturas para los recursos y las dimensiones.

![miniaturas de Content Analytics](../assets/aca-thumbnails.png)

## Previsualizaciones

Para las dimensiones que tienen miniaturas (como Nombre del recurso, Nombre de la experiencia y otras), puede abrir una ventana emergente de vista previa.

Para abrir la vista previa con los siguientes detalles:

* Seleccione ![EsquemaDeInformación](/help/assets/icons/InfoOutline.svg). Verá los siguientes detalles.

  | Previsualización de experiencia | Previsualización de recursos |
  |---|---|
  | ![Vista previa de Content Analytics Experience](../assets/aca-experience-preview.png) | ![Vista previa de recursos Content Analytics](../assets/aca-asset-preview.png) |
  | **[!UICONTROL Nombre de la experiencia]** | **[!UICONTROL Nombre del recurso]** |
  | **[!UICONTROL Impresiones (todas las veces)]**: Número de impresiones de la experiencia. | **[!UICONTROL Impresiones (todas las veces)]**: número de impresiones del recurso. |
  | **[!UICONTROL Assets]**: número de recursos que contiene esta experiencia. Seleccione ![Desglose](/help/assets/icons/Breakdown.svg) para inspeccionar los recursos. | **[!UICONTROL Experiencias]**: Número de experiencias en las que se muestra este recurso. [Desglose](/help/assets/icons/Breakdown.svg) para inspeccionar los recursos. |
  | **[!UICONTROL Primera impresión]**: Fecha de la primera impresión de la experiencia. | **[!UICONTROL Primera impresión]**: Fecha de la primera impresión del recurso. |
  | **[!UICONTROL impresión más reciente]**: Fecha de la impresión más reciente de la experiencia. | **[!UICONTROL Impresión más reciente]**: Fecha de la impresión más reciente del recurso. |
  | **[!UICONTROL Atributos de experiencia]**: Los atributos de la experiencia. | **[!UICONTROL Atributos de recurso]**: Los atributos del recurso. |


## Plantilla

Detalles acerca de las plantillas...


>[!MORELIKETHIS]
>
>[componentes de Content Analytics](components.md)
>
