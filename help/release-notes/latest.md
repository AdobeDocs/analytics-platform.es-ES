---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 4de95c6c869e25a0301990669b7c8409ab025350
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 58%

---

# Notas de la versión actuales de Adobe Customer Journey Analytics (septiembre de 2023)

**Última actualización**: 13 de septiembre de 2023

Estas notas de la versión abarcan el periodo de lanzamiento del 13 de septiembre de 2023 al 3 de octubre de 2023. Las versiones de Customer Journey Analytics operan en un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Compatibilidad con clasificaciones A4T en el conector de origen de Analytics** | Compatibilidad con nuevos `correlationID` campo para Adobe Analytics | El `_experience.decisioning.propositions.scopeDetails.correlationID` El campo ahora está disponible en el esquema del conector de origen de Adobe Analytics. Este campo se utiliza para clasificaciones de A4T y se rellenará a partir de septiembre de 2023. | | N/A | 12 de septiembre de 2023 |
| **Actualizaciones en campos derivados** | Se han realizado las siguientes actualizaciones en la funcionalidad de campos derivados:<ul><li>El [!UICONTROL Búsqueda] se ha cambiado el nombre de la función a [!UICONTROL Clasificar], con opciones adicionales para cargar datos CSV. **(Versiones del 27 de septiembre de 2023)**</li><li>Hay funciones adicionales disponibles para utilizar al definir un campo derivado: [!UICONTROL Recortar], [!UICONTROL Minúsculas] y [!UICONTROL Búsqueda].</li><li>Las definiciones de campo derivadas ahora también admiten campos de [!UICONTROL Búsqueda] y [!UICONTROL Perfil] conjuntos de datos.</li></ul>[Más información](/help/data-views/derived-fields/derived-fields.md) | N/A | 13 de septiembre de 2023 |
| **Nuevas funciones de Adobe Product Analytics** | <ul><li>**Detección de anomalías**: Compare eventos con valores esperados derivados de tendencias históricas. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/trends/usage.html)</li><li>**Tendencias Vista de frecuencia de uso**: mida la adopción de las funciones por frecuencia de uso. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/trends/frequency.html)</li><li>**Preferencias de usuario**: configure una serie de preferencias de usuario, como paletas de color y formato de número. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=es)</li></ul> | N/A | 18 de septiembre de 2023 |
| **Búsquedas de dispositivos de Experience Edge** | Habilite la recopilación automática de datos de tipo de dispositivo a través de la red de Experience Platform Edge. Este servicio Experience Edge beneficia al Customer Journey Analytics junto con otras aplicaciones de Experience Platform. (Vínculo de documentación a continuación) | N/A | 27 de septiembre de 2023 |

{style="table-layout:auto"}

## Correcciones en Customer Journey Analytics

AN-310972; AN-319509; AN-322245; AN-323411; AN-323719; AN-326101; AN-326125; AN-326888


## Avisos importantes para los administradores de Customer Journey Analytics

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| N/A | N/A | N/A |

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
