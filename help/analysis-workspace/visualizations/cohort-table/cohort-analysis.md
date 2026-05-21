---
title: Resumen de tabla de cohorte
description: Aprenda a profundizar en los datos de su audiencia y a dividir esos datos en grupos relacionados mediante el análisis de cohorte. Utilice el análisis de cohorte en Analysis Workspace.
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
role: User
TQID: https://experienceleague.adobe.com/3WB5sKKSaLe9VvAe6rlCTUqDYsG3kiqLCN-KaEtIlDw
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: addf009e-030a-4310-8534-776a3e62ed48
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 754
ht-degree: 91%

---

# Información general de la tabla de cohorte {#cohort-table-overview}

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
>abstract="Agrupe a los usuarios en función de la finalización de un evento y, a continuación, analice su participación actual y las cancelaciones a lo largo del tiempo. Especifique los ajustes adicionales como granularidad, tipo de análisis de cohorte y si desea utilizar o no el cálculo móvil. Puede establecer opciones avanzadas para crear una tabla de latencia o una cohorte de dimensión personalizada basada en una dimensión seleccionada."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artículo documenta la tabla de cohorte en_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._<br/>_Consulte [Tabla de cohorte](https://experienceleague.adobe.com/es/docs/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis) para la_ ![versión de AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** de este artículo._

>[!ENDSHADEBOX]


Una *cohorte* es un grupo de personas que comparten características en común durante un periodo especificado. La visualización ![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL Tabla de cohorte]** es útil, por ejemplo, cuando desea saber cómo se relaciona una cohorte con una marca. Puede identificar fácilmente los cambios en tendencias y responder en consecuencia. (Las explicaciones de [!UICONTROL análisis de cohorte] se encuentran disponibles en la web, como en la [Guía básica de análisis de cohorte](https://es.wikipedia.org/wiki/Cohort_analysis)).

Después de crear un informe de cohorte, puede depurar sus componentes (dimensiones, métricas y segmentos específicos), y luego compartir el informe de cohorte con quien desee. Consulte [Depurar y compartir](/help/analysis-workspace/curate-share/curate.md).

Ejemplos de lo que puede hacer con una [!UICONTROL Tabla de cohorte]:

* Inicie campañas diseñadas para estimular una acción deseada.
* Modificar el presupuesto de marketing en el momento justo del ciclo de vida del cliente.
* Reconocer cuándo debe finalizar una prueba o una oferta, para maximizar el valor.
* Obtener ideas para pruebas A/B en áreas como precios, ruta de actualización, etc.

La [!UICONTROL Tabla de cohorte] está disponible para todos los clientes de Customer Journey Analytics con derechos de acceso a [!UICONTROL Analysis Workspace].


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Análisis de cohorte en Analysis Workspace](https://experienceleague.adobe.com/es/docs/analytics-learn/tutorials/analysis-workspace/cohort-analysis/cohort-analysis-workspace){target="_blank"} para ver un vídeo de demostración.

{{videoaa}}

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>El [!UICONTROL Análisis de cohorte] no admite métricas no segmentables (incluidas las métricas calculadas), métricas de números no enteros (como Ingresos), u Ocurrencias. En el [!UICONTROL Análisis de cohorte] solo se pueden utilizar las métricas que se pueden utilizar en los segmentos, y solo se pueden incrementar de 1 en 1.

Las tablas de cohortes de Customer Journey Analytics admiten métricas de base doble (o cualquier métrica numérica). Por ejemplo, Purchase.Value (un valor doble) se puede utilizar como métrica de inclusión/retorno. Además, todas las métricas que se pasan a Adobe Experience Platform a través del conector de origen de Analytics también son dobles.

## Funcionalidades de la tabla de cohorte

En las secciones siguientes se describen las funciones de Análisis de cohorte que permiten un control preciso de las cohortes que está creando.

Para obtener información más detallada sobre cómo crear una cohorte y ejecutar un informe de [!UICONTROL Análisis de cohorte], consulte [Configuración de una tabla de cohorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md).

### Tabla de retención

Una tabla de cohorte de [!UICONTROL retención] devuelve personas: cada celda de datos muestra el número sin procesar y el porcentaje de personas en la cohorte que realizó la acción durante ese periodo de tiempo. Se pueden incluir hasta 3 métricas y hasta 10 segmentos.

![Informe de cohorte de retención que muestra las unidades y el porcentaje de personas de la cohorte.](assets/retention-report.png)

### Tabla de pérdida

Una tabla de cohorte de [!UICONTROL cancelación] es la inversa de una tabla de retención y muestra a las personas que abandonaron o que no llegaron a satisfacer los criterios de regreso de su cohorte a lo largo del tiempo. Se pueden incluir hasta 3 métricas y hasta 10 segmentos.

![Tabla de cancelación que muestra las unidades y el porcentaje de personas que no cumplen los criterios de regreso para una cohorte.](assets/churn-report.png)

### Cálculo móvil

Puede calcular la retención o la cancelación basada en la columna anterior, no la columna incluida, que se denomina cálculo móvil.

![Informe de retención de cohorte que muestra los cálculos basados en una columna de datos anterior.](assets/retention-report-rolling.png)

### Tabla de latencias

Una tabla de latencia mide el tiempo que transcurre antes y después de que se produzca el evento de inclusión. Medir la latencia es una excelente herramienta para el análisis previo/posterior. La columna **[!UICONTROL Incluido]** está en el centro de la tabla y a ambos lados se muestran los periodos de tiempo antes y después del evento de inclusión.

![Informe de cohorte que muestra el tiempo transcurrido antes y después de un evento.](assets/retention-report-latency.png)

### Cohorte de dimensión personalizada

Cree cohortes basadas en una dimensión seleccionada y no en el tiempo (que es el comportamiento predeterminado). Utilice dimensiones como [!UICONTROL Ciudad geo], [!UICONTROL Canal de marketing], [!UICONTROL campaña], [!UICONTROL producto], [!UICONTROL página], [!UICONTROL región] o cualquier otra dimensión para mostrar cómo cambia la retención. En función de los diferentes valores de estas dimensiones.

![Un informe de cohorte que muestra un informe personalizado con dimensiones seleccionadas no es la cohorte predeterminada basada en el tiempo.](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[Configuración de una tabla de cohorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)
>

