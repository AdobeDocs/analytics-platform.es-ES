---
title: ¿Qué es la persistencia de la dimensión en el Customer Journey Analytics?
description: La persistencia del Dimension es una combinación de asignación y caducidad. Juntos, determinan qué valores de dimensión persisten.
translation-type: tm+mt
source-git-commit: b99e108e9f6dd1c27c6ebb9b443f995beb71bdbd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Persistencia

La persistencia del Dimension es una combinación de asignación y caducidad. Juntos, determinan qué valores de dimensión persisten. Adobe recomienda explicar en su organización cómo se gestionan los valores múltiples para cada dimensión (asignación) y cuándo los valores de dimensión dejan de contener datos (caducidad).

* De forma predeterminada, un valor de dimensión utiliza la última asignación. Los valores nuevos sobrescriben los valores persistentes.
* De forma predeterminada, un valor de dimensión utiliza una caducidad de [!UICONTROL Session].

## Asignación

Determina la forma en que CJA asigna crédito por un evento de éxito si una variable recibe varios valores antes del evento. Los valores admitidos son:

* Más reciente: El último valor de la eVar siempre recibe el crédito por los eventos de éxito hasta que la eVar caduque.
* Valor original: La primera eVar siempre recibe crédito por los eventos de éxito hasta que la eVar caduque.
* Instancia: ??

Nota: Si se cambia la asignación a Lineal o de Lineal, los datos históricos no se mostrarán. La combinación de tipos de asignación en la interfaz de informes puede llevar a una exposición incorrecta de los datos en los informes. Por ejemplo, la asignación Lineal puede dividir los ingresos entre un número de distintos valores de eVar. Después de volver a cambiar a la asignación Más reciente, el 100 % de esos ingresos se asociarán con el valor único más reciente. Esta asociación puede llevar a conclusiones incorrectas por parte de los usuarios.

Para evitar confusión en los informes, Analytics impide que la interfaz tenga acceso a los datos históricos. Esos datos se pueden ver si decide cambiar de nuevo la eVar a su valor de asignación inicial, pero no debería cambiar ese valor simplemente para acceder a los datos históricos. Adobe recomienda usar una eVar nueva cuando se desee otra configuración de asignación para los datos ya registrados, en lugar de cambiar la configuración de asignación en una eVar que ya dispone de una cantidad importante de datos históricos creados.

## Caducidad

Los valores del Dimension caducan después del período de tiempo especificado. Una vez que caduca el valor de dimensión, ya no recibe el crédito por una métrica. Los Dimension también se pueden configurar para que caduquen en las métricas. Por ejemplo, si tiene una promoción interna que caduca el final de una visita, la promoción interna recibe el crédito solo por las compras o registros que se produzcan durante la visita en la que se activaron.

Hay dos maneras de que una eVar caduque:

Puede configurar la eVar para que caduque después de un período de tiempo o evento especificados.
Puede forzar la caducidad de una eVar al restablecerla, lo que resulta útil cuando se cambia el propósito de una variable.
Por ejemplo, si cambia la caducidad de una eVar de 30 a 90 días, los valores de la eVar recopilados persistirán durante el nuevo conjunto de caducidad (en este caso, 90 días). El sistema simplemente observa la configuración de caducidad actual y la última marca de tiempo establecida del valor de eVar obtenido para determinar la caducidad. Solo la opción Restablecer caduca los valores y lo hace de inmediato.

Otro ejemplo: si se usa una eVar en mayo para reflejar promociones internas y caduca después de 21 días, y en junio se usa para capturar palabras clave de búsqueda interna, el 1 de junio, debe forzar la caducidad o restablecer la variable. De hacerlo, ayudará a mantener los valores de promoción internos fuera de los informes de junio.