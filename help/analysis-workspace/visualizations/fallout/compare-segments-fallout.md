---
description: Puede crear filtros a partir de un punto de contacto, añadir filtros como punto de contacto y comparar flujos de trabajo clave entre diversos filtros en Analysis Workspace.
keywords: visitas en el orden previsto y filtros;filtros en el análisis de visitas en el orden previsto;comparar filtros en visitas en el orden previsto
title: Aplicación de filtros en un análisis de visitas en orden previsto
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
role: User
source-git-commit: de04792035aa7c235751019ee9f9fe5b74b9b102
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 45%

---

# Aplicación de filtros en un análisis de visitas en orden previsto

Puede crear filtros a partir de un punto de contacto, añadir filtros como punto de contacto y comparar flujos de trabajo clave entre diversos filtros en Analysis Workspace.

>[!IMPORTANT]
>
>Los filtros utilizados como puntos de comprobación en visitas en orden previsto deben utilizar un contenedor que esté en un nivel inferior al contexto general de la visualización Visita en orden previsto. Con las visitas en orden previsto respectivas a las personas, los filtros utilizados como puntos de comprobación deben ser filtros basados en visitas o eventos. Con las visitas en orden previsto respectivas a las visitas, los filtros utilizados como puntos de comprobación deben ser filtros basados en eventos. Si utiliza una combinación no válida, el resultado de visitas en orden previsto es del 100 %. Verá una advertencia en la visualización de abandonos cuando añada un filtro incompatible como punto de contacto. Determinadas combinaciones de contenedores de filtros no válidas generan diagramas de visitas en orden previsto no válidos, como:

* Cuando se usa un filtro basado en personas como punto de contacto dentro de una visualización de abandonos de persona.
* Cuando se usa un filtro basado en personas como punto de contacto dentro de una visualización de abandonos de visitas.
* Cuando se usa un filtro basado en visitas como punto de contacto dentro de una visualización de visitas en orden previsto de visitas.

## Creación de filtros a partir de un punto de contacto

1. Cree un filtro a partir de un punto de contacto específico en el que esté especialmente interesado y que pueda ser útil para su aplicación en otros informes. Haga clic con el botón derecho en el punto de contacto y seleccione **[!UICONTROL Crear filtro a partir del punto de contacto]**.

   ![Menú desplegable de Touchpoint con la opción Crear segmento a partir de punto de contacto resaltada.](assets/fallout-createfilter.png)

   Se abre el generador de filtros [!UICONTROL Filter Builder], previamente completado con el filtro secuencial generado previamente que coincide con el punto de contacto seleccionado:

   ![El Generador de filtros muestra el filtro secuencial generado y rellenado previamente.](assets/fallout-definefilter.png)

1. Asigne un título y una descripción al filtro y guárdelo.

   Ahora puede utilizar este filtro en cualquier proyecto que desee.

## Añadir un filtro como punto de contacto

Si desea ver, por ejemplo, la tendencia de los usuarios de Estados Unidos y cómo afectan a las visitas en el orden previsto, solo tiene que arrastrar el filtro correspondiente a la visita en el orden previsto:

![El filtro de usuarios de EE. UU. seleccionado y resaltado para arrastrarlo a la visita en el orden previsto.](assets/fallout-addfilter.png)

O puede crear un punto de contacto AND arrastrando el filtro de usuarios de Estados Unidos a otro punto de comprobación.

## Comparación de filtros en visitas en orden previsto

Puede comparar una cantidad ilimitada de filtros en la visualización de visitas en el orden previsto.

1. Seleccione los filtros que quiera comparar en el panel [!UICONTROL Filtro] de la izquierda. En el ejemplo, se seleccionaron tres filtros: *Detalles del vuelo: Versión de página A*, *Detalles del vuelo: Versión de página B* y *Detalles del vuelo: Versión de página C*.
1. Los tres filtros se arrastran a la zona de colocación Filtro en la parte superior de la visualización.


1. Opcional: puede mantener *Todas las visitas* como el contenedor predeterminado o eliminar el contenedor.

   ![Secuelas que muestran todas las visitas junto con los dos filtros arrastrados en el paso anterior.](assets/fallout-multiplefilters.png)

1. Ahora puede comparar las visitas en el orden previsto de los tres filtros como, por ejemplo, cuando un filtro supera a otro u otra información.
