---
title: Análisis de retención
description: Mida cuántos usuarios siguen utilizando su producto.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: ad181b5ba3de1a038c661159a159d234da6c3edf
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 2%

---

# Análisis de retención

El análisis ![Retención](/help/assets/icons/Retention.svg) **[!UICONTROL Retención]** mide cómo los usuarios siguen usando tu producto a lo largo del tiempo, lo que puede ayudarte a comprender el ajuste del mercado de tu producto. El análisis cuenta los usuarios en función de dos eventos importantes:

* Evento Start: el evento utilizado para clasificar a los usuarios para incluirlos en el análisis.
* Evento de retorno: uno o más eventos con los que debe interactuar un usuario para contar como usuario que regresa en el análisis.

En este análisis, el eje x del gráfico representa el tiempo desde el evento de inicio inicial de un usuario y el eje y representa el porcentaje de usuarios que se relacionan con uno o más eventos de retorno. Puede ver tanto la retención como la pérdida en todas las duraciones, y las duraciones mostradas se pueden personalizar a través de la configuración de consulta. Debajo del gráfico, una tabla proporciona datos agregados con la opción de mostrar cohortes individuales, que son un grupo de personas que realizaron el evento de inicio en la misma fecha.

+++ Vídeo de demostración

>[!VIDEO](https://video.tv.adobe.com/v/3430503/?learn=on)

+++

![Retención](../assets/retention.png)

## Casos prácticos

Los casos de uso de este análisis incluyen:

* **Análisis de cohorte**: agrupe a los usuarios en cohortes en función de las acciones que realicen, como suscripciones o compras. Puede comparar el rendimiento de estos grupos y determinar cómo abordar la mejora de la experiencia de usuario de cada grupo.
* **Ajuste del mercado del producto**: mida el uso regular del producto y visualícelo como curvas de retención. Una mayor retención significa un mejor ajuste al mercado del producto, y el lugar donde la curva se aplana indica cuánto tiempo se tarda en alcanzar el ajuste. Vea este análisis a nivel general o desglose por funciones de producto individuales para obtener información más detallada.
* **Análisis del servicio de suscripción**: si el producto emplea una suscripción u otro tipo de modelo de ingresos recurrentes, puede ver el porcentaje de usuarios que aprovechan al máximo el producto. Puede identificar ciertas cualidades y comportamientos que muestran estos usuarios.
* **Participación del usuario**: Evalúe cómo se relacionan ciertos tipos de usuarios con su producto y compare en paralelo la frecuencia con la que regresan. Un segmento determinado con una retención menor que otros puede proporcionarle una perspectiva sobre la mejora de las posibles experiencias inferiores que podrían tener.

## Interfaz

Consulte [Interfaz](../overview.md#interface) para obtener una descripción general de la interfaz de análisis guiado. Las siguientes configuraciones son específicas de este análisis:

### Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **[!UICONTROL Evento de inicio]**: Los criterios de evento con los que debe interactuar un usuario para calificar para la inclusión en su análisis. Los usuarios que interactúan con el evento de inicio se cuentan en la columna &quot;Usuarios&quot; de la tabla. Este evento sirve como denominador para las tasas de retención mostradas. Se admite un evento y se pueden aplicar filtros de propiedad según sea necesario. De forma predeterminada, los eventos de inicio y retorno están vinculados, lo que significa que un usuario debe realizar el evento seleccionado una vez para incluirlo en la cohorte y, a continuación, volver a contarlo como usuario recurrente. En el menú Más, puede desvincular los eventos de inicio y retorno si desea que la acción de retorno sea diferente de la acción de inclusión.
* **[!UICONTROL Devolver eventos]**: Los criterios de evento con los que debe interactuar un usuario para contar como usuarios que regresan en los bloques de duración. Puede seleccionar hasta tres eventos de retorno para comparar la retención entre sí.
* **[!UICONTROL Contado como]**: El método de contabilización que desea aplicar a los usuarios retenidos. Las opciones incluyen: 
   * **[!UICONTROL Métrica]**: muestra el número de [!UICONTROL usuarios] o el [!UICONTROL porcentaje de usuarios] retenidos. El denominador para el porcentaje de usuarios retenidos es el de los usuarios incluidos para la cohorte y es el mismo en todos los bloques de duración.
   * **[!UICONTROL Devolución]**: Permite controlar cómo se cuentan los usuarios que regresan. Las opciones incluyen: 
      * **[!UICONTROL En o después de]**: a menudo denominada retención &quot;sin límites&quot;, esta opción cuenta un usuario si regresa en o después de la duración especificada. Por ejemplo, en el día 7 o en cualquier momento después del día 7. Esta opción es útil para mostrar cómo los usuarios siguen interactuando y, como resultado, genera una curva de retención más suave.
      * **[!UICONTROL En exactamente]**: a menudo denominada retención &quot;limitada&quot;, esta opción cuenta un usuario si regresa exactamente en la duración especificada. Por ejemplo, el día 7 exactamente. Esta opción es útil para mostrar cómo los usuarios regresan dentro de marcos de tiempo específicos y genera una curva de retención con más ondulación como resultado. Nota: El análisis de cohorte en Analysis Workspace utiliza el recuento &quot;exactamente&quot; como base para su análisis.
   * **[!UICONTROL Each]**: El período de tiempo que desea que sea cada período de duración. Las opciones incluyen: 
      * **[!UICONTROL Día/Semana/Mes]**: las opciones disponibles dependen del intervalo de fechas seleccionado. Estas opciones son idénticas a la configuración de **[!UICONTROL Intervalo]** al seleccionar el intervalo de fechas y actualiza esa configuración automáticamente.
      * **[!UICONTROL Corchetes personalizados]**: esta opción solo está disponible para la configuración &quot;En cada uno&quot;. Permite contar usuarios en un periodo de tiempo mayor; por ejemplo, del día 7 al 10, en lugar de solo el día 7.
   * **[!UICONTROL Configuración de duración]**: permite controlar los bloques de duración que se muestran en el gráfico y la tabla. Una duración es el período de tiempo después del evento de inicio en el que se produjo el evento de retorno. Nota: Los usuarios que cumplen los requisitos para los bloques de duración se basan en el tiempo transcurrido, no en los días del calendario. Por ejemplo, si un usuario cumple los requisitos para un evento a las 23:55 del 6 de septiembre y luego cumple los requisitos para un evento de retorno a las 12:05 del 7 de septiembre, no aparecerá en el bloque de duración de 1 día. Deben transcurrir 24 horas completas antes de que el usuario cumpla los requisitos del bloque de duración de 1 día. Los bloques de duración disponibles dependen del intervalo de fechas que establezca.
      * **[!UICONTROL Duraciones automáticas]** define automáticamente los bloques de duración en función de la longitud del intervalo de fechas y de la proximidad al día actual en que se encuentre el intervalo de fechas.
      * **[!UICONTROL Duraciones personalizadas]** le permiten personalizar los cuatro bloques de duración que se muestran en el gráfico y la tabla.
* **[!UICONTROL Segmentos]**: los segmentos que desea medir. Cada segmento seleccionado agrega una fila a la tabla de cohorte. Se pueden incluir hasta tres segmentos.

### Ajustes del gráfico

El análisis [!UICONTROL Retención] ofrece la siguiente configuración de gráfico, que se puede ajustar en el menú situado encima del gráfico:

* **[!UICONTROL Tipo de gráfico]**: El tipo de visualización que desea utilizar. Las opciones incluyen [!UICONTROL Barra] y [!UICONTROL Línea].

### Intervalo de fechas

El intervalo de fechas deseado para el análisis. Esta configuración consta de dos componentes:

* **[!UICONTROL Intervalo]**: La granularidad de fecha según la cual desea ver los datos de retención. Las opciones válidas son Daily, Weekly y Monthly. El mismo intervalo de fechas puede tener diferentes intervalos, lo que afecta a las opciones del bloque de duración.
* **[!UICONTROL Fecha]**: La fecha de inicio y finalización. Los ajustes preestablecidos de intervalo de fechas móviles y los intervalos personalizados guardados anteriormente están disponibles para su comodidad, o puede utilizar el selector de calendario para elegir un intervalo de fechas fijo.

Si selecciona un intervalo de fechas cercano al día actual, no se incluyen los usuarios que inicialmente interactúan demasiado cerca del día actual. Este análisis siempre ofrece a todos los usuarios la oportunidad de ser incluidos en todos los bloques de duración. Un mensaje debajo del selector de calendario proporciona información sobre el intervalo de fechas en el que los usuarios interactúan y el intervalo que se reserva únicamente para los usuarios que regresan:

* **[!UICONTROL Análisis de usuarios que realizaron el evento de inicio en [Intervalo de fecha]]**: Si un usuario se involucra con el evento dentro de este intervalo de fecha, se incluyen en el análisis. Este intervalo de fechas garantiza a todos los usuarios tiempo suficiente para cumplir los requisitos de todos los bloques de duración. Este intervalo de fechas puede ser diferente al seleccionado si está cerca del día actual.
* **[!UICONTROL Los datos del [intervalo de fecha] están reservados para completar el análisis]**: Si un usuario se involucra por primera vez dentro de este período, **no** se incluyen en el análisis. Para intervalos de fechas recientes, estos usuarios no tendrían la oportunidad de cumplir los requisitos de todos los bloques de duración. Para intervalos de fechas anteriores, estos usuarios estaban activos fuera del intervalo de fechas seleccionado.
