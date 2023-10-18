---
title: Tasas de retención
description: Mida cuántos usuarios siguen utilizando su producto.
feature: Guided Analysis
keywords: análisis de productos
source-git-commit: 74525c4ce9ad1fd3f3abf35a9d9cb2c521d23874
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 2%

---

# Tasas de retención

El **[!UICONTROL Tasas de retención]** La vista muestra el porcentaje de usuarios que regresan después de su participación inicial dentro del intervalo de fechas deseado. El eje horizontal representa el número de días desde la primera participación de un usuario. El eje vertical representa el porcentaje de usuarios que vuelven a interactuar.

Este análisis cuenta los usuarios en función de dos eventos importantes:

* La primera vez que un usuario participó en el evento dentro del intervalo de fechas
* La hora más reciente en la que un usuario participó con el evento dentro del intervalo de fechas analizado

El bloque de duración &quot;día 0&quot; representa la primera vez que un usuario interactúa con el evento y siempre es igual exactamente al 100 %. La cantidad de tiempo que transcurre entre la participación inicial y la participación de retorno determina dónde aparece el usuario.

* Si un usuario interactúa con el evento solo una vez durante el intervalo de fechas deseado (la participación inicial), solo aparece en el bloque de duración &quot;día 0&quot;.
* Si un usuario se involucra con el evento varios días después de cumplir los requisitos iniciales para la inclusión en el análisis, aparece en el último bloque de duración correspondiente y en todos los bloques de duración previos al mismo.
* Si un usuario se involucra con el evento muchas veces durante el intervalo de fechas configurado, solo se incluyen en el análisis los eventos primero y último.

## Casos prácticos

Los casos de uso para este tipo de vista incluyen:

* **Análisis de cohorte**: agrupe a los usuarios en cohortes en función de cualquier evento, como suscripciones o compras. Puede comparar la permanencia de estos grupos y determinar cómo abordar la mejora de la experiencia de usuario de ese grupo.
* **Análisis del servicio de suscripción**: Si su producto utiliza una suscripción u otro tipo de modelo de ingresos recurrentes, puede ver el porcentaje de usuarios que aprovechan al máximo su producto. Es más probable que aquellos que no utilizan su producto o servicio pierdan, lo que le permite identificar a esos usuarios y centrarse en ellos.
* **Participación del usuario**: evalúe cómo interactúan determinados tipos de usuarios con el producto y compare en paralelo la frecuencia con la que regresan. Un segmento determinado con una curva de retención más pronunciada que otros puede proporcionarle información sobre la mejora de posibles experiencias inferiores que podrían tener.

## Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **[!UICONTROL Evento de inicio y retorno]**: los criterios de evento con los que debe interactuar un usuario para cumplir los requisitos de inclusión en el análisis. Se admite un evento, pero puede incluir filtros de propiedad.
* **[!UICONTROL People]**: Los segmentos que desea medir. Cada segmento seleccionado agrega una fila a la tabla de cohorte. Se pueden incluir hasta tres segmentos.

## Ajustes del gráfico

El [!UICONTROL Tasas de retención] La vista ofrece la siguiente configuración de gráfico, que se puede ajustar en el menú situado encima del gráfico:

* **[!UICONTROL Métrica]**: Cómo desea medir los usuarios retenidos. Las opciones incluyen [!UICONTROL Usuarios retenidos] y [!UICONTROL Porcentaje de usuarios retenidos].
* **[!UICONTROL Tipo de gráfico]**: el tipo de visualización que desea utilizar. Las opciones incluyen [!UICONTROL Barra] y [!UICONTROL Línea].

## Configuración de duración

Permite controlar cómo muestra el análisis los usuarios según el número de días transcurridos.

* **[!UICONTROL Duraciones automáticas]**: establezca automáticamente las duraciones en función de la longitud del intervalo de fechas y de la proximidad al día actual en que se encuentre el intervalo de fechas.
* **[!UICONTROL Duraciones personalizadas]**: establezca manualmente los días transcurridos deseados. Puede establecer cuatro duraciones.

No puede establecer una duración superior al tiempo que tarda un usuario en interactuar con un evento y cumplir los requisitos del último bloque de duración antes de llegar al día actual. Por ejemplo, si la fecha actual es el 30 de septiembre y el intervalo de fechas configurado es del 1 de septiembre al 30 de septiembre, la duración máxima de este intervalo de fechas es de 14 días.

## Intervalo de fechas

El intervalo de fechas deseado para el análisis. Esta configuración consta de dos componentes:

* **[!UICONTROL Intervalo]**: La granularidad de fecha que desea ver en los datos de retención. Las opciones válidas incluyen Diario, Semanal, Mensual y Trimestral. El mismo intervalo de fechas puede tener diferentes intervalos, que afectan al establecimiento automático de la duración de los días.
* **[!UICONTROL Fecha]**: la fecha de inicio y finalización. Los ajustes preestablecidos de intervalo de fechas móviles y los intervalos personalizados guardados anteriormente están disponibles para su comodidad, o puede utilizar el selector de calendario para elegir un intervalo de fechas fijo.

Si selecciona un intervalo de fechas cercano al día actual, no se incluyen los usuarios que inicialmente interactúan demasiado cerca del día actual. Este análisis siempre ofrece a todos los usuarios la oportunidad de ser incluidos en todos los bloques de duración. Un mensaje debajo del selector de calendario proporciona información sobre el intervalo de fechas en el que los usuarios interactúan y el intervalo que se reserva solo para los usuarios que regresan:

* **Análisis de la primera [Intervalo de fecha] de la cohorte de [Intervalo de fechas]**: Si un usuario interactúa con el evento dentro de este intervalo de fechas, se incluye en el análisis. Este intervalo de fechas garantiza a todos los usuarios tiempo suficiente para cumplir los requisitos de todos los bloques de duración. Este intervalo de fechas puede ser diferente al seleccionado si está cerca del día actual.
* **La final [Intervalo de fecha] está reservado para completar el análisis**: Si un usuario se involucra con el evento por primera vez dentro de este intervalo, lo está **no** incluido en el análisis. Los usuarios que inicialmente interactúen con el evento dentro de este intervalo no tendrían la oportunidad de cumplir los requisitos para todos los bloques de duración o de encontrarse fuera del intervalo de fechas deseado.

## Tabla de cohorte

La tabla debajo del gráfico proporciona una vista agregada (similar a los datos del gráfico) y una tabla de cohorte completa. La tabla de cohorte completa proporciona detalles sobre cada intervalo de fecha individual y cuándo participan los usuarios.
