---
description: Cómo realizar preguntas de análisis de datos acerca de la documentación de Customer Journey Analytics
title: Data Analysis AI Assistant en Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
hidefromtoc: true
hide: true
source-git-commit: ab8a4c65de59e725d7d181ee699d7a196988bf98
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 4%

---


# Data Analysis AI Assistant en Customer Journey Analytics - Alpha

Data Analysis AI Assistant es un agente de conversación inteligente y consciente del contexto que puede ayudarle a responder de forma más rápida y eficaz a las preguntas que pueda tener sobre sus datos de Analysis Workspace en Customer Journey Analytics.

El Ayudante examina todos los datos de una vista de datos, incluidos los distintos tipos de métricas y componentes, y traduce el mensaje a la dimensión, métrica e intervalo de fechas adecuados para este análisis. En lugar de tener que familiarizarse con los componentes de la vista de datos y, a continuación, arrastrar y soltar esos componentes en la mejor combinación para responder a su pregunta, simplemente puede escribir la pregunta en el asistente de IA.

## Funciones dentro y fuera de ámbito para la versión de Alpha

### Funciones en el ámbito

| Función admitida | Descripción |
| --- | --- |
| **Generar y actualizar visualizaciones** | Genera una tabla de forma libre y una visualización asociada (por ejemplo, una línea, una barra, un anillo, etc.).<p>Ejemplo: *¿Cuál es el beneficio entre SKU de febrero a mayo?* |
| **Tipos de visualización compatibles** | <ul><li>Línea</li><li>De varias líneas</li><li>De forma libre</li><li>Barra</li><li>Anillo</li><li>Número de resumen</li></ul> |
| **Detección de mensajes fuera del ámbito** | Si envía un mensaje que está fuera del ámbito, como &quot;exportar este proyecto&quot;, el Ayudante le responderá informándole de que la pregunta está fuera del ámbito. |
| **aclarando preguntas** | Si hace una pregunta que no tiene contexto suficiente para que la responda el asistente de IA, o es demasiado genérica, el asistente de IA responde con una pregunta aclaratoria y/o opciones sugeridas. Ejemplos: <p>**Componentes**<ul><li>Métrica: *¿A qué métrica de &quot;ingresos&quot; se refería?*</li><li>Dimension: *¿En cuál de las siguientes &quot;regiones&quot; desea centrarse?*</li><li>Filtro: *¿Qué filtro de &quot;cuenta&quot; quería aplicar?*</li><li>Intervalo de fechas: *Por &quot;mes pasado&quot;, ¿se refería al último mes completo o a los últimos 30 días?*</li></ul>**elementos de Dimension**: ¿A qué &quot;nombre de tienda&quot; se refería? (por ejemplo, #5274 de tienda, #2949 de tienda, etc.) |
| **Giro múltiple** | El asistente de IA responde a un mensaje con el contexto de los mensajes anteriores, lo que permite a los usuarios actualizar las visualizaciones y hacer preguntas de seguimiento. Ejemplo: *Mostrarme los datos de marzo a abril en su lugar.* |
| **Comentarios** | <ul><li>Pulgares hacia arriba</li><li>Pulgares hacia abajo</li><li>Indicador</li></ul> |

### Funciones fuera de ámbito

| Función no admitida | Descripción |
| --- | --- |
| **Resumen o respuesta en línea** | El asistente de IA no puede responder en línea en el carril de chat con una respuesta de resumen de una petición de datos del usuario.Ejemplo de peticiones de datos fuera de ámbito:<ul><li>*Dame un resumen de los datos de mi última solicitud.*</li><li>*Resumir los elementos destacados de la visualización de líneas.*</li></ul> |
| **aclarando preguntas** | Las preguntas de aclaración se limitan a componentes y elementos de dimensión. El asistente de IA no puede aclarar vistas de datos, visualizaciones, granularidad de datos, comparación, ámbito, etc. Sin aclarar preguntas, el Ayudante toma como valor predeterminado lo que es más probable que pida. Si devuelve una visualización o una granularidad de datos inesperada, puede utilizar la capacidad de varias vueltas y actualizaciones para ajustar la visualización y los datos. |
| **Acciones / Capacidades De Workspace** | El asistente de IA no puede realizar acciones para un usuario en Workspace aparte de crear y actualizar visualizaciones. Por ejemplo, no puede realizar ninguna de las siguientes acciones:<ul><li>Botones de la interfaz de usuario de la acción contextual (añadir a gráfico, nuevo panel, nueva tabla)</li><li>Compartir</li><li>Exportar</li><li>Descargar</li><li>Administrar preferencias de usuario</li><li>Depurar</li><li>Administrar vista de datos</li><li>Aplicación de paneles de Analytics</li><li>Atribución</li></ul> |
| **Tipos de visualización no compatibles** | <ul><li>Flujo</li><li>Visita en orden previsto</li><li>Tabla de cohortes</li><li>Área, área apilada</li><li>Barra apilada</li><li>Viñeta</li><li>Combo</li><li>Histograma</li><li>Barras horizontales, barras horizontales apiladas</li><li>Resumen de métricas clave</li><li>Dispersión</li><li>Cambio de resumen</li><li>Texto</li><li>Gráfico de rectángulos</li><li>Venn</li></ul> |
| **Explicación y verificabilidad** | Descripción o cita transparente de cómo el asistente de IA generó una respuesta y le proporciona una forma de confirmar que la respuesta es correcta. |

<!---## Feature access in the Customer Journey Analytics UI

[Do we even need this section for the Alpha?]

The following parameters govern access to the Data Analysis AI Assistant feature:

* **Solution access**: The Data Analysis AI Assistant is available for Customer Journey Analytics Prime and Ultimate customers. It is not available in Adobe Analytics. 

It is also available in Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP and additional Experience Platform apps.

* **Contractual access**: If you are not able to use AI Assistant, please contact your organization's administrator or Adobe Account Representative. Before your organization can use Data Analysis AI Assistant, your must agree to certain GenAI-related legal terms.

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL AI Assistant: Data Analysis]** permission determines access to this tool. A [product profile admin](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) needs to follow these steps in the [!UICONTROL Admin Console]:
   1. Navigate to **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**
   1. Select the title of the product profile for which you want to provide access to [!UICONTROL AI Assistant: Product Knowledge].
   1. In the specific product profile, select **[!UICONTROL Permissions]**.
   1. Select ![Edit](/help/assets/icons/Edit.svg) to edit **[!UICONTROL Reporting Tools]**.
   1. Select ![AddCircle](/help/assets/icons/AddCircle.svg) to add **AI Assistant: Data Analysis** to **[!UICONTROL Included permission items]**.
   
      ![Add permission](assets/ai-assistant-permissions.png).

   1. Select **[!UICONTROL Save]** to save the permissions.

