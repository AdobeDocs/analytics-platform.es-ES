---
title: Panel de audiencia media por minuto de medios
description: Cómo utilizar e interpretar el panel Audiencia media por minuto de medios en Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: c55b5534-a9a6-47f1-8b43-c8c0b8686c53
source-git-commit: e4d4ff530d28e692301ca0671e055a164b9f7035
workflow-type: tm+mt
source-wordcount: '1664'
ht-degree: 31%

---

# Panel de audiencia media por minuto de medios

>[!NOTE]
>
>El panel Audiencia media por minuto de medios solo está disponible para los clientes que han adquirido el complemento Colección de medios de streaming para Customer Journey Analytics.
>
>Póngase en contacto con su representante de ventas de Adobe o con el equipo de cuenta de Adobe para adquirir el complemento de recopilación de medios de streaming.

En Analysis Workspace, la audiencia media por minuto es el tiempo que se pasa viendo el flujo de medios dividido por la duración del contenido o la selección total del periodo y la granularidad seleccionada.

El panel Audiencia media por minuto de medios le permite comprender mejor el consumo promedio del contenido al comparar programas de cualquier género o duración. Por ejemplo, puede comprender el consumo promedio al comparar una comedia de TV de 30 minutos con un evento deportivo de 3 horas.

Además, puede usar el panel Audiencia media por minuto de medios para comparar o anexar esta audiencia media por minuto digital a métricas de minuto promedio de televisión lineales.

El panel Audiencia media por minuto de medios proporciona las siguientes ventajas sobre la métrica Audiencia media por minuto:

* Admite periodos de tiempo personalizados

* Permite actualizar la clasificación de duración después de procesar las vistas (si no estaba presente o si debe corregirse)

  Si hizo esto al utilizar la métrica, o bien no existirá (si la clasificación no estaba presente) o estará desactualizada (si la clasificación estaba presente, pero era incorrecta).

## Acceso al panel Audiencia media por minuto de medios

1. En Analysis Workspace, vaya a un grupo de informes que tenga componentes habilitados desde el complemento de recopilación de medios de streaming.

1. En la barra de navegación izquierda, seleccione el icono **Paneles**.

   ![Icono de paneles en la navegación izquierda](assets/panels-icon.png)

1. Arrastre el panel [!UICONTROL **Audiencia media por minuto de medios**] al lienzo en Analysis Workspace.

