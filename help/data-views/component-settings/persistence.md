---
title: Configuración de componentes de persistencia
description: Determina cómo persisten los valores de dimensión de un evento a otro, o si lo hace.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 8e10818efa7da54b0802c56e5388e6c7ef7fd8b6
workflow-type: tm+mt
source-wordcount: '1037'
ht-degree: 79%

---


# Configuración de componentes de [!UICONTROL persistencia] {#persistence-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_persistence"
>title="Persistencia"
>abstract="Configure el modelo de asignación predeterminado aplicado a una dimensión. La asignación se aplica antes de los segmentos en la creación de informes."

<!-- markdownlint-enable MD034 -->



La [!UICONTROL persistencia] es la capacidad de un valor de dimensión determinado para atribuirse a una métrica más allá del evento en el que está establecido. Utiliza una combinación de asignación y caducidad.

![Ventana de vistas de datos que resalta las opciones de Persistencia](../assets/persistence.png)

* La **asignación** le permite determinar qué valor conservar cuando más de un elemento de dimensión puede persistir a la vez en una sola columna.

  >[!NOTE]
  >
  >Si tiene un [modelo de atribución no predeterminado](/help/data-views/component-settings/attribution.md) establecido en una métrica de un informe, el modelo de atribución ignorará la asignación que haya establecido en la dimensión para el mismo informe.
  >
  >Sin embargo, al realizar una [exportación de tabla completa](/help/analysis-workspace/export/export-cloud.md) que incluye varias dimensiones, la atribución conserva los modelos de asignación aplicados a cada dimensión.

* La **caducidad** le permite determinar cuánto tiempo persiste un elemento de dimensión más allá del evento en el que está establecido.

[!UICONTROL La persistencia] solo está disponible en dimensiones y es retroactiva a los datos a los que se aplica. Se trata de una transformación inmediata de los datos que se produce antes de aplicar la segmentación u otras operaciones de análisis.

| Configuración | Descripción |
| --- | --- |
| [!UICONTROL Establecer persistencia] | Habilite la persistencia para la dimensión. Si la persistencia no está habilitada, la dimensión solo se relaciona con métricas que existen en el mismo evento. Esta opción está desactivada de manera predeterminada. |
| [!UICONTROL Asignación] | Especifique el modelo de asignación utilizado en una dimensión para la persistencia. Las opciones son:<ul><li>**[!UICONTROL Más reciente]**: los valores de la dimensión persisten hasta que los valores subsiguientes los sobrescriban</li><li> **[!UICONTROL Original]**: el primer valor de esta dimensión persiste y no se sobrescribe con valores posteriores</li><li>**[!UICONTROL Todos]**: todos los valores de esta dimensión persisten simultáneamente</li><li>**[!UICONTROL Primero conocido]**: Se usa el primer valor de esta dimensión, que se aplicará a todos los eventos antes y después.</li><li>**[!UICONTROL Último conocido]**: se usa el último valor de esta dimensión, que se aplicará a todos los eventos antes y después.</li></ul> |
| [!UICONTROL Caducidad] | Especifique la ventana de persistencia para una dimensión. Las opciones son: <ul><li>**[!UICONTROL Sesión]** (valor predeterminado). </li><li>**[!UICONTROL Persona]**</li><li>**[!UICONTROL Tiempo personalizado]**</li><li>**[!UICONTROL Métrica]**</li></ul>. Es posible que deba poder caducar la dimensión de una compra (por ejemplo, términos de búsqueda internos u otros casos de uso de comercialización). El tiempo de caducidad máximo que puede establecer es de 90 días. Si selecciona una asignación de [!UICONTROL Todos], solo está disponible la caducidad de la [!UICONTROL Sesión] o [!UICONTROL Persona]. |

{style="table-layout:auto"}

## Configuración de [!UICONTROL asignación]

La configuración de asignación disponible es:

* **[!UICONTROL Más reciente]**: conserva el valor más reciente (por marca de tiempo) presente en la dimensión. Cualquier valor posterior que aparezca en el periodo de caducidad de la dimensión reemplaza al valor que persiste anteriormente. Si Tratar Sin valor como un valor está habilitado en esta dimensión en [Sin opciones de valor](no-value-options.md), los valores vacíos sobrescriben los valores persistentes anteriormente. Por ejemplo, vea la siguiente tabla con asignación [!UICONTROL Más reciente] y caducidad de [!UICONTROL Sesión]:

  | Dimensión | Visita 1 | Visita 2 | Visita 3 | Visita 4 | Visita 5 |
  | --- | --- | --- | --- | --- | --- |
  | Valores del conjunto de datos |  | C | B |  | A |
  | Asignación más reciente |  | C | B | B | A |

