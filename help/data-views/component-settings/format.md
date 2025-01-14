---
title: Formato de configuración de componentes
description: Configure el formato de una métrica.
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 23%

---

# Formato de configuración de componentes {#format-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_format"
>title="Formato"
>abstract="Determine cómo se muestra un componente cuando se utiliza en los informes."

<!-- markdownlint-enable MD034 -->


El formato le permite determinar cómo se muestra una métrica determinada cuando se utiliza en los informes.

## Configurar los ajustes de formato de una métrica

Puede determinar cómo se muestra una métrica determinada ajustando su configuración de formato.

1. En Customer Journey Analytics, seleccione la pestaña [!UICONTROL **Vistas de datos**].

1. Seleccione la vista de datos que contiene el componente cuya configuración de formato desee configurar.

1. Seleccione la pestaña [!UICONTROL **Componentes**].

1. Seleccione el componente que desea configurar y, a continuación, expanda la sección [!UICONTROL **Formato**] en el lado derecho de la página.

   ![Configuración de formato](../assets/format-settings.png)

1. Especifique la siguiente información:

   | Configuración | Descripción |
   | --- | --- |
   | **[!UICONTROL Formato]** | Permite especificar el formato de una métrica, como Decimal, Hora, Porcentaje o Moneda. |
   | **[!UICONTROL Decimal]** | No visible en los tipos de datos de esquema de enteros. Permite especificar el número de decimales que debe mostrar una métrica. |
   | **[!UICONTROL Fecha]** | Permite determinar cómo desea que se muestre el campo de fecha y hora cuando se utiliza como dimensión en la creación de informes.  [Más información](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL Fecha-hora]** | Permite determinar cómo desea que se muestre el campo de fecha y hora cuando se utiliza como dimensión en la creación de informes.  [Más información](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL Moneda]** | Permite determinar en qué moneda desea que se muestre la métrica. <p>Si analiza los datos globales en los que las transacciones se realizan en distintas monedas, consulte [Usar conversión de moneda](#use-currency-conversion).</p> |
   | **[!UICONTROL Mostrar tend ascendente como]** | Permite especificar si una tendencia al alza en esta métrica debe considerarse buena (verde) o mala (rojo). |
   | **[!UICONTROL Valor verdadero]** y **[!UICONTROL Valor falso]** | Solo visible en los tipos de datos de esquema booleano. Permite personalizar la etiqueta del elemento de dimensión para los valores `true` y `false`. |

   {style="table-layout:auto"}

## Usar conversión de moneda {#use-currency-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_format_currencyconversion"
>title="Conversión de moneda"
>abstract="Seleccione una dimensión de código de moneda para configurar y mostrar la moneda en un tipo de moneda seleccionado."

<!-- markdownlint-enable MD034 -->

La conversión de divisas en Customer Journey Analytics puede ser extremadamente valiosa para las empresas que operan a nivel internacional. Al eliminar las complejidades de la conversión manual de divisas, la conversión de divisas en Customer Journey Analytics aporta uniformidad y claridad a los datos financieros. La conversión de moneda realiza un seguimiento de los tipos de cambio históricos diarios y mantiene esos tipos de cambio diarios durante un período de 4 años.

Por ejemplo, si una empresa de comercio electrónico opera en los Estados Unidos, el Reino Unido y la UE, los datos de ventas se pueden convertir automáticamente a dólares estadounidenses, lo que garantiza una comparación sencilla y una comprensión integral del rendimiento.

>[!NOTE]
>
>Antes de comenzar a configurar una métrica para la conversión de moneda, tenga en cuenta lo siguiente:
>
>* La métrica que seleccione para la conversión de moneda debe tener un tipo numérico (Double, Long, Integer, Short, Byte).
>* Configure la conexión de Customer Journey Analytics para que contenga al menos un conjunto de datos de evento que contenga una dimensión de código de moneda para cada evento que contenga una métrica de moneda. Esa dimensión de código de moneda utiliza un código de moneda alfabético que se ajusta al estándar [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) para representar monedas. Estos valores deben estar en formato completo en mayúsculas, como USD para $, EUR para €, GBP para £.

Para determinar cómo se muestran y convierten las divisas para una métrica determinada:

1. Comience a configurar la métrica para la cual desea usar moneda como formato, como se ha descrito anteriormente, en [Configurar la configuración de formato de una métrica](#configure-format-settings-for-a-metric).

1. Con la métrica seleccionada, realice las siguientes selecciones en la sección [!UICONTROL **Formato**] de la derecha de la página:

   * En el campo [!UICONTROL **Formato**], seleccione [!UICONTROL **Moneda**].

   * En el campo [!UICONTROL **Cifras decimales**], elija el número de decimales que mostrará la métrica.

     Esta opción solo está disponible si la métrica tiene un tipo numérico &quot;Double&quot;.

   * Seleccione la opción [!UICONTROL **Convertir moneda**].

   * En el campo [!UICONTROL **Seleccionar dimensión de código de moneda**], seleccione la dimensión que representa la moneda desde la que está realizando la conversión (la moneda en la que se basan los datos). Por ejemplo, seleccione una dimensión llamada [!UICONTROL **Código de moneda**].

     Si no tiene una dimensión en el esquema de datos actual que contenga un campo de código de moneda, puede crear un nuevo campo de código de moneda con [Preparación de datos](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=es), [Data Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html) o [Campos derivados](/help/data-views/derived-fields/derived-fields.md). La preparación de datos solo es adecuada para nuevas implementaciones, ya que solo se realiza en adelante. Según la configuración de una organización, Data Distiller y los campos derivados se pueden utilizar para acceder históricamente a los valores de código de divisa.

   * En el campo [!UICONTROL **Convertir y mostrar moneda en**], elija la moneda en la que desea convertir los datos.

1. Repita estos pasos si desea aplicar la conversión de moneda a métricas adicionales.



### Preguntas frecuentes 

+++ ¿Cómo se ejecuta la conversión de moneda?

Tras la creación del informe, el valor de la métrica y el código de moneda original se convierten a USD y, a continuación, a la moneda configurada para su visualización. Para esta conversión, se utilizan los tipos de cambio de moneda diarios, aplicables en el momento del evento.

+++

