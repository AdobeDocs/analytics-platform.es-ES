---
title: Guía de transición
description: Aprenda a realizar la transición de Customer Journey Analytics a Customer Journey Analytics B2B edition
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: d0e6398b-8080-4e36-b178-0cb91945d0c5
autotag-review: '2026-05-19T08:06:36.475Z'
TQID: 'https://experienceleague.adobe.com/vkf6272OwRu9B4ZgpiXKhc4J3WAqUAm8r-3iQLUgOKg'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
  - id: d3f42e9e-bb51-4077-a732-358b801d8b29
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 9c87ce4fb30c7d1d66ce88174443369ef44a7377
workflow-type: tm+mt
source-wordcount: 623
ht-degree: 3%

---

# Guía de transición

En esta guía se explica cómo realizar la transición de Customer Journey Analytics a B2B edition de Customer Journey Analytics.

El artículo supone que ya utiliza Customer Journey Analytics en cierta medida:

* Tiene [conexiones](/help/connections/overview.md) que consumen datos en Customer Journey Analytics.
* Tiene [vistas de datos](/help/data-views/data-views.md) que utilizan los datos de estas conexiones.
* Tiene [proyectos](/help/analysis-workspace/home.md) con informes y visualizaciones que aprovechan estas vistas de datos.

Si no ha usado Customer Journey Analytics anteriormente, consulte la [guía de inicio rápido de B2B edition](cja-b2b-quick-start-guide.md).

Si es un usuario de Adobe Analytics y planea usar Customer Journey Analytics B2B edition, primero consulte la [documentación de actualización de Adobe Analytics a Customer Journey Analytics](cja-upgrade/cja-upgrade-recommendations.md).


## Implementación existente

La implementación existente de Customer Journey Analytics no cambia en absoluto una vez que dispone de una licencia y está aprovisionado para Customer Journey Analytics B2B edition.

Todas las conexiones existentes se consideran [conexiones basadas en personas](cja-b2b-concepts-features.md#connections-and-identifiers) y continúan funcionando sin ninguna actualización. Todo lo que se basa en los datos de estas conexiones basadas en personas, como vistas de datos, proyectos de Workspace, segmentos, exportaciones programadas, alertas y mucho más, sigue funcionando según lo planeado y previsto originalmente.

>[!IMPORTANT]
>
>No puede cambiar las conexiones basadas en personas existentes a una conexión basada en cuentas. Se requiere una nueva conexión basada en cuentas para utilizar las funciones de B2B edition.
>


## Implementación de funciones B2B

Para implementar funciones B2B en la implementación existente, debe seguir estos pasos:

1. Modele sus datos B2B. Puede usar [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es) para estandarizar los datos B2B y definir esquemas para los datos B2B.<br/>Puede basar sus esquemas en las [clases estándar que se proporcionan en Real-time CDP B2B edition](https://experienceleague.adobe.com/es/docs/experience-platform/rtcdp/schemas/b2b) o puede usar sus propias clases y esquemas personalizados. Los [casos de uso](/help/use-cases/b2b/b2b-edition/use-cases-overview.md) artículos utilizan clases y esquemas de Real-time CDP B2B edition, sin embargo, no se requiere una licencia de Real-time CDP B2B edition para utilizar las clases y esquemas estándar. <br/>Customer Journey Analytics B2B edition supone al menos datos de eventos de series temporales basados en la cuenta y se beneficia de datos de perfiles o registros de búsqueda adicionales. Como datos de cuenta, datos de grupos de compras, datos de oportunidades, datos de miembros de listas de marketing y mucho más.

   * Defina qué identificador desea utilizar como identificador de cuenta principal (ID de cuenta). A menudo, un CRM existente u otra herramienta (por ejemplo: Demandbase) le ayuda a determinar ese identificador.
   * Identifique identificadores adicionales para los demás datos B2B que planea utilizar: identificador de cuenta global, identificador de oportunidad, identificador de grupo de compra e identificador de persona.

1. Prepare sus datos B2B. Asegúrese de añadir y recopilar identificadores de cuenta en todos los datos de eventos de series temporales y los datos de registro relevantes. Del mismo modo, asegúrese de que los datos de evento de series temporales y el registro de búsqueda contengan otros identificadores para los eventos relevantes. Por ejemplo: un evento que indica el paso a otra fase de ventas debe tener un identificador de oportunidad. Y ese identificador debe formar parte de los datos de búsqueda de oportunidades.

1. [Crear una nueva conexión basada en cuentas](/help/connections/create-connection.md#account-based-connection). Seleccione los contenedores opcionales que desee incluir, [agregue conjuntos de datos](/help/connections/create-connection.md#add-datasets) y defina la [configuración para cada conjunto de datos](/help/connections/create-connection.md#dataset-settings). Utilice [coincidencia por contenedor](cja-b2b-concepts-features.md#match-by-container) para conjuntos de datos de registro de búsqueda siempre que sea posible.

1. [Crear vistas de datos](/help/data-views/create-dataview.md) en función de la nueva conexión.

   * Asegúrese de añadir todos los campos relevantes como métricas o dimensiones a partir de los datos introducidos.
   * Aplique la configuración de componentes (como persistencia, atribución, etc.) si es necesario.
   * Agregue campos derivados adicionales cuando corresponda.

1. [Cree proyectos del espacio de trabajo](/help/analysis-workspace/build-workspace-project/create-projects.md) para informar y obtener información sobre sus datos B2B. Use características específicas de B2B, como [contenedores](cja-b2b-concepts-features.md#containers), para obtener información más detallada.

   Puede combinar informes y perspectivas B2B (basados en persona) y B2B (basados en cuenta) mediante el uso de varios [paneles](/help/analysis-workspace/c-panels/panels.md) en un proyecto de Workspace.
