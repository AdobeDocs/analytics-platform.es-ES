---
title: Panel de visualizadores simultáneos de medios
description: Cómo utilizar e interpretar el panel Visualizadores simultáneos de medios en Analysis Workspace.
feature: Panels
exl-id: a442fb9c-165f-4136-95e2-ce92b9280c25
role: User
source-git-commit: 0101986bb86c49776a044f754d912dc1bcb9422c
workflow-type: tm+mt
source-wordcount: '1174'
ht-degree: 88%

---

# Panel Visualizadores simultáneos de medios {#media-concurrent-viewers-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_button"
>title="Espectadores simultáneos de medios"
>abstract="Cree un panel para analizar los visualizadores simultáneos durante un período de tiempo específico."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_panel"
>title="Espectadores simultáneos de medios"
>abstract="Analice los visualizadores simultáneos a lo largo del tiempo, vea la concurrencia máxima y, opcionalmente, desglose y compare mediante segmentos, dimensiones, elementos de dimensión o intervalos de fechas."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artículo documenta el panel de visualizadores simultáneos de medios en_ ![CustomerJourney Analytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_.<br/>_Consulte [Panel de visualizadores simultáneos de medios](https://experienceleague.adobe.com/es/docs/analytics/analyze/analysis-workspace/panels/media-concurrent-viewers) para la_ ![versión de Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** de este artículo._

>[!ENDSHADEBOX]


>[!NOTE]
>
>El panel Audiencia media por minuto de medios solo está disponible para los clientes que han adquirido el complemento Recopilación de medios de streaming para Customer Journey Analytics.
>
>Póngase en contacto con el representante de ventas de Adobe o con el equipo de cuentas de Adobe para obtener más información.
>

El panel **[!UICONTROL Visualizadores simultáneos de medios]** permite el análisis de los visualizadores simultáneos a lo largo del tiempo, con detalles sobre la concurrencia máxima y la capacidad de desglosar y comparar.  

Puede analizar los visualizadores simultáneos para comprender dónde se produjo el pico de concurrencia o dónde se produjeron los abandonos para proporcionar un valioso conocimiento de la calidad del contenido y la participación del visualizador. Y para solucionar problemas o planificar el volumen o la escala.

En Analysis Workspace, la métrica de espectadores simultáneos es el número de personas únicas que ven sus transmisiones de medios en un momento específico, independientemente del número de sesiones.


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Panel de visualizadores simultáneos de medios](https://video.tv.adobe.com/v/26990/?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

{{videoaa}}

>[!ENDSHADEBOX]

## Usar

Para usar un panel de **[!UICONTROL Espectadores simultáneos de medios]**:

1. Cree un panel **[!UICONTROL Espectadores simultáneos de medios]**. Para obtener información sobre cómo crear un panel, consulte [Crear un panel](panels.md#create-a-panel).

1. Asegúrese de seleccionar una vista de datos para el panel que tenga componentes configurados de la recopilación de medios de streaming.

1. Especifica la [entrada](#panel-input) para el panel.

1. Observa la [salida](#panel-output) del panel.

### Entrada de panel

Puede configurar el panel Espectadores simultáneos de medios con esta configuración de entrada:

| Configuración | Descripción |
|---|---|
| **[!UICONTROL Intervalo de fechas del panel]** | El intervalo de fechas predeterminado del panel es Hoy.  Puede editarlo para ver un solo día o varios meses a la vez. <br> <br>Esta visualización está limitada a 1440 filas de datos (por ejemplo, 24 horas con una granularidad por minuto).  Si la combinación de intervalo de fechas y granularidad genera más de 1440 filas, la granularidad se actualiza automáticamente para dar cabida al intervalo de fechas completo. |
| **[!UICONTROL Granularidad]** | El valor predeterminado de granularidad es Minuto.<br>Esta visualización está limitada a 1440 filas de datos (por ejemplo, 24 horas con una granularidad por minuto).  Si la combinación de intervalo de fechas y granularidad genera más de 1440 filas, la granularidad se actualiza automáticamente para dar cabida al intervalo de fechas completo. |
| **[!UICONTROL Números de resumen del panel]** | Para ver los detalles de fecha y hora de los visualizadores simultáneos, hay disponible un número de resumen. El Máximo muestra detalles para la concurrencia máxima. **[!UICONTROL Mínimo]** muestra los detalles de la depresión.  El panel predeterminado muestra Máximo solamente, pero puede cambiarlo para mostrar Mínimo o Máximo y Mínimo.<br><br>Si utiliza desgloses, se muestra un número de resumen para cada uno. |
| **[!UICONTROL Desglose de la serie]** | De forma opcional, puede desglosar la visualización por segmentos, dimensiones, elementos de dimensión o intervalos de fechas.<br>Puede ver hasta 10 líneas a la vez. Los desgloses están limitados a un solo nivel.<br>Al arrastrar una dimensión, los elementos de dimensión principales se seleccionan automáticamente en función del intervalo de fechas del panel seleccionado.<br>Para comparar intervalos de fechas, arrastre 2 o más intervalos de fechas al segmento de desglose de series. |

He aquí un ejemplo del panel configurado para granularidad **[!UICONTROL Minuto]**, con números de resumen **[!UICONTROL Solo máximo]**. Y desglosado por **[!UICONTROL Otro]**, **[!UICONTROL Tabla]**, **[!UICONTROL Teléfono móvil]**, **[!UICONTROL Consola de juegos]**, **[!UICONTROL Reproductor multimedia]**, **[!UICONTROL Decodificador]**, **[!UICONTROL Televisión]**.

![La vista de desglose de la serie de visualizadores simultáneos de medios que muestra 7 de 10 dimensiones, segmentos o intervalos de fechas.](assets/concurrent-viewers-series-breakdown.png)

### Salida de panel

El panel Visualizadores simultáneos de medios devuelve un gráfico de líneas y números de resumen para incluir detalles de los visualizadores simultáneos máximos o mínimos.  En la parte superior del panel, se proporciona una línea de resumen para recordarle la configuración del panel seleccionada. 

En cualquier momento, seleccione ![Editar panel de visualizadores simultáneos de medios](/help/assets/icons/Edit.svg) para editar y reconstruir el panel.

Si selecciona el desglose de series, se mostrará una línea en el gráfico de líneas y un número de resumen para cada uno:

![Salida de visualizadores simultáneos de medios.](assets/concurrent-viewers-output.png)

### Fuente de datos

La única métrica que se puede usar en este panel es **[!UICONTROL Visualizadores simultáneos]**:

| Métrica | Descripción |
|---|---|
| **[!UICONTROL Visualizadores simultáneos]** | Número de personas únicas que ven su(s) flujo(s) de medios en un punto específico en el tiempo, independientemente del número de sesiones. |

No hay ninguna tabla de forma libre disponible en esta vista.  Para ver la fuente de datos, puede descargarla desde el menú contextual de visualización del gráfico de líneas y seleccionar **[!UICONTROL Descargar datos como CSV]**.  Se incluyen los desgloses de serie.

![Las opciones de salida de los visualizadores simultáneos con &quot;Descargar datos como CSV&quot; resaltadas.](assets/concurrent-viewers-download-csv.png)

## Preguntas frecuentes

| Pregunta | Respuesta |
|---|---|
| ¿Dónde está la tabla de forma libre? ¿Cómo puedo ver la fuente de datos? | La tabla de forma libre no está disponible en esta vista.  Puede descargar la fuente de datos desde el menú contextual del gráfico de líneas y seleccionar **[!UICONTROL Descargar datos como CSV]**. |
| ¿Por qué ha cambiado la granularidad? | Esta visualización está limitada a 1440 filas de datos (por ejemplo, 24 horas con una granularidad por minuto).  Si la combinación de intervalo de fechas y granularidad genera más de 1440 filas, la granularidad se actualiza automáticamente para dar cabida al intervalo de fechas completo.<br><br>Al cambiar de un intervalo de fechas más grande a uno más pequeño, la granularidad se actualiza con el detalle más bajo permitido una vez que se cambia el intervalo de fechas. Para ver una granularidad más alta, edite el panel y vuelva a generar. |
| ¿Cómo comparo nombres de vídeo, segmentos, tipos de contenido y otros? | Para comparar estos elementos en una sola visualización, arrastre segmentos, dimensiones o elementos de dimensión específicos en el segmento de desglose de series.<br><br>La vista está limitada a 10 desgloses.  Para ver más de 10, debe usar varios paneles. |
| ¿Cómo comparo intervalos de fechas? | Para comparar intervalos de fechas en una sola visualización, utilice los desgloses de series arrastrando 2 o más intervalos de fechas.  Estos intervalos de fechas anularán el intervalo de fechas del panel. |
| ¿Cómo cambio el tipo de visualización? | Este panel solo permite la visualización de líneas de la serie temporal. |
| ¿Puedo ejecutar la detección de anomalías? | No.  La detección de anomalías no está disponible para este panel. |
| ¿Por qué utilizar personas únicas en lugar de sesiones activas? | El uso de personas únicas permite eliminar los picos no deseados en los límites de los programas (donde las sesiones finalizan y comienzan al mismo tiempo). |
| ¿Qué significa tener visualizadores simultáneos de mayor granularidad que minutos? | Con una granularidad de más de un minuto, los visualizadores simultáneos son la suma de visualizadores simultáneos únicos para todos los minutos dentro de ese intervalo de tiempo.  Por ejemplo, al nivel de granularidad de hora, los visualizadores simultáneos son la suma de los visualizadores simultáneos únicos para todos los minutos dentro de la hora. |
| ¿Muestra el panel del espacio de trabajo la misma información que el informe Visualizadores simultáneos? | No.  En Analysis Workspace, la métrica de espectadores simultáneos se definen como el número de personas únicas que ven sus transmisiones de medios en un momento específico. Independientemente del número de sesiones.<br><br>Esta métrica es diferente a los informes de Visualizadores simultáneos de la sección Informes, que utiliza Sesiones activas concurrentes.  El uso de personas únicas permite eliminar los picos no deseados en los límites de los programas (donde las sesiones finalizan y comienzan al mismo tiempo). |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->


>[!MORELIKETHIS]
>
>[Crear un panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>[Panel Tiempo invertido en la reproducción de medios](media-playback-time-spent.md)
>[Panel Público medio por minuto de medios](average-minute-audience-panel.md)
>