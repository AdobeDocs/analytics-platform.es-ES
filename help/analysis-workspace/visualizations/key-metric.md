---
description: Utilice la visualización de resumen de métricas clave para comparar el rendimiento de las métricas en dos líneas de tiempo.
title: Resumen de métricas clave
feature: Visualizations
role: User, Admin
exl-id: c74e77ff-15d6-48f1-a845-85bdf3444c3a
source-git-commit: 6238a3b2239a20aaedbec5e5603d0c72bb4ae463
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 6%

---

# Resumen de métricas clave

>[!NOTE]
>
>Actualmente, esta funcionalidad está en [prueba limitada](/help/release-notes/releases.md).

La variable [!UICONTROL Resumen de métricas clave] la visualización le permite ver las tendencias de una métrica importante dentro de un solo intervalo de tiempo. También le permite comparar el rendimiento de las métricas en dos intervalos de tiempo. Proporciona las ventajas de varias visualizaciones combinadas en una sola visualización:

* **[!UICONTROL Línea]** visualizaciones que muestran la tendencia de la métrica para los intervalos de fechas principales y de comparación

* **[!UICONTROL Cambio de porcentaje de resumen]** que muestra el aumento o la disminución de la métrica entre los intervalos de fechas principal y de comparación

* Valor total actual ([!UICONTROL **número de resumen**]) para la métrica

## Casos prácticos

Esta visualización aborda una variedad de casos de uso comunes, entre los que se incluyen:

* Un analista tratando de entender cómo se vio la creación de oportunidades este mes comparado con el mismo periodo del año pasado.

* Un especialista en marketing que explora cómo la generación de posibles clientes para un tipo de posible cliente específico ha cambiado de este mes a último.

* Un ejecutivo que quiere entender cómo cambiaron las nuevas reservas de este trimestre al último trimestre.

## Configurar el resumen de métricas clave

1. Arrastre el **[!UICONTROL Resumen de métricas clave]** visualización desde el **[!UICONTROL Visualizaciones]** del carril izquierdo en un panel.

1. Configure la visualización seleccionando una métrica, un intervalo de fechas principal, un intervalo de fechas de comparación y un segmento (si lo desea):

   ![](assets/key-metric-config.png)

   | Configuración | Definición |
   | --- | --- |
   | **[!UICONTROL Métrica]** | Seleccione la métrica que desee examinar. Todas las métricas son compatibles. |
   | **[!UICONTROL Intervalo de fechas principal]** | El intervalo de fechas actual para la tabla improvisada. |
   | **[!UICONTROL Intervalo de fechas de comparación]** | El intervalo de fechas en el que se desea comparar el intervalo de fechas principal. |
   | **[!UICONTROL Segmento (opcional)]** | Cualquier segmento que le interese específicamente para este resumen. |

   {style=&quot;table-layout:auto&quot;}

1. Haga clic en **[!UICONTROL Generar]**.

## Ver el resultado

![](assets/key-metric-output.png)

Tenga en cuenta:

* La variable **[!UICONTROL Período anterior]** el gráfico de líneas (siempre mostrado en gris) corresponde a la variable **[!UICONTROL Intervalo de fechas de comparación]** en el paso de configuración.

* Si no se especifica un intervalo de fechas de comparación durante la configuración o está oculto en la configuración de visualización, solo se muestra el gráfico de líneas del intervalo de fechas principal. El cambio de resumen estará oculto.

* Desde aquí, puede pasar el ratón por encima de los gráficos de líneas para ver las estadísticas de los días individuales:

![](assets/key-metric-output2.png)

## Configuración de visualización

El resumen de métricas clave ofrece varias configuraciones flexibles para permitir mejores informes y comunicación de métricas importantes. Se puede acceder a la configuración a través del icono de engranaje en la esquina superior derecha de la visualización.

![](assets/key-metric-settings.png)

| Configuración | Descripción |
| --- | --- |
| **[!UICONTROL Resaltar cambio porcentual]** | Mostrar el cambio de resumen en negrita destacado en el centro de la visualización |
| **[!UICONTROL Valor numérico de énfasis]** | Mostrar el número de resumen en negrita destacado en el centro de la visualización |
| **[!UICONTROL Leyenda visible]** | Mostrar u ocultar la leyenda en la parte inferior de la visualización |
| **[!UICONTROL Mostrar anotaciones]** | Mostrar u ocultar anotaciones agregadas por un administrador |
| **[!UICONTROL Mostrar minigráficos]** | Mostrar u ocultar gráficos de líneas en la parte inferior del gráfico. Cuando esté oculta, la leyenda cambiará para no hacer referencia visual a las líneas |
| **[!UICONTROL Mostrar mínimo y máximo en minigráficos]** | Mostrar u ocultar valores mínimos y máximos en gráficos de líneas principales y de comparación |
| **[!UICONTROL Mostrar comparación]** | Mostrar u ocultar datos de comparación. Cuando está oculto, el gráfico de líneas de comparación y los objetos de cambio de resumen quedan ocultos. |
| **[!UICONTROL Mostrar número total]** | Mostrar u ocultar número de resumen |
| **[!UICONTROL Mostrar diferencia sin procesar]** | Mostrar u ocultar la diferencia sin procesar entre el valor total de la métrica en el intervalo de fechas principal y el intervalo de fechas secundario |
| **[!UICONTROL Valor abreviado]** | Abreviar los valores numéricos para simplificar las perspectivas comunicadas (por ejemplo, 20 000 -> 20 000) |

## Editar visualización

Después de crear la visualización, aún puede editar la configuración original.

1. Haga clic en el icono de lápiz en la esquina superior derecha de la visualización (junto al icono de engranaje de configuración).

   ![](assets/edit-icon.png)

   Ahora volverá a la vista de configuración original.

1. Cambie la métrica, el intervalo de fechas principal, el intervalo de fechas de comparación o el segmento como prefiera.
