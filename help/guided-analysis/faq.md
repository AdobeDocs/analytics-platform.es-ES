---
title: Preguntas frecuentes sobre análisis guiados
description: Preguntas frecuentes sobre el análisis guiado.
exl-id: 32bfce23-a59c-45cb-b1cd-82f048fb13d2
feature: Guided Analysis
source-git-commit: 84cafd2756a09537c93524ff728ea78b7cbf5c8e
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 3%

---

# Preguntas frecuentes sobre análisis guiados

{{release-limited-testing}}

Preguntas frecuentes sobre el análisis guiado.

+++**¿Está disponible el análisis guiado para todos?**

No; el análisis guiado es un complemento de pago para Customer Journey Analytics. Si desea empezar a utilizar este complemento, póngase en contacto con el equipo de cuenta de Adobe.

+++

+++**¿Qué cambios de implementación se requieren para utilizar el análisis guiado?**

Si ya utiliza Analysis Workspace en Customer Journey Analytics, no es necesario realizar cambios de implementación adicionales. El análisis guiado utiliza las mismas vistas de datos y conexiones que Analysis Workspace. El proceso para incorporar y utilizar cualquier tipo de proyecto es idéntico para todos los Customer Journey Analytics, incluido el análisis guiado.

+++

+++**¿Cómo se relacionan los términos entre sí dentro y fuera del análisis guiado?**

El análisis guiado utiliza términos que se utilizan con mayor frecuencia en la industria del análisis de productos. Puede hacer referencia a esta tabla al cambiar entre Análisis guiado y Analysis Workspace.

| Término del análisis guiado | Término de Analysis Workspace |
| --- | --- |
| Evento | Métrica |
| Propiedad | Dimensión |
| Valor | Elemento de dimensión |
| Segmento | Filtro |

{style="table-layout:auto"}

+++

+++**¿Cuáles son algunas diferencias en la forma en que Analysis Workspace y el análisis guiado abordan los informes?**

Aunque Analysis Workspace y el análisis guiado utilizan los mismos datos subyacentes, la forma en que cada herramienta consulta esos datos es diferente.

* **Analysis Workspace es una experiencia centrada en las dimensiones.** Las tablas suelen consistir en filas de elementos de dimensión, mientras que las columnas suelen ser métricas. Puede aplicar filtros a cualquiera de las dos para obtener los datos deseados.

* **El análisis guiado es una experiencia centrada en eventos.** Las visualizaciones se centran en eventos, utilizando dimensiones y filtros para complementar esos datos.

![Estructura](assets/structure.png)

Preste atención al siguiente ejemplo, en el que se centra en los datos de la página principal del sitio web. Los equipos hacen preguntas similares, pero el enfoque del análisis puede ser diferente.

* Un enfoque típico de Analysis Workspace centrado en las dimensiones sería: &quot;¿Cuántas vistas de página ha recibido la página principal?&quot;

  ![centrado en Dimension](assets/dimension-centered.png)

* Un enfoque típico del análisis guiado centrado en eventos sería: &quot;¿Cuántos usuarios han visto la página principal?&quot;

  ![Centrado en evento](assets/event-centered.png)

Estas instrucciones ilustran dos métodos diferentes para lograr el mismo informe, según la estrategia de administración de eventos.

+++
