---
title: Análisis de Recorridos en todos los canales
description: Analice y extraiga información de las interacciones de los clientes en todo el recorrido del cliente.
exl-id: 285532b1-eb37-4984-9559-054a18515ddf
solution: Customer Journey Analytics
feature: Use Cases, Cross-Channel Analysis
role: User
source-git-commit: 5e80e68c6b5d3dca19dae21c6719b040b28afaf9
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 68%

---

# Análisis en canales múltiples {#cross-channel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-additional-datasets"
>title="Añadir conjuntos de datos adicionales a la conexión"
>abstract="Cuando haya añadido datos a un conjunto de datos de Adobe Experience Platform, podrá añadir ese conjunto de datos a su conexión en Customer Journey Analytics. Asegúrese de que, al añadir datos de otros canales, siguen el esquema que utiliza su organización.<br><br>Cada conjunto de datos que añada requiere una gran cantidad de trabajo, especialmente para garantizar que el identificador único exista para cada evento y para garantizar que la estructura de datos general se ajuste al esquema personalizado de su organización. Establecer este flujo de trabajo puede llevar varios meses de coordinación de muchos equipos en su organización."

<!-- markdownlint-enable MD034 -->

El análisis en canales múltiples permite una sola vista consolidada del comportamiento de los clientes en varios canales mediante la unificación de datos de varias propiedades web, móviles y sin conexión. Por ejemplo, puede utilizar esta vista consolidada para analizar las interacciones de los clientes en equipos de escritorio y dispositivos móviles, a fin de comprender el comportamiento de los clientes y extraer perspectivas para optimizar las experiencias de los clientes digitales. También puede analizar las interacciones de los clientes entre canales, incluidos los canales digitales y sin conexión, como las interacciones de soporte y las compras en la tienda, para comprender y optimizar mejor el recorrido del cliente.

## Pasos de la implementación

![Flujo de pasos de implementación como se describe en esta sección.](../assets/cca-architecture.png)

1. [Cree esquemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=es) para introducir los datos.
1. [Cree conjuntos de datos](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html?lang=es) para incorporar los datos.
1. [Ingesta de datos en Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html?lang=es):
   1. Datos basados en eventos ![event](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg) del sitio web o la aplicación móvil a través del conector de origen de Edge Network o Analytics.
   2. Datos de perfil ![perfil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg) (por ejemplo, de un sistema CRM, aplicación de centro de llamadas, aplicación de fidelidad).
   3. Datos de búsqueda ![lookup](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) (por ejemplo, nombre de producto, categoría de un sistema de información de productos).

1. Utilice un ID de área de nombres común en todos los conjuntos de datos. Use [La vinculación](../../stitching/overview.md) para elevar cualquier conjunto de datos basado en evento ![actualización de datos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataRefresh_18_N.svg) con respecto a proporcionar el ID común en cada fila. Tenga en cuenta que Customer Journey Analytics no utiliza actualmente los servicios de perfil o intentidad de Experience Platform para la vinculación.
1. Realice cualquier preparación de datos personalizada para asegurarse de que se incorpora una clave común en los conjuntos de datos de series temporales en Customer Journey Analytics.
1. Asigne un ID principal a los datos de búsqueda que pueda unirse a un campo en los datos de evento. Cuenta como filas en licencias.
1. Establezca el mismo ID principal para los datos de perfil que el ID principal de los datos de evento.
1. [Cree una conexión](../../connections/overview.md) para ingerir los conjuntos de datos relevantes de Experience Platform a Customer Journey Analytics.
1. [Cree una vista de datos](/help/data-views/create-dataview.md) con la conexión para seleccionar las dimensiones y métricas específicas que se incluirán en la vista. La configuración de atribución y asignación también se configura en la vista de datos. Estas configuraciones se calculan en el momento del informe.
1. [Cree un proyecto](/help/analysis-workspace/home.md) para configurar tableros e informes en Analysis Workspace.

## Consideraciones

Al establecer este flujo de trabajo, asegúrese de tener en cuenta los siguientes puntos.

* El análisis de datos entre canales requiere la misma área de nombres de ID en cada registro.
* El proceso de unión de conjuntos de datos dispares requiere una clave persona/entidad principal común en todos los conjuntos de datos.
* Actualmente no se admiten uniones secundarias basadas en claves.
* El proceso de vinculación permite volver a incrustar identidades en filas basadas en información de ID transitoria (como un ID de autenticación) de registros que comparten el mismo ID persistente. Esto permite resolver registros dispares en un único ID vinculado para su análisis en el nivel de persona, en lugar de en el nivel de dispositivo o cookie.
* Los objetos y atributos del mismo campo XDM se combinan en una dimensión en Customer Journey Analytics. Para combinar varios atributos de varios conjuntos de datos en la misma dimensión de Customer Journey Analytics, los conjuntos de datos deben hacer referencia al mismo campo o esquema XDM.

