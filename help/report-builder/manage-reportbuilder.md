---
title: Administración de bloques de datos mediante el uso de Report Builder en Customer Journey Analytics
description: Describe cómo utilizar la función de administración en Report Builder
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 70103020-a4a9-43be-933c-bde5a6d088c8
source-git-commit: e9856269ee07b7119f75b98489b47e1f35f7cf5f
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 1%

---

# Administrar bloques de datos en el Report Builder

Puede ver y administrar todos los bloques de datos de un libro mediante el Administrador de bloques de datos. El Administrador de bloques de datos proporciona funciones de búsqueda, filtro y clasificación que le permiten localizar rápidamente bloques de datos específicos. Después de seleccionar uno o más bloques de datos, puede editar, eliminar o actualizar los bloques de datos seleccionados.

![image](./assets/image52.png)

## Ver bloques de datos

Haga clic en **Administrar** para ver una lista de todos los bloques de datos de un libro.


![image](./assets/image53.png)

El Administrador de bloques de datos enumera todos los bloques de datos presentes en un libro. 

![image](./assets/image52.png)

## Ordenar la lista Bloques de datos

Puede ordenar la lista de bloqueados de datos por una columna mostrada. Por ejemplo, puede ordenar la lista de bloqueados de datos por grupos de informes, filtros, intervalo de fechas y otras variables.

Para ordenar la lista de bloqueados de datos, haga clic en un encabezado de columna.

![image](./assets/image54.png)

## Búsqueda en la Lista de bloqueados de datos

Utilice el campo Search para localizar cualquier cosa en la tabla de bloques de datos. Por ejemplo, puede buscar métricas contenidas en los bloques de datos o en el grupo de informes. También puede buscar fechas que aparezcan en las columnas de intervalo de fechas, fecha de modificación o fecha de última ejecución.

![image](./assets/image55.png)

## Editar bloques de datos

Puede editar la vista de datos, el intervalo de fechas o los filtros aplicados a uno o varios bloques de datos.

Por ejemplo, puede reemplazar un filtro existente con un nuevo filtro en uno o más bloques de datos.

1. Seleccione los bloques de datos que desea actualizar. Puede seleccionar la casilla de verificación de nivel superior para seleccionar todos los bloques de datos o puede seleccionar bloques de datos individuales.

   ![image](./assets/image56.png)

1. Haga clic en el icono de edición para mostrar la ventana de edición rápida.

   ![image](./assets/image58.png)

1. Seleccione un vínculo de filtro para actualizar vistas de datos, intervalos de fechas o filtros.

   ![image](./assets/image59.png)

## Actualizar bloques de datos

Haga clic en el icono de actualización para actualizar los bloques de datos de la lista.

<img src="./assets/refresh-icon.png" width="15%"/>

Para comprobar si se actualiza un bloque de datos, consulte el icono de estado de actualización. Una marca de verificación en un círculo verde <img src="./assets/refresh-success.png" width="5%"/> indica que la actualización del bloque de datos se ha realizado correctamente. Un bloque de datos que no se haya podido actualizar mostrará un icono de advertencia <img src="./assets/refresh-failure.png" width="5%"/>.  Esto facilita la identificación si algún bloque de datos tiene errores.


![image](./assets/image512.png)

## Eliminar un bloque de datos

Haga clic en el icono de la papelera para eliminar un bloque de datos seleccionado.

## Bloques de datos de grupo

Puede agrupar bloques de datos utilizando la variable **Agrupar por** menú desplegable o puede hacer clic en el título de una columna. Para ordenar los bloques de datos por columna, haga clic en el título de la columna. Para agrupar bloques de datos por grupos, seleccione un nombre de grupo en el **Agrupar por** menú desplegable. Por ejemplo, la captura de pantalla siguiente muestra bloques de datos agrupados por hoja. Muestra los bloques de datos agrupados por Hoja1 y Hoja2.  Esto resulta útil, por ejemplo, en el caso de uso de reemplazo de filtros. Si se han aplicado varios filtros a cada bloque de datos, resulta útil crear un grupo que contenga todos los bloques de datos que desea reemplazar. A continuación, puede seleccionarlos y editarlos fácilmente a la vez.

![image](./assets/group-data-blocks.png)

## Modificación de la vista Administrador de bloques de datos

Puede modificar qué columnas están visibles en la ventana Administrador de bloques de datos .


Haga clic en la lista de columnas <img src="./assets/image515.png" width="3%"/> para seleccionar qué columnas aparecen en el Administrador de bloques de datos. Seleccione un nombre de columna para mostrar la columna. Anule la selección del nombre de columna para quitar la columna de la vista.

![imagen](./assets/image516.png)