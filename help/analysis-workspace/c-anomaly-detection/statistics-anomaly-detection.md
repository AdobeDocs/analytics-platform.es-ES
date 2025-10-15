---
description: Descubra qué técnicas estadísticas se utilizan para identificar anomalías.
title: Técnicas Estadísticas Utilizadas En La Detección De Anomalías
feature: Anomaly Detection
exl-id: 7165e7a1-a04f-450e-bffd-e329adac6903
role: User
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 36%

---

# Técnicas estadísticas

La detección de anomalías de Analysis Workspace utiliza una serie de técnicas estadísticas avanzadas para determinar si una observación debe considerarse como anómala o no.

En función de la granularidad de fecha utilizada en el informe, se utilizan 3 técnicas estadísticas distintas: específicamente para la detección de anomalías horarias, diarias, semanales/mensuales. Cada técnica estadística se enumera a continuación.

## Detección de anomalías para la granularidad diaria

Para los informes de granularidad diaria, el algoritmo considera distintos factores importantes para ofrecer los resultados más precisos posibles. En primer lugar, el algoritmo determina qué tipo de modelo se aplica en función de los datos disponibles que el algoritmo selecciona entre una de las dos clases: un modelo basado en series temporales o un modelo de detección de externos (llamado segmentación funcional).

La selección del modelo de serie temporal se basa en las siguientes combinaciones para el tipo de error, tendencia y estacionalidad (ETS), tal como lo describe [Hyndman y cols. (2008)](https://idp.springer.com/authorize?response_type=cookie&client_id=springerlink&redirect_uri=https%3A%2F%2Flink.springer.com%2Fbook%2F10.1007%2F978-3-540-71918-2). Específicamente, el algoritmo intenta las siguientes combinaciones:

1. ANA (error aditivo, sin tendencia, estacionalidad aditiva)
1. AAA (error aditivo, tendencia aditiva, estacionalidad aditiva)
1. MNM (error multiplicativo, sin tendencia, estacionalidad multiplicativa)
1. ENM (error multiplicativo, sin tendencia, estacionalidad aditiva)
1. AAN (error aditivo, tendencia aditiva, sin estacionalidad)

El algoritmo prueba la idoneidad de cada una de estas combinaciones seleccionando la que presenta el mejor porcentaje absoluto medio de error (MAPE). Sin embargo, si el MAPE del mejor modelo de serie temporal es mayor del 15 %, se aplica la segmentación funcional. Normalmente, los datos con un alto grado de repetición (por ejemplo, semana tras semana o mes tras mes) son los que mejor se ajustan a un modelo de serie temporal.

Después de la selección del modelo, el algoritmo ajusta los resultados en función de los festivos y la estacionalidad año tras año. En el caso de los festivos, el algoritmo comprueba si alguno de los siguientes festivos está presente en el intervalo de fechas de la creación de informes:

* Día de los Caídos
* Julio de 4
* Acción de Gracias
* Black Friday
* Cyber Monday
* Del 24 al 26 de diciembre
* Enero de 1
* Diciembre de 31

Estos festivos se han seleccionado en base a un análisis estadístico exhaustivo de muchos puntos de datos de clientes para identificar los festivos más relevantes en el mayor número de tendencias de clientes. Aunque la lista no es completa para todos los ciclos de cliente o de negocio, la aplicación de festivos mejora significativamente el rendimiento del algoritmo en general para casi todos los conjuntos de datos de clientes.

Una vez se ha seleccionado el modelo y se han identificado los festivos en el rango de fechas de generación de informes, el algoritmo se ejecuta de la siguiente manera:

1. Construya el periodo de referencia de la anomalía. Este periodo de referencia de anomalías incluye hasta 35 días antes del intervalo de fechas del sistema de informes y un intervalo de fechas equivalente 1 año antes. Se deben tener en cuenta los días bisiestos cuando sea necesario e incluyen cualquier festivo aplicable que pueda haberse producido en un día del calendario diferente el año anterior.
1. Comprueba si los festivos en el periodo actual (excluido el año anterior) son anómalos en función de los datos más recientes.
1. Si el festivo en el rango de fechas actual es anómalo, se ajusta el valor esperado y el intervalo de confianza del festivo actual teniendo en cuenta el festivo del año anterior (se tienen en cuenta 2 días antes y después). La corrección del festivo actual se basa en el error de porcentaje absoluto medio más bajo de:

   1. Efectos aditivos
   1. Efectos multiplicativos
   1. Diferencia interanual

Observe la drástica mejora en el rendimiento en el día de Navidad y en el día de Año Nuevo en el ejemplo siguiente:

![Gráficos de dos líneas que muestran cambios de rendimiento con y sin rendimiento de vacaciones.](assets/anomaly_statistics.png)

## Detección de anomalías para la granularidad horaria

Los datos horarios dependen del mismo método de algoritmo de serie temporal que el algoritmo de granularidad diaria. Sin embargo, se basa en gran medida en dos patrones de tendencia: el ciclo de 24 horas, así como el ciclo de fin de semana / día de la semana. Para capturar estos dos efectos estacionales, el algoritmo por hora crea dos modelos separados para un fin de semana y un día entre semana utilizando el mismo enfoque descrito anteriormente.

Los períodos de prueba para las tendencias horarias se basan en una ventana retrospectiva de 336 horas.

## Detección de anomalías para granularidades semanales y mensuales

Las tendencias semanales y mensuales no muestran las mismas tendencias semanales o diarias encontradas en las granularidades diarias o por hora, por lo que se utiliza un algoritmo independiente. Para la detección semanal y mensual, un enfoque de detección de casos atípicos de dos pasos se conoce como la prueba de Desviación Estudiantil Extrema Generalizada (GESD, por sus siglas en inglés). Esta prueba considera el número máximo de anomalías esperadas combinadas con el método de diagramas de cajas ajustado (un método no paramétrico para la detección de casos aparte) para determinar el número máximo de periféricos. Los dos pasos son:

1. Función de trazado de cajas ajustada: Esta función determina el número máximo de anomalías dados los datos de entrada.
1. Función GESD: Se aplica a los datos de entrada con la salida del paso 1.

A continuación, el paso de detección de anomalías por temporadas año a año y de festivos resta los datos del año anterior de los datos de este año. Y luego itera en los datos de nuevo usando el proceso de dos pasos anterior para verificar que las anomalías son adecuadas para la temporada. Cada una de estas granularidades utiliza un periodo de 15 de inclusión retrospectiva de la fecha del rango de generación de informes seleccionada (tanto 15 meses como 15 semanas) y un rango de fechas correspondiente 1 año anterior para aprendizaje.
