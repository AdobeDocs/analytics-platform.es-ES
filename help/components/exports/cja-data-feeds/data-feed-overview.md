---
description: Aprenda a utilizar las fuentes de datos para obtener datos sin procesar de Customer Journey Analytics. Descubra los requisitos previos para utilizar fuentes de datos y qué hacer a continuación.
keywords: flujo de navegación;fuente de datos;fuente de datos;Fuente de datos
title: Información general sobre las fuentes de datos de Analytics
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
source-git-commit: 5e77857ca846767e3b9e7479baa4a4b18c6e3c8f
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 21%

---

# Resumen de fuentes de datos

Las fuentes de datos son una forma eficaz de obtener datos sin procesar de Customer Journey Analytics. Puede utilizar estos datos sin procesar en otras plataformas fuera de Adobe según convenga a su organización. Los datos se entregan en lotes por hora al final de cada hora o en lotes diarios al final de cada día.

## Requisitos previos

Asegúrese de cumplir todos los requisitos antes de utilizar fuentes de datos:

* Implementación en funcionamiento con datos que se están ingiriendo en Adobe Customer Journey Analytics <!-- For more information, see Data ingestion overview - add link -->
* Su cuenta es un administrador de productos de Analytics o pertenece a un perfil de producto con acceso a fuentes de datos <!--???-->
* Un contenedor configurado en {DNL Amazon S3}, {DNL Google Cloud Platform}, {DNL Azure RBAC} o {DNL Azure SAS}

## Introducción

Para empezar a utilizar fuentes de datos en Customer Journey Analytics, primero debe comprender cómo difieren las fuentes de datos en Customer Journey Analytics de las fuentes de datos en Adobe Analytics. Después de comprender las diferencias, puede asignar fuentes de datos de Adobe Analytics a Customer Journey Analytics y, a continuación, empezar a crear una fuente de datos.

1. [Comprenda las diferencias entre las fuentes de datos en Customer Journey Analytics y Adobe Analytics](/help/components/exports/cja-data-feeds/df-comparison.md).

1. [Asigne columnas de fuentes de datos de Adobe Analytics a Customer Journey Analytics](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md).

1. [Crear una fuente de datos](/help/components/exports/cja-data-feeds/create-feed.md).
