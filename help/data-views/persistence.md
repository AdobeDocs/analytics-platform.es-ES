---
title: ¿Qué es la persistencia de la dimensión en el Customer Journey Analytics?
description: La persistencia del Dimension es una combinación de asignación y caducidad. Juntos, determinan qué valores de dimensión persisten.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
translation-type: tm+mt
source-git-commit: 16e43f5d938ac25445f382e5eba8fc12e0e67161
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 18%

---

# Persistencia

La persistencia del Dimension es una combinación de asignación y caducidad. Juntos, determinan qué valores de dimensión persisten. Adobe recomienda explicar en su organización cómo se gestionan los valores múltiples para cada dimensión (asignación) y cuándo los valores de dimensión dejan de contener datos (caducidad).

* De forma predeterminada, un valor de dimensión utiliza [QUÉ?] asignación.
* De forma predeterminada, un valor de dimensión utiliza una caducidad de [!UICONTROL Session].

## Asignación

La asignación aplica una transformación al valor subyacente que está utilizando. Los modelos de asignación admitidos son:

* Más reciente
* Original
* Todas
* Primera conocida
* Última conocida

### [!UICONTROL Asignación más ] reciente

Este es un ejemplo anterior y posterior de la asignación [!UICONTROL más reciente]:

| Dimensión | Visita 1 | Visita 2 | Visita 3 | Visita 4 | Visita 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 3 | 6 | 7 |
| valores originales |  | C | B |  | A |
| Asignación más reciente |  | C | B | B | A |

###  Asignación original

Este es un ejemplo anterior y posterior de la asignación [!UICONTROL Original]:

| Dimensión | Visita 1 | Visita 2 | Visita 3 | Visita 4 | Visita 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 1 | 6 | 7 |
| valores originales |  | C | B |  | A |
| Asignación original |  | C | C | C | C |

###  Asignación

Esta nueva asignación de dimensiones se puede aplicar tanto a dimensiones basadas en arreglos de discos como a dimensiones de un solo valor. Actúa de manera similar al modelo de atribución [!UICONTROL Participación] de las métricas. La diferencia es que los valores individuales dentro del campo pueden caducar en diferentes puntos. Por ejemplo, supongamos que tenemos 5 eventos en un campo de cadena, con la asignación configurada en &quot;Todos&quot; y la caducidad establecida en 5 minutos. Esperaríamos el siguiente comportamiento:

| Dimensión | Visita 1 | Visita 2 | Visita 3 | Visita 4 | Visita 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 3 | 6 | 7 |
| valores originales | A | B | C |  | A |
| después de la persistencia | A | A,B | A,B,C | B,C | A,C |

Observe que el valor de A persiste hasta que alcanza la marca de 5 minutos, mientras que B y C continúan persistiendo en la visita individual 4 porque aún no han pasado 5 minutos para esos valores. Tenga en cuenta que esta asignación creará una dimensión multivalor a partir de un campo de un solo valor. Este modelo también debe admitirse en dimensiones basadas en arreglos de discos:

| Dimensión | Visita 1 | Visita 2 | Visita 3 | Visita 4 | Visita 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 3 | 2 | 3 | 6 | 7 |
| valores originales | A,B | C | B,C |  | A |
| después de la persistencia | A,B | A,B,C | A,B,C | B,C | A,B,C |

### Asignaciones &quot;Primer conocimiento&quot; y &quot;Último conocimiento&quot;

Estos dos nuevos modelos de asignación toman el primer o último valor observado para una dimensión dentro de un ámbito de persistencia especificado (sesión, persona o período de tiempo personalizado con retrospectiva) y lo aplican a todos los eventos dentro del ámbito especificado. Ejemplo:

| Dimensión | Visita 1 | Visita 2 | Visita 3 | Visita 4 | Visita 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 3 | 6 | 7 |
| valores originales |  | C | B |  | A |
| la primera | C | C | C | C | C |
| last known | A | A | A | A | A |

Los primeros o últimos valores conocidos podrían aplicarse solo a una sesión o al ámbito de la persona (ventana de informes) o a un ámbito personalizado o basado en el tiempo (esencialmente, un ámbito de persona con una ventana retrospectiva añadida).

## Caducidad

 Expirationpermite especificar la ventana de persistencia de una dimensión.

Existen cuatro formas de caducar un valor de dimensión:

* Sesión (predeterminada): Caduca después de una sesión determinada.
* Persona: ?
* Tiempo: Puede configurar el valor de dimensión para que caduque después de un período de tiempo o evento especificados.
* Métrica: Puede especificar cualquiera de las métricas definidas como fin de caducidad para esta dimensión (por ejemplo, una métrica &quot;Compra&quot;).
* Personalizado:

### ¿Cuál es la diferencia entre Asignación y Atribución?

**Asignación**: Considere la asignación como una &quot;transformación de datos&quot; de la dimensión. La asignación se produce antes del filtrado. Si crea un filtro, se elimina de la dimensión transformada.

**Atribución**: ¿Cómo puedo distribuir el crédito de una métrica a la dimensión a la que se aplica? La atribución se produce después del filtrado.
