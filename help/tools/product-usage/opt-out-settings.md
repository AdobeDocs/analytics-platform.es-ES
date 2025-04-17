---
title: Configuración de la exclusión del uso del producto
description: Administre la configuración de la exclusión para usuarios individuales dentro de su organización.
exl-id: 0ea24582-bab8-4a76-ac00-7c265423e8bb
source-git-commit: e7534a1943307f5bbc92a845ddffe0651794b854
workflow-type: ht
source-wordcount: '222'
ht-degree: 100%

---

# Configuración de la exclusión del uso del producto {#product-usage-opt-out-settings}

La página _Configuración de exclusión_ le permite excluir o volver a incluir a usuarios de su organización del seguimiento del uso de productos. Solo está visible para los administradores de productos.

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Herramientas]** > **[!UICONTROL Uso del producto]** > **[!UICONTROL Configuración de exclusión]**

En esta página están disponibles los siguientes se abarcan los siguientes ajustes:

* **[!UICONTROL Exclusión de usuarios]**: una lista desplegable que contiene todos los usuarios de Customer Journey Analytics de su organización. Seleccione un usuario en esta lista desplegable y seleccione **[!UICONTROL Exclusión]** para excluir a ese usuario del seguimiento del uso del producto. Ese usuario se añade a la tabla [!UICONTROL Lista de exclusión de usuarios] que aparece a continuación.
* **[!UICONTROL Lista de exclusión de usuarios]**: una tabla que muestra todos los usuarios que actualmente están excluidos del seguimiento del uso del producto. Para volver a incluir a un usuario en el seguimiento del uso del producto, seleccione la casilla de verificación que hay junto a un usuario determinado y, a continuación, seleccione el botón **[!UICONTROL Inclusión]**.

Adobe utiliza una combinación de seguimiento del lado del cliente y del lado del servidor para recopilar datos de uso de productos para su organización. Cuando inicialmente se excluye a un usuario, es posible que ese usuario siga viendo los datos de seguimiento del lado del cliente en su depurador hasta que cierre la sesión y vuelva a iniciarla en Customer Journey Analytics. La validación del lado del servidor de Adobe garantiza que los datos de seguimiento del lado del cliente se descarten para los usuarios excluidos.

>[!CONTEXTUALHELP]
>id="cja_product_usage_opt_out_settings"
>title="Exclusión de usuarios"
>abstract="Excluya usuarios del seguimiento del uso del producto."

>[!CONTEXTUALHELP]
>id="product_usage_opt_out_settings"
>title="Exclusión de usuarios"
>abstract="Excluya usuarios del seguimiento del uso del producto."
