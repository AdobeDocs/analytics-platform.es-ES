---
title: Configuración de informes de Google Analytics en Customer Journey Analytics
description: null
translation-type: tm+mt
source-git-commit: 9bbc625aca9e0b8384b3e95d79fd695fda863f0b
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%

---


# Configuración de informes de Google Analytics en Customer Journey Analytics

configuración del conector de almacenamiento de Google Cloud,

configurar Google Tag Manager

Esquema BigQuery Export (https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)

1. Convertir sesiones GA en eventos en Big Query
1. Exportar eventos de Google Analytics al almacenamiento de Google Cloud
1. Importar eventos GCS a Adobe Experience Platform y asignarlos al esquema XDM

## Requisitos previos

* Acceso a Adobe Experience Platform
* Acceso a Google Analytics universales (versión 360 de Google Analytics) o Google Analytics 4 (versión gratuita o versión 360 de Google Analytics)
* Acceso al Customer Journey Analytics

## Conexión de datos de Google Analytics a Adobe Experience Platform

La forma de introducir los datos de los Google Analytics en Adobe Experience Platform depende de la versión de Google Analytics que utilice:

| Si utiliza... | También necesita esta licencia... | Y haz esto... |
| --- | --- | --- |
| **Google Analytics universales** | Google Analytics 360 | Siga los pasos 1 a x de las instrucciones siguientes |
| **Google Analytics 4** | Versión gratuita de GA para Google Analytics 360 | No es necesario realizar el paso x en las instrucciones siguientes. |

Las siguientes instrucciones están basadas en Google Analytics universales.

1. Conecte los datos de sus Google Analytics a BigQuery y
Consulte [estas instrucciones](https://support.google.com/analytics/answer/3416092?hl=en).
1. (Solo clientes de Universal Analytics) Transforme sesiones de Google Analytics a eventos en BigQuery.
Consulte [estas instrucciones](https://support.google.com/analytics/answer/3437618?hl=en).
1. Exportar eventos de Google Analytics al almacenamiento en la nube de Google.
Consulte [estas instrucciones](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089).
