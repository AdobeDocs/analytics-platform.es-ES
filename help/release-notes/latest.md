---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 5a38bb3a792b1b5b998e60870eb40a5aeced4280
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 56%

---

# Notas de la versión del Customer Journey Analytics actual (CJA) (agosto de 2022)

**Última actualización**: 12 de agosto de 2022

## Funciones principales

| Función | Descripción | [Fecha objetivo](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Panel de visualizadores simultáneos de medios** | Comprenda dónde se produjo el pico de concurrencia o dónde se produjeron las disminuciones. Obtenga valiosos conocimientos de la calidad del contenido y de la participación del visualizador, y solucione problemas o planifique el volumen o la escala.  [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html?lang=es) | 9 de agosto de 2022 |
| **Panel Tiempo invertido en la reproducción de medios** | El Tiempo invertido en la reproducción de medios proporciona un valioso conocimiento sobre la participación de los espectadores y permite a las organizaciones de medios obtener una información más profunda y granular. Esto se realiza con la participación de los usuarios detallada minuto a minuto, por medio de un análisis avanzado del tiempo invertido con capacidades de partición del día. Puede observar la cantidad de tiempo que se dedica a ver sus flujos de contenido en un momento determinado. Puede dividir la duración de la reproducción por diferentes granularidades, incluyendo las nuevas granularidades de 5, 15 y 30 minutos.   [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html?lang=es) | 9 de agosto de 2022 |
| **Publicación de audiencias en el Perfil del cliente en tiempo real** | Permite publicar audiencias descubiertas en CJA en Adobe Experience Platform/Perfil del cliente en tiempo real para personalización y segmentación de clientes.  [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/audiences-overview.html?lang=es) | 17 de agosto de 2022 |
| **Compatibilidad con CJA para etiquetas y políticas de control de datos** | Automatiza la integración entre las etiquetas y políticas de privacidad de CJA y Adobe Experience Platform. Las etiquetas de datos creadas en conjuntos de datos consumidos por Platform se muestran en las vistas de datos de CJA para detener o advertir a los usuarios que crean métricas o dimensiones a partir de campos confidenciales. Además, cuando los datos se exportan desde CJA (a través de informes de Workspace o Report Builder, exportación, API, etc.) se agregarán etiquetas o advertencias adicionales para notificar a los usuarios que un informe contiene información confidencial que debe tratarse de una manera específica.  [Más información](/help/data-views/data-governance.md) | 17 de agosto de 2022 |
| **Panel de experimentos para CJA (Alza y confianza genéricas)** | Este nuevo panel de Workspace permite a los usuarios de CJA evaluar el alza y la confianza de cualquier experimento A/B desde cualquier fuente: en línea, sin conexión, desde soluciones de Adobe, Adobe Journey Optimizer e incluso datos de BYO. Más información a continuación. | 17 de agosto de 2022 |
| **Compatibilidad con campos de fecha en CJA** | Permite que CJA informe sobre los campos de fecha y hora.  [Más información](/help/data-views/data-views-usecases.md#date) | 17 de agosto de 2022 |
| **Compatibilidad entre regiones para el conector de origen de Analytics** | Ahora puede ingerir grupos de informes de cualquier región (Estados Unidos, Reino Unido o Singapur). Sin embargo, estos grupos de informes deben asignarse a la misma organización que la instancia de espacio aislado del Experience Platform en la que se está creando la conexión de origen.  [Más información](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es) | 24 de agosto de 2022 |
| **Creación de informes de sesión nueva frente a repetida** | Ahora puede descubrir si una sesión en particular fue la primera de un usuario. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=es#new-repeat) | 24 de agosto de 2022 |

{style=&quot;table-layout:auto&quot;}

## Correcciones

AN-297141

## Avisos importantes para los administradores de CJA

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| **Asignación de IP a geolocalización mejorada** | 11 de julio de 2022 | El proveedor de Adobe para búsquedas de IP, Digital Element, está actualizando a un nuevo conjunto de datos mejorado (NetAcuity Pulse) para la asignación de IP a geolocalización. Adobe Analytics adoptará este nuevo conjunto de datos en el **Octubre de 2022** intervalo de tiempo. La nueva base de datos será más precisa que las versiones anteriores. Algunas asignaciones de IP a regiones cambiarán o mejorarán cuando se adopte la nueva base de datos.<p> Los datos de CJA proporcionados a través del conector de origen de Analytics también aprovecharán automáticamente las nuevas asignaciones. |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
