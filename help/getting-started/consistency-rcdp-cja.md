---
description: Explica qué factores influyen en la coherencia de las métricas y los recuentos de pertenencia a audiencias entre Real-time Customer Data Platform (Real-time CDP) y CJA.
title: Coherencia de métricas y recuentos de miembros de audiencia entre Real-time CDP y CJA
role: Admin
feature: CJA Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 769eef205df32865874753859ce79e573db40641
workflow-type: ht
source-wordcount: '577'
ht-degree: 100%

---


# Coherencia de métricas y recuentos de miembros de audiencia entre Real-time CDP y CJA

En situaciones reales, no se puede garantizar la coherencia de las métricas y los recuentos de miembros de audiencia en Real-time Customer Data Platform (Real-time CDP) y Customer Journey Analytics (CJA). Este documento explica por qué.

Al comparar los recuentos de miembros de audiencia entre Real-time CDP y CJA, es importante tener en cuenta los diferentes propósitos de estas dos herramientas. Real-time CDP utiliza datos de perfil del cliente para dirigir las experiencias digitales a consumidores individuales, mientras que CJA está diseñado para ayudar a los usuarios a comprender los patrones en métricas y segmentos clave del negocio. Aunque la publicación de audiencias de CJA a Real-time CDP permite al usuario de estas herramientas “activar” de forma fácil y nativa una perspectiva, aprovechando las lecciones aprendidas en CJA, estas herramientas sirven para propósitos fundamentalmente diferentes.

## Diferencias en las configuraciones de identidad

Real-time CDP y CJA no comparten la misma definición de una persona en la actualidad. Real-time CDP se basa completamente en la información de [Identity Graph](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identifies/understanding-identity-and-identity-graphs.html?lang=es) para crear un perfil combinado.

CJA se puede configurar para usar [Cross-Channel Analytics](/help/connections/cca/overview.md), que extrae identificadores de conjuntos de datos en el lago de datos y aplica lógica personalizada para vincularlos juntos.

En el futuro, CJA podrá utilizar Identity Graph.

## Diferencias en la configuración del conjunto de datos

Puede elegir poner algunos datos en Real-time CDP y otros en CJA; a menudo, los clientes eligen incorporar más datos históricos en CJA de lo que es relevante para Real-time CDP. Otros conjuntos de datos pueden ser más relevantes para Real-time CDP que para CJA.

## Diferencias en la configuración de procesamiento

CJA permite realizar amplias modificaciones de los datos en el momento de la consulta, como la combinación de campos, la división de campos entre sí y otras manipulaciones como inclusiones/exclusiones, subcadenas, deduplicación de valores, sesionización y filtrado en el nivel de fila.

Real-time CDP ofrece un conjunto diferente de herramientas de manipulación de datos. Se aplica [combinar directivas](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=es) para determinar qué datos se priorizarán y qué datos se combinarán para crear una vista unificada de una persona.

## Diferencias en TTL (Tiempo de vida) e incorporación de datos

Incluso si los conjuntos de datos de Real-time CDP y CJA son los mismos, Real-time CDP solo puede mantener una ventana muy limitada de historial. Por el contrario, es probable que CJA tenga muchos años de datos. Además:

* Los clientes de CJA y Real-time CDP pueden establecer ventanas de retención personalizadas para datos, independientes entre sí.

* CJA y Real-time CDP tienen una lógica diferente para la ingesta de datos. CJA ignora los registros sin ID de persona o marca de tiempo y tiene límites estrictos con respecto al número de registros que puede tener un solo perfil o una persona.

* Los clientes de Real-time CDP obtienen siete días de acceso a los datos en el lago, principalmente para facilitar la incorporación de datos en el perfil y para consultas ad hoc.

* No hay TTL para los datos en el lago para los clientes de CJA. Sin embargo, los usuarios de CJA pueden establecer ellos mismos una ventana de retención personalizada en CJA al crear una conexión.

* El Almacenamiento de perfiles en Real-time CDP permite configurar los TTL para el cliente. Los clientes pueden cambiar este TTL a lo que necesiten para permanecer dentro de sus derechos de licencia.

## Diferencias en la latencia de la ingesta de datos

CJA todavía no tiene las capacidades de Real-time CDP y, como consecuencia de esto, la creación de informes de CJA incluye cierta latencia antes de que los datos estén disponibles para la creación de informes o audiencias. Real-time CDP procesa los datos a través de diferentes sistemas que tienen una latencia diferente.
