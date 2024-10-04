---
description: Explica qué factores influyen en la coherencia de las métricas y los recuentos de miembros de audiencia entre Real-time Customer Data Platform (Real-time CDP) y Customer Journey Analytics.
title: Coherencia de las métricas y pertenencia a audiencias
role: Admin
feature: Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 90d1c51c11f0ab4d7d61b8e115efa8257a985446
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 97%

---


# Coherencia de las métricas y pertenencia a audiencias

En situaciones reales, no se puede garantizar la coherencia de las métricas y los recuentos de miembros de audiencia en Real-time Customer Data Platform (Real-time CDP) y Customer Journey Analytics. Este documento explica por qué.

Al comparar los recuentos de miembros de audiencia entre Real-time CDP y Customer Journey Analytics, es importante tener en cuenta los diferentes propósitos de estas dos herramientas. Real-time CDP utiliza datos de perfil del cliente para dirigir las experiencias digitales a consumidores individuales, mientras que Customer Journey Analytics está diseñado para ayudar a los usuarios a comprender los patrones en métricas y segmentos clave del negocio. Aunque la publicación de audiencias desde Customer Journey Analytics hasta Real-time CDP permite al usuario de estas herramientas “activar” de forma fácil y nativa una perspectiva, aprovechando las lecciones aprendidas en Customer Journey Analytics, estas herramientas sirven para propósitos fundamentalmente diferentes.

## Diferencias en las configuraciones de identidad

Real-time CDP y Customer Journey Analytics no comparten la misma definición de una persona en la actualidad. Real-time CDP se basa completamente en la información del [gráfico de identidad](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=es) para crear un perfil combinado.

Customer Journey Analytics se puede configurar para usar la [Identificación](../stitching/overview.md), que extrae identificadores de conjuntos de datos en el lago de datos y aplica lógica personalizada para vincularlos juntos.

En el futuro, Customer Journey Analytics podrá utilizar el gráfico de identidad.

## Diferencias en la configuración del conjunto de datos

Puede elegir colocar algunos datos en Real-time CDP y otros en Customer Journey Analytics; a menudo, los clientes eligen incorporar más datos históricos en Customer Journey Analytics de los que son relevantes para Real-time CDP. Otros conjuntos de datos pueden ser más relevantes para Real-time CDP que para Customer Journey Analytics.

## Diferencias en la configuración de procesamiento

Customer Journey Analytics permite realizar amplias modificaciones de los datos en el momento de la consulta, como la combinación de campos, la división de campos entre sí y otras manipulaciones como inclusiones/exclusiones, subcadenas, deduplicación de valores, definición de sesiones y filtrado en el nivel de fila.

Real-time CDP ofrece un conjunto diferente de herramientas de manipulación de datos. Se aplica [combinar directivas](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=es) para determinar qué datos se priorizarán y qué datos se combinarán para crear una vista unificada de una persona.

## Diferencias en TTL (Tiempo de vida) e incorporación de datos

Incluso si los conjuntos de datos de Real-time CDP y Customer Journey Analytics son los mismos, Real-time CDP solo puede mantener una ventana muy limitada de historial. Por el contrario, es probable que Customer Journey Analytics disponga de años de datos. Además, consulte lo siguiente:

* Los clientes de Customer Journey Analytics y Real-time CDP pueden establecer ventanas de retención personalizadas para datos, independientes entre sí.

* CDP y Real-time Customer Journey Analytics tienen una lógica diferente para la ingesta de datos. Customer Journey Analytics ignora los registros sin ID de persona o marca de tiempo y tiene límites estrictos en cuanto al número de registros que puede tener un solo perfil o una persona.

* Los clientes de Real-time CDP obtienen siete días de acceso a los datos en el lago, principalmente para facilitar la incorporación de datos en el perfil y para consultas ad hoc.

* No hay TTL para los datos en el lago para los clientes de Customer Journey Analytics. Sin embargo, los usuarios de Customer Journey Analytics pueden establecer ellos mismos una ventana de retención personalizada en Customer Journey Analytics al crear una conexión.

* El Almacenamiento de perfiles en Real-time CDP permite configurar los TTL para el cliente. Los clientes pueden cambiar este TTL a lo que necesiten para permanecer dentro de sus derechos de licencia.

## Diferencias en la latencia de la ingesta de datos

Customer Journey Analytics todavía no tiene las capacidades de Real-time CDP y, como consecuencia de esto, Customer Journey Analytics incluye un poco latencia antes de que los datos estén disponibles para la creación de informes o audiencias. Real-time CDP procesa los datos a través de diferentes sistemas que tienen una latencia diferente.
