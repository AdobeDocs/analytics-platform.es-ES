---
title: Opciones de inserción de datos para Customer Journey Analytics
description: Comprender las distintas formas de ingerir datos en Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 32dd6194ab2777652c3fb7df5fadd42395a0697d
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 31%

---


# Opciones de inserción de datos para Customer Journey Analytics

Tiene una serie de opciones para la ingesta de datos en Customer Journey Analytics. Algunos de ellos suponen que desea mover los datos tradicionales de Adobe Analytics, algunos de los cuales suponen que los ingiere directamente desde Adobe Experience Platform. Esta referencia proporciona pasos de alto nivel a seguir.

## Ingestar datos de Adobe Analytics tradicional

Este flujo de trabajo utiliza el conector de datos de Adobe Analytics y varía en función de si utiliza la DTM o Launch como Administrador de etiquetas.

### Mediante la administración dinámica de etiquetas (DTM)

1. [Crear una capa de datos](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html), si aún no lo ha hecho. Una capa de datos es un marco de objetos de JavaScript del sitio que contiene todos los valores de variables utilizados en la implementación. Permite un mayor control y un mantenimiento más sencillo en la implementación.
1. Usar [DTM](https://docs.adobe.com/content/help/es-ES/analytics/implementation/other/dtm/dtm-implementation-overview.html) para implementar código en el sitio para la recopilación de datos, si aún no lo ha hecho. Dynamic Tag Management proporciona una única capa de datos que transmite datos de múltiples fuentes.
1. Crear un [Conector de origen de Adobe Analytics](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) en Adobe Experience Platform. Este conector de origen ingesta los datos de Analytics en un Experience Platform en un marco normalizado denominado [Sistema de modelo de datos de experiencia (XDM)](https://docs.adobe.com/content/help/es-ES/experience-platform/xdm/home.html).
1. Usar [Customer Journey Analytics](https://docs.adobe.com/content/help/es-ES/analytics-platform/using/cja-overview/cja-getting-started.html) para crear una o varias conexiones y vistas de datos que informarán al sistema de informes entre canales.

### Vía Launch

1. [Crear una capa de datos](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html), si aún no lo ha hecho. Una capa de datos es un marco de objetos de JavaScript del sitio que contiene todos los valores de variables utilizados en la implementación. Permite un mayor control y un mantenimiento más sencillo en la implementación.
1. Usar [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/analytics/implementation/launch/overview.html) para implementar código en el sitio para la recopilación de datos, si aún no lo ha hecho. Launch es una solución de administración de etiquetas que le permite implementar código de Analytics junto con otros requisitos de etiquetado. Inicie integraciones de ofertas con otras soluciones y productos, y le permite implementar código personalizado. Todas estas tareas se pueden realizar sin depender de ningún equipo de desarrollo de la organización para actualizar el código del sitio..
1. Crear un [Conector de origen de Adobe Analytics](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) en Adobe Experience Platform. Este conector de origen ingesta los datos de Analytics en un Experience Platform en un marco normalizado denominado [Sistema de modelo de datos de experiencia (XDM)](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).
1. Usar [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) para crear una o varias conexiones y vistas de datos que informarán al sistema de informes entre canales.

## Ingesta de datos desde el SDK web de AEP

Por determinar

### A través de Experience Edge

Por determinar

### Vía Launch

Por determinar

## Ingesta por lotes e ingestión por flujo continuo

Por determinar

## Datos de Google Analytics de entrada

Por determinar

## Ingesta de datos mediante la API de ingestión masiva

Por determinar