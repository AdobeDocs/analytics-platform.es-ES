---
title: Guía de inicio rápido de Customer Journey Analytics
description: Comprenda los requisitos previos y el flujo de trabajo necesarios para implementar Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: 7b824c914187854e9779ebdc51c5f5d6e77f6b16
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 99%

---

# Guía de inicio rápido

Para implementar Customer Journey Analytics, debe seguir este flujo de trabajo. Algunas tareas iniciales se realizan en Adobe Experience Platform y otras, en Customer Journey Analytics.

## Requisitos previos

Customer Journey Analytics está disponible para los clientes que

* se proporcionan para [Adobe Experience Platform](https://www.adobe.com/es/experience-platform.html) y
* ha adquirido la SKU de Customer Journey Analytics.

## Flujo de trabajo

| Tarea | Detalles |
| --- | --- |
| **Paso 1: si está actualizando de Adobe Analytics a Customer Journey Analytics: elija una ruta de actualización y envíe datos a Adobe Experience Platform** | Hay varias rutas disponibles para la actualización de Adobe Analytics a Customer Journey Analytics. Cada posible ruta de actualización tiene sus propias ventajas y desventajas, y una ruta correcta para una organización podría no tener sentido para otra. <p>Para comenzar la actualización de Adobe Analytics a Customer Journey Analytics, realice una de las acciones siguientes:</p><ul><li>Siga la ruta de actualización recomendada por Adobe. Para obtener más información, consulte [Ruta recomendada al actualizar de Adobe Analytics a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</li><li>Obtenga información sobre todas las rutas de actualización disponibles y elija la que mejor se adapte a su organización. Para obtener más información, consulte [Introducción a la actualización a Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md).</li></ul> |
| **Paso 2: introducir otros datos en Adobe Experience Platform** | Este paso, realizado en Adobe Experience Platform, incluye varios subpasos:<ul><li>**Paso 2a: Preparar el esquema de datos**: Uso del modelo de datos de [Adobe Experience (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es) para estandarizar los datos de experiencia del cliente y [definir esquemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=es) para la administración de experiencias del cliente.</li><li>**Paso 2b: Crear un conjunto de datos basado en el esquema**: Los datos de Platform constan de conjuntos de datos, como conjuntos de datos de correo electrónico, de CRM, de POS, de Adobe Analytics, etc. Cada conjunto de datos consta de un esquema y lotes de datos. Puede [crear un conjunto de datos en Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=es).</li><li>**Paso 2c: Ingesta de datos en Experience Platform**: Aquí tiene varias opciones.</li></ul> |
| **Paso 3: crear conexiones entre conjuntos de datos de Platform y Customer Journey Analytics** | Una conexión le permite integrar conjuntos de datos de Adobe Experience Platform el Espacio de trabajo. Para informar sobre conjuntos de datos de Experience Platform, primero debe establecer una conexión entre conjuntos de datos en Experience Platform y Espacio de trabajo.<br>Consulte [Crear o editar una conexión](/help/connections/create-connection.md). |
| **Paso 4: crear vistas de datos** | Una vista de datos es una vista “filtrada” de los datos. Puede crear distintas vistas de datos para la misma conexión, con diferentes configuraciones para el tiempo de espera de visita, la atribución, etc. Puede crear varias vistas de datos para un único conjunto de datos.<br>Consulte [Crear una vista de datos](/help/data-views/create-dataview.md). |
| **Paso 5: puerto del uso de API de informes**</br> Solo se aplica al migrar desde Adobe Analytics | La API de informes de Customer Journey Analytics tiene el mismo formato, pero utiliza un punto final diferente. Transfiera el uso de la API de informes desde la API de informes de Adobe Analytics a la API de informes de Customer Journey Analytics. |
| **Paso 6: cuenta para fuentes de datos y casos de uso de Data Warehouse**</br> Solo se aplica al migrar desde Adobe Analytics | Decida cómo utilizará las opciones de exportación disponibles en Customer Journey Analytics para replicar mejor las funciones de fuentes de datos y Data Warehouse que utilizaba en Adobe Analytics. <!-- link to docs Rob is creating --> |
| **Paso 7: migrar proyectos y componentes**</br> Solo se aplica al migrar desde Adobe Analytics | El área Migración de componentes en Adobe Analytics le permite migrar proyectos y sus componentes asociados de Adobe Analytics a Customer Journey Analytics.<p>El proceso de migración incluye:</p><ul><li>Creación de nuevo de los proyectos de Adobe Analytics en Customer Journey Analytics.</li><li>Asignación de dimensiones y métricas de grupos de informes de Adobe Analytics a dimensiones y métricas en vistas de datos de Customer Journey Analytics.</li></ul><p>Antes de comenzar la migración, primero [prepárese para migrar los componentes y proyectos de Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=es).</p><p>Después de hacer todos los preparativos necesarios, puede [migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html?lang=es).</p> |
| **Paso 8: planificar la incorporación del usuario** | Al igual que en Adobe Analytics, Analysis Workspace es la principal herramienta de cara al usuario en Customer Journey Analytics. Sin embargo, existen algunas diferencias clave al utilizar Analysis Workspace en Customer Journey Analytics que los usuarios deben tener en cuenta.<p>Debe dar a los usuarios tiempo suficiente (de 3 a 6 meses) para familiarizarse con las diferencias clave de Analysis Workspace en Customer Journey Analytics.</p><p>Para obtener información sobre algunas de las diferencias clave entre Adobe Analytics y Customer Journey Analytics, consulte [Guía del usuario para usuarios de Adobe Analytics](/help/getting-started/aa-to-cja-user.md).</p> |
| **Paso 9: informar sobre los datos de canales cruzados en el Espacio de trabajo** | Después de crear conexiones y vistas de datos, analice los datos que ha introducido con la potencia y flexibilidad de Analysis Workspace.<br>Consulte [Realizar análisis básicos](/help/analysis-workspace/perform-basic-analysis.md) y [Realizar análisis avanzados](/help/analysis-workspace/perform-adv-analysis.md). |

## Guías de inicio rápido

La sección [Ingesta de datos](../data-ingestion/data-ingestion.md) proporciona guías de inicio rápido sobre el flujo de trabajo anterior. Estas guías de inicio rápido ilustran cómo ingerir datos de una variedad de fuentes (incluido Adobe Analytics) en Adobe Experience Platform y luego usar esos datos en Customer Journey Analytics.
