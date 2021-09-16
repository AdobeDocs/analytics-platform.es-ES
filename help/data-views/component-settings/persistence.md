---
title: Configuración de componentes de persistencia
description: Determine cómo o si los valores de dimensión persisten de un evento a otro.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
source-git-commit: 0c27f75eed8f1f3dec3f287cfe35ab748bbfc1bb
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 23%

---


#  Configuración de componentes de persistencia

 La persistencia es la capacidad de un valor de dimensión determinado para relacionarse con una métrica más allá del evento en el que está establecido. Utiliza una combinación de asignación y caducidad.

* **** La asignación le permite determinar qué valor se conserva cuando más de un elemento de dimensión puede persistir a la vez en una sola columna.
* **** Caducidad le permite determinar cuánto tiempo persiste un elemento de dimensión más allá del evento en el que está establecido.

 La persistencia solo está disponible en dimensiones y es retroactiva a los datos a los que se aplica. Se trata de una transformación inmediata de los datos que se produce antes de aplicar el filtrado u otras operaciones de análisis.

![Persistencia](../assets/persistence.png)

| Configuración | Descripción |
| --- | --- |
| [!UICONTROL Establecer persistencia] | Habilite la persistencia para la dimensión. Si la persistencia no está habilitada, la dimensión solo se relaciona con métricas que existen en el mismo evento. Esta opción está desactivada de manera predeterminada. |
| [!UICONTROL Asignación] | Permite especificar el modelo de asignación utilizado en una dimensión para la persistencia. Las opciones son: [!UICONTROL Más reciente], [!UICONTROL Original], [!UICONTROL Instancia], [!UICONTROL Todos]. |
| [!UICONTROL Caducidad] | Permite especificar la ventana de persistencia para una dimensión. Las opciones son: [!UICONTROL Sesión] (predeterminada), [!UICONTROL Persona], [!UICONTROL Tiempo personalizado], [!UICONTROL Métrica]. Es posible que deba poder caducar la dimensión de una compra (por ejemplo, términos de búsqueda internos u otros casos de uso de comercialización). El tiempo de caducidad máximo que puede establecer es de 90 días. Si selecciona una asignación de [!UICONTROL All], solo está disponible la caducidad [!UICONTROL Session] o [!UICONTROL Person]. |

##  Configuración de asignación

Detalles sobre la configuración de asignación disponible.

* **[!UICONTROL Más reciente]**: persiste en el valor más reciente (por marca de tiempo) presente en la dimensión. Cualquier valor posterior que se produzca dentro del periodo de caducidad de la dimensión reemplaza al valor que persiste anteriormente. Si &quot;Tratar &#39;Sin valor&#39; como un valor&quot; está habilitado en esta dimensión en [Sin opciones de valor](no-value-options.md), los valores vacíos sobrescriben los valores persistentes anteriormente. Por ejemplo, considere la siguiente tabla con [!UICONTROL asignación más reciente] y [!UICONTROL caducidad de la sesión]:

   | Dimensión | Visita 1 | Visita 2 | Visita 3 | Visita 4 | Visita 5 |
   | --- | --- | --- | --- | --- | --- |
   | Valores de conjunto de datos |  | C | B |  | A |
   | Asignación más reciente |  | C | B | B | A |

* **[!UICONTROL Original]**: Mantiene el valor original por marca de tiempo presente en la dimensión durante el periodo de caducidad. Si esta dimensión tiene un valor, no se sobrescribe cuando se ve un valor diferente en un evento posterior. Por ejemplo, considere la siguiente tabla con asignación [!UICONTROL Original] y caducidad de [!UICONTROL Session]:

   | Dimensión | Visita 1 | Visita 2 | Visita 3 | Visita 4 | Visita 5 |
   | --- | --- | --- | --- | --- | --- |
   | Valores de conjunto de datos |  | C | B |  | A |
   | Asignación original |  | C | C | C | C |

* **[!UICONTROL Todo]**: Actúa de forma similar al modelo de atribución de   participación para las métricas. Mantiene todos los valores de forma equitativa, de modo que cada uno obtenga crédito total para la métrica en los informes. Por ejemplo, considere la siguiente tabla con [!UICONTROL All] asignación y [!UICONTROL caducidad de la sesión]:

   | Dimensión | Visita 1 | Visita 2 | Visita 3 | Visita 4 | Visita 5 |
   | --- | --- | --- | --- | --- | --- |
   | Valores de conjunto de datos | A | B | C |  | A |
   | Toda la asignación | A | A,B | A,B,C | A,B,C | A,B,C |

##  Configuración de caducidad

Detalles sobre la configuración de caducidad disponible.

* **Sesión**: Caduca después de una sesión determinada. Ventana de caducidad predeterminada.
* **Persona**: Caduca al final de la ventana de informes.
* **Tiempo**: Puede configurar el valor de dimensión para que caduque después de un período de tiempo especificado (hasta 90 días). Esta opción de caducidad solo está disponible para los modelos de asignación Original y Más reciente. Al utilizar la caducidad basada en el tiempo, se tienen en cuenta los valores anteriores al inicio de la ventana de informes (hasta 90 días).
* **Métrica**: Cuando esta métrica se ve en una visita, caduca inmediatamente el valor persistente en la dimensión. Puede usar cualquier métrica como fin de caducidad para esta dimensión. Esta opción de caducidad solo está disponible para las opciones de asignación Original y Más reciente .
