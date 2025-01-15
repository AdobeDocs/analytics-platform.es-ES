---
title: Configuración de la tabla de cohortes
description: Aprenda a utilizar una tabla de cohorte para el análisis de cohorte en Analysis Workspace
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
role: User
source-git-commit: f8abf388e0cb1e2e2eb9ff69fed2c542a26dcd66
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 33%

---

# Configuración de la tabla de cohortes {#cohort-table-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_button"
>title="Tabla de cohortes"
>abstract="Cree una visualización de cohorte para agrupar usuarios en función de la finalización de un evento y analice la participación en curso y las cancelaciones a lo largo del tiempo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_panel"
>title="Tabla de cohortes"
>abstract="Agrupe a los usuarios en función de la finalización de un evento y, a continuación, analice su participación actual y las cancelaciones a lo largo del tiempo.<br/><br/>**Parámetros **<br/>**Criterios de inclusión**: los componentes utilizados para definir las cohortes de visitantes iniciales.<br/>**Criterios de retorno**: los componentes utilizados para determinar si un visitante ha regresado."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*Este artículo documenta la tabla de cohorte en ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg)**Customer Journey Analytics**.<br/>Consulte [Tabla de cohortes](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis) para la versión de ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg)**Adobe Analytics**de este artículo.*

>[!ENDSHADEBOX]


Una *cohorte* es un grupo de personas que comparten características en común durante un período especificado. Una visualización de ![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL tabla de cohortes]** resulta útil, por ejemplo, cuando desea saber cómo se involucra una cohorte con una marca. Puede identificar fácilmente los cambios en tendencias y responder en consecuencia. (Las explicaciones de [!UICONTROL análisis de cohorte] se encuentran disponibles en la web, como en la [Guía básica de análisis de cohorte](https://es.wikipedia.org/wiki/Cohort_analysis)).

Después de crear un informe de cohorte, puede depurar sus componentes (dimensiones, métricas y filtros específicos), y luego compartir el informe de cohorte con quien desee. Consulte [Depurar y compartir](/help/analysis-workspace/curate-share/curate.md).

Ejemplos de lo que puede hacer con una [!UICONTROL tabla de cohorte]:

* Iniciar campañas diseñadas para generar una acción deseada.
* Modificar el presupuesto de marketing en el momento justo del ciclo de vida del cliente.
* Reconoce cuándo finalizar una prueba o una oferta para maximizar el valor.
* Obtener ideas para pruebas A/B en áreas como precios, ruta de actualización, etc.

[!UICONTROL La tabla de cohorte] está disponible para todos los clientes Customer Journey Analytics con derechos de acceso a [!UICONTROL Analysis Workspace].

+++ Vea un vídeo de demostración de la tabla de cohorte.

>[!VIDEO](https://video.tv.adobe.com/v/23990/?quality=12)

{{videoaa}}

+++

>[!IMPORTANT]
>
>[!UICONTROL Análisis de cohorte] no admite métricas no filtrables (incluidas las métricas calculadas), métricas no enteras (como Ingresos) u Ocurrencias. Solo se pueden usar las métricas de los filtros en [!UICONTROL Análisis de cohorte], y solamente se pueden incrementar de uno en uno.

Las tablas de cohorte de Customer Journey Analytics admiten métricas de doble base (o numéricas). Por ejemplo, Purchase.Value (un valor doble) se puede utilizar como Métrica de inclusión/devolución. Además, todas las métricas que se pasan a Adobe Experience Platform a través del conector de Source de Analytics también son dobles.

## Funcionalidades de tabla de cohorte

Las siguientes funciones permiten un control preciso de las cohortes que está creando:

### Tabla [!UICONTROL Retención]

Una tabla de cohorte [!UICONTROL Retención] devuelve personas: cada celda de datos muestra el número sin procesar y el porcentaje de personas en la cohorte que realizó la acción durante ese período de tiempo. Se pueden incluir hasta 3 métricas y hasta 10 filtros.

![Informe de cohorte de representación que muestra las unidades y el porcentaje de personas de la cohorte.](assets/retention-report.png)

### Tabla [!UICONTROL Pérdida]

Una tabla de cohorte [!UICONTROL Pérdida] es la inversa de una tabla de retención y muestra a las personas que abandonaron o que no llegaron a satisfacer los criterios de regreso de su cohorte a lo largo del tiempo. Se pueden incluir hasta 3 métricas y hasta 10 filtros.

![Tabla de pérdida que muestra las unidades y el porcentaje de personas que no cumplen los criterios de regreso para una cohorte.](assets/churn-report.png)

### [!UICONTROL Cálculo móvil]

Puede calcular la retención o la pérdida en función de la columna anterior, no de la columna incluida, que se denomina cálculo móvil.

![Informe de retención de cohorte que muestra cálculos basados en una columna de datos anterior.](assets/retention-report-rolling.png)

### Tabla [!UICONTROL Latencia]

Una tabla de latencia mide el tiempo transcurrido antes y después de que se produzca el evento de inclusión. La medición de latencia es una excelente herramienta para el análisis previo y posterior. La columna **[!UICONTROL Incluido]** está en el centro de la tabla y a ambos lados se muestran los periodos de tiempo antes y después del evento de inclusión.

![Informe de cohorte que muestra el tiempo transcurrido antes y después de un evento.](assets/retention-report-latency.png)

### [!UICONTROL Cohorte de dimensión personalizada]

Puede crear cohortes basadas en una dimensión seleccionada y no en el tiempo (el valor predeterminado). Utilice dimensiones como [!UICONTROL Ciudad geo], [!UICONTROL Canal de marketing], [!UICONTROL campaña], [!UICONTROL producto], [!UICONTROL página], [!UICONTROL región] o cualquier otra dimensión para mostrar cómo cambia la retención. En función de los diferentes valores de estas dimensiones.

![Un informe de cohorte que muestra un informe personalizado con dimensiones seleccionadas no es la cohorte predeterminada basada en el tiempo.](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[Configurar una tabla de cohorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).
>

