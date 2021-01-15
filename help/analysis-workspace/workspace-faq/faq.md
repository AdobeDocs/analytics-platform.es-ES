---
description: Preguntas frecuentes sobre Workspace
title: Preguntas frecuentes
translation-type: tm+mt
source-git-commit: 3dc9d0d0a1f65a4205120895c35aa508f080c25d
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 87%

---


# Preguntas frecuentes

>[!NOTE]
>
>Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

| Pregunta | Respuesta |
|--- |--- |
| ¿Cuáles son los requisitos previos para utilizar Analysis Workspace? | El uso de Analysis Workspace requiere una implementación de Customer Journey Analytics de trabajo. Asegúrese de que su organización está enviando datos al Adobe Experience Platform antes de utilizar la herramienta. |
| ¿Cuáles son los requisitos de administración y acceso de Analysis Workspace? | Consulte [Requisitos de administración](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| ¿Afectará el uso de Analysis Workspace a la recopilación de datos? | Como Analysis Workspace es una herramienta de generación de informes, no afecta a la recopilación de datos. No hay repercusiones en arrastrar indiscriminadamente componentes a un proyecto para ver qué funciona. Arrastre diferentes combinaciones de dimensiones y métricas al proyecto del espacio de trabajo para ver qué hay disponible. Si arrastra accidentalmente un componente no válido al proyecto del espacio de trabajo o desea volver atrás un paso, pulse ctrl+Z (Windows) o cmd+Z (Mac) para deshacer la última acción realizada. También puede empezar con una pizarra limpia haciendo clic en *[!UICONTROL Proyecto] > [!UICONTROL Nuevo]* en el menú superior izquierdo. |
| ¿Cómo se implementa Analysis Workspace? | No se requiere implementación especial. Analysis Workspace está disponible para todos los Customer Journey Analytics de compañías. Sin embargo, se aplican permisos estándar al contenido (como los componentes del proyecto) y para depurar y compartir proyectos. Consulte [Administración y requisitos de acceso](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| ¿Cómo puedo optimizar el rendimiento de Analysis Workspace? | Consulte [Optimización del rendimiento](/help/analysis-workspace/workspace-faq/optimizing-performance.md). |

## Resolución de problemas

**Cuando arrastro una métrica, significa “Datos no válidos”.**

Datos no válidos significa que Adobe no puede devolver datos mediante la combinación de dimensiones y métricas utilizadas en el informe. Por ejemplo: dos métricas apiladas una encima de la otra no se pueden devolver como datos, ya que no hay forma de mostrar dos métricas de esa manera. En su lugar, coloque las métricas una al lado de la otra.

**Cuando arrastro una métrica, no veo ningún dato real, solo ceros.**

Si ha creado correctamente un informe de espacio de trabajo pero no hay datos, puede comprobar algunas cosas:

* Compruebe el grupo de informes y asegúrese de que se rellena con datos.
* Si aplicó un segmento en el informe, es posible que los criterios del segmento no coincidan con ningún dato. Intente eliminar el segmento o ajustar la definición del mismo.
* Compruebe el intervalo de fechas en la esquina superior derecha y compruebe que está establecido en un valor que esperaba.
* Vaya al sitio web y utilice [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=es-ES) para validar que se están recopilando datos.