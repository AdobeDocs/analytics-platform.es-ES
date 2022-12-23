---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: fbfc7113aef8857e11ccfba5e5e557eed16c2465
workflow-type: ht
source-wordcount: '598'
ht-degree: 100%

---

# Notas de la versión de Customer Journey Analytics (CJA) (octubre/noviembre de 2022)

**Última actualización**: 25 de octubre de 2022

Las versiones de Customer Journey Analytics operan en un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones principales y actualizaciones

| Función | Descripción | [Inicio del despliegue](/help/release-notes/releases.md) | [Disponibilidad general](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **[!UICONTROL Resumen de métricas clave] visualización** | La visualización [!UICONTROL Resumen de métricas clave] permite ver las tendencias de una métrica importante dentro de un único periodo de tiempo. También le permite comparar el rendimiento de las métricas en dos intervalos de tiempo.  [Más información](/help/analysis-workspace/visualizations/key-metric.md) | 5 de octubre de 2022 | 19 de octubre de 2022 |
| **Variables de varios valores que no distinguen entre mayúsculas y minúsculas** | En el caso de las variables de varios valores que no distinguen entre mayúsculas y minúsculas, los valores que se almacenan en `mvvar1` - `mvvar3` ya no se convertirán en minúsculas automáticamente. En su lugar, los datos pasados a través del conector de origen de Analytics a Adobe Experience Platform y CJA reflejarán el caso original que se pasó desde la página. Las columnas ASC/CJA `_experience.analytics.customDimensions.lists.list1.list[]` - `_experience.analytics.customDimensions.lists.list3.list[]` se ven afectadas por este cambio. | N/A | 24 de octubre de 2022 |
| **Registro de auditoría de CJA** | Customer Journey Analytics (CJA) le permite auditar la actividad del usuario para varios servicios y funcionalidades en forma de “registros de auditoría”. Estos registros forman una pista de auditoría que puede ser útil en la resolución de problemas y ayudar a su empresa a cumplir de manera eficaz con las políticas de administración de datos corporativos y los requisitos regulatorios, como la Ley de Portabilidad y Responsabilidad del Seguro de Salud (HIPAA, Health Insurance Portability and Accountability Act). Anteriormente, estos registros solo estaban disponibles a través de la API de registros de auditoría.  [Más información](/help/privacy/audit-log.md) | N/A | 26 de octubre de 2022 |
| **Preparación para la HIPAA** | Actualmente, Adobe admite la recepción, el uso, el mantenimiento o la transmisión de información médica protegida en Customer Journey Analytics y otras aplicaciones basadas en Experience Platform únicamente para clientes de Healthcare Shield. Healthcare Shield es para clientes del sector sanitario que sean una entidad cubierta o un socio comercial solamente en Estados Unidos. [Más información](https://www.adobe.com/trust/compliance/hipaa-ready.html) | N/A | 7 de noviembre de 2022 |
| **Protección de proyectos programados con contraseña** | Esta funcionalidad forma parte de la preparación para la HIPAA y se aplica solo a los clientes de Healthcare Shield.  [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=es#password) | N/A | 7 de noviembre de 2022. |

{style=&quot;table-layout:auto&quot;}

## Correcciones

* Se ha corregido un problema por el cual las últimas versiones de MacOS se denominaban incorrectamente como “Macintosh”. Con esta corrección, la dimensión del sistema operativo empezará a utilizar la numeración de las versiones de “MacOS” a partir de MacOS 11. (AN-301834)

### Otras correcciones

AN-302367; AN-302562; AN-304036

## Avisos importantes para los administradores de CJA

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| **Página de aterrizaje predeterminada** | 29 de septiembre de 2023 | La [nueva página de aterrizaje](/help/getting-started/landing.md) que se introdujo a principios de este año se convertirá en la experiencia predeterminada para todos los usuarios en **enero de 2023**. La página actual quedará obsoleta y todos tendrán que utilizar la nueva experiencia. |
| **Asignación de IP a geolocalización mejorada** | 29 de septiembre de 2022 | El proveedor de Adobe para búsquedas de IP, Digital Element, está actualizando a un nuevo conjunto de datos mejorado (NetAcuity Pulse) para la asignación de IP a geolocalización. Adobe Analytics ha pospuesto la adopción de este nuevo conjunto de datos a **enero de 2023**. La nueva base de datos será más precisa que las versiones anteriores. Algunas asignaciones de IP a regiones cambiarán o mejorarán cuando se adopte la nueva base de datos.<p> Los datos de CJA proporcionados a través del [!UICONTROL conector de origen de Analytics] también aprovecharán automáticamente las nuevas asignaciones. |
| **[!UICONTROL Detección de anomalías] condiciones de ejecución automática** | 29 de septiembre de 2022 | Hoy, [!UICONTROL Detección de anomalías] se ejecuta automáticamente en todas las columnas de tablas de forma libre de series temporales. Para garantizar que los datos estén disponibles para análisis y que los proyectos se carguen más rápido, Adobe cambiará la forma en que [!UICONTROL Detección de anomalías] se ejecuta automáticamente. A partir del **26 de octubre de 2022**, la detección de anomalías se ejecutará automáticamente solo en la primera columna de métrica de una tabla. Puede configurar la configuración de columna para que se ejecute [!UICONTROL Detección de anomalías] en otras columnas, si es necesario. |

{style=&quot;table-layout:auto&quot;}


## Recursos relacionados

* [Notas de la versión de CJA anteriores de 2022](/help/release-notes/2022.md)

* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)

* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)

* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)

* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
