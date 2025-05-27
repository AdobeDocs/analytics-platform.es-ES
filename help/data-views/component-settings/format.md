---
title: Formato de configuración de componentes
description: Configure el formato de una métrica.
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 6fdb6cbd6f12a0417f513565b02e3ad60c8df6cb
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 88%

---

# Formato de configuración de componentes {#format-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_format"
>title="Formato"
>abstract="Determine cómo se muestra un componente cuando se utiliza en los informes."

<!-- markdownlint-enable MD034 -->


El formato le permite determinar cómo se muestra un componente determinado cuando se utiliza en los informes.

## Configuración de formato para un componente

Puede determinar cómo se muestra un componente determinado ajustando su configuración de formato.

1. En Customer Journey Analytics, vaya a la pestaña [!UICONTROL **Vistas de datos**].

1. Seleccione la vista de datos que contiene el componente cuya configuración de formato desea configurar.

1. Seleccione la pestaña [!UICONTROL **Componentes**].

1. Seleccione el componente que desea configurar y, a continuación, expanda la sección [!UICONTROL **Formato**] en el lado derecho de la página.

   ![Configuración de formato](../assets/format-settings.png)

1. Especifique la siguiente información:

   | Configuración | Descripción |
   | --- | --- |
   | **[!UICONTROL Formato]** | Permite especificar el formato de un componente, como Decimal, Hora, Porcentaje o Moneda. |
   | **[!UICONTROL Decimal]** | No visible en los tipos de datos de esquema de enteros. Permite especificar el número de decimales que debe mostrar un componente. |
   | **[!UICONTROL Fecha]** | Permite determinar cómo desea que se muestre el campo de fecha y hora cuando se utiliza como dimensión en la creación de informes.  [Más información](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL Fecha-hora]** | Permite determinar cómo desea que se muestre el campo de fecha y hora cuando se utiliza como dimensión en la creación de informes.  [Más información](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL Moneda]** | Permite determinar en qué moneda desea que se muestre el componente. <p>Si analiza los datos globales en los que las transacciones se realizan en distintas monedas, consulte [Usar conversión de moneda](#use-currency-conversion).</p> |
   | **[!UICONTROL Mostrar tend ascendente como]** | Permite especificar si una tendencia al alza en este componente es buena (verde) o mala (rojo). |
   | **[!UICONTROL Valor verdadero]** y **[!UICONTROL Valor falso]** | Solo visible en los tipos de datos de esquema booleano. Permite personalizar la etiqueta del elemento de dimensión para los valores `true` y `false`. |

   {style="table-layout:auto"}

## Usar conversión de moneda {#use-currency-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_format_currencyconversion"
>title="Conversión de moneda"
>abstract="Seleccione una dimensión de código de moneda para configurar y mostrar la moneda en un tipo de moneda seleccionado."

<!-- markdownlint-enable MD034 -->

La conversión de moneda de Customer Journey Analytics puede ser extremadamente valiosa para las empresas que operan a nivel internacional. Dado que elimina las complejidades de la conversión manual de divisas, la conversión de moneda de Customer Journey Analytics aporta uniformidad y claridad a los datos financieros. La conversión de moneda realiza un seguimiento de los tipos de cambio históricos diarios y mantiene esos tipos de cambio diarios durante un período de 4 años.

Por ejemplo, si una empresa de comercio electrónico opera en los Estados Unidos, el Reino Unido y la UE, los datos de las ventas se pueden convertir automáticamente a dólares estadounidenses, lo que garantiza una comparación sencilla y un tener conocimiento integral del rendimiento.

>[!NOTE]
>
>Antes de comenzar a configurar una métrica para la conversión de moneda, tenga en cuenta lo siguiente:
>
>* La métrica que seleccione para la conversión de moneda debe ser de tipo numérico (Double, Long, Integer, Short, Byte).
>* Configure la conexión de Customer Journey Analytics para que contenga al menos un conjunto de datos de evento que tenga una dimensión de código de moneda para cada evento que contiene una métrica de moneda. Esa dimensión de código de moneda utiliza un código de moneda alfabético que se ajusta al estándar [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html?lang=es) para representar monedas. Estos valores deben tener el formato completo de mayúsculas, como USD para $, EUR para €, GBP para £.

Para determinar cómo se muestran y convierten las divisas correspondientes a una métrica determinada:

1. Comience a configurar la métrica para la cual desea usar el formato de moneda, como se ha descrito anteriormente, en [Configuración de los ajustes de formato de una métrica](#configure-format-settings-for-a-metric).

1. Con la métrica seleccionada, realice las siguientes selecciones en la sección [!UICONTROL **Formato**] en el lado derecho de la página:

   * En el campo [!UICONTROL **Formato**], seleccione [!UICONTROL **Moneda**].

   * En el campo [!UICONTROL **Cifras decimales**], elija el número de decimales que mostrará la métrica.

     Esta opción solo está disponible si la métrica tiene el tipo numérico “Doble”.

   * Seleccione la opción [!UICONTROL **Convertir moneda**].

   * En el campo [!UICONTROL **Seleccionar dimensión de código de moneda**], seleccione la dimensión que representa la moneda desde la que está realizando la conversión (la moneda en la que se basan los datos). Por ejemplo, seleccione una dimensión llamada [!UICONTROL **Código de moneda**].

     Si no tiene una dimensión en el esquema de datos actual que contenga un campo de código de moneda, puede crear un nuevo campo de código de moneda con [Preparación de datos](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=es), [Data Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html?lang=es) o [Campos derivados](/help/data-views/derived-fields/derived-fields.md). La preparación de datos solo es adecuada para nuevas implementaciones, ya que solo se realiza desde ese momento en adelante. Según la configuración de una organización, Data Distiller y los campos derivados se pueden utilizar para acceder históricamente a los valores de código de divisa.

   * En el campo [!UICONTROL **Convertir y mostrar moneda en**], elija la moneda a la que desea convertir los datos.

1. Repita los pasos si desea aplicar la conversión de moneda a métricas adicionales.



### Preguntas frecuentes 

+++ ¿Cómo se ejecuta la conversión de moneda?

Tras la creación del informe, el valor de la métrica y el código de moneda original se convierten a USD y, a continuación, a la moneda configurada para su visualización. Para esta conversión, se utilizan los tipos de cambio de moneda diarios, aplicables en el momento del evento.

+++

