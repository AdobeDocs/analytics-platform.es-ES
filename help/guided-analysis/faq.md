---
title: Preguntas frecuentes sobre el análisis guiado
description: Preguntas frecuentes sobre el análisis guiado.
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 92%

---

# Preguntas frecuentes sobre el análisis guiado

Preguntas frecuentes sobre el análisis guiado.

+++**¿Tiene mi organización acceso al análisis guiado?**

Las vistas del análisis guiado se incluyen en todos los paquetes de Customer Journey Analytics. Consulte la sección de [aprovisionamiento](overview.md#provisioning) en la página de información general para obtener más información sobre las vistas que desbloquea el paquete de CJA.

+++

+++**¿Qué cambios de implementación se requieren para utilizar el análisis guiado?**

Si ya utiliza Customer Journey Analytics hoy, no es necesario realizar cambios de implementación adicionales. El análisis guiado utiliza las mismas [Vistas de datos](../data-views/data-views.md) y [Conexiones](../connections/overview.md) que otras interfaces de CJA, como [Analysis Workspace](../analysis-workspace/home.md).

Para permitir que los usuarios finales tengan más éxito con el análisis guiado, se recomienda tener un esquema de eventos y una estrategia de administración sólidos en Adobe Experience Platform y [Vistas de datos](../data-views/data-views.md).

+++

+++**¿Cuándo se debe utilizar el análisis guiado o Analysis Workspace?**

El **análisis guiado** puede ayudar a los usuarios a obtener información de alta calidad rápidamente. Resulta útil para equipos de productos y usuarios que buscan trabajar con datos con mayor confianza, e incluso analistas como punto de partida para un análisis más profundo.

**[Analysis Workspace](../analysis-workspace/home.md)** es un espacio de forma más libre que le permite profundizar en los datos para obtener más información. Resulta útil para analistas y usuarios avanzados que comprenden bien los datos y desean profundizar en ellos.

+++

+++**¿En qué se diferencia la terminología entre el análisis guiado y Analysis Workspace?**

El análisis guiado y [Analysis Workspace](../analysis-workspace/home.md) coinciden en la mayoría de la terminología clave, con algunas pequeñas diferencias.

| Término Análisis guiado | Término Analysis Workspace |
| --- | --- |
| Evento (métrica binaria 1/0) | Métrica |
| Usuarios | Personas |
| Dimensión | Dimensión |
| Elemento de dimensión | Elemento de dimensión |
| Segmento | Segmento |
| Filtro | Filtro de informes |
| Métrica calculada, Métricas | Métrica calculada |

{style="table-layout:auto"}

+++

+++**¿Cuáles son algunas diferencias en la forma en que el análisis guiado y Analysis Workspace plantean la creación de informes?**

Mientras que [Analysis Workspace](../analysis-workspace/home.md) y el análisis guiado utilizan los mismos datos subyacentes, la forma en que cada herramienta permite formar consultas de esos datos es diferente.

* **Analysis Workspace es una experiencia centrada en la dimensión.** Las tablas suelen consistir en filas dimensionales, mientras que las columnas suelen ser métricas. Los segmentos se pueden aplicar tanto en filas como en columnas para obtener los datos deseados.

* **El análisis guiado es una experiencia centrada en el evento y el usuario.** Cada análisis comienza seleccionando eventos, luego se pueden agregar dimensiones y segmentos para restringir los datos de evento.

![Vistas de Analysis Workspace y del análisis guiado](assets/structure.png){style="border:1px solid gray"}

Preste atención al siguiente ejemplo, en el que se centra en los datos en torno a la página principal del sitio web. Los equipos hacen preguntas similares, pero el enfoque del análisis puede ser diferente.

* Un enfoque típico de Analysis Workspace centrado en las dimensiones sería, “Veamos la página principal y cuántas vistas de página recibió”.

  ![Centrado en la dimensión](assets/dimension-centered.png){style="border:1px solid gray"}

* Un enfoque típico de análisis guiado por eventos y centrado en el usuario sería: “¿Cuántos usuarios han visitado nuestra página principal?”

  ![Centrado en el evento](assets/event-centered.png){style="border:1px solid gray"}

+++
