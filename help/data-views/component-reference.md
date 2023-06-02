---
title: Referencia de componente estándar
description: Detalles e información sobre todos los componentes estándar que se pueden agregar a cualquier vista de datos.
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 0fdf95906e17b9e90fa6ba652aa8e53f695279a4
workflow-type: tm+mt
source-wordcount: '1012'
ht-degree: 88%

---

# Referencia de componente estándar

La mayoría de las dimensiones y métricas de CJA se basan en elementos de esquema del conjunto de datos de Adobe Experience Platform. Sin embargo, hay varios componentes disponibles para agregarlos a una vista de datos independientemente de la conexión que utilice.

Los [!UICONTROL Componentes estándares] son componentes que no se generan a partir de los campos de esquema del conjunto de datos, sino que se generan en el sistema. Algunos componentes del sistema son necesarios para facilitar las funciones de creación de informes en Analysis Workspace, mientras que otros componentes del sistema son opcionales.

![Componentes estándar](assets/standard-components.png)

## Componentes estándares necesarios {#required}

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

{style="table-layout:auto"}

## Componentes estándar opcionales {#optional}

Los componentes estándar opcionales están disponibles en la pestaña **[!UICONTROL Vistas de datos]** > **[!UICONTROL Editar vista de datos]** > **[!UICONTROL Componentes]** > **[!UICONTROL Componentes estándar]**.

| Nombre del componente | Dimensión o métrica | Notas y valores |
| --- | --- | --- |
| [!UICONTROL a. m./p. m.] | Dimensión de partición de tiempo | a. m. o p. m. |
| [!UICONTROL ID de lote] | Dimensión | Representa el lote de Experience Platform del que formaba parte un [!UICONTROL Evento]. |
| [!UICONTROL ID de conjunto de datos] | Dimensión | Representa el conjunto de datos del Experience Platform del que formaba parte un [!UICONTROL Evento]. |
| [!UICONTROL Día del mes] | Dimensión de partición de tiempo | 1-31 |
| [!UICONTROL Día de la semana] | Dimensión de partición de tiempo | lunes, martes, miércoles, jueves, viernes, sábado, domingo |
| [!UICONTROL Día del año] | Dimensión de partición de tiempo | 1-366 |
| [!UICONTROL Hora del día] | Dimensión de partición de tiempo | 0-23 |
| [!UICONTROL  Mes del año] | Dimensión de partición de tiempo | Enero-diciembre |
| [!UICONTROL Sesiones por primera vez] | Métrica | Primera sesión de una persona definida dentro de la ventana de creación de informes. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=es#new-repeat) |
| [!UICONTROL Sesiones de retorno] | Métrica | El número de sesiones que no fueron la primera sesión de una persona. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=es#new-repeat) |
| [!UICONTROL ID de la persona] | Dimensión | Cada esquema del conjunto de datos definido en Experience Platform puede tener su propio conjunto de una o más identidades definidas y asociadas a un área de nombres de identidad. Cualquiera de ellos puede utilizarse como ID de persona. Algunos ejemplos son: ID de cookie, ID vinculado, ID de usuario, código de seguimiento, etc. El [!UICONTROL ID de persona] La dimensión es la base de la combinación de conjuntos de datos y la identificación de personas únicas en CJA.<p>Los posibles casos de uso incluyen los siguientes:<ul><li>Creación de un filtro con un valor de ID de persona específico para filtrar todo según el comportamiento de ese usuario.</li><li>Depuración: asegúrese de que los datos de un ID de cookie específico (o un ID de cliente específico) estén presentes.</li><li>Identificación de los usuarios que llamaron a un centro de llamadas.</li></ul> |
| [!UICONTROL Área de nombres de ID de persona] | Dimensión | De qué tipo de identificación consta el [!UICONTROL ID de persona]. Ejemplos: `email address`, `cookie ID`, `Analytics ID`, etc. |
| [!UICONTROL Trimestre del año] | Dimensión de partición de tiempo | T1, T2, T3, T4 |
| [!UICONTROL Repetir sesión] | Métrica | Número de sesiones que no fueron la primera sesión de una persona. [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=es#new-repeat) |
| [!UICONTROL La sesión finaliza] | Métrica | El número de eventos que fueron el primer evento de una sesión. Cuando se utiliza en una definición de filtro (por ejemplo, [!UICONTROL La sesión inicia] existe), se filtra hasta el primer evento de cada sesión.<p>Este componente debe incluirse en la vista de datos para lo siguiente [métrica calculada](/help/components/calc-metrics/default-calcmetrics.md) para que esté disponible en Workspace: <ul><li>Tasa de inicio de sesión</li></p> |
| [!UICONTROL La sesión termina] | Métrica | El número de eventos que fueron el último evento de una sesión. De forma similar a [!UICONTROL Inicio de sesión], también se puede utilizar en una definición de filtro para filtrar cosas hasta el último evento de cada sesión.<p>Este componente debe incluirse en la vista de datos para lo siguiente [métrica calculada](/help/components/calc-metrics/default-calcmetrics.md) para que esté disponible en Workspace: <ul><li>Tasa de finalización de sesión</li></p> |
| [!UICONTROL Tipo de sesión] | Dimensión | Esta dimensión tiene dos valores: 1) [!UICONTROL Primera vez] y 2) Retorno. El elemento de línea [!UICONTROL Primera vez] incluye todo el comportamiento (es decir, las métricas respecto a esta dimensión) de una sesión que se ha determinado que es la primera sesión definida por una persona. Todo lo demás está incluido en el elemento de línea [!UICONTROL Devolución] (suponiendo que todo pertenece a una sesión). Cuando las métricas no forman parte de ninguna sesión, caerían en el bloque &quot;No aplicable&quot; para esta dimensión.  [Más información](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=es#new-repeat) |
| [!UICONTROL Tiempo empleado (segundos)] | Métrica | Suma el tiempo entre dos valores diferentes para una dimensión.<p>Este componente debe incluirse en la vista de datos para lo siguiente [métricas calculadas](/help/components/calc-metrics/default-calcmetrics.md) para que esté disponible en Workspace: <ul><li>Tiempo empleado por persona</li><li>Tiempo empleado por sesión</li></p> |
| [!UICONTROL Tiempo empleado por evento] | Dimensión | Agrupa el [!UICONTROL Tiempo empleado] de la métrica en bloques de [!UICONTROL Eventos]. |
| [!UICONTROL Tiempo empleado por sesión] | Dimensión | Agrupa el [!UICONTROL Tiempo empleado] de la métrica en bloques de [!UICONTROL Sesiones]. |
| [!UICONTROL Tiempo empleado por persona] | Dimensión | Agrupa el [!UICONTROL Tiempo empleado] de la métrica en bloques de [!UICONTROL Personas]. |
| [!UICONTROL Fin de semana]/[!UICONTROL día laborable] | Dimensión de partición de tiempo | Fin de semana o día laborable |

{style="table-layout:auto"}
