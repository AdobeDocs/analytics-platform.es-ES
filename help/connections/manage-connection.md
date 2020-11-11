---
title: Administrar conexiones
description: Describe cómo administrar conexiones a conjuntos de datos de Platform.
translation-type: tm+mt
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 23%

---


# Administrar conexiones

Una vez que haya creado una o más conexiones, puede administrarlas en el Administrador de [!UICONTROL conexiones]. Puede

* Eliminar una conexión.
* Cambiar el nombre de una conexión.
* Crear una vista de datos a partir de una conexión.
* Inicio y parada de la transmisión de datos.

![Administrador de conexiones](assets/connections-manager.png)

1. Haga clic en la pestaña **[!UICONTROL Conexiones]**.

2. Seleccione las conexiones que desea editar o administrar.

3. Complete una de las siguientes acciones:

   | Acción | Descripción |
   |---|---|
   | [!UICONTROL Eliminar] | Al eliminar una conexión, no se elimina el conjunto de datos, ya que los datos siguen en [!DNL Adobe Experience Platform]. Consulte &quot;Eliminar conexiones&quot; a continuación. |
   | [!UICONTROL Cambiar el nombre] | Puede cambiar el nombre de la conexión con un nombre más descriptivo. |
   | [!UICONTROL Crear Vista de datos] | Este vínculo lo lleva al [creador de vistas de datos](/help/data-views/create-dataview.md). |
   | [!UICONTROL Inicio o parada del flujo de datos] | &quot;Streaming&quot; significa que si se agregan lotes nuevos a cualquiera de los conjuntos de datos de la conexión, estos nuevos datos se introducirán en [!UICONTROL Customer Journey Analytics] para sistema de informes. |

## Eliminar conexiones

| Y si... | Esto sucede |
| --- | --- |
| ¿Desea eliminar una conexión en [!UICONTROL Customer Journey Analytics]? | Un mensaje de error indicará que:<ul><li>Las vistas de datos creadas para la conexión eliminada ya no funcionarán.</li><li> Del mismo modo, cualquier proyecto de Workspace que dependa de vistas de datos en la conexión eliminada dejará de funcionar.</li></ul> |
| ¿Desea eliminar un conjunto de datos en [!UICONTROL Adobe Experience Platform]? | Al eliminar un conjunto de datos en AEP, se detendrá el flujo de datos desde ese conjunto de datos a cualquier conexión que incluya dicho conjunto de datos. Los datos de ese conjunto de datos no se eliminan automáticamente de las conexiones CJA asociadas. |
| ¿Desea eliminar un conjunto de datos en [!UICONTROL Customer Journey Analytics]? | Actualmente, no puede eliminar un conjunto de datos dentro de una conexión que se haya guardado. Tendrías que borrar toda la conexión y el inicio. (Sin embargo, puede eliminar un conjunto de datos en [!UICONTROL Adobe Experience Platform].) |
| ¿Desea eliminar un lote de un conjunto de datos (en [!UICONTROL Adobe Experience Platform])? | Si se elimina un lote de un conjunto de datos [!UICONTROL Adobe Experience Platform], se eliminará el mismo lote de cualquier conexión [!UICONTROL Customer Journey Analytics] que contenga ese lote específico. [!UICONTROL Se notificó al ] análisis de viaje del cliente de los lotes que se eliminaron en  [!UICONTROL Adobe Experience Platform]. |
| ¿Desea eliminar un lote **mientras se está ingeriendo** en [!UICONTROL Customer Journey Analytics]? | Si sólo hay un lote en el conjunto de datos, no aparecerán datos ni datos parciales de ese lote en [!UICONTROL Customer Journey Analytics]. La ingestión se revertirá. Si, por ejemplo, hay 5 lotes en el conjunto de datos y 3 de ellos ya se han ingerido cuando se eliminó el conjunto de datos, los datos de esos 3 lotes aparecerán en [!UICONTROL Customer Journey Analytics]. |
