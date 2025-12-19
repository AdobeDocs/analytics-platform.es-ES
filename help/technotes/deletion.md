---
title: Implicaciones de la eliminación
description: Comprender las implicaciones de la eliminación o restablecimiento de objetos de Customer Journey Analytics o Experience Platform.
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: Basics
role: Admin
source-git-commit: c8b646b7e92663ed9c7e8454a336d25e34415cbe
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 11%

---

# Implicaciones de eliminación y restablecimiento

La eliminación o restablecimiento de objetos de Customer Journey Analytics o Experience Platform tiene implicaciones. Estas implicaciones se describen en este artículo.

## Customer Journey Analytics

Tenga en cuenta las siguientes implicaciones antes de eliminar conexiones, vistas de datos o conjuntos de datos en Customer Journey Analytics:

| Acción | Implicaciones |
| --- | --- |
| Eliminar una conexión en [!UICONTROL Customer Journey Analytics] | El mensaje de error indica lo siguiente:<ul><li>Ya no funciona ninguna vista de datos creada para la conexión eliminada.</li><li> Del mismo modo, los proyectos de Workspace que dependan de vistas de datos en la conexión eliminada dejarán de funcionar.</li></ul>Tenga en cuenta que no puede eliminar conexiones de Customer Journey Analytics que:<ul><li>Están vinculados a zonas protegidas de Adobe Experience Platform para los que no tiene permisos. Aunque tenga permisos para las vistas de datos creadas en esas conexiones, no podrá eliminar las conexiones hasta que se le concedan permisos para los entornos limitados subyacentes de Adobe Experience Platform.</li><li>Tenga seleccionada la siguiente opción de compatibilidad para una vista de datos asociada con la conexión: **[!UICONTROL Establecer como vista de datos predeterminada en Adobe Journey Optimizer]**<p>Para obtener más información acerca de esta opción de configuración, consulte [Compatibilidad](/help/data-views/create-dataview.md#compatibility) en [Crear o editar una vista de datos](/help/data-views/create-dataview.md)</p></li></ul> |
| Eliminar un conjunto de datos en [!UICONTROL Customer Journey Analytics] | Cuando se elimina un conjunto de datos de una conexión en Customer Journey Analytics, las vistas de datos y los proyectos que dependen de ese conjunto de datos ya no funcionan. |
| Eliminar una vista de datos en [!UICONTROL Customer Journey Analytics] | Cuando se elimina una vista de datos en Customer Journey Analytics, cualquier panel de un proyecto de Workspace que dependa de la vista de datos ya no funciona correctamente. |



## Experience Platform

Tenga en cuenta las siguientes implicaciones antes de eliminar conjuntos de datos o lotes, o cuando restablezca o elimine entornos limitados en Experience Platform:

| Acción | Implicaciones |
| --- | --- |
| Eliminar un conjunto de datos en [!UICONTROL Experience Platform] | El flujo de datos de ese conjunto de datos en Experience Platform se detiene en cualquier conexión que incluya ese conjunto de datos. Los datos de ese conjunto de datos no se eliminan automáticamente de las conexiones con Customer Journey Analytics asociadas. |
| Eliminar un lote de un conjunto de datos en [!UICONTROL Experience Platform] | Si se elimina un lote de un conjunto de datos de [!UICONTROL Adobe Experience Platform], se eliminará el mismo lote de cualquier conexión de [!UICONTROL Customer Journey Analytics] que contenga ese lote específico. [!UICONTROL Customer Journey Analytics] recibirá una notificación de los lotes que se eliminaron en [!UICONTROL Adobe Experience Platform]. |
| Eliminar un lote de [!UICONTROL Experience Platform] **mientras se está ingiriendo** en [!UICONTROL Customer Journey Analytics] | Si solo hay un lote en el conjunto de datos, no aparecerán datos ni datos parciales de dicho lote en [!UICONTROL Customer Journey Analytics]. La ingesta se revierte. Si, por ejemplo, hay 5 lotes en el conjunto de datos y 3 de ellos ya se han introducido cuando se eliminó el cuarto lote, los datos de esos 3 lotes aparecerán en [!UICONTROL Customer Journey Analytics]. |
| Eliminar conjuntos de datos de búsqueda en [!UICONTROL Experience Platform] | Mientras que la eliminación de conjuntos de datos es posible para otros conectores de origen, no se admite la eliminación de [conjuntos de datos del conector Source de clasificaciones de Analytics](https://experienceleague.adobe.com/es/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications). Si elimina un conjunto de datos de este tipo por error, póngase en contacto con el Servicio de atención al cliente. |
| Eliminación o restablecimiento de una zona protegida en Experience Platform | Al [eliminar una zona protegida de Experience Platform](https://experienceleague.adobe.com/es/docs/experience-platform/sandbox/ui/user-guide#delete-a-sandbox), también se eliminarán todos los esquemas, conjuntos de datos, lotes, directivas y mucho más de dicha zona protegida. La zona protegida ya no existe, así como el identificador y el nombre de la zona protegida.<br/>Al [restablecer una zona protegida de Experience Platform](https://experienceleague.adobe.com/es/docs/experience-platform/sandbox/ui/user-guide#reset-a-sandbox), se eliminarán todos los esquemas, conjuntos de datos, lotes, directivas y mucho más de dicha zona protegida. Aunque el nombre y los permisos de la zona protegida permanecen intactos, el identificador de la zona protegida se cambia una vez finalizado el restablecimiento.<br/><br/>Customer Journey Analytics usa el identificador y el nombre de la zona protegida para asociar una conexión con una zona protegida. Como resultado: <ul><li>Se eliminan las conexiones asociadas con la zona protegida eliminada o restablecida.</li><li>Se eliminan las vistas de datos (y todas las definiciones de componentes, como los campos derivados, dentro de la vista de datos) basadas en las conexiones eliminadas.</li><li>Se eliminan los componentes que dependen de las vistas de datos eliminadas. Como segmentos, métricas calculadas, anotaciones, alertas, audiencias publicadas y exportaciones.</li><li>Los paneles de los proyectos de Workspace que hacen referencia a las vistas de datos eliminadas no se pueden utilizar. Estos paneles muestran **[!UICONTROL errores de vista de datos desconocidos]**. Quite estos paneles o, si es posible, asócielos a una vista de datos existente.</li><li>Ya no debería consultar los datos (históricos) de la conexión eliminada que ya está disponible en Customer Journey Analytics mediante el servicio de consultas o las herramientas que dependen de la extensión de BI. Finalmente, el soporte técnico o de ingeniería de Adobe eliminará estos datos de Customer Journey Analytics.</li></ul>Como las implicaciones de restablecer o eliminar una zona protegida en Experience Platform son importantes, tenga en cuenta lo siguiente antes de restablecer o eliminar una zona protegida:<ul><li>Enumere las conexiones para comprender qué conexiones pertenecen a cada zona protegida.</li><li>Muestre vistas de datos para comprender qué vistas de datos están asociadas a qué conexiones.</li><li>Identifique proyectos importantes de Workspace y comprenda a qué vistas de datos hacen referencia estos proyectos en sus paneles.</li><li>Identifique las integraciones con herramientas que utilizan la extensión de BI y comprenda en qué vistas de datos se basan estas integraciones.</li></ul> |
