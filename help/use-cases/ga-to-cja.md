---
title: Cómo obtener datos de Google Analytics en Adobe Experience Platform para su análisis en Customer Journey Analytics (CJA)
description: 'Explica cómo aprovechar Customer Journey Analytics (CJA) para ingerir sus Google Analytics y datos de firebase en Adobe Experience Platform. '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: 793b2ce4ec8a487f6c4290fe2eff00879fcca13d
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 2%

---


# Ingesta de datos de Google Analytics en Adobe Experience Platform

Este caso de uso se centra en cómo introducir los datos de sus Google Analytics como un conjunto de datos en Adobe Experience Platform. (Esto se aplica a los datos históricos y a los datos activos). Una vez finalizado, puede combinar ambos conjuntos de datos para obtener una vista entre dispositivos del recorrido del usuario.

Los conjuntos de datos del Experience Platform se componen de dos cosas: un esquema y los registros reales en el conjunto de datos. El esquema (lo llamamos Experience Data Model o XDM para abreviar) es como las columnas del conjunto de datos y es como el modelo o las reglas que describen los datos en sí. Dentro de la plataforma, Adobe proporciona dos tipos de esquemas:

* Esquemas predeterminados que puede asignar los datos de sus Google Analytics a automáticamente (denominado esquema de Experience Event)
* Esquemas personalizados que se pueden crear y asignar fácilmente a los datos de Google Analytics

Uno de los aspectos más potentes del modelo de datos de Adobe es que le permite estandarizar todos los datos de interacción con los clientes en un esquema común, lo que facilita en gran medida la vinculación de los datos en CJA.

## Requisitos previos

Para realizar estas tareas, necesita los siguientes permisos y acceso:

* Acceso a Adobe Experience Platform
* Acceso a Google Analytics universales (versión 360 de Google Analytics) o Google Analytics 4 (versión gratuita o versión 360 de Google Analytics)
* Acceso al Customer Journey Analytics y sus [permisos de administración](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=es-ES#admin-access-permissions).

La forma de introducir los datos de los Google Analytics en Adobe Experience Platform depende de la versión de Google Analytics que utilice:

| Si utiliza... | También necesita esta licencia... | Y haz esto... |
| --- | --- | --- |
| **Google Analytics universales** | Google Analytics 360 | Siga los pasos 1 a 5 de las instrucciones siguientes |
| **Google Analytics 4** | Versión gratuita de GA para Google Analytics 360 | Siga los pasos 1 y 3-5 de las instrucciones siguientes. No es necesario el paso 2. |

## 1. Conecte los datos de sus Google Analytics a BigQuery

Tenga en cuenta que las siguientes instrucciones están basadas en Google Analytics universales.

Consulte [estas instrucciones](https://support.google.com/analytics/answer/3416092?hl=en).

## 2. Transformar sesiones de Google Analytics a eventos en BigQuery

>[!IMPORTANT]
>
>Este paso solo se aplica a los clientes de Universal Analytics

Los datos de GA almacenan cada registro en sus datos como una sesión del usuario en lugar de como eventos individuales. La transformación de los datos hace que sean compatibles con Adobe Experience Platform.

Consulte [estas instrucciones](https://support.google.com/analytics/answer/3437618?hl=en).

Debe crear una consulta SQL para transformar los datos de Universal Analytics en un formato compatible con Experience Platform. Vea este vídeo para obtener instrucciones:

>[!VIDEO](https://video.tv.adobe.com/v/332634)

## 3. Exporte eventos de Google Analytics en formato JSON a Google Cloud Storage y guárdelos en un bucket

Consulte [estas instrucciones](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089).

## 4. Incorporar los datos del almacenamiento de Google Cloud al Experience Platform

Vea este vídeo para obtener instrucciones:

>[!VIDEO](https://video.tv.adobe.com/v/332641)

## 5. Importar eventos GCS a Adobe Experience Platform y asignarlos al esquema XDM

Esquema BigQuery Export (https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)
