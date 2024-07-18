---
title: Etiquetas y políticas
description: Descubra cómo las etiquetas y políticas de datos definidas en Adobe Experience Platform afectan a las vistas de datos y a la creación de informes en Customer Journey Analytics.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
source-git-commit: 6526ca2b7caaf64acf29d97c859c3e813d003d2d
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 100%

---

# Etiquetas y políticas

Al crear un conjunto de datos en Experience Platform, puede crear [etiquetas del uso de datos](https://experienceleague.adobe.com/es/docs/experience-platform/data-governance/labels/reference) para algunos o todos los elementos del conjunto de datos. Puede ver estas etiquetas y políticas en Customer Journey Analytics.

Las siguientes etiquetas son de especial interés para Customer Journey Analytics:

* La etiqueta`C8` **[!UICONTROL Sin medición]**. Esta etiqueta significa que los datos no se pueden usar para los análisis en los sitios web o las aplicaciones de su organización.

* La etiqueta`C12`: **[!UICONTROL Sin exportación de datos general]**. Los campos de esquema etiquetados de esta manera no se pueden exportar ni descargar de Customer Journey Analytics (a través de la creación de informes, exportación, API, etc.)

>[!NOTE]
>
>Las etiquetas del uso de datos no se propagan automáticamente a los conjuntos de datos vinculados. Sin embargo, se pueden añadir manualmente.

El etiquetado, en sí, no significa que se apliquen estas etiquetas de uso de datos. Para eso sirven las políticas. Puede crear políticas mediante la [IU de Experience Platform](https://experienceleague.adobe.com/es/docs/experience-platform/data-governance/policies/user-guide) o la [API del servicio de políticas](https://experienceleague.adobe.com/es/docs/experience-platform/data-governance/api/overview) de Experience Platform.

Hay dos políticas definidas por Adobe disponibles en Experience Platform que pueden aparecer en Customer Journey Analytics y afectar a la creación de informes y a la exportación de datos:

* Directiva **[!UICONTROL Restringir el análisis de uso y la medición basada en el usuario]**, utilizando la etiqueta`C8` y directiva
* **[!UICONTROL Restringir la exportación de datos]** utilizando la etiqueta`C12`.

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

Si una o más políticas están activadas con las etiquetas C8 o C12, los componentes del esquema que tengan aplicadas determinadas etiquetas de datos no se pueden añadir a las vistas de datos.

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


