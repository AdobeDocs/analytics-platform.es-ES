---
title: Configuración de datos de Google Analytics de flujo continuo en Adobe Experience Platform
description: Obtenga información sobre cómo configurar la implementación para enviar una capa de datos de Google a Adobe Experience Platform
source-git-commit: 17b9e14e58f5bd2f4ec995de54989b00c26076f2
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 2%

---

# Configuración de datos de Google Analytics de flujo continuo en Adobe Experience Platform

Esta página se centra en cómo introducir los datos de los Google Analytics activos en Adobe Experience Platform, lo que le permite hacer referencia a ese conjunto de datos en una vista de datos dentro de un Customer Journey Analytics. Puede combinar los pasos de esta página con [Ingesta de datos históricos de Google Analytics en Adobe Experience Platform](backfill.md), que genera un conjunto de datos que contiene datos históricos. Combine un conjunto de datos de flujo continuo con un conjunto de datos de relleno para obtener una vista perfecta de los datos pasados y presentes en el Customer Journey Analytics.

La configuración de la recopilación de datos implica los siguientes pasos:

1. Implementación [Etiquetas para Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=es). Consulte la [Guía de inicio rápido](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) para obtener una implementación básica en funcionamiento.
1. Instale el [Extensión de la capa de datos de Google](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html). Esta extensión actúa como alternativa a la instalación de la extensión del SDK web, orientado específicamente a una capa de datos de Google.
1. [Crear un conjunto de datos](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) en la recopilación de datos de Adobe Experience Platform. Configure el almacén de datos para enviar datos a Adobe Experience Platform. Actualmente debe asignar cada objeto de capa de datos de Google a un campo XDM aplicable aquí. Adobe planea simplificar este flujo de trabajo de asignación en el futuro.

Una vez que implemente y publique las etiquetas deseadas en el sitio, puede continuar con [Crear una conexión](/help/connections/create-connection.md), luego [Creación de una vista de datos](/help/data-views/create-dataview.md).
