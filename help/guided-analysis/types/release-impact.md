---
title: Análisis de impacto de versiones
description: Compare el rendimiento en períodos iguales antes y después de la publicación.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: 93e6e4f1-bbe4-4a6c-8ec3-54d1f9a8b847
role: User
source-git-commit: d492220eaf12242a870f3826b31edd3d1ea99a3b
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 7%

---

# [!UICONTROL Análisis del impacto de la versión] {#release-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_guidedanalysis_releaseimpact_button"
>title="Impacto de la versión"
>abstract="Compare el rendimiento en períodos iguales antes y después de la publicación."

<!-- markdownlint-enable MD034 -->

El análisis ![Versión](/help/assets/icons/Release.svg) **[!UICONTROL Impacto de la versión]** muestra una comparación del rendimiento de los indicadores clave antes y después de una fecha determinada. El eje horizontal de este informe es un intervalo de tiempo, mientras que el eje vertical mide los indicadores clave deseados. Una barra vertical en medio del gráfico representa la fecha que desea comparar antes y después de. Esta fecha suele representar un cambio notable en el producto con el que desea medir, como una actualización del producto o un lanzamiento de campaña.

>[!VIDEO](https://video.tv.adobe.com/v/3421665/?learn=on)

## Casos prácticos

Los casos de uso de este análisis incluyen:

* **Evaluación general del rendimiento:** La comparación de indicadores clave generales, como las medidas de participación, puede ayudarle a determinar si una versión determinada tuvo éxito en general.
* **Monitoreo**: rastrea métricas vitales que esperarías que permanecieran planas cuando se hicieran cambios, como tiempo de carga o cantidad de inicios de sesión. Utilice este análisis para compararlos antes y después de una publicación, y garantizar que no tenga consecuencias no deseadas.
* **Adopción de características**: si una actualización de producto se centra en mejorar una característica determinada, puede usar este análisis para comparar directamente el uso de esa característica antes y después de la actualización del producto.
* **Detección de errores**: El seguimiento del número de errores antes y después de una versión puede proporcionar un indicador anticipado de los problemas de los clientes. Si observa un aumento de errores inmediatamente después de una versión, puede trabajar con equipos de ingeniería o desarrollo para identificar y corregir el problema, lo que evita un mayor impacto para los clientes.

## Interfaz

Consulte [Interfaz](../overview.md#interface) para obtener una descripción general de la interfaz de análisis guiado. Las siguientes configuraciones son específicas de este análisis:

### Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **[!UICONTROL Vista]**: cambiar entre este análisis y [Primer impacto de uso](first-use-impact.md).
* **[!UICONTROL Indicadores clave]**: Los eventos que desea medir por usuario. Cada indicador clave seleccionado se representa como una línea de color. Se agrega a la tabla una fila que representa el evento. Se pueden incluir hasta tres eventos.
* **[!UICONTROL Contado como]**: El método de conteo que desea aplicar a los eventos seleccionados. Las opciones incluyen [!UICONTROL Eventos por usuario], [!UICONTROL Porcentaje de usuarios], [!UICONTROL Eventos], [!UICONTROL Sesiones] y [!UICONTROL Usuarios].
* **[!UICONTROL Factores]**: La fecha que desea comparar antes y después de.
* **[!UICONTROL Segmentos]**: El segmento que desea medir. El segmento seleccionado filtra los datos para centrarse únicamente en las personas que coinciden con los criterios del segmento.

### Ajustes del gráfico

El análisis [!UICONTROL Impacto de la versión] ofrece la siguiente configuración de gráfico, que se puede ajustar en el menú situado encima del gráfico:

* **[!UICONTROL Tipo de gráfico]**: El tipo de visualización que desea utilizar. Las opciones incluyen [!UICONTROL Línea] y [!UICONTROL Barra].

### Intervalo de fechas

La selección de fechas en el análisis de impacto funciona de forma diferente a otros análisis, ya que el informe gira en torno a la fecha especificada en el carril de la consulta. Las opciones disponibles son las siguientes:

* **[!UICONTROL Intervalo]**: La granularidad de fecha por la que desea ver los datos de tendencias. Las opciones válidas incluyen [!UICONTROL Diario], [!UICONTROL Semanal], [!UICONTROL Mensual] y [!UICONTROL Trimestral]. Cambiar el intervalo afecta a las opciones disponibles para los periodos Antes y Después.
* **[!UICONTROL Antes y después del período]**: Cantidad de tiempo que se debe analizar antes y después de la fecha especificada en el carril de consultas. Las opciones disponibles dependen de la selección de [!UICONTROL Intervalo].


<!--
## Example

See below for an example of the analysis.

![Release impact](../assets/release-impact.png)

-->
