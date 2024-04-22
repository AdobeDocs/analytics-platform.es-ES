---
title: Introducción a la migración a Customer Journey Analytics
description: Planifique la migración de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: 21d77f06595993172460b724dc7991cb9a5a02a8
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 8%

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
Esta página representa el paso 1 de la migración, como se muestra en la siguiente tabla. Complete todos los pasos de esta tabla para migrar de Adobe Analytics a Customer Journey Analytics.

| Tarea | Detalles |
|---------|----------|
| **Paso 1: [Introducción a la migración](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Conozca las ventajas de migrar a Adobe Analytics y el proceso de migración básico. |
| **Paso 2: [Elija el método de migración.](/help/getting-started/cja-migration/cja-migration-method.md)** | Hay varios métodos disponibles para migrar a Customer Journey Analytics. Elija el método que mejor se adapte a su organización, teniendo en cuenta el entorno actual de Adobe Analytics de su organización y sus objetivos a largo plazo. |
| **Paso 3: [Envío de datos a Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | El proceso de envío de datos a Adobe Experience Platform difiere según el método de migración elegido en el paso 1. |
| **Paso 4: [Asignación de datos al esquema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Esquemas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) se utilizan en Adobe Experience Platform para describir la estructura de los datos de una manera uniforme y reutilizable. Al definir los datos de forma coherente en todos los sistemas, resulta más fácil conservar el significado y, por lo tanto, obtener valor de los datos.<p>La mayoría de los métodos de migración requieren que cree un nuevo esquema XDM o que asigne el esquema de Adobe Analytics existente a XDM mediante la asignación de flujos de datos.</p> |
| **Paso 5: [Conservar datos históricos](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | La mayoría de las organizaciones necesitan conservar sus datos históricos de Adobe Analytics durante un periodo de tiempo determinado. Hay varias opciones disponibles para hacerlo. |
| **Paso 6: [Planificar la incorporación del usuario](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Debe dar a los usuarios tiempo suficiente (de 3 a 6 meses) para familiarizarse con las diferencias clave de Analysis Workspace en Customer Journey Analytics. |
| **Paso 7: [Puerto del uso de API de informes](/help/getting-started/cja-migration/cja-migration-api.md)** | La API de informes de Customer Journey Analytics tiene el mismo formato, pero utiliza un punto de conexión diferente. Publique el uso de la API de informes desde la API de informes de Adobe Analytics a la API de informes de Customer Journey Analytics. |
| **Paso 8: [Reemplazar fuentes de datos y Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decida cómo utilizará las opciones de exportación disponibles en Customer Journey Analytics para reemplazar las fuentes de datos y las funciones de Data Warehouse que utilizaba en Adobe Analytics. |
| **Paso 9: [Migrar proyectos y componentes](/help/getting-started/cja-migration/cja-migration-projects.md)** | El área Migración de componentes en Adobe Analytics le permite migrar proyectos y sus componentes asociados de Adobe Analytics a Customer Journey Analytics. |
| **Paso 10: [Realizar tareas posteriores a la migración](/help/getting-started/cja-getting-started.md)** | Una vez completada la migración, debe realizar varias tareas, como introducir otros datos en Experience Platform, crear conexiones entre conjuntos de datos de Platform y Customer Journey Analytics, crear vistas de datos y aprender a informar sobre datos de canales cruzados en Analysis Workspace. |

{style="table-layout:auto"}

## Primero, elija el método de migración

Hay varios métodos disponibles para migrar a Customer Journey Analytics. [Elija el método que mejor se adapte a su organización](/help/getting-started/cja-migration/cja-migration-method.md).

El método de migración que elija depende del entorno de Adobe Analytics actual de su organización y de los objetivos a largo plazo.
