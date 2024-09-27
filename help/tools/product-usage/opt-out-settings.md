---
title: Configuración de exclusión del uso del producto
description: Administre la configuración de exclusión para usuarios individuales dentro de su organización.
hide: true
hidefromtoc: true
source-git-commit: 60c53b29f8e4105f96bf312462610024517605b8
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 0%

---

# Configuración de exclusión del uso del producto

La página _Configuración de exclusión_ le permite excluir o volver a incluir usuarios de su organización del seguimiento del uso de productos.

**Customer Journey Analytics** > **[!UICONTROL Herramientas]** > **[!UICONTROL Uso del producto]** > **[!UICONTROL Configuración de exclusión]**

Las siguientes configuraciones están disponibles en esta página:

* **[!UICONTROL Usuario de exclusión]**: Una lista desplegable que contiene todos los usuarios Customer Journey Analytics de su organización. Seleccione un usuario de esta lista desplegable y seleccione **[!UICONTROL Exclusión]** para excluir a ese usuario del seguimiento del uso del producto. Ese usuario se agrega a la tabla [!UICONTROL Lista de usuarios excluidos] que aparece a continuación.
* **[!UICONTROL Lista de usuarios excluidos]**: Una tabla que muestra todos los usuarios que actualmente están excluidos del seguimiento del uso del producto. Para volver a incluir a un usuario en el seguimiento del uso del producto, selecciona la casilla de verificación que hay junto a un usuario determinado y, a continuación, selecciona el botón **[!UICONTROL Inclusión]**.

El Adobe de utiliza una combinación de seguimiento del lado del cliente y del lado del servidor para recopilar datos de uso de productos para su organización. Cuando se excluye a un usuario por primera vez, es posible que ese usuario siga viendo los datos de seguimiento del lado del cliente en su depurador hasta que cierre la sesión y vuelva a iniciarla en el Customer Journey Analytics. La validación del lado del servidor de Adobe garantiza que los datos de seguimiento del lado del cliente se descarten para los usuarios excluidos.
