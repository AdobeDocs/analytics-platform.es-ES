---
description: Explica qué factores influyen en la coherencia de las métricas entre Real-time Customer Data Platform (CDP en tiempo real) y CJA.
title: Coherencia de métricas entre CDP en tiempo real y CJA
role: Admin
feature: CJA Basics
source-git-commit: 2318b303c981ad556dc61a3419af4cce9fbbf92b
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 2%

---


# Coherencia de métricas entre CDP en tiempo real y CJA

En escenarios reales, no se puede garantizar la coherencia de las métricas en Real-time Customer Data Platform (CDP en tiempo real) y Customer Journey Analytics (CJA). Este documento explica por qué.

## CJA todavía no utiliza Identity Graph

CDP y CJA no comparten la misma definición de persona hoy en día. CJA todavía no utiliza [Gráfico de identidad](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=es) informar de su definición de persona. CDP en tiempo real se basa completamente en la información del gráfico de identidad para crear un perfil combinado.

CJA utiliza un método llamado [Vinculación basada en el campo](/help/connections/cca/overview.md) que extrae identificadores de conjuntos de datos en el lago de datos y aplica lógica personalizada para vincularlos juntos. En el futuro intermedio, se espera que CJA empiece a utilizar [Servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en) exporta al lago de datos, permitiendo una noción compartida de identidad a través de CDP y CJA en tiempo real.

>[!IMPORTANT]
>
>Hacer que el servicio de identidad de Adobe Experience Platform sea la fuente de identidad de todas las aplicaciones de Adobe Experience Platform no hace que las métricas sean coherentes de forma automática en todas las aplicaciones. Siga leyendo para saber por qué.

## Flexibilidad de los datos de las aplicaciones

Experience Platform no aplica una aplicación estricta para mantener los datos entre Perfil del cliente en tiempo real y Lago de datos iguales. Algunos casos de uso funcionan con los datos en [Perfil del cliente en tiempo real](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/profile/profile-overview.html?lang=en) (activación), mientras que otros funcionan fuera de la función [lago de datos](https://business.adobe.com/blog/basics/data-lake) (servicio de informes y consultas).

Los clientes de CDP en tiempo real generalmente no tienen el 100% de los datos en el lago de datos de Adobe Experience Platform yendo a Perfil. Esto es por diseño: los clientes deben habilitar específicamente los datos en el lago para Profile. CJA permite a los analistas de datos seleccionar libremente qué datos desean incorporar para su análisis desde el lago de datos, independientemente de lo que esté habilitado para CDP en tiempo real.

## Modificadores específicos de la aplicación

CJA permite realizar amplias modificaciones de los datos en el momento de la consulta, como la combinación de campos, la división de campos entre sí y otras manipulaciones como conversiones de moneda, deduplicación de valores, sesionización y filtrado en el nivel de fila. Estas capacidades no están disponibles para CDP.

Del mismo modo, se aplica CDP en tiempo real [combinar directivas](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en) para determinar qué datos se priorizarán y qué datos se combinarán para crear una vista unificada de una persona. Estas configuraciones se encuentran dentro de la lógica de cada aplicación y no se comparten.

## Comportamiento de tiempo de lectura frente a tiempo de escritura

CDP en tiempo real requiere la vinculación de perfiles puntuales mediante el último gráfico de ID.

* CDP en tiempo real está diseñado para ensamblar información de perfil en tiempo real para su activación.

* Puede admitir en tiempo real todos los cambios realizados en los identificadores establecidos para un usuario determinado.

* La ventana retrospectiva se controla mediante la definición del segmento.

CJA requiere que los datos se vinculen en tiempo de escritura mediante las exportaciones de ID Graph.

* CJA aplica pasos complejos de preprocesamiento, como la indexación, el uso compartido y la agrupación, antes de que los datos estén listos para su análisis.

* El identificador de persona de un usuario determinado es una entrada crítica para las fases de preprocesamiento; cambiar el identificador de persona posteriormente tiene un coste de reprocesamiento significativo.

* La ventana retrospectiva se controla a nivel de aplicación.

## Diferencias en TTL (Tiempo de vida) e ingesta de datos

Incluso si los conjuntos de datos en tiempo real CDP y CJA son los mismos, CDP en tiempo real solo puede mantener una ventana muy limitada de historial. Por el contrario, es probable que CJA tenga años de datos. Además:

* Los clientes de CJA y CDP en tiempo real pueden establecer ventanas de retención personalizadas para datos, independientes entre sí.

* CDP y CJA en tiempo real tienen una lógica diferente para la ingesta de datos. CJA ignora los registros sin ID de persona o marca de tiempo y tiene límites estrictos con respecto al número de registros que puede tener un solo perfil o persona.

* Los clientes de CDP en tiempo real obtienen 7 días de acceso a los datos en el lago, principalmente para facilitar la incorporación de datos en el perfil y para consultas ad hoc.

* No hay TTLs para los datos en el lago para los clientes de CJA. Sin embargo, los usuarios de CJA pueden establecer ellos mismos una ventana de retención personalizada en CJA al crear una conexión.

* El Almacenamiento de perfiles en CDP en tiempo real permite configurar TTL para el cliente. Los clientes pueden cambiar este TTL a lo que necesiten para permanecer dentro de sus derechos de licencia.

## Diferencias en el procesamiento del RGPD (Reglamento General de Protección de Datos)

La lógica de procesamiento de datos para el RGPD y la higiene de los datos en CDP en tiempo real y lago de datos es bastante diferente. Estamos trabajando para lograr un enfoque único.

## Diferencias en la latencia del consumo de datos

Los informes de CJA incluyen cierta latencia antes de que los datos estén disponibles para la creación de informes o audiencias. CDP en tiempo real procesa los datos a través de diferentes sistemas que tienen una latencia diferente.