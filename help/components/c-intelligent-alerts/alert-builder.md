---
description: Obtenga alertas cuando los componentes del proyecto alcancen ciertos umbrales.
title: Creación de alertas
feature: Workspace Basics
role: User, Admin
source-git-commit: df0fd0af8a22c84705c3dea11065132359dd80ff
workflow-type: tm+mt
source-wordcount: '991'
ht-degree: 19%

---

# Creación de alertas {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_alerts_timegranularity"
>title="Granularidad de tiempo"
>abstract="La granularidad de tiempo hace referencia a la frecuencia con la que se comprobará la alerta y a lo que se incluirá"

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>El uso de alertas con detección de anomalías (también conocido como _alertas inteligentes_) solo está disponible para organizaciones con un paquete Customer Journey Analytics Select, Prime o Ultimate.

Las alertas de Customer Journey Analytics permiten recibir notificaciones basadas en porcentajes modificados o puntos de datos específicos. Según el paquete del Customer Journey Analytics, también puede utilizar alertas para activarlas en función de los umbrales de anomalías.

Para obtener información general más detallada sobre las alertas, consulte [Información general sobre alertas](/help/components/c-intelligent-alerts/intelligent-alerts.md).

Para crear una alerta:

1. En el Customer Journey Analytics <!-- add this back in after the other methods are available like in AA and make a bulleted list: "You can access the alert builder in any of the following ways:" -->, seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Alertas]**. En el [Administrador de alertas](alert-manager.md), seleccione ![AgregarCírculo](/help/assets/icons/AddCircle.svg) **[!UICONTROL Agregar]** para crear una nueva alerta o seleccione cualquiera de las alertas enumeradas para modificar una alerta existente.

   Se muestra la interfaz [Generador de alertas](#alert-builder).

1. Seleccione **[!UICONTROL Guardar]** para guardar la alerta. Seleccione **[!UICONTROL Guardar como]** para guardar una copia de la alerta.


## Generador de alertas

La interfaz del Generador de alertas resulta familiar a quienes hayan creado filtros o calculado métricas en Customer Journey Analytics:

![](assets/alert-builder.png)

Especifique los siguientes detalles en el Generador de alertas para una alerta:

| Elemento | Descripción |
|---------|----------|
| **[!UICONTROL Título]** | Especifique un nombre para la alerta. El nombre de la alerta puede contener el nombre del umbral de informe o de métricas. |
| **[!UICONTROL Descripción (opcional)]** | Especifique una descripción para la alerta. |
| **[!UICONTROL Granularidad de tiempo]** | Seleccione la frecuencia con la que desea que se compruebe la métrica: Diaria, Semanal o Mensual.<p><b>Nota:</b>Para las vistas de datos con un calendario personalizado, no se admite la granularidad mensual en el Generador de alertas.<!--true?--></p> |
| **[!UICONTROL Destinatarios]** | Especifique hacia dónde se puede enviar la alerta. Se puede enviar una alerta a un usuario de Analytics, un grupo de Analytics o a una dirección de correo electrónico sin procesar o a un número de teléfono.<p><b>Importante:</b>El número de teléfono debe estar precedido por &quot;+&quot; y [código de país](https://countrycode.org/).</p><p>El correo electrónico que un usuario recibe después de activar una alerta tiene un aspecto similar al siguiente:</p><p>![Correo electrónico de alerta](assets/alerts-email.PNG)</p> |
| **[!UICONTROL Fecha de caducidad]** | Establezca la fecha y la hora en que desea que la alerta caduque. |
| **[!UICONTROL Retraso]** | El tiempo necesario antes de que los datos se completen y estén disponibles para su notificación en Customer Journey Analytics varía según la organización, normalmente oscila entre 3 y 9 horas después del evento de datos. Para que las alertas sean precisas, los datos de evento de un intervalo de eventos determinado deben estar completos, lo que significa que el Adobe ya no recibe datos de evento para el intervalo de eventos especificado.<p>Para tener en cuenta este retraso en el tiempo de ingesta, las alertas tienen un retraso predeterminado de 9 horas antes de enviarse.</p><p>Puede ajustar el retraso predeterminado de 9 horas a cualquier valor entre 0 y 24 horas. Sin embargo, si se reduce el retraso por debajo de 9 horas, puede significar que está generando informes con datos incompletos, lo que da como resultado información de alerta inexacta.</p><p>Tenga en cuenta lo siguiente al reducir el tiempo de retraso:</p><ul><li>**Comprender la disponibilidad de los datos frente a su integridad**: aunque es posible que algunos datos estén disponibles para generar informes antes, todos los datos por lotes se incorporan en un conjunto de datos de Platform solo después de un período de 3 a 9 horas. Para que las alertas sean precisas, la ingesta de datos debe ser completa, con todos los datos por lotes disponibles en el conjunto de datos.</li><li>**Determine cuánto tiempo tardan los datos en estar completos y disponibles en el conjunto de datos**: los tiempos de ingesta de datos difieren según la organización. Asegúrese de que el tiempo de demora que elija para la entrega de alertas sea el mismo o menos frecuente que el tiempo que tardan los datos por lotes en estar disponibles en el conjunto de datos de Platform<!--add link? -->.</li><p>**Sugerencia:** La forma más precisa de saber el tiempo necesario para completar e incorporar todos los datos por lotes en el conjunto de datos de Platform es consultar a los ingenieros de datos de su organización.</p><p>También puede hacerse una idea general de cuánto tiempo tarda el envío por lotes en su organización en estar disponible en el conjunto de datos de Platform creando la siguiente tabla de forma libre en Analysis Workspace:</p><ol><li>En una tabla de forma libre de Analysis Workspace, agregue una métrica de [!UICONTROL **Eventos**] y una dimensión de [!UICONTROL **Día**].</li><li>Desglose la dimensión [!UICONTROL **Día**] con una dimensión [!UICONTROL **Horas**].<p>Las horas sin datos se mostrarán como 0.</p></li></ol><li>**Tener en cuenta los errores en los cálculos**: Si reduce el tiempo de retraso predeterminado, le recomendamos que configure el retraso durante al menos una hora más que el tiempo que tarda su organización en completar la ingesta de datos. Por ejemplo, si hay un retraso de 3 horas antes de que se complete la ingesta de datos, debe establecer el retraso en 4 horas.</li></ul><p>Para obtener más información, consulte [Los tiempos de ingesta de datos varían en el Customer Journey Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md#data-ingestion-times-vary-in-customer-journey-analytics) en el artículo [Comparación de características de alertas: Customer Journey Analytics y Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md). |
| **[!UICONTROL Enviar una alerta cuando]** | [!UICONTROL **déclencheur de cualquiera de estas métricas**]: arrastre y suelte las métricas (incluidas las calculadas) aquí para crear déclencheur para la alerta.<p>Aparece el mensaje **&quot;componentes incompatibles&quot;** si no todas las métricas, dimensiones o segmentos de la alerta son compatibles con la vista de datos seleccionada actualmente.</p><p>Determine el umbral que debe superar la métrica para que se establezca la alerta. Puede ajustar este valor a un umbral y, a continuación, a una de las condiciones siguientes:</p><ul><li>existe anomalía</li><li>anomalía por encima de lo esperado</li><li>anomalía por debajo de lo esperado</li><li>mayor o igual que</li><li>menor o igual que</li><li>cambia por un</li><li>Puede establecer el umbral en 90 %, 95 %, 99 %, 99,75 % y 99,9 %.</li></ul><p>[!UICONTROL **Con todos estos filtros**]: Arrastre y suelte los segmentos o dimensiones para agregar filtros. Por ejemplo, si agrega un segmento &quot;Solo dispositivos móviles&quot; significará que la regla se aplica únicamente a los déclencheur móviles. Puede agregar filtros adicionales mediante una instrucción AND. Puede añadir las reglas AND u OR si hace clic en el icono de engranaje.</p><p>Consulte [Alertas - casos de uso](/help/components/c-intelligent-alerts/alerts-use-cases.md) para ver casos de uso por ejemplo.</p> |
| **[!UICONTROL Vista previa]** | La vista previa de alertas interactiva le muestra con qué frecuencia, aproximada, se activará una alerta en función de las experiencias pasadas.<p>Por ejemplo, si establece la granularidad de tiempo a diario, en la vista previa podrá ver cuántas veces se habrá activado una alerta para una métrica en particular durante los últimos 30 o 31 días.</p><p>Si descubre que se habrían activado demasiadas alertas, puede ajustar el umbral en [Administrar alertas](/help/components/c-intelligent-alerts/alert-manager.md).</p><p>![](assets/alert-preview.png){width="50%"}</p> |

