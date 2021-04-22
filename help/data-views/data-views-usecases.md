---
title: Casos de uso de vistas de datos en el Customer Journey Analytics
description: Casos de uso múltiple que muestran la flexibilidad y la potencia de las vistas de datos en el Customer Journey Analytics
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
translation-type: tm+mt
source-git-commit: 37c667b9c3f85e781c79a6595648be63c686649b
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 1%

---

# Casos de uso de vistas de datos

Estos casos de uso muestran la flexibilidad y la potencia de las vistas de datos en el Customer Journey Analytics.

## Creación de una métrica Pedidos a partir de un campo de esquema pageTitle (string)

Por ejemplo, al crear una vista de datos, puede crear una métrica [!UICONTROL Pedidos] a partir de un campo de esquema [!UICONTROL pageTitle] que sea una cadena. Estos son los pasos:

1. En la ficha Componentes, arrastre [!UICONTROL pageTitle] a la sección [!UICONTROL Métricas] en [!UICONTROL Componentes incluidos].
   ![](assets/use-case1a.png)
1. Ahora, resalte la métrica que acaba de arrastrar y cambie el nombre a [!UICONTROL Configuración de componentes] a la derecha:
   ![](assets/orders.png)
1. Abra el cuadro de diálogo [!UICONTROL Incluir/Excluir valores] a la derecha y especifique lo siguiente:
   ![](assets/orders2.png)

   La frase &quot;confirmación&quot; indica que se trata de un pedido. Después de revisar todos los títulos de las páginas donde se cumplen esos criterios, se cuenta un &quot;1&quot; para cada instancia. El resultado es una nueva métrica (no una métrica calculada). Una métrica que ha incluido o excluido valores puede utilizarse en cualquier otra métrica. Funciona con Attribution IQ, filtros y en cualquier otro lugar donde se pueden usar métricas estándar.
1. Puede especificar un modelo de atribución para esta métrica, como [!UICONTROL Último toque], con una [!UICONTROL ventana de retrospectiva] de [!UICONTROL Sesión].
También puede crear otra métrica [!UICONTROL Pedidos] desde el mismo campo y especificar un modelo de atribución diferente para él, como [!UICONTROL Primer toque] y una ventana [!UICONTROL Retrospectiva] diferente, como [!UICONTROL 30 días].

## Usar números enteros como dimensiones

Anteriormente, los enteros se trataban automáticamente como métricas en CJA. Ahora, los números (incluidos los eventos personalizados de Adobe Analytics) pueden tratarse como dimensiones. Vea el siguiente ejemplo:

1. Arrastre el entero [!UICONTROL call_length_min] a la sección [!UICONTROL Dimension] en [!UICONTROL Componentes incluidos]:

   ![](assets/integers.png)

1. Ahora puede agregar [!UICONTROL Value Bucketing] para presentar esta dimensión en forma de agrupamiento en los informes. (Sin agrupar, cada instancia de esta dimensión aparecería como un elemento de línea en los informes de Workspace).

   ![](assets/bucketing.png)

Para obtener más información sobre otras configuraciones de vistas de datos, consulte [Creación de vistas de datos](/help/data-views/create-dataview.md).
Para obtener una descripción general conceptual de las vistas de datos, consulte [Información general sobre las vistas de datos](/help/data-views/data-views.md).
