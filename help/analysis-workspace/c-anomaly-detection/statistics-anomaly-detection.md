---
description: Aprenda a identificar anomalías estadísticas con técnicas de detección de anomalías.
title: Técnicas Estadísticas Utilizadas En La Detección De Anomalías
feature: Anomaly Detection
exl-id: 7165e7a1-a04f-450e-bffd-e329adac6903
role: User
source-git-commit: f3c9a000ae5baa19cb5a6cf0e0343de3a9685b56
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 67%

---

# Técnicas estadísticas

La detección de anomalías de Analysis Workspace utiliza una serie de técnicas estadísticas avanzadas para determinar si una observación debe considerarse como anómala o no.

En función de la granularidad de fecha utilizada en el informe, se utilizan 3 técnicas estadísticas distintas: específicamente para la detección de anomalías horarias, diarias, semanales/mensuales. Cada técnica estadística se enumera a continuación.

## Detección de anomalías para la granularidad diaria

Para los informes de granularidad diaria, el algoritmo considera distintos factores importantes para ofrecer los resultados más precisos posibles. En primer lugar, el algoritmo determina qué tipo de modelo se aplica en función de los datos disponibles que el algoritmo selecciona entre una de las dos clases: un modelo basado en series temporales o un modelo de detección de externos (llamado segmentación funcional).

El modelo de selección de series temporales se basa en las siguientes combinaciones por tipo de error, tendencia o temporada (ETS) como se describe en [Hyndman et al. (2008)](https://idp.springer.com/authorize?response_type=cookie&client_id=springerlink&redirect_uri=https%3A%2F%2Flink.springer.com%2Fbook%2F10.1007%2F978-3-540-71918-2). En concreto, el algoritmo prueba las siguientes combinaciones:

1. ANA (error acumulativo, sin tendencia, temporada acumulativa)
1. AAA (error acumulativo, tendencia acumulativa, temporada acumulativa)
1. MNM (error multiplicativo, sin tendencia, temporada multiplicativa)
1. MNA (error multiplicativo, sin tendencia, temporada acumulativa)
1. AAN (error acumulativo, tendencia acumulativa, sin temporada)

El algoritmo prueba la idoneidad de cada una de estas combinaciones seleccionando la que presenta el mejor porcentaje absoluto medio de error (MAPE). Sin embargo, si el MAPE del mejor modelo de serie temporal es mayor del 15 %, se aplica la segmentación funcional. Normalmente, los datos con un alto grado de repetición (por ejemplo, semana tras semana o mes tras mes) son los que mejor se ajustan a un modelo de serie temporal.

Tras la selección de modelo, a continuación, el modelo ajusta los resultados en función de los festivos y las temporadas año a año. Durante las vacaciones, el algoritmo comprueba si alguno de los festivos está presente en el rango de fechas de la generación de informes:

* Día de los Caídos (solo EE. UU.)
* Julio de 4
* Acción de gracias (solo EE. UU.)
* Black Friday
* Ciberlunes
* 24 al 26 de diciembre
* Enero de 1
* Diciembre de 31

Estos festivos se han seleccionado en base a un análisis estadístico exhaustivo de muchos puntos de datos de clientes para identificar los festivos más relevantes en el mayor número de tendencias de clientes. Aunque la lista no es completa para todos los ciclos de cliente o de negocio, la aplicación de festivos mejora significativamente el rendimiento del algoritmo en general para casi todos los conjuntos de datos de clientes.

Una vez se ha seleccionado el modelo y se han identificado los festivos en el rango de fechas de generación de informes, el algoritmo se ejecuta de la siguiente manera:

1. Construya el periodo de referencia de la anomalía. Este periodo de referencia de anomalías incluye hasta 35 días antes del intervalo de fechas del sistema de informes y un intervalo de fechas equivalente 1 año antes. Se deben tener en cuenta los días bisiestos cuando sea necesario e incluyen cualquier festivo aplicable que pueda haberse producido en un día del calendario diferente el año anterior.
1. Comprueba si los festivos en el periodo actual (excluido el año anterior) son anómalos en función de los datos más recientes.
1. Si el festivo en el rango de fechas actual es anómalo, se ajusta el valor esperado y el intervalo de confianza del festivo actual teniendo en cuenta el festivo del año anterior (se tienen en cuenta 2 días antes y después). La corrección del festivo actual se basa en el error de porcentaje absoluto de la media más baja de:

   1. Efectos acumulativos
   1. Efectos multiplicativos
   1. Diferencia año a año

Observe la drástica mejora en el rendimiento en el día de Navidad y en el día de Año Nuevo en el ejemplo siguiente:

![Gráficos de dos líneas que muestran cambios de rendimiento con y sin rendimiento de vacaciones.](assets/anomaly_statistics.png)

## Detección de anomalías para la granularidad horaria

Los datos horarios dependen del mismo método de algoritmo de serie temporal que el algoritmo de granularidad diaria. Sin embargo, dependen en gran medida de dos patrones de tendencia: el ciclo de 24 horas, así como el ciclo de fin de semana/día laboral. Para capturar estos dos efectos de temporada, el algoritmo por horas construye dos modelos independientes para días de fin de semana y días laborables utilizando el mismo método detallado anteriormente.

Los plazos de aprendizaje de las tendencias horarias dependen de un plazo de retrospectiva de 336 horas.

## Detección de anomalías para granularidades semanales y mensuales

Las tendencias semanales y mensuales no muestran las mismas tendencias semanales o diarias que las granularidades por días u horas, por tanto, se utiliza un algoritmo independiente. Para la detección semanal y mensual, un enfoque de detección de casos atípicos de dos pasos se conoce como la prueba de Desviación Estudiantil Extrema Generalizada (GESD, por sus siglas en inglés). Esta prueba considera el número máximo de anomalías esperadas combinadas con el método de diagramas de cajas ajustado (un método no paramétrico para la detección de casos aparte) para determinar el número máximo de periféricos. Los dos pasos son:

1. Función de diagrama de cajas ajustado: esta función determina el número máximo de anomalías sobre los datos de entrada.
1. Función GESD: se aplica a los datos de entrada con el resultado del paso 1.

A continuación, el paso de detección de anomalías por temporadas año a año y de festivos resta los datos del año anterior de los datos de este año. Y luego itera en los datos de nuevo usando el proceso de dos pasos anterior para verificar que las anomalías son adecuadas para la temporada. Cada una de estas granularidades utiliza un periodo de 15 de inclusión retrospectiva de la fecha del rango de generación de informes seleccionada (tanto 15 meses como 15 semanas) y un rango de fechas correspondiente 1 año anterior para aprendizaje.
