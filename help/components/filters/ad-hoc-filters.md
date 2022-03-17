---
description: Utilizar filtros específicos en Analysis Workspace.
title: Filtros de proyecto específicos
feature: CJA Workspace Basics
role: User, Admin
exl-id: 79513ad9-3c9d-441e-a5c5-c2b1e5cacc2e
source-git-commit: 5743bece216431fecc073528ca2509cd2ed72f2b
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 54%

---

# Filtros de proyecto específicos

Los filtros de proyecto específicos le permiten arrastrar y soltar cualquier componente directamente en la zona de colocación del panel para crear un filtro. El filtro se convierte en un [filtro de nivel de proyecto](https://experienceleague.adobe.com/docs/analytics-platform/analysis-workspace/components/filters/quick-filters.html?#what-are-project-only-segments) local al proyecto actual.

Aquí tiene un vídeo sobre la creación de filtros de proyecto específicos:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)


1. 
   1. Coloque cualquier tipo de componente (dimensión, elemento de dimensión, evento, métrica, segmento, plantilla de segmento, intervalo de fechas) en la zona de colocación de filtros en la parte superior de un panel. Los tipos de componente se convierten automáticamente en filtros ad hoc o [Filtros rápidos](/help/components/filters/quick-filters.md) si es compatible.

   Este es un ejemplo de cómo crear un filtro para el dominio de referencia de Twitter:

   ![](assets/ad-hoc1.png)

   El panel obtiene automáticamente este filtro y puede ver los resultados al instante.

1. Puede agregar un número ilimitado de filtros a un panel.
1. Si decide guardar este filtro, consulte la sección siguiente.

Recuerde:

* **No puede** soltar los siguientes tipos de componentes en la zona de filtros: métricas calculadas y dimensiones/métricas desde las que no se pueden crear filtros.
* Para las dimensiones y eventos completos, Analysis Workspace crea filtros de visita del tipo “existe”. Ejemplos: `Hit where eVar1 exists` o `Hit where event1 exists`.
* Si se suelta sin especificar o como “ninguno” en la zona de colocación de filtros, se convierten automáticamente en un filtro “no existe”, de modo que se los trate adecuadamente en la segmentación.

## Guardar filtros de proyecto específicos {#ad-hoc-save}

Puede elegir guardar estos filtros siguiendo estos pasos:

1. Sitúese sobre el filtro de la zona de colocación y haga clic en el icono “i”.
1. Haga clic en el lápiz de edición para ir al Generador de filtros.
1. Marque **[!UICONTROL Poner a disposición de todos los proyectos y añadirlos a la lista de componentes]**.
1. Haga clic en **[!UICONTROL GUARDAR]**.

Una vez guardado, el filtro está disponible en la lista de componentes del carril izquierdo y se puede compartir con otros usuarios desde el Administrador de filtros.

