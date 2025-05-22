---
title: Guía de transición
description: Aprenda a realizar la transición de Customer Journey Analytics a Customer Journey Analytics B2B edition
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B edition"
hide: true
hidefromtoc: true
source-git-commit: c0446bd85b65109fd3311d54e33f9fb33af28f88
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 0%

---

# Guía de transición

{{draft-b2b}}

En esta guía se explica cómo realizar la transición de Customer Journey Analytics a B2B edition de Customer Journey Analytics.

El artículo supone que ya utiliza Customer Journey Analytics en cierta medida:

* Tiene [conexiones](/help/connections/overview.md) que consumen datos en Customer Journey Analytics.
* Tiene [vistas de datos](/help/data-views/data-views.md) que utilizan los datos de estas conexiones.
* Tiene [proyectos](/help/analysis-workspace/home.md) con informes y visualización que aprovechan estas vistas de datos.

Si no ha usado Customer Journey Analytics anteriormente, consulte la [guía de inicio rápido de B2B edition](cja-b2b-quick-start-guide.md).


## Implementación existente

La implementación existente de Customer Journey Analytics no cambia en absoluto una vez que dispone de una licencia y está aprovisionado para Customer Journey Analytics B2B edition.

Todas las conexiones existentes se consideran [conexiones basadas en personas](cja-b2b-concepts-features.md#connections-and-identifiers) y continúan funcionando sin ninguna actualización. Todo lo que se basa en los datos de estas conexiones basadas en personas, como vistas de datos, proyectos de Workspace, segmentos, exportaciones programadas, alertas y mucho más, sigue funcionando según lo planeado y previsto originalmente.

>[!IMPORTANT]
>
>No puede cambiar las conexiones basadas en personas existentes a una conexión basada en cuentas. Se requiere una nueva conexión basada en cuentas para utilizar las funciones de B2B edition.
>


## Implementación de funciones B2B

Para implementar funciones B2B en la implementación existente, debe seguir estos pasos:

1. Modele sus datos B2B. Customer Journey Analytics B2B edition supone al menos datos de eventos de series temporales basados en cuentas y se beneficia de datos de perfiles o registros de búsqueda adicionales. Como datos de cuenta, datos de grupos de compras, datos de oportunidades, datos de miembros de listas de marketing y mucho más.

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