See [Access control](/help/technotes/access-control.md#access-control) for more information.--->

## Acceso y uso del Data Analysis AI Assistant

1. Vaya a este vínculo para abrir Workspace en la organización IMS de Labs (en fase) e inicie sesión con su Adobe ID.

1. Haga clic en **[!UICONTROL Proyecto en blanco]** en el banner situado en la parte superior de la página de proyectos para abrir un nuevo proyecto en blanco.

1. Haga clic en el icono de chat del Ayudante de IA en la parte superior derecha.

   ![icono del Asistente de IA](/help/assets/ai-asst-icon.png)

1. En el cuadro de diálogo **[!UICONTROL Preguntar por el Customer Journey Analytics]** de la parte inferior, haga una pregunta de análisis de datos en el asistente de IA.

### Ejemplo 1

Por ejemplo, supongamos que le interesan los pedidos que recibió su empresa en julio.

1. Introduzca &quot;Mostrar pedidos en julio&quot;.

   ![petición de datos de IA](/help/assets/ai-asst-prompt1.png)

1. El asistente de IA ahora recopila perspectivas consultando los datos de la vista de datos, incluidas las métricas y los componentes. Traduce el mensaje a las dimensiones, métricas y rangos de datos adecuados.

   Como puede ver, ha generado automáticamente un gráfico de líneas y una tabla de forma libre que muestra los pedidos para julio.

   ![Respuesta a la solicitud: gráfico de líneas y tabla de forma libre](/help/assets/ai-asst-result.png)

### Ejemplo 2

A continuación, desea ver cómo se comparan los ingresos por región.

1. En la ventana del mensaje, introduzca &quot;Mostrar ingresos por región&quot;.

2. La IA es lo suficientemente inteligente como para comprender que por &quot;región&quot; se entiende &quot;región del cliente&quot;. Genera un gráfico de barras que muestra mejor los ingresos por región:

   ![Gráfico de barras](/help/assets/ai-asst-result2.png)

### Ejemplo 3

Ahora, veamos los ingresos por categoría de producto.

1. En la ventana de solicitud, introduzca &quot;Mostrar ingresos por categoría de producto&quot;.

2. De nuevo, el asistente de inteligencia artificial aplicada al análisis de datos selecciona la visualización más adecuada, en este caso la visualización **[!UICONTROL Anillo]**, para responder a la pregunta.

   ![Anillo](/help/assets/ai-asst-result3.png)

### Ejemplo 4

Por último, desea saber qué SKU es la más rentable y dónde debe invertir los recursos de marketing.

1. En la ventana del mensaje, pregunte &quot;¿Cuál es la ganancia en SKU de febrero a mayo?&quot;.

1. Un gráfico simple de **[!UICONTROL barras]** proporciona la respuesta más concisa:

   ![Gráfico de barras](/help/assets/ai-asst-result4.png)

## Ejemplos de solicitudes de análisis de datos

Estos son algunos ejemplos de indicadores comunes y de la visualización que utiliza el asistente de IA para responder a dichos mensajes.

| Mensaje de ejemplo | Visualización esperada |
| --- | --- |
| Mostrar mis ganancias en [Mes] | Línea<p>Si se solicita una tendencia o métrica dentro de un intervalo de tiempo determinado, de forma predeterminada, se devuelve una visualización de línea. |
| Tendencia de pedidos en [Mes] | Línea |
| Mostrar ingresos por región en [mes] | Barra |
| Porcentaje de ingresos por categoría de producto | Anillo |
| Pedidos por día de la semana, de enero a mayo | Barra |
| Mostrar pedidos por sexo, de marzo a junio | Barra |
| ¿Cuál es el beneficio entre SKU de febrero a mayo? | Barra |
| Ingresos por nombre de tienda en [Mes] | Barra |
| ¿Cuáles fueron mis 10 SKU principales por beneficio en [Mes]? | Barra |
| Proporción de compras por mes del año | Anillo |
| Beneficio total en [mes] | Número de resumen<p>Solicitar el &quot;total&quot; de una métrica en un intervalo de tiempo determinado debe devolver una visualización de Número de resumen. |


## Impulso de las prácticas recomendadas

Por determinar

## Expectativas de prueba del Alpha y comentarios solicitados

Después de formular cada pregunta, revise cuidadosamente la respuesta proporcionada por el asistente. Es crucial evaluar las visualizaciones generadas de forma exhaustiva antes de proporcionar comentarios.

Evalúe la respuesta: ¿la respuesta es correcta?

Si el asistente responde en el carril de chat: Evalúe la respuesta textual.

* Si se muestra una visualización/gráfico: evalúe la visualización. ¿Es la visualización adecuada/esperada para su pregunta?

* Si se muestra una tabla de forma libre: Evalúe la tabla de forma libre. ¿Son correctos los datos de la tabla de forma libre? ¿Se desglosan los datos donde se solicitan? ¿Los filtros aplicados son los solicitados o los esperados?

* Si se muestra un mensaje de error genérico que indica que la pregunta está fuera del ámbito, indique si cree que el mensaje fuera del ámbito es apropiado teniendo en cuenta su pregunta. ¿El mensaje estaba realmente en el ámbito?

Para cada respuesta, dé un pulgar hacia arriba o hacia abajo, según la respuesta

Después de la selección de los pulgares hacia arriba/hacia abajo, seleccione las casillas de comentarios de selección múltiple correspondientes. Si desea proporcionar comentarios adicionales, agregue notas en el cuadro de texto abierto.

## Preguntas y contacto

* Correo electrónico `taylorb@adobe.com` (PM)
* Envía preguntas y comentarios en el canal de Slack del Alpha: #aep-cja-ai-assistant-testers ???


