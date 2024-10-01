---
title: Configuración de datos de uso del producto
description: Habilite, deshabilite o configure las opciones de uso del producto.
hide: true
hidefromtoc: true
source-git-commit: 8f2a340f59d8cdf97a5309ec20dc36f49b8f1129
workflow-type: tm+mt
source-wordcount: '292'
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
* **Entorno aislado**: Determina el entorno aislado de Adobe Experience Platform en el que se crearon el esquema y el conjunto de datos. La zona protegida que elija no afecta a la recopilación de datos de uso del producto. Si cambia esta configuración de zona protegida, se crea un conjunto de datos, una conexión y una vista de datos independientes. Los datos históricos permanecen en la zona protegida anterior.
* **Anular período de retención de datos**: cada conjunto de datos tiene un período de retención de datos predeterminado. Si esta configuración está deshabilitada, el uso del producto sigue ese período de tiempo predeterminado. Puede habilitar esta configuración si desea reducir el tiempo que se conservan los datos. No puede ampliar la retención de datos más allá del período de retención de datos predeterminado del conjunto de datos.

>[!CONTEXTUALHELP]
>id="cja_product_usage_sandbox"
>title="Entorno aislado de Adobe Experience Platform"
>abstract="Determina el entorno limitado de Adobe Experience Platform en el que se crean el esquema y el conjunto de datos."

>[!CONTEXTUALHELP]
>id="cja_product_usage_data_retention"
>title="Anular período de retención de datos"
>abstract="Reduzca la disponibilidad de los datos de uso del producto para ayudar a reducir los costes."
