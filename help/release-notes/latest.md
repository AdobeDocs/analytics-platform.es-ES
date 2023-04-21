---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 64a774d9151c40ea9eadb1fb80c07db168ac8667
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 66%

---

# Notas de la versión de Customer Journey Analytics (CJA) actuales (abril de 2023)

**Última actualización**: 12 de abril de 2023

Las versiones de Customer Journey Analytics operan en un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones principales y actualizaciones

| Función | Descripción | [Inicio del despliegue](/help/release-notes/releases.md) | [Disponibilidad general](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Filtrado de filas y columnas para el streaming del conector de origen de Analytics** | El conector de origen de Analytics en Adobe Experience Platform ahora permite filtrar los datos de Analytics que se usan para rellenar perfiles en el [Perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=es). El filtrado de nivel de fila reduce el número de eventos asociados a perfiles. El filtrado a nivel de columna ayuda a reducir la riqueza de los propios eventos, lo que permite optimizar el uso de derechos de perfil. Este filtrado solo se aplica a los datos enviados al perfil del cliente en tiempo real y al [Servicio de identidad](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=es). **El filtrado no afecta a los datos que se envían al lago de datos para su uso en aplicaciones como Customer Journey Analytics**. [Más información](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es#filtering-for-profile) | N/A | 29 de marzo de 2023 |
| **Diccionario de datos de Analysis Workspace** | El diccionario de datos ayuda a los usuarios y administradores a realizar un seguimiento de los componentes y a comprenderlos mejor (dimensiones, métricas) en su entorno CJA. [Más información](/help/components/data-dictionary/data-dictionary-overview.md) | 8 de marzo de 2023 | 29 de marzo de 2023 |
| **Uso compartido de vínculos para proyectos (no se requiere inicio de sesión)** | <p>Ahora puede compartir vínculos de solo lectura a proyectos de Analysis Workspace con personas que no tienen acceso a Adobe Analytics. Esto incluye el uso compartido con personas fuera de su organización o con personas dentro de su organización que no estén aprovisionadas para CJA. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=en#share-public-link)</p> <p>Esta funcionalidad está habilitada de forma predeterminada y el administrador del sistema puede desactivarla. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#company-preferences)</p> | 26 de abril de 2023 (solo acceso beta privado) | Junio de 2023 |
| **Análisis de productos de Adobe: solo acceso beta privado** | El 21 de marzo de 2023, el Adobe anunció el Adobe de Análisis de productos , una nueva forma de interactuar con datos y perspectivas multicanal en Customer Journey Analytics. Estas nuevas funciones permiten a los equipos de productos proporcionar datos y perspectivas sobre su experiencia de producto mediante flujos de trabajo de análisis guiados &#x200B;. Los equipos pueden:<ul><li>Comprender los patrones de participación del usuario a lo largo del tiempo &#x200B;</li><li>Analizar el crecimiento de la base de usuarios &#x200B;</li><li>Identificar áreas de fricción en una secuencia de pasos&#x200B;</li><li>Medir el impacto de las versiones de funciones&#x200B;</li><li>Descubra segmentos significativos para interactuar y nutrir a lo largo de su recorrido con el &#x200B; del producto durante toda su vida</li><li>Abra en Analysis Workspace para un análisis y una colaboración más profundos con los analistas y mucho más &#x200B;</li></ul>Si es cliente de CJA y está interesado en unirse a la versión beta privada, póngase en contacto con su equipo de cuentas de Adobe. [Más información](https://business.adobe.com/products/product-analytics/adobe-product-analytics.html) | N/A | 17 de julio de 2023 |

{style="table-layout:auto"}

## Correcciones en Customer Journey Analytics

AN-313118; AN-313390; AN-314135; AN-316381; AN-316811

## Avisos importantes para los administradores de CJA

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| N/A | N/A | N/A |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de la versión de CJA anteriores de 2023](/help/release-notes/2023.md)
* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)
* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)
* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
