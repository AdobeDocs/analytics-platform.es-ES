---
title: Configuración de datos de uso del producto
description: Habilite, deshabilite o configure las opciones de uso del producto.
hide: true
hidefromtoc: true
source-git-commit: 18686285efbdbc9e8fdac93e215adc4061bb0022
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---

# Configuración de datos de uso del producto

La página _Configuración de datos_ administra la configuración de uso del producto. Puede utilizar esta página para habilitar o deshabilitar el uso del producto para su organización. También puede configurar en qué entorno limitado de Adobe Experience Platform se crea el conjunto de datos y anular el período de retención de datos si lo desea.

**Customer Journey Analytics** > **Herramientas** > **Uso del producto** > **Configuración de datos**

Las siguientes configuraciones están disponibles en esta página:

* **Habilitar el uso del producto**: cambia la disponibilidad de la recopilación de datos de uso del producto. Si habilita el uso del producto y luego lo deshabilita en el futuro, el conjunto de datos, la conexión y la vista de datos no se eliminarán. El seguimiento está desactivado globalmente para su organización cuando está desactivado.
* **Entorno aislado**: Determina el entorno aislado de Adobe Experience Platform en el que se crearon el esquema y el conjunto de datos. La zona protegida que elija no afecta a la recopilación de datos de uso del producto.
* **Anular período de retención de datos**: cada conjunto de datos tiene un período de retención de datos predeterminado. Si esta configuración está deshabilitada, el uso del producto sigue ese período de tiempo predeterminado. Puede habilitar esta configuración si desea reducir el tiempo que se conservan los datos. No puede ampliar la retención de datos más allá del período de retención de datos predeterminado del conjunto de datos.
