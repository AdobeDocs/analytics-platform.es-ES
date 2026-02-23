---
title: Análisis de retención
description: Mida cuántos usuarios siguen usando el producto.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '1262'
ht-degree: 97%

---

# Análisis de retención {#retention}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_retention_button"
>title="Retención"
>abstract="Mida cuántos usuarios siguen usando el producto."

<!-- markdownlint-enable MD034 -->

El análisis ![Retención](/help/assets/icons/Retention.svg) **[!UICONTROL Retención]** mide cómo los usuarios siguen usando su producto a lo largo del tiempo, lo que puede ayudarle a conocer si su producto se adecúa al mercado. El análisis contabiliza los usuarios en función de dos eventos importantes:

* Evento de inicio: el evento que se utiliza para calificar a los usuarios para incluirlos en el análisis.
* Evento de retorno: uno o más eventos en los que un usuario debe participar y que se contabilizan como usuario recurrente en el análisis.

En este análisis, el eje x del gráfico representa el tiempo desde el evento de inicio inicial de un usuario y el eje y representa el porcentaje de usuarios que participan en uno o más eventos de retorno. Puede ver tanto la retención como la cancelación en todas las duraciones, y las duraciones mostradas se pueden personalizar a través de la configuración de consulta. Debajo del gráfico, una tabla proporciona datos añadidos con la opción de mostrar cohortes individuales, que son un grupo de personas que realizaron el evento inicial en la misma fecha.

>[!VIDEO](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/retention)


## Casos de uso

Los casos de uso de este análisis incluyen:

* **Análisis de cohorte**: agrupe a los usuarios en cohortes en función de las acciones que realicen, como suscripciones o compras. Puede comparar el rendimiento de estos grupos y determinar cómo abordar la mejora de la experiencia de usuario de cada grupo.
* **Adecuación del producto al mercado**: mida el uso regular del producto y visualícelo como curvas de retención. Una mayor retención significa una mayor adecuación del producto al mercado y el lugar donde la curva se aplana indica cuánto tiempo se tarda en lograr la adecuación. Visualice este análisis a nivel general o desglóselo por funciones de producto individuales para obtener información más detallada.
* **Análisis del servicio de suscripción**: si el producto emplea una suscripción u otro tipo de modelo de ingresos recurrentes, puede ver el porcentaje de usuarios que aprovechan al máximo el producto. Puede identificar determinadas cualidades y comportamientos que muestran estos usuarios.
* **Participación del usuario**: evalúe cómo determinados tipos de usuarios interactúan con su producto y compare la frecuencia con la que vuelven. Un segmento determinado con una retención menor que otros puede proporcionarle información para mejorar las posibles experiencias negativas que puedan tener.

## Interfaz

