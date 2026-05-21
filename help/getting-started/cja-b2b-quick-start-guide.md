---
title: Guía de inicio rápido de Customer Journey Analytics B2B
description: Guía de inicio rápido para B2B Edition de Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: ff8d419e-5cc6-4e1b-8cf8-9dbaa8054179
TQID: https://experienceleague.adobe.com/SjixkRCOmeUYuhZCVO7-7tLHalpnXO6QCVE1BiG9h2E
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: a67cb189-a535-41f6-afa2-448f39c4759f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 431
ht-degree: 88%

---

# Guía de inicio rápido de B2B Edition

Para implementar Customer Journey Analytics B2B Edition, asegúrese de que comprende primero los conceptos y las funciones específicas de B2B. Además, debe estar familiarizado con el flujo de trabajo tradicional para implementar Customer Journey Analytics.

Este documento se centra en el flujo de trabajo específico para la implementación de Customer Journey Analytics.

## Requisitos previos

Para implementar Customer Journey Analytics B2B Edition, se aplican los siguientes requisitos previos:

* No cuenta con el [control de acceso y los permisos](/help/technotes/access-control.md) necesarios para realizar tareas de administración en Customer Journey Analytics.
* Ha adquirido el paquete de complementos de Customer Journey Analytics B2B Edition.


## Flujo de trabajo

| Tarea | Detalles |
| --- | --- |
| **Paso 1: obtener datos de B2B en Experience Platform** | Este paso, realizado en Experience Platform, incluye varios subpasos:<ul><li>**Paso 1a: Prepare su esquema de datos**: Utilice [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es) para estandarizar los datos B2B y [defina esquemas](https://experienceleague.adobe.com/es/docs/experience-platform/rtcdp/schemas/b2b) para sus datos B2B.</li><li>**Paso 1b: crear un conjunto de datos basado en el esquema**: los datos de Platform constan de conjuntos de datos como, por ejemplo, datos de cuenta, datos de oportunidad, datos de grupo de compra, datos de campaña, datos de lista de marketing, conjuntos de datos de correo electrónico, conjuntos de datos de CRM, conjuntos de datos de POS, etc. Cada conjunto de datos consta de un esquema y lotes de datos. Puede [crear un conjunto de datos en Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=es).</li><li>**Paso 1c: Ingesta de datos en Experience Platform**: Tiene [varias opciones](https://experienceleague.adobe.com/es/docs/experience-platform/ingestion/home).</li></ul> |
| **Paso 2: crear conexiones entre conjuntos de datos de Platform y Customer Journey Analytics** | Una conexión le permite integrar conjuntos de datos de Adobe Experience Platform el Espacio de trabajo. Para informar sobre conjuntos de datos de Experience Platform, primero debe establecer una conexión entre conjuntos de datos en Experience Platform y Workspace. Dispone de opciones adicionales al configurar una conexión con B2B Edition. <br>Consulte [Crear o editar una conexión](/help/connections/create-connection.md). |
| **Paso 3: crear vistas de datos** | Una vista de datos es una vista *filtrada* de los datos. Puede crear distintas vistas de datos para la misma conexión, con diferentes configuraciones para el tiempo de espera de visita, la atribución, etc. Puede crear varias vistas de datos para un único conjunto de datos. Dispone de opciones adicionales al configurar una vista de datos con B2B edition.<br>Consulte [Crear una vista de datos](/help/data-views/create-dataview.md). |
| **Paso 4: informar sobre los datos de canales cruzados en el Espacio de trabajo** | Después de crear conexiones y vistas de datos, analice los datos B2B que ha traído con la potencia y flexibilidad de Analysis Workspace.<br>Vea [Realizar análisis básicos](/help/analysis-workspace/perform-basic-analysis.md) y [Realizar análisis avanzados](/help/analysis-workspace/perform-adv-analysis.md). |

<!--

## Use Case

The [B2B Use Case ](../data-ingestion/data-ingestion.md) document provides an example use case on how to implement Customer  Journey Analytics B2B Edition.

-->