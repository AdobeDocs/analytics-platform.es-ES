---
title: Configuración de componentes de opciones sin valor
description: Determina cómo gestionar una dimensión si está vacía.
exl-id: c7f226c5-0058-4151-9c9a-652b37266beb
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 93%

---

# Configuración de componentes de opciones sin valor {#no-value-options-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_novalueoptions"
>title="Sin opciones de valor"
>abstract="Configure el comportamiento predeterminado para cuando no haya ningún valor presente en una dimensión."

<!-- markdownlint-enable MD034 -->


Ninguna opción de valor le permite determinar cómo gestiona Analysis Workspace las situaciones en las que un evento de un conjunto de datos contiene una métrica, pero la dimensión no contiene un valor. Puede elegir el nombre de este elemento de dimensión, ocultarlo por completo o incluso tratarlo como un valor real.

![Sin opciones de valor](../assets/no-value-options.png)

## Configuración {#settings}

| Configuración | Descripción |
| --- | --- |
| [!UICONTROL Si se muestra, solicite Sin valor] | Campo de texto que permite cambiar el nombre del elemento de dimensión **[!UICONTROL Sin valor]** por otro. |
| [!UICONTROL No mostrar Ningún valor de forma predeterminada] | No muestra este valor en la creación de informes. Las ocurrencias de métricas no vinculadas a esta dimensión no son visibles en el informe. |
| [!UICONTROL Mostrar Ningún valor de forma predeterminada] | Muestra este valor en la creación de informes. |
| [!UICONTROL Tratar Ningún valor como valor] | Reemplaza los valores en blanco de los datos con el texto especificado en [!UICONTROL Si se muestra, solicite Sin valor]. Por ejemplo, si tuviera los tipos de dispositivos móviles como dimensión, podría cambiar el nombre del elemento **[!UICONTROL Ningún valor]** por Escritorio. Tenga en cuenta que cuando cambia este campo a un valor personalizado, el valor personalizado se trata como un valor de cadena legítimo. Por lo tanto, si introduce el valor “Rojo” en este campo, cualquier instancia de la cadena “Rojo” que aparezca en los datos en sí también se moverá bajo el mismo elemento de línea que haya especificado. |

{style="table-layout:auto"}

## Publicación de blog

Esta es una publicación de blog relacionada sobre [el manejo de &quot;sin valor&quot; en el Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/handling-quot-no-value-quot-in-customer-journey-analytics/ba-p/597339).
