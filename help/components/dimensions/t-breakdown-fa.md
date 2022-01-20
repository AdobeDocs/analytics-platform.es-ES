---
description: Desglose de dimensiones y elementos de dimensión en Analysis Workspace.
keywords: Analysis Workspace
title: Desglose de dimensiones
exl-id: 6b433db3-02c1-4deb-916e-b01c0b79889e
source-git-commit: 0176f10ffed85786b0bfa77204ca7a19d9c39ba7
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 53%

---

# Desglose de dimensiones en Workspace

>[!NOTE]
>
>Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=es). [Más información...](/help/getting-started/cja-aa.md)

Desglose de dimensiones y elementos de dimensión en Analysis Workspace.

Desglose los datos de manera ilimitada según sus necesidades específicas; genere consultas utilizando métricas, dimensiones, filtros, líneas de tiempo y otros valores de desglose de análisis relevantes.

1. [Cree un proyecto](/help/analysis-workspace/home.md) con una tabla de datos.
1. En la tabla de datos, haga clic con el botón secundario en un elemento de línea y seleccione **[!UICONTROL Desglosar]** > *`<item>`*.

   ![Resultado](assets/fa_data_table_actions.png)

   Puede desglosar métricas por elementos de dimensión o filtros de audiencia entre periodos de tiempo seleccionados. También puede continuar desglosando hasta un nivel más granular.

   >[!NOTE]
   >
   >El número de desgloses de la tabla está limitado a 200 desgloses. Este límite aumentará para la exportación de desgloses.

**Vídeo: Dimension en Analysis Workspace**

>[!VIDEO](https://video.tv.adobe.com/v/23971)

**Vídeo: Desgloses de Dimension**

>[!VIDEO](https://video.tv.adobe.com/v/23969)

## Aplicar modelos de atribución a desgloses

Cualquier desglose dentro de una tabla también puede tener aplicado cualquier modelo de atribución. Este modelo de atribución puede ser el mismo o diferente de la columna principal. Por ejemplo, puede analizar Pedidos lineales en su dimensión de Canales de marketing pero aplicar Pedidos en forma de U a los códigos de seguimiento específicos dentro de un Canal. Para editar el modelo de atribución aplicado a un desglose, simplemente sitúe el ratón encima del modelo de desglose y haga clic en **[!UICONTROL Editar]**:

![Configuración del desglose](assets/breakdown_settings.png)

Este es el comportamiento esperado al aplicar modelos de atribución a desgloses o editarlos:

* Si aplica una atribución cuando no existen otras atribuciones, la atribución se aplica a todo el árbol de columnas.

* Si agrega un desglose después de aplicar una atribución, utilizará el valor predeterminado para el desglose dado que se añadió (si esa dimensión tiene un valor predeterminado). De lo contrario, se utiliza el desglose de la columna principal. Algunas dimensiones tienen una asignación predeterminada. Por ejemplo, las dimensiones temporales y el referente utilizan el mismo contacto. La dimensión Producto utiliza Último toque. Otras dimensiones no tienen un valor predeterminado y utilizarán la asignación de columna principal.

* Si ya hay atribuciones en el árbol de columnas, cambiar la atribución solo afecta al que esté editando.

## Vídeos

Adición de dimensiones y métricas al proyecto en Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/30606)

Trabajo con dimensiones en una tabla de forma libre:

>[!VIDEO](https://video.tv.adobe.com/v/40179)

Desgloses del Dimension por posición:

>[!VIDEO](https://video.tv.adobe.com/v/24033)
