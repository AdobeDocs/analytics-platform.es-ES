---
title: Calcular el tamaño de la conexión
description: Informe sobre el uso actual del Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 1f496175e504cefed4239aab454744ecae72a6ea
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 0%

---


# Calcular el tamaño de la conexión

Es posible que necesite saber cuántas filas de datos tiene actualmente en [!UICONTROL Customer Journey Analytics]. El propósito de este tema es mostrarle cómo informar sobre el uso actual de [!UICONTROL Customer Journey Analytics].

1. En [!UICONTROL Customer Journey Analytics], haga clic en la ficha **[!UICONTROL Conexiones]**.
1. En la pantalla [!UICONTROL Editar conexión], seleccione una conexión para la que desee determinar el tamaño de uso/conexión.

   ![Editar conexión](assets/edit-connection.png)

1. Seleccione un conjunto de datos que forme parte de la conexión desde el carril izquierdo. En este caso, es el conjunto de datos &quot;Impresión B2B&quot;.

   ![conjunto de datos](assets/dataset.png)

1. Haga clic en el icono azul (i) (información) junto a su nombre. Observará que el conjunto de datos tiene 3,800 filas/eventos. Además, para el número exacto de filas, haga clic en **[!UICONTROL Editar en Experience Platform]** debajo de la tabla de previsualizaciones. Esto lo redirigirá a los datasets en [!UICONTROL Adobe Experience Platform].

   ![Información del conjunto de datos de AEP](assets/data-size.png)

1. Observe que los **[!UICONTROL registros totales]** de este conjunto de datos ascienden a 3.830 registros, con un tamaño de 388,59 KB para los datos.

1. Repita los pasos del 1 al 5 para otros conjuntos de datos de la conexión y agregue el número de registros/filas. El número agregado final será la métrica de uso de su conexión. Es el número de filas de los conjuntos de datos de la conexión que va a ingestar de [!UICONTROL Adobe Experience Platform].

## Determinar el número de filas ingeridas

El número de eventos ingeridos realmente en [!UICONTROL Customer Journey Analytics] depende de la configuración de conexión. Además, si seleccionó el ID de persona incorrecto o si este ID no está disponible para algunas filas en los conjuntos de datos, [!UICONTROL Customer Journey Analytics] ignorará esas filas. Para determinar las filas reales de eventos ingeridos, realice los siguientes pasos:

1. Una vez guardada la conexión, cree una vista de datos de la misma conexión sin ningún filtros.
1. Cree un proyecto de Workspace y seleccione la vista de datos correcta. Cree una tabla improvisada y arrastre y suelte la métrica **[!UICONTROL Eventos]** con una dimensión **[!UICONTROL Año]**. Elija un intervalo de fechas lo suficientemente grande del calendario de selección de fechas para encapsular todos los datos de la conexión. Esto le permite ver el número de eventos que se están ingeriendo en [!UICONTROL Customer Journey Analytics].

   ![Proyecto de Workspace](assets/event-number.png)

   >[!NOTE]
   >
   >Esto le permite ver el número de eventos que se están ingeriendo desde el conjunto de datos de eventos. No incluye conjuntos de datos de tipo de búsqueda y perfil. Siga los pasos del 1 al 3 en &quot;Estimar el tamaño de conexión&quot; para los conjuntos de datos de búsqueda y perfil y agregue los números para obtener el número total de filas para esta conexión.

## Diagnóstico de discrepancias

En algunos casos, es posible que observe que el número total de eventos ingestados por su conexión es diferente al número de filas en el conjunto de datos en [!UICONTROL Adobe Experience Platform]. En este ejemplo, el conjunto de datos &quot;Impresión B2B&quot; tiene 7650 filas, pero el conjunto de datos contiene 3830 filas en [!UICONTROL Adobe Experience Platform]. Existen varias razones por las que pueden producirse discrepancias y se pueden realizar los siguientes pasos para diagnosticar:

1. Desglose esta dimensión por **[!UICONTROL Id. de conjunto de datos de plataforma]** y observará dos conjuntos de datos con el mismo tamaño pero diferentes **[!UICONTROL Id. de conjunto de datos de plataforma]**. Cada conjunto de datos tiene 3825 registros. Esto significa que [!UICONTROL Customer Journey Analytics] omitió 5 registros debido a la falta de ID de persona o a la falta de marcas de hora:

   ![desglose](assets/data-size2.png)

1. Además, si registramos [!UICONTROL Adobe Experience Platform], no hay ningún conjunto de datos con el identificador &quot;5f21c12b732044194bffc1d0&quot;, por lo que alguien eliminó este conjunto de datos concreto de [!UICONTROL Adobe Experience Platform] cuando se creaba la conexión inicial. Más adelante se volvió a agregar a [!UICONTROL Customer Journey Analytics], pero [!UICONTROL ID de conjunto de datos de plataforma] se generó mediante [!UICONTROL Adobe Experience Platform].

   Obtenga más información sobre las [implicaciones de la eliminación de conjuntos de datos y conexiones](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#implications-of-deleting-data-components) en [!UICONTROL Customer Journey Analytics] y [!UICONTROL Adobe Experience Platform].
