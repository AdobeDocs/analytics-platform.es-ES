---
title: Crear filtros
description: Comprenda la interfaz de usuario para la creación de filtros.
translation-type: tm+mt
source-git-commit: 0c5bd5ce0b0ba4ba758a1ef1adf5a4a519e9cf8c
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 38%

---


# Crear filtros

El Generador de filtros proporciona un lienzo para arrastrar y soltar las métricas, las dimensiones, los filtros y los eventos para filtrar a los visitantes en función de la lógica, las reglas y los operadores de la jerarquía de contenedor. Esta herramienta de desarrollo integrado le permite generar y guardar filtros simples o complejos que identifican atributos y acciones de visitantes en visitas y visitas individuales de páginas.

Puede crear filtros instantáneos soltando cualquier tipo de componente (dimensión, elemento de dimensión, evento, métrica, segmento, plantilla de segmento, intervalo de fechas) en la zona de colocación del filtro en la parte superior de un panel.

Los tipos de componente se convierten automáticamente en filtros. Alternatively, you can click the &quot;+&quot; sign in the **[!UICONTROL Add Filter]** drop box.

Tenga en cuenta que:

* You **cannot** drop the following component types into the filter zone: calculated metrics and dimensions/metrics from which you cannot build filters.
* Para dimensiones y eventos completos, el Analysis Workspace crea filtros de visita &quot;existe&quot;. Ejemplos: “Visita donde existe eVar1” o “Visita donde existe evento1”.
* Si se coloca &quot;sin especificar&quot; o &quot;ninguno&quot; en la zona de colocación del filtro, se convierte automáticamente en un filtro &quot;no existe&quot; para que se trate correctamente.

![](assets/segment-dropzone.png)

>[!NOTE] Los Filtros creados de esta forma son internos al proyecto.

Puede elegir que estos filtros sean públicos (globales) siguiendo estos pasos:

1. Pase el ratón sobre el filtro en la zona de colocación y haga clic en el icono &quot;i&quot;.
1. En el panel de información que aparece, haga clic en **[!UICONTROL Convertir en público]**.

   ![](assets/segment-info.png)

## Otros métodos para aplicar filtros

Existen otros métodos para aplicar filtros a un proyecto:

| Acción | Descripción |
|--- |--- |
| Crear filtro a partir de selección | Cree un filtro en línea. Seleccione filas, haga clic con el botón secundario en la selección y, a continuación, cree un filtro en línea. Este filtro solo se aplica al proyecto abierto y no se guarda como filtro CJA. 1. Seleccione filas.  2. Haga clic con el botón secundario en la selección.  3. Click *Create filter from selection*. |
| Componentes > Nuevo filtro | Muestra el Generador de filtros. See [Filter Builder](https://docs.adobe.com/content/help/es-ES/analytics/components/segmentation/segmentation-workflow/seg-build.html) for more information about filtering. |
| Compartir > Compartir proyecto o Compartir > Depurar datos del proyecto | In [Curate and Share](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6), learn how filters that you apply to the project are available in shared analysis for the recipient. |
| Usar filtros como dimensiones | Vídeo: [Uso de segmentos como dimensiones en Analysis Workspace](https://www.youtube.com/watch?v=WmSdReKTWto&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=39) |
