---
title: Configuración del streaming de datos de Google Analytics
description: Obtenga información sobre cómo configurar la implementación para enviar una capa de datos de Google a Adobe Experience Platform
exl-id: 58854f4b-ae28-424e-a2cf-0e76219cb802
feature: Use Cases
role: Admin
source-git-commit: 8262539078c57e32bc3195ef669325fa4889bea0
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 89%

---

# Configuración del streaming de datos de Google Analytics

Esta página se centra en cómo introducir los datos activos de Google Analytics en Adobe Experience Platform, lo que le permite hacer referencia a ese conjunto de datos en una vista de datos dentro de Customer Journey Analytics. Puede combinar los pasos de esta página con [Ingesta de datos históricos de Google Analytics en Adobe Experience Platform](backfill.md), que genera un conjunto de datos que contiene los datos históricos. Combine un conjunto de datos de streaming con un conjunto de datos de relleno para obtener una vista perfecta de los datos pasados y presentes en Customer Journey Analytics.

La configuración de la recopilación de datos implica los siguientes pasos:

1. Implementación de [Etiquetas para Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=es). Consulte la [Guía de inicio rápido](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=es) para poner en marcha una implementación básica.
1. Instale la [Extensión de la capa de datos de Google](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html?lang=es). Esta extensión actúa como una alternativa a la instalación de la extensión del SDK web, orientado específicamente a una capa de datos de Google.
1. [Crear una secuencia de datos](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=es) en la recopilación de datos de Adobe Experience Platform. Configure la secuencia de datos para enviar datos a Adobe Experience Platform. Actualmente, debe asignar cada objeto de capa de datos de Google a un campo XDM aplicable aquí. Adobe planea simplificar este flujo de trabajo de asignación en el futuro.

Una vez que implemente y publique las etiquetas deseadas en su sitio, puede continuar con [crear una conexión](/help/connections/create-connection.md) y luego [crear una vista de datos](/help/data-views/create-dataview.md).
