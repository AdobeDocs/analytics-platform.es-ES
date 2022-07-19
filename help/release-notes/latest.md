---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: d642b17baa93c3b3533a7e1b4fb966cb66f22173
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Notas de la versión del Customer Journey Analytics actual (CJA) (julio de 2022)

**Última actualización**: 13 de julio de 2022

>[!NOTE]
>
>Esta página contiene información previa al lanzamiento y está sujeta a cambios.

## Funciones principales

| Función | Descripción | [Fecha objetivo](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| Informes de primera sesión frente a repetida | Ahora puede descubrir si una sesión en particular fue la primera sesión de un usuario. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) | 20 de julio de 2022 |
| Compatibilidad con campos numéricos como claves de búsqueda y valores de búsqueda | Resulta útil si desea clasificar valores de cadena con un campo numérico como, por ejemplo, COGS o margen en un SKU de producto. Al permitir métricas de búsquedas, puede obtener estos puntos de datos en los informes. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=es#numeric) | 20 de julio de 2022 |

## Correcciones

AN-288455; AN-288828; AN-289323

## Avisos importantes para los administradores de CJA

| Aviso | Añadido o actualizado | Descripción |
| --- | --- | --- |
| Asignación de IP a geolocalización mejorada | 11 de julio de 2022 | El proveedor de Adobes para búsquedas de IP, Digital Element, está actualizando a un nuevo conjunto de datos mejorado (NetAcuity Pulse) para la asignación de IP a geolocalización. Adobe Analytics adoptará este nuevo conjunto de datos en el intervalo de tiempo de octubre de 2022. La nueva base de datos será más precisa que las versiones anteriores. Algunas asignaciones de IP a regiones cambiarán o mejorarán cuando se adopte la nueva base de datos.<p> Los datos de CJA proporcionados a través del conector de origen de Analytics también aprovecharán automáticamente las nuevas asignaciones. |

>[!MORELIKETHIS]
>[Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
