---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e9d2bfb4f4c4aa3ac96d0300e537376a1ef7821a
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 39%

---

# Notas de la versión actuales de Adobe Customer Journey Analytics (julio de 2023)

**Última actualización**: 10 de julio de 2023

Las versiones de Adobe Customer Journey Analytics funcionan de forma [modelo de envío continuo](releases.md) lo que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Product Analytics** | Un nuevo tipo de proyecto que permite a los equipos de productos autoabastecer rápidamente sus necesidades de datos para que puedan tomar decisiones de productos más basadas en datos. Se basa en los flujos de trabajo de conexión y vista de datos existentes en Customer Journey Analytics. No es necesario realizar cambios de implementación o configuración. [Más información](/help/guided-analysis/overview.md)<p>El Product Analytics es un complemento de pago para el Customer Journey Analytics. Si su organización desea que se le aprovisione para utilizar esta función, póngase en contacto con el equipo de cuenta de Adobe. | N/A | 17 de julio de 2023 |
| **Campos derivados** | Representa la versión inicial de los campos Derivados. Un campo derivado permite definir manipulaciones de datos (a menudo complejas) sobre la marcha, mediante un generador de reglas personalizable. Puede definir aún más el campo derivado como un componente (métrica o dimensión) en las vistas de datos y, a continuación, utilizar el campo derivado como un componente en Workspace.<p>Esta versión es compatible con una plantilla de canales de marketing y las siguientes funciones:</p><ul><li>Concatenar</li><li>Caso de que</li><li>Buscar y reemplazar</li><li>Búsqueda</li><li>Análisis de URL</li></ul> <p>[Más información](/help/data-views/derived-fields/derived-fields.md)</p> | 10 de mayo de 2023 | 2 de agosto de 2023 |
| **Compatibilidad de búsqueda ampliada para datos de perfil y búsqueda** | Proporciona la capacidad de agregar conjuntos de datos como búsquedas de campos dentro de conjuntos de datos de perfil o búsqueda. Anteriormente, solo se admitían conjuntos de datos de eventos. [Más información] | 21 de junio de 2023 | 12 de julio de 2023 |
| **Mejoras del Report Builder** | <ul><li>Filtre desde la celda para varios bloques de datos. Puede cambiar los filtros en varios bloques de datos desde una celda. Utilice una celda predefinida, asígnela a varios bloques de datos y actualice los datos en función de los filtros definidos en la celda. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=en)</li><li>Mostrar y ocultar encabezados de fila y columna. Puede mostrar u ocultar encabezados de tabla de bloques de datos, o encabezados de fila y columna para cambiar el formato de la tabla y alinear los bloques de datos en un informe. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html?lang=en#build-the-data-block)</li></ul> | N/A | 19 de julio de 2023 |
| **Búsquedas geográficas de Experience Edge** | Adobe Experience Edge está agregando un servicio de búsqueda geográfica que proporciona datos geográficos unificados a todos los usuarios de Experience Edge (Adobe Analytics, Customer Journey Analytics, Adobe Target, Adobe Medium Analytics, Adobe Experience Platform, etc.). | N/A | 26 de julio de 2023 |

{style="table-layout:auto"}

## Correcciones en Customer Journey Analytics

AN-317971; AN-319234; AN-320439; AN-320519; AN-321740; AN-322444; AN-323116

## Avisos importantes para los administradores de Customer Journey Analytics

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| **Cambios en el modo en que el Customer Journey Analytics procesa los datos** | 22 de junio de 2023 | Recientemente hemos cambiado la forma en que procesamos los datos en Customer Journey Analytics.<ul><li>Se transmite cualquier dato de evento con una marca de tiempo de menos de 24 horas.</li><li>Cualquier dato de evento con una marca de tiempo de más de 24 horas (incluso si está en el mismo lote que los datos más recientes) se considera relleno y se ingiere con una prioridad inferior.</li></ul> |

{style="table-layout:auto"}

## Avisos de final de la vida útil

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Migración a las credenciales de servidor a servidor de Adobe I/O OAuth** | 11 de mayo de 2023 | Los clientes de la API de Adobe Analytics, la API de Customer Journey Analytics y Livestream que utilizan las credenciales de JWT de AdobeIO deben migrar a las credenciales de servidor a servidor de OAuth de AdobeIO de **1 de enero de 2025**. Adobe I/O no permitirá que se creen nuevas credenciales de JWT a partir del 1 de mayo de 2024. Los clientes que utilizan JWT deben crear una nueva credencial de servidor a servidor OAuth o migrar su credencial JWT existente a una credencial de servidor a servidor OAuth. Los clientes también deben actualizar sus aplicaciones cliente para utilizar las nuevas credenciales de servidor a servidor de OAuth. <ul><li>[Migración de credenciales de cuenta de servicio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Uso de las nuevas credenciales de servidor a servidor de OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Preguntas frecuentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## Recursos relacionados

* [Notas de la versión anteriores de Customer Journey Analytics de 2023](/help/release-notes/2023.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
