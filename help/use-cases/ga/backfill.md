---
title: Ingesta de datos históricos de Google Analytics
description: Explica cómo utilizar Adobe Customer Journey Analytics para introducir los datos de los Google Analytics en Adobe Experience Platform.
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 90d1c51c11f0ab4d7d61b8e115efa8257a985446
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 88%

---


# Ingesta de datos históricos de Google Analytics

Esta página se centra en cómo introducir los datos históricos de Google Analytics en Adobe Experience Platform como un conjunto de datos, lo que le permite hacer referencia a ese conjunto de datos en una vista de datos dentro de Customer Journey Analytics. Puede combinar los pasos de esta página con la [Configuración de una implementación de Google Analytics activa](streaming.md), que genera un conjunto de datos recurrente. Combine este conjunto de datos histórico con el conjunto de datos de su implementación actual para obtener una vista perfecta de los datos en Customer Journey Analytics con los datos actuales y los rellenados.

## Requisitos previos

Para realizar estas tareas, necesita los siguientes permisos y acceso:

* Acceso a Adobe Experience Platform
* Acceso a Google Analytics (GA Standard o GA 360)
* [Acceso administrativo](/help/technotes/access-control.md) a Customer Journey Analytics

## Configuración de una exportación de BigQuery

La estructura de datos de las propiedades de Universal Analytics es diferente de la estructura de datos de las propiedades de Google Analytics 4. Configure una exportación de BigQuery basada en el tipo de propiedad desde el que desee exportar los datos:

* [Configuración de una exportación de BigQuery para una propiedad de Universal Analytics](https://support.google.com/analytics/answer/3416092)
* [Configuración de una exportación de BigQuery para una propiedad de Google Analytics 4](https://support.google.com/analytics/answer/9823238)

### Requisitos adicionales para las propiedades de Universal Analytics

>[!NOTE]
>
>Esta sección solo se aplica a las propiedades de Universal Analytics. Si está exportando desde una propiedad de GA4, puede continuar con [Exportación de datos a Google Cloud Platform](#export-gcp).

Las propiedades de Universal Analytics almacenan cada registro en sus datos como una sesión de usuario en lugar de como eventos individuales. Se requiere una consulta SQL para transformar los datos de Universal Analytics en un formato compatible con Adobe Experience Platform. Aplique la función `UNNEST` al campo `hits` en el esquema de GA y guárdelo como una tabla de BigQuery.

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

## Exportación de datos a Google Cloud Platform {#export-gcp}

En Google Cloud Platform, vaya a **Exportar > Exportar a GCS**. Una vez que los datos se encuentran en Google Cloud Storage, están listos para incorporarse a Adobe Experience Platform.

## Importación de los datos de Google Cloud Storage a Experience Platform

1. En Adobe Experience Platform, seleccione **[!UICONTROL Fuentes]** a la izquierda.
1. En el Catálogo, busque la opción **[!UICONTROL Google Cloud Storage]**. Haga clic en **[!UICONTROL Agregar datos]**.

>[!VIDEO](https://video.tv.adobe.com/v/332676)

>[!TIP]
>
>Si planea importar datos de Google Analytics de streaming activo e históricos, asegúrese de utilizar el mismo esquema para ambos conjuntos de datos. Puede combinar los conjuntos de datos en un Customer Journey Analytics usando un [Conjunto de datos combinado](/help/connections/combined-dataset.md).

Puede asignar los datos de evento de GA a un conjunto de datos existente que haya creado anteriormente, o crear uno, utilizando el esquema XDM que elija. Una vez que haya seleccionado el esquema, Experience Platform aplica el aprendizaje automático para asignar automáticamente previamente cada uno de los campos de los datos de Google Analytics a su [esquema XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es#ui).

![Asignación de esquema que resalta los campos de datos de GA y las asignaciones de esquema de Target](../assets/schema-map.png)

Una vez que haya terminado de asignar los campos al esquema XDM, puede programar esta importación de forma recurrente y aplicar la validación de errores durante el proceso de ingesta. Esta validación garantiza que no haya ningún problema con los datos importados.

## Campos XDM requeridos

Algunos campos XDM de Platform requieren el formato correcto para que los datos se procesen correctamente.

* **`timestamp`**: cree un campo calculado especial en la IU del esquema de Experience Platform. Haga clic en **[!UICONTROL Agregar campo calculado]** y ajuste la cadena `timestamp` en una función `date`:

  `date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

  Guarde el campo calculado en la estructura de datos de marca de tiempo del esquema:

  ![Marca de tiempo](../assets/timestamp.png)

* **`_id`**: este campo debe tener un valor en él, al Customer Journey Analytics no le importa cuál sea. Puede agregar un “1” al campo:

  ![ID](../assets/_id.png)

## Pasos siguientes

* Si tiene datos actuales que desea transmitir a Adobe Experience Platform, consulte [Configuración del streaming para datos de Google Analytics](streaming.md).
* Si quiere comenzar con la creación de informes sobre los datos rellenados, consulte [Creación de una conexión](/help/connections/create-connection.md).
