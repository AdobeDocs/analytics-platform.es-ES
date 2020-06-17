---
description: La partición de tiempo toma la marca de hora de los aciertos recogidos y lo divide en dimensiones más significativas, como “Hora del día” o “Día de la semana”.
title: Dimensiones de partición de tiempo
uuid: c9fa7921-aa57-483c-b2f9-da55013ada17
translation-type: tm+mt
source-git-commit: 0c5bd5ce0b0ba4ba758a1ef1adf5a4a519e9cf8c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 100%

---


# Dimensiones de partición de tiempo

La partición de tiempo toma la marca de hora de los aciertos recogidos y lo divide en dimensiones más significativas, como “Hora del día” o “Día de la semana”.

Las dimensiones de partición de tiempo se basan en el huso horario del grupo de informes o del grupo de informes virtuales. Estas dimensiones están disponibles en Analysis Workspace y pueden ayudar a responder a las siguientes preguntas:

* En un rango de datos de gran volumen, ¿cuál es la hora del día más popular para que los visitantes accedan a mi sitio o aplicación?
* ¿Hay días de la semana u horas del día en que la conversión es mayor en mi sitio o aplicación?
* ¿Qué rendimiento tienen las ventas del fin de semana en comparación con las ventas en días laborables?
* ¿Cuándo genera mayor conversión una determinada campaña de marketing? ¿Por la mañana o por la tarde?

>[!NOTE] Las dimensiones de partición de tiempo solo están disponibles en Analysis Workspace. Para utilizar dimensiones de partición de tiempo en otras soluciones de análisis, puede implementar el [complemento getTimeParting](https://docs.adobe.com/content/help/es-ES/analytics/implementation/vars/plugins/gettimeparting.html).

Las dimensiones de partición de tiempo en Analysis Workspace incluyen:

| Dimensión | Valores de ejemplo |
|--- |--- |
| Hora del día | 0-23 |
| AM/PM | AM, PM |
| Día de la semana | Lunes, martes, miércoles, jueves, viernes, sábado, domingo |
| Fin de semana / Día de la semana | Fin de semana, día de la semana |
| Día del mes | 1-31 |
| Mes del año | Enero-Diciembre |
| Día del año | 1-366 |
| Trimestre del año | T1, T2, T3, T4 |
