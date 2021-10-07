---
title: Cómo usar los filtros en el Report Builder en el Customer Journey Analytics
description: Describe cómo usar filtros en Report Builder para CJA
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
source-git-commit: dc6317bc754218c03d78145be1c8681ad202bcb8
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 2%

---


# Filtrar dimensiones

De forma predeterminada, cada elemento de dimensión de la tabla devuelve los 10 elementos principales para esa dimensión.

Para cambiar los elementos de dimensión devueltos para cada dimensión

1. Seleccione un bloque de datos y haga clic en Editar bloque de datos en el panel COMANDOS .

1. Haga clic en Siguiente para mostrar la pestaña Dimension .

1. Haga clic en **...Icono** junto al nombre de un componente en la tabla.

   ![](./assets/image27.png)

1. Seleccione **Filter dimension** en el menú emergente para mostrar el panel **Filter dimension**.

1. Seleccione **Más popular** o **Específico**.

   ![](./assets/image28.png)

1. Seleccione las opciones adecuadas en función del tipo de filtro elegido.

1. Haga clic en **Apply** para agregar el filtro.

   El Report Builder muestra una notificación para confirmar el filtro añadido.

Para mostrar los filtros aplicados, pase el ratón sobre una dimensión. Los Dimension con filtros aplicados muestran un icono de filtro a la derecha del nombre del Dimension.

## Tipo de filtro

Existen dos formas de filtrar los elementos de dimensión: Más popular y específico.

## Más popular

La opción Más popular le permite filtrar dinámicamente los elementos de dimensión en función de los valores de las métricas. El filtrado más popular devuelve los elementos de dimensión de mayor clasificación en función de los valores de las métricas. De forma predeterminada, se muestran los 10 primeros elementos de dimensión, ordenados por la primera métrica agregada al bloque de datos.

![archivos de imagen](./assets/image29.png)


### Opciones de página y filas

Utilice los campos **Page** y **Rows** para dividir los datos en grupos o páginas secuenciales. Esto le permite extraer en el informe valores de fila clasificados que no sean los valores más altos. Esta función es especialmente útil para extraer datos que superen el límite de 50 000 filas.

#### Valores predeterminados de página y filas

- Página = 1
- Filas = 10

La configuración predeterminada Página y Filas identifica que cada página tiene 10 filas de datos. La página 1 devuelve los 10 elementos principales, la página 2 devuelve los 10 elementos siguientes, etc.

En la tabla siguiente se muestran ejemplos de valores de página y fila y el resultado.

| Página | Fila | Salida |
|------|--------|----------------------|
| 1 | 10 | Principales 10 elementos |
| 2 | 10 | Temas 11 a 20 |
| 1 | 100 | Principales 100 elementos |
| 2 | 100 | Temas 101 a 200 |
| 2 | 50 000 | Temas 50.001 a 100.000 |

#### Valores mínimo y máximo

- Página de inicio: Mín. = 1, Máx.: 50 millones
- Número de filas: Mín. = 1, Máx.: 50.000

### Incluir &quot;Sin valor&quot;

En Customer Journey Analytics, algunas dimensiones recopilan una entrada &quot;sin valor&quot;. Este filtro le permite excluir estos valores de los informes. Por ejemplo, puede crear una clasificación como la clasificación Nombre del producto basada en la clave SKU del producto. Si no se ha configurado un SKU de producto específico con su clasificación de nombre de producto específica, su valor de nombre de producto se establece en &quot;sin valor&quot;.

Incluir &quot;**Ningún valor**&quot; está seleccionado de forma predeterminada. Anule la selección de esta opción para excluir las entradas sin valor.

### Filtrar por criterios

Puede filtrar los elementos de dimensión en función de si se cumplen todos los criterios o si se cumple alguno.

Definición de criterios de filtrado

1. Seleccione un operador en la lista desplegable.

   ![](./assets/image31.png)

1. Introduzca un valor en el campo de búsqueda.

1. Haga clic en Añadir fila para confirmar la selección y añadir otro elemento de criterio.

1. Haga clic en el icono de eliminación para eliminar un elemento de criterio.

   Puede incluir hasta 10 elementos de criterios.

### Cambiar el filtro y el orden

Aparece una flecha junto a la métrica utilizada para filtrar y ordenar el bloque de datos. La dirección de la flecha indica si la métrica se ordena de bueno a menos o menos a bueno.

Para cambiar la dirección de ordenación, haga clic en la flecha situada junto a la métrica. 

Para cambiar la métrica utilizada para filtrar y ordenar el bloque de datos,

1. Pase el ratón sobre el componente de métrica deseado en el Generador de tablas para ver las opciones adicionales.

2. Haga clic en la flecha de la métrica preferida. 

   ![](./assets/image30.png)


## Filtro específico

La opción Específico permite crear una lista fija de elementos de dimensión para cada dimensión. Utilice el tipo de filtrado **Specific** para especificar los elementos de dimensión exactos que se incluirán en el filtro. Puede seleccionar elementos de una lista o de un rango de celdas.

![](./assets/image32.png)

### De la lista

1. Seleccione la opción **From list** para buscar y seleccionar elementos de dimensión.

   Cuando selecciona la opción **From list**, la lista se rellena con elementos de dimensión con la mayor cantidad de eventos primero.

   ![](./assets/image33.png)

   La lista **Elementos disponibles** se ordena desde los elementos de dimensión con la mayor cantidad de eventos a los que tienen menos.

1. Introduzca un término de búsqueda en el campo **Add item** para buscar en la lista.

1. Para buscar un elemento no incluido en los últimos 90 días de datos, haga clic en **Mostrar elementos de los últimos 6 meses** para ampliar la búsqueda.

   ![](./assets/image34.png)

   Después de cargar los datos de los últimos seis meses, el Report Builder actualiza el vínculo a **Mostrar elementos durante los últimos 18 meses**.

1. Seleccione un elemento de dimensión.

   Los elementos de dimensión seleccionados se añaden automáticamente a la lista **Elementos seleccionados**.

   ![](./assets/image35.png)

   Para eliminar un elemento de la lista, haga clic en el icono eliminar para eliminarlo de la lista.

   Para mover un elemento en la lista, arrastre y suelte el elemento o haga clic en ... para mostrar el menú mover.

   ![](./assets/image36.png)

1. Haga clic en **Aplicar**

   Report Builder actualiza la lista para mostrar el filtro específico que ha aplicado.

### Desde el rango de celdas

Seleccione la opción **From range of Cells** para elegir un rango de celdas que contenga la lista de elementos de dimensiones que desea hacer coincidir.

![](./assets/image37.png)

Cuando seleccione un rango de celdas, tenga en cuenta las restricciones siguientes:

- El rango debe tener al menos una celda.
- El rango no puede tener más de 50.000 celdas.
- El rango debe estar en una sola fila o columna sin pausarlo.

La selección puede contener celdas vacías o celdas con valores que no coinciden con un elemento de dimensión específico.

### Desde la ficha Dimension del Generador de tablas

En la pestaña **Dimension**, haga clic en el icono de cheurón situado junto al nombre de una dimensión para ver la lista de elementos de dimensión.

![](./assets/dimensions_chevron.png)

Puede arrastrar y soltar elementos en la **Tabla** o hacer doble clic en un nombre de elemento para agregarlo al Generador de **Tabla**.
