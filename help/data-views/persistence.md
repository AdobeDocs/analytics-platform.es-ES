---
title: ¿Qué es la persistencia de la dimensión en el Customer Journey Analytics?
description: La persistencia del Dimension es una combinación de asignación y caducidad. Juntos, determinan cómo o si los valores de dimensión persisten de un evento a otro.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
translation-type: tm+mt
source-git-commit: 7370caf3495ff707698022889bf17528582da803
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 9%

---

# Persistencia

La persistencia del Dimension es una combinación de asignación y caducidad. Juntos, determinan cómo o si los valores de dimensión persisten de un evento a otro. La persistencia del Dimension se configura en una dimensión dentro de las vistas de datos y es retroactiva y no destructiva para los datos a los que se aplica. La persistencia del Dimension es una transformación de datos inmediata aplicada a una dimensión que se produce antes de que el filtrado u otras operaciones de análisis se realicen en los informes.

* De forma predeterminada, un valor de dimensión no tiene habilitada ninguna persistencia.
* De forma predeterminada, cuando cualquier modelo de asignación está habilitado para una dimensión, se utiliza una caducidad de [!UICONTROL Session].

## Asignación

La asignación aplica una transformación al valor subyacente que está utilizando. Los modelos de asignación admitidos son:

* Más reciente
* Original
* Todas

### [!UICONTROL Asignación más ] reciente

La asignación más reciente persistirá en el valor más reciente (por marca de tiempo) presente en la dimensión. Los valores posteriores que se produzcan dentro de la misma sesión reemplazarán al valor que persiste anteriormente. Tenga en cuenta que si se ha seleccionado &quot;Tratar &#39;Sin valor&#39; como valor&quot; en esta dimensión, los valores vacíos se sustituirán por &quot;Sin valor&quot; antes de aplicar la persistencia. Este es un ejemplo anterior y posterior de la asignación [!UICONTROL más reciente] suponiendo que se utiliza una [!UICONTROL sesión] para la caducidad y que todos los eventos se producen dentro de una [!UICONTROL sesión]:

| Dimensión | Visita 1 | Visita 2 | Visita 3 | Visita 4 | Visita 5 |
| --- | --- | --- | --- | --- | --- |
| valores del conjunto de datos |  | C | B |  | A |
| Asignación más reciente |  | C | B | B | A |

###  Asignación original

La asignación original persistirá en el valor original (por marca de tiempo) presente dentro de la dimensión durante un periodo de caducidad. Este es un ejemplo anterior y posterior de la asignación [!UICONTROL Original]:

| Dimensión | Visita 1 | Visita 2 | Visita 3 | Visita 4 | Visita 5 |
| --- | --- | --- | --- | --- | --- |
| valores del conjunto de datos |  | C | B |  | A |
| Asignación original |  | C | C | C | C |

###  Asignación

Esta asignación de dimensión se puede aplicar tanto a dimensiones basadas en arreglos de discos como a dimensiones de un solo valor. Actúa de manera similar al modelo de atribución [!UICONTROL Participación] de las métricas. Una diferencia clave es que las dimensiones con Todas las asignaciones pueden utilizarse en las definiciones de Filtro. Por ejemplo, supongamos que tenemos 5 eventos en un campo de cadena, con la asignación configurada en &quot;Todos&quot; y la caducidad establecida en 5 minutos:

| Dimensión | Visita 1 | Visita 2 | Visita 3 | Visita 4 | Visita 5 |
| --- | --- | --- | --- | --- | --- |
| valores del conjunto de datos | A | B | C |  | A |
| después de la persistencia | A | A,B | A,B,C | A,B,C | A,B,C |

## Caducidad

 Expirationpermite especificar la ventana de persistencia de una dimensión.

Existen cuatro formas de caducar un valor de dimensión:

* Sesión (predeterminada): Caduca después de una sesión determinada.
* Persona: Caduca al final de la ventana de informes.
* Tiempo: Puede configurar el valor de dimensión para que caduque después de un período de tiempo o evento especificados. Esta opción de caducidad solo está disponible para los modelos de asignación Original y Más reciente.
* Métrica: Puede especificar cualquiera de las métricas definidas como fin de caducidad para esta dimensión (por ejemplo, una métrica &quot;Compra&quot;). Esta caducidad solo está disponible para los modelos de asignación Original y Más reciente.

### ¿Cuál es la diferencia entre Asignación y Atribución?

**Asignación**: Considere la asignación como una transformación de datos en la dimensión. La asignación se produce antes del filtrado. Si crea un filtro, se elimina de la dimensión transformada.

**Atribución**: ¿Cómo puedo distribuir el crédito de una métrica a la dimensión a la que se aplica? La atribución no es una transformación de datos, se aplica durante la agregación de datos y no afecta a los datos que se incluyen mediante un filtro.
