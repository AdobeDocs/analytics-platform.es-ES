---
title: Uso de campos derivados para informar sobre objetivos
description: Descubra cómo puede utilizar los campos derivados para informar sobre los objetivos en sus proyectos de Workspace.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: 5cd838f7-e394-4a67-9d2e-e1d08a864ca0
role: User
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 6%

---

# Uso de campos derivados para informar sobre objetivos

En este caso de uso se describe cómo utilizar la potencia de los campos derivados para establecer objetivos para una dimensión específica y, a continuación, utilizarlos en el proyecto de Workspace.

Si no está familiarizado con los campos derivados, consulte el [tutorial](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/data-views/derived-fields-in-cja.html?lang=es) y la [documentación](../data-views/derived-fields/derived-fields.md) para obtener una introducción.


## Definir metas

Para definir objetivos, cree un nuevo campo derivado en el que establezca explícitamente valores numéricos personalizados directa o indirectamente utilizando los valores resultantes de reglas anteriores en la definición del campo derivado.


### Objetivos de pedidos de certificados de regalo mensuales

Desea establecer explícitamente objetivos para los pedidos de certificados de regalo de cuatro meses, de julio de 2023 a octubre de 2023. Para ello:

1. Cree un nuevo campo derivado con el nombre `Monthly Gift Certificate Orders Goal (Incremental)`.

1. Establezca valores estáticos, con una REGLA CASE WHEN, para cada mes, estableciendo un **[!UICONTROL valor numérico personalizado]**. Consulte la regla Objetivos de producto mensuales a continuación.

   ![Metas mensuales de productos](assets/goals-derived-field-product-goals-1.png)


### Objetivos de ingresos del canal de marketing

Desea establecer una meta de ingresos mensuales para cada uno de sus canales de marketing. Para ello:

1. Cree un nuevo campo derivado utilizando la [plantilla de función de canales de mercadotecnia](/help/data-views/derived-fields/derived-fields.md#marketing-channels) con el nombre `Monthly Marketing Channel Revenue Goal (Incremental)`.

1. Defina todas las reglas para identificar correctamente cada uno de los canales de marketing en función de una combinación de reglas URL PARSE y CASE WHEN. Por ejemplo:

   ![Definición de reglas para el campo derivado del canal de marketing](assets/goals-derived-field-marketing-channel-1.png)

1. Establezca explícitamente valores estáticos, que representen los objetivos de ingresos mensuales, para los canales de marketing específicos en una regla CASO CUÁNDO final, estableciendo un **[!UICONTROL valor numérico personalizado]**. Consulte la regla [!DNL Monthly Goal] a continuación.

   ![Metas mensuales](assets/goals-derived-field-marketing-channel-2.png)



## Usar metas

Para utilizar objetivos en el proyecto de Workspace, utilice la funcionalidad de métrica calculada para &quot;normalizar&quot; el campo derivado de nuevo a su valor estático original. Esta normalización es necesaria, ya que los valores estáticos establecidos para los campos derivados que definen metas se incrementan con cada evento.

### Objetivos de pedidos de certificados de regalo mensuales

1. Cree un campo de métrica calculada denominado `Monthly Gift Certificate Orders Goal`, definido como:

   ![Objetivo de pedidos](assets/calculated-metric-ordersgoals.png)

1. Puede crear campos calculados adicionales, por ejemplo `% of Monthly Gift Certificate Orders Goal`, para mostrar el progreso real respecto a los objetivos, por ejemplo:

   ![Porcentaje de objetivo de pedidos](assets/calculated-metric-ordersgoalspercent.png)

Puede utilizar estas métricas calculadas para informar sobre el progreso en tablas improvisadas y visualizaciones. Por ejemplo:

![Tabla de forma libre que muestra los objetivos de ingresos de marketing](assets/freeform-table-product-order-goals.png)


### Objetivos de ingresos del canal de marketing

1. Cree un campo de métrica calculada denominado `Marketing Channel Revenue Goal`, definido como:

   ![Objetivo de ingresos](assets/calculated-metric-revenuegoals.png)

1. Puede crear campos calculados adicionales, por ejemplo `% of Marketing Channel Revenue Goal`, para mostrar el progreso real respecto a los objetivos, por ejemplo:

   ![Porcentaje de objetivo de ingresos](assets/calculated-metric-revenuegoalspercent.png)

Puede utilizar estas métricas calculadas para informar sobre el progreso en tablas improvisadas y visualizaciones. Por ejemplo:

![Tabla de forma libre que muestra los objetivos de ingresos de marketing](assets/freeform-table-marketing-channel-revenue-goals.png)
