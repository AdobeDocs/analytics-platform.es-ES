---
title: Información general de Data Mirror
description: Obtenga información sobre cómo sincronizar datos entre las soluciones nativas de Data Warehouse y Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta"
source-git-commit: 9bd124ad651274b48052edc56bfb72358aa2d79a
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 1%

---

# Información general sobre Experience Platform Data Mirror

{{release-limited-testing}}

Data Mirror es una funcionalidad de Experience Platform que permite la ingesta de cambios a nivel de fila desde bases de datos externas al lago de datos mediante esquemas basados en modelos. Conserva las relaciones de datos, fuerza la exclusividad y admite el control de versiones sin requerir procesos de extracción, transformación y carga (ETL) en sentido ascendente.

Utilice Data Mirror para sincronizar inserciones, actualizaciones y eliminaciones (datos mutables) de soluciones nativas externas del almacén de datos como [!DNL Snowflake], [!DNL Azure Databricks] o [!DNL Google BigQuery] directamente en Experience Platform. Data Mirror le ayuda a preservar la estructura y la integridad de los datos del modelo de base de datos existente a medida que introduce datos en Experience Platform.


## Capacidades y ventajas

Data Mirror proporciona las siguientes funciones esenciales para la sincronización de bases de datos:

* **Aplicación de clave principal**. Garantiza la exclusividad dentro de los conjuntos de datos y evita registros duplicados durante la ingesta.
* **Ingesta de cambios a nivel de fila**. Admite cambios de datos granulares, incluidas actualizaciones y eliminaciones con control de precisión.
* **Relaciones de esquema**. Habilita relaciones de clave externa y principal entre conjuntos de datos mediante descriptores.
* **Control de eventos desordenado**. Los procesos cambian eventos utilizando descriptores de versión y marca de tiempo, incluso cuando llegan fuera de secuencia.
* **Integración directa con el almacén**. Se conecta con almacenes de datos en la nube compatibles para la sincronización de cambios en tiempo real.

Utilice Data Mirror para introducir cambios directamente desde los sistemas de origen, aplicar la integridad del esquema y hacer que los datos estén disponibles para los flujos de trabajo de análisis, orquestación de recorrido y conformidad. Data Mirror elimina los procesos complejos de ETL ascendentes y acelera la implementación al permitir la duplicación directa de los modelos de base de datos existentes. Esta eliminación puede mejorar la gobernanza de los datos mediante un control preciso de las eliminaciones y las operaciones de higiene de los datos.

<!-- Add link when AEP docs are ready... -->

Consulte también la documentación de Experience Platform sobre Data Mirror.


## Data Mirror para Customer Journey Analytics

>[!NOTE]
>
>La funcionalidad Experience Platform Data Mirror para Customer Journey Analytics está disponible en **versión beta pública** hasta el 25 de marzo de 2026. Durante el período beta, las actualizaciones de la captura de datos de cambio (CDC) están limitadas al 0,5 % de las filas mensuales de datos de su organización. Las filas mensuales de datos se basan en su asignación anual para filas de datos divididas entre 12. Adobe se reserva el derecho de finalizar el acceso beta a Experience Platform Data Mirror para Customer Journey Analytics en caso de que su organización supere este límite.
>

La funcionalidad Experience Platform Data Mirror para Customer Journey Analytics está disponible para las soluciones nativas seleccionadas del Data Warehouse ([!DNL Azure Databricks], [!DNL Google BigQuery] y [!DNL Snowflake]). La versión de Customer Journey Analytics de la capacidad Data Mirror requiere una configuración y configuración adecuadas de varios componentes:

* [Solución nativa del Data Warehouse](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)


>[!MORELIKETHIS]
>
>[Guía de inicio rápido de Data Mirror: crear reflejos y utilizar datos basados en modelos](data-mirror.md)
>