---
description: Explica qué factores influyen en la coherencia de las métricas y los recuentos de pertenencia a audiencias entre Real-time Customer Data Platform (CDP en tiempo real) y CJA.
title: Coherencia de métricas y recuentos de miembros de audiencia entre CDP en tiempo real y CJA
role: Admin
feature: CJA Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 769eef205df32865874753859ce79e573db40641
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 0%

---


# Coherencia de métricas y recuentos de miembros de audiencia entre CDP en tiempo real y CJA

En escenarios reales, no se puede garantizar la coherencia de las métricas y los recuentos de miembros de audiencia en Real-time Customer Data Platform (CDP en tiempo real) y Customer Journey Analytics (CJA). Este documento explica por qué.

Al comparar los recuentos de miembros de la audiencia entre CDP en tiempo real y CJA, es importante tener en cuenta los diferentes propósitos de estas dos herramientas. CDP en tiempo real utiliza datos de perfil del cliente para dirigir experiencias digitales a consumidores individuales, mientras que CJA está diseñado para ayudar a los usuarios a comprender los patrones en métricas y segmentos clave del negocio. Aunque la publicación de audiencias de CJA a CDP en tiempo real permite al usuario de estas herramientas &quot;activar&quot; de forma fácil y nativa una perspectiva, aprovechando las lecciones obtenidas en CJA, estas herramientas sirven para propósitos fundamentalmente diferentes.

## Diferencias en las configuraciones de identidad

CDP y CJA en tiempo real no comparten la misma definición de una persona en la actualidad. CDP en tiempo real se basa completamente en la información del [Gráfico de identidad](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=en) para crear un perfil combinado.

CJA se puede configurar para usar [Análisis en canales múltiples](/help/connections/cca/overview.md) que extrae identificadores de conjuntos de datos en el lago de datos y aplica lógica personalizada para vincularlos juntos.

En el futuro, CJA podrá utilizar Identity Graph.

## Diferencias en la configuración del conjunto de datos

Puede elegir poner algunos datos en CDP en tiempo real y algunos en CJA; a menudo, los clientes eligen incorporar más datos históricos en CJA de lo que es relevante para CDP en tiempo real. Otros conjuntos de datos pueden ser más relevantes para CDP en tiempo real que para CJA.

## Diferencias en la configuración de procesamiento

CJA permite realizar amplias modificaciones de los datos en el momento de la consulta, como la combinación de campos, la división de campos entre sí y otras manipulaciones como inclusiones/exclusiones, subcadenas, deduplicación de valores, sesionización y filtrado en el nivel de fila.

CDP en tiempo real ofrece un conjunto diferente de herramientas de manipulación de datos. Se aplica [combinar directivas](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en) para determinar qué datos se priorizarán y qué datos se combinarán para crear una vista unificada de una persona.

## Diferencias en TTL (Tiempo de vida) e ingesta de datos

Incluso si los conjuntos de datos en tiempo real CDP y CJA son los mismos, CDP en tiempo real solo puede mantener una ventana muy limitada de historial. Por el contrario, es probable que CJA tenga años de datos. Además:

* Los clientes de CJA y CDP en tiempo real pueden establecer ventanas de retención personalizadas para datos, independientes entre sí.

* CDP y CJA en tiempo real tienen una lógica diferente para la ingesta de datos. CJA ignora los registros sin ID de persona o marca de tiempo y tiene límites estrictos con respecto al número de registros que puede tener un solo perfil o persona.

* Los clientes de CDP en tiempo real obtienen 7 días de acceso a los datos en el lago, principalmente para facilitar la incorporación de datos en el perfil y para consultas ad hoc.

* No hay TTLs para los datos en el lago para los clientes de CJA. Sin embargo, los usuarios de CJA pueden establecer ellos mismos una ventana de retención personalizada en CJA al crear una conexión.

* El Almacenamiento de perfiles en CDP en tiempo real permite configurar TTL para el cliente. Los clientes pueden cambiar este TTL a lo que necesiten para permanecer dentro de sus derechos de licencia.

## Diferencias en la latencia del consumo de datos

CJa todavía no tiene las capacidades en tiempo real de CDP en tiempo real y, como resultado, la creación de informes de CJA incluye cierta latencia antes de que los datos estén disponibles para la creación de informes o audiencias. CDP en tiempo real procesa los datos a través de diferentes sistemas que tienen una latencia diferente.
