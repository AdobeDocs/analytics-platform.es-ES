---
title: Crear filtros
description: Comprenda la interfaz de usuario para la creación de filtros.
translation-type: tm+mt
source-git-commit: 21bf268600c12dbf1db24dbc10028a0c29fc48a7
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 100%

---


# Crear filtros

El Generador de filtros proporciona un lienzo para arrastrar y soltar las métricas, las dimensiones, los filtros y los eventos para filtrar a los visitantes en función de la lógica, las reglas y los operadores de la jerarquía de contenedor. Esta herramienta de desarrollo integrado le permite generar y guardar filtros simples o complejos que identifican atributos y acciones de visitantes en visitas y visitas individuales de páginas.

Puede crear filtros instantáneos soltando cualquier tipo de componente (dimensión, elemento de dimensión, evento, métrica, segmento, plantilla de segmento, intervalo de fechas) en la zona de colocación de filtros en la parte superior de un panel.

Los tipos de componente se convierten automáticamente en filtros. También puede hacer clic en el signo “+” en el cuadro desplegable **[!UICONTROL Agregar filtro]**.

Tenga en cuenta que:

* **No puede** soltar los siguientes tipos de componentes en la zona de filtros: métricas calculadas y dimensiones/métricas desde las que no se pueden crear filtros.
* Para las dimensiones y eventos completos, Analysis Workspace crea filtros de visita del tipo “existe”. Ejemplos: “Visita donde existe eVar1” o “Visita donde existe evento1”.
* Si se suelta “sin especificar” o “ninguno” en la zona de colocación de filtros, se convierten automáticamente en un filtro “no existe”, de modo que se los trate adecuadamente en la segmentación.

![](assets/segment-dropzone.png)

>[!NOTE]
>
>Los filtros creados de esta forma son internos del proyecto.

Puede convertir estos filtros en públicos (globales) siguiendo estos pasos:

1. Sitúese sobre el filtro de la zona de colocación y haga clic en el icono “i”.
1. En el panel de información que aparece, haga clic en **[!UICONTROL Convertir en público]**.

   ![](assets/segment-info.png)

## Otros métodos para aplicar filtros

Hay varios métodos más para aplicar filtros a un proyecto:

| Acción | Descripción |
|--- |--- |
| Crear filtro desde la selección | Cree un filtro en línea. Seleccione filas, haga clic con el botón secundario en la selección y cree un filtro en línea. Este filtro se aplica solamente al proyecto abierto y no se guarda como filtro de CJA. 1. Seleccione filas.  2. Haga clic con el botón secundario en la selección.  3. Haga clic en *Crear filtro de selección*. |
| Componentes > Nuevo filtro | Se abre el Generador de filtros. Consulte el [Generador de filtros](https://docs.adobe.com/content/help/es-ES/analytics/components/segmentation/segmentation-workflow/seg-build.html) para obtener más información acerca de la creación de filtros. |
| Compartir > Compartir proyecto o Compartir > Depurar datos del proyecto | En [Depurar y compartir](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6), los segmentos aplicados al proyecto se encuentran disponibles en el análisis compartido para el destinatario. |
| Usar filtros como dimensiones | Vídeo: uso de filtros como dimensiones en Analysis Workspace |

>[!VIDEO](https://video.tv.adobe.com/v/23974)
