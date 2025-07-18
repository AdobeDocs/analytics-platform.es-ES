---
title: Panel Tiempo invertido en la reproducción de medios
description: Aprenda a utilizar e interpretar el panel Tiempo invertido en la reproducción de contenido en Analysis Workspace.
feature: Panels
exl-id: de0fdbea-71f0-445b-a1e4-c7e895f142d4
role: User
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '1074'
ht-degree: 98%

---

# Panel Tiempo invertido en la reproducción de medios {#media-playback-time-spent-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaplaybacktimespent_button"
>title="Tiempo invertido en la reproducción de medios"
>abstract="Cree un panel para analizar el consumo de vídeo a lo largo del tiempo, con varios niveles de granularidad, y la capacidad de realizar desgloses y comparaciones."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaplaybacktimespent_panel"
>title="Tiempo invertido en la reproducción de medios"
>abstract="Analice el consumo de vídeo a lo largo del tiempo, seleccione varias granularidades y, opcionalmente, desglose y compare usando segmentos, dimensiones, elementos de dimensión o intervalos de fechas."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_En este artículo se describe el panel Tiempo invertido en la reproducción de medios en_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;_.<br/>_Consulte el [panel Tiempo invertido en la reproducción de medios](https://experienceleague.adobe.com/es/docs/analytics/analyze/analysis-workspace/panels/media-playback-time-spent) para ver la versión de_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** de este artículo._

>[!ENDSHADEBOX]


>[!NOTE]
>
>El panel Audiencia media por minuto de medios solo está disponible para los clientes que han adquirido el complemento de la colección de medios de streaming para Customer Journey Analytics.
>&#x200B;>Póngase en contacto con su representante de ventas de Adobe o con el equipo de cuentas de Adobe para obtener más información.
>

El panel **[!UICONTROL Tiempo invertido en la reproducción de medios]** permite analizar la reproducción a lo largo del tiempo, con detalles sobre los picos de simultaneidad y la posibilidad de realizar desgloses y comparaciones. 

En Analysis Workspace, el tiempo invertido en la reproducción es la cantidad de tiempo empleado en visualizar las transmisiones de medios en un momento determinado. Incluye pausa, búfer y el tiempo para el inicio.

Los clientes que hayan adquirido el complemento de recopilación de medios de streaming pueden analizar el tiempo invertido en la reproducción para obtener un valioso conocimiento de la calidad del contenido y la participación del visualizador. Y para ayudar a solucionar problemas o a planificar el volumen o la escala.

El tiempo invertido en la reproducción puede ayudarle a conocer lo siguiente:

* Dónde se produjo el pico de simultaneidad.

* Dónde se produjeron los abandonos.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Tiempo invertido en la reproducción de contenido](https://video.tv.adobe.com/v/338699){target="_blank"} para ver un vídeo de demostración.

{{videoaa}}

>[!ENDSHADEBOX]


## Utiliza

Para usar un panel **[!UICONTROL Tiempo invertido en la reproducción de medios]**:

1. Cree un panel **[!UICONTROL Tiempo invertido en la reproducción de medios]**. Para obtener información sobre cómo crear un panel, consulta [Crear un panel](panels.md#create-a-panel).

1. Asegúrese de seleccionar una vista de datos para el panel que tenga componentes configurados de la colección de medios de streaming.

1. Especifica la [entrada](#panel-input) para el panel.

1. Observa la [salida](#panel-output) del panel.


### Entrada de panel

Puede configurar el panel Tiempo invertido en la reproducción de contenido con esta configuración de entrada:

| Configuración | Descripción |
|---|---|
| Intervalo de fecha del panel | El intervalo de fechas predeterminado del panel es Hoy. Puede editarlo para ver un solo día o varios meses a la vez.<br>Esta visualización está limitada a 1440 filas de datos (por ejemplo, 24 horas con una granularidad por minuto). Si la combinación de intervalo de fechas y granularidad genera más de 1440 filas, la granularidad se actualiza automáticamente para dar cabida al intervalo de fechas completo. |
| Granularidad | El valor predeterminado de granularidad es Minuto.<br>Esta visualización está limitada a 1440 filas de datos (por ejemplo, 24 horas con una granularidad por minuto). Si la combinación de intervalo de fechas y granularidad genera más de 1440 filas, la granularidad se actualiza automáticamente para dar cabida al intervalo de fechas completo. |
| Números de resumen del panel | Para ver los detalles de fecha y hora del tiempo invertido en la reproducción, hay disponible un número de resumen. El Máximo muestra detalles para la concurrencia máxima. El Mínimo muestra los detalles de la emisión. Suma recoge el tiempo total de reproducción invertido para la selección. El panel predeterminado muestra Máximo solamente, pero puede cambiarlo para mostrar Mínimo, Suma o cualquier combinación de los tres.<br>Si utiliza desgloses, se muestra un número de resumen para cada uno. |
| Desglose de serie | De forma opcional, puede desglosar la visualización por segmentos, dimensiones, elementos de dimensión o intervalos de fechas.<p>: Puede ver hasta 10 líneas a la vez. Los desgloses se limitan a un solo nivel.</p><p>- Al arrastrar una dimensión, los elementos de dimensión principales se seleccionarán automáticamente en función del intervalo de fechas del panel seleccionado.</p>- Para comparar intervalos de fechas, arrastre 2 o más intervalos de fechas al segmento de desglose de series. |
| Formato de hora | Puede ver el tiempo de reproducción transcurrido en `Hours:Minutes:Seconds` (valor predeterminado) o en `Minutes` (que se muestra en números enteros redondeados a 0,5). |
| Visualización de la secuencia de fechas | Si ha colocado al menos dos segmentos de intervalo de fechas como desgloses de serie, aparece la opción para seleccionar la superposición (predeterminada) o secuencial. La superposición mostrará las líneas con un inicio común del eje x para que se ejecuten en paralelo, mientras que la secuencial mostrará las líneas con su inicio específico del eje x. Si los datos se alinean (por ejemplo, el segmento 1 termina a las 8:44 p. m. y el segmento 2 comienza a las 8:45 p. m.), las líneas se muestran en secuencia. |


![Vista predeterminada del tiempo invertido en el manual de tácticas de medios.](assets/mpts_default_view.png)

### Salida del panel

El panel Tiempo invertido en la reproducción de contenido devuelve un gráfico de líneas y números de resumen para incluir detalles sobre el tiempo de reproducción máximo, mínimo o total. En la parte superior del panel, se proporciona una línea de resumen para recordarle la configuración del panel seleccionada.

En cualquier momento, seleccione ![Editar panel de tiempo invertido en la reproducción de medios](/help/assets/icons/Edit.svg) para editar y reconstruir el panel.

Si seleccionó el desglose de series, se mostrará una línea en el gráfico de líneas y un número de resumen para cada:

![Salida del tiempo invertido en la reproducción de medios que muestra un gráfico de líneas y un resumen.](assets/mpts_outputs1.png)

### Fuente de datos

La única métrica que se puede usar en este panel es Tiempo invertido en la reproducción.

| Métrica | Descripción |
|---|---|
| Tiempo invertido en la reproducción | Total de `hours:minutes:seconds` (o `minutes`) de contenido visualizado durante la granularidad seleccionada, incluidas la pausa, el búfer y el tiempo para el inicio. |

## Preguntas frecuentes

| Pregunta | Respuesta |
|---|---|
| ¿Dónde está la tabla de forma libre? ¿Cómo puedo ver la fuente de datos? | <p></p><p>La tabla de forma libre no está disponible en esta vista. Para descargar la fuente de datos, en el menú contextual del gráfico de líneas, seleccione la opción para descargar el archivo CSV.</p> |
| <p>¿Por qué ha cambiado la granularidad?</p> | <p>Esta visualización está limitada a 1440 filas de datos (por ejemplo, 24 horas con una granularidad por minuto). Si la combinación de intervalo de fechas y granularidad genera más de 1440 filas, la granularidad se actualiza automáticamente para dar cabida al intervalo de fechas completo.</p><p></p><p>Al cambiar de un intervalo de fechas más grande a uno más pequeño, la granularidad se actualiza al menor detalle permitido una vez cambiado el intervalo de fechas. Para ver una granularidad mayor, edite el panel y vuélvalo a a generar.</p> |
| <p></p><p>¿Cómo comparo nombres de vídeo, segmentos, tipos de contenido, etc.?</p> | <p>Para compararlos en una sola visualización, arrastre segmentos, dimensiones o elementos de dimensión específicos en el segmento de desglose de series.</p><p></p><p>La vista está limitada a 10 desgloses. Para ver más de 10, debe usar varios paneles.</p> |
| ¿Cómo comparo intervalos de fechas? | Para comparar intervalos de fechas en una sola visualización, utilice los desgloses de series arrastrando 2 o más intervalos de fechas. Estos intervalos de fechas anulan el intervalo de fechas del panel. |
| ¿Cómo cambio el tipo de visualización? | <p></p><p>Este panel solo permite la visualización de líneas de la serie temporal.</p> |
| ¿Puedo ejecutar la detección de anomalías? | <p></p><p>No. La detección de anomalías no está disponible para este panel.</p> |


>[!MORELIKETHIS]
>
>[Crear un panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>&#x200B;>[Panel Audiencia media por minuto de medios](average-minute-audience-panel.md)
>&#x200B;>[Panel Visualizadores simultáneos de medios](media-concurrent-viewers.md)
>
