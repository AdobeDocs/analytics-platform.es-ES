---
title: Análisis de Recorridos en todos los canales
description: Analice y extraiga información de las interacciones de los clientes en todo el recorrido del cliente.
exl-id: 285532b1-eb37-4984-9559-054a18515ddf
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: a9009c44a8e739add7fbcb9f9c31676d38af0094
workflow-type: ht
source-wordcount: '433'
ht-degree: 100%

---

# Análisis de Recorridos en todos los canales

Disponer de una sola vista consolidada del comportamiento de los clientes en varios canales mediante la unificación de datos de varias propiedades web, móviles y sin conexión. Por ejemplo, puede utilizar esta vista consolidada para analizar las interacciones de los clientes en equipos de escritorio y dispositivos móviles, a fin de comprender el comportamiento de los clientes y extraer perspectivas para optimizar las experiencias de los clientes digitales. También puede analizar las interacciones de los clientes entre canales, incluidos los canales digitales y sin conexión, como las interacciones de soporte y las compras en la tienda, para comprender y optimizar mejor el recorrido del cliente.

## Arquitectura

![Arquitectura de varios canales](../assets/cross-channel-architecture.svg)

## Pasos de la implementación

1. [Cree esquemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=es) para introducir los datos.
1. [Cree conjuntos de datos](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html?lang=es) para incorporar los datos.
1. [Ingresar datos en Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html?lang=es).
1. Use un ID de área de nombres común en todos los conjuntos de datos o utilice [Cross-Channel Analytics](/help/cca/overview.md) para vincular personas. Tenga en cuenta que Customer Journey Analytics no utiliza actualmente los servicios de perfil o intentidad de Experience Platform para la vinculación.
1. Realice cualquier preparación de datos personalizada para asegurarse de que se incorpora una clave común en los conjuntos de datos de series temporales en Customer Journey Analytics.
1. Asigne un ID principal a los datos de búsqueda que pueda unirse a un campo en los datos de evento. Cuenta como filas en licencias.
1. Establezca el mismo ID principal para los datos de perfil que el ID principal de los datos de evento.
1. Configure una conexión de datos para introducir datos de Experience Platform a Customer Journey Analytics.
1. [Cree una vista de datos](/help/data-views/create-dataview.md) con la conexión para seleccionar las dimensiones y métricas específicas que se incluirán en la vista. La configuración de atribución y asignación también se configura en la vista de datos. Estas configuraciones se calculan en el momento del informe.
1. Cree un proyecto para configurar tableros e informes en Analysis Workspace.

## Consideraciones

Al establecer este flujo de trabajo, asegúrese de tener en cuenta los siguientes puntos.

* El análisis de datos entre canales requiere la misma área de nombres de ID en cada registro.
* El proceso de unión de conjuntos de datos dispares requiere una clave persona/entidad principal común en todos los conjuntos de datos.
* Actualmente no se admiten uniones secundarias basadas en claves.
* El proceso de vinculación de identidad basado en campos permite volver a incrustar identidades en filas basándose en registros de ID transitorios posteriores, como un ID de autenticación. Esto permite resolver registros dispares en un único ID para su análisis en el nivel de la persona, en lugar de en el nivel de dispositivo o cookie.
* Los objetos y atributos del mismo campo XDM se combinan en una dimensión en Customer Journey Analytics. Para combinar varios atributos de varios conjuntos de datos en la misma dimensión de Customer Journey Analytics, los conjuntos de datos deben hacer referencia al mismo campo o esquema XDM.
