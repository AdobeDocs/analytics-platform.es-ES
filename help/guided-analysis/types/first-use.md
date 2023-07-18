---
title: Vista de primer uso
description: Medir el impacto del uso de funciones por primera vez en indicadores clave.
feature: Guided Analysis
source-git-commit: 4cae5968e2ae1b6048522b9eb065d4b6e2272938
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 3%

---

# [!UICONTROL Primer uso] vista

El **[!UICONTROL Primer uso]** La vista muestra una comparación del rendimiento de los indicadores clave antes y después de que un usuario utilice una función de producto por primera vez. El eje horizontal de este informe es un intervalo de tiempo relativo antes y después del evento, mientras que el eje vertical mide los indicadores clave deseados. Una barra vertical en medio del gráfico representa el día 0 para el momento en que un usuario determinado utiliza por primera vez una función. Dado que los usuarios no siempre adoptan las funciones el mismo día y que los despliegues pueden producirse durante varios días, el día 0 significará algo diferente para cada usuario individual.

>[!VIDEO](https://video.tv.adobe.com/v/3421661/?learn=on)

## Casos prácticos

Los casos de uso para este tipo de vista incluyen:

* **Análisis de nuevas funciones**: si va a lanzar una nueva función dentro del producto, puede comparar el rendimiento de los indicadores clave antes y después de que los usuarios se expusieran a esa nueva función por primera vez.
* **Despliegues por fases**: Debido a que el análisis busca el primer uso de la función en lugar de una fecha fija, esta vista es especialmente útil si despliega las funciones gradualmente durante un periodo de tiempo.
* **Análisis de la nueva versión del producto**: si va a lanzar una nueva versión de su producto, puede comparar el rendimiento de los indicadores clave antes y después de que los usuarios se expusieran a esa nueva versión por primera vez. Seleccione &quot;cualquier evento&quot; como primer evento de uso y fíltrelo a la propiedad Número de versión.
* **Mejoras de funciones existentes**: si está realizando mejoras en una función existente de su producto, puede comparar el rendimiento de los indicadores clave antes y después de que los usuarios se expusieran a esas nuevas mejoras por primera vez. Este análisis se puede realizar de varias formas en función de la instrumentación de las funciones. 1) Seleccione un evento que represente la mejora como su primer evento de uso o 2) Seleccione la fecha en la que los cambios empezaron a implementarse o 3) Segmente el análisis al grupo de personas expuestas a las mejoras.
* **Eficacia de campañas**: Cuando un usuario hace clic desde una campaña determinada, puede comparar el rendimiento de los indicadores clave antes y después de que el usuario interactuara con esa campaña.

## Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **[!UICONTROL Indicadores clave]**: los eventos que desea medir por usuario. Cada indicador clave seleccionado se representa como una línea de color. Se agrega a la tabla una fila que representa el evento. Se pueden incluir hasta tres eventos.
* **[!UICONTROL Factores]**: Existen dos factores para esta vista:
   * **[!UICONTROL Fecha]**: Hasta dónde desea empezar a buscar el primer evento de uso que se produjo.
   * **[!UICONTROL Evento]**: evento en el que desea buscar el primer uso para centrar el análisis.
* **[!UICONTROL People]**: El segmento que desea medir. El segmento seleccionado filtra los datos para centrarse únicamente en las personas que coinciden con los criterios del segmento.

## Ajustes del gráfico

La vista Primer uso ofrece la siguiente configuración de gráfico, que se puede ajustar en el menú situado encima del gráfico:

* **[!UICONTROL Métrica]**: La métrica que desea medir. Las opciones incluyen [!UICONTROL Eventos por usuario], [!UICONTROL Eventos], [!UICONTROL Sesiones], y [!UICONTROL Usuarios].
* **[!UICONTROL Tipo de gráfico]**: el tipo de visualización que desea utilizar. Las opciones incluyen Línea.

## Intervalo de fechas

Las selecciones de fecha en Análisis de impacto funcionan de forma diferente a otros tipos de análisis, ya que el análisis gira en torno a la fecha especificada en el carril de consulta. Las opciones disponibles son las siguientes:

* **[!UICONTROL Intervalo]**: La granularidad de fecha por la que desea ver los datos de tendencias. Las opciones válidas incluyen [!UICONTROL Diario], [!UICONTROL Semanalmente], [!UICONTROL Mensual], y [!UICONTROL Trimestral]. Cambiar el intervalo afecta a las opciones disponibles para los periodos Antes y Después.
* **[!UICONTROL Antes y después del período]**: Cantidad de tiempo que se debe analizar antes y después del primer evento de uso especificado en el carril de consultas. Las opciones disponibles dependen de la variable [!UICONTROL Intervalo] selección.
