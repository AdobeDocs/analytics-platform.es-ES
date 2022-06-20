---
description: Desglose de dimensiones y elementos de dimensión en Analysis Workspace.
keywords: Analysis Workspace
title: Desglose de dimensiones
feature: Dimensions
exl-id: 6b433db3-02c1-4deb-916e-b01c0b79889e
solution: Customer Journey Analytics
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 98%

---

# Desglose de dimensiones en Workspace

Desglose de dimensiones y elementos de dimensión en Analysis Workspace.

Desglose los datos de forma ilimitada para sus necesidades específicas; genere consultas con métricas, dimensiones, filtros, líneas de tiempo y otros valores de desglose de análisis relevantes.

1. [Cree un proyecto](/help/analysis-workspace/home.md) con una tabla de datos.
1. En la tabla de datos, haga clic con el botón secundario en un elemento de línea y seleccione **[!UICONTROL Desglosar]** > *`<item>`*.

   ![Resultado](assets/fa_data_table_actions.png)

   Puede desglosar métricas por elementos de dimensión o filtros de audiencia entre periodos de tiempo seleccionados. También puede continuar desglosando hasta un nivel más granular.

   >[!NOTE]
   >
   >El número de desgloses de la tabla está limitado a 200 desgloses. Este límite aumenta para la exportación de desgloses.

**Vídeo: Dimensiones en Analysis Workspace**

>[!VIDEO](https://video.tv.adobe.com/v/23971)

**Vídeo: Desgloses de dimensiones**

>[!VIDEO](https://video.tv.adobe.com/v/23969)

## Aplicar modelos de atribución a desgloses

Cualquier desglose dentro de una tabla también puede tener aplicado cualquier modelo de atribución. Este modelo de atribución puede ser el mismo o diferente de la columna principal. Por ejemplo, puede analizar Pedidos lineales en su dimensión de Canales de marketing pero aplicar Pedidos en forma de U a los códigos de seguimiento específicos dentro de un Canal. Para editar el modelo de atribución aplicado a un desglose, simplemente sitúe el ratón encima del modelo de desglose y haga clic en **[!UICONTROL Editar]**:

![Configuración del desglose](assets/breakdown_settings.png)

Este es el comportamiento esperado al aplicar modelos de atribución a desgloses o editarlos:

* Si aplica una atribución cuando no existen otras atribuciones, esta se aplica a todo el árbol de columnas.

* Si añade un desglose después de aplicar una atribución, utilizará el valor predeterminado para el desglose dado que se añadió (si esa dimensión tiene un valor predeterminado). De lo contrario, se utiliza el desglose de la columna principal. Algunas dimensiones tienen una asignación predeterminada. Por ejemplo, las dimensiones temporales y el remitente del reenvío utilizan el mismo contacto. La dimensión Producto utiliza Último contacto. Otras dimensiones no tienen un valor predeterminado y utilizarán la asignación de columna principal.

* Si ya hay atribuciones en el árbol de columnas, cambiar la atribución solo afecta a la que esté editando.

## Vídeos

Adición de dimensiones y métricas al proyecto en Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/30606)

Trabajo con dimensiones en una tabla de forma libre:

>[!VIDEO](https://video.tv.adobe.com/v/40179)

Desgloses de dimensiones por posición:

>[!VIDEO](https://video.tv.adobe.com/v/24033)
