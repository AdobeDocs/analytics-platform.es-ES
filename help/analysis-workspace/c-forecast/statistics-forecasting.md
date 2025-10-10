---
description: Obtenga información sobre cómo la previsión en Analysis Workspace utiliza una serie de técnicas estadísticas avanzadas para determinar los valores de previsión.
title: Técnicas estadísticas
feature: Visualizations
role: User
exl-id: f042a6dd-6af5-4bdd-afc9-07546d8ded6e
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 6%

---

# Técnicas estadísticas

El servicio de pronóstico actualmente es compatible con Prophet y se ha demostrado que funciona de manera eficiente y confiable para la mayoría de los datos. Prophet es un paquete de pronóstico de código abierto ampliamente utilizado desarrollado por Meta. Descompone los datos en componentes de tendencias, temporadas y eventos. El modelo Profeta es eficiente y se adapta bien a muchas aplicaciones de pronóstico. Además, el modelo funciona de forma robusta contra periféricos y datos faltantes.

En el futuro, hay planes para seleccionar modelos basados en heurística, por ejemplo, elija Proceso gaussiano aproximado en línea para transmitir datos o NeuralProphet cuando los usuarios especifiquen la mejor precisión de pronóstico y puedan tolerar un tiempo de espera más largo.

El servicio reduce automáticamente la escala de los datos cuando hay demasiados puntos de datos, para garantizar el tiempo de respuesta. El tiempo de respuesta de destino se establece en ~3 segundos. Actualmente, cuando el número de puntos de datos supera los 5500, los datos de las series temporales se reducen de forma adaptativa en función de la longitud de los datos. El resultado se vuelve a convertir a la frecuencia de datos original, por lo que el proceso de muestreo adaptable no afectará a las experiencias de los usuarios.

Los efectos festivos se tienen en cuenta cuando se dispone de datos correspondientes a varios años. Actualmente, la lista de días festivos en consideración es:

* Día de Martin Luther King
* Día del Presidente
* Día de los Caídos (solo EE. UU.)
* Julio de 4
* Acción de gracias (solo EE. UU.)
* Black Friday
* Ciberlunes
* Navidad

El servicio también puede eliminar una anomalía simple (periféricos), por ejemplo, eliminando puntos de datos que estén fuera del intervalo de seis sigmas. Esto no está habilitado de forma predeterminada, ya que se supone que todos los puntos de datos son válidos. Las anomalías pueden tener una influencia negativa en la calidad del modelo, aunque el modelo Profeta sea resistente a periféricos en general.

El servicio acepta configuraciones de temporalidad especificadas por el usuario, por ejemplo temporadas diarias y semanales. De lo contrario, el modelo selecciona automáticamente la estacionalidad. Para diferentes granularidades de datos, el servicio utiliza diferentes longitudes de datos históricos para crear modelos de previsión. Por ejemplo, para los datos diarios, extrae más de un año de datos (si está disponible). Para los datos por hora, extrae ocho semanas de datos (si están disponibles). La extracción de datos puede llevar mucho tiempo y, a veces, causa un tiempo de espera más largo.

Los datos históricos necesarios para diferentes granularidades de tiempo:

| Granularidad | Datos históricos requeridos |
|---|--:|
| Minuto | 3 días |
| Hora | 2 semanas |
| Día | 8 semanas |
| Semana | 2 años |
| Mes | 2 años |
| Trimestre | 8 trimestres |
| Año | 8 años |


El resultado de la previsión para cada tiempo especificado viene con un intervalo de predicción (definido por el límite inferior y superior), que se espera que contenga el valor observado futuro el 95 % del tiempo, a menudo, denominado intervalo de confianza. No hay límite en cuanto a hasta dónde puede prever el servicio en el futuro. Sin embargo, la incertidumbre en las previsiones aumenta con las fechas futuras, lo que se refleja en un intervalo de predicción más amplio a lo largo del tiempo.

El servicio no realiza suposiciones sobre los datos de usuario. Por ejemplo, el servicio no supone que los datos no sean negativos. Esto significa que las predicciones y/o sus límites pueden ser negativos, si los datos muestran una fuerte tendencia a la baja, aunque todos los puntos de datos observados no sean negativos.


## Referencias

1. Taylor, Sean J. y Benjamin Letham: *Pronóstico a escala.* El Estadístico Estadounidense 72.1 (2018): 37-45.
1. Triebe, Oskar, et al.: *Neuralprophet: pronóstico explicable a escala.* arXiv preimpresión arXiv:2111.15397(2021).
1. Zhang y Arbor: *Detección de anomalías en series de tiempo.* #18/057883 de solicitud de patente de EE. UU.
