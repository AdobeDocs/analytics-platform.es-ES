---
title: Customer Journey Analytics Report Builder
description: Explica cómo utilizar Report Builder para extraer datos de Customer Journey Analytics en Excel para la creación de informes recurrentes.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 2%
---

# Report Builder

Este artículo describe cómo se puede usar [!DNL Report Builder] para implementar el siguiente [caso de uso de exportación de datos](overview.md):

* Creación de informes ad hoc y recurrentes

## Introducción

[!DNL Report Builder] [!DNL Report Builder] es un complemento de Microsoft Excel que extrae datos de Customer Journey Analytics en bloques de datos de un libro. Los usuarios empresariales que ya están familiarizados con Excel pueden crear informes recurrentes sin conocer Analysis Workspace o SQL.

## Más información

Cada bloque de datos de [!DNL Report Builder] devuelve hasta 50 000 filas. Para recuperar más filas, use las opciones **[!UICONTROL Página]** y **[!UICONTROL Filas]** para extraer datos en páginas secuenciales que superen el límite de 50 000 filas. Consulte [Filtrar dimensiones](/help/report-builder/filter-dimensions.md) para obtener más información.

Puede programar un libro para su envío por correo electrónico o exportarlo a un destino de nube, como Amazon S3, Google Cloud Platform o Azure. Vea [Programar libros compartiéndolos por correo electrónico](/help/report-builder/schedule-reportbuilder.md) y [Programar libros exportándolos a destinos en la nube](/help/report-builder/report-builder-export.md) para obtener más información.

Para obtener una introducción a la configuración y el uso de [!DNL Report Builder], consulte [Información general de Report Builder](/help/report-builder/rb-overview.md).