Consulte [Interfaz](../overview.md#interface) para obtener información general sobre la interfaz de análisis guiado. Las siguientes configuraciones son específicas de este análisis:

### Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **[!UICONTROL Evento de inicio]**: los criterios del evento en el que un usuario debe participar para optar a la inclusión en su análisis. Los usuarios que participan en el evento de inicio se contabilizan en la columna &quot;Usuarios&quot; de la tabla. Este evento sirve como denominador para las tasas de retención mostradas. Se admite un evento y se pueden aplicar filtros de propiedad según sea necesario. De forma predeterminada, los eventos de inicio y retorno están vinculados, lo que significa que un usuario debe realizar el evento seleccionado una vez para ser incluido en la cohorte y, a continuación, otra vez para ser contabilizado como usuario recurrente. En el menú Más, puede desvincular los eventos de inicio y retorno si desea que la acción de retorno sea diferente de la acción de inclusión.
* **[!UICONTROL Eventos de retorno]**: los criterios del evento en el que un usuario debe participar para contabilizarse como usuario recurrente en los intervalos de duración. Puede seleccionar hasta tres eventos de retorno para comparar la retención.
* **[!UICONTROL Contabilizado como]**: método de contabilización que desea aplicar a los eventos seleccionados. Las opciones incluyen: 
   * **[!UICONTROL Métrica]**: muestre el número de [!UICONTROL usuarios] o el [!UICONTROL porcentaje de usuarios] retenidos. El denominador para el porcentaje de usuarios retenidos es el de los usuarios incluidos para la cohorte y es el mismo en todos los intervalos de duración.
   * **[!UICONTROL Recurrente]**: le permite controlar cómo se contabilizan los usuarios recurrentes. Las opciones incluyen: 
      * **[!UICONTROL A partir de]**: a menudo denominada retención &quot;sin límite&quot;, esta opción contabiliza un usuario si regresa en la duración especificada o después de ella. Por ejemplo, el día 7 o en cualquier momento después del día 7. Esta opción es útil para mostrar cómo los usuarios siguen participando y, como resultado, genera una curva de retención más suave.
      * **[!UICONTROL Exactamente el]**: a menudo denominada retención &quot;limitada&quot;, esta opción contabiliza a un usuario si regresa exactamente en la duración especificada. Por ejemplo, el día 7 exactamente. Esta opción es útil para mostrar cómo los usuarios regresan dentro de lapsos de tiempo específicos y genera una curva de retención con más ondulación como resultado. Nota: El análisis de cohorte en Analysis Workspace utiliza el recuento &quot;exactamente el&quot; como base para su análisis.
   * **[!UICONTROL Cada]**: el período de tiempo que desea que tenga cada intervalo de duración. Las opciones incluyen: 
      * **[!UICONTROL Día/Semana/Mes]**: las opciones disponibles dependen del intervalo de fechas seleccionado. Estas opciones son idénticas a la configuración de **[!UICONTROL Intervalo]** cuando se selecciona el intervalo de fechas y actualiza esa configuración automáticamente.
      * **[!UICONTROL Secciones personalizadas]**: esta opción solo está disponible para la configuración &quot;En cada&quot;. Permite contabilizar usuarios en un periodo de tiempo mayor; por ejemplo, del día 7 al 10, en lugar de solo el día 7.
   * **[!UICONTROL Configuración de la duración]**: permite controlar los intervalos de duración que se muestran en el gráfico y la tabla. Una duración es el período de tiempo después del evento de inicio en el que se ha producido el evento de retorno. Nota: Los usuarios que cumplen los requisitos para los intervalos de duración se basan en el tiempo transcurrido, no en los días del calendario. Por ejemplo, si un usuario cumple los requisitos para un evento a las 11:55 p. m. del 6 de septiembre y luego cumple los requisitos para un evento de retorno a las 12:05 a. m. del 7 de septiembre, no aparecerá en el bloque de duración de 1 día. Deberán transcurrir 24 horas completas para que el usuario pueda optar al intervalo de duración de 1 día. Los intervalos de duración disponibles dependen del intervalo de fechas que establezca.
      * **[!UICONTROL Duraciones automáticas]** define automáticamente los intervalos de duración en función de la longitud del intervalo de fechas y de la proximidad al día actual en que se encuentre el intervalo de fechas.
      * **[!UICONTROL Duraciones personalizadas]** le permiten personalizar los intervalos de duración que se muestran en el gráfico y la tabla.
* **[!UICONTROL Segmentos]**: los segmentos que desea medir. Cada segmento seleccionado añadir una fila a la tabla de cohorte. Se pueden incluir hasta tres segmentos.

### Configuración del gráfico

El análisis [!UICONTROL Retención] ofrece la siguiente configuración de gráfico, que se puede ajustar en el menú situado encima del gráfico:

* **[!UICONTROL Tipo de gráfico]**: el tipo de visualización que desea utilizar. Las opciones incluyen [!UICONTROL Barra] y [!UICONTROL Línea].

### Intervalo de fechas

El intervalo de fechas deseado para el análisis. Esta configuración consta de dos componentes:

* **[!UICONTROL Intervalo]**: la granularidad de la fecha según la cual desea ver los datos de retención. Las opciones válidas son Diario, Semanal y Mensual. El mismo intervalo de fechas puede tener diferentes intervalos, lo que afecta a las opciones del intervalo de duración.
* **[!UICONTROL Fecha]**: la fecha de inicio y finalización. Los ajustes preestablecidos de intervalo de fechas móviles y los intervalos personalizados guardados anteriormente están disponibles para su comodidad, o puede utilizar el selector de calendario para elegir un intervalo de fechas fijo.

Si selecciona un intervalo de fechas próximo al día actual, no se incluirán los usuarios que inicialmente participan demasiado cerca del día actual. Este análisis siempre ofrece a todos los usuarios la oportunidad de ser incluidos en todos los intervalos de duración. Un mensaje debajo del selector de calendario proporciona información sobre el intervalo de fechas en el que los usuarios interactúan y el intervalo que se reserva únicamente para los usuarios recurrentes:

* **[!UICONTROL Análisis de usuarios que realizaron el evento de inicio en [Intervalo de fechas]]**: si un usuario participa en el evento dentro de este intervalo de fechas, se incluye en el análisis. Este intervalo de fechas garantiza a todos los usuarios tiempo suficiente para optar a todos los intervalos de duración. Este intervalo de fechas puede ser diferente al seleccionado si está cerca del día actual.
* **[!UICONTROL Los datos del [intervalo de fecha] están reservados para completar el análisis]**: si un usuario se involucra por primera vez dentro de este período, **no** se incluirá en el análisis. En el caso de los intervalos de fechas recientes, estos usuarios no tendrían la oportunidad de cumplir los requisitos de todos los intervalos de duración. En el caso de los intervalos de fechas anteriores, estos usuarios estaban activos fuera del intervalo de fechas seleccionado.

<!--
## Example

See below for an example of the analysis.

![Retention](../assets/retention.png)

-->