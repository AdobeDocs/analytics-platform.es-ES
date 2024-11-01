---
description: Cómo hacer preguntas de análisis de datos a Customer Journey Analytics documentación
title: Asistente de IA de análisis de datos en Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
hidefromtoc: true
hide: true
source-git-commit: e18d8facbd54ae65d158ce2c72f47709ef988f8f
workflow-type: tm+mt
source-wordcount: '1422'
ht-degree: 4%

---


# Asistente de IA de análisis de datos en Customer Journey Analytics - Alpha

El asistente de IA de análisis de datos es un agente de conversación inteligente y sensible al contexto que puede ayudarlo a responder de manera más rápida y eficiente las preguntas que pueda tener sobre sus datos de Analysis Workspace en Customer Journey Analytics.

El Asistente examina todos los datos de un vista de datos, incluidos los diferentes tipos de métricas y componentes, y traduce el mensaje en el dimensión, el Métrica y el intervalo de fecha correctos para este análisis. En lugar de tener que familiarizarse con los componentes de vista de datos y, a continuación, arrastrar y soltar esos componentes en la mejor combinación para responder a su pregunta, simplemente puede escribir la pregunta en el Asistente de IA.

## Características internas ámbito y fuera de ámbito para la versión alfa

### Funciones en ámbito

| Función compatible | Descripción |
| --- | --- |
| **Cree y actualice visualizaciones** | Genera una tabla improvisada y una visualización asociada (por ejemplo, línea, barra, anillo, etc.).<p>Ejemplo: *¿Cuál es el beneficio en SKU de febrero a mayo?* |
| **Tipos de visualización compatibles** | <ul><li>Línea</li><li>Varias líneas</li><li>De forma libre</li><li>Barra</li><li>Anillo</li><li>Número de resumen</li></ul> |
| **Detección rápida fuera de ámbito** | Si envía un mensaje que está fuera del ámbito, como &quot;exportar este proyecto&quot;, el Ayudante le responderá informándole de que la pregunta está fuera del ámbito. |
| **aclarando preguntas** | Si hace una pregunta que no tiene contexto suficiente para que la responda el asistente de IA, o es demasiado genérica, el asistente de IA responde con una pregunta aclaratoria y/o opciones sugeridas. Ejemplos: <p>**Componentes**<ul><li>Métrica: *¿A qué métrica de &quot;ingresos&quot; se refería?*</li><li>Dimension: *¿En cuál de las siguientes &quot;regiones&quot; desea centrarse?*</li><li>Filtro: *¿Qué filtro de &quot;cuenta&quot; quería aplicar?*</li><li>Intervalo de fechas: *Por &quot;mes pasado&quot;, ¿se refería al último mes completo o a los últimos 30 días?*</li></ul>**elementos de Dimension**: ¿A qué &quot;nombre de tienda&quot; se refería? (por ejemplo, #5274 de tienda, #2949 de tienda, etc.) |
| **Giro múltiple** | El asistente de IA responde a un mensaje con el contexto de los mensajes anteriores, lo que permite a los usuarios actualizar las visualizaciones y hacer preguntas de seguimiento. Ejemplo: *Mostrarme los datos de marzo a abril en su lugar.* |
| **Comentarios** | <ul><li>Pulgares hacia arriba</li><li>Pulgares hacia abajo</li><li>Indicador</li></ul> |

### Funciones fuera de ámbito

| Función no admitida | Descripción |
| --- | --- |
| **Resumen o respuesta en línea** | El asistente de IA no puede responder en línea en el carril de chat con una respuesta de resumen de una petición de datos del usuario.Ejemplo de peticiones de datos fuera de ámbito:<ul><li>*Dame un resumen de las ideas de mi último mensaje.*</li><li>*Resumir los aspectos más destacados de la visualización de líneas.*</li></ul> |
| **Aclaración de preguntas** | Las preguntas aclaratorias se limitan a componentes y elementos dimensión. El Asistente de IA no puede aclarar vistas de datos, visualizaciones, Granularidad de datos, comparaciones, ámbito, etc. Sin aclarar las preguntas, el Asistente toma por defecto lo que probablemente esté pidiendo. Si devuelve una visualización inesperada o una Granularidad de datos, puede usar la capacidad de actualización o vuelta múltiple para ajustar la visualización y los datos. |
| **Acciones/capacidades de Espacio de trabajo** | El asistente de IA no puede realizar acciones para un usuario en Workspace aparte de crear y actualizar visualizaciones. Por ejemplo, no puede realizar ninguna de las siguientes acciones:<ul><li>Botones de la interfaz de usuario de la acción contextual (añadir a gráfico, nuevo panel, nueva tabla)</li><li>Compartir</li><li>Exportar</li><li>Descargar</li><li>Administrar preferencias de usuario</li><li>Depurar</li><li>Administrar vista de datos</li><li>Aplicación de paneles de Analytics</li><li>Atribución</li></ul> |
| **Tipos de visualización no admitidos** | <ul><li>Flujo</li><li>Visita en orden previsto</li><li>Tabla de cohortes</li><li>Área, área apilada</li><li>Barra apilada</li><li>Viñeta</li><li>Combo</li><li>Histograma</li><li>Barras horizontales, barras horizontales apiladas</li><li>Resumen de métricas clave</li><li>Dispersión</li><li>Cambio de resumen</li><li>Texto</li><li>Gráfico de rectángulos</li><li>Venn</li></ul> |
| **Explicabilidad y verificabilidad** | Transparente descripción o cita de cómo el Asistente de IA generó una respuesta y proporcionarle una forma de confirmar que la respuesta es correcta. |

## Acceso a funciones en la IU de Customer Journey Analytics

[¿igualado necesitamos esta sección para el Alfa?]

Los siguientes parámetros rigen el acceso a la función Data Analysis AI Assistant:

* **Acceso a** soluciones: El asistente de IA de análisis de datos está disponible para clientes de Customer Journey Analytics Prime y Ultimate. No está disponible en Adobe Analytics.

También está disponible en Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP y otras aplicaciones de Experience Platform.

* **Acceso contractual**: Si no puede usar el Asistente de IA, comuníquese con el administrador de su organización o con el representante de cuenta Adobe. Antes de que su organización pueda utilizar Data Analysis AI Assistant, su empresa debe aceptar ciertos términos legales relacionados con GenAI.

* **Permisos**: en [!UICONTROL Adobe Admin Console], el permiso de [!UICONTROL Herramientas de informes] **[!UICONTROL Asistente de IA: Análisis de datos]** determina el acceso a esta herramienta. Un [administrador de perfil de producto](https://helpx.adobe.com/es/enterprise/using/manage-product-profiles.html) debe seguir estos pasos en el [!UICONTROL Admin Console]:
   1. Vaya a **[!UICONTROL Admin Console]** > **[!UICONTROL Productos y servicios]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Perfiles de productos]**
   1. Seleccione el título del perfil de producto para el que desea proporcionar acceso a [!UICONTROL AI Assistant: Product Knowledge].
   1. En el perfil de producto específico, seleccione **[!UICONTROL Permisos]**.
   1. Seleccione ![Editar](/help/assets/icons/Edit.svg) para editar **[!UICONTROL Herramientas de informes]**.
   1. Seleccione ![AddCircle](/help/assets/icons/AddCircle.svg) para agregar **AI Assistant: Data Analysis** a **[!UICONTROL Elementos de permiso incluidos]**.

      ![Agregar permiso](assets/ai-assistant-permissions.png).

   1. Seleccione **[!UICONTROL Guardar]** para guardar los permisos.

Consulte [Control de acceso](/help/technotes/access-control.md#access-control) para obtener más información.

## Acceso y uso del Data Analysis AI Assistant

1. Vaya a este vínculo para abrir Workspace en la organización IMS de Labs (en fase) e inicie sesión con su Adobe ID.

1. Haga clic en **[!UICONTROL Proyecto en blanco]** en el banner situado en la parte superior de la página de proyectos para abrir un nuevo proyecto en blanco.

1. Haz clic en el icono de chat del Asistente de IA en la parte superior derecha.

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

1. En la ventana de solicitud, pregunte &quot;¿Cuál es el beneficio en SKU de febrero a mayo?&quot;

1. Un simple **[!UICONTROL gráfico de barras]** proporciona la respuesta más concisa:

   ![Gráfico de barras](/help/assets/ai-asst-result4.png)

## Ejemplos de solicitudes de análisis de datos

Estos son algunos ejemplos de mensajes comunes y qué visualización utiliza el asistente de IA para responder a esos avisos.

| Ejemplo de mensaje | Visualización esperada |
| --- | --- |
| Mostrar me ganancias en [Mes] | Línea<p>Solicitar una tendencia o Métrica dentro de un cierto intervalo de tiempo de forma predeterminada devuelve una visualización de líneas. |
| Tendencia de pedidos en [mes] | Línea |
| Mostrar ingresos por área geográfica en [mes] | Barra |
| Proporción de ingresos por producto categoría | Anillo |
| Pedidos por día de la semana, de enero a mayo | Barra |
| Mostrar pedidos por género, de marzo a junio | Barra |
| ¿Cuál es el beneficio en SKU de febrero a mayo? | Barra |
| Ingresos por nombre de tienda en [Mes] | Barra |
| ¿Cuáles fueron mis 10 SKU principales por beneficio en [Mes]? | Barra |
| Proporción de compras por mes del año | Anillo |
| Beneficio total en [mes] | Número de resumen<p>Solicitar el &quot;total&quot; de un Métrica en un cierto rango de tiempo debería devolver una visualización de número de resumen. |


## Recomendaciones

Por determinar

## Expectativas de pruebas alfa y comentarios solicitados

Después de plantear cada pregunta, revise cuidadosamente la respuesta proporcionada por el asistente. Es crucial evaluar las visualizaciones generadas de manera exhaustiva antes de proporcionar comentarios.

Evalúe la respuesta: ¿es correcta la respuesta dada?

Si el Asistente responde en la carril de chat: Evalúa la respuesta textual.

* Si se muestra una visualización/gráfico: evalúe la visualización. ¿Es la visualización adecuada/esperada para su pregunta?

* Si se muestra una tabla de forma libre: Evalúe la tabla de forma libre. ¿Son correctos los datos de la tabla de forma libre? ¿Se desglosan los datos donde se solicitan? ¿Los filtros aplicados son los solicitados o los esperados?

* Si se muestra un mensaje de error genérico que indica que la pregunta está fuera del ámbito, indique si cree que el mensaje fuera del ámbito es apropiado teniendo en cuenta su pregunta. ¿El mensaje estaba realmente en el ámbito?

Para cada respuesta, dé un pulgar hacia arriba o hacia abajo, según la respuesta

Después de la selección de los pulgares hacia arriba/hacia abajo, seleccione las casillas de comentarios de selección múltiple correspondientes. Si desea proporcionar comentarios adicionales, agregue notas en el cuadro de texto abierto.

## Preguntas y contacto

Correo electrónico `taylorb@adobe.com` (PM)
Envía preguntas y comentarios en el canal de Slack del Alpha: #aep-cja-ai-assistant-testers ???


