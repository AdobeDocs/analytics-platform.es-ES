---
title: Introducción a la actualización a Customer Journey Analytics
description: Planifique la actualización de Adobe Analytics a Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 56%

---

# Paso 1: Introducción a la actualización a Customer Journey Analytics

>[!AVAILABILITY]
>
>La información de esta página se reemplaza con la siguiente información de actualización más completa: <ul><li>**Pasos de actualización recomendados**<p>Para obtener información detallada, consulte [Ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Guía de actualización de Customer Journey Analytics**<p>Hay disponible una nueva guía de actualización que genera dinámicamente pasos de actualización adaptados a su organización y a sus circunstancias únicas.</p><p>Para acceder a la guía desde Customer Journey Analytics, selecciona la pestaña **[!UICONTROL Workspace]** y, a continuación, selecciona **[!UICONTROL Actualizar a Customer Journey Analytics]** en el panel izquierdo. Siga las instrucciones que aparecen en pantalla.</p></li></ul>

Customer Journey Analytics es la próxima generación de análisis. Permite la recopilación de datos multicanal (tanto datos en línea como sin conexión), combinados con una potente funcionalidad de procesamiento en el tiempo de los informes (a través de la definición de componentes y campos derivados en vistas de datos).

Antes de comenzar el proceso de actualización de Adobe Analytics a Customer Journey Analytics, debe comprender las ventajas de Customer Journey Analytics, así como los pasos necesarios para una actualización correcta.

## Conocer las ventajas de Customer Journey Analytics

A continuación se indican algunas de las ventajas principales: (para obtener una lista completa, así como más información sobre cada una de estas características clave, consulte [Funciones disponibles solo en Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics).)

* [Creación de informes multicanal](/help/getting-started/aa-to-cja-user.md#changes-to-data-architecture)

  Customer Journey Analytics se combina con la capacidad de Experience Platform para albergar todo tipo de esquemas y datos. Recopile datos e informe sobre ellos desde varios canales, como digital (web), sistemas de puntos de venta, móvil, CRM y muchos más.

* [Transformaciones en el tiempo del informe en vistas de datos](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md#customer-journey-analytics-data-views)

  Las vistas de datos de Customer Journey Analytics le permiten interpretar aún más los datos de una conexión. Puede modificar o quitar datos sin cambiar su implementación, utilizar subcadenas para manipular dimensiones, crear métricas a partir de cualquier valor o usar campos derivados. Todas estas transformaciones se realizan de manera no destructiva. 

* [Las transformaciones se aplican a datos nuevos e históricos](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)

  Se puede aplicar la manipulación de la vista de datos a datos nuevos e históricos de una manera no destructiva.

* [Campos derivados](/help/data-views/derived-fields/derived-fields.md)

  Los campos derivados permiten realizar transformaciones en el tiempo e informe de los datos. Los datos pueden combinarse, corregirse o crearse sobre la marcha y aplicarse de forma retroactiva a todos los informes.

* [Las vistas de datos reemplazan a los grupos de informes virtuales](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-virtual-report-suites)

  Las vistas de datos adoptan el concepto de grupos de informes virtuales tal como existen hoy en día y lo amplían para habilitar controles adicionales en los datos disponibles mediante conexiones. Estos cambios hacen que la configuración general, como los intervalos de huso horario y de tiempo de espera de sesión, sea configurable y retroactiva. 

* [Métricas y dimensiones ilimitadas de clientes](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-evars-and-props)

  Los valores pueden ser numéricos, texto, objetos, listas o combinaciones de todos ellos. Las dimensiones pueden estar anidadas o ser jerárquicas. 

## Comprender el proceso de actualización

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
La información de esta página cubre el paso 1 del proceso de actualización, como se indica en la tabla siguiente. Complete todos los pasos de esta tabla para actualizar de Adobe Analytics a Customer Journey Analytics.

| Actualizar tarea | Detalles |
|---------|----------|
| <span class="preview">**Paso 1: Introducción a la actualización**</span> | <span class="preview">Conozca las ventajas de actualizar a Customer Journey Analytics y el proceso de actualización básico.</span> |
| **Paso 2: [Elija la ruta de actualización](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Hay varios métodos disponibles para actualizar a Customer Journey Analytics. Elija el método que mejor se adapte a su organización, en función del entorno de Adobe Analytics actual de su organización y los objetivos a largo plazo. |
| **Paso 3: [Enviar datos a Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | El proceso de envío de datos a Adobe Experience Platform difiere según la ruta de actualización elegida en el paso 2. |
| **Paso 4: [Conservar los datos históricos](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | La mayoría de las organizaciones necesitan conservar sus datos históricos de Adobe Analytics durante un periodo de tiempo determinado. Hay varias opciones disponibles para hacerlo. |
| **Paso 5: [Realizar tareas de implementación adicionales](/help/getting-started/cja-getting-started.md)** | En este punto del proceso de actualización, debe realizar varias tareas antes de que el entorno de Customer Journey Analytics esté listo para su uso.<p>Estas tareas adicionales se aplican a las actualizaciones desde Adobe Analytics, así como a las nuevas implementaciones de Customer Journey Analytics.</p><p>Esta tareas son:</p><ul><li>Incorporación de datos a Experience Platform</li><li>Creación de conexiones entre conjuntos de datos de Platform y Customer Journey Analytics</li><li>Creación de vistas de datos </li><li>Transferencia del uso de API de informes</li><li>Contabilidad de fuentes de datos y Data Warehouse</li><li>Migración de proyectos y componentes</li><li>Planificación de la incorporación del usuario</li></ul> <p>Para obtener más información, consulte [Introducción a Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

## Primero, elija la ruta de actualización

Hay varios métodos disponibles para actualizar a Customer Journey Analytics. [Elija el método que mejor se adapte a su organización](/help/getting-started/cja-upgrade/cja-upgrade-path.md).

La ruta de actualización que elija dependerá del entorno de Adobe Analytics actual de su organización y de los objetivos a largo plazo.
