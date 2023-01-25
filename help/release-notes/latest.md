---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: ddba0cdee1956048ba1875b49e8f2b77085c46da
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 40%

---

# Notas de la versión del Customer Journey Analytics actual (CJA) (enero de 2023)

**Última actualización**: 24 de enero de 2023

Las versiones de Customer Journey Analytics operan en un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funciones. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Funciones principales y actualizaciones

| Función | Descripción | [Inicio del despliegue](/help/release-notes/releases.md) | [Disponibilidad general](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Compatibilidad con matrices de objetos para conjuntos de datos de perfil y búsqueda** | Los conjuntos de datos de perfil y los conjuntos de datos de búsqueda ahora admiten matrices de objetos para su uso en CJA. | 11 de enero de 2023 | 19 de enero de 2023 |
| **Carpetas en el Espacio de trabajo** | Las carpetas le ayudan a organizar y categorizar sus proyectos para una mejor recuperación y acceso. Además, un **[!UICONTROL Empresa]** permite a los administradores crear y compartir contenido fácilmente con todos los usuarios de Workspace.  [Más información](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.html?lang=es) | N/A | 11 de enero de 2023 |
| **Página de aterrizaje predeterminada** | La variable [nueva página de aterrizaje](/help/getting-started/landing.md) que se introdujo a principios de 2022 se convertirá en la experiencia predeterminada para todos los usuarios de **11 de enero de 2023**. La página de aterrizaje heredada quedará obsoleta y todos tendrán que utilizar la nueva experiencia. | N/A | 11 de enero de 2023 |
| **Página Administrador de proyectos en desuso** | Con el lanzamiento de la nueva página de aterrizaje, hemos desaprobado el **[!UICONTROL Administrador de proyectos]** como aparece en **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Componentes]**. La nueva página de aterrizaje tiene todas las funciones de la antigua página Administrador de proyectos y más.  [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=en#deprecate-pm-page) | N/A | 11 de enero de 2023 |
| **Programar libros en el Report Builder** | En Customer Journey Analytics, puede crear programaciones para enviar libros a intervalos regulares. Ahora los destinatarios pueden recibir las actualizaciones más recientes de sus libros de trabajo de forma regular.  [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/schedule-reportbuilder.html) | N/A | 11 de enero de 2023 |
| **Guardar automáticamente nuevos proyectos** | Analysis Workspace ahora guarda automáticamente los proyectos recién creados. Si, por cualquier motivo, pierde de forma inesperada el acceso a un proyecto recién creado antes de guardarlo manualmente, ya está disponible una versión de recuperación del proyecto. Anteriormente, los proyectos se guardaban automáticamente solo después de guardarse inicialmente manualmente.  [Más información](/help/analysis-workspace/build-workspace-project/save-projects.md) | N/A | 11 de enero de 2023 |
| **Preferencias de usuario mejoradas** | Ahora puede configurar preferencias adicionales a nivel de usuario (en [!UICONTROL Componentes] > [!UICONTROL Preferencias]). Al establecer las preferencias de usuario, las selecciones se extienden a lo largo de los proyectos, tablas y visualizaciones. La página Preferencias ahora contiene las siguientes pestañas nuevas, cada una de las cuales contiene muchas opciones de configuración nuevas:<ul><li>Tabla de forma libre</li><li>Visualizaciones>/li></ul>  Además, ahora hay más preferencias disponibles en el **[!UICONTROL General]** y **[!UICONTROL Proyecto]** pestañas.<p>Anteriormente, muchas de estas preferencias solo se podían configurar para proyectos, tablas y visualizaciones individuales.  [Más información](/help/analysis-workspace/user-preferences.md) | N/A | 11 de enero de 2023 |

{style=&quot;table-layout:auto&quot;}

## Correcciones

AN-287349; AN-301684; AN-305491; AN-305769; AN-307912

## Avisos importantes para los administradores de CJA

| Aviso | Aviso añadido o actualizado | Descripción |
| --- | --- | --- |
| **Asignación de IP a geolocalización mejorada** | 29 de septiembre de 2022 | El proveedor de Adobe para búsquedas de IP, Digital Element, está actualizando a un nuevo conjunto de datos mejorado (NetAcuity Pulse) para la asignación de IP a geolocalización. Adobe Analytics ha pospuesto la adopción de este nuevo conjunto de datos a **11 de enero de 2023**. La nueva base de datos será más precisa que las versiones anteriores. Algunas asignaciones de IP a regiones cambiarán o mejorarán cuando se adopte la nueva base de datos.<p> Los datos de CJA proporcionados a través del [!UICONTROL conector de origen de Analytics] también aprovecharán automáticamente las nuevas asignaciones. |

{style=&quot;table-layout:auto&quot;}


## Recursos relacionados

* [Notas de la versión de CJA anteriores de 2022](/help/release-notes/2022.md)

* [Notas de la versión de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)

* [Notas de la versión de Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=es)

* [Notas de la versión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=es)

* [Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
