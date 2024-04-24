---
title: Introducción a la migración a Customer Journey Analytics
description: Planifique la migración de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: 7bc4425f11980780ab64a201029cd63e4bd7849c
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 10%

---

# Paso 1: Introducción a la migración a Customer Journey Analytics

Customer Journey Analytics es la próxima generación de análisis. Permite la recopilación de datos multicanal (tanto datos en línea como sin conexión), combinados con una potente funcionalidad de procesamiento de tiempo de informes (a través de la definición de componentes y campos derivados en vistas de datos).

Antes de comenzar el proceso de migración de Adobe Analytics a Customer Journey Analytics, debe comprender las ventajas de Customer Journey Analytics, así como los pasos necesarios para que la migración se realice correctamente.

## Comprender las ventajas de Customer Journey Analytics

A continuación se indican algunas de las ventajas principales: (Para obtener una lista completa, así como más información sobre cada una de estas características clave, consulte [Funciones disponibles solo en Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics).)

* [Informes multicanal](/help/getting-started/aa-to-cja-user.md#changes-to-data-architecture)

  Customer Journey Analytics se combina con la capacidad de Experience Platform para albergar todo tipo de esquemas y datos. Recopile datos e informe sobre ellos desde varios canales, como digital (web), sistemas de puntos de venta, móvil, CRM y muchos más.

* [Transformaciones de tiempo de los informes en vistas de datos](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md#customer-journey-analytics-data-views)

  Las vistas de datos de Customer Journey Analytics le permiten interpretar aún más los datos de una conexión. Puede modificar o quitar datos sin cambiar la implementación, utilizar subcadenas para manipular dimensiones, crear métricas a partir de cualquier valor, filtrar subeventos o utilizar campos derivados. Todas estas transformaciones son no destructivas.

* [Las transformaciones se aplican a datos nuevos e históricos](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)

  La manipulación de la vista de datos se puede aplicar a datos nuevos e históricos de una manera no destructiva.

* [Campos derivados](/help/data-views/derived-fields/derived-fields.md)

  Los campos derivados permiten realizar transformaciones en el tiempo del informe de los datos. Los datos pueden combinarse, corregirse o crearse sobre la marcha y aplicarse de forma retroactiva a todos los informes.

* [Las vistas de datos reemplazan a los grupos de informes virtuales](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-virtual-report-suites)

  Las vistas de datos toman el concepto de grupos de informes virtuales tal como existen hoy en día y lo amplían para habilitar controles adicionales en los datos disponibles mediante conexiones. Estos cambios hacen que la configuración general, como los intervalos de huso horario y de tiempo de espera de sesión, sea configurable y retroactiva.

* [Métricas y dimensiones de clientes ilimitadas](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-evars-and-props)

  Los valores pueden ser numéricos, texto, objetos, listas o mezclas de todos. Los Dimension pueden estar anidados o ser jerárquicos.

## Comprensión del proceso de migración

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
La información de esta página cubre el paso 1 de la migración, como se indica en la tabla siguiente. Complete todos los pasos de esta tabla para migrar de Adobe Analytics a Customer Journey Analytics.

| Tarea de migración | Detalles |
|---------|----------|
| <span class="preview">**Paso 1: Introducción a la migración**</span> | <span class="preview">Conozca las ventajas de migrar a Adobe Analytics y el proceso de migración básico.</span> |
| **Paso 2: [Elija la ruta de migración](/help/getting-started/cja-migration/cja-migration-path.md)** | Hay varios métodos disponibles para migrar a Customer Journey Analytics. Elija el método que mejor se adapte a su organización, según el entorno de Adobe Analytics actual de su organización y los objetivos a largo plazo. |
| **Paso 3: [Envío de datos a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | El proceso de envío de datos a Adobe Experience Platform difiere según la ruta de migración elegida en el paso 2. |
| **Paso 4: [Conservar datos históricos](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La mayoría de las organizaciones necesitan conservar sus datos históricos de Adobe Analytics durante un periodo de tiempo determinado. Hay varias opciones disponibles para hacerlo. |
| **Paso 5: [Realizar tareas de implementación adicionales](/help/getting-started/cja-getting-started.md)** | En este punto del proceso de migración, debe realizar varias tareas antes de que el entorno del Customer Journey Analytics esté listo para su uso.<p>Estas tareas adicionales se aplican a las migraciones desde Adobe Analytics, así como a las implementaciones de nuevos Customer Journey Analytics.</p><p>Estas tareas incluyen:</p><ul><li>Introducción de otros datos en Experience Platform</li><li>Creación de conexiones entre conjuntos de datos de Platform y el Customer Journey Analytics</li><li>Creación de vistas de datos</li><li>Transferencia del uso de API de informes</li><li>Contabilidad de fuentes de datos y Data Warehouse</li><li>Migración de proyectos y componentes</li><li>Planificación de la incorporación del usuario</li></ul> <p>Para obtener más información, consulte [Introducción al Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

## Primero, elija la ruta de migración

Hay varios métodos disponibles para migrar a Customer Journey Analytics. [Elija el método que mejor se adapte a su organización](/help/getting-started/cja-migration/cja-migration-path.md).

La ruta de migración que elija dependerá del entorno de Adobe Analytics actual de su organización y de los objetivos a largo plazo.
