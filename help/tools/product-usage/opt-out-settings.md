---
title: Configuración de la exclusión del uso del producto
description: Administre la configuración de la exclusión para usuarios individuales dentro de su organización.
exl-id: 0ea24582-bab8-4a76-ac00-7c265423e8bb
autotag-review: '2026-05-19T09:31:49.294Z'
TQID: 'https://experienceleague.adobe.com/O67EiLS9ltB20iQ3d4mxlDcrwR06-r9SmbXZJ37slJs'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: a67cb189-a535-41f6-afa2-448f39c4759fid: cc5596a7-18f9-4e6c-87eb-ce3d0a9efb66
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 85%

---

# Configuración de la exclusión del uso del producto {#product-usage-opt-out-settings}

La página _Configuración de exclusión_ le permite excluir o volver a incluir a usuarios de su organización del seguimiento del uso de productos. Solo está visible para los administradores de productos.

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Herramientas]** > **[!UICONTROL Uso del producto]** > **[!UICONTROL Configuración de exclusión]**

En esta página están disponibles los siguientes se abarcan los siguientes ajustes:

* **[!UICONTROL Usuario de exclusión]**: Un menú desplegable que contiene todos los usuarios de Customer Journey Analytics de su organización. Seleccione un usuario de este menú desplegable y seleccione **[!UICONTROL Exclusión]** para excluir a ese usuario del seguimiento del uso del producto. Ese usuario se añade a la tabla [!UICONTROL Lista de exclusión de usuarios] que aparece a continuación.
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
