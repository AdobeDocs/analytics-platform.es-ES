---
title: Configuración de los datos de uso del producto
description: Habilite, deshabilite o configure las opciones de uso del producto.
exl-id: 85e2b515-78e6-41e8-9947-369b1e65e4fd
source-git-commit: e7534a1943307f5bbc92a845ddffe0651794b854
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 100%

---

# Configuración de los datos de uso del producto {#product-usage-data-settings}

La página _Configuración de datos_ administra la configuración de uso del producto. Puede utilizar esta página para habilitar o deshabilitar el uso del producto para su organización. También puede configurar en qué zona protegida de Adobe Experience Platform se crea el conjunto de datos y anular la ventana de retención de datos si lo desea. Solo está visible para los administradores de productos.

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Herramientas]** > **[!UICONTROL Uso del producto]** > **[!UICONTROL Configuración de datos]**

>[!IMPORTANT]
>Cuando habilite esta función, debe aceptar los términos y condiciones antes de utilizarla. Cuando acepta estos términos y condiciones, lo hace en nombre de toda la organización.

En esta página están disponibles los siguientes se abarcan los siguientes ajustes:

* **[!UICONTROL Habilitar el uso del producto]**: conmuta la disponibilidad de la recopilación de datos de uso del producto. Si habilita el uso del producto y luego lo deshabilita en el futuro, el conjunto de datos, la conexión y la vista de datos no se eliminarán. El seguimiento se desactiva globalmente para su organización cuando se desactiva.
* **[!UICONTROL Zona protegida]**: determina la zona protegida de Adobe Experience Platform en la que se crean el esquema y el conjunto de datos. La zona protegida que elija no afecta a la recopilación de datos de uso del producto. Si cambia esta configuración de zona protegida, se eliminarán todos los datos existentes. Se crearán un nuevo conjunto de datos, conexión y vista de datos en la zona protegida seleccionada.
* **[!UICONTROL Anular ventana de retención de datos]**: cada conjunto de datos tiene una ventana de retención de datos predeterminada. Si esta configuración se desactiva, el uso del producto sigue ese período de tiempo predeterminado. Puede habilitar esta configuración si desea reducir el tiempo que se conservan los datos. Reducir el período de retención de datos ayuda a reducir los costes y le permite cumplir las directrices de privacidad específicas de cada empleado. No puede ampliar la retención de datos más allá del período de retención de datos predeterminado del conjunto de datos.

>[!CONTEXTUALHELP]
>id="cja_product_usage_sandbox"
>title="Zona protegida de Adobe Experience Platform"
>abstract="Determina la zona protegida de Adobe Experience Platform en la que se crean el esquema y el conjunto de datos."

>[!CONTEXTUALHELP]
>id="cja_product_usage_data_retention"
>title="Anulación del período de retención de datos"
>abstract="Reduzca la disponibilidad de los datos de uso del producto para ayudar a disminuir los costes o cumplir con las directrices de privacidad."

>[!CONTEXTUALHELP]
>id="product_usage_sandbox"
>title="Zona protegida de Adobe Experience Platform"
>abstract="Determina la zona protegida de Adobe Experience Platform en la que se crean el esquema y el conjunto de datos."

>[!CONTEXTUALHELP]
>id="product_usage_data_retention"
>title="Anulación del período de retención de datos"
>abstract="Reduzca la disponibilidad de los datos de uso del producto para ayudar a disminuir los costes o cumplir con las directrices de privacidad."
