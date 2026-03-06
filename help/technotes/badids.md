---
title: ID incorrectos de Customer Journey Analytics
description: Información sobre los ID incorrectos (BAVID) en Customer Journey Analytics. Obtenga información sobre cómo identificar ID incorrectos en sus datos, por qué afectan a la creación de informes y cómo investigar y resolver la exposición a ID incorrectos en sus conexiones.
solution: Customer Journey Analytics
feature: Basics
role: Admin
source-git-commit: b7b2a1f3eb1c149caf65ab3e4321e4f4347695cc
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 0%

---


# ID incorrectos

Este artículo proporciona contexto sobre los ID incorrectos y cómo detectar su presencia o el riesgo de que se produzcan en los datos mediante el servicio de consulta.


>[!INFO]
>
>Los ID incorrectos también se denominan BAVID en la interfaz de Customer Journey Analytics (se originan en [Analytics BAVID](https://experienceleague.adobe.com/es/docs/experience-cloud-kcs/kbarticles/ka-16444)).
>

## Definición

En Customer Journey Analytics, como parte de todos los datos definidos en una conexión, un ID incorrecto es un identificador:

* con un valor de ID específico que se origina
   * de un campo de ID de persona (conjuntos de datos no enlazados), **o**
   * desde un ID persistente o un campo de ID de persona (conjuntos de datos habilitados para la vinculación),

  **y**
* está en más de un millón (1 000 000) de eventos en los datos de conexión (contabilizados para todos los conjuntos de datos de la conexión), en un mes.

Cuando un valor de ID se marca como un ID incorrecto, los eventos futuros que contengan ese valor de ID se descartarán de los datos de conexión y no se mostrarán en los informes.

### Ejemplo

Un ejemplo de un escenario de ID incorrectos es que tiene valores personalizados o de marcador de posición en el campo ID de persona (por ejemplo, `undefined` para el tráfico anónimo). Para un conjunto de datos habilitado para la vinculación, esta situación puede tener un impacto aún mayor en los datos de informes, ya que la calidad de la vinculación se ve muy probablemente afectada. Para resolver esto, es posible que tenga que borrar y volver a habilitar la configuración de vinculación, incluida la eliminación de datos históricos de conjuntos de datos en la conexión.


## Métricas

La interfaz de Customer Journey Analytics Connection ofrece **[!UICONTROL ID incorrectos]** información de métricas en varios lugares de la interfaz.

* Puede ver **[!UICONTROL ID incorrectos]** (o **[!UICONTROL BAVIDs]**) como posibles motivos para omitir registros en el cuadro de diálogo **[!UICONTROL Comprobar detalles omitidos]**. Use **[!UICONTROL Comprobar detalles]** (si está disponible) debajo de **[!UICONTROL Registros omitidos]** en la [pantalla de detalles de una conexión](/help/connections/create-connection.md).
* Para un conjunto de datos habilitado para la vinculación, la [**[!UICONTROL vista previa del conjunto de datos]**](/help/stitching/use-stitching-ui.md#bad-ids) muestra **[!UICONTROL ID incorrectos]** como parte de las **[!UICONTROL métricas de vinculación]**. Esta métrica puede ayudarle a identificar posibles casos de ID incorrectos. Sin embargo, tenga en cuenta que esta métrica se calcula en función de un conjunto limitado de datos.

Consulte [Exposición de ID incorrectos](#bad-ids-exposure) para identificar la presencia de ID incorrectos para un conjunto de datos que planea usar en una conexión (independientemente de si la vinculación está habilitada o no).


## Exposición

Para investigar la exposición de ID incorrectos para un determinado campo de conjunto de datos, considere la posibilidad de realizar la siguiente consulta en el servicio de consultas de Experience Platform. Compruebe los principales valores de ID devueltos para ver si hay algún candidato para ID incorrectos. Tenga en cuenta que la [definición de ID incorrecta](#definition) tiene en cuenta todos los conjuntos de datos de la conexión.


### Identificación (riesgo) de ID incorrectos dentro de un campo

Puede utilizar Experience Platform Query para el servicio de ID a fin de identificar el riesgo potencial de ID incorrectos dentro de un campo.

La siguiente consulta devuelve los 20 primeros valores de ID de un campo. En orden descendente por recuento de eventos totales. Y donde cada valor se detecta dentro de un determinado intervalo (por ejemplo, en los últimos 30 días).

Ejecute esta consulta para un campo de ID de persona específico que desee analizar. Para un conjunto de datos que necesite vinculación, también puede ejecutar la consulta para un campo de ID persistente.

```sql
SELECT
    /* INSERT FIELD HERE */,
    COUNT(*) AS occurrences
FROM /* INSERT DATASET TABLE NAME HERE */
WHERE timestamp >= NOW() - INTERVAL '30 days' 
GROUP BY /* INSERT FIELD HERE */
ORDER BY occurrences DESC
LIMIT 20; 
```

En la consulta, reemplace `INSERT FIELD HERE` según el tipo de campo que investigue para los ID incorrectos:

* `full.field.path.from.XDM.schema` (para campos de cadena definidos en esquema XDM)
* `identityMap['namespace_value'][0].id` (para campos definidos con `namespace_value` en `identityMap`)

Compruebe los resultados para ver si hay valores de ID problemáticos. Como los valores personalizados o de marcador de posición, o valores con alta incidencia que obtienen o podrían llegar a cerca de 1 millón en un mes en el nivel de datos de conexión.
Incluso si la implementación aún se encuentra en la fase de desarrollo, debe evaluar el riesgo de presencia de ID incorrectos una vez que la configuración sea estable y esté lista para la producción.