1. Para configurar el panel, continúe con [Entradas del panel](#panel-inputs).

## Entradas de panel {#Input}

Utilice la configuración de entrada descrita en esta sección para configurar el panel Audiencia media por minuto de medios.

1. Comience a crear un panel Audiencia media por minuto de medios, tal como se describe en [Acceso al panel Audiencia media por minuto de medios](#access-the-media-average-minute-audience-panel).

1. Configure las siguientes opciones de entrada:

   | Configuración | Descripción |
   |---------|------------|
   | **Intervalo de fechas del panel** | El intervalo de fechas predeterminado del panel es [!UICONTROL **Este mes**]. Puede editarlo para ver un solo día o varios meses a la vez. <br></br> Esta visualización está limitada a 1440 filas de datos (por ejemplo, 24 horas con una granularidad por minuto). Si la combinación de intervalo de fechas y granularidad genera más de 1440 filas, la granularidad se actualiza automáticamente para dar cabida al intervalo de fechas completo. |
   | [!UICONTROL **Suelte un segmento aquí (o cualquier otro componente)**] | Al igual que otros paneles, esta configuración filtra las selecciones en función de los segmentos que haya creado. Esta es una buena manera de ver plataformas específicas, emisiones en directo u otros segmentos de medios comunes. |
   | [!UICONTROL **Calcular métrica para**] | Elija si desea ver la audiencia media por minuto de un contenido específico o si desea ver la audiencia de minuto promedio para un período de tiempo personalizado:<ul><li>**Contenido específico:** Esto solo está disponible si la duración se ha actualizado mediante Clasificaciones. Si la duración no está disponible, o si desea ver la audiencia de minuto promedio de una serie temporal con varios fragmentos de contenido o contenido sin una duración asignada específica (como durante un flujo o evento en vivo), debe seleccionar [!UICONTROL **Período de tiempo personalizado**]. (Las duraciones se pueden configurar mediante clasificaciones antes o después del tiempo de procesamiento).</li><li>**Período de tiempo personalizado:** Esto está disponible independientemente de si las duraciones están disponibles mediante Clasificaciones.</li></ul> <p>Esta configuración cambia el flujo de trabajo y el resultado del informe.</p> |

1. Continúe con [Contenido específico](#specific-content) o [Período de tiempo personalizado](#custom-time-period), según la opción que haya elegido en el menú desplegable [!UICONTROL **Calcular métrica para**].

### Contenido específico

1. Si seleccionó [!UICONTROL **Contenido específico**] en el menú desplegable [!UICONTROL **Calcular métrica para**] al [configurar entradas del panel](#panel-inputs), especifique las siguientes opciones de configuración:

   | Configuración | Descripción |
   |---------|------------|
   | [!UICONTROL **Dimensión de informe**] | Al elegir contenido específico, puede seleccionar el resultado del informe para utilizar los campos Nombre del vídeo o ID de contenido, y mostrar el contenido y su audiencia de minuto promedio asociada durante el período de tiempo seleccionado. |
   | [!UICONTROL **Filtrar contenido por (opcional)**] | Elija cómo filtrar el contenido específico, según la vista que desee o la forma en que se estructuran los datos. <ul>[!UICONTROL **Programa, temporada, episodio**]: muestra los programas disponibles en la lista desplegable, que puede filtrar con una búsqueda (o arrastrando y soltando el nombre para mostrar de la columna izquierda). Puede terminar su selección allí para ver todas las temporadas del programa, o puede filtrar por temporadas individuales y luego por episodios individuales. Esta configuración muestra los datos de los programas, las temporadas o los episodios del período de tiempo seleccionado.</li><li>[!UICONTROL **Dimensión personalizada**]: Si el nombre para mostrar se encuentra en una dimensión personalizada, puede encontrarla buscando en la lista desplegable de dimensiones (opcional) o utilizando la búsqueda de la columna izquierda. El elemento de dimensión se rellena automáticamente en función de esa selección y se trata como un episodio.</li><li>[!UICONTROL **Ninguno**]: Muestra todos los nombres de vídeo que tienen datos de audiencia de minuto promedio para la selección que ha elegido. (Esta opción está seleccionada de forma predeterminada).</li></ul> |

1. Continúe con [Configuración avanzada de contenido específico](#specific-content-advanced-settings) para establecer la configuración avanzada.

### Configuración avanzada de contenido específico

1. Con [!UICONTROL **Contenido específico**] seleccionado en el menú desplegable [!UICONTROL **Calcular métrica para**], seleccione [!UICONTROL **Mostrar configuración avanzada**] y luego especifique las siguientes opciones de configuración:

   | Configuración | Descripción |
   |---------|------------|
   | Configuración de tabla | La configuración predeterminada muestra los valores de cálculo de la tabla, que muestran el numerador y el denominador de la audiencia media por minuto como las columnas anteriores de la tabla. Al anular la selección de esta opción, se eliminan esas dos columnas, por lo que queda solo la audiencia de minuto promedio junto al nombre del vídeo o el ID de contenido. |
   | Métrica de tiempo empleado | Puede elegir el tiempo invertido en contenido predeterminado, que incluye solo el tiempo invertido en contenido, o bien puede elegir usar el tiempo invertido en contenido, que incluye el contenido y el tiempo de publicidad juntos como cálculo del numerador para la audiencia media por minuto. |

1. Seleccione [!UICONTROL **Generar**] para terminar de crear el panel Audiencia media por minuto de medios.

1. Continúe con [Salida de panel](#panel-output) para obtener información sobre cómo usar el panel Audiencia media por minuto de medios.

### Período de tiempo personalizado

1. Si seleccionó [!UICONTROL **Período de tiempo personalizado**] en el menú desplegable [!UICONTROL **Calcular métrica para**] al [configurar entradas del panel](#panel-inputs), especifique las siguientes opciones de configuración:

   | Configuración | Descripción |
   |---------|------------|
   | Granularidad | La granularidad predeterminada es [!UICONTROL **5-Minute**], pero puede elegir cualquiera de las granularidades que se usan como denominador para la serie temporal dentro de la selección de período de tiempo global realizada en la selección de calendario. Por ejemplo, si se selecciona de 12:00 pm a 12:30 pm con una granularidad de 5 minutos, la audiencia media por minuto devolverá la media de media hora, así como seis filas con la audiencia media por minuto para cada periodo de 5 minutos. Estas filas se utilizan como puntos de datos para el gráfico de series temporales. |
   | [!UICONTROL **Filtrar contenido por (opcional)**] | Elija cómo filtrar el contenido específico, según la vista que desee o la forma en que se estructuran los datos. <ul>[!UICONTROL **Programa, temporada, episodio**]: muestra los programas disponibles en la lista desplegable, que puede filtrar con una búsqueda (o arrastrando y soltando el nombre para mostrar de la columna izquierda). Puede terminar su selección allí para ver todas las temporadas del programa, o puede filtrar por temporadas individuales y luego por episodios individuales. Esta configuración muestra los datos de los programas, las temporadas o los episodios del período de tiempo seleccionado.</li><li>[!UICONTROL **Dimensión personalizada**]: Si el nombre para mostrar se encuentra en una dimensión personalizada, puede encontrarla buscando en la lista desplegable de dimensiones (opcional) o utilizando la búsqueda de la columna izquierda. El elemento de dimensión se rellena automáticamente en función de esa selección y se trata como un episodio.</li><li>[!UICONTROL **Ninguno**]: Muestra todos los nombres de vídeo que tienen datos de audiencia de minuto promedio para la selección que ha elegido. (Esta opción está seleccionada de forma predeterminada).</li></ul> |

1. Continúe con [Configuración avanzada de período de tiempo personalizado](#custom-time-period-advanced-settings) para establecer la configuración avanzada.

### Configuración avanzada de período de tiempo personalizado

1. Con [!UICONTROL **Período de tiempo personalizado**] seleccionado en el menú desplegable [!UICONTROL **Calcular métrica para**], seleccione [!UICONTROL **Mostrar configuración avanzada**] y después especifique la siguiente opción de configuración:

   | Configuración | Descripción |
   |---------|------------|
   | Configuración de tabla | La configuración predeterminada muestra los valores de cálculo de la tabla, que muestra el numerador y el denominador de la audiencia de minuto promedio como las columnas anteriores de la tabla. Al anular la selección de esta opción, se eliminan esas dos columnas, por lo que queda solo la audiencia de minuto promedio junto al período de tiempo. |

1. Seleccione [!UICONTROL **Generar**] para terminar de crear el panel Audiencia media por minuto de medios.

1. Continúe con [Salida de panel](#panel-output) para obtener información sobre cómo usar el panel Audiencia media por minuto de medios.

## Salida de panel

La salida del panel varía en función de si elige [!UICONTROL **Contenido específico**] o [!UICONTROL **Período de tiempo personalizado**] en el menú desplegable [!UICONTROL **Calcular métrica para**] al [configurar las entradas del panel](#panel-inputs).

### Contenido específico

El panel Audiencia media por minuto de medios devuelve lo siguiente:

* Audiencia media total por minuto de toda la selección
* Filtros y audiencia media por minuto para los vídeos individuales mostrados en una tabla
* Tiempo invertido en contenido y duración del vídeo si se seleccionó esa configuración avanzada

Para editar y reconstruir el panel en cualquier momento, seleccione el icono Editar (lápiz) en la parte superior derecha.

![Vista predeterminada](assets/specific-content-panel-output.png)

### Fuente de datos de contenido específica

El panel Audiencia media por minuto de medios solo utiliza la métrica Audiencia media por minuto de medios para recopilar datos. Los desgloses u otras métricas no se pueden usar en el panel.

| Métrica | Descripción |
|--------|-------------|
| Promedio de audiencia por minuto | El tiempo empleado en ver el flujo de medios dividido por la duración del vídeo proporcionada mediante clasificaciones. |

### Período de tiempo personalizado {#custom-time-period-output}

El panel Audiencia media por minuto de medios devuelve lo siguiente:

* La audiencia media total por minuto de toda la selección

* La audiencia de minuto promedio máxima y mínima

* Gráfico de series de líneas que muestra la audiencia media por minuto de toda la selección.

* Una tabla que muestra los filtros y la audiencia media por minuto de las granularidades, así como el tiempo invertido en contenido y la granularidad de cada período de tiempo

  Esta tabla sólo se muestra si está seleccionada la opción de configuración avanzada [!UICONTROL **Mostrar valores de cálculo en la tabla**].

Para editar y reconstruir el panel en cualquier momento, seleccione el icono Editar (lápiz) en la parte superior derecha.

![salida de visualizadores simultáneos](assets/custom-time-period-panel-output.png)

### Fuente de datos de período de tiempo personalizado

El panel Audiencia media por minuto de medios solo utiliza la métrica Audiencia media por minuto de medios para recopilar datos. Los desgloses u otras métricas no se pueden usar en el panel.

| Métrica | Descripción |
|---|---|
| Promedio de audiencia por minuto | El tiempo empleado en ver el flujo de medios dividido por la selección total o la granularidad seleccionada en minutos. |
