---
title: Información general de Data Mirror
description: Obtenga información sobre cómo sincronizar datos entre las soluciones nativas de Data Warehouse y Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
autotag-review: '2026-05-19T08:55:53.979Z'
TQID: 'https://experienceleague.adobe.com/10YCh2cnMTVriKKVOyYfzFfngvGQ2VVHOxzedE5NpWA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 2b0204c229a7d53c0a497fe448c165acf84536ad
workflow-type: tm+mt
source-wordcount: 455
ht-degree: 3%

---

# Información general sobre Experience Platform Data Mirror

Data Mirror es una funcionalidad de Experience Platform que permite la ingesta de cambios a nivel de fila desde bases de datos externas al lago de datos mediante esquemas relacionales. Conserva las relaciones de datos, fuerza la exclusividad y admite el control de versiones sin requerir procesos de extracción, transformación y carga (ETL) en sentido ascendente.

Utilice Experience Platform Data Mirror para sincronizar inserciones, actualizaciones y eliminaciones (datos mutables) de soluciones nativas externas de Data Warehouse ([!DNL Snowflake], [!DNL Azure Databricks] o [!DNL Google BigQuery]) directamente con datos de Experience Platform. Data Mirror le ayuda a preservar la estructura y la integridad de los datos del modelo de base de datos existente a medida que introduce datos en Experience Platform.

## Capacidades y ventajas

Data Mirror proporciona las siguientes funciones esenciales para la sincronización de bases de datos:

* **Aplicación de clave principal.** Garantiza la exclusividad dentro de los conjuntos de datos y evita registros duplicados durante la ingesta.
* **Ingesta de cambios a nivel de fila.** Admite cambios de datos granulares, incluidas actualizaciones y eliminaciones con control de precisión.
* **Relaciones de esquema.** Habilita relaciones de clave externa y principal entre conjuntos de datos mediante descriptores.
* **Control de eventos desordenado.** Los procesos cambian eventos utilizando descriptores de versión y marca de tiempo, incluso cuando llegan fuera de secuencia.
* **Integración directa con el almacén.** Se conecta con almacenes de datos en la nube compatibles para la sincronización de cambios en tiempo real.

Utilice Data Mirror para introducir cambios directamente desde los sistemas de origen, aplicar la integridad del esquema y hacer que los datos estén disponibles para los flujos de trabajo de análisis, orquestación de recorrido y conformidad. Data Mirror elimina los procesos complejos de ETL ascendentes y acelera la implementación al permitir la duplicación directa de los modelos de base de datos existentes. Esta eliminación puede mejorar la gobernanza de los datos mediante un control preciso de las eliminaciones y las operaciones de higiene de los datos.

Consulte también la [documentación de Experience Platform en Data Mirror](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/data-mirror/overview){target="_blank"}.

## Data Mirror para Customer Journey Analytics

>[!NOTE]
>
>Data Mirror es una característica que admite la sincronización de datos de almacenes de datos seleccionados mediante la captura de datos de cambio (CDC) para su análisis en Customer Journey Analytics.<br/>Consulte la descripción del producto aplicable para comprender cómo la característica puede afectar al consumo límite de ingesta anual.
>

>[!IMPORTANT]
>
>Los conjuntos de datos de captura de datos modificados que cree en Experience Platform para Data Mirror for Customer Journey Analytics no deben reutilizarse en otras soluciones de Experience Platform como Real-Time Customer Data Platform o Journey Optimizer. Si desea utilizar los mismos datos para estas soluciones, considere la posibilidad de crear conjuntos de datos alternativos con los mismos datos.
>



Experience Platform Data Mirror para Customer Journey Analytics está disponible para las soluciones nativas seleccionadas del Data Warehouse ([!DNL Azure Databricks], [!DNL Google BigQuery] y [!DNL Snowflake]). La versión de Customer Journey Analytics de Experience Platform Data Mirror requiere la configuración adecuada de las siguientes aplicaciones o componentes:

* [Soluciones nativas del almacén de datos](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)

>[!MORELIKETHIS]
>
>[Guía de inicio rápido de Data Mirror: crear reflejos y utilizar datos relacionales](relational.md)
>[Data Mirror (documentación de Experience Platform)](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/data-mirror/overview)
>[Esquemas relacionales (documentación de Experience Platform)](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/schema/relational)