* **[!UICONTROL Original]**: conserva el valor original por marca de tiempo que está presente en la dimensión durante el período de caducidad. Si esta dimensión tiene un valor, no se sobrescribe cuando se ve un valor diferente en un evento posterior. Por ejemplo, vea la siguiente tabla con asignación [!UICONTROL Original] y caducidad de [!UICONTROL Sesión]:

  | Dimensión | Visita 1 | Visita 2 | Visita 3 | Visita 4 | Visita 5 |
  | --- | --- | --- | --- | --- | --- |
  | Valores del conjunto de datos |  | C | B |  | A |
  | Asignación original |  | C | C | C | C |

* **[!UICONTROL Todos]**: actúa de manera similar al modelo de atribución [!UICONTROL Participación] de las métricas. Conserva todos los valores de forma equitativa, de modo que cada uno obtenga crédito total para la métrica en la creación de informes. Por ejemplo, vea la siguiente tabla con asignación de [!UICONTROL Todo] y caducidad de [!UICONTROL Sesión]:

  | Dimensión | Visita 1 | Visita 2 | Visita 3 | Visita 4 | Visita 5 |
  | --- | --- | --- | --- | --- | --- |
  | Valores del conjunto de datos | A | B | C |  | A |
  | Toda la asignación | A | A,B | A,B,C | A,B,C | A,B,C |

* **[!UICONTROL Conocido por primera vez]** y **[!UICONTROL Último conocido]**: (19 de enero de 2022 ) estos dos modelos de asignación satisfacen los casos de uso de dimensiones “entrada” y “salida”. Toman el primer o el último valor observado para una dimensión dentro de un ámbito de persistencia especificado (sesión, persona o período de tiempo personalizado con retrospectiva) y lo aplican a todos los eventos dentro del ámbito especificado. Ejemplo:

  | Dimensión | Visita 1 | Visita 2 | Visita 3 | Visita 4 | Visita 5 |
  | --- | --- | --- | --- | --- | --- |
  | Marca de tiempo (mín.) | 1 | 2 | 3 | 6 | 7 |
  | Valores originales |  | C | B |  | A |
  | Primero conocido | C | C | C | C | C |
  | Último conocido | A | A | A | A | A |


## Configuración de [!UICONTROL caducidad]

La configuración de caducidad disponible es:

* **Sesión**: caduca después de una sesión determinada. Ventana de caducidad predeterminada.
* **Ventana de informes de persona**: caduca al final de la ventana de informes.
* **Ventana de informes de cuenta global** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}: Caduca al final de la ventana de informes.
* **Ventana de informes de cuenta** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}: Caduca al final de la ventana de informes.
* **Ventana de informes de oportunidad** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}: Caduca al final de la ventana de informes.
* **Ventana de creación de informes del grupo de compras** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}: caduca al final de la ventana de informes.
* **Hora personalizada**: caduca después de un período de tiempo especificado (hasta 90 días). Esta opción de caducidad solo está disponible para los modelos de asignación Original y Más reciente. Al utilizar la caducidad basada en el tiempo, se tienen en cuenta los valores anteriores al inicio de la ventana de creación de informes (hasta 90 días).
* **Métrica**: cuando esta métrica se ve en un evento, caduca inmediatamente el valor persistente de la dimensión. Puede usar cualquier métrica como fin de caducidad para esta dimensión. Esta opción de caducidad solo está disponible para la configuración de asignación Original y Más reciente.


## [!UICONTROL Dimensión de enlace]

Menú desplegable que permite enlazar la persistencia de un valor de dimensión a valores de dimensión de otra dimensión. Las opciones válidas incluyen otras dimensiones incluidas en la vista de datos.

Consulte [Uso de dimensiones y métricas de enlace en Customer Journey Analytics](../../use-cases/data-views/binding-dimensions-metrics.md) para ver ejemplos sobre cómo utilizar dimensiones de enlace de forma eficaz.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimensiones del enlace](https://video.tv.adobe.com/v/3409291/?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


## [!UICONTROL Métrica de enlace]

Menú desplegable que permite elegir una métrica que actúa como déclencheur de enlace. Las opciones válidas incluyen métricas incluidas en la vista de datos.

Esta configuración solo aparece cuando la dimensión de enlace es inferior en la matriz de objetos que el componente. Cuando la métrica de enlace está presente en un evento, los valores de dimensión se copian de la dimensión de nivel de evento hasta el nivel de esquema inferior de la dimensión de enlace.

Vea el segundo ejemplo en [Uso de dimensiones y métricas de enlace en Customer Journey Analytics](../../use-cases/data-views/binding-dimensions-metrics.md) para obtener más información sobre cómo utilizar las métricas de enlace de forma eficaz.
