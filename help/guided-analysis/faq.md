---
title: Preguntas frecuentes sobre el análisis guiado
description: Preguntas frecuentes sobre el análisis guiado.
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: df00d954de5db89f0ccc40f7eb2474523d9e774e
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 71%

---

# Preguntas frecuentes sobre el análisis guiado

Preguntas más frecuentes sobre el análisis guiado.

+++**¿Tiene mi organización acceso al análisis guiado?**

Las vistas de análisis guiado se incluyen en todos los paquetes de Customer Journey Analytics. Consulte la sección [aprovisionamiento](overview.md#provisioning) en la página de información general para obtener más información sobre las vistas que desbloquea el paquete de CJA.

+++

+++**¿Qué cambios de implementación se requieren para utilizar el análisis guiado?**

Si ya utiliza Customer Journey Analytics hoy, no es necesario realizar cambios de implementación adicionales. El análisis guiado utiliza las mismas [Vistas de datos](../data-views/data-views.md) y [Conexiones](../connections/overview.md) que otras interfaces de CJA, como [Analysis Workspace](../analysis-workspace/home.md).

Para permitir que los usuarios finales tengan más éxito con el análisis guiado, se recomienda contar con un esquema de eventos y una estrategia de administración sólidos en Adobe Experience Platform y [Vistas de datos](../data-views/data-views.md).

+++

+++**¿Cuándo se debe utilizar el análisis guiado o Analysis Workspace?**

El **análisis guiado** puede ayudar a los usuarios a obtener información de alta calidad rápidamente. Resulta útil para equipos de productos y usuarios que buscan trabajar con datos con mayor confianza, e incluso analistas como punto de partida para un análisis más profundo.

**[Analysis Workspace](../analysis-workspace/home.md)** es un espacio de forma más libre que le permite profundizar en los datos para obtener más información. Resulta útil para analistas y usuarios avanzados que comprenden bien los datos y desean profundizar en ellos.

+++

+++**¿Cómo se compara la terminología entre el análisis guiado y Analysis Workspace?**

El análisis guiado utiliza términos que se utilizan con mayor frecuencia entre los equipos de productos. Puede hacer referencia a esta tabla al cambiar entre el análisis guiado y [Analysis Workspace](../analysis-workspace/home.md).

| Término Análisis guiado | Término Analysis Workspace |
| --- | --- |
| Evento | Métrica |
| Usuarios | Personas |
| Propiedad | Dimensión |
| Valor | Elemento de dimensión |
| Segmento | Filtro |

{style="table-layout:auto"}

+++

+++**¿Cuáles son algunas diferencias en la forma en que el análisis guiado y el enfoque de Analysis Workspace aplican la creación de informes?**

Mientras que [Analysis Workspace](../analysis-workspace/home.md) y el análisis guiado utilizan los mismos datos subyacentes, la forma en que cada herramienta permite formar consultas de esos datos es diferente.

* **Analysis Workspace es una experiencia centrada en la dimensión.** Las tablas suelen consistir en filas dimensionales, mientras que las columnas suelen ser métricas. Los filtros se pueden aplicar tanto a filas como a columnas para obtener los datos deseados.

* **El análisis guiado es una experiencia centrada en el evento y el usuario.** Cada análisis comienza seleccionando eventos. A continuación, se pueden añadir dimensiones y filtros para restringir los datos de evento.

![Vistas de Analysis Workspace y del análisis guiado](assets/structure.png){style="border:1px solid gray"}

Preste atención al siguiente ejemplo, en el que se centra en los datos en torno a la página principal del sitio web. Los equipos hacen preguntas similares, pero el enfoque del análisis puede ser diferente.

* Un enfoque típico de Analysis Workspace centrado en las dimensiones sería, “Veamos la página principal y cuántas vistas de página recibió”.

  ![Centrado en la dimensión](assets/dimension-centered.png){style="border:1px solid gray"}

* Un enfoque típico de análisis guiado centrado en el usuario y el evento sería: &quot;¿Cuántos usuarios han visitado la página principal?&quot;

  ![Centrado en el evento](assets/event-centered.png){style="border:1px solid gray"}

+++
