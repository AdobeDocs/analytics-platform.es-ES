---
description: Preguntas frecuentes y sugerencias para la solución de problemas de Workspace.
title: Preguntas frecuentes
feature: FAQ
exl-id: d7233b26-9887-4b71-ad46-3c6ffe27d904
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 96%

---

# Preguntas frecuentes

| Pregunta | Respuesta |
|--- |--- |
| **¿Cuáles son los requisitos previos para utilizar Analysis Workspace?** | El uso de Analysis Workspace en Customer Journey Analytics requiere una implementación de Customer Journey Analytics en funcionamiento. Compruebe que su organización está enviando datos a Adobe Experience Platform antes de utilizar la herramienta. |
| **¿Cuáles son los requisitos de administración y acceso de Analysis Workspace?** | Consulte [Requisitos de administración](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| **¿Afectará el uso de Analysis Workspace a la recopilación de datos?** | Como Analysis Workspace es una herramienta de generación de informes, no afecta a la recopilación de datos. No hay repercusiones en arrastrar indiscriminadamente componentes a un proyecto para ver qué funciona. Arrastre diferentes combinaciones de dimensiones y métricas al proyecto de Workspace para ver qué hay disponible. Si arrastra accidentalmente un componente no válido al proyecto de Workspace o desea volver atrás un paso, pulse ctrl+Z (Windows) o cmd+Z (Mac) para deshacer la última acción realizada. También puede empezar con una pizarra limpia haciendo clic en *[!UICONTROL Proyecto] > [!UICONTROL Nuevo]* en el menú superior izquierdo. |
| **¿Cómo se implementa Analysis Workspace?** | No se requiere implementación especial. Analysis Workspace está disponible para Customer Journey Analytics de todas las empresas. Sin embargo, son aplicables los permisos estándares para el contenido (como los componentes de proyecto) y para depurar y compartir proyectos. Consulte [Administración y requisitos de acceso](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| **¿Cómo puedo optimizar el rendimiento de Analysis Workspace?** | Consulte [Optimización del rendimiento](/help/admin/optimizing-performance.md). |

## Resolución de problemas

**Cuando arrastro una métrica, significa “Datos no válidos”.**

Datos no válidos significa que Adobe no puede devolver datos mediante la combinación de dimensiones y métricas utilizadas en el informe. Por ejemplo: dos métricas apiladas una encima de la otra no se pueden devolver como datos, ya que no hay forma de mostrar dos métricas de esa manera. En su lugar, coloque las métricas una al lado de la otra.

**Cuando arrastro una métrica, no veo ningún dato real, solo ceros.**

Si ha creado correctamente un informe de Workspace pero no hay datos, puede comprobar algunas cosas:

* Si aplicó un filtro en el informe, es posible que los criterios de filtro no coincidan con ningún dato. Intente eliminar el filtro o ajustar su definición.
* Compruebe el intervalo de fechas en la esquina superior derecha y compruebe que está establecido en un valor que esperaba.
* Vaya al sitio web y utilice [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=es) para validar que se están recopilando datos.
