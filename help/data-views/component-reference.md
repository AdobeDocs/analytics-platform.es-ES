---
title: Referencia de componente estándar
description: Detalles e información sobre todos los componentes estándar que se pueden agregar a cualquier vista de datos.
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
source-git-commit: 181fc4fbf599c5ca34f4786439e83ac0e4a524dd
workflow-type: ht
source-wordcount: '583'
ht-degree: 100%

---

# Referencia de componente estándar

La mayoría de las dimensiones y métricas de CJA se basan en elementos de esquema del conjunto de datos de Adobe Experience Platform. Sin embargo, hay varios componentes disponibles para agregarlos a una vista de datos independientemente de la conexión que utilice.

Los [!UICONTROL Componentes estándares] son componentes que no se generan a partir de los campos de esquema del conjunto de datos, sino que se generan en el sistema. Algunos componentes del sistema son necesarios para facilitar las funciones de creación de informes en Analysis Workspace, mientras que otros componentes del sistema son opcionales.

![Componentes estándar](assets/standard-components.png)

## Componentes estándares necesarios

De forma predeterminada, estos componentes estándares necesarios se añaden a cada vista de datos. Son esenciales para las funciones de creación de informes que ofrece el Customer Journey Analytics.

| Nombre del componente | Dimensión o métrica | Notas |
| --- | --- | --- |
| [!UICONTROL Personas] | Métrica | Basado en el ID de persona especificado en una [!UICONTROL Conexión]. |
| [!UICONTROL Sesiones] | Métrica | Basado en la configuración de sesión de la vista de datos. |
| [!UICONTROL Eventos] | Métrica | El número de filas de todos los conjuntos de datos de evento de una [!UICONTROL Conexión]. |
| [!UICONTROL Minuto] | Dimensión | El minuto en que ocurrió un evento determinado (redondeado hacia abajo). El primer elemento de dimensión es el primer minuto del intervalo de fechas y el último elemento de dimensión es el último minuto del intervalo de fechas. |
| [!UICONTROL Hora] | Dimensión | Hora a la que se produjo un evento determinado (redondeado hacia abajo). El primer elemento de dimensión es la primera hora del intervalo de fechas y el último elemento de dimensión es la última hora del intervalo de fechas. |
| [!UICONTROL Día] | Dimensión | El día en que se produjo un evento determinado. El primer elemento de dimensión es el primer día del intervalo de fechas y el último elemento de dimensión es el último día del intervalo de fechas. |
| [!UICONTROL Semana] | Dimensión | La semana en que se produjo un evento determinado. El primer elemento de dimensión es la primera semana del intervalo de fechas y el último elemento de dimensión es la última semana del intervalo de fechas. |
| [!UICONTROL Mes] | Dimensión | Mes en el que se produjo un evento determinado. El primer elemento de dimensión es el primer mes del intervalo de fechas y el último elemento de dimensión es el último mes del intervalo de fechas. |
| [!UICONTROL Trimestre] | Dimensión | El trimestre en el que se produjo un evento determinado. El primer elemento de dimensión es el primer trimestre del intervalo de fechas y el último elemento de dimensión es el último trimestre del intervalo de fechas. |
| [!UICONTROL Año] | Dimensión | Año en el que se produjo un evento determinado. El primer elemento de dimensión es el primer año del intervalo de fechas y el último elemento de dimensión es el año más reciente del intervalo de fechas. |

## Componentes estándar opcionales

Los componentes estándar opcionales están disponibles en la pestaña **[!UICONTROL Vistas de datos]** > **[!UICONTROL Editar vista de datos]** > **[!UICONTROL Componentes]** > **[!UICONTROL Componentes estándar]**.

| Nombre del componente | Dimensión o métrica | Notas |
| --- | --- | --- |
| [!UICONTROL La sesión finaliza] | Métrica | El número de eventos que fueron el primer evento de una sesión. Cuando se utiliza en una definición de filtro (por ejemplo, [!UICONTROL La sesión inicia] existe), se filtra hasta el primer evento de cada sesión. |
| [!UICONTROL La sesión termina] | Métrica | El número de eventos que fueron el último evento de una sesión. De forma similar a [!UICONTROL Inicio de sesión], también se puede utilizar en una definición de filtro para filtrar cosas hasta el último evento de cada sesión. |
| [!UICONTROL Tiempo empleado (segundos)] | Métrica | Suma el tiempo entre dos valores diferentes para una dimensión. |
| [!UICONTROL Tiempo empleado por evento] | Dimensión | Agrupa el [!UICONTROL Tiempo empleado] de la métrica en bloques de [!UICONTROL Eventos]. |
| [!UICONTROL Tiempo empleado por sesión] | Dimensión | Agrupa el [!UICONTROL Tiempo empleado] de la métrica en bloques de [!UICONTROL Sesiones]. |
| [!UICONTROL Tiempo empleado por persona] | Dimensión | Agrupa el [!UICONTROL Tiempo empleado] de la métrica en bloques de [!UICONTROL Personas]. |
| [!UICONTROL ID de lote] | Dimensión | Representa el lote de Experience Platform del que formaba parte un [!UICONTROL Evento]. |
| [!UICONTROL ID de conjunto de datos] | Dimensión | Representa el conjunto de datos del Experience Platform del que formaba parte un [!UICONTROL Evento]. |
