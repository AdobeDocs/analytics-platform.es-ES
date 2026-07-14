---
title: Etiquetas Y Políticas
description: Descubra cómo las etiquetas y políticas de datos definidas en Adobe Experience Platform afectan a las vistas de datos y a la creación de informes en Customer Journey Analytics.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
hold: true
autotag-review: '2026-05-19T08:59:31.818Z'
TQID: 'https://experienceleague.adobe.com/SoIHLRSx90B4j8EkHWBVt3rVtt-968TN8ocWU2zuYN4'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4id: eb00932f-4d46-46bc-b1d8-10de7588db8did: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2: id: e1471301-a189-438e-8d48-264a8db508a6
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 1254207526535e44c848dfeed0052339fbd8d65d
workflow-type: tm+mt
source-wordcount: 745
ht-degree: 66%

---

# Etiquetas, políticas y acciones de marketing

Al crear un conjunto de datos en Experience Platform, puede crear [etiquetas del uso de datos](https://experienceleague.adobe.com/es/docs/experience-platform/data-governance/labels/reference) para algunos o todos los elementos del conjunto de datos. Puede ver estas etiquetas y políticas en Customer Journey Analytics.

Las siguientes etiquetas y acciones de marketing son de especial interés para Customer Journey Analytics:


| Etiqueta | Acción de marketing | Definición |
|---------|----------|---------|
| `C2` | [!UICONTROL Exportar a terceros] | La etiqueta y la acción de marketing asociada significan que los datos no se pueden exportar a terceros si la directiva DULE correspondiente está habilitada. |
| `C3` | [!UICONTROL Combinar con datos directamente identificables] | La etiqueta y la acción de marketing asociada significan que los datos no se pueden combinar ni utilizar de otro modo con información directamente identificable, si la directiva DULE correspondiente está habilitada. |
| `C8` | [!UICONTROL Analytics] | La etiqueta y la acción de marketing asociada significan que los datos no se pueden utilizar para análisis en los sitios web o las aplicaciones de la organización, si la directiva DULE correspondiente está habilitada. |
| `C9` | [!UICONTROL Ciencia de datos] | La etiqueta y la acción de marketing asociada significan que los datos no se pueden utilizar en flujos de trabajo de ciencia de datos si la directiva DULE correspondiente está habilitada. |
| `C12` | [!UICONTROL Exportación de datos] | La etiqueta y la acción de marketing asociada significan que los campos de esquema etiquetados de esta manera no se pueden exportar ni descargar desde Customer Journey Analytics (a través de creación de informes, exportación, API, etc.), si la directiva DULE correspondiente está habilitada. |

>[!NOTE]
>
>Las etiquetas del uso de datos no se propagan automáticamente a los conjuntos de datos vinculados. Sin embargo, se pueden añadir manualmente.

El etiquetado, en sí, no significa que se apliquen estas etiquetas de uso de datos. Para eso sirven las políticas. Puede crear políticas mediante la [IU de Experience Platform](https://experienceleague.adobe.com/es/docs/experience-platform/data-governance/policies/user-guide) o la [API del servicio de políticas](https://experienceleague.adobe.com/es/docs/experience-platform/data-governance/api/overview) de Experience Platform.

Hay cinco directivas definidas por Adobe disponibles en Experience Platform que pueden aparecer en Customer Journey Analytics y afectar a la exportación de datos y sistemas de informes:


| Política | Etiqueta |
|---------|----------|
| [!UICONTROL Restringir la exportación de datos de terceros] | `C2` |
| [!UICONTROL Restringir la combinación de datos directamente identificables] | `C3` |
| [!UICONTROL Restringir el análisis de uso y la medición basada en usuarios] | `C8` |
| [!UICONTROL Restringir la ciencia de datos] | `C9` |
| [!UICONTROL Restringir la exportación de datos] | `C12` |


## Visualización de etiquetas de datos en las vistas de datos de Customer Journey Analytics

Las etiquetas de datos que usted u otras personas han creado en Experience Platform se muestran en tres ubicaciones de la interfaz de usuario de vistas de datos:

| Ubicación | Descripción |
| --- | --- |
| Botón Información de un campo de esquema | Al hacer clic en este botón, se indica qué [!UICONTROL Etiquetas de uso de datos] se aplican en ese monento a un campo:<p>![](assets/data-label-left.png) |
| Carril derecho bajo [Configuración de componentes](/help/data-views/component-settings/overview.md) | Cualquier [!UICONTROL Etiqueta de uso de datos] se enumera aquí:<p>![](assets/data-label-right.png) |
| Adición de etiquetas de datos como una columna | Puede añadir [!UICONTROL Etiquetas de uso de datos] como una columna a los [!UICONTROL Componentes incluidos] en vistas de datos. Seleccione simplemente el icono del selector de columnas y seleccione **[!UICONTROL Etiquetas de uso de datos]**:<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## Filtro en las etiquetas de Gobernanza de datos en las vistas de datos

En el editor de vistas de datos, seleccione el icono de [!UICONTROL filtro] en el carril de la izquierda y filtre los componentes de vistas de datos por **[!UICONTROL Gobernanza de datos]** y el tipo de **[!UICONTROL Etiqueta]**:

![](assets/filter-labels.png)

Haga clic en **[!UICONTROL Aplicar]** para ver qué componentes tienen etiquetas adjuntas.

## Filtro en políticas de Gobernanza de datos en vistas de datos

Puede comprobar para ver si una directiva (por ejemplo, una directiva que ha creado, denominada **[!UICONTROL Aplicar Analytics]**) está activada. Y si esa directiva bloquea el uso de determinados elementos de la vista de datos de Customer Journey Analytics para el análisis o la exportación de datos.

De nuevo, seleccione el icono de [!UICONTROL filtro] en el carril izquierdo y, debajo de **[!UICONTROL Gobernanza de datos]**, seleccione **[!UICONTROL Políticas]**:

![Filtro de los componentes incluidos por la lista que muestra Restringir el análisis de uso y la medición basada en el usuario que se ha seleccionado](assets/filter-policies.png)

Haga clic en **[!UICONTROL Aplicar]** para ver qué políticas están habilitadas.

## Cómo afectan las políticas habilitadas a las vistas de datos

Si una o más políticas están activadas con etiquetas C1, C2, C3, C8, C9 o C12, esos componentes de esquema que tienen determinadas etiquetas de datos aplicadas no se pueden añadir a las vistas de datos.

Estos componentes aparecen atenuados en la lista del carril izquierdo [!UICONTROL Campos del esquema]:

![Los componentes atenuados y el mensaje de políticas indican que se han aplicado políticas a este campo que restringen el uso de los datos](assets/component-greyed.png)

Tampoco puede guardar una vista de datos que tenga campos bloqueados.

Tenga cuidado al intentar aplicar etiquetas de acceso y de gobernanza de datos (mediante políticas) en campos o grupos de campos en Experience Platform para los que ya tenga componentes definidos en la vista de datos. Es posible que aparezca este cuadro de diálogo.

![Infracción](assets/violation.png)

Primero debe resolver la infracción (por ejemplo, quitar los componentes de la vista de datos).


>[!MORELIKETHIS]
>
>[Descarga de datos confidenciales](/help/analysis-workspace/export/download-send.md)

>[!MORELIKETHIS]
>
>[¿Qué son las etiquetas restringidas en Report Builder?](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-reportbuilder/restricted-labels)


