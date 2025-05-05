---
description: Cómo hacer preguntas de análisis de datos sobre la documentación de Customer Journey Analytics
title: Visualización de datos con Data Insights Agent en Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
hidefromtoc: true
hide: true
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: 9f954709a3dde01b4e01581e34aece07fe0256b1
workflow-type: tm+mt
source-wordcount: '1878'
ht-degree: 5%

---

# Visualización de datos con Data Insights Agent en Customer Journey Analytics

Data Insights Agent, que forma parte del asistente de IA de Customer Journey Analytics, es un agente de conversación de IA generativo que responde de forma rápida y eficaz a las preguntas sobre sus datos. Crea visualizaciones relevantes en Analysis Workspace utilizando componentes de la vista de datos y utilizando los datos reales.

El uso de Data Insights Agent para responder preguntas centradas en los datos en Analysis Workspace puede ahorrar incontables horas que, de lo contrario, podría dedicar a la creación manual de visualizaciones en Analysis Workspace y a familiarizarse con los componentes de las vistas de datos.

![Data Insights Agent en el asistente de IA](assets/cja-ai-asst-da.gif)

## Funciones dentro y fuera de ámbito para Beta

### Funciones de Beta en el ámbito

| Función admitida | Descripción |
| --- | --- |
| **Generar y actualizar visualizaciones** | Genera una tabla de forma libre y una visualización asociada (como una línea, una barra, un anillo, etc.).<p>Ejemplo: *¿Cuál es el beneficio entre SKU de febrero a mayo?* |
| **Tipos de visualización compatibles** | <ul><li>Línea</li><li>De varias líneas</li><li>Tabla de forma libre</li><li>Barra</li><li>Anillo</li><li>Número de resumen</li></ul> |
| **Detección de mensajes fuera del ámbito** | Si envía un mensaje que está fuera de ámbito, como &quot;exportar este proyecto&quot;, Data Insights Agent le responde indicando que la pregunta está fuera de ámbito. |
| **aclarando preguntas** | Si hace una pregunta que no tiene contexto suficiente para que Data Insights Agent responda o es demasiado genérica, Data Insights Agent responde con una pregunta aclaratoria o con opciones sugeridas. Ejemplos: <p>**Componentes**<ul><li>Métrica: *¿A qué métrica de &quot;ingresos&quot; se refería?*</li><li>Dimension: *¿En cuál de las siguientes &quot;regiones&quot; desea centrarse?*</li><li>Segmento: *¿Qué segmento de &quot;cuenta&quot; quería aplicar?*</li><li>Intervalo de fechas: *Por &quot;mes pasado&quot;, ¿se refería al último mes completo o a los últimos 30 días?*</li></ul>**elementos de Dimension**: ¿a qué &quot;nombre de tienda&quot; se refería? (Por ejemplo, Almacenar #5274, Almacenar #2949, etc.). |
| **Giro múltiple** | Data Insights Agent responde a una solicitud con el contexto de cualquier solicitud anterior, lo que permite a los usuarios actualizar las visualizaciones y hacer preguntas de seguimiento. Ejemplo: <ul><li>Preguntar 1: *Eventos de tendencia de marzo.*</li><li>Mensaje 2: *Mostrarme los datos de marzo a abril*</li></ul> |
| **Verificabilidad** | La verificabilidad y corrección de los datos se puede confirmar mediante la tabla de forma libre y la visualización de datos generadas. Por ejemplo, si un usuario pregunta *Tendencia de pedidos el mes pasado*, puede confirmar que la métrica (&quot;pedidos&quot;) y el intervalo de fechas (&quot;el mes pasado&quot;) correctos se seleccionaron en el panel, la visualización de datos y la tabla de forma libre recién generados. |
| **Comentarios** | <ul><li>Pulgares hacia arriba</li><li>Pulgar hacia abajo</li><li>Indicador</li></ul> |

### Funciones de Beta fuera de ámbito

| Función no admitida | Descripción |
| --- | --- |
| **Resumen o respuesta en línea** | Data Insights Agent no puede responder en línea en el carril de chat con una respuesta resumida de una petición de datos del usuario. Ejemplos de mensajes fuera de ámbito:<ul><li>*Dame un resumen de los datos de mi última solicitud.*</li><li>*Resumir los elementos destacados de la visualización de líneas.*</li></ul> |
| **aclarando preguntas** | Las preguntas de aclaración se limitan a componentes y elementos de dimensión. Data Insights Agent no puede aclarar cosas como vistas de datos, visualizaciones, granularidad de datos, comparación y ámbito. Cuando no se pueden aclarar preguntas, el agente toma de forma predeterminada lo que es más probable que pida. Si devuelve una visualización o una granularidad de datos inesperada, puede utilizar la capacidad de varias vueltas/actualización para ajustar la visualización y los datos. |
| **Acciones/capacidades de Workspace** | Data Insights Agent no puede realizar acciones para un usuario en Workspace aparte de crear y actualizar visualizaciones. Por ejemplo, no puede realizar ninguna de las siguientes acciones:<ul><li>Botones de la interfaz de usuario de la acción contextual (añadir a gráfico, nuevo panel, nueva tabla)</li><li>Compartir</li><li>Exportar</li><li>Descargar</li><li>Administrar preferencias de usuario</li><li>Depurar</li><li>Administrar vista de datos</li><li>Aplicación de paneles de Analytics</li><li>Atribución</li></ul> |
| **Tipos de visualización no compatibles** | <ul><li>Flujo</li><li>Visita en orden previsto</li><li>Tabla de cohortes</li><li>Área, área apilada</li><li>Barra apilada</li><li>Viñeta</li><li>Combo</li><li>Histograma</li><li>Barras horizontales, barras horizontales apiladas</li><li>Resumen de métricas clave</li><li>Puntos</li><li>Cambio de resumen</li><li>Texto</li><li>Gráfico de rectángulos</li><li>Venn</li></ul> |

## Administración del acceso a Data Insights Agent en Customer Journey Analytics

Los siguientes parámetros rigen el acceso a Data Insights Agent en Customer Journey Analytics:

* **Acceso a la solución**: Data Insights Agent está disponible para los clientes de Customer Journey Analytics Prime y Ultimate. No está disponible en Adobe Analytics.

* **Acceso contractual**: Si no puede usar Data Insights Agent en el asistente de IA, póngase en contacto con el administrador de su organización o con el representante de cuentas de Adobe. Antes de que su organización pueda utilizar Data Insights Agent, debe aceptar ciertos términos legales relacionados con GenAI.

* **Permisos**: en [!UICONTROL Adobe Admin Console], el permiso de [!UICONTROL Herramientas de informes] **[!UICONTROL Asistente de IA: visualización de datos]** determina el acceso a esta herramienta. Un [administrador de perfil de producto](https://helpx.adobe.com/es/enterprise/using/manage-product-profiles.html) debe seguir estos pasos en [!UICONTROL Admin Console]:
   1. Vaya a **[!UICONTROL Admin Console]** > **[!UICONTROL Productos y servicios]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Perfiles de productos]**
   1. Seleccione el título del perfil de producto para el que desea proporcionar acceso a [!UICONTROL AI Assistant: Product Knowledge].
   1. En el perfil de producto específico, seleccione **[!UICONTROL Permisos]**.
   1. Seleccione ![Editar](/help/assets/icons/Edit.svg) para editar **[!UICONTROL Herramientas de creación de informes]**.
   1. Seleccione ![AddCircle](/help/assets/icons/AddCircle.svg) para agregar **Asistente de IA: Conocimiento del producto** y **Asistente de IA: Análisis de datos** a **[!UICONTROL Elementos de permiso incluidos]**.

      ![Agregar permiso](assets/ai-assistant-permissions.png).

   1. Seleccione **[!UICONTROL Guardar]** para guardar el esquema.

Consulte [Control de acceso](/help/technotes/access-control.md#access-control) para obtener más información.

## Acceso a Data Insights Agent en el asistente de IA

1. Vaya a [experience.adobe.com](https://experience.adobe.com/) e inicie sesión con su Adobe ID.

2. Seleccione **Customer Journey Analytics** en la página de inicio de Experience Cloud.

3. Seleccione **[!UICONTROL Proyecto en blanco]** en el banner de la parte superior de la página de proyectos para abrir un nuevo proyecto en blanco.

4. Asegúrese de que la vista de datos seleccionada para el panel sea la misma vista de datos que se habilitó para usar con las pruebas de Data Insights Agent for Beta.

   Si no está seguro, póngase en contacto con el canal de Slack de Beta.

5. Seleccione el icono de chat AI Assistant en el área superior derecha de la página.

   Si no ve el icono de chat, póngase en contacto con el administrador para que pueda habilitar las siguientes funciones en Admin Console:

   * **[!UICONTROL Asistente de IA: conocimiento del producto]**

   * **[!UICONTROL Asistente de IA: análisis de datos]**

   Para obtener más información, los administradores pueden ver [estas instrucciones](https://experienceleague.adobe.com/es/docs/experience-platform/ai-assistant/access).

   ![icono del Asistente de IA](/help/assets/ai-asst-icon.png)

6. En el cuadro de diálogo **[!UICONTROL Preguntar por Customer Journey Analytics]** que aparece en la parte inferior de la página, haga una pregunta sobre visualización de datos con Data Insights Agent.

   Para obtener más información, consulte los siguientes ejemplos.

### Ejemplo 1

Por ejemplo, supongamos que le interesan los pedidos que recibió su empresa en julio.

**Mensaje:** Escriba *&quot;Tendencia de pedidos en julio.&quot;*

![petición de datos de IA](/help/assets/ai-asst-prompt1.png)

**Respuesta:** Data Insights Agent recopila información consultando los datos de la vista de datos, incluidas las métricas y los componentes. Traduce el mensaje a las dimensiones y métricas correctas dentro del rango de datos.

Como puede ver, generó automáticamente un gráfico de líneas y una tabla de forma libre para mostrar los pedidos de julio.

![Respuesta a la solicitud: gráfico de líneas y tabla de forma libre](/help/assets/ai-asst-result.png)

### Ejemplo 2

A continuación, desea ver cómo se comparan los ingresos por región.

**Mensaje:** En la ventana del mensaje, escriba *&quot;Mostrar ingresos por región.&quot;*

**Respuesta:** Data Insights Agent entiende de forma inteligente que por &quot;región&quot; se entiende &quot;región del cliente&quot;. Genera un gráfico de barras que muestra mejor los ingresos por región:

![Gráfico de barras](/help/assets/ai-asst-result2.png)

### Ejemplo 3

A continuación, además de comprender los ingresos por región, también desea ver datos para obtener beneficios por región. En lugar de repetir la solicitud anterior, puede solicitar a Data Insights Agent que actualice la visualización más reciente y la tabla de forma libre.

**Mensaje:** En la ventana del mensaje, escriba *&quot;Agregar ganancia.&quot;*

**Respuesta:** El gráfico de **[!UICONTROL barras]** sigue proporcionando la respuesta más concisa, pero la métrica de beneficios se ha agregado como una columna en la tabla de forma libre:

![Gráfico de barras](/help/assets/ai-asst-result4.png)

### Ejemplo 4

Por último, veamos los ingresos por categoría de producto.

**Mensaje:** En la ventana del mensaje, escriba *&quot;Proporción de ingresos por categoría de producto.&quot;*

**Respuesta:** De nuevo, Data Insights Agent elige la visualización más adecuada, en este caso la visualización **[!UICONTROL Anillo]**, para responder a la pregunta.

![Anillo](/help/assets/ai-asst-result3.png)

## Ejemplos de solicitudes de visualización de datos

A continuación, se muestran algunos ejemplos de indicadores comunes y las visualizaciones utilizadas por Data Insights Agent para responder a dichos mensajes.

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

Data Insights Agent procesa el contexto proporcionado por cada mensaje de usuario e intenta responder de forma inteligente con la visualización y los componentes más adecuados en una tabla de forma libre.

Las respuestas pueden variar en función de las palabras y frases específicas utilizadas en el mensaje, y los ligeros cambios de idioma pueden dar lugar a resultados diferentes.

Para obtener los mejores resultados, tenga en cuenta las siguientes directrices:

* Sea específico: incluya términos exactos para reducir la respuesta. A continuación se muestra un ejemplo de un mensaje específico: &quot;Ventas del mes pasado en California&quot;

* Utilice métricas y segmentos claros: Añadir métricas específicas (como &quot;Ingresos&quot;), dimensiones (como &quot;nombre del sitio web&quot;), segmentos (como &quot;usuarios de iPhone&quot;) e intervalos de fechas (como &quot;últimos tres meses&quot;) ayuda a Data Insights Agent a centrarse en los datos correctos.

* Formule preguntas directas: La formulación de preguntas directamente facilita que Data Insights Agent proporcione perspectivas claras y relevantes. A continuación se muestra un ejemplo de cómo hacer una pregunta directa en un mensaje: &quot;¿Cuál es el ingreso promedio por categoría de producto este año?&quot;

Revise la siguiente tabla de términos y frases de ejemplo que puede utilizar en las peticiones de datos con Data Insights Agent, junto con los tipos de respuesta que puede esperar.

Estos ejemplos están diseñados para ayudarle a familiarizarse con cómo palabras o estructuras específicas pueden influir en la salida del agente de Data Insight, lo que garantiza perspectivas más precisas y valiosas. Data Insights Agent utiliza IA generativa, por lo que las visualizaciones o los datos seleccionados pueden variar ligeramente según los indicadores similares.

| Resultado deseado | Ejemplo de términos y frases |
| --- | --- |
| Visualización de número de resumen | <ul><li>Total</li></ul> |
| Comparar componentes | <ul><li>Comparar</li><li>VS</li><li>Contraste</li><li>Semana a semana</li><li>Mes tras mes</li><li>Trimestre tras trimestre</li><li>Año tras año</li></ul> |
| Visualización de anillo | <ul><li>Proporción</li><li>Cuota de</li><li>Distribución</li><li>Porcentaje</li><li>Contribución</li><li>Parte</li><li>Piezas</li></ul> |
| Visualización de líneas | <ul><li>Tendencia</li><li>[Métrica] en [intervalo de tiempo]</li></ul> |
| Visualización de barras | <ul><li>[Métrica] por [Dimension]</li></ul> |

## Expectativas de prueba de Beta y comentarios solicitados

Después de formular cada pregunta, revise cuidadosamente la respuesta proporcionada por el asistente. Es crucial evaluar las visualizaciones generadas de forma exhaustiva antes de proporcionar comentarios.

Tenga en cuenta lo siguiente al evaluar una respuesta desde Data Insights Agent:

* Plantilla o respuesta del carril del chat: evalúe la respuesta textual proporcionada. ¿Es la respuesta adecuada teniendo en cuenta el contexto del mensaje?

* Visualización/gráfico: evalúe la visualización. ¿Es la visualización adecuada o esperada para su pregunta, o habría esperado una visualización diferente?

* Tabla de forma libre: Evalúe la tabla de forma libre. ¿Son correctos los datos de la tabla de forma libre? ¿Se desglosan los datos donde se solicitan? ¿Los segmentos aplicados son los solicitados o los esperados?

* Mensaje de error / Fuera de ámbito: si se proporciona un mensaje de error genérico que indica que la pregunta está fuera de ámbito, proporcione comentarios sobre si cree que el mensaje fuera de ámbito es adecuado, en función de su pregunta. ¿El mensaje estaba realmente en el ámbito?

**En cada respuesta, dé un pulgar hacia arriba o hacia abajo, según la respuesta.**

Siguiendo la selección de pulgares hacia arriba o hacia abajo, seleccione los cuadros de comentarios de selección múltiple correspondientes. Si desea proporcionar comentarios adicionales, agregue notas en el cuadro de texto abierto.

## Preguntas y contacto

* Envíe preguntas y comentarios en el canal de Slack de Beta: #data-insights-agent-in-cja-beta
