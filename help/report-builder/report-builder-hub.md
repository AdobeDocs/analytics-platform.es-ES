---
title: ¿Qué es el Report Builder Hub en Customer Journey Analytics?
description: Describe los componentes de Report Builder Hub
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
source-git-commit: bb53440ac1019b639b5c4dd1e0ecd41fc1150ec3
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 1%

---


# Centro de Report Builder

Utilice el concentrador de Report Builder para crear, actualizar o eliminar bloques de datos.

El centro de Report Builder contiene los paneles COMANDOS y EDICIÓN RÁPIDA .

![](./assets/image13.png)

## Panel COMANDOS

Utilice el panel COMANDOS para acceder a comandos compatibles con las celdas seleccionadas o con una acción anterior.

![](./assets/hub1.png)

### Comandos

| Comandos mostrados | Disponible cuando... | Finalidad |
|------|------------------|--------|
| Crear bloque de datos | Se seleccionan una o más celdas en el libro. | Se utiliza para crear un bloque de datos |
| Editar bloque de datos | El rango de celdas o celdas seleccionado forma parte de un solo bloque de datos. | Se utiliza para editar un bloque de datos. |
| Actualizar bloque de datos | La selección contiene al menos un bloque de datos. El comando solo actualizará los bloques de datos de la selección. | Se utiliza para actualizar uno o más bloques de datos. |
| Actualizar todos los bloques de datos | El libro contiene uno o más bloques de datos. | Se utiliza para actualizar TODOS los bloques de datos del libro |
| Copiar bloque de datos | La celda o el rango de celdas seleccionado forma parte de uno o más bloques de datos. | Se utiliza para copiar un bloque de datos. |
| Eliminar bloque de datos | El rango de celdas o celdas seleccionado forma parte de un solo bloque de datos. | Se utiliza para eliminar un bloque de datos. |

## panel EDICIÓN RÁPIDA

Cuando se seleccionan uno o varios bloques de datos en una hoja de cálculo, el Report Builder muestra el panel EDITAR RÁPIDO . Puede utilizar el panel EDICIÓN RÁPIDA para cambiar parámetros en un solo bloque de datos o para cambiar parámetros en varios bloques de datos al mismo tiempo.

![](./assets/hub2.png)

Los cambios realizados con las secciones Edición rápida se aplican a todos los bloques de datos seleccionados.

### Vistas de datos

Los bloques de datos extraen datos de una vista de datos seleccionada. Si se seleccionan varios bloques de datos en una hoja de cálculo y no se extraen datos de la misma vista de datos, el enlace **Vistas de datos** muestra *Múltiples*.

Al cambiar la vista de datos, todos los bloques de datos de la selección adoptan la nueva vista de datos. Los componentes del bloque de datos coinciden con la nueva vista de datos en función del ID (por ejemplo, que coincida con ```evars```). Si no se encuentra un componente en un bloque de datos, se muestra un mensaje de advertencia y el componente se elimina del bloque de datos.

Para cambiar la vista de datos, seleccione una nueva vista de datos en el menú desplegable.

![](./assets/image16.png)

### Intervalo de fechas

**El intervalo de** fechas muestra el intervalo de fechas para los bloques de datos seleccionados. Si se seleccionan varios bloques de datos con varios intervalos de fechas, el enlace **Intervalo de fechas** muestra *Varios*.

### Filtros

El vínculo **Filters** muestra una lista resumida de los filtros utilizados por los bloques de datos seleccionados. Si se seleccionan varios bloques de datos con varios filtros aplicados, el enlace **Filters** muestra *Multiple*.
