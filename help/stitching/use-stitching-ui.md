---
title: Usar vinculación
description: Cómo usar la vinculación
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
badgePremium: label="Beta" type="Informative"
source-git-commit: 23b890ec6a3266d1ca0621b09264f1d6a2f82645
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 3%

---

# Usar vinculación

Puede habilitar la vinculación en uno o varios conjuntos de datos de evento que haya configurado como parte de la conexión. El paquete de Customer Journey Analytics con licencia determina el número de conjuntos de datos de evento que puede habilitar para la vinculación

{{release-limited-testing}}

Puede habilitar la vinculación como parte de la [configuración del conjunto de datos](/help/connections/create-connection.md#dataset-settings) para un conjunto de datos de evento al [crear una conexión](/help/connections/create-connection.md) o al [editar una conexión](/help/connections/manage-connections.md#edit-a-connection).

## Requisitos previos

Para habilitar la vinculación en un conjunto de datos de evento dentro de la interfaz de usuario de Conexiones:

* El esquema en el que se basa el conjunto de datos debe tener:

   * Varios campos configurados como identidad y que le permiten seleccionar valores diferentes para un ID persistente y un ID de persona.
   * al menos un campo marcado como identidad principal con un área de nombres asociada en caso de que desee utilizar el mapa de identidad y el área de nombres de identidad principal para un ID persistente o ID de persona.

* El conjunto de datos de evento debe estar [habilitado para el servicio de identidad](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) en caso de que desee usar el gráfico de identidad y la vinculación basada en gráficos.


## Comprobaciones previas

Si cumple los requisitos previos, es posible que desee realizar algunas comprobaciones previas de los datos del conjunto de datos de evento antes de habilitar la vinculación de identidad:

* Asegúrese de que las identidades se marquen correctamente en el esquema del conjunto de datos de evento. [Consulte Información general del área de nombres de identidad](https://experienceleague.adobe.com/es/docs/experience-platform/identity/features/namespaces).
* Compruebe la cobertura de identidad tanto para el ID persistente como para el ID de persona:
   * ID persistente: consulte 7 días de datos en los que el campo de ID persistente no sea nulo y divida los datos por una consulta de 7 días para todos los eventos del conjunto de datos. Este porcentaje debe ser superior al 95 %.

     Ejemplo de una consulta que puede utilizar para la verificación:

     ```sql
     SELECT
       COUNT(*) AS total_events,
       COUNT({PERSISTENT_ID_FIELD}) AS events_with_persistentid,
       ROUND(COUNT({PERSISTENT_ID_FIELD}) / COUNT(*), 2) AS percent_with_persistentid_not_null
     FROM 
       {DATASET_TABLE_NAME}
     WHERE
       TO_TIMESTAMP(timestamp, '{FORMAT_STRING}') >= TIMESTAMP '{START_DATE}'
       AND TO_TIMESTAMP(timestamp, 'FORMAT_STRING') < TIMESTAMP '{END_DATE}';
     ```

     Donde:

      * `{PERSISTENT_ID_FIELD}` es el campo para el identificador persistente. Por ejemplo: `identityMap.ecid[0]`.
      * `{DATASET_TABLE_NAME}` es el nombre de tabla para el conjunto de datos de evento.
      * `{FORMAT_STRING}` es la cadena de formato para el campo de marca de tiempo. Por ejemplo: `MM/DD/YY HH12:MI AM`.
      * `{START_DATE} ` es la fecha de inicio. Por ejemplo: `2024-01-01 00:00:00`.
      * `{END_DATE}` es la fecha de finalización en formato estándar. Por ejemplo: `2024-01-08 00:00:00`.


   * ID de persona: consulte 7 días de datos en los que el campo de ID de persona no sea nulo y divida los datos por una consulta de 7 días para todos los eventos del conjunto de datos. Este porcentaje debe ser superior al 5 %.

     Ejemplo de una consulta que puede utilizar para la verificación:

     ```sql
     SELECT
       COUNT(*) AS total_events,
       COUNT({PERSON_ID_FIELD}) AS events_with_personid,
       ROUND(COUNT({PERSON_ID_FIELD}) / COUNT(*), 2) AS percent_with_personid_not_null
     FROM 
       {DATASET_TABLE_NAME}
     WHERE
       TO_TIMESTAMP(timestamp, '{FORMAT_STRING}') >= TIMESTAMP '{START_DATE}'
       AND TO_TIMESTAMP(timestamp, 'FORMAT_STRING') < TIMESTAMP '{END_DATE}';
     ```

     Donde:

      * `{PERSON_ID_FIELD}` es el campo para el ID de persona. Por ejemplo: `identityMap.crmId[0]`.
      * `{DATASET_TABLE_NAME}` es el nombre de tabla para el conjunto de datos de evento.
      * `{FORMAT_STRING}` es la cadena de formato para el campo de marca de tiempo. Por ejemplo: `MM/DD/YY HH12:MI AM`.
      * `{START_DATE}` es la fecha de inicio. Por ejemplo: `2024-01-01 00:00:00`.
      * `{END_DATE}` es la fecha de finalización en formato estándar. Por ejemplo: `2024-01-08 00:00:00`.



## Habilitación de la vinculación de identidad

>[!NOTE]
>
>Si **[!UICONTROL Habilitar vinculación de identidad]** no está disponible en la interfaz Conexiones, use el procedimiento de [solicitud para habilitar la vinculación](/help/stitching/use-stitching.md) en un conjunto de datos.



Para habilitar la vinculación, en la sección del conjunto de datos de evento del cuadro de diálogo **[!UICONTROL Agregar conjuntos de datos]** o **[!UICONTROL Editar conjunto de datos]**:

![Opciones de vinculación de identidad al habilitar la vinculación de identidad](assets/identity-stitching-ui.png)

1. Seleccione **[!UICONTROL Habilitar vinculación de identidad]**.

   Si habilita la vinculación para un conjunto de datos de evento existente, el cuadro de diálogo **[!UICONTROL Cambiar ID de persona]** muestra las implicaciones de un cambio del ID de persona debido al uso de la vinculación. Seleccione **[!UICONTROL Continuar]** para continuar.

   El cuadro de diálogo **[!UICONTROL Habilitar vinculación de identidad]** resume las consecuencias de vincular identidades. Seleccione **[!UICONTROL Continuar]** para continuar.

1. Seleccione un ID persistente del menú desplegable **[!UICONTROL ID persistente]**.

   Si selecciona **[!UICONTROL mapa de identidad]** para el ID persistente, debe seleccionar un área de nombres Tiene dos opciones:

   * Habilitar **[!UICONTROL Usar el área de nombres de identidad principal]** para usar el área de nombres de identidad principal.
   * Seleccione un área de nombres del menú desplegable **[!UICONTROL Área de nombres]**.

1. Seleccione un ID de persona en el menú desplegable **[!UICONTROL ID de persona]**.

   Si selecciona **[!UICONTROL mapa de identidad]** para el ID de persona, debe seleccionar un área de nombres. Tiene dos opciones:

   * Habilitar **[!UICONTROL Usar el área de nombres de identidad principal]** para usar el área de nombres de identidad principal.
   * Seleccione un área de nombres del menú desplegable **[!UICONTROL Área de nombres]**.


   Si selecciona **[!UICONTROL Gráfico de identidad]** para el ID de persona (para usar [vinculación basada en gráficos](/help/stitching/gbs.md)), debe seleccionar un área de nombres.

   >[!NOTE]
   >
   >Asegúrese de que tiene derecho a utilizar el gráfico de identidad.
   >

   Antes de eso, se muestra el cuadro de diálogo **[!UICONTROL Cambiar al gráfico de identidad]** para asegurarse de que ha [finalizado la configuración del gráfico de identidad para el conjunto de datos](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) antes de usar el gráfico de identidad para la vinculación. Seleccione **[!UICONTROL Continuar]** para continuar.

   * Seleccione un área de nombres del menú desplegable **[!UICONTROL Área de nombres]**.


1. Seleccione una ventana retrospectiva en el menú desplegable **[!UICONTROL Ventana retrospectiva]**. Las opciones disponibles dependen del paquete de Customer Journey Analytics al que esté autorizado.

Una vez guardada una conexión que contiene conjuntos de datos habilitados para la vinculación de identidad, el proceso de vinculación de cada conjunto de datos comienza cuando se inicia la ingesta de datos para ese conjunto de datos.

## Limitaciones

Además de las [limitaciones de vinculación basadas en el campo](/help/stitching/fbs.md#limitations) y las [limitaciones de vinculación basadas en gráficos](/help/stitching/gbs.md#limitations), se aplican las siguientes limitaciones al habilitar la vinculación en la interfaz Conexiones:

* Solo puede vincular un conjunto de datos de evento una vez como parte de una sola conexión. No puede definir el mismo conjunto de datos de evento más de una vez y utilizar una configuración de vinculación independiente para cada instancia. Si desea aplicar diferentes configuraciones de vinculación en el mismo conjunto de datos, utilice una conexión independiente para cada configuración.

