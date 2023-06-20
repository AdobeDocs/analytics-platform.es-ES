---
title: Cómo usar filtros en Report Builder en Customer Journey Analytics
description: Describe cómo utilizar filtros en Report Builder para Customer Journey Analytics
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
exl-id: 1f39d7f4-b508-45d8-9b97-81242c3805d3
solution: Customer Journey Analytics
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 97%

---

# Trabajo con filtros en Report Builder

Puede aplicar Filtros cuando cree un nuevo bloque de datos o cuando seleccione la opción **Editar bloque de datos** del panel COMANDOS.

## Aplicación de filtros a un bloque de datos

Para aplicar un filtro a todo el bloque de datos, haga doble clic en un filtro o arrastre y suelte los filtros de la lista de componentes en la sección Filtros de la Tabla.

## Aplicación de filtros a métricas individuales

Para aplicar filtros a métricas individuales, arrastre y suelte un filtro en una métrica de la tabla. También puede hacer clic en el botón **...** a la derecha de una métrica en el panel Tabla y, a continuación, seleccionar **Métrica de filtro**. Para ver los filtros aplicados, pase el ratón sobre una métrica o selecciónela en el panel Tabla. Las métricas con filtros aplicados muestran un icono de filtro.

<!-- ![](./assets/image24.png) -->

![](./assets/filter_by.png)

## Filtros de edición rápida

Puede utilizar el panel de edición rápida para añadir, quitar o reemplazar los filtros para bloques de datos existentes.

Cuando se selecciona un rango de celdas en la hoja de cálculo, la variable **Filtros** en el panel Edición rápida muestra una lista resumida de los filtros utilizados por los bloques de datos de esa selección.

Edición de filtros mediante el panel Edición rápida

1. Seleccione un rango de celdas de uno o varios bloques de datos.

   ![](./assets/select_multiple_dbs.png)

1. Haga clic en el vínculo Filtros para iniciar el panel Edición rápida - Filtros.

   ![](./assets/quick_edit_filters.png)

### Agregado o eliminación de un filtro

Puede añadir o quitar filtros utilizando las opciones Agregar o Quitar.

1. Seleccione la pestaña **Agregar/eliminar** en el panel Edición rápida - Filtros.

   Todos los filtros aplicados a los bloques de datos seleccionados se muestran en el panel Edición rápida - Filtros. Los filtros aplicados a todos los bloques de datos de la selección se enumeran en el encabezado **Se aplica a todos los bloques de datos seleccionados**. Los filtros aplicados a algunos bloques de datos, pero no a todos, se enumeran en el encabezado **Se aplica a uno o más bloques de datos seleccionados**.

   Cuando hay varios filtros presentes en los bloques de datos seleccionados, puede buscar filtros específicos mediante el campo de búsqueda **Añadir filtro**.

   ![](./assets/add_filter.png)

1. Añadir filtros seleccionándolos en el menú desplegable **Añadir filtro**.

   La lista de filtros en los que se puede buscar incluye todos los filtros accesibles para las vistas de datos que están presentes en uno o más de los bloques de datos seleccionados, así como todos los filtros disponibles globalmente en la organización.

   Al añadir un filtro, se aplica el filtro a todos los bloques de datos de la selección.

1. Para quitar filtros, haga clic en el icono Eliminar **x** a la derecha de los filtros de la lista **Filtros aplicados**.

1. Haga clic en **Aplicar** para guardar los cambios y volver al panel central.

   Report Builder muestra un mensaje para confirmar los cambios del filtro aplicado.

### Reemplazo de un filtro

Puede reemplazar un filtro existente por otro para cambiar la forma en que se filtran los datos.

1. Seleccione la pestaña **Reemplazar** en el panel Edición rápida - Filtros.

   ![](./assets/replace_filter.png)

1. Utilice el campo de búsqueda **Lista de búsqueda** para localizar filtros específicos.

1. Elija uno o varios filtros que desee reemplazar.

1. Busque uno o varios filtros en el campo Reemplazar con.

   Al seleccionar un filtro, se añade a la lista **Reemplazar con**...

   ![](./assets/replace_screen_new.png)

1. Haga clic en **Aplicar**.

   Report Builder actualiza la lista de filtros para reflejar el reemplazo.
