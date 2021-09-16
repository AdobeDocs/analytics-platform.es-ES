---
title: Sin opciones de valor, configuración del componente
description: Determine cómo manejar una dimensión si está vacía.
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 35%

---


# Sin configuración de componentes de Opciones de valor

Ninguna opción de valor le permite determinar cómo gestiona Analysis Workspace las situaciones en las que un evento de un conjunto de datos contiene una métrica pero la dimensión no contiene un valor. Puede elegir el nombre de este elemento de dimensión, ocultarlo por completo o incluso tratarlo como un valor real.

![Sin opciones de valor](../assets/no-value-options.png)

| Configuración | Descripción |
| --- | --- |
| [!UICONTROL Si se muestra, llame a &quot;Sin valor&quot;] | Campo de texto que permite cambiar el nombre del elemento de dimensión **[!UICONTROL No value]** por otro. |
| [!UICONTROL No mostrar Ningún valor de forma predeterminada] | No muestra este valor en la creación de informes. Las ocurrencias de métricas no vinculadas a esta dimensión no son visibles en el informe. |
| [!UICONTROL Mostrar Ningún valor de forma predeterminada] | Muestra este valor en los informes. |
| [!UICONTROL Tratar Ningún valor como valor] | Reemplaza los valores en blanco en los datos con el texto especificado en [!UICONTROL Si se muestra, llame a &quot;Ningún valor&quot;]. Por ejemplo, si tuviera los tipos de dispositivos móviles como dimensión, podría cambiar el nombre del elemento **[!UICONTROL Ningún valor]** por Escritorio. Al cambiar este campo a un valor personalizado, el valor personalizado se trata como un valor de cadena legítimo. Por lo tanto, si introduce el valor “Rojo” en este campo, cualquier instancia de la cadena “Rojo” que aparezca en los datos en sí también se moverá bajo el mismo elemento de línea que haya especificado. |
