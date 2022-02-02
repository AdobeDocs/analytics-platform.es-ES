---
description: Utilizar filtros específicos en Analysis Workspace.
title: Filtros de proyecto específicos
feature: CJA Workspace Basics
role: User, Admin
exl-id: 79513ad9-3c9d-441e-a5c5-c2b1e5cacc2e
source-git-commit: cea2faeaf9c2779ab808506025780fd3659a94b1
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 100%

---

# Filtros de proyecto específicos

Aquí tiene un vídeo sobre la creación de filtros de proyecto específicos:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

Puede crear filtros de proyecto específicos si desea explorar rápidamente cómo un filtro podría afectar a su proyecto, sin ir al Generador de segmentos. Piense en estos filtros como filtros temporales en cuanto al proyecto. No suelen formar parte de la biblioteca de filtros, como los filtros de componentes en el carril izquierdo. Sin embargo, puede guardarlos, como se muestra a continuación.

Para ver una comparación de lo que pueden hacer los filtros de proyecto específicos frente a los filtros de nivel de componente completos, vaya [aquí](/help/components/filters/filters-overview.md).

1. Soltar cualquier tipo de componente (dimensión, elemento de dimensión, evento, métrica, filtro, plantilla de filtro, intervalo de fechas) en la zona de colocación de filtros en la parte superior de un panel. Los tipos de componente se convierten automáticamente en filtros.
Este es un ejemplo de cómo crear un filtro para el dominio de referencia de Twitter:

   ![](assets/ad-hoc1.png)

   El panel obtiene automáticamente este filtro y puede ver los resultados al instante.

1. Puede agregar un número ilimitado de componentes a un panel.
1. Si decide guardar este filtro, consulte la sección siguiente.

Recuerde:

* **No puede** soltar los siguientes tipos de componentes en la zona de filtros: métricas calculadas y dimensiones/métricas desde las que no se pueden crear filtros.
* Para las dimensiones y eventos completos, Analysis Workspace crea filtros de visita del tipo “existe”. Ejemplos: `Hit where eVar1 exists` o `Hit where event1 exists`.
* Si se suelta sin especificar o como “ninguno” en la zona de colocación de filtros, se convierten automáticamente en un filtro “no existe”, de modo que se los trate adecuadamente en la segmentación.

>[!NOTE]
>
>Los segmentos creados de esta forma son internos del proyecto.

## Guardar filtros de proyecto específicos {#ad-hoc-save}

Puede elegir guardar estos filtros siguiendo estos pasos:

1. Sitúese sobre el filtro de la zona de colocación y haga clic en el icono “i”.
1. En el panel de información que aparece, haga clic en **[!UICONTROL Guardar]**.

   ![](assets/segment-info.png)

## ¿Qué son los filtros de solo proyecto?

Los filtros de solo proyecto son filtros rápidos o filtros de proyecto específicos del espacio de trabajo. Al editarlas o abrirlas en el generador de filtros, se mostrará el cuadro de solo proyecto. Si APLICAN un filtro rápido en el generador, pero no marcan la casilla de disponibilidad, entonces sigue siendo un filtro solo de proyecto, pero ya no se puede abrir en el generador de QS. Si marca la casilla y la opción GUARDAR, ahora es un filtro de lista de componentes.
