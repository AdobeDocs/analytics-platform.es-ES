---
title: Preguntas frecuentes sobre el análisis guiado
description: Preguntas frecuentes sobre el análisis guiado.
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: Product Analytics
role: User
TQID: https://experienceleague.adobe.com/4fwNjSWPcLFNewlSHjxJq6MVWQY1Lc0-CpSomNkU69M
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 443
ht-degree: 89%

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

* **Analysis Workspace es una experiencia centrada en dimensiones.** Las tablas suelen consistir en filas dimensionales, mientras que las columnas suelen ser métricas. Los segmentos se pueden aplicar tanto a filas como a columnas para obtener los datos deseados.

* **El análisis guiado es un evento y una experiencia centrada en el usuario.** Cada análisis comienza seleccionando eventos. A continuación, se pueden añadir dimensiones y segmentos para restringir los datos de evento.

![Vistas de Analysis Workspace y del análisis guiado](assets/structure.png){style="border:1px solid gray"}

Preste atención al siguiente ejemplo, en el que se centra en los datos en torno a la página principal del sitio web. Los equipos hacen preguntas similares, pero el enfoque del análisis puede ser diferente.

* Un enfoque típico de Analysis Workspace centrado en las dimensiones sería, “Veamos la página principal y cuántas vistas de página recibió”.

  ![Centrado en la dimensión](assets/dimension-centered.png){style="border:1px solid gray"}

* Un enfoque típico de análisis guiado por eventos y centrado en el usuario sería: “¿Cuántos usuarios han visitado nuestra página principal?”

  ![Centrado en el evento](assets/event-centered.png){style="border:1px solid gray"}

+++
