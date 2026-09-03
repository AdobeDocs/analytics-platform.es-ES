---
title: Transición de Google Analytics 4 a Customer Journey Analytics
description: Aprenda conceptos clave para obtener informes en Customer Journey Analytics, dirigidos a analistas familiarizados con Google Analytics 4.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: 3d7c8b91-f2a4-4e6b-9c1d-5f8e3a720469
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 046df00868ca4a5b3bab3eb36cca7d91b141333a
workflow-type: tm+mt
source-wordcount: 590
ht-degree: 3%

---


# Transición de Google Analytics 4 a Customer Journey Analytics

Esta guía ayuda a los analistas familiarizados con Google Analytics 4 a conocer los conceptos e informes equivalentes en Adobe Customer Journey Analytics. Si es el responsable de la implementación técnica en lugar de generar informes, consulte [Actualizar una solución de análisis de terceros a Customer Journey Analytics](../cja-upgrade/cja-upgrade-third-party-solution.md) para obtener instrucciones sobre la configuración de Web SDK y la ingesta de datos. Si su organización aún necesita migrar los datos de Google Analytics existentes a Adobe Experience Platform, consulte [Migrar datos de Google Analytics](/help/use-cases/third-party/ga/overview.md).

## Diferencias clave entre GA4 y Customer Journey Analytics

GA4 y Customer Journey Analytics comparten la misma filosofía básica: cada interacción del usuario es un evento y el análisis se realiza en una herramienta de lienzo en blanco donde se arrastran y sueltan dimensiones y métricas para crear vistas personalizadas. Si está familiarizado con el GA4 Explore, es probable que Analysis Workspace se reconozca inmediatamente.

Las diferencias más significativas se dan cuando Customer Journey Analytics se extiende más allá de GA4:

* **Datos en canales múltiples**: Customer Journey Analytics puede combinar análisis web con fuentes de datos sin conexión (como registros de centros de llamadas, actividad de CRM, programas de fidelidad o participación por correo electrónico) en el mismo análisis. GA4 se limita a las interacciones digitales recopiladas a través de su SDK.
* **Procesamiento de tiempo del informe**: Customer Journey Analytics aplica lógica como modelos de atribución, definiciones de sesión y reglas de segmentos en el momento de la consulta, no en el momento de la recopilación. Los cambios realizados en las definiciones de sesión o los modelos de atribución se aplican de forma retroactiva a todos los datos históricos sin necesidad de volver a procesar.
* **Definiciones de sesión flexibles**: La duración del tiempo de espera de sesión, los eventos de inicio de sesión y los eventos de fin de sesión se pueden configurar por vista de datos en Customer Journey Analytics. El tiempo de espera de sesión de GA4 es ajustable (valor predeterminado de 30 minutos, hasta 7 horas y 55 minutos), pero se aplica en toda la propiedad, y su comportamiento de inicio y final de sesión es fijo.
* **Vinculación de identidad**: la capacidad de vinculación de Customer Journey Analytics puede vincular interacciones entre dispositivos y canales cruzados con la misma persona, lo que produce recuentos de personas más precisos que el modelo de identidad combinado de GA4.

## Cuenta y estructura de datos

GA4 y Customer Journey Analytics organizan los datos de forma diferente a nivel de plataforma.

| GA4 | Customer Journey Analytics |
|---|---|
| cuenta de Google | Adobe IMS org |
| Propiedad | Conexión + vista de datos |
| Flujo de datos | [!UICONTROL Conjunto de datos de evento] en Platform |
| Filtros de datos | Filtros de componentes de vista de datos |
| Subpropiedad | Separar vista de datos con filtros aplicados |
| Propiedad de resumen | Conexión que combina varios conjuntos de datos |

La diferencia estructural más importante es que una propiedad de GA4 gestiona el cableado de datos y los informes como un solo objeto. Customer Journey Analytics separa estos conceptos en dos capas distintas:

* Una **conexión** vincula uno o más conjuntos de datos de Adobe Experience Platform con Customer Journey Analytics. Este paso incorpora datos en Customer Journey Analytics en un formato optimizado para la creación de informes.
* Se ha creado una **vista de datos** sobre una conexión y define qué dimensiones, métricas y configuraciones están disponibles para los informes. Es la capa de configuración del sistema de informes.

Ambos deben existir antes de poder analizar los datos en Customer Journey Analytics. No hay grupos de informes en Customer Journey Analytics.

## Introducción a Analysis Workspace

GA4 Explore y Analysis Workspace son herramientas de análisis de arrastrar y soltar en lienzo en blanco. El modelo de interacción es el mismo; la terminología difiere ligeramente.

| Exploración de GA4 | Analysis Workspace |
|---|---|
| Lienzo de exploración | paneles |
| Gráfico o tipo de visualización | Visualización |
| Dimensión | Dimensión |
| Métrica | Métrica |
| Segmento o filtro | Segmento |
| Recuento de eventos | [!UICONTROL Eventos] |
| Usuarios | [!UICONTROL Personas] |
| Sesiones | [!UICONTROL Sesiones] |

>[!TIP]
>
>Los contenedores de segmentos de GA4 se denominan Usuarios, Sesiones y Eventos. En Customer Journey Analytics, los contenedores equivalentes son **[!UICONTROL Person]**, **[!UICONTROL Session]** y **[!UICONTROL Event]**. La lógica de ámbito es la misma.

>[!MORELIKETHIS]
>
>* [Migrar datos de Google Analytics](/help/use-cases/third-party/ga/overview.md)
