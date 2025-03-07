---
title: Administración de bloques de datos mediante Report Builder en Customer Journey Analytics
description: Describe cómo utilizar la función de administración en Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 70103020-a4a9-43be-933c-bde5a6d088c8
source-git-commit: bd2d45b9fc1380e36fc482ee75e1a9bbb26f6cf7
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 57%

---

# Administrar bloques de datos en Report Builder

Puede ver y administrar todos los bloques de datos de un libro mediante el Administrador de bloques de datos. El Administrador de bloques de datos proporciona capacidades de búsqueda, filtro y ordenación que le permiten localizar rápidamente bloques de datos concretos. Después de seleccionar uno o más bloques de datos, puede editar, eliminar o actualizar los bloques de datos seleccionados.

![Pantalla del administrador de bloques de datos.](./assets/image52.png)

## Ver bloques de datos

Haga clic en **Administrar** para ver una lista de todos los bloques de datos de un libro.


![Opción Administrar para ver una lista de todos los bloques de datos.](./assets/image53.png)

El Administrador de bloques de datos muestra todos los bloques de datos presentes en un libro. 

![La lista de todos los bloques de datos presentes en un libro.](./assets/image52.png)

## Ordenar la lista de bloques de datos

Puede ordenar la lista de bloques de datos por una columna mostrada. Por ejemplo, puede ordenar la lista de bloqueados de datos por vistas de datos, segmentos, intervalo de fechas y otras variables.

Para ordenar la lista de bloques de datos, haga clic en un encabezado de columna.

![Ordenando los bloques de datos.](./assets/image54.png)

## Buscar en la lista de bloques de datos

Utilice el campo Buscar para localizar cualquier contenido en la tabla de bloques de datos. Por ejemplo, puede buscar métricas contenidas en los bloques de datos o la vista de datos. También puede buscar fechas que aparezcan en las columnas de intervalo de fechas, fecha de modificación o fecha de última ejecución.

![Usando el campo Buscar para localizar cualquier elemento en la tabla de bloques de datos.](./assets/image55.png)

## Editar bloques de datos

Puede editar la vista de datos, el intervalo de fechas o los segmentos aplicados a uno o varios bloques de datos.

Por ejemplo, puede reemplazar un segmento existente con un nuevo segmento en uno o más bloques de datos.

1. Seleccione los bloques de datos que desea actualizar. Puede seleccionar la casilla de verificación de nivel superior para seleccionar todos los bloques de datos o puede seleccionar bloques de datos individuales.

   ![Icono de edición a lápiz](./assets/image56.png)

1. Haga clic en el icono de edición para mostrar la ventana de edición rápida.

   ![Ventana de edición rápida](./assets/image58.png)

1. Seleccione un vínculo de segmento para actualizar vistas de datos, intervalos de fechas o segmentos.

   ![El campo Agregar segmento en la ventana de edición rápida](./assets/image59.png)

## Actualizar bloques de datos

Haga clic en el icono de actualización para actualizar los bloques de datos de la lista.

<img src="./assets/refresh-icon.png" width="15%" alt="Icono Actualizar"/>

Para comprobar si un bloque de datos se ha actualizado, consulte el icono de estado de la actualización.

Un bloque de datos actualizado correctamente muestra una marca de verificación en un círculo verde: <img src="./assets/refresh-success.png" width="5%" alt="Círculo verde con icono de marca de verificación"/>.

Un bloque de datos que no se ha podido actualizar muestra un icono de advertencia: <img src="./assets/refresh-failure.png" width="5%" alt="Triángulo rojo con signo de exclamación"/>. Esto facilita la identificación si algún bloque de datos contiene errores.


![Administrador de bloques de datos que muestra el estado de actualización de cada bloque de datos enumerado.](./assets/image512.png)

## Eliminar un bloque de datos

Haga clic en el icono de la papelera para eliminar un bloque de datos seleccionado.

## Agrupar bloques de datos

Puede agrupar bloques de datos mediante el menú desplegable **Agrupar por** o bien puede hacer clic en un título de columna. Para ordenar los bloques de datos por columna, haga clic en el título de la columna. Para agrupar bloques de datos por grupos, seleccione un nombre de grupo en el menú desplegable **Agrupar por**. Por ejemplo, la captura de pantalla siguiente muestra bloques de datos agrupados por hoja. Muestra los bloques de datos agrupados por Hoja1 y Hoja2.  Esto resulta útil, por ejemplo, en el caso de uso de reemplazo de segmentos. Si se han aplicado varios segmentos a cada bloque de datos, resulta útil crear un grupo que contenga todos los bloques de datos que desea reemplazar. A continuación, puede seleccionarlos y editarlos fácilmente de una vez.

![Administrador de bloques de datos que muestra la lista Agrupar por hoja.](./assets/group-data-blocks.png)

## Modificar la vista del Administrador de bloques de datos

Puede modificar qué columnas están visibles en la ventana Administrador de bloques de datos.


Haga clic en el icono  <img src="./assets/image515.png" width="3%" alt="Icono de lista de columnas"/> de la lista de columnas para seleccionar qué columnas aparecen en el Administrador de bloques de datos. Seleccione un nombre de columna para mostrar la columna. Anule la selección del nombre de columna para quitar la columna de la vista.

![Administrador de bloques de datos que muestra la lista de columnas](./assets/image516.png)
