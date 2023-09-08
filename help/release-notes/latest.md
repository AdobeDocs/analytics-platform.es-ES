---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 8f299dad39678047d362291cfe8a2a3c116071dd
workflow-type: ht
source-wordcount: '571'
ht-degree: 100%

---

# Notas actuales de la versión de Adobe Customer Journey Analytics (agosto de 2023)

**Última actualización**: 24 de agosto de 2023

Estas notas de la versión abarcan el periodo de lanzamiento del 9 de agosto al 13 de septiembre de 2023. Las versiones de Customer Journey Analytics operan en un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Mejoras de Report Builder** | <ul><li>Puede descargar una tarea programada desde la pestaña Libros y, a continuación, asignarle un título, guardarla y compartirla. [Más información](/help/report-builder/schedule-reportbuilder.md)</li><li>La fecha de inicio como dimensión le permite mostrar la fecha de inicio del bloque de datos como dimensión en la salida del bloque de datos. [Más información](/help/report-builder/create-a-data-block.md) </li></ul> | N/A | 17 de agosto de 2023 |
| **Conversión de moneda** | El recorrido del cliente añade la capacidad de admitir varias divisas. Puede convertir una moneda a otra en la configuración de vistas de datos. [Más información](/help/data-views/component-settings/format.md) | N/A | 30 de agosto de 2023 |
| **Compatibilidad con clasificaciones A4T en el conector de origen de Analytics** | Se va a agregar un ID de correlación para facilitar la unión de los datos de clasificación para las actividades y los eventos de experiencia de Adobe Target. | N/A | 11 de septiembre de 2023 |
| **Administrador de actividades de creación de informes** | Proporciona a los administradores una visibilidad detallada del consumo de creación de informes para cada conexión, lo que permite a los administradores diagnosticar fácilmente y luego corregir los problemas de capacidad durante las horas de mayor actividad de creación de informes. | N/A | 12 de septiembre de 2023 |
| **Acceso de Power BI y Tableau a vistas de datos de Customer Journey Analytics** | El conector SQL de Adobe Customer Journey Analytics habilita el acceso SQL a las vistas de datos que ha definido en Customer Journey Analytics. Los ingenieros y analistas de datos más familiarizados con Power BI, Tableau u otras herramientas de inteligencia y visualización empresarial ahora pueden crear informes y paneles basados en las mismas vistas de datos que los usuarios de Customer Journey Analytics utilizan para sus proyectos de Analysis Workspace. [Más información](/help/data-views/sql-connector.md) | N/A | 12 de septiembre de 2023 |

{style="table-layout:auto"}

## Correcciones en Customer Journey Analytics

AN-309141; AN-319198; AN-324576; AN-324939; AN-325138; AN-325554

## Avisos importantes para los administradores de Customer Journey Analytics

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| **Cambios en el modo en que Customer Journey Analytics procesa los datos** | 22 de junio de 2023 | Recientemente hemos cambiado la forma en que procesamos los datos en Customer Journey Analytics.<ul><li>Se transmite cualquier dato de evento con una marca de tiempo de menos de 24 horas.</li><li>Cualquier dato de evento con una marca de tiempo de más de 24 horas (incluso si está en el mismo lote que los datos más recientes) se considera relleno y se ingiere con una prioridad inferior.</li></ul> |

{style="table-layout:auto"}

## Avisos de final de la vida útil

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Migración a las credenciales de servidor a servidor de Adobe I/O OAuth** | 11 de mayo de 2023 | Los clientes de la API de Adobe Analytics, la API de Customer Journey Analytics y Livestream que usan las credenciales de JWT de Adobe I/O deben migrar a las credenciales de servidor a servidor de Adobe I/O OAuth el **1 de enero de 2025**. Adobe I/O no permitirá que se creen nuevas credenciales de JWT a partir del 1 de mayo de 2024. Los clientes que utilizan JWT deben crear una nueva credencial de servidor a servidor OAuth o migrar su credencial JWT existente a una credencial de servidor a servidor OAuth. Los clientes también deben actualizar sus aplicaciones cliente para utilizar las nuevas credenciales de servidor a servidor de OAuth. <ul><li>[Migración de credenciales de cuenta de servicio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Uso de las nuevas credenciales de servidor a servidor de OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Preguntas frecuentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## Recursos relacionados

* [Notas de la versión anteriores de Customer Journey Analytics de 2023](/help/release-notes/2023.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
