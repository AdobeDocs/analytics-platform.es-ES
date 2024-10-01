---
title: Configuración de datos de uso del producto
description: Habilite, deshabilite o configure las opciones de uso del producto.
hide: true
hidefromtoc: true
source-git-commit: 40b761928697d1d55e1177aa7b2b3c056739ecc9
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---

# Configuración de datos de uso del producto {#product-usage-data-settings}

{{release-limited-testing}}

La página _Configuración de datos_ administra la configuración de uso del producto. Puede utilizar esta página para habilitar o deshabilitar el uso del producto para su organización. También puede configurar en qué entorno limitado de Adobe Experience Platform se crea el conjunto de datos y anular el período de retención de datos si lo desea. Solo están visibles para los administradores de productos.

**Customer Journey Analytics** > **Herramientas** > **Uso del producto** > **Configuración de datos**

>[!IMPORTANT]
>
>Al habilitar esta función, debe aceptar los términos y condiciones antes de utilizarla. Cuando acepta estos términos y condiciones, lo hace en nombre de toda la organización.

Las siguientes configuraciones están disponibles en esta página:

* **Habilitar el uso del producto**: cambia la disponibilidad de la recopilación de datos de uso del producto. Si habilita el uso del producto y luego lo deshabilita en el futuro, el conjunto de datos, la conexión y la vista de datos no se eliminarán. El seguimiento está desactivado globalmente para su organización cuando está desactivado.
* **Entorno aislado**: Determina el entorno aislado de Adobe Experience Platform en el que se crearon el esquema y el conjunto de datos. La zona protegida que elija no afecta a la recopilación de datos de uso del producto. Si cambia esta configuración de zona protegida, se eliminarán todos los datos existentes. Se crea un nuevo conjunto de datos, conexión y vista de datos en el entorno limitado seleccionado.
* **Anular período de retención de datos**: cada conjunto de datos tiene un período de retención de datos predeterminado. Si esta configuración está deshabilitada, el uso del producto sigue ese período de tiempo predeterminado. Puede habilitar esta configuración si desea reducir el tiempo que se conservan los datos. Reducir el período de retención de datos, ayudar a reducir los costes y permitirle cumplir con las directrices de privacidad específicas de cada empleado. No puede ampliar la retención de datos más allá del período de retención de datos predeterminado del conjunto de datos.

>[!CONTEXTUALHELP]
>id="cja_product_usage_sandbox"
>title="Entorno aislado de Adobe Experience Platform"
>abstract="Determina el entorno limitado de Adobe Experience Platform en el que se crean el esquema y el conjunto de datos."

>[!CONTEXTUALHELP]
>id="cja_product_usage_data_retention"
>title="Anular período de retención de datos"
>abstract="Reduzca la disponibilidad de los datos de uso del producto para ayudar a reducir los costes o cumplir con las directrices de privacidad."
