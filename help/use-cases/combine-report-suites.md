---
title: Combinación de grupos de informes con diferentes esquemas
description: Aprenda a utilizar la preparación de datos para combinar grupos de informes con distintos esquemas
source-git-commit: 02483345326180a72a71e3fc7c60ba64a5f8a9d6
workflow-type: tm+mt
source-wordcount: '1308'
ht-degree: 3%

---


# Combinación de grupos de informes con diferentes esquemas

La variable [Conector de origen de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=es) incorpora datos de grupos de informes de Adobe Analytics en Adobe Experience Platform (AEP) para su uso en aplicaciones AEP, como Real-time Customer Data Platform y Customer Journey Analytics (CJA). Cada grupo de informes introducido en AEP está configurado como flujo de datos de conexión de origen individual, y cada flujo de datos se aterriza como un conjunto de datos dentro del lago de datos de AEP. El conector de origen de Analytics crea un conjunto de datos por grupo de informes.

Los clientes de CJA utilizan [conexiones](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=es) para integrar conjuntos de datos de AEP data lake en Analysis Workspace de CJA. Sin embargo, al combinar grupos de informes dentro de una conexión, las diferencias de esquema entre grupos de informes deben resolverse con el [Preparación de datos](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=es) funcionalidad. El propósito es garantizar que las variables de Adobe Analytics, como las props y las eVars, tengan un significado coherente en CJA.

## Las diferencias de esquema entre los grupos de informes son problemáticas

Supongamos que su empresa desea importar datos de dos grupos de informes diferentes a AEP para usarlos en CJA, y supongamos que los esquemas de los dos grupos de informes tienen diferencias:

| Grupo de informes A | Grupo de informes B |
| --- | --- |
| eVar1 = Término de búsqueda | eVar1 = Unidad de negocio |
| eVar2 = Categoría del cliente | eVar2 = Término de búsqueda |

Para simplificar, supongamos que son las únicas eVars definidas para ambos grupos de informes.

Además, supongamos que realiza las siguientes acciones:

- Crear una conexión de origen de Analytics (sin usar la preparación de datos) que ingrese **Grupo de informes A** en el lago de datos de AEP como **Conjunto De Datos A**.
- Crear una conexión de origen de Analytics (sin usar la preparación de datos) que ingrese **Grupo de informes B** en el lago de datos de AEP como **Conjunto de datos B**.
- Cree un [Conexión CJA](/help/connections/create-connection.md) llamado **Todos los grupos de informes** que combina el conjunto de datos A y el conjunto de datos B.
- Cree un [Vista de datos de CJA](/help/data-views/create-dataview.md) llamado **Vista global** que se basa en la conexión Todos los grupos de informes .

Sin el uso de la preparación de datos para resolver las diferencias de esquema entre el conjunto de datos A y el conjunto de datos B, las eVars de la vista de datos global contendrán una mezcla de valores:

| Vista de datos de Global View en CJA |
| --- |
| eVar1 => una combinación de términos de búsqueda y unidades de negocio |
| eVar2 => una combinación de categorías de clientes y términos de búsqueda |

Esta situación resulta en informes sin sentido para el eVar 1 y el eVar 2:

- Los campos de eVar contienen una mezcla de valores con diferentes significados semánticos.
- Los términos de búsqueda se distribuyen entre eVar1 y eVar2.
- No es posible utilizar diferentes modelos de atribución para cada uno de los términos de búsqueda, unidades de negocio y categorías de clientes.

## Usar la preparación de datos de AEP para resolver diferencias de esquema entre grupos de informes

La funcionalidad de preparación de datos del Experience Platform está integrada con el conector de origen de Analytics y se puede utilizar para resolver las diferencias de esquema descritas en el escenario anterior. Esto da como resultado eVars con significados coherentes en la vista de datos de CJA. (Las convenciones de nomenclatura que se utilizan a continuación se pueden personalizar para adaptarlas a sus necesidades).

