---
title: Optimizar el rendimiento de CJA
description: Prácticas recomendadas sobre cómo optimizar el rendimiento de CJA
solution: Customer Journey Analytics
role: Admin
hide: true
hide-from-toc: true
source-git-commit: a546c52d2a686c38f7a9a23e0c541568c2918495
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 93%

---


# Optimizar el rendimiento de CJA

>[!NOTE]
>
>Para optimizar los factores de rendimiento de Workspace, consulte [Optimizar [!UICONTROL Analysis Workspace] rendimiento](/help/analysis-workspace/workspace-faq/optimizing-performance.md).

Estos factores influyen en el rendimiento general de CJA:

| Factor | Definición | Afectado por | Optimización |
| --- | --- | --- | --- |
| Complejidad de filtro | Los filtros intrincados pueden tener un impacto significativo en el desempeño del proyecto. | Los factores que añaden complejidad a un filtro (en orden descendente de impacto) son: <ul><li>Los operadores de “contiene”, “contiene algo de”, “coincide con”, “comienza con” o “termina con” </li><li>El filtrado secuencial, sobre todo cuando se utilizan restricciones de dimensión (Dentro/Después) </li><li>El número de elementos de dimensiones únicas dentro de las dimensiones utilizadas en el filtro (por ejemplo, Página = “A” cuando Página tiene 10 elementos únicos será más rápido que Página = “A” cuando Página tiene 100000 elementos únicos) </li><li>Número de dimensiones diferentes utilizadas (por ejemplo, Página = “Home” y Página = “Search results” será más rápido que eVar 1 = “red” y eVar 2 = “blue”)</li><li>Muchos operadores OR (en lugar de AND)</li><li>Contenedores anidados que varían en ámbito (por ejemplo, Visita (hit) en el interior de la “Visita” dentro de “Visitante”)</li></ul> | Aunque algunos de los factores de complejidad no se pueden prevenir, busque opciones para reducir la complejidad de sus filtros. En general, cuanto más específico pueda ser con sus criterios de filtro, mejor. Por ejemplo:<ul><li>Con los contenedores, el uso de un solo contenedor en la parte superior del filtro será más rápido que una serie de contenedores anidados.</li><li>Con los operadores, “es igual que” será más rápido que “contiene” y “es equivalente a” será más rápido que “contiene algo de”.</li><li>Con muchos criterios, los operadores AND serán más rápidos que varios operadores OR.</li></ul> Busque oportunidades para reducir muchas condiciones “OR” en una sola condición “es equivalente a”.<br> |
| Complejidad de la visualización (métricas, filtros) | El tipo de visualización agregado (p. ej., abandonos o tabla de forma libre) no tiene demasiada influencia por sí mismo en el rendimiento de un proyecto. Lo que afecta al tiempo de procesamiento es la complejidad de la visualización. | Entre los factores que aumentan la complejidad de una visualización están:<ul><li>Intervalo de datos solicitado</li><li>El número de filtros aplicados; por ejemplo, los filtros utilizados como columnas de una tabla de forma libre.</li><li>Uso de filtros complejos</li><li>Filas o columnas de [elementos manuales](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) en tablas de forma libre</li><li>Los filtros aplicados a las filas de una tabla de forma libre.</li><li>El número de métricas incluidas, en especial las métricas calculadas que utilizan filtros.</li></ul> | Si ha notado que sus proyectos no se cargan tan rápido como le gustaría, pruebe a sustituir algunos filtros por eVars y filtros, si es posible.<br><br>Si usa constantemente filtros y métricas calculadas para puntos de datos que son importantes para su negocio, plantéese mejorar su implementación para capturar estos puntos de datos de forma más directa. El uso de un administrador de etiquetas como Adobe Experience Platform Launch y las reglas de procesamiento de Adobe pueden hacer que los cambios de implementación sean rápidos y sencillos. |
| Capacidad del centro de datos | La cantidad de capacidad de creación de informes que usted y otros clientes comparten dentro de un centro de datos de Adobe. | Esto se ve afectado por el número de consultas simultáneas realizadas por su organización y otras organizaciones dentro del centro de datos. | Su organización tiene derecho a una capacidad fija y, si el sistema está bajo una carga ligera, Adobe le transferirá más capacidad, por encima y más allá de su asignación. |



