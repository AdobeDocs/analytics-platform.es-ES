---
title: Información general sobre Customer Journey Analytics Connections
description: Obtenga información sobre las conexiones en Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 93%

---

# Información general sobre conexiones

Las conexiones permiten a los administradores de productos de Customer Journey Analytics definir qué fuentes de datos de [!DNL  Experience Platform] se ingieren, como conjuntos de datos de evento, búsqueda, perfil y resumen. Las conexiones son la base de Customer Journey Analytics y determinan la disponibilidad de los datos (campos) que puede definir en una [vista de datos](/help/data-views/data-views.md) como dimensión o como métricas.

>[!IMPORTANT]
>
>Puede combinar varios conjuntos de datos de [!DNL Experience Platform] en una sola conexión.


## Flujo de trabajo Conexiones

![Flujo de trabajo Conexiones](assets/connection-workflow.png)

>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Conectarse a fuentes de datos](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/connections/connecting-customer-journey-analytics-to-data-sources-in-platform){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]

En un nivel superior, el flujo de trabajo Conexiones le permite lo siguiente:

| Interfaz | Descripción |
|:---:|---|
| ➊ | [Administrar sus conexiones y el uso general](manage-connections.md) de Customer Journey Analytics desde el Administrador de conexiones. |
| ➋ | [Inspeccionar los detalles de una conexión](manage-connections.md#connection-details), como los registros de conjuntos de datos ingeridos, omitidos o eliminados. |
| ➌ | [Crear o editar la configuración de una conexión](create-connection.md#create-or-edit-a-connection), como una ventana de datos móvil, la zona protegida que se va a usar, qué conjuntos de datos forman parte de la conexión y mucho más. |
| ➍ | [Añadir conjuntos de datos a una conexión](create-connection.md#add-datasets). La conexión debe tener al menos un conjunto de datos de evento o resumen, pero puede contener una variedad de conjuntos de datos de evento, perfil, búsqueda y resumen. |
| ➎ | [Configurar las opciones](create-connection.md#dataset-settings) de los conjuntos de datos que añada. Puede determinar cómo vincular diferentes conjuntos de datos en función de un identificador común basado en personas o en cuentas de [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}. |
| ➏ | [Editar la configuración de un conjunto de datos existente](create-connection.md#edit-a-dataset). Siempre puede volver a visitar la configuración del conjunto de datos en una etapa posterior. |



## Control de acceso

El acceso a la administración de conexiones debe restringirse a un grupo de administración principal. Las configuraciones a nivel de conexión tienen implicaciones contractuales con respecto a las asignaciones de volumen para los datos introducidos en Customer Journey Analytics.

>[!MORELIKETHIS]
>
>[Control de acceso](/help/technotes/access-control.md).

