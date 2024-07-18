---
description: Muestra los cinco valores principales correspondientes a las dimensiones que no sean temporales (y 15 valores para las temporales).
title: Previsualización de dimensiones en Customer Journey Analytics Workspace
feature: Dimensions
exl-id: 3e620bfa-825c-4f25-956c-83c905c49f84
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 90%

---

# Previsualización de dimensiones en Analysis Workspace

Sitúe el ratón encima del icono de información (i) que encontrará junto a una dimensión. Se mostrarán los cinco valores principales correspondientes a las dimensiones que no sean temporales. En el caso de las dimensiones temporales, se mostrarán los 15 valores principales. Anteriormente estos valores solían ser estáticos, es decir, los cinco valores seleccionados no cambiaban nunca.

![Valores principales de cinco dimensiones que no sean temporales.](assets/dimension-preview.png)

Ahora, y de forma predeterminada, se mostrarán valores dinámicos en lugar de valores estáticos, con la opción de convertirlos en estáticos. Otros aspectos que considerar:

* A medida que los datos se actualicen, las columnas de dimensión dinámica se actualizarán para mostrar cinco de los quince elementos de dimensión actuales.
* Las columnas de dimensión dinámica que se copien o se muevan pasarán a ser de dimensión estática.
* Al pasar el ratón por encima de una columna de dimensión estática, verá un icono de bloqueo que indicará que la dimensión es estática.

![ventana emergente de la columna del Dimension que resalta el icono de candado.](assets/dimension_static.png)

## Mostrar los elementos de la dimensión

Al pasar el ratón por encima de una dimensión y hacer clic en la flecha derecha gris que se muestra al lado, aparece una lista de los elementos de su dimensión. Normalmente, en cualquier lista de elementos de dimensión se muestran los elementos principales de los últimos 30 días.

Si se desplaza hacia abajo hasta la parte final de la lista, verá **[!UICONTROL Mostrar los elementos principales de los últimos 6 meses]**. Haga clic en esta opción para ver los elementos principales de la dimensión durante los últimos 180 días.
