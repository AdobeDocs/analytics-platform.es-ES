---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 524aed20a62b8d8648230be81c63f9c58c84ae87
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 80%

---

# Notas de la versión de Customer Journey Analytics (CJA) actuales (febrero de 2023)

**Última actualización**: 6 de febrero de 2023

Las versiones de Customer Journey Analytics operan en un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones principales y actualizaciones

| Función | Descripción | [Inicio del despliegue](/help/release-notes/releases.md) | [Disponibilidad general](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Actualización de las audiencias de CJA** | Después de crear una audiencia, Adobe crea un segmento de streaming de Experience Platform para cada nueva audiencia de CJA. Solo se creará un segmento de streaming si su organización está configurada para la segmentación de streaming. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=es#after-audience-created) | N/A | 3 de febrero de 2023 |
| **Ocultar intervalos de fechas de comparación en los cuadros de resultados móviles** | Con los cuadros de resultados móviles, ahora puede ocultar los intervalos de fechas de comparación. | N/A | 8 de febrero de 2023 |
| **Actualizaciones de calendario en Workspace** | <ul><li>Fechas del panel de anclaje: puede hacer que los componentes del intervalo de fechas sean relativas al calendario del panel.  [Más información](/help/components/date-ranges/calendar.md)</li><li>Actualizaciones de estilo del calendario: los estilos de calendario de toda la IU se han actualizado para presentar un flujo de trabajo más coherente y fácil de usar.</li><li>Actualizaciones de la fórmula del calendario: si utiliza fechas relativas, todas las fórmulas del calendario reflejarán el inicio del intervalo de fechas del panel. [Más información](/help/components/date-ranges/calendar.md)</li></ul> | N/A | 8 de febrero de 2023 |
| **Actualizaciones del intervalo de fechas del panel** | En Workspace, se han añadido las siguientes mejoras:<ul><li>A partir de la versión de febrero, las vistas previas de componentes y datos se basarán en el intervalo de fechas del panel y no en los últimos 90 días. </li><li>Todos los componentes enumerados en el carril izquierdo estarán disponibles en función del intervalo de fechas del panel.</li><li>Todas las vistas previas de fechas del segmento y los creadores de métricas calculadas se basarán en el intervalo de fechas del panel (a menos que se acceda desde los administradores de componentes, que no tienen un panel asociado, se basarán en los últimos 90 días).</li><li>Cualquier vista previa de datos mostrará datos o componentes en función del intervalo de fechas del panel.</li></ul> | N/A | 8 de febrero de 2023 |
| **Filtrado de filas y columnas para el streaming del conector de origen de Adobe Analytics** | El conector de origen de Analytics en Adobe Experience Platform ahora permite filtrar los datos de Analytics que se usan para rellenar perfiles en el [Perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=es).<p>El filtrado a nivel de fila ayuda a reducir el número de eventos asociados a perfiles. El filtrado a nivel de columna ayuda a reducir la riqueza de los propios eventos, lo que permite optimizar el uso de derechos de perfil. Este filtrado solo se aplica a los datos enviados al Perfil del cliente en tiempo real y al [Servicio de identidad](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=es).<p>**El filtrado no afecta a los datos que se envían a Data Lake para su uso en aplicaciones como Customer Journey Analytics**. [Más información](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es#filtering-for-profile) | N/A | 22 de febrero de 2023 |

{style=&quot;table-layout:auto&quot;}

## Correcciones en Customer Journey Analytics

AN-309106

## Avisos importantes para los administradores de CJA

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| No hay avisos actuales | N/A | N/A |

{style=&quot;table-layout:auto&quot;}

## Recursos relacionados

* [Notas de la versión de CJA anteriores de 2023](/help/release-notes/2023.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
