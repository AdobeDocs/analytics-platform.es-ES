---
title: Dispositivos compartidos
description: Explicación de cómo gestionar dispositivos compartidos mediante la vinculación y otras técnicas.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a7d14968-33a2-46a8-8e32-fb6716650d0a
autotag-review: '2026-05-19T09:47:24.777Z'
TQID: 'https://experienceleague.adobe.com/8Xq8mUchtogMLiEuPVv-DWpkWtD5ubJGSQm2SRaZmps'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: faea9abd-7024-4c5e-a5b4-87919e09b24b
  - id: bf2b169f-d8b2-488a-97b9-f3bc9532e35c
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 726
ht-degree: 16%

---

# Dispositivos compartidos

Este artículo proporciona contexto sobre dispositivos compartidos, cómo manejar y mitigar los datos de dispositivos compartidos mediante la vinculación [stitching](/help/stitching/overview.md) y comprender la exposición de dispositivos compartidos en sus datos mediante el servicio de consulta.

## ¿Qué es un dispositivo compartido?

Un dispositivo compartido es aquel que utiliza más de una persona. Los escenarios comunes son dispositivos como tabletas, dispositivos utilizados en quioscos o equipos informáticos compartidos por agentes en un centro de llamadas.

Cuando dos personas utilizan el mismo dispositivo y ambas realizan una compra autenticada, los datos de evento de muestra pueden tener el siguiente aspecto:

| Evento | Marca de tiempo | Nombre de la página | ID de dispositivo | Correo electrónico |
|--:|---|---|---|---|
| 1 | 2023-05-12 12:01 | Página de inicio | `1234` | |
| 2 | 2023-05-12 12:02 | Página de producto | `1234` | |
| 3 | 2023-05-12 12:03 | Pedido realizado correctamente | `1234` | `ryan@a.com` |
| 4 | 2023-05-12 12:07 | Página de producto | `1234` | |
| 5 | 2023-05-12 12:08 | Pedido realizado correctamente | `1234` | `cassidy@a.com` |

Como puede ver en esta tabla, una vez que la autenticación se produce en los eventos 3 y 5, comienza a formarse un vínculo entre un ID de dispositivo y un ID de persona. Para comprender el impacto de cualquier esfuerzo de marketing en el nivel de persona, estos eventos no autenticados deben atribuirse a la persona correcta.

<!--
The order success (purchase) events assign the data accurately to the correct email. How this assignment impacts your analysis depends on how you perform analysis:

- Device centric approach: analysis performed using the Device ID. With this approach, both authenticated and unauthenticated data are included in analysis. However, this approach does not allow for a more person based analysis. 
- Person centric approach: analysis performed using the email address or other person identifier. With this approach, only authenticated events are included in the analysis. This approach doesn't provide a complete picture of the customer journey, including acquisition

-->

## Mejorar el análisis centrado en las personas

El proceso de vinculación soluciona este problema de atribución añadiendo el identificador de persona seleccionado (en los datos de ejemplo, el correo electrónico) a eventos en los que ese identificador no existe. La configuración aprovecha una asignación entre ID de dispositivo e ID de persona para garantizar que el tráfico autenticado y no autenticado se pueda utilizar en el análisis, manteniéndolo centrado en la persona. Consulte [Vinculación](/help/stitching/overview.md) para obtener más información.

La configuración puede atribuir datos de dispositivo compartidos mediante atribución de última autenticación o atribución de división del dispositivo. Todos los intentos de vincular eventos no autenticados a un usuario conocido no son deterministas.


### Atribución de última autenticación

La última autenticación atribuye toda la actividad desconocida de un dispositivo compartido al usuario que se autenticó por última vez. El servicio de identidad de Experience Platform crea el gráfico en función de la atribución de última autenticación y, como tal, se utiliza en la vinculación basada en gráficos. Consulte [Reglas de vinculación de gráficos de identidad](https://experienceleague.adobe.com/es/docs/experience-platform/identity/features/identity-graph-linking-rules/identity-optimization-algorithm#identity-optimization-algorithm-details) para obtener más información.

Cuando se utiliza la atribución de última autenticación en la vinculación, los ID vinculados se resuelven como se muestra en la tabla siguiente.

| Marca de tiempo | Nombre de la página | ID de dispositivo | Correo electrónico | ID vinculado |
|---|---|---|---|---|
| 2023-05-12 12:01 | Página de inicio | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:02 | Página de producto | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:03 | Pedido realizado correctamente | `1234` | `ryan@a.com` | `cassidy@a.com` |
| 2023-05-12 12:07 | Página de producto | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:08 | Pedido realizado correctamente | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Página de inicio | `1234` | | `cassidy@a.com` |


### Device-split

La división del dispositivo atribuye la actividad anónima de un dispositivo compartido al usuario conocido más reciente que ve en el pasado. La división del dispositivo se utiliza actualmente en la vinculación basada en el campo.

Cuando se utiliza la atribución dividida por el dispositivo en la vinculación, los ID vinculados se resuelven como se muestra en la tabla siguiente.

| Marca de tiempo | Nombre de la página | ID de dispositivo | Correo electrónico | ID vinculado |
|---|---|---|---|---|
| 2023-05-12 12:01 | Página de inicio | `1234` | | `ryan@a.com` |
| 2023-05-12 12:02 | Página de producto | `1234` | | `ryan@a.com` |
| 2023-05-12 12:03 | Pedido realizado correctamente | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Página de producto | `1234` | | `ryan@a.com` |
| 2023-05-12 12:08 | Pedido realizado correctamente | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Página de inicio | `1234` | | `cassidy@a.com` |


<!--

### ECID reset 

As the name implies, ECID reset implements functionality that resets the ECID on a predetermined trigger, in most cases a login or logout event. With this implementation, a single device gets a new ECID every time the predetermined trigger fires. Essentially, this reset forces the device to become a *new device* over and again from a data perspective. The ECID reset also helps to prevent shared devices from even showing up in the data. No additional algorithms are required, but you have the responsibility to implement the ECID reset signal as part of your Adobe data collection implementation.


When using ECID reset, Stitched IDs resolve as shown in the table below. 

| Timestamp | Page name | Device ID | Email | Stitched ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Home page | `1234` | | `ryan@a.com`|
| 2023-05-12 12:02 | Product page  | `1234` | |`ryan@a.com` |
| 2023-05-12 12:03 | Order success | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Product page  | 5678  | | `cassidy@a.com` |
| 2023-05-12 12:08 | Order success | 5678 |  `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Home page | 5678 | | `cassidy@a.com` |

-->

## Exposición de dispositivo compartido

Tenga en cuenta varios factores para comprender correctamente la omnipresencia de los dispositivos compartidos en su organización. Además, comprender la contribución general de los eventos de dispositivos compartidos puede ayudarle a comprender el impacto en los datos de evento generales utilizados para el análisis.

Para comprender la exposición del dispositivo compartido, puede pensar en realizar las siguientes consultas.

1. **Identificar dispositivos compartidos**

   Para comprender el número de dispositivos compartidos, realice una consulta que cuente los ID de dispositivo con dos o más ID de persona asociados. Esto ayuda a identificar los dispositivos utilizados por varias personas.

   ```sql
   SELECT COUNT(*)
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
         COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
     FROM /* INSERT DATASET HERE */
     GROUP BY 1
   )
   WHERE transient_count > 1; 
   ```


2. **Atribución de eventos a dispositivos compartidos**

   En el caso de los dispositivos compartidos identificados, determine cuántos eventos del total pueden atribuirse a estos dispositivos. Esta atribución proporciona a insight información sobre el impacto que los dispositivos compartidos tienen en los datos y las implicaciones para el análisis.

   ```sql
   SELECT COUNT(*) AS total_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) /
           COUNT(*)) * 100 AS shared_persistent_ids_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```

3. **Identificar eventos anónimos en dispositivos compartidos**

   Entre los eventos atribuidos a dispositivos compartidos, identifique cuántos carecen de un ID de persona, lo que indica eventos anónimos. El algoritmo que elija (por ejemplo, last-auth, device-split o ECID-reset) para mejorar la calidad de los datos afecta a estos eventos anónimos.

   ```sql
   SELECT COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) shared_persistent_ids_anon_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) /
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null))) * 100 AS shared_persistent_ids_anon_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */ 
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids 
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```

4. **Calcular exposición de clasificación errónea de eventos**

   Por último, evalúe la exposición a la que podría enfrentarse cada cliente debido a una clasificación errónea de los eventos. Calcule el porcentaje de eventos anónimos sobre el total de eventos para cada dispositivo compartido. Esto ayuda a comprender el impacto potencial en la precisión de los datos de los clientes.

   ```sql
   SELECT COUNT(*) AS total_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) /
           COUNT(*)) * 100 AS shared_persistent_ids_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */ 
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids 
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```
