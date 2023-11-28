---
title: Visualización de anotaciones
description: Cómo ver anotaciones en Espacio de trabajo.
role: User, Admin
feature: Components
exl-id: c0e4fb37-b20c-463c-b29a-310ca3adb2c7
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 86%

---

# Visualización de anotaciones

Las anotaciones se manifiestan de forma ligeramente diferente, en función de si abarcan un solo día o un intervalo de fechas.

## Visualización de anotaciones en gráficos de líneas o tablas

| Fecha | Aspecto |
| --- | --- |
| **Día único** | ![Visualización de gráfico de líneas con anotación resaltada](assets/single-day.png)<p>Cuando pasa el ratón por encima de la anotación, puede ver sus detalles, puede editarla seleccionando el icono de la pluma o puede eliminarla:<p> ![Detalles de anotaciones con la opción para editar o eliminar la anotación.](assets/hover.png) |
| **Intervalo de fechas** | El icono cambia y, cuando pasa el ratón por encima, aparece el intervalo de fechas.<p>![Icono de anotación de intervalo de fechas](assets/multi-day.png)<p>Cuando lo selecciona en el gráfico de líneas, aparecen los metadatos de la anotación y puede editarlos o eliminarlos:![](assets/multi-hover.png)<p>En una tabla, aparece un icono en cada fecha del intervalo de fechas.<p>![](assets/multi-day-table.png) |
| **Anotaciones superpuestas** | En los días que tengan más de una anotación vinculada a ellos, el icono será de color gris.<p>![Detalles de anotaciones superpuestas  ](assets/grey.png)<p>Cuando pasa el ratón por encima del icono gris, aparecen todas las anotaciones superpuestas:<p>![](assets/overlap.png) |

{style="table-layout:auto"}

## Visualización de anotaciones en un archivo .pdf

Dado que no puede pasar el ratón sobre los iconos de un archivo .pdf, este archivo (tras la exportación) proporciona notas de explicaciones en la parte inferior de un panel. Vea el siguiente ejemplo:

![Vista resaltada de un archivo .pdf que muestra explicaciones de anotaciones.](assets/ann-pdf.png)

## Ver anotaciones con datos de tendencias

A veces, las anotaciones se muestran con datos sin tendencias, pero vinculados a una dimensión específica. En ese caso, solo aparecen en una anotación de resumen en la esquina inferior derecha. Vea el siguiente ejemplo:

![](assets/non-date.png)

El gráfico de resumen aparece en todos los tipos de visualización de la esquina, no solo en tablas improvisadas sin tendencias y números de resumen. También aparece en visualizaciones como [!UICONTROL Anillos], [!UICONTROL Flujo], [!UICONTROL Visita en el orden previsto], [!UICONTROL Cohorte], etc.

![Gráfico de resumen en visualizaciones](assets/ann-summary.png)
