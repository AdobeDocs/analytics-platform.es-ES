---
title: Información general de Data Mirror
description: Obtenga información sobre cómo sincronizar datos entre las soluciones nativas de Data Warehouse y Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
source-git-commit: 3cd771669370a58230fc4806e2b7fb2fc16444b9
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 1%

---

# Información general sobre Experience Platform Data Mirror

{{release-limited-testing}}

Data Mirror es una funcionalidad de Experience Platform que permite la ingesta de cambios a nivel de fila desde bases de datos externas al lago de datos mediante esquemas basados en modelos. Conserva las relaciones de datos, fuerza la exclusividad y admite el control de versiones sin requerir procesos de extracción, transformación y carga (ETL) en sentido ascendente.

Utilice Experience Platform Data Mirror para sincronizar inserciones, actualizaciones y eliminaciones (datos mutables) de soluciones nativas externas de Data Warehouse ([!DNL Snowflake], [!DNL Azure Databricks] o [!DNL Google BigQuery]) directamente con datos de Experience Platform. Data Mirror le ayuda a preservar la estructura y la integridad de los datos del modelo de base de datos existente a medida que introduce datos en Experience Platform.

## Capacidades y ventajas

Data Mirror proporciona las siguientes funciones esenciales para la sincronización de bases de datos:

* **Aplicación de clave principal.** Garantiza la exclusividad dentro de los conjuntos de datos y evita registros duplicados durante la ingesta.
* **Ingesta de cambios a nivel de fila.** admite cambios de datos granulares, incluidas actualizaciones y eliminaciones con control de precisión.
* **Relaciones de esquema.** Habilita relaciones de clave principal y externa entre conjuntos de datos mediante descriptores.
* **Control de eventos desordenado.** procesos cambian eventos utilizando descriptores de versión y marca de tiempo, incluso cuando llegan fuera de secuencia.
* **Integración directa con el almacén.** se conecta con los almacenes de datos en la nube compatibles para sincronizar cambios en tiempo real.

Utilice Data Mirror para introducir cambios directamente desde los sistemas de origen, aplicar la integridad del esquema y hacer que los datos estén disponibles para los flujos de trabajo de análisis, orquestación de recorrido y conformidad. Data Mirror elimina los procesos complejos de ETL ascendentes y acelera la implementación al permitir la duplicación directa de los modelos de base de datos existentes. Esta eliminación puede mejorar la gobernanza de los datos mediante un control preciso de las eliminaciones y las operaciones de higiene de los datos.

Consulte también la documentación de Experience Platform sobre Data Mirror.

## Data Mirror para Customer Journey Analytics

>[!NOTE]
>
>La funcionalidad Experience Platform Data Mirror para Customer Journey Analytics está disponible en **versión beta pública** hasta el 25 de marzo de 2026. Durante el período beta, las actualizaciones de las capturas de datos de cambio (CDC) se limitan a 10 millones de filas de cambios diarios para Customer Journey Analytics. Adobe se reserva el derecho de finalizar el acceso beta a la funcionalidad de Experience Platform Data Mirror en caso de que su organización supere este límite. Para solicitar acceso a esta funcionalidad, póngase en contacto con el equipo de su cuenta de Adobe.
>

Experience Platform Data Mirror para Customer Journey Analytics está disponible para las soluciones nativas seleccionadas del Data Warehouse ([!DNL Azure Databricks], [!DNL Google BigQuery] y [!DNL Snowflake]). La versión de Customer Journey Analytics de Experience Platform Data Mirror requiere la configuración adecuada de las siguientes aplicaciones o componentes:

* [Soluciones nativas del Data Warehouse](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)

>[!MORELIKETHIS]
>
>[Guía de inicio rápido de Data Mirror: crear reflejos y utilizar datos basados en modelos](model-based.md)
>