---
title: ¿Qué es la persistencia de la dimensión en Customer Journey Analytics?
description: La persistencia de la dimensión es una combinación de asignación y caducidad. Juntos, determinan cómo persisten los valores de dimensión de un evento a otro, o si lo hacen.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
translation-type: ht
source-git-commit: ffeada325825545ae0ab43f176e5d301cd1761ee
workflow-type: ht
source-wordcount: '574'
ht-degree: 100%

---

# Persistencia

La persistencia de la dimensión es una combinación de asignación y caducidad. Juntos, determinan cómo persisten los valores de dimensión de un evento a otro, o si lo hacen. La persistencia de la dimensión se configura en una dimensión de las vistas de datos, y es retroactiva y no destructiva para los datos a los que se aplica. La persistencia de la dimensión es una transformación de datos inmediata aplicada a una dimensión que se produce antes de que el filtrado u otras operaciones de análisis se realicen en los informes.

* De forma predeterminada, un valor de dimensión no tiene habilitada ninguna persistencia.
* De forma predeterminada, cuando cualquier modelo de asignación está habilitado para una dimensión, se utiliza una caducidad de [!UICONTROL Sesión].

## Asignación

La asignación aplica una transformación al valor subyacente que está utilizando. Las opciones de asignación que se admiten son las siguientes:

* Más reciente
* Original
* Todas

### Asignación [!UICONTROL más reciente]

La asignación más reciente persistirá en el valor más reciente (por marca de tiempo) presente en la dimensión. Los valores posteriores que se produzcan dentro de la misma sesión reemplazarán al valor que persiste anteriormente. Tenga en cuenta que si se ha seleccionado Tratar sin valor como valor en esta dimensión, los valores vacíos se sustituirán por Sin valor antes de aplicar la persistencia. Este es un ejemplo del antes y después de la asignación [!UICONTROL Más reciente] suponiendo que se utiliza una [!UICONTROL Sesión] para la caducidad y que todos los eventos se producen dentro de una [!UICONTROL Sesión]:

| Dimensión | Visita 1 | Visita 2 | Visita 3 | Visita 4 | Visita 5 |
| --- | --- | --- | --- | --- | --- |
| valores del conjunto de datos |  | C | B |  | A |
| Asignación más reciente |  | C | B | B | A |

### Asignación [!UICONTROL original]

La asignación original persistirá en el valor original (por marca de tiempo) presente dentro de la dimensión durante un periodo de caducidad. Este es un ejemplo del antes y después de la asignación [!UICONTROL original]:

| Dimensión | Visita 1 | Visita 2 | Visita 3 | Visita 4 | Visita 5 |
| --- | --- | --- | --- | --- | --- |
| valores del conjunto de datos |  | C | B |  | A |
| Asignación original |  | C | C | C | C |

### [!UICONTROL Toda] la asignación

Esta asignación de dimensión se puede aplicar tanto a dimensiones basadas en matrices como a dimensiones de un solo valor. Actúa de manera similar al modelo de atribución [!UICONTROL Participación] de las métricas. Una diferencia clave es que las dimensiones con Toda la asignación pueden utilizarse en las definiciones de Filtro. Por ejemplo, supongamos que tenemos 5 eventos en un campo de cadena, con la asignación configurada en Toda y la caducidad establecida en 5 minutos:

| Dimensión | Visita 1 | Visita 2 | Visita 3 | Visita 4 | Visita 5 |
| --- | --- | --- | --- | --- | --- |
| valores del conjunto de datos | A | B | C |  | A |
| después de la persistencia | A | A,B | A,B,C | A,B,C | A,B,C |

## Caducidad

[!UICONTROL Expiración] permite especificar la ventana de persistencia para una dimensión.

Existen cuatro formas en que caduca un valor de dimensión:

* Sesión (predeterminada): Caduca después de una sesión determinada.
* Persona: Caduca al final de la ventana de informes.
* Tiempo: Puede configurar el valor de dimensión para que caduque después de un período de tiempo especificado (hasta 90 días). Esta opción de caducidad solo está disponible para los modelos de asignación Original y Más reciente. Al utilizar la caducidad basada en el tiempo, se tienen en cuenta los valores anteriores al inicio de la ventana de informes (hasta 90 días).
* Métrica: Le permite especificar cualquiera de las métricas definidas como la caducidad de esta dimensión (por ejemplo, una métrica de compra). Esta caducidad solo está disponible para los modelos de asignación Original y Más reciente.

### ¿Cuál es la diferencia entre asignación y atribución?

**Asignación**: Considere la asignación como una transformación de datos en la dimensión. La asignación se produce antes del filtrado. Si crea un filtro, se elimina de la dimensión transformada.

**Atribución**: ¿Cómo puedo distribuir el crédito de una métrica a la dimensión a la que se aplica? La atribución no es una transformación de datos, se aplica durante la agregación de datos y no afecta a los datos que se incluyen mediante un filtro.
