---
title: Combinación de grupos de informes con diferentes esquemas
description: Aprenda a utilizar la preparación de datos para combinar grupos de informes con distintos esquemas
exl-id: 2656cc21-3980-4654-bffb-b10908cb21f5
source-git-commit: 69356510596d047d80af63338fccca71e8af53cd
workflow-type: tm+mt
source-wordcount: '1335'
ht-degree: 100%

---

# Combinación de grupos de informes con diferentes esquemas

El [conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es) incorpora datos de grupos de informes de Adobe Analytics en Adobe Experience Platform (AEP) para su uso en aplicaciones AEP, como Real-time Customer Data Platform y Customer Journey Analytics (CJA). Cada grupo de informes introducido en AEP está configurado como flujo de datos de conexión de origen individual, y cada flujo de datos aterriza como un conjunto de datos dentro del lago de datos de AEP. El conector de origen de Analytics crea un conjunto de datos por grupo de informes.

Los clientes de CJA utilizan [conexiones](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=es) para integrar conjuntos de datos del lago de datos de AEP en Analysis Workspace de CJA. Sin embargo, al combinar grupos de informes dentro de una conexión, las diferencias de esquema entre grupos de informes deben resolverse con la funcionalidad [Preparación de datos](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=es). El propósito es garantizar que las variables de Adobe Analytics, como las props y las eVars, tengan un significado coherente en CJA.

## Las diferencias de esquema entre los grupos de informes son problemáticas

Supongamos que su empresa desea importar datos de dos grupos de informes diferentes a AEP para usarlos en CJA, y que los esquemas de los dos grupos de informes tienen diferencias:

| Grupo de informes A | Grupo de informes B |
| --- | --- |
| eVar1 = Término de búsqueda | eVar1 = Unidad de negocio |
| eVar2 = Categoría del cliente | eVar2 = Término de búsqueda |

Para simplificar, supongamos que son las únicas eVars definidas para ambos grupos de informes.

Además, supongamos que realiza las siguientes acciones:

- Crear una conexión de origen de Analytics (sin usar la preparación de datos) que ingrese **Grupo de informes A** en el lago de datos de AEP como **Conjunto de datos A**.
- Crear una conexión de origen de Analytics (sin usar la preparación de datos) que ingrese **Grupo de informes B** en el lago de datos de AEP como **Conjunto de datos B**.
- Crear una [conexión CJA](/help/connections/create-connection.md) llamada **Todos los grupos de informes** que combina los conjuntos de datos A y B.
- Crear una [vista de datos de CJA](/help/data-views/create-dataview.md) llamada **Vista global** que se basa en la conexión Todos los grupos de informes.

Sin el uso de la preparación de datos para resolver las diferencias de esquema entre los conjuntos de datos A y B, las eVars de la vista de datos global contendrán una mezcla de valores:

| Vista de datos de Global View en CJA |
| --- |
| eVar1 => una combinación de términos de búsqueda y unidades de negocio |
| eVar2 => una combinación de categorías de clientes y términos de búsqueda |

Esta situación resulta en informes sin sentido para eVar1 y eVar2:

- Los campos de eVar contienen una mezcla de valores con diferentes significados semánticos.
- Los términos de búsqueda se distribuyen entre eVar1 y eVar2.
- No es posible utilizar diferentes modelos de atribución para cada uno de los términos de búsqueda, unidades de negocio y categorías de clientes.

## Use la preparación de datos de AEP para resolver diferencias de esquema entre grupos de informes

La funcionalidad de preparación de datos de Experience Platform está integrada con el conector de origen de Analytics y se puede utilizar para resolver las diferencias de esquema descritas en el escenario anterior. Esto da como resultado eVars con significados coherentes en la vista de datos de CJA. (Las convenciones de nomenclatura que se utilizan a continuación se pueden personalizar para adaptarlas a sus necesidades).

1. Antes de crear los flujos de datos de conexión de origen para los grupos de informes A y B, [cree un nuevo esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=es) en AEP (lo llamaremos **Esquema unificado** en nuestro ejemplo). Añada lo siguiente al esquema:

   | «Esquema unificado» |
   | --- |
   | clase **XDM ExperienceEvent** |
   | grupo de campos **Plantilla de Adobe Analytics ExperienceEvent** |

