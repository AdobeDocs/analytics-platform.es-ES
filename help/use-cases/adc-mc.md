---
title: Importación de Canales de marketing en CJA mediante el conector de datos de Analytics
description: Utilice la configuración correcta del conector de datos de Analytics para incorporar las reglas de procesamiento de Marketing Canal a Adobe Experience Platform.
translation-type: tm+mt
source-git-commit: 26486c79f6d94db1aa795bf024f581cad74c25f6
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 7%

---


# Importación de Canales de marketing en CJA mediante el conector de datos de Analytics

Si su organización utiliza el [conector de datos de Analytics](https://docs.adobe.com/content/help/es-ES/experience-platform/sources/connectors/adobe-applications/analytics.html) para llevar los datos del grupo de informes a CJA, puede configurar una conexión en CJA para informar sobre las dimensiones de Marketing Canal.

## Requisitos previos

* Los datos del grupo de informes ya deben importarse a Adobe Experience Platform mediante el [conector de datos de Analytics](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html).
* Las reglas de procesamiento de Marketing canal ya deben estar configuradas. Consulte [Reglas de procesamiento para Canales de marketing](https://docs.adobe.com/content/help/es-ES/analytics/components/marketing-channels/c-rules.html) en la guía Componentes de Analytics tradicionales.

## Elementos de esquema de Marketing Canal

Una vez que utilice el conector de datos de Analytics en un grupo de informes deseado, se creará un esquema XDM. Este esquema contiene todas las dimensiones y métricas de Analytics como datos sin procesar. Estos datos sin procesar no contienen atribución ni persistencia. En su lugar, cada visita se ejecuta a través de las reglas de procesamiento del canal de mercadotecnia y registra la primera regla que coincide. Especifique la atribución y la persistencia al crear una vista de datos en CJA.

1. [Cree una ](/help/connections/create-connection.md) conexión que incluya un conjunto de datos basado en el conector de datos de Analytics.
2. [Cree una ](/help/data-views/create-dataview.md) vista de datos que incluya las siguientes dimensiones:
   * **`channel.typeAtSource`**:: Equivalente a la dimensión  [de canal ](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-channel.html) de marketing.
   * **`channel._id`**:: Equivalente al detalle del canal  [de marketing](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-detail.html)
3. Proporcione a cada dimensión el modelo de atribución y la persistencia deseados. Si desea dimensiones de primer toque y de último toque, arrastre cada dimensión de canal de marketing al área de componentes varias veces. Proporcione a cada dimensión el modelo de atribución y la persistencia deseados. Adobe también recomienda asignar un nombre para mostrar a cada dimensión para facilitar su uso en Workspace.
4. Cree la vista de datos.

Sus dimensiones de canal de marketing ya están disponibles para su uso en Analysis Workspace.

## Diferencias de procesamiento y arquitectura

>[!IMPORTANT]
>
>Existen varias diferencias fundamentales entre los datos del grupo de informes y los datos de la plataforma. Adobe recomienda encarecidamente ajustar las reglas de procesamiento de canales de mercadotecnia del grupo de informes para facilitar la recopilación adecuada de datos en la plataforma.


Dado que las dimensiones de canal de primer y último toque son básicamente la misma dimensión con diferentes modelos de atribución, puede volver a crear dimensiones similares cuando [cree una vista de datos](/help/data-views/create-dataview.md). Se pueden crear varias dimensiones basadas en el mismo elemento de esquema, lo que les proporciona distintos modelos de atribución y persistencia.

## Diferencias entre

