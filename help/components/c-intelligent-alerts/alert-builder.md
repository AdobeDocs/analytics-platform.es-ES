---
description: Obtenga alertas cuando los componentes del proyecto alcancen ciertos umbrales.
title: Creación de alertas
feature: Workspace Basics
role: User, Admin
exl-id: 5b4b2e2b-0a73-48df-a40c-98d2c47f94c8
source-git-commit: 53069702055e0adf7abf9061c592fb15772ded73
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 95%

---

# Creación de alertas {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="Granularidad de tiempo"
>abstract="La granularidad de tiempo hace referencia a la frecuencia con la que se comprobará la alerta y a lo que se incluirá"

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>El uso de alertas con detección de anomalías (también conocido como _Alertas inteligentes_) solo está disponible en las organizaciones con un paquete de Customer Journey Analytics Prime o Ultimate.

Las alertas de Customer Journey Analytics le permiten recibir notificaciones basadas en porcentajes modificados o puntos de datos específicos. Según el paquete de Customer Journey Analytics, también puede utilizar alertas para activarlas en función de los umbrales de anomalías. 

Para obtener información general más detallada sobre las alertas, consulte [Información general sobre alertas](/help/components/c-intelligent-alerts/intelligent-alerts.md).

Para crear una alerta:

1. En Customer Journey Analytics, <!-- add this back in after the other methods are available like in AA and make a bulleted list: "You can access the alert builder in any of the following ways:" -->, seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Alertas]**. En el [Administrador de alertas](alert-manager.md), seleccione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Añadir]** para crear una nueva alerta o seleccione cualquiera de las alertas enumeradas para modificar una alerta existente.

   Se muestra la interfaz [Generador de alertas](#alert-builder).

1. Seleccione **[!UICONTROL Guardar]** para guardar la alerta. Seleccione **[!UICONTROL Guardar como]** para guardar una copia de la alerta.


## Generador de alertas

La interfaz del Generador de alertas resulta familiar a quienes hayan creado segmentos o calculado métricas en Customer Journey Analytics:

![](assets/alert-builder.png)

Especifique los siguientes detalles en el Generador de alertas para una alerta:

| Elemento | Descripción |
|---------|----------|
| **[!UICONTROL Título]** | Especifique un nombre para la alerta. El nombre de la alerta puede contener el nombre del umbral de informe o de métricas. |
| **[!UICONTROL Descripción (opcional)]** | Especifique una descripción para la alerta.  |
| **[!UICONTROL Granularidad de tiempo]** | Seleccione con qué frecuencia desea que se compruebe la métrica: diariamente, semanalmente o mensualmente.<p><b>Nota:</b> En el caso de las vistas de datos con un calendario personalizado, no admitimos la granularidad mensual en el Generador de alertas.<!--true?--></p> |
| **[!UICONTROL Destinatarios]** | Especifique hacia dónde se puede enviar la alerta. Se puede enviar una alerta a un usuario de Analytics, un grupo de Analytics o a una dirección de correo electrónico sin procesar o a un número de teléfono.<p><b>Importante</b> El número de teléfono debe estar precedido el signo “+” y un [código de país](https://countrycode.org/).</p><p>El correo electrónico que el usuario recibe una vez que se activa una alerta es similar al siguiente:</p><p>![Correo electrónico de alerta](assets/alerts-email.PNG)</p> |
| **[!UICONTROL Fecha de caducidad]** | Establezca la fecha y la hora en que desea que la alerta caduque. |
| **[!UICONTROL Retraso]** | El tiempo necesario hasta que se completen los datos y hasta que estén disponibles para la creación de informes en Customer Journey Analytics varía según la organización, y suele oscilar entre 3 y 9 horas después del evento de datos. Para que las alertas sean precisas, los datos de evento de un intervalo de eventos determinado deben estar completos, lo que significa que Adobe ya no recibe datos de evento para el intervalo de eventos especificado.<p>Para tener en cuenta este retraso en el tiempo de ingesta, las alertas tienen un retraso predeterminado de 9 horas antes de enviarse.</p><p>Puede ajustar el retraso predeterminado de 9 horas a cualquier valor entre 0 y 24 horas. Sin embargo, si se reduce el retraso por debajo de 9 horas, puede indicar que está generando informes sobre datos incompletos, lo que da como resultado una información de alerta inexacta.</p><p>Considere los siguientes puntos a la hora de reducir el tiempo de demora:</p><ul><li>**Comprender la disponibilidad de los datos frente a su integridad**: aunque es posible que algunos datos estén disponibles para generar informes antes, todos los datos por lotes se incorporan en un conjunto de datos de Platform solo después de un período de 3 a 9 horas. Para que las alertas sean precisas, la ingesta de datos debe ser completa, con todos los datos por lotes disponibles en el conjunto de datos.</li><li>**Determine cuánto tiempo tardan los datos en estar completos y disponibles en el conjunto de datos**: los tiempos de ingesta de datos difieren según la organización. Asegúrese de que el tiempo de demora que elija para el envío de alertas sea el mismo o menos frecuente que el tiempo que tardan los datos por lotes en estar disponibles en el conjunto de datos de Platform<!--add link? -->.</li><p>**Sugerencia:** la forma más precisa de saber el tiempo necesario para completar e incorporar todos los datos por lotes en el conjunto de datos de Platform es consultar a los ingenieros de datos de su organización.</p><p>También puede hacerse una idea general de cuánto tiempo tarda el envío por lotes en su organización en estar disponible en el conjunto de datos de Platform creando la siguiente tabla de forma libre en Analysis Workspace:</p><ol><li>En una tabla de forma libre de Analysis Workspace, añada una métrica de [!UICONTROL **Eventos**] y una dimensión de [!UICONTROL **Día**].</li><li>Desglose la dimensión [!UICONTROL **Día**] mediante una dimensión [!UICONTROL **Horas**].<p>Las horas que carecen de datos se mostrarán como 0.</p></li></ol><li>**Tener en cuenta los errores en los cálculos**: si reduce el tiempo de demora predeterminado, le recomendamos que configure el retraso durante al menos una hora más que el tiempo que tarda su organización en completar la ingesta de datos. Por ejemplo, si hay un demora de 3 horas hasta que se complete la ingesta de datos, debe establecer el retraso en 4 horas.</li></ul><p>Para obtener más información, consulte [Los tiempos de ingesta de datos varían en Customer Journey Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md#data-ingestion-times-vary-in-customer-journey-analytics) en el artículo [Comparación de características de alertas: Customer Journey Analytics y Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md). |
| **[!UICONTROL Enviar una alerta cuando]** | [!UICONTROL **Se active cualquiera de estas métricas**]: arrastre y suelte las métricas (incluidas las métricas calculadas) aquí para crear activadores para la alerta.<p>Aparezca un mensaje **&quot;componentes incompatibles&quot;** si no todas las métricas, las dimensiones o los segmentos de la alerta son compatibles con la vista de datos seleccionada.  </p><p>Determine el umbral que debe superar la métrica para que se establezca la alerta. Puede ajustar este valor a un umbral y, a continuación, a una de las condiciones siguientes:</p><ul><li>existe anomalía</li><li>anomalía por encima de lo esperado</li><li>anomalía por debajo de lo esperado</li><li>mayor o igual que</li><li>menor o igual que</li><li>cambia por un</li><li>Puede establecer el umbral en 90 %, 95 %, 99 %, 99,75 % y 99,9 %.</li></ul><p>[!UICONTROL **Con todos estos segmentos**]: Arrastre y suelte los segmentos o dimensiones para agregar segmentos. Por ejemplo, si añade un segmento “Solo dispositivos móviles” significa que la regla solamente se activará para los dispositivos móviles. Puede agregar segmentos adicionales mediante una instrucción AND. Puede añadir las reglas AND u OR si hace clic en el icono de engranaje.</p><p>Consulte [Alertas - casos de uso](/help/components/c-intelligent-alerts/alerts-use-cases.md) para ver casos de uso por ejemplo.</p> |
| **[!UICONTROL Vista previa]** | La vista previa de alertas interactiva le muestra con qué frecuencia, aproximada, se activará una alerta en función de las experiencias pasadas.<p>Por ejemplo, si establece la granularidad de tiempo a diario, en la vista previa podrá ver cuántas veces se habrá activado una alerta para una métrica en particular durante los últimos 30 o 31 días.</p><p>Si considera que se habrían activado demasiadas alertas, puede ajustar el umbral en el [Administración de alertas](/help/components/c-intelligent-alerts/alert-manager.md).</p><p>![](assets/alert-preview.png){width="50%"}</p> |