1. Antes de crear los flujos de datos de conexión de origen para el grupo de informes A y el grupo de informes B, [crear un grupo de campos personalizado](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=en#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail.) en AEP (lo llamaremos **Campos unificados** en nuestro ejemplo) que contiene los siguientes campos:

   | Grupo de campos personalizados &quot;Campos unificados&quot;  |
   | --- |
   | Término de búsqueda |
   | Unidad empresarial |
   | Categoría del cliente |

1. [Crear un nuevo esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=en) en AEP (lo llamaremos **Esquema unificado** en nuestro ejemplo). Agregue los siguientes grupos de campos al esquema :

   | Grupos de campos para &quot;Esquema unificado&quot; |
   | --- |
   | Evento de experiencia XDM |
   | Plantilla de eventos de la experiencia de Adobe Analytics |
   | Campos unificados |

   Al crear el flujo de datos de la conexión de origen para **Grupo de informes A**, seleccione **Esquema unificado** para su uso en el flujo de datos.

1. Agregue asignaciones personalizadas de la siguiente manera:

   | Campo de origen del grupo de informes A | Campo de destino del grupo de campos Campos unificados |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Search_term |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

   >[!NOTE]
   >
   >La ruta XDM para los campos de destino dependerá de cómo configure el grupo de campos personalizados.

1. Al crear el flujo de datos de la conexión de origen para **Grupo de informes B**, vuelva a seleccionar **Esquema unificado** para su uso en el flujo de datos.

   El flujo de trabajo muestra que dos campos tienen un conflicto de nombres de descriptor. Esto se debe a que los descriptores de eVar 1 y eVar 2 son diferentes en el grupo de informes B que en el grupo de informes A. Pero ya lo sabemos, así que podemos ignorar con seguridad el conflicto y usar asignaciones personalizadas de la siguiente manera:

   | Campo de origen del grupo de informes B | Campo de destino del grupo de campos Campos unificados |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Business_unit |
   | _experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Search_term |

1. Ahora cree un **Todos los grupos de informes** conexión para CJA, que combina el conjunto de datos A y el conjunto de datos B.

1. Cree un **Vista global** vista de datos en CJA.

   Ignore los campos de eVar originales e incluya solo los campos del grupo de campos Campos unificados .

   Vista de datos de Global View en CJA:

   | Campo de origen | Incluir en la vista de datos? |
   | --- | --- | 
   | \_experience.analytics.customDimensions.eVars.eVar1 | No |
   | \_experience.analytics.customDimensions.eVars.eVar2 | No |
   | _\&lt;path>_.Search_term | Sí |
   | _\&lt;path>_.Customer_category  | Sí |
   | _\&lt;path>_.Business_unit | Sí |

   Ahora ha asignado eVar1 y eVar2 de los grupos de informes de origen a tres campos nuevos. Tenga en cuenta que otra ventaja de usar asignaciones de preparación de datos es que los campos de destino ahora se basan en nombres semánticamente significativos (término de búsqueda, unidad de negocio, categoría de cliente) en lugar de los nombres de eVar menos significativos (eVar1, eVar2).

   >[!NOTE]
   >
   >El grupo de campos personalizados Campos unificados y las asignaciones de campos asociadas se pueden agregar a flujos de datos y conjuntos de datos del conector de origen de Analytics existentes en cualquier momento. Sin embargo, esto solo afecta a los datos a partir de ahora.

## Más que solo grupos de informes

Las capacidades de la preparación de datos para combinar conjuntos de datos con distintos esquemas van más allá de los grupos de informes de Analytics. Supongamos que tiene dos conjuntos de datos que contienen los siguientes datos:

| Conjunto de datos A = Grupo de informes de Analytics mediante el conector de origen de Analytics |
| --- |
| `eVar1` => Categoría del cliente |

| Conjunto de datos B = Datos del centro de llamadas |
| --- |
| Some_field => Categoría del cliente |

Con la Preparación de datos, puede combinar la Categoría del cliente en eVar 1 en los datos de Analytics con la Categoría del cliente en el campo Algunos_datos en los datos del centro de llamadas. Aquí hay una manera de que puedas hacer eso. De nuevo, la convención de nombres se puede modificar para adaptarla a sus necesidades.

1. Crear un grupo de campos personalizados:

   | Grupo de campos personalizados &quot;Información del cliente&quot;  |
   | --- |
   | Customer_category |

1. Cree un esquema en AEP. Agregue los siguientes grupos de campos al esquema :

   | Grupos de campos para &quot;Esquema extendido&quot; |
   | --- | 
   | Evento de experiencia XDM |
   | Plantilla de eventos de la experiencia de Adobe Analytics |
   | Información del cliente |

1. Al crear el flujo de datos para **Conjunto De Datos A**, seleccione **Esquema extendido** como esquema.

1. Agregue asignaciones personalizadas de la siguiente manera:

   | Conjunto de datos Un campo de origen | Campo de destino del grupo de campos Información del cliente |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

1. Al crear el flujo de datos para **Conjunto de datos B**, vuelva a seleccionar **Esquema extendido** como esquema.

1. Agregue asignaciones personalizadas de la siguiente manera:

   | Campo de origen del conjunto de datos B | Campo de destino del grupo de campos Información del cliente |
   | --- | --- |
   | _\&lt;path>_.Some_field | _\&lt;path>_.Customer_category |

   Cree una conexión CJA que combine el conjunto de datos A y el conjunto de datos B. Cree una vista de datos en CJA, utilizando la conexión CJA que acaba de crear. Ignore los campos de eVar originales e incluya solo los campos del grupo de campos Información del cliente .

   Vista de datos en CJA:

   | Campo de origen | Incluir en la vista de datos? |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | No |
   | \_experience.analytics.customDimensions.eVars.eVar2 | No |
   | _\&lt;path>_.Customer_category | Sí |

## Preparación de datos e ID de componente

Como se ha descrito anteriormente, la preparación de datos le permite asignar distintos campos juntos en varios grupos de informes de Adobe Analytics. Esto resulta útil en CJA cuando desea combinar datos de varios conjuntos de datos en una única conexión CJA. Sin embargo, si tiene intención de mantener los grupos de informes en conexiones CJA independientes pero desea utilizar un conjunto de informes en esas conexiones y vistas de datos, cambiar el ID de componente subyacente en CJA permite hacer que los informes sean compatibles incluso si los esquemas son diferentes. Consulte [Configuración de componentes](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html?lang=en) para obtener más información.

Cambiar el ID de componente es una función solo de CJA y no afecta a los datos del conector de origen de Analytics que se envían a Perfil del cliente en tiempo real y RTCDP.

