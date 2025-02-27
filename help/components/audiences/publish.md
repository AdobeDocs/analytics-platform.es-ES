---
title: Crear y publicar audiencias
description: Obtenga información sobre cómo publicar audiencias desde Customer Journey Analytics
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
feature: Audiences
role: User
source-git-commit: e444474d9f859f59613caa8fad06998372cdf742
workflow-type: tm+mt
source-wordcount: '1973'
ht-degree: 18%

---

# Crear y publicar audiencias {#create-and-publish-audiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_audiences_refreshfrequency"
>title="Frecuencia de actualización"
>abstract="Vea la frecuencia con la que se reevalúa el abono de un público.<br/>Los públicos únicos solo se evalúan una vez."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_audiences_audiencelimit"
>title="Límite de público"
>abstract="Los públicos actualizados están limitados a la frecuencia con la que se actualizan."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_refreshlookbackwindow"
>title="Actualizar ventana de retrospección"
>abstract="Defina el número de días de retrospectiva a partir de hoy en los que se evaluará a un público."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_audiencesizelimit"
>title="Límite de tamaño de público"
>abstract="Los públicos no pueden exceder un tamaño de 20 millones de miembros."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_namespacesincluded"
>title="Espacios de nombres incluidos"
>abstract="Las identidades de este público se comprenden en los espacios de nombres a continuación."

<!-- markdownlint-enable MD034 -->




En este tema se explica cómo crear y publicar audiencias identificadas en Customer Journey Analytics en [Perfil del cliente en tiempo real](https://experienceleague.adobe.com/es/docs/experience-platform/profile/home) en Adobe Experience Platform para la segmentación y personalización de clientes.

Lea esta [descripción general](/help/components/audiences/audiences-overview.md) para familiarizarse con el concepto de audiencias de Customer Journey Analytics.

## Creación y publicación de una audiencia {#create}

1. Para crear y publicar una audiencia, siga uno de estos procedimientos:

   | Método de creación | Detalles |
   | --- | --- |
   | Desde la interfaz **[!UICONTROL Audiencias]**. | Seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Audiencias]** en el menú principal de Customer Journey Analytics. Se muestra la interfaz Audiencias. Seleccione **[!UICONTROL Crear audiencia]** y se abrirá [!UICONTROL el generador de audiencias]. |
   | Desde una visualización en Analysis Workspace | Muchas visualizaciones en Analysis Workspace permiten crear una audiencia utilizando el menú contextual. Por ejemplo, puede seleccionar **[!UICONTROL Crear audiencia]** en el menú contextual de un elemento en una [tabla de forma libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) o en un nodo en [lienzo de Recorrido](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md).<p>Mediante este método se rellena previamente el filtro del Generador de audiencias con la dimensión o el elemento de dimensión que haya seleccionado.</p><p>Las siguientes visualizaciones le permiten crear una audiencia utilizando el menú contextual:</p><ul><li>[Tabla de cohorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)</li><li>[Visita en orden previsto](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)</li><li>[Flujo](/help/analysis-workspace/visualizations/c-flow/flow.md)</li><li>[Tabla de forma libre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)</li><li>[lienzo de Recorrido](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)</li><li>[Venn](/help/analysis-workspace/visualizations/venn.md)</li></ul><p>**Nota:** Las audiencias no pueden incluir métricas calculadas. Si intenta crear una audiencia que contenga una métrica calculada, esta no se incluye en la definición de la audiencia.</p> |
   | Desde la interfaz de usuario de creación/edición de filtros | Marque la casilla que dice **[!UICONTROL Crear una audiencia a partir de este filtro]**. Mediante este método se rellena previamente el filtro. Consulte [Crear filtros](/help/components/filters/create-filters.md) para obtener más información. |

   {style="table-layout:auto"}

1. Genere la audiencia con [Audience Builder](#audience-builder).

1. Interprete los datos con el panel [Vista previa de fecha](#data-preview).

1. Seleccione **[!UICONTROL [!UICONTROL Ver ID de muestra]]** para ver una muestra de los ID de esta audiencia. En el cuadro de diálogo **[!UICONTROL ID de muestra]** puede usar ![Buscar](/help/assets/icons/Search.svg) [!UICONTROL *Buscar ID de muestra*] para buscar ID de muestra.

1. Compruebe la configuración de la audiencia y seleccione **[!UICONTROL Publicar]**.
Recibirá un mensaje de confirmación que indica que la audiencia se ha publicado. La publicación tarda solo uno o dos minutos en mostrarse en Experience Platform.

1. Seleccione **[!UICONTROL Ver la audiencia en AEP]** dentro del mismo mensaje y se le redirigirá a la [interfaz de usuario del segmento](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/overview) en Adobe Experience Platform. Para obtener más información, vaya más abajo.

## Generador de audiencias

Configure estas opciones para definir o actualizar la audiencia.

![Captura de pantalla de la creación de una audiencia que muestra la configuración descrita en la siguiente sección.](assets/create-audience.png)

| Configuración | Descripción |
| --- | --- |
| ![Datos](/help/assets/icons/Data.svg) | Seleccione una vista de datos para utilizarla en la creación de audiencias. |
| **[!UICONTROL Nombre]** | Nombre de la audiencia. Por ejemplo, `Really Interested in Potential Car Buyers` |
| **[!UICONTROL Etiquetas]** | Las etiquetas que quiera asignar a la audiencia con fines organizativos. Puede seleccionar una o varias etiquetas preexistentes o introducir una nueva. |
| **[!UICONTROL Descripción]** | Una descripción de la audiencia para diferenciarla de otras. Por ejemplo, `Build an audience of really interested potential car buyers` |
| **[!UICONTROL Frecuencia de actualización]** | La frecuencia con la que desea actualizar la audiencia.<p/>Puede elegir entre <ul><li>**[!UICONTROL Audiencia única]**: audiencia (predeterminada) que no necesita ninguna actualización. Por ejemplo, esta opción podría resultar útil para campañas únicas específicas.<br/>Debe especificar un **[!UICONTROL intervalo de fecha único]**. Puede usar ![Calendario](/help/assets/icons/Calendar.svg) para especificar un intervalo de fechas.</li><li>Una audiencia refrescante. Puede seleccionar las siguientes opciones:<ul><li>**[!UICONTROL Cada 4 horas]** s: una audiencia que se actualiza cada 4 horas.</li><li>**[!UICONTROL Diario]**: una audiencia que se actualiza diariamente</li><li>**[!UICONTROL Semanal]**: una audiencia que se actualiza semanalmente.</li><li>**[!UICONTROL Mensual]**: una audiencia que se actualiza mensualmente</li></ul></li>Para actualizar audiencias, debe especificar:<ul><li>**[!UICONTROL Actualizar ventana retrospectiva]**. Defina el número de días de retrospectiva a partir de hoy en los que se evaluará una audiencia. Puede seleccionar entre las opciones o definir un Tiempo personalizado. El máximo es de 90 días.</li><li>**[!UICONTROL Fecha de caducidad]**: defina cuándo la audiencia deja de actualizar. Puede usar ![Calendario](/help/assets/icons/Calendar.svg) para seleccionar una fecha. El valor predeterminado es 1 año a partir de la fecha de creación. Las audiencias que caducan se tratan de manera similar a los informes programados que caducan. El administrador recibe un correo electrónico un mes antes de que la audiencia caduque.</li></ul> Tenga en cuenta que hay un límite de 75 a 150 actualizaciones de audiencia, según los derechos de Customer Journey Analytics.</li></ul> |
| **[!UICONTROL Filtro]** | Los filtros son la entrada principal a la audiencia. Arrastre y suelte uno o más filtros del panel ![Segmentación](/help/assets/icons/Segmentation.svg) **[!UICONTROL Filtro]** izquierdo en el área de Filtro. Puede usar ![Buscar](/help/assets/icons/Search.svg) [!UICONTROL *Filtros de búsqueda*] para buscar filtros. Se pueden agregar hasta 20 filtros. Los filtros se pueden unir con los operadores **[!UICONTROL And]** o **[!UICONTROL Or]**.<p>Al crear una audiencia a partir de una visualización en Analysis Workspace (como una tabla de forma libre o un lienzo de Recorrido), se conservan los filtros aplicados al panel o a la columna. Puede eliminar cualquier filtro que se aplique automáticamente.</p> |
| **[!UICONTROL Vista previa de datos]** | Seleccione ![Información](/help/assets/icons/Info.svg) para mostrar u ocultar la [Vista previa de datos](#data-preview) para el intervalo de fechas seleccionado. |

## Previsualización de datos

El panel Vista previa de datos proporciona la siguiente información.

| Elemento | Descripción |
| --- | --- |
| **[!UICONTROL Personas totales]** | Un número de resumen del total de personas en esta audiencia. El tamaño máximo es de 20 millones de personas. Si la audiencia supera los 20 millones de personas, debe reducir el tamaño de la audiencia para poder publicar. |
| **[!UICONTROL Límite de tamaño de audiencia]** | Visualización para mostrar a qué distancia del límite de 20 millones está esta audiencia. |
| **[!UICONTROL Retorno calculado de la audiencia]** | Puede utilizar este valor para redirigirse a las personas de esta audiencia que regresen a su sitio, aplicación móvil u otro canal.<p>Puede seleccionar el lapso de tiempo (**[!UICONTROL Próximos 7 días]**, **[!UICONTROL Próximas 2 semanas]** o **[!UICONTROL Próximo mes]**) para el número estimado de clientes que pueden regresar. |
| **[!UICONTROL Cálculo de retorno]** | Este número proporciona un número estimado de clientes que regresan durante el lapso de tiempo seleccionado. Este número se predice usando la tasa de pérdida histórica para esta audiencia. |
| **[!UICONTROL Previsualizar métricas]** | Puede seleccionar una métrica específica para ver cómo se basan los datos de esa métrica en la audiencia que defina.  Cada métrica de Vista previa muestra un total para la métrica en función de la audiencia. Y un porcentaje de la métrica basada en audiencia del total general de la métrica, según lo definido por la vista de datos. Por ejemplo, 381 personas (la métrica que seleccionó) son el resultado de su definición de audiencia, que es el 5 % del total de personas disponibles en la vista de datos. Puede seleccionar cualquier métrica que esté disponible en la vista de datos. |
| **[!UICONTROL Espacios de nombres incluidos]** | Los espacios de nombres específicos asociados a las personas de la audiencia. Algunos ejemplos son ECID, CRM ID, direcciones de correo electrónico, etc. |
| **[!UICONTROL Zona protegida]** | La [zona protegida de Experience Platform](https://experienceleague.adobe.com/es/docs/experience-platform/sandbox/home) en la que reside esta audiencia. Cuando publica esta audiencia en Platform, solo puede trabajar con la audiencia dentro de los límites de esta zona protegida. |

{style="table-layout:auto"}

## ¿Qué sucede después de crear y publicar una audiencia? {#after-audience-created}

Después de crear y publicar una audiencia en Customer Journey Analytics, esta estará disponible en Experience Platform. Un segmento de streaming de Adobe Experience Platform solo se crea si su organización está configurada para la segmentación de streaming.

* La audiencia de Platform comparte el mismo nombre y la misma descripción que la audiencia de Customer Journey Analytics. El nombre se adjunta con el ID de audiencia de Customer Journey Analytics para garantizar que la audiencia sea única.
* Cualquier cambio realizado en el nombre o la descripción de la audiencia en Customer Journey Analytics se reflejará en Experience Platform.
* Si se elimina una audiencia en Customer Journey Analytics, esta permanecerá disponible en Experience Platform hasta que caduque el perfil al que pertenece la audiencia. La pertenencia al perfil caduca pasados 420 días en el caso de audiencias únicas y después de 16 días en el de audiencias recurrentes.

## Consideraciones de latencia {#latency}

En varios puntos antes, durante y después de la publicación de audiencias, se pueden producir latencias. A continuación se muestra una información general de las posibles latencias.

![Latencias en la publicación de audiencias como se describe en esta sección.](assets/latency-diagram.svg)

|  | Punto de latencia | Duración de la latencia |
| --- | --- | --- |
| No se muestra | Conector de origen de Adobe Analytics a Analytics (A4T) | Hasta 30 minutos |
| 1 | Ingesta de datos en el lago de datos (desde el conector de origen de Analytics u otras fuentes) | Hasta 90 minutos |
| 2 | Ingesta de datos del lago de datos de Experience Platform en Customer Journey Analytics | Hasta 90 minutos |
| 3 | Publicación de audiencias en el Perfil del cliente en tiempo real, incluida la creación automática del segmento de flujo continuo y que permite que el segmento esté listo para recibir los datos. | Unos segundos |
| 4 | Frecuencia de actualización para audiencias | <ul><li>Actualización única (latencia inferior a 5 minutos)</li><li>Actualizar cada 4 horas, diariamente, semanalmente, mensualmente (la latencia va de la mano con la velocidad de actualización) |
| 5 | Creación del destino en Adobe Experience Platform: Activación del nuevo segmento | 1 a 2 horas |

{style="table-layout:auto"}

## Uso de audiencias de Customer Journey Analytics en Experience Platform {#audiences-aep}

Customer Journey Analytics toma todas las combinaciones de área de nombres e ID de la audiencia publicada y las transmite a Real-Time Customer Data Platform Customer Journey Analytics envía la audiencia a Experience Platform con la identidad principal establecida, según lo que se seleccionó como [!UICONTROL ID de persona] cuando se configuró la conexión.

A continuación, Real-Time Customer Data Platform examina cada combinación de área de nombres e ID y busca un perfil del que pueda formar parte. Un perfil es básicamente un clúster de áreas de nombres, ID y dispositivos vinculados. Si encuentra un perfil, agrega el área de nombres y el ID a los demás ID de este perfil como un atributo de pertenencia a un segmento. Por ejemplo, <user@adobe.com> se puede dirigir a todos sus dispositivos y canales. Si no se encuentra un perfil, se crea uno nuevo.

Para ver las audiencias de Customer Journey Analytics en Platform:

1. Expanda **[!UICONTROL Cliente]** en el panel izquierdo y, a continuación, seleccione **[!UICONTROL Audiencias]**. <!-- is there a folder called "Customer Journey Analytics? -->

1. Seleccione la ficha **[!UICONTROL Examinar]**.

1. Para localizar la audiencia publicada desde Customer Journey Analytics, realice una de las siguientes acciones:

   Opción ![Audiencias en el panel izquierdo](assets/aep-audiences.png)

   * Ordene la tabla por la columna **[!UICONTROL Origen]** para ver las audiencias que muestran [!UICONTROL **Customer Journey Analytics**] como origen.

   * Filtra ![Filter](/help/assets/icons/Filter.svg) por **[!UICONTROL Origin]** y selecciona **[!UICONTROL Customer Journey Analytics]**.

   * Utilice el campo de búsqueda ![Buscar](/help/assets/icons/Search.svg).

Para obtener más información sobre el uso de Audiences en Platform, consulte la sección [Audiencias](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder) en la [guía de la interfaz de usuario del generador de segmentos](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder) en la documentación de Experience Platform.


## Preguntas frecuentes {#faq}

Preguntas más frecuentes sobre la publicación de audiencias.

+++**¿Qué sucede si un usuario ya no es miembro de una audiencia en Customer Journey Analytics?**

En este caso, se envía un evento de salida a Experience Platform desde Customer Journey Analytics.

+++

+++**¿Qué sucede si se elimina una audiencia en Customer Journey Analytics?**

Cuando se elimina una audiencia de Customer Journey Analytics, esta ya no se muestra en la interfaz de usuario de Experience Platform. Sin embargo, los perfiles asociados a esa audiencia no se eliminan en Experience Platform.

+++

+++**Si no existe un perfil correspondiente en Real-Time Customer Data Platform, ¿se crea un perfil nuevo?**

Efectivamente.

+++

+++**¿Customer Journey Analytics envía los datos de audiencia como eventos de canalización o como un archivo sin formato que también va al lago de datos?**

Customer Journey Analytics transmite los datos a Real-Time Customer Data Platform a través de la canalización y estos datos también se recopilan en un conjunto de datos del sistema en el lago de datos.

+++

+++**¿Qué identidades envía Customer Journey Analytics?**

Los pares de identidad/área de nombres especificados en [Configuración de conexión](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection). Específicamente, el paso cuando un usuario selecciona el campo que desea utilizar como ID de persona.

+++

+++**¿Qué ID se elige como identidad principal?**

Véase más arriba. Solo se envía una identidad por cada persona de Customer Journey Analytics.

+++

+++**¿Real-Time Customer Data Platform también procesa los mensajes de Customer Journey Analytics? ¿Puede Customer Journey Analytics agregar identidades a un gráfico de identidades de perfil mediante el uso compartido de audiencias?**

No. Solo se envía una identidad por persona, por lo que Real-Time Customer Data Platform no tendría extremos de gráfico que consumir.

+++

+++**¿A qué hora del día se producen las actualizaciones diarias, semanales y mensuales? ¿Qué día de la semana se producen las actualizaciones semanales?**

El momento de la actualización se basa en el momento en el que se publicó la audiencia original y se ancla a esa hora del día (y al día de la semana o del mes).

+++

+++**¿Puede configurar el tiempo de actualización diario, semanal y mensual?**

No, los usuarios no pueden configurar la hora de la actualización.

+++


## Pasos siguientes

* Para administrar esta audiencia, vaya a la [interfaz de usuario de administración](/help/components/audiences/manage.md).
