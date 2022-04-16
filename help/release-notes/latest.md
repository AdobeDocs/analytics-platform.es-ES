---
title: Ver las notas de la versión de Customer Journey Analytics actuales
description: Últimas notas de la versión de CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 56f62d8af96e64a6867e38a9701219bcefc62a6a
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 15%

---

# Notas de la versión del Customer Journey Analytics actual (CJA) (abril de 2022)

>[!NOTE]
>
>Esta página contiene información previa al lanzamiento que está sujeta a cambios.

**Última actualización**: 13 de abril de 2022

## Funciones principales

| Función | Descripción | [Fecha objetivo](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| subcadenas de Dimension | Proporciona varios métodos para extraer la parte deseada de una cadena para utilizarla como elementos de dimensión. Esta función también le permite tratar una dimensión de cadena como una matriz si la cadena contiene valores delimitados. [Más información](../data-views/component-settings/substring.md) | 20 de abril de 2022 |
| Preparación de datos para el conector de origen de Analytics | La variable [Conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es) ahora está integrado con la variable [Preparación de datos](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html) funciones proporcionadas por Adobe Experience Platform. Los clientes de Adobe Real-time Customer Data Platform (RTCDP), CJA y Adobe Journey Optimizer (AJO) ahora pueden ampliar el grupo de campos de Analytics con grupos de campos adicionales. También pueden aprovechar más de 100 operadores de preparación de datos para enriquecer los datos de Analytics durante la ingesta en Adobe Experience Platform (AEP). Los clientes de RTCDP ahora pueden habilitar varios grupos de informes habilitados para la preparación de datos para el perfil.<p>Los clientes de CJA que consumen varios grupos de informes a través del conector de origen de Analytics ahora disponen de un medio para desactivar las diferencias de columna entre los grupos de informes. Por ejemplo, si &quot;Término de búsqueda&quot; está almacenado en `eVar1` en un grupo de informes y en `eVar2` en otro grupo de informes, con Preparación de datos puede ampliar el grupo de campos de Analytics con una nueva columna que combine los valores de las dos eVars. | 25 de abril de 2022 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Actualizaciones de la documentación de Customer Journey Analytics](/help/release-notes/doc-changes.md)
