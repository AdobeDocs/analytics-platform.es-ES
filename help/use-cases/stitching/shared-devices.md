---
title: Dispositivos compartidos
description: Explicación de cómo gestionar dispositivos compartidos mediante la vinculación y otras técnicas.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hidefromtoc: true
role: Admin
source-git-commit: d94f6d6b592b2ddecfa0b1024b9ae045b3c3ce11
workflow-type: tm+mt
source-wordcount: '993'
ht-degree: 6%

---


# Dispositivos compartidos

Este artículo proporciona contexto sobre dispositivos compartidos, cómo gestionar y mitigar los datos de dispositivos compartidos mediante la vinculación y comprender la exposición de dispositivos compartidos en sus datos mediante el servicio de consulta.

## ¿Qué es un dispositivo compartido?

Un dispositivo compartido es aquel que utiliza más de una persona. Los escenarios comunes son dispositivos como tabletas, dispositivos utilizados en quioscos o equipos informáticos compartidos por agentes en centros de llamadas.

Cuando dos personas utilizan el mismo dispositivo y ambas realizan una compra, los datos de evento de muestra pueden tener el siguiente aspecto:

| Marca de tiempo | Nombre de página | ID de dispositivo | Correo electrónico |
|---|---|---|---|
| 2023-05-12 12:01 | Página de inicio | 1234 | |
| 2023-05-12 12:02 | Página de producto | 1234 | |
| 2023-05-12 12:03 | Pedido realizado correctamente | 1234 | <ryan@a.com> |
| 2023-05-12 12:07 | Página de producto | 1234 | |
| 2023-05-12 12:08 | Pedido realizado correctamente | 1234 | <cassidy@a.com> |

Los eventos de éxito del pedido (compra) asignan los datos con precisión al correo electrónico correcto. El impacto de esta asignación en el análisis depende de cómo realice el análisis:

- Enfoque centrado en el dispositivo: análisis realizado con el ID del dispositivo. Con este enfoque, los datos autenticados y no autenticados se incluyen en el análisis. Sin embargo, este enfoque no permite un análisis más basado en personas.
- Enfoque centrado en la persona: análisis realizado mediante la dirección de correo electrónico u otro identificador de persona. Con este método, solo se incluyen en el análisis los eventos autenticados. Este método no proporciona una imagen completa del recorrido del cliente, incluida la adquisición

## Mejorar el análisis centrado en las personas

Para mejorar el análisis centrado en las personas de los dispositivos compartidos, tiene dos opciones: puede utilizar la vinculación o puede implementar la funcionalidad de restablecimiento de ECID. Ambos enfoques se analizan con más detalle en las secciones siguientes.

### Unión

El proceso de vinculación aborda las deficiencias del enfoque centrado en la persona. La vinculación agrega el identificador de persona seleccionado (en los datos de ejemplo, el correo electrónico) a los eventos en los que ese identificador no existe. La configuración aprovecha una asignación entre ID de dispositivo e ID de persona para garantizar que el tráfico autenticado y no autenticado se pueda utilizar en el análisis, manteniéndolo centrado en la persona. Consulte [Vinculación](/help/stitching/overview.md) para obtener más información.

La configuración puede atribuir datos de dispositivo compartidos mediante atribución de última autenticación o atribución de división del dispositivo. Sin embargo, los cambios de implementación mediante el restablecimiento de ECID también pueden abordar dispositivos compartidos.


#### Atribución de última autenticación

La última autenticación atribuye toda la actividad desconocida de un dispositivo compartido al usuario que se autenticó por última vez. Última autenticación se utiliza en Audience Manager y es el método preferido para los casos de uso del Perfil de datos del cliente en tiempo real. El servicio de identidad del Experience Platform crea el gráfico en función de la atribución de última autenticación y, como tal, se utiliza en la vinculación basada en gráficos. Consulte [Introducción a las reglas de vinculación de gráficos de identidad](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-linking-rules/overview) para obtener más información.

Cuando se utiliza la atribución de última autenticación en la vinculación, los ID vinculados se resuelven como se muestra en la tabla siguiente.

| Marca de tiempo | Nombre de página | ID de dispositivo | Correo electrónico | ID vinculado |
|---|---|---|---|---|
| 2023-05-12 12:01 | Página de inicio | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:02 | Página de producto | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:03 | Pedido realizado correctamente | 1234 | <ryan@a.com> | <cassidy@a.com> |
| 2023-05-12 12:07 | Página de producto | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:08 | Pedido realizado correctamente | 1234 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | Página de inicio | 1234 | | <cassidy@a.com> |


#### Device-split

La división del dispositivo atribuye la actividad anónima de un dispositivo compartido al usuario más próximo a la actividad anónima. La división del dispositivo se utiliza actualmente en la vinculación basada en el campo. La división de dispositivos es el enfoque preferido para los casos de uso analíticos, ya que la división de dispositivos da crédito por la actividad no autenticada y autenticada a la persona conocida más cercana. La división del dispositivo se utiliza actualmente en la vinculación basada en el campo.

Cuando se utiliza la atribución dividida por el dispositivo en la vinculación, los ID vinculados se resuelven como se muestra en la tabla siguiente.

| Marca de tiempo | Nombre de página | ID de dispositivo | Correo electrónico | ID vinculado |
|---|---|---|---|---|
| 2023-05-12 12:01 | Página de inicio | 1234 | | <ryan@a.com> |
| 2023-05-12 12:02 | Página de producto | 1234 | | <ryan@a.com> |
| 2023-05-12 12:03 | Pedido realizado correctamente | 1234 | <ryan@a.com> | <ryan@a.com> |
| 2023-05-12 12:07 | Página de producto | 1234 | | <ryan@a.com> |
| 2023-05-12 12:08 | Pedido realizado correctamente | 1234 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | Página de inicio | 1234 | | <cassidy@a.com> |


### Restablecimiento de ECID

Como su nombre indica, el restablecimiento de ECID implementa una funcionalidad que restablece el ECID en un déclencheur predeterminado, en la mayoría de los casos un evento de inicio de sesión o cierre de sesión. Con esta implementación, un solo dispositivo obtiene un nuevo ECID cada vez que se activa el déclencheur predeterminado. Básicamente, este restablecimiento fuerza al dispositivo a convertirse en *nuevo dispositivo* una y otra vez desde la perspectiva de los datos. El restablecimiento de ECID también ayuda a evitar que los dispositivos compartidos se muestren en los datos. No se requieren algoritmos adicionales, pero usted tiene la responsabilidad de implementar la señal de restablecimiento de ECID como parte de su implementación de recopilación de datos de Adobe.


Cuando se utiliza el restablecimiento de ECID, los ID conectados se resuelven como se muestra en la tabla siguiente.

| Marca de tiempo | Nombre de página | ID de dispositivo | Correo electrónico | ID vinculado |
|---|---|---|---|---|
| 2023-05-12 12:01 | Página de inicio | 1234 | | <ryan@a.com> |
| 2023-05-12 12:02 | Página de producto | 1234 | | <ryan@a.com> |
| 2023-05-12 12:03 | Pedido realizado correctamente | 1234 | <ryan@a.com> | <ryan@a.com> |
| 2023-05-12 12:07 | Página de producto | 5678 | | <cassidy@a.com> |
| 2023-05-12 12:08 | Pedido realizado correctamente | 5678 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | Página de inicio | 5678 | | <cassidy@a.com> |

## Exposición de dispositivo compartido

Tenga en cuenta varios factores para comprender correctamente la omnipresencia de los dispositivos compartidos en su organización. Además, comprender la contribución general de los eventos de dispositivos compartidos puede ayudarle a comprender el impacto en los datos de evento generales utilizados para el análisis.

Para comprender la exposición del dispositivo compartido, puede pensar en realizar las siguientes consultas.

1. Número de dispositivos compartidos. Puede utilizar una consulta que cuente los ID de dispositivo que tienen dos o más ID de persona asociados al ID de dispositivo. Una consulta de ejemplo podría tener el siguiente aspecto:

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


2. En el caso de los dispositivos compartidos, como resultado de la primera consulta, debe comprender cuántos eventos del total de eventos se pueden atribuir a estos dispositivos compartidos. Esta atribución le da una mejor idea del impacto de los dispositivos compartidos en los datos y del impacto cuando realiza el análisis. Una consulta de ejemplo podría tener el siguiente aspecto:

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

3. Para los eventos atribuidos a dispositivos compartidos (el resultado de la segunda consulta), debe comprender cuántos de estos eventos NO tienen un ID de persona. De lo contrario, ¿cuántos eventos de dispositivos compartidos son eventos anónimos? En última instancia, el algoritmo (última autenticación, división del dispositivo, restablecimiento de ECID) que seleccione para mejorar la calidad de los datos afecta a estos eventos anónimos de dispositivos compartidos. Una consulta de ejemplo podría tener el siguiente aspecto:

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

4. Por último, desea comprender la exposición que cada cliente experimentaría debido a la clasificación errónea de eventos. Para obtener esta exposición, debe calcular, para cada dispositivo compartido, el porcentaje de eventos anónimos relacionados con el número total de eventos. Una consulta de ejemplo podría tener el siguiente aspecto:

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


