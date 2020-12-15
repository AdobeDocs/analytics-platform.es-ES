---
description: Puede crear segmentos a partir de un punto de contacto, añadir segmentos como punto de contacto y comparar flujos de trabajo clave entre diversos segmentos en Analysis Workspace.
keywords: fallout and segmentation;segments in fallout analysis;compare segments in fallout
title: Aplicación de segmentos en el análisis de abandonos
uuid: e87a33df-160e-4943-8d02-4d6609ae3bb1
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 23%

---


# Aplicar filtros en un análisis de visitas en orden previsto

>[!NOTE]
>
>Está viendo la documentación de Analysis Workspace en Customer Journey Analytics. Su conjunto de funciones difiere ligeramente del [Analysis Workspace de la versión tradicional de Adobe Analytics](https://docs.adobe.com/content/help/es-ES/analytics/analyze/analysis-workspace/home.html). [Más información...](/help/getting-started/cja-aa.md)

Puede crear filtros desde un punto de contacto, agregar segmentos como punto de contacto y comparar flujos de trabajo clave en varios filtros de Analysis Workspace.

>[!IMPORTANT]
>
>Los filtros utilizados como puntos de comprobación en Visitas en el orden previsto deben utilizar un contenedor que esté en un nivel inferior al contexto general de la visualización de visitas en el orden previsto. Con una visita en el orden previsto de contexto de visitante, los filtros utilizados como puntos de comprobación deben ser visitas o filtros basados en visitas. Con una visita en el orden previsto de contexto, los filtros utilizados como punto de comprobación deben ser segmentos basados en visitas individuales. Si utiliza una combinación no válida, el resultado de abandonos será del 100%. Se ha añadido una advertencia a la visualización de visitas en el orden previsto que se mostrará cuando añada un filtro incompatible como punto de contacto. Determinadas combinaciones de contenedores de filtro no válidas provocarán diagramas de visitas en el orden previsto no válidos, como:

* Uso de un filtro basado en visitantes como punto de contacto dentro de una visualización de visitas en el orden previsto en contexto de visitante
* Uso de un filtro basado en visitantes como punto de contacto dentro de una visualización de visitas en el orden previsto en contexto
* Uso de un filtro basado en visitas como punto de contacto dentro de una visualización de visitas en el orden previsto en contexto

## Crear un filtro a partir de un punto de contacto {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Cree un filtro a partir de un punto de contacto específico en el que esté especialmente interesado y que pueda resultar útil para aplicar a otros informes. Para ello, haga clic con el botón derecho en el punto de contacto y seleccione **[!UICONTROL Crear filtro a partir del punto de contacto]**.

   ![](assets/segment-from-touchpoint.png)

   Se abre el Generador de filtros, previamente rellenado con el filtro secuencial precompilado que coincide con el punto de contacto seleccionado:

   ![](assets/segment-builder.png)

1. Asigne al filtro un título y una descripción y guárdelo.

   Ahora puede usar este filtro en cualquier proyecto que desee.

## Añadir un filtro como punto de contacto {#section_17611C1A07444BE891DC21EE8FC03EFC}

Si desea ver, por ejemplo, la tendencia de los usuarios de EE. UU. y su efecto en las visitas en el orden previsto, simplemente arrastre el filtro de usuarios de EE. UU. a las visitas en el orden previsto:

![](assets/segment-touchpoint.png)

O bien, puede crear un punto de contacto AND arrastrando el filtro de usuarios de EE. UU. a otro punto de comprobación.

## Comparar filtros en visitas en el orden previsto {#section_E0B761A69B1545908B52E05379277B56}

Puede comparar un número ilimitado de filtros en la visualización de visitas en el orden previsto.

1. Seleccione los segmentos que desee comparar en el carril [!UICONTROL Filtro] de la izquierda. En nuestro ejemplo, hemos seleccionado 2 segmentos: usuarios de EE. UU. y usuarios fuera de EE. UU.
1. Arrástrelos a la zona de colocación Filtro en la parte superior.

   ![](assets/segment-drop.png)

1. Opcional: puede mantener “Todas las visitas” como el contenedor predeterminado o eliminarlo.

   ![](assets/seg-compare.png)

1. Ahora puede comparar las visitas en el orden previsto en los dos filtros, como por ejemplo, dónde un filtro supera a otro u otras perspectivas.
