---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e6b2df9ae90ef5663206e768b985749de38e263c
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 100%

---

# Notas actuales de la versión de Customer Journey Analytics (julio de 2023)

**Última actualización**: 25 de julio de 2023

Las versiones de Customer Journey Analytics operan en un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones nuevas o actualizadas

| Función | Descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Product Analytics** | Adobe Product Analytics es una nueva forma de interactuar con datos y perspectivas en canales múltiples en Customer Journey Analytics. Estas nuevas funciones permiten a los equipos de productos autogestionar los datos y las perspectivas sobre su experiencia de producto mediante flujos de trabajo de análisis guiados. Los equipos pueden:<ul><li>Entender patrones en la participación del usuario a lo largo del tiempo</li><li>Realice un seguimiento del crecimiento y la retención de la base de usuarios del producto</li><li>Identificar las áreas de fricción en el producto</li><li>Medir el impacto de las versiones de funcionalidades y su primer uso</li><li>Descubrir segmentos significativos de usuarios y usuarias con los que interactuar y a los que atender a lo largo de su recorrido de por vida con el producto</li><li>Conectarse a Analysis Workspace para realizar análisis y colaboraciones más profundos con analistas</li></ul>Adobe Product Analytics es un complemento de pago para Customer Journey Analytics. Si su organización desea que se le aprovisione para utilizar esta función, póngase en contacto con el equipo de cuentas de Adobe. [Más información](/help/guided-analysis/overview.md) | N/A | 17 de julio de 2023 |
| **Campos derivados** | Representa la versión inicial de los campos Derivados. Un campo derivado permite definir manipulaciones de datos (a menudo complejas) sobre la marcha, mediante un generador de reglas personalizable. Puede definir el campo derivado como componente (métrica o dimensión) en las vistas de datos y, a continuación, utilizar el campo derivado como componente en el Espacio de trabajo.<p>Esta versión es compatible con una plantilla de canales de marketing y las siguientes funciones:</p><ul><li>Concatenar</li><li>Caso de que</li><li>Buscar y reemplazar</li><li>Búsqueda</li><li>Análisis de URL</li></ul> <p>[Más información](/help/data-views/derived-fields/derived-fields.md)</p> | 10 de mayo de 2023 | 2 de agosto de 2023 |
| **Compatibilidad de búsqueda ampliada para datos de perfil y búsqueda** | Proporciona la posibilidad de añadir conjuntos de datos como búsquedas de campos dentro de conjuntos de datos de perfil o de búsqueda. Anteriormente, solo se admitían conjuntos de datos de eventos. [Más información](/help/connections/create-connection.md) | 21 de junio de 2023 | 12 de julio de 2023 |
| **Mejoras de Report Builder** | <ul><li>Filtre desde la celda para varios bloques de datos. Puede cambiar los filtros en varios bloques de datos desde una celda. Utilice una celda predefinida, asígnela a varios bloques de datos y actualice los datos en función de los filtros definidos en la celda. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=es)</li><li>Muestre y oculte encabezados de fila y columna. Puede mostrar u ocultar encabezados de tabla de bloques de datos, o bien encabezados de fila y columna para cambiar el formato de la tabla y alinear los bloques de datos en un informe. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block?lang=es#build-the-data-block)</li></ul> | N/A | 19 de julio de 2023 |

{style="table-layout:auto"}

## Correcciones en Customer Journey Analytics

AN-317971; AN-319234; AN-320439; AN-320519; AN-321740; AN-322444; AN-323116

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
