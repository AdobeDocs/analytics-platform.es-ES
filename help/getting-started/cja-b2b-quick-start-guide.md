---
title: Guía de inicio rápido de Customer Journey Analytics B2B
description: Guía de inicio rápido para B2B edition de Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B edition"
exl-id: ff8d419e-5cc6-4e1b-8cf8-9dbaa8054179
source-git-commit: 326a82e93c0c8d57db224023ed5f3a7ab94a8997
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 22%

---


# Guía de inicio rápido de B2B edition

{{draft-b2b}}

Para implementar Customer Journey Analytics B2B edition, asegúrese de que comprende primero los conceptos y las funciones específicas de B2B. Además, debe estar familiarizado con el flujo de trabajo tradicional para implementar Customer Journey Analytics.

Este documento se centra en el flujo de trabajo específico para la implementación de Customer Journey Analytics.

## Requisitos previos

Para implementar Customer Journey Analytics B2B edition, se aplican los siguientes requisitos previos:

* No cuenta con el control de acceso y los permisos [necesarios](/help/technotes/access-control.md) para realizar tareas de administración en Customer Journey Analytics.
* Ha adquirido el paquete de complementos de Customer Journey Analytics B2B edition.


## Flujo de trabajo

| Tarea | Detalles |
| --- | --- |
| **Paso 1: obtener datos B2B en Experience Platform** | Este paso, realizado en Experience Platform, incluye varios subpasos:<ul><li>**Paso 1a: Prepare su esquema de datos**: Use [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es) para estandarizar los datos B2B y [definir esquemas](https://experienceleague.adobe.com/es/docs/experience-platform/rtcdp/schemas/b2b) para sus datos B2B.</li><li>**Paso 1b: crear un conjunto de datos basado en el esquema**: los datos de Platform constan de conjuntos de datos como, por ejemplo, datos de cuenta, datos de oportunidad, datos de grupo de compra, datos de campaña, datos de lista de marketing, conjuntos de datos de correo electrónico, conjuntos de datos CRM, conjuntos de datos de POS, etc. Cada conjunto de datos consta de un esquema y lotes de datos. Puede [crear un conjunto de datos en Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=es).</li><li>**Paso 1c: Ingesta de datos en Experience Platform**: Tiene [varias opciones](https://experienceleague.adobe.com/es/docs/experience-platform/ingestion/home).</li></ul> |
| **Paso 2: crear conexiones entre conjuntos de datos de Platform y Customer Journey Analytics** | Una conexión le permite integrar conjuntos de datos de Adobe Experience Platform el Espacio de trabajo. Para informar sobre conjuntos de datos de Experience Platform, primero debe establecer una conexión entre conjuntos de datos en Experience Platform y Workspace. Dispone de opciones adicionales al configurar una conexión con B2B edition. <br>Consulte [Crear o editar una conexión](/help/connections/create-connection.md). |
| **Paso 3: crear vistas de datos** | Una vista de datos es una vista *filtrada* de los datos. Puede crear diferentes vistas de datos para la misma conexión, con diferentes configuraciones para el tiempo de espera de visita, la atribución, etc. Puede crear varias vistas de datos para un único conjunto de datos. Dispone de opciones adicionales al configurar una vista de datos con B2B edition.<br>Consulte [Crear una vista de datos](/help/data-views/create-dataview.md). |
| **Paso 4: informar sobre los datos de canales cruzados el Espacio de trabajo** | Después de crear conexiones y vistas de datos, analice los datos B2B que ha introducido con la potencia y flexibilidad de Analysis Workspace.<br>Consulte [Realizar análisis básicos](/help/analysis-workspace/perform-basic-analysis.md) y [Realizar análisis avanzados](/help/analysis-workspace/perform-adv-analysis.md). |

<!--

## Use Case

The [B2B Use Case ](../data-ingestion/data-ingestion.md) document provides an example use case on how to implement Customer  Journey Analytics B2B Edition.

-->