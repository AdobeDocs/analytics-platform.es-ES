---
description: Cómo hacer preguntas de análisis de datos sobre la documentación de Customer Journey Analytics
title: Data Analysis AI Assistant en Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
hidefromtoc: true
hide: true
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: ac3ec479938acf509bbd26be282b75e75dd49c33
workflow-type: tm+mt
source-wordcount: '1650'
ht-degree: 3%

---

# Visualización de datos con el asistente de IA en Customer Journey Analytics

El asistente de IA de Customer Journey Analytics es un agente de conversación de IA generativo que responde de forma rápida y eficaz a las preguntas sobre sus datos. Crea visualizaciones relevantes en Analysis Workspace utilizando componentes de la vista de datos y utilizando los datos reales.

El uso del Asistente de IA para responder preguntas centradas en datos en Analysis Workspace puede ahorrar incontables horas que, de lo contrario, podría dedicar a crear visualizaciones manualmente en Analysis Workspace y a familiarizarse con los componentes de las vistas de datos.

![Asistente de análisis de datos](assets/cja-ai-asst-da.gif)

## Funciones dentro y fuera de ámbito para la versión de Alpha

### Funciones de Alpha en el ámbito

| Función admitida | Descripción |
| --- | --- |
| **Generar y actualizar visualizaciones** | Genera una tabla de forma libre y una visualización asociada (como una línea, una barra, un anillo, etc.).<p>Ejemplo: *¿Cuál es el beneficio entre SKU de febrero a mayo?* |
| **Tipos de visualización compatibles** | <ul><li>Línea</li><li>De varias líneas</li><li>Tabla de forma libre</li><li>Barra</li><li>Anillo</li><li>Número de resumen</li></ul> |
| **Detección de mensajes fuera del ámbito** | Si envía un mensaje que está fuera de ámbito, como &quot;exportar este proyecto&quot;, el Ayudante le responde indicando que la pregunta está fuera de ámbito. |
| **aclarando preguntas** | Si hace una pregunta que no tiene contexto suficiente para que la responda el asistente de IA, o es demasiado genérica, el asistente de IA responde con una pregunta aclaratoria u opciones sugeridas. Ejemplos: <p>**Componentes**<ul><li>Métrica: *¿A qué métrica de &quot;ingresos&quot; se refería?*</li><li>Dimension: *¿En cuál de las siguientes &quot;regiones&quot; desea centrarse?*</li><li>Filtro: *¿Qué filtro de &quot;cuenta&quot; quería aplicar?*</li><li>Intervalo de fechas: *Por &quot;mes pasado&quot;, ¿se refería al último mes completo o a los últimos 30 días?*</li></ul>**elementos de Dimension**: ¿a qué &quot;nombre de tienda&quot; se refería? (Por ejemplo, Almacenar #5274, Almacenar #2949, etc.). |
| **Giro múltiple** | El asistente de IA responde a un mensaje con el contexto de cualquier mensaje anterior, lo que permite a los usuarios actualizar las visualizaciones y hacer preguntas de seguimiento. Ejemplo: <ul><li>Preguntar 1: *Eventos de tendencia de marzo.*</li><li>Mensaje 2: *Mostrarme los datos de marzo a abril*</li></ul> |
| **Verificabilidad** | La verificabilidad y corrección de los datos se puede confirmar mediante la tabla de forma libre y la visualización de datos generadas. Por ejemplo, si un usuario pregunta *Tendencia de pedidos el mes pasado*, puede confirmar que la métrica (&quot;pedidos&quot;) y el intervalo de fechas (&quot;el mes pasado&quot;) correctos se seleccionaron en el panel, la visualización de datos y la tabla de forma libre recién generados. |
| **Comentarios** | <ul><li>Pulgares hacia arriba</li><li>Pulgar hacia abajo</li><li>Indicador</li></ul> |

### Funciones de Beta fuera de ámbito

| Función no admitida | Descripción |
| --- | --- |
| **Resumen o respuesta en línea** | El asistente de IA no puede responder en línea en el carril de chat con una respuesta de resumen de una petición de datos del usuario. Ejemplos de mensajes fuera de ámbito:<ul><li>*Dame un resumen de los datos de mi última solicitud.*</li><li>*Resumir los elementos destacados de la visualización de líneas.*</li></ul> |
| **aclarando preguntas** | Las preguntas de aclaración se limitan a componentes y elementos de dimensión. El asistente de IA no puede aclarar cosas como vistas de datos, visualizaciones, granularidad de datos, comparación y ámbito. Cuando no se pueden aclarar las preguntas, el Ayudante toma como valor predeterminado lo que más probablemente esté pidiendo. Si devuelve una visualización o una granularidad de datos inesperada, puede utilizar la capacidad de varias vueltas/actualización para ajustar la visualización y los datos. |
| **Acciones/capacidades de Workspace** | El asistente de IA no puede realizar acciones para un usuario en Workspace aparte de crear y actualizar visualizaciones. Por ejemplo, no puede realizar ninguna de las siguientes acciones:<ul><li>Botones de la interfaz de usuario de la acción contextual (añadir a gráfico, nuevo panel, nueva tabla)</li><li>Compartir</li><li>Exportar</li><li>Descargar</li><li>Administrar preferencias de usuario</li><li>Depurar</li><li>Administrar vista de datos</li><li>Aplicación de paneles de Analytics</li><li>Atribución</li></ul> |
| **Tipos de visualización no compatibles** | <ul><li>Flujo</li><li>Visita en orden previsto</li><li>Tabla de cohortes</li><li>Área, área apilada</li><li>Barra apilada</li><li>Viñeta</li><li>Combo</li><li>Histograma</li><li>Barras horizontales, barras horizontales apiladas</li><li>Resumen de métricas clave</li><li>Dispersión</li><li>Cambio de resumen</li><li>Texto</li><li>Gráfico de rectángulos</li><li>Venn</li></ul> |

<!---## Feature access in the Customer Journey Analytics UI

[Do we even need this section for the Alpha?]

The following parameters govern access to Data visualization in AI Assistant:

* **Solution access**: Data visualization in AI Assistant is available for Customer Journey Analytics Prime and Ultimate customers. It is not available in Adobe Analytics. 

It is also available in Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP and additional Experience Platform apps.

* **Contractual access**: If you are not able to use AI Assistant, please contact your organization's administrator or Adobe Account Representative. Before your organization can use Data visualization in AI Assistant, your must agree to certain GenAI-related legal terms.

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL AI Assistant: Data visualization]** permission determines access to this tool. A [product profile admin](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) needs to follow these steps in the [!UICONTROL Admin Console]:
   1. Navigate to **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**
   1. Select the title of the product profile for which you want to provide access to [!UICONTROL AI Assistant: Product Knowledge].
   1. In the specific product profile, select **[!UICONTROL Permissions]**.
   1. Select ![Edit](/help/assets/icons/Edit.svg) to edit **[!UICONTROL Reporting Tools]**.
   1. Select ![AddCircle](/help/assets/icons/AddCircle.svg) to add **AI Assistant: Data visualization** to **[!UICONTROL Included permission items]**.
   
      ![Add permission](assets/ai-assistant-permissions.png).

   1. Select **[!UICONTROL Save]** to save the permissions.

See [Access control](/help/technotes/access-control.md#access-control) for more information.--->

## Acceso y uso de la visualización de datos en el asistente de IA

1. Vaya a [experience.adobe.com](https://experience.adobe.com/) e inicie sesión con su Adobe ID.

2. Seleccione **Customer Journey Analytics** en la página de inicio de Experience Cloud.

3. Seleccione **[!UICONTROL Proyecto en blanco]** en el banner de la parte superior de la página de proyectos para abrir un nuevo proyecto en blanco.

4. Asegúrese de que la vista de datos seleccionada para el panel sea la misma vista de datos que se habilitó para usar con el Asistente de IA para pruebas de Beta.

   Si no está seguro, póngase en contacto con el canal de Slack de Beta.

5. Seleccione el icono de chat AI Assistant en el área superior derecha de la página.

   Si no ve el icono de chat, póngase en contacto con el administrador para que pueda habilitar las siguientes funciones en Admin Console:

   * **[!UICONTROL Asistente de IA: conocimiento del producto]**

   * **[!UICONTROL Asistente de IA: análisis de datos]**

   Para obtener más información, los administradores pueden ver [estas instrucciones](https://experienceleague.adobe.com/en/docs/experience-platform/ai-assistant/access).

   ![icono del Asistente de IA](/help/assets/ai-asst-icon.png)

6. En el cuadro de diálogo **[!UICONTROL Preguntar por Customer Journey Analytics]** que aparece en la parte inferior de la página, haga una pregunta sobre visualización de datos en el Asistente de IA.

   Para obtener más información, consulte los siguientes ejemplos.

### Ejemplo 1

Por ejemplo, supongamos que le interesan los pedidos que recibió su empresa en julio.

**Mensaje:** Escriba *&quot;Tendencia de pedidos en julio.&quot;*

![petición de datos de IA](/help/assets/ai-asst-prompt1.png)

**Respuesta:** El Asistente para IA recopila perspectivas consultando los datos de la vista de datos, incluidas las métricas y los componentes. Traduce el mensaje a las dimensiones y métricas correctas dentro del rango de datos.

Como puede ver, generó automáticamente un gráfico de líneas y una tabla de forma libre para mostrar los pedidos de julio.

![Respuesta a la solicitud: gráfico de líneas y tabla de forma libre](/help/assets/ai-asst-result.png)

### Ejemplo 2

A continuación, desea ver cómo se comparan los ingresos por región.

**Mensaje:** En la ventana del mensaje, escriba *&quot;Mostrar ingresos por región.&quot;*

**Respuesta:** El Asistente de inteligencia artificial entiende que por &quot;región&quot; se entiende &quot;región del cliente&quot;. Genera un gráfico de barras que muestra mejor los ingresos por región:

![Gráfico de barras](/help/assets/ai-asst-result2.png)

### Ejemplo 3

A continuación, además de comprender los ingresos por región, también desea ver datos para obtener beneficios por región. En lugar de repetir la solicitud anterior, puede pedir al asistente de IA que actualice la visualización más reciente y la tabla de forma libre.

**Mensaje:** En la ventana del mensaje, escriba *&quot;Agregar ganancia.&quot;*

**Respuesta:** El gráfico de **[!UICONTROL barras]** sigue proporcionando la respuesta más concisa, pero la métrica de beneficios se ha agregado como una columna en la tabla de forma libre:

![Gráfico de barras](/help/assets/ai-asst-result4.png)

### Ejemplo 4

Por último, veamos los ingresos por categoría de producto.

**Mensaje:** En la ventana del mensaje, escriba *&quot;Proporción de ingresos por categoría de producto.&quot;*

**Respuesta:** De nuevo, la visualización de datos en el Asistente de IA elige la visualización más adecuada, en este caso la visualización **[!UICONTROL Anillo]**, para responder a la pregunta.

![Anillo](/help/assets/ai-asst-result3.png)

## Ejemplos de solicitudes de visualización de datos

A continuación se muestran algunos ejemplos de indicadores comunes y las visualizaciones utilizadas por el asistente de IA para responder a dichos mensajes.

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

El asistente de IA procesa el contexto proporcionado por cada mensaje de usuario e intenta responder de forma inteligente con la visualización y los componentes más adecuados en una tabla de forma libre.

Las respuestas pueden variar en función de las palabras y frases específicas utilizadas en el mensaje, y los ligeros cambios de idioma pueden dar lugar a resultados diferentes.

Para obtener los mejores resultados, tenga en cuenta las siguientes directrices:

* Sea específico: incluya términos exactos para reducir la respuesta. A continuación se muestra un ejemplo de un mensaje específico: &quot;Ventas del mes pasado en California&quot;

* Utilice métricas y filtros claros: Añadir métricas específicas (como &quot;Ingresos&quot;), dimensiones (como &quot;nombre del sitio web&quot;), filtros (como &quot;usuarios de iPhone&quot;) e intervalos de fechas (como &quot;últimos tres meses&quot;) ayuda al asistente de IA a centrarse en los datos correctos.

* Formule preguntas directas: La formulación de preguntas directamente facilita que el asistente de IA proporcione perspectivas claras y relevantes. A continuación se muestra un ejemplo de cómo hacer una pregunta directa en un mensaje: &quot;¿Cuál es el ingreso promedio por categoría de producto este año?&quot;

Revise la siguiente tabla de términos y frases de ejemplo que puede utilizar en las peticiones de datos con visualización de datos en el Ayudante de IA, junto con los tipos de respuesta que puede esperar.

Estos ejemplos están diseñados para ayudarle a familiarizarse con cómo palabras o estructuras específicas pueden influir en la salida del asistente de IA, lo que garantiza perspectivas más precisas y valiosas. El asistente de IA utiliza IA generativa, por lo que las visualizaciones de los datos seleccionados pueden variar ligeramente según los indicadores similares.

| Resultado deseado | Ejemplo de términos y frases |
| --- | --- |
| Visualización de número de resumen | <ul><li>Total</li></ul> |
| Comparar componentes | <ul><li>Comparar</li><li>VS</li><li>Contraste</li><li>Semana a semana</li><li>Mes tras mes</li><li>Trimestre tras trimestre</li><li>Año tras año</li></ul> |
| Visualización de anillo | <ul><li>Proporción</li><li>Cuota de</li><li>Distribución</li><li>Porcentaje</li><li>Contribución</li><li>Parte</li><li>Piezas</li></ul> |
| Visualización de líneas | <ul><li>Tendencia</li><li>[Métrica] en [intervalo de tiempo]</li></ul> |
| Visualización de barras | <ul><li>[Métrica] por [Dimension]</li></ul> |

## Expectativas de prueba de Beta y comentarios solicitados

Después de formular cada pregunta, revise cuidadosamente la respuesta proporcionada por el asistente. Es crucial evaluar las visualizaciones generadas de forma exhaustiva antes de proporcionar comentarios.

Tenga en cuenta lo siguiente al evaluar una respuesta del asistente de IA:

* Plantilla o respuesta del carril del chat: evalúe la respuesta textual proporcionada por el asistente. ¿Es la respuesta adecuada teniendo en cuenta el contexto del mensaje?

* Visualización/gráfico: evalúe la visualización. ¿Es la visualización adecuada o esperada para su pregunta, o habría esperado una visualización diferente?

* Tabla de forma libre: Evalúe la tabla de forma libre. ¿Son correctos los datos de la tabla de forma libre? ¿Se desglosan los datos donde se solicitan? ¿Los filtros aplicados son los solicitados o los esperados?

* Mensaje de error / Fuera de ámbito: si se proporciona un mensaje de error genérico que indica que la pregunta está fuera de ámbito, proporcione comentarios sobre si cree que el mensaje fuera de ámbito es adecuado, en función de su pregunta. ¿El mensaje estaba realmente en el ámbito?

**En cada respuesta, dé un pulgar hacia arriba o hacia abajo, según la respuesta.**

Siguiendo la selección de pulgares hacia arriba o hacia abajo, seleccione los cuadros de comentarios de selección múltiple correspondientes. Si desea proporcionar comentarios adicionales, agregue notas en el cuadro de texto abierto.

## Preguntas y contacto

* Envíe preguntas y comentarios en el canal de Slack de Alpha: #cja-assistant-data-alpha
