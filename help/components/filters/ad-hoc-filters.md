---
description: Utilizar filtros específicos en Analysis Workspace.
title: Filtros de proyecto específicos
feature: Workspace Basics
role: User, Admin
source-git-commit: 275c552b14a4c2a47e00d0600ac3eae6811beae9
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 17%

---


# Filtros de proyecto específicos

Aquí tiene un vídeo sobre la creación de filtros de proyecto ad-hoc:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

Puede crear filtros de proyecto específicos si desea explorar rápidamente cómo un filtro podría afectar a su proyecto, sin ir al Generador de segmentos. Piense en estos filtros como filtros temporales a nivel de proyecto. Normalmente no formarán parte de la &quot;biblioteca&quot; de filtros, como los filtros de componentes en el carril izquierdo. Sin embargo, puede guardarlos, como se muestra a continuación.

Para ver una comparación de lo que pueden hacer los filtros de proyecto ad-hoc frente a los filtros de nivel de componente completos, vaya [aquí](/help/components/filters/filters-overview.md).

1. Coloque cualquier tipo de componente (dimensión, elemento de dimensión, evento, métrica, filtro, plantilla de filtro, intervalo de fechas) en la zona de colocación de filtros en la parte superior de un panel. Los tipos de componente se convierten automáticamente en filtros.
Este es un ejemplo de cómo crear un filtro para el dominio de referencia de Twitter:

   ![](assets/ad-hoc1.png)

   El panel obtiene automáticamente este filtro y puede ver los resultados al instante.

1. Puede agregar un número ilimitado de componentes a un panel.
1. Si decide guardar este filtro, consulte la sección siguiente.

Recuerde:

* **No puede** soltar los siguientes tipos de componentes en la zona de filtros: métricas calculadas y dimensiones/métricas desde las que no se pueden crear filtros.
* Para las dimensiones y eventos completos, Analysis Workspace crea filtros de visita del tipo “existe”. Ejemplos: `Hit where eVar1 exists` o `Hit where event1 exists`.
* Si se suelta &quot;sin especificar&quot; o &quot;ninguno&quot; en la zona de colocación de filtros, se convierte automáticamente en un filtro &quot;no existe&quot; para que se lo trate correctamente en el filtrado.

>[!NOTE]
>
>Los segmentos creados de esta forma son internos del proyecto.

## Guardar filtros de proyecto específicos {#ad-hoc-save}

Puede guardar estos filtros siguiendo estos pasos:

1. Sitúese sobre el filtro de la zona de colocación y haga clic en el icono “i”.
1. En el panel de información que aparece, haga clic en **[!UICONTROL Guardar]**.

   ![](assets/segment-info.png)

## ¿Qué son los filtros de solo proyecto?

Los filtros de solo proyecto son filtros rápidos o filtros de proyecto específicos de Workspace. Al editarlas o abrirlas en el generador de filtros, se mostrará el cuadro de solo proyecto. Si APLICAN un filtro rápido en el generador pero no marcan la casilla de disponibilidad, entonces sigue siendo un filtro solo de proyecto pero ya no se puede abrir en el generador de QS. Si marca la casilla y la opción GUARDAR ahora es un filtro de lista de componentes.