---
title: Dispositivos compartidos
description: Explicación de cómo gestionar dispositivos compartidos mediante la vinculación y otras técnicas.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a7d14968-33a2-46a8-8e32-fb6716650d0a
source-git-commit: 81d1c6abbda63c4ac8cdcc96d1b730974b137ad9
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 6%

---

# Dispositivos compartidos

Este artículo proporciona contexto sobre dispositivos compartidos, cómo manejar y mitigar los datos de dispositivos compartidos mediante la vinculación [stitching](/help/stitching/overview.md) y comprender la exposición de dispositivos compartidos en sus datos mediante el servicio de consulta.

## ¿Qué es un dispositivo compartido?

Un dispositivo compartido es aquel que utiliza más de una persona. Los escenarios comunes son dispositivos como tabletas, dispositivos utilizados en quioscos o equipos informáticos compartidos por agentes en centros de llamadas.

Cuando dos personas utilizan el mismo dispositivo y ambas realizan una compra, los datos de evento de muestra pueden tener el siguiente aspecto:

| Evento | Marca de tiempo | Nombre de página | ID de dispositivo | Correo electrónico |
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

La última autenticación atribuye toda la actividad desconocida de un dispositivo compartido al usuario que se autenticó por última vez. El servicio de identidad del Experience Platform crea el gráfico en función de la atribución de última autenticación y, como tal, se utiliza en la vinculación basada en gráficos. Consulte [Introducción a las reglas de vinculación de gráficos de identidad](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-linking-rules/overview) para obtener más información.

Cuando se utiliza la atribución de última autenticación en la vinculación, los ID vinculados se resuelven como se muestra en la tabla siguiente.

| Marca de tiempo | Nombre de página | ID de dispositivo | Correo electrónico | ID vinculado |
|---|---|---|---|---|
| 2023-05-12 12:01 | Página de inicio | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:02 | Página de producto | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:03 | Pedido realizado correctamente | `1234` | `ryan@a.com` | `cassidy@a.com` |
| 2023-05-12 12:07 | Página de producto | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:08 | Pedido realizado correctamente | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Página de inicio | `1234` | | `cassidy@a.com` |


### Device-split

La división del dispositivo atribuye la actividad anónima de un dispositivo compartido al usuario más próximo a la actividad anónima. La división del dispositivo se utiliza actualmente en la vinculación basada en el campo.

Cuando se utiliza la atribución dividida por el dispositivo en la vinculación, los ID vinculados se resuelven como se muestra en la tabla siguiente.

| Marca de tiempo | Nombre de página | ID de dispositivo | Correo electrónico | ID vinculado |
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

   En el caso de los dispositivos compartidos identificados, determine cuántos eventos del total pueden atribuirse a estos dispositivos. Esta atribución proporciona una perspectiva del impacto que los dispositivos compartidos tienen en los datos y las implicaciones para el análisis.

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
