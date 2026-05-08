---
title: Información general de Data Mirror
description: Obtenga información sobre cómo sincronizar datos entre las soluciones nativas de Data Warehouse y Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
source-git-commit: dc3aa31c280c1a8ee8a0187edeca9bd34a2c9e2e
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# Información general sobre Experience Platform Data Mirror

{{release-limited-testing}}

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
>Data Mirror es una característica actualmente en fase beta que admite la sincronización de datos de almacenes de datos seleccionados mediante la captura de datos modificados (CDC) para su análisis en Customer Journey Analytics.<br/>Esta característica estará disponible para el público general en Customer Journey Analytics el 18 de junio de 2026. Consulte la Descripción del producto aplicable para comprender cómo podría afectar al consumo límite de ingesta anual a partir de ahora. Tenga en cuenta que su organización seguirá teniendo acceso a la función cuando Data Mirror pase de la versión beta a la versión de disponibilidad general.
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
