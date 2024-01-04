---
description: Puede crear filtros a partir de un punto de contacto, añadir filtros como punto de contacto y comparar flujos de trabajo clave entre diversos filtros en Analysis Workspace.
keywords: visitas en el orden previsto y filtros;filtros en el análisis de visitas en el orden previsto;comparar filtros en visitas en el orden previsto
title: Aplicación de filtros en un análisis de visitas en orden previsto
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 76%

---

# Aplicación de filtros en un análisis de visitas en orden previsto

Puede crear filtros a partir de un punto de contacto, añadir filtros como punto de contacto y comparar flujos de trabajo clave entre diversos filtros en Analysis Workspace.

>[!IMPORTANT]
>
>Los filtros utilizados como puntos de comprobación en visitas en orden previsto deben utilizar un contenedor que esté en un nivel inferior al contexto general de la visualización Visita en orden previsto. Con las visitas en orden previsto respectivas a las personas, los filtros utilizados como puntos de comprobación deben ser filtros basados en visitas o eventos. Con las visitas en orden previsto respectivas a las visitas, los filtros utilizados como puntos de comprobación deben ser filtros basados en eventos. Si utiliza una combinación no válida, el resultado de visitas en orden previsto será del 100 %. Se ha añadido una advertencia a la visualización de visitas en orden previsto que se mostrará cuando añada un filtro incompatible como punto de contacto. Determinadas combinaciones de contenedores de filtros no válidas producirán diagramas de visitas en orden previsto no válidos, como:

* Cuando se usa un filtro basado en personas como punto de contacto dentro de una visualización de abandonos de persona.
* Cuando se usa un filtro basado en personas como punto de contacto dentro de una visualización de abandonos de visitas.
* Cuando se usa un filtro basado en visitas como punto de contacto dentro de una visualización de visitas en orden previsto de visitas.

## Creación de filtros a partir de un punto de contacto {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Cree un filtro a partir de un punto de contacto específico en el que esté especialmente interesado y que pueda ser útil para su aplicación en otros informes. Para ello, haga clic con el botón derecho en el punto de contacto y seleccione **[!UICONTROL Crear filtro a partir de un punto de contacto]**.

   ![Menú desplegable de Touchpoint con la opción Crear segmento a partir de punto de contacto resaltada.](assets/segment-from-touchpoint.png)

   Cuando el Generador de filtros se abre, ya contiene el filtro secuencial creado previamente que concuerda con el punto de contacto seleccionado:

   ![El Generador de filtros muestra el filtro secuencial rellenado previamente y generado previamente.](assets/segment-builder.png)

1. Asigne un título y una descripción al filtro y guárdelo.

   Ahora puede utilizar este filtro en cualquier proyecto que desee.

## Añadir un filtro como punto de contacto {#section_17611C1A07444BE891DC21EE8FC03EFC}

Si desea ver, por ejemplo, la tendencia de los usuarios de Estados Unidos y cómo afectan a las visitas en el orden previsto, solo tiene que arrastrar el filtro correspondiente a la visita en el orden previsto:

![El filtro de usuarios de EE. UU. seleccionado y resaltado para arrastrarlo a la visita en el orden previsto.](assets/segment-touchpoint.png)

O puede crear un punto de contacto AND arrastrando el filtro de usuarios de Estados Unidos a otro punto de comprobación.

## Comparación de filtros en visitas en orden previsto {#section_E0B761A69B1545908B52E05379277B56}

Puede comparar una cantidad ilimitada de filtros en la visualización de visitas en el orden previsto.

1. Seleccione los filtros que quiera comparar en el carril [!UICONTROL Filtros] de la izquierda. En nuestro ejemplo, hemos seleccionado 2 filtros: usuarios de EE. UU. y usuarios fuera de EE. UU.
1. Arrástrelos a la zona de colocación Filtro en la parte superior.

   ![La visualización de visitas en el orden previsto con filtros seleccionados y una flecha roja que señala a la zona de colocación Filtro.](assets/segment-drop.png)

1. Opcional: puede mantener Todas las visitas como el contenedor predeterminado o eliminarlo.

   ![La visita en orden previsto muestra todas las visitas junto con los dos filtros arrastrados en el paso anterior.](assets/seg-compare.png)

1. Ahora puede comparar las visitas en orden previsto de los dos filtros como, por ejemplo, cuando un filtro supera a otro u otra información.
