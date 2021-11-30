---
title: Configuración de componentes de opciones sin valor
description: Determina cómo gestionar una dimensión si está vacía.
exl-id: c7f226c5-0058-4151-9c9a-652b37266beb
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 100%

---

# Configuración de componentes de opciones sin valor

Ninguna opción de valor le permite determinar cómo gestiona Analysis Workspace las situaciones en las que un evento de un conjunto de datos contiene una métrica, pero la dimensión no contiene un valor. Puede elegir el nombre de este elemento de dimensión, ocultarlo por completo o incluso tratarlo como un valor real.

![Sin opciones de valor](../assets/no-value-options.png)

| Configuración | Descripción |
| --- | --- |
| [!UICONTROL Si se muestra, solicite Sin valor] | Campo de texto que permite cambiar el nombre del elemento de dimensión **[!UICONTROL Sin valor]** por otro. |
| [!UICONTROL No mostrar Ningún valor de forma predeterminada] | No muestra este valor en la creación de informes. Las ocurrencias de métricas no vinculadas a esta dimensión no son visibles en el informe. |
| [!UICONTROL Mostrar Ningún valor de forma predeterminada] | Muestra este valor en la creación de informes. |
| [!UICONTROL Tratar Ningún valor como valor] | Reemplaza los valores en blanco de los datos con el texto especificado en [!UICONTROL Si se muestra, solicite Sin valor]. Por ejemplo, si tuviera los tipos de dispositivos móviles como dimensión, podría cambiar el nombre del elemento **[!UICONTROL Ningún valor]** por Escritorio. Tenga en cuenta que cuando cambia este campo a un valor personalizado, el valor personalizado se trata como un valor de cadena legítimo. Por lo tanto, si introduce el valor “Rojo” en este campo, cualquier instancia de la cadena “Rojo” que aparezca en los datos en sí también se moverá bajo el mismo elemento de línea que haya especificado. |
