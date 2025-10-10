---
title: Panel Audiencia media por minuto de medios
description: Aprenda a utilizar e interpretar el panel Audiencia media por minuto de medios en Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: c55b5534-a9a6-47f1-8b43-c8c0b8686c53
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '1681'
ht-degree: 91%

---

# Panel Público medio por minuto de medios {#media-average-minute-audience-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaminuteaverageaudience_button"
>title="Público medio por minuto de medios"
>abstract="Cree un panel para analizar el público medio por minuto de contenido específico o durante un período de tiempo específico."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaaverageminuteaudience_panel"
>title="Público medio por minuto de medios"
>abstract="Muestra el rendimiento de contenido de medios específicos o el rendimiento durante un período de tiempo personalizado. Especifique la dimensión de la creación de informes y, opcionalmente, segmente el contenido."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_En este artículo se describe el panel Audiencia media por minuto de medios en_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_.<br/>_Consulte el [panel de audiencia media por minuto de medios](https://experienceleague.adobe.com/es/docs/analytics/analyze/analysis-workspace/panels/average-minute-audience-panel) para ver la versión de_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** version of this article._

>[!ENDSHADEBOX]

>[!NOTE]
>
>El panel **[!UICONTROL Público medio por minuto de medios]** solo está disponible para los clientes que hayan comprado la Colección de medios de streaming para Customer Journey Analytics.
>
>Póngase en contacto con su representante de ventas de Adobe o con el equipo de cuentas de Adobe para obtener más información.
>

En Analysis Workspace, el público medio por minuto puede proporcionar información sobre

* el tiempo empleado en ver un flujo de medios específico dividido por la duración del contenido o
* el tiempo empleado de visionado durante un período de tiempo personalizado con la granularidad seleccionada.

El panel Público medio por minuto de medios le permite conocer el consumo promedio del contenido comparando programas de cualquier longitud o género. Por ejemplo, puede conocer el consumo medio comparando una comedia de 30 minutos con un evento deportivo de 3 horas.

Además, puede usar el panel Público medio por minuto de medios para comparar o añadir este público media por minuto digital a las métricas medias por minuto de la televisión lineal.

El panel Público medio por minuto de medios proporciona las siguientes ventajas sobre la métrica Público medio por minuto:

* Admite periodos de tiempo personalizados

* Permite actualizar la clasificación de la duración después de procesar las vistas (si la clasificación de la duración no estaba presente o debe corregirse)

  Si realiza esta actualización al utilizar la métrica, la clasificación de la duración no existe (si la clasificación no estaba presente). O la clasificación de la duración está desactualizada (si la clasificación estaba presente pero era incorrecta).

## Utiliza

Para utilizar un panel **[!UICONTROL Público medio por minuto de medios]**:

1. Cree un panel **[!UICONTROL Público medio por minuto de medios]**. Para obtener información sobre cómo crear un panel, consulta [Crear un panel](panels.md#create-a-panel).

1. Asegúrese de seleccionar una vista de datos para el panel que tenga componentes configurados de la colección de medios de streaming.

1. Especifica la [entrada](#panel-input) para el panel.

1. Observa la [salida](#panel-output) del panel.

### Entrada de panel

Utilice la configuración de entrada que se describe en esta sección para configurar el panel Público medio por minuto de medios.

1. Realice la siguiente configuración de entrada:

   | Configuración | Descripción |
   |---------|------------|
   | **Intervalo de fechas del panel** | El intervalo de fechas predeterminado del panel es [!UICONTROL **Este mes**] Puede editarlo para verlo un solo día o varios meses a la vez. <br></br> Esta visualización está limitada a 1440 filas de datos (por ejemplo, 24 horas con una granularidad por minuto). Si la combinación de intervalo de fechas y granularidad genera más de 1440 filas, la granularidad se actualiza automáticamente para dar cabida al intervalo de fechas completo. |
   | [!UICONTROL **Soltar un segmento aquí (o cualquier otro componente)**]. | Al igual que otros paneles, esta configuración segmenta las selecciones en función de los segmentos que haya creado. Esta configuración es una buena manera de examinar plataformas específicas, emisiones en directo u otros segmentos de medios comunes. |
   | [!UICONTROL **Calcular métrica para**] | Elija si desea ver el público medio por minuto de [**[!UICONTROL contenido específico]**](#specific-content). O si desea ver el público medio por minuto de un [**[!UICONTROL período de tiempo personalizado]**](#custom-time-period).<br/><br/>Seleccione [!UICONTROL **Período de tiempo personalizado**]: <ul><li>Si la duración no está disponible, o </li><li>si desea ver el público medio por minuto de una serie temporal con varios fragmentos de contenido, o</li><li>para el contenido sin una duración asignada específica (como durante una emisión o un evento en directo)</li></ul></li></li></ul> <p>Esta configuración cambia el flujo de trabajo y el resultado del informe.</p> |

1. Continúe con [Contenido específico](#specific-content) o [Período de tiempo personalizado](#custom-time-period), según la opción que haya elegido en el menú desplegable [!UICONTROL **Calcular métrica para**].

#### Contenido específico

1. Si seleccionó [!UICONTROL **Contenido específico**] en el menú desplegable [!UICONTROL **Calcular métrica para**] al [configurar las entradas del panel](#panel-inputs), especifique las siguientes opciones de configuración:

   | Configuración | Descripción |
   |---------|------------|
   | [!UICONTROL **Dimensión de los informes**] | Cuando selecciona contenido específico, puede seleccionar que la salida del informe utilice los campos de nombre de vídeo o ID de contenido para mostrar el contenido y su público medio por minuto asociada. |
   | [!UICONTROL **Filtrar contenido por (opcional)**] | Puede filtrar el contenido específico según la vista que desee o la forma en que se estructuran los datos. <ul>[!UICONTROL **Mostrar temporada, episodio**]: muestra los programas disponibles en la lista desplegable, que puede filtrar mediante una búsqueda (o arrastrando y soltando el nombre del programa desde la columna izquierda). Puede terminar su selección allí para ver todas las temporadas del programa, o puede filtrar por temporadas individuales y luego por episodios individuales. Esta configuración muestra los datos de los programas, las temporadas o los episodios del período de tiempo seleccionado.</li><li>[!UICONTROL **Dimensión personalizada**]: si el nombre para mostrar se encuentra en una dimensión personalizada, puede encontrarla buscando en el menú desplegable de dimensión (opcional) o utilizando la búsqueda de la columna izquierda. El elemento de dimensión se rellena automáticamente en función de esa selección y se trata como un episodio.</li><li>[!UICONTROL **Ninguno**]: muestra todos los nombres de vídeo que tengan datos de público medio por minuto para la selección que haya elegido. (Esta opción está seleccionada de manera predeterminada).</li></ul> |

1. Continúe con [Configuración avanzada de contenido específico](#specific-content-advanced-settings) para establecer la configuración avanzada.

#### Configuración avanzada de contenido específico

1. Con el [!UICONTROL **Contenido específico**] seleccionado en el menú desplegable [!UICONTROL **Calcular métrica para**], seleccione [!UICONTROL **Mostrar configuración avanzada**] y luego especifique las siguientes opciones de configuración:

   | Opciones | Descripción |
   |---------|------------|
   | **[!UICONTROL Configuración de la tabla]** | La configuración predeterminada **[!UICONTROL Mostrar valores de cálculo de la tabla]**, que muestran el numerador y el denominador del público medio por minuto como las columnas anteriores de la tabla. Al anular la selección de esta opción, se eliminan esas dos columnas. La columna de público medio por minuto permanece en la tabla junto al nombre del vídeo o el ID de contenido. |
   | **[!UICONTROL Métrica de tiempo empleado]** | Puede elegir la opción predeterminada **[!UICONTROL Tiempo invertido en contenido]**, que solo incluye el tiempo de contenido. O puede optar por utilizar **[!UICONTROL Tiempo medio empleado]**, que incluye conjuntamente el contenido y el tiempo de publicidad como cálculo del numerador para el público medio por minuto. |

1. Seleccione [!UICONTROL **Generar**] para terminar de crear el panel Público medio por minuto de medios.

1. Continúe con [Salida del panel](#panel-output) para obtener información sobre cómo usar el panel Público medio por minuto de medios.

#### Período de tiempo personalizado

1. Si seleccionó [!UICONTROL **Período de tiempo personalizado**] en el menú desplegable [!UICONTROL **Calcular métrica para**] al [configurar las entradas del panel](#panel-inputs), especifique las siguientes opciones de configuración:

   | Opciones | Descripción |
   |---------|------------|
   | **[!UICONTROL Granularidad]** | La granularidad predeterminada es de [!UICONTROL **5 minutos**], pero puede elegir cualquiera de las granularidades que se utilizan como denominador para la serie temporal dentro del período de tiempo seleccionado. Por ejemplo, si se selecciona de 12:00 pm a 12:30 pm con una granularidad de 5 minutos, la audiencia media por minuto devolverá la media de media hora, así como seis filas con la audiencia media por minuto para cada período de 5 minutos. Estas filas se utilizan como puntos de datos para el gráfico de serie temporal. |
   | [!UICONTROL **Filtrar contenido por (opcional)**] | Puede filtrar el contenido específico según la vista que desee o la forma en que se estructuran los datos. <ul>[!UICONTROL **Mostrar temporada, episodio**]: muestra los programas disponibles en la lista desplegable, que puede filtrar mediante una búsqueda (o arrastrando y soltando el nombre del programa desde la columna izquierda). Puede terminar su selección allí para ver todas las temporadas del programa, o puede filtrar por temporadas individuales y luego por episodios individuales. Esta configuración muestra los datos de los programas, las temporadas o los episodios del período de tiempo seleccionado.</li><li>[!UICONTROL **Dimensión personalizada**]: si el nombre para mostrar se encuentra en una dimensión personalizada, puede encontrarla buscando en el menú de dimensión (opcional) o utilizando la búsqueda de la columna izquierda. El elemento de dimensión se rellena automáticamente en función de esa selección y se trata como un episodio.</li><li>[!UICONTROL **Ninguno**]: muestra todos los nombres de vídeo que tengan datos de público medio por minuto para la selección que haya elegido. (Esta opción está seleccionada de manera predeterminada).</li></ul> |

1. Continúe con [Configuración avanzada del período de tiempo personalizado](#custom-time-period-advanced-settings) para establecer la configuración avanzada.

#### Configuración avanzada de período de tiempo personalizado

1. Con el [!UICONTROL **Contenido específico**] seleccionado en el menú desplegable [!UICONTROL **Calcular métrica para**], seleccione [!UICONTROL **Mostrar configuración avanzada**] y luego especifique las siguientes opciones de configuración:

   | Opción | Descripción |
   |---------|------------|
   | **[!UICONTROL Configuración de la tabla]** | La configuración predeterminada muestra los valores de cálculo de la tabla, que muestra el numerador y el denominador del público medio por minuto como las columnas anteriores de la tabla. Al anular la selección de esta opción, se eliminan esas dos columnas, por lo que queda solo el público promedio por minuto junto al período de tiempo. |

1. Seleccione [!UICONTROL **Generar**] para terminar de crear el panel Público medio por minuto de medios.

1. Continúe con [Salida del panel](#panel-output) para obtener información sobre cómo usar el panel Público medio por minuto de medios.

### Salida del panel

La salida del panel varía en función de si ha elegido [!UICONTROL **Contenido específico**] o [!UICONTROL **Período de tiempo personalizado**] en el menú desplegable [!UICONTROL **Calcular métrica para**] al [configurar las entradas del panel](#panel-inputs).

#### Contenido específico

El panel Público medio por minuto de medios devuelve lo siguiente:

* Público medio total por minuto de toda la selección
* Filtros y público medio por minuto de los vídeos individuales mostrados en una tabla
* Tiempo invertido en contenido y duración del vídeo si se seleccionó esa configuración avanzada

Para editar y reconstruir el panel en cualquier momento, seleccione ![Editar](/help/assets/icons/Edit.svg) en la parte superior derecha.

![Vista predeterminada](assets/specific-content-panel-output.png)

#### Fuente de datos de contenido específico

El panel Público medio por minuto de medios solo utiliza la métrica Público medio por minuto de medios para recopilar datos. Los desgloses u otras métricas no se pueden usar en el panel.

| Métrica | Descripción |
|--------|-------------|
| **[!UICONTROL Público medio por minuto]** | El tiempo empleado en ver el flujo de medios dividido por la duración del vídeo proporcionada mediante clasificaciones. |

#### Período de tiempo personalizado {#custom-time-period-output}

El panel Público medio por minuto de medios devuelve lo siguiente:

* El público medio total por minuto de toda la selección

* El público medio por minuto máxima y mínima

* Gráfico de series lineales que muestra el público medio por minuto de toda la selección.

* Una tabla muestra los filtros y el público medio por minuto de las granularidades, así como el tiempo empleado en contenido y la granularidad de cada período de tiempo

  Esta tabla solo se muestra si está seleccionada la opción de configuración avanzada denominada [!UICONTROL **Mostrar valores de cálculo de la tabla**].

Para editar y reconstruir el panel en cualquier momento, seleccione ![Editar panel de público medio por minuto de medios](/help/assets/icons/Edit.svg) en la parte superior derecha.


#### Fuente de datos del período de tiempo personalizado

El panel Público medio por minuto de medios solo utiliza la métrica Público medio por minuto de medios para recopilar datos. Los desgloses u otras métricas no se pueden usar en el panel.

| Métrica | Descripción |
|---|---|
| **[!UICONTROL Promedio de público por minuto]** | El tiempo empleado en ver el flujo de medios dividido por la selección total o la granularidad seleccionada en minutos. |


>[!MORELIKETHIS]
>
> [Crear un panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
> > [Panel Visualizadores simultáneos de medios](media-concurrent-viewers.md)
> > [Panel Tiempo invertido en la reproducción de medios](media-playback-time-spent.md)
>