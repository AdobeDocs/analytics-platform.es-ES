---
title: Implicaciones de eliminación
description: Qué sucede cuando se eliminan conexiones, conjuntos de datos o lotes en Customer Journey Analytics o Adobe Experience Platform.
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 64c165e30926f2571bce5ea2f31560daf50acc46
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 81%

---

# Implicaciones de eliminación

Tenga esto en cuenta esto antes de eliminar conexiones, conjuntos de datos o lotes en Customer Journey Analytics o Adobe Experience Platform:

| Cuando... | Esto sucede... |
| --- | --- |
| Eliminar una conexión en [!UICONTROL Customer Journey Analytics] | Aparecerá un mensaje de error para indicar lo siguiente:<ul><li>Las vistas de datos creadas para la conexión eliminada ya no funcionarán.</li><li> Del mismo modo, los proyectos de Workspace que dependan de vistas de datos en la conexión eliminada dejarán de funcionar.</li></ul>Tenga en cuenta que no puede eliminar conexiones de CJA vinculadas a zonas protegidas de AEP para las que no tiene permisos. Aunque tenga permisos para las vistas de datos creadas en esas conexiones, no podrá eliminar las conexiones hasta que se le concedan permisos para las zonas protegidas de AEP subyacentes. |
| Eliminar un conjunto de datos en [!UICONTROL Adobe Experience Platform] (AEP) | Al eliminar un conjunto de datos en AEP, se detendrá el flujo de datos desde dicho conjunto de datos a cualquier conexión que incluya el conjunto de datos. Los datos de ese conjunto de datos no se eliminan automáticamente de las conexiones con CJA asociadas. |
| Eliminar un conjunto de datos en [!UICONTROL Customer Journey Analytics] | Al eliminar un conjunto de datos de una conexión en CJA, las vistas de datos y los proyectos que dependían de ese conjunto de datos dejarán de funcionar. |
| Eliminar un lote de un conjunto de datos (en [!UICONTROL Adobe Experience Platform]) | Si se elimina un lote de un conjunto de datos de [!UICONTROL Adobe Experience Platform], se eliminará el mismo lote de cualquier conexión de [!UICONTROL Customer Journey Analytics] que contenga ese lote específico. [!UICONTROL Customer Journey Analytics] recibirá una notificación de los lotes que se eliminaron en [!UICONTROL Adobe Experience Platform]. |
| Eliminar un lote **mientras se está ingiriendo** en [!UICONTROL Customer Journey Analytics] | Si solo hay un lote en el conjunto de datos, no aparecerán datos ni datos parciales de dicho lote en [!UICONTROL Customer Journey Analytics]. La ingesta se revertirá. Si, por ejemplo, hay 5 lotes en el conjunto de datos y 3 de ellos ya se han ingerido cuando se elimine el conjunto de datos, los datos de esos 3 lotes aparecerán en [!UICONTROL Customer Journey Analytics]. |
| Eliminar conjuntos de datos de búsqueda en [!UICONTROL Adobe Experience Platform] | Mientras que la eliminación de conjuntos de datos es posible para otros conectores de origen, actualmente no se admite para [Conector de origen de clasificaciones de Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html?lang=es). Si elimina un conjunto de datos por error, póngase en contacto con el Servicio de atención al cliente de Adobe. |
