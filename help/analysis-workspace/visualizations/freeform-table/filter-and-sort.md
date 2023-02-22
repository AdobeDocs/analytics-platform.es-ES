---
description: Documentación que describe el filtrado y la ordenación tablas en Analysis Workspace.
title: Filtrado y ordenación de tablas
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
source-git-commit: 43c8af6f9010354258a702fb702a330873d9cb8e
workflow-type: ht
source-wordcount: '692'
ht-degree: 100%

---

# Filtrado y ordenación de tablas

Las tablas de forma libre en Analysis Workspace son la base del análisis interactivo de datos. Como tal, pueden contener miles de filas de información. Filtrar y ordenar los datos puede ser una parte fundamental para que la información más importante aparezca de forma eficaz.

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## Filtrar tablas {#section_36E92E31442B4EBCB052073590C1F025}

Los filtros de Analysis Workspace le ayudan a mostrar la información más importante.

Para filtrar datos en tablas de forma libre, haga lo siguiente:

1. En una tabla de forma libre, pase el ratón sobre la columna que contiene los datos que desee filtrar. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Seleccione el icono de **Filtro** cuando aparezca.

   ![Icono de filtro en una tabla](assets/table-filter-icon.png)

1. En el campo de [!UICONTROL **Buscar palabra o frase**] especifique una palabra o frase por la que desee filtrar. Solo se muestran las filas que contienen la palabra o la frase exacta especificada.

1. (Opcional) Para filtrar por diferentes criterios o por varios criterios, seleccione [!UICONTROL **Mostrar avanzadas**].

   Las opciones disponibles son las siguientes

   | Opción | Función |
   |---------|----------|
   | [!UICONTROL **Incluir no especificado (ninguno)**] | Seleccione esta opción para mostrar los datos de la tabla que no estén dentro de ninguna de las dimensiones de la tabla. <!--what is this?--> |
   | [!UICONTROL **Coincidencias**] | <p>Seleccione [!UICONTROL **Si se cumplen todos los criterios**] para mostrar solo los datos que cumplan todos los criterios especificados. Esta opción suele dar como resultado datos más precisos.</p> <p>Seleccione [!UICONTROL **Si se cumplen algunos criterios**] para mostrar los datos que cumplan cualquiera de los criterios de filtro especificados. Esta opción suele dar como resultado datos menos precisos.</p> |
   | [!UICONTROL **Criterios**] | <p>Seleccione entre las siguientes opciones de filtro:</p><p>(Seleccione [!UICONTROL **Agregar fila**] para añadir varios criterios de filtro. La opción que seleccione en la sección [!UICONTROL **Coincidencia**] determina si se deben cumplir todos o cualquiera de los criterios agregados).</p><ul><li><p>[!UICONTROL **Contiene la frase**]: en los resultados filtrados solo se incluyen los datos que contienen la frase exacta especificada. Las palabras deben estar en el orden especificado en el [!UICONTROL **Campo de Búsqueda de la palabra o frase**].<p>Esta es la configuración predeterminada al realizar una búsqueda simple.</p></p></li><li><p>[!UICONTROL **Contiene cualquier término**]: en los resultados filtrados solo se incluyen los datos que contienen una o más palabras de la frase especificada. </p></li><li><p>[!UICONTROL **Contiene todos los términos**]: en los resultados filtrados solo se incluyen los datos que contienen todas las palabras de la frase especificada. Las palabras no tienen que estar en el orden especificado en el [!UICONTROL **Campo de Búsqueda de la palabra o frase**].</p></li><li><p>[!UICONTROL **No contiene ningún término**]: en los resultados filtrados solo se incluyen los datos que no contienen ninguna de las palabras de la frase especificada. </p></li><li><p>[!UICONTROL **No contiene la frase**]: en los resultados filtrados solo se incluyen los datos que no contienen la frase exacta especificada. Las palabras deben estar en el orden especificado en el [!UICONTROL **Campo de Búsqueda de la palabra o frase**].</p></li><li><p>[!UICONTROL **Es igual a**]: en los resultados filtrados solo se incluyen los datos que coinciden exactamente con la frase especificada. </p></li><li><p>[!UICONTROL **No es igual a**]: en los resultados filtrados solo se incluyen los datos que no coinciden exactamente con la frase especificada. </p></li><li><p>[!UICONTROL **Comienza con**]: en los resultados filtrados solo se incluyen los datos que comienzan con la palabra o frase exacta que especifique. </p></li><li><p>[!UICONTROL **Finaliza con**]: en los resultados filtrados solo se incluyen los datos que terminan con la palabra o frase exacta que especifique. </p></li></ul> |
   | [!UICONTROL **Excluir artículos siempre**] | Especifique el nombre de cualquier elemento que desee excluir de los datos filtrados. |

1. Seleccione [!UICONTROL **Aplicar**] para filtrar los datos.

   El icono de **filtro** de la ![Tabla filtrada](assets/table-filter-blue-icon.png) se vuelve azul cuando se aplica un filtro a la tabla.

## Ordenar tablas

Puede ordenar los datos de una tabla de forma libre según cualquier columna de Analysis Workspace que sea Dimensión o Métrica.

El icono de flecha hacia abajo en la ![columna de tabla ordenada](assets/table-sort-arrow-icon.png) es visible en el encabezado de la columna por la que se ordenan actualmente los datos.

1. En cualquier tabla de forma libre de Analysis Workspace, haga clic en la flecha situada junto al nombre de la dimensión o métrica.

   Tenga en cuenta lo siguiente al ordenar:

   * La flecha hacia abajo ordena en orden de bajada y la flecha hacia arriba (predeterminada) lo hace en orden de subida.
   * Puede ordenar las dimensiones de manera alfabética o numérica. Por ejemplo, es posible que haya numerado los pasos de un flujo de trabajo y que desee ordenarlos por el número de paso. Puede ordenar una dimensión relacionada con la fecha por fecha. Asimismo, puede ordenar las fuentes de datos alfabéticamente como en la imagen siguiente.

   ![](assets/sort-dimensions.png)


