---
title: Análisis de impacto del primer uso
description: Mida el impacto del uso de funciones por primera vez en indicadores clave.
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
exl-id: 2c512184-2d79-4c41-8229-a09e440179ea
role: User
source-git-commit: ad181b5ba3de1a038c661159a159d234da6c3edf
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 4%

---

# [!UICONTROL Análisis de impacto de primer uso]

El análisis ![PrimerUso](/help/assets/icons/FirstUse.svg) **[!UICONTROL Impacto en el primer uso]** muestra una comparación del rendimiento de los indicadores clave antes y después de que un usuario use una característica del producto por primera vez. El eje horizontal de este informe es un intervalo de tiempo relativo antes y después del evento, mientras que el eje vertical mide los indicadores clave deseados. Una barra vertical en medio del gráfico representa el día 0 para el momento en que un usuario determinado utiliza por primera vez una función. Dado que los usuarios no siempre adoptan funciones en el mismo día y que los despliegues pueden producirse potencialmente durante varios días, el día 0 puede significar algo diferente para cada usuario individual.

+++ Vídeo de demostración

>[!VIDEO](https://video.tv.adobe.com/v/3421661/?learn=on)

+++

![Impacto de primer uso](../assets/first-use-impact.png)


## Casos prácticos

Los casos de uso de este análisis incluyen:

* **Análisis de nuevas características**: si va a lanzar una nueva característica en su producto, puede comparar el rendimiento de los indicadores clave antes y después de que los usuarios se expusieran a esa nueva característica por primera vez.
* **Despliegues por fases**: dado que el análisis busca el primer uso de la característica en lugar de una fecha fija, este análisis es útil si se modifica gradualmente el despliegue de las características a lo largo del tiempo.
* **Análisis de la nueva versión del producto**: si va a lanzar una nueva versión de su producto, puede comparar el rendimiento de los indicadores clave antes y después de que los usuarios se expusieran a esa nueva versión por primera vez. Seleccione &quot;cualquier evento&quot; como primer evento de uso y fíltrelo a la propiedad Número de versión.
* **Mejoras en las características existentes**: si está realizando mejoras en una característica existente de su producto, puede comparar el rendimiento de los indicadores clave antes y después de que los usuarios se expusieran a esas nuevas mejoras por primera vez. Este análisis se puede realizar de una o varias formas según la instrumentación de las funciones.
   * Seleccione un evento que represente la mejora como evento de primer uso
   * Seleccione la fecha en la que empezaron a implementarse los cambios
   * Segmentar el análisis al grupo de personas expuestas a las mejoras
* **Eficacia de la campaña**: Cuando un usuario hace clic desde una campaña determinada, puede comparar el rendimiento de los indicadores clave antes y después de que el usuario interactuara con esa campaña.

## Interfaz

Consulte [Interfaz](../overview.md#interface) para obtener una descripción general de la interfaz de análisis guiado. Las siguientes configuraciones son específicas de este análisis:

### Carril de consulta

El carril de consulta permite configurar los siguientes componentes:

* **[!UICONTROL Vista]**: cambie entre este análisis y [Versión](release-impact.md).
* **[!UICONTROL Indicadores clave]**: Los eventos que desea medir por usuario. Cada indicador clave seleccionado se representa como una línea de color. Se agrega a la tabla una fila que representa el evento. Se pueden incluir hasta tres eventos.
* **[!UICONTROL Contado como]**: El método de conteo que desea aplicar a los eventos seleccionados. Las opciones incluyen [!UICONTROL Eventos por usuario], [!UICONTROL Eventos], [!UICONTROL Sesiones] y [!UICONTROL Usuarios].
* **[!UICONTROL Factores]**: Hay dos factores para este análisis:
   * **[!UICONTROL Fecha]**: ¿Hasta dónde quiere empezar a buscar la primera vez que se produjo el evento de uso?
   * **[!UICONTROL Evento]**: el evento en el que desea buscar el primer uso, para centrar el análisis.
* **[!UICONTROL Segmentos]**: El segmento que desea medir. El segmento seleccionado filtra los datos para centrarse únicamente en las personas que coinciden con los criterios del segmento. Para este análisis se admite un solo segmento.

### Ajustes del gráfico

El análisis [!UICONTROL Impacto de primer uso] ofrece la siguiente configuración de gráfico, que se puede ajustar en el menú situado encima del gráfico:

* **[!UICONTROL Tipo de gráfico]**: El tipo de visualización que desea utilizar. Las opciones incluyen Línea.

### Intervalo de fechas

Las selecciones de fecha en el análisis [!UICONTROL Primer uso del impacto] funcionan de manera diferente que otros análisis, ya que el análisis gira en torno a la fecha especificada en el carril de la consulta. Las opciones disponibles son las siguientes:

* **[!UICONTROL Intervalo]**: La granularidad de fecha por la que desea ver los datos de tendencias. Las opciones válidas incluyen [!UICONTROL Diario], [!UICONTROL Semanal], [!UICONTROL Mensual] y [!UICONTROL Trimestral]. Cambiar el intervalo afecta a las opciones disponibles para los periodos Antes y Después.
* **[!UICONTROL Antes y después del período]**: Cantidad de tiempo que se debe analizar antes y después del primer evento de uso especificado en el carril de consultas. Las opciones disponibles dependen de la selección de [!UICONTROL Intervalo].
