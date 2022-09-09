---
title: Ingesta de datos históricos de Google Analytics en Adobe Experience Platform
description: Explica cómo utilizar Customer Journey Analytics (CJA) para introducir los datos de sus Google Analytics en Adobe Experience Platform.
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: f65f13d696ad2045f58ccb5c9ef7fed45eb9d68c
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 9%

---


# Ingesta de datos históricos de Google Analytics en Adobe Experience Platform

Esta página se centra en cómo introducir los datos históricos de sus Google Analytics en Adobe Experience Platform como un conjunto de datos, lo que le permite hacer referencia a ese conjunto de datos en una vista de datos dentro de un Customer Journey Analytics. Puede combinar los pasos de esta página con [Configuración de una implementación de Google Analytics activos](streaming.md), que genera un conjunto de datos recurrente. Combine este conjunto de datos histórico con el conjunto de datos de su implementación actual para obtener una vista perfecta de los datos en Customer Journey Analytics con los datos actuales y los rellenados.

## Requisitos previos

Para realizar estas tareas, necesita los siguientes permisos y acceso:

* Acceso a Adobe Experience Platform
* Acceso a Google Analytics (GA Standard o GA 360)
* [Acceso de administrador](/help/getting-started/cja-access-control.md) al Customer Journey Analytics

## Configurar una exportación BigQuery

La estructura de datos de las propiedades de Universal Analytics es diferente de la estructura de datos de las propiedades de Google Analytics 4. Configure una exportación BigQuery basada en el tipo de propiedad desde el que desee exportar los datos:

* [Configurar una exportación BigQuery para una propiedad de Universal Analytics](https://support.google.com/analytics/answer/3416092)
* [Configurar una exportación BigQuery para una propiedad de Google Analytics 4](https://support.google.com/analytics/answer/9823238)

### Requisitos adicionales para las propiedades de Universal Analytics

>[!NOTE]
>
>Esta sección solo se aplica a las propiedades de Universal Analytics. Si está exportando desde una propiedad de GA4, puede continuar con [Exportar datos a Google Cloud Platform](#export-gcp).

Las propiedades de Universal Analytics almacenan cada registro en sus datos como una sesión de usuario en lugar de como eventos individuales. Se requiere una consulta SQL para transformar los datos de Universal Analytics en un formato compatible con Adobe Experience Platform. Aplique la variable `UNNEST` a la función `hits` en el esquema GA y guárdelo como tabla BigQuery.

>[!VIDEO](https://video.tv.adobe.com/v/332634)

```sql
SELECT
   *,
   timestamp_seconds(`visitStartTime` + hit.time) AS `timestamp` 
FROM
   (
      SELECT
         fullVisitorId,
         visitNumber,
         visitId,
         visitStartTime,
         trafficSource,
         socialEngagementType,
         channelGrouping,
         device,
         geoNetwork,
         hit 
      FROM
         `example_bq_table_*`,
         UNNEST(hits) AS hit 
   )
```

## Exportar datos a Google Cloud Platform {#export-gcp}

En Google Cloud Platform, vaya a **Exportar > Exportar a GCS**. Una vez que los datos se encuentran en Google Cloud Storage, están listos para ser incorporados a Adobe Experience Platform.

## Importar los datos del almacenamiento en la nube de Google en Experience Platform

1. En Adobe Experience Platform, seleccione **[!UICONTROL Fuentes]** a la izquierda.
1. En el Catálogo, busque **[!UICONTROL Almacenamiento en la nube de Google]** . Haga clic en **[!UICONTROL Añadir datos]**.

>[!VIDEO](https://video.tv.adobe.com/v/332676)

>[!TIP]
>
>Si planea importar datos de Google Analytics de flujo continuo en vivo e históricos, asegúrese de utilizar el mismo esquema para ambos conjuntos de datos. Puede combinar los conjuntos de datos en una CJA mediante una [Conjunto de datos combinado](/help/connections/combined-dataset.md).

Puede asignar los datos de evento GA a un conjunto de datos existente que haya creado anteriormente, o crear un conjunto de datos, utilizando el esquema XDM que elija. Una vez que haya seleccionado el esquema, Experience Platform aplica el aprendizaje automático para asignar automáticamente previamente cada uno de los campos de los datos de Google Analytics a su [esquema XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es#ui).

![Mapa del esquema](../assets/schema-map.png)

Una vez que haya terminado de asignar los campos al esquema XDM, puede programar esta importación de forma recurrente y aplicar la validación de errores durante el proceso de ingesta. Esta validación garantiza que no haya ningún problema con los datos importados.

## Campos XDM requeridos

Algunos campos XDM de Platform requieren el formato correcto para que los datos se procesen correctamente.

* **`timestamp`**: Cree un campo calculado especial en la interfaz de usuario del esquema del Experience Platform. Haga clic en **[!UICONTROL Añadir campo calculado]** y ajuste la variable `timestamp` cadena en un `date` función:

   `date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

   Guarde el campo calculado en la estructura de datos de marca de tiempo del esquema :

   ![Marca de tiempo](../assets/timestamp.png)

* **`_id`**: Este campo debe tener un valor en él: a CJA no le importa cuál sea el valor. Puede añadir un &quot;1&quot; al campo:

   ![ID](../assets/_id.png)

## Pasos siguientes

* Si tiene datos actuales que desea transmitir a Adobe Experience Platform, consulte [Configuración de flujo continuo para datos de Google Analytics](streaming.md).
* Si desea comenzar a generar informes sobre los datos rellenados, consulte [Crear una conexión](/help/connections/create-connection.md).
