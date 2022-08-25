---
title: Etiquetas y políticas
description: Descubra cómo las etiquetas y políticas de datos definidas en AEP afectan a las vistas de datos y la creación de informes en CJA.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
source-git-commit: 7962114aaab42a283f1cb35a312b0a707038c31a
workflow-type: ht
source-wordcount: '468'
ht-degree: 100%

---

# Etiquetas y políticas

Al crear un conjunto de datos en Experience Platform, puede crear [etiquetas de uso de datos](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=es) para algunos o todos los elementos del conjunto de datos. Hasta ahora, estas etiquetas no estaban expuestas en CJA. Con esta versión, puede ver estas etiquetas y políticas en CJA.

Estas etiquetas son de especial interés para CJA:

* La etiqueta`C8` **[!UICONTROL Sin medición]**. Esta etiqueta significa que los datos no se pueden usar para análisis en los sitios web o las aplicaciones de su organización.

* La etiqueta`C12` **[!UICONTROL Sin exportación de datos general]**. Los campos de esquema etiquetados de esta manera no se pueden exportar ni descargar desde CJA (a través de creación de informes, exportación, API, etc.)

El etiquetado, en sí, no significa que se apliquen estas etiquetas de uso de datos. Para eso sirven las políticas. Las políticas se crean mediante la [API del servicio de políticas](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=es) en Experience Platform.

En CJA aparecen dos políticas definidas por Adobe que afectan a la creación de informes y a la descarga/uso compartido:

* **[!UICONTROL Aplicación de la política de Analytics]**
* **[!UICONTROL Aplicación de la política de descarga]**

## Visualización de etiquetas de datos en vistas de datos de CJA

Las etiquetas de datos que se crearon en Experience Platform se muestran en tres ubicaciones de la interfaz de usuario de vistas de datos:

| Ubicación | Descripción |
| --- | --- |
| Botón Información de un campo de esquema | Al hacer clic en este botón, se indica qué [!UICONTROL Etiquetas de uso de datos] se aplican en ese monento a un campo:<p>![](assets/data-label-left.png) |
| Carril derecho bajo [Configuración de componentes](/help/data-views/component-settings/overview.md) | Cualquier [!UICONTROL Etiqueta de uso de datos] se enumera aquí:<p>![](assets/data-label-right.png) |
| Adición de etiquetas de datos como una columna | Puede añadir [!UICONTROL Etiquetas de uso de datos] como una columna a los [!UICONTROL Componentes incluidos] en vistas de datos. Haga clic en el icono del selector de columnas y seleccione **[!UICONTROL Etiquetas de uso de datos]**:<p>![](assets/data-label-column.png) |

{style=&quot;table-layout:auto&quot;}

## Filtro en las etiquetas de Gobernanza de datos en las vistas de datos

En el editor de vistas de datos, haga clic en el icono Filtro del carril izquierdo y filtre los componentes de vistas de datos por **[!UICONTROL Gobernanza de datos]** y tipo de **[!UICONTROL Etiqueta]**:

![](assets/filter-labels.png)

Haga clic en **[!UICONTROL Aplicar]** para ver qué componentes tienen etiquetas adjuntas.

## Filtro en políticas de Gobernanza de datos en vistas de datos

Puede comprobar si hay una política activada que bloquee el uso de ciertos elementos de vista de datos de CJA para análisis o exportación con fines específicos.

De nuevo, haga clic en el icono Filtro en el carril izquierdo y, debajo de **[!UICONTROL Gobernanza de datos]**, en **[!UICONTROL Políticas]**:

![](assets/filter-policies.png)

Haga clic en **[!UICONTROL Aplicar]** para ver qué políticas están habilitadas.

## Cómo afectan las políticas habilitadas a las vistas de datos

Si las políticas **[!UICONTROL Aplicar Analytics]** o **[!UICONTROL Aplicar descarga]** están activadas, los componentes de esquema que tienen determinadas etiquetas de datos (como C8 o C12) asociadas a ellas no se pueden añadir a las vistas de datos.

Estos componentes aparecen atenuados en la lista del carril izquierdo [!UICONTROL Campos de esquema]:

![](assets/component-greyed.png)

Tampoco puede guardar una vista de datos que tenga campos bloqueados.

>[!MORELIKETHIS]
>[Descarga de datos confidenciales](/help/analysis-workspace/curate-share/download-send.md)

>[!MORELIKETHIS]
>[¿Qué son las etiquetas restringidas en Report Builder?](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/restricted-labels.html?lang=es)


