---
title: Configuración de los datos de uso del producto
description: Habilite, deshabilite o configure las opciones de uso del producto.
exl-id: 85e2b515-78e6-41e8-9947-369b1e65e4fd
autotag-review: '2026-05-19T09:31:13.042Z'
TQID: 'https://experienceleague.adobe.com/5aCc69OL9tJ1-5fq0OpSrqpYhLjZgbT1auS0csSDxUA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: a67cb189-a535-41f6-afa2-448f39c4759f
  - id: cc5596a7-18f9-4e6c-87eb-ce3d0a9efb66
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 357
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