1. Añada otro grupo de campos al esquema o [cree un grupo de campos personalizado](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=es#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail) y agréguelo al esquema. Crearemos un nuevo grupo de campos y lo llamaremos **Campos unificados**. A continuación, agregaremos los campos siguientes al nuevo grupo de campos:

   | Grupo de campos personalizados «Campos unificados»  |
   | --- |
   | Término de búsqueda |
   | Unidad empresarial |
   | Categoría del cliente |

1. Cree el flujo de datos de la conexión de origen para **Grupo de informes A** seleccionando **Esquema unificado** para su uso en el flujo de datos. Agregue asignaciones personalizadas al flujo de datos de la siguiente manera:

   | Campo de origen del grupo de informes A | Campo de destino del grupo de campos Campos unificados |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Search_term |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

   >[!NOTE]
   >
   >La ruta XDM para los campos de destino dependerá de la estructura del grupo de campos personalizados.

1. Cree el flujo de datos de la conexión de origen para **Grupo de informes B** volviendo a seleccionar **Esquema unificado** para su uso en el flujo de datos. El flujo de trabajo mostrará que dos campos tienen un conflicto de nombres de descriptor. Esto se debe a que los descriptores de eVar1 y eVar2 son diferentes en Grupo de informes B y Grupo de informes A. Pero ya lo sabemos, así que podemos ignorar con seguridad el conflicto y usar asignaciones personalizadas de la siguiente manera:

   | Campo de origen del grupo de informes B | Campo de destino del grupo de campos Campos unificados |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Business_unit |
   | _experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Search_term |

1. Ahora cree una conexión **Todos los grupos de informes** para CJA que combina los conjuntos de datos A y B.

1. Cree una vista de datos **Vista global** en CJA. Ignore los campos de eVar originales e incluya solo los campos del grupo de campos Campos unificados.

   Vista de datos **Vista global** en CJA:

   | Campo de origen | ¿Incluir en la vista de datos? |
   | --- | --- | 
   | \_experience.analytics.customDimensions.eVars.eVar1 | No |
   | \_experience.analytics.customDimensions.eVars.eVar2 | No |
   | _\&lt;path>_.Search_term | Sí |
   | _\&lt;path>_.Customer_category  | Sí |
   | _\&lt;path>_.Business_unit | Sí |

Ahora ha asignado eVar1 y eVar2 de los grupos de informes de origen a tres campos nuevos. Tenga en cuenta que otra ventaja de usar asignaciones de preparación de datos es que los campos de destino ahora se basan en nombres semánticamente significativos (término de búsqueda, unidad de negocio, categoría de cliente) en lugar de los nombres de eVar menos significativos (eVar1, eVar2).

>[!NOTE]
>
>El grupo de campos personalizados Campos unificados y las asignaciones de campos asociadas se pueden agregar a flujos y conjuntos de datos del conector de origen de Analytics existentes en cualquier momento. Sin embargo, esto solo afecta a los datos a partir de ahora.

## Algo más que grupos de informes

Las capacidades de la preparación de datos para combinar conjuntos de datos con distintos esquemas van más allá de los grupos de informes de Analytics. Supongamos que tiene dos conjuntos de datos que contienen los siguientes datos:

| Conjunto de datos A = Grupo de informes de Analytics mediante el conector de origen de Analytics |
| --- |
| `eVar1` => Categoría del cliente |

| Conjunto de datos B = Datos del centro de llamadas |
| --- |
| Some_field => Categoría del cliente |

Con la preparación de datos, puede combinar la categoría del cliente en eVar 1 en los datos de Analytics con la categoría del cliente en el campo Some_field en los datos del centro de llamadas. Esta es una forma de hacerlo. De nuevo, la convención de nombres se puede modificar para adaptarla a sus necesidades.

1. Cree un esquema en AEP. Añada lo siguiente al esquema:

   | «Esquema extendido» |
   | --- | 
   | clase **Evento de experiencia XDM** |
   | grupo de campos **Plantilla de eventos de la experiencia de Adobe Analytics** |

1. Cree un nuevo grupo de campos y agréguelo al esquema. Agregue campos al grupo de campos:

   | Grupo de campos personalizados «Información del cliente»  |
   | --- |
   | Customer_category |

1. Cree el flujo de datos para **Conjunto de datos A** seleccionando **Esquema extendido** como esquema. Agregue asignaciones personalizadas al flujo de datos de la siguiente manera:

   | Campo de origen Conjunto de datos A | Campo de destino del grupo de campos Información del cliente |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

1. Cree el flujo de datos para **Conjunto de datos B** volviendo a seleccionar **Esquema extendido** como esquema. Agregue asignaciones personalizadas al flujo de datos de la siguiente manera:

   | Campo de origen Conjunto de datos B | Campo de destino del grupo de campos Información del cliente |
   | --- | --- |
   | _\&lt;path>_.Some_field | _\&lt;path>_.Customer_category |

1. Cree una conexión CJA que combine los conjuntos de datos A y B.

1. Cree una vista de datos en CJA utilizando la conexión CJA que acaba de crear. Ignore los campos de eVar originales e incluya solo los campos del grupo de campos Información del cliente.

   Vista de datos en CJA:

   | Campo de origen | ¿Incluir en la vista de datos? |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | No |
   | \_experience.analytics.customDimensions.eVars.eVar2 | No |
   | _\&lt;path>_.Customer_category | Sí |

## Preparación de datos e ID de componente

Como se ha descrito anteriormente, la preparación de datos le permite asignar diferentes campos entre varios conjuntos de informes de Adobe Analytics. Esto resulta útil en CJA cuando desea combinar datos de varios conjuntos de datos en una única conexión CJA. Sin embargo, si tiene intención de mantener los grupos de informes en conexiones CJA independientes pero desea utilizar un conjunto de informes en esas conexiones y vistas de datos, cambiar el ID de componente subyacente en CJA permite hacer que los informes sean compatibles aunque los esquemas sean diferentes. Consulte [Configuración de componentes](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html?lang=es) para obtener más información.

El cambio del ID del componente es una función exclusiva de CJA y no afecta a los datos del conector de origen de Analytics que se envían al perfil del cliente en tiempo real y a RTCDP.
