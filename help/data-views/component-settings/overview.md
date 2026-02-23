---
title: Configuración de componentes
description: Vea la configuración principal de un componente de vista de datos.
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '3739'
ht-degree: 56%

---

# Configuración de componentes {#component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_settings"
>title="Configuración de componentes"
>abstract="Vea y configure el nombre, la descripción y otras configuraciones relacionadas con un componente. Marque esta casilla para ocultar este componente de los usuarios no administradores en la creación de informes. Los administradores aún pueden acceder a él haciendo clic en **[!UICONTROL Mostrar todos los componentes]** en un proyecto de Workspace."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_contextlabels"
>title="Etiquetas de contexto"
>abstract="La eliminación de una etiqueta de contexto puede afectar a paneles o informes específicos donde se requiera el componente."

<!-- markdownlint-enable MD034 -->


La siguiente información describe la configuración que utiliza un componente de vista de datos.

![La configuración de componentes se describe en esta sección](../assets/component-settings.png)

| Configuración | Descripción/caso de uso |
| --- | --- |
| [!UICONTROL Tipo de componente] | Requerido. Permite cambiar un componente de Métrica a Dimension o viceversa. Si se cambia esta lista desplegable, el componente pasará al área de componentes incluidos correspondiente. |
| [!UICONTROL Nombre del componente] | Obligatorio. Permite especificar el nombre descriptivo que aparecerá en Analysis Workspace. Puede cambiar el nombre de un componente para darle un nombre específico para la vista de datos. |
| [!UICONTROL Descripción] | Opcional, pero recomendada. Proporciona información sobre el componente a otros usuarios. |
| [!UICONTROL Etiquetas] | Opcional. Le permite etiquetar el componente con etiquetas personalizadas o listas para usar para facilitar la búsqueda y el filtrado en la interfaz de usuario de Analysis Workspace. |
| [!UICONTROL Etiquetas de contexto] | Opcional. Un menú desplegable de [etiquetas de contexto](#context-labels) definidas por el sistema que se pueden aplicar a un componente. |
| [!UICONTROL Nombre del campo de esquema] | Nombre del campo de esquema. |
| [!UICONTROL Tipo de conjunto de datos] | Requerido. Campo no editable que muestra el tipo de conjunto de datos (evento, búsqueda o perfil) del que procede el componente. |
| [!UICONTROL Conjunto de datos] | Campo no editable que muestra el conjunto de datos desde el que se originó el componente. Este campo puede contener varios conjuntos de datos. |
| [!UICONTROL Tipo de esquema] | Campo no editable que muestra el tipo de datos del componente. Aunque puede utilizar cualquier tipo de campo de esquema admitido en Platform, no todos los tipos de campos son compatibles con Customer Journey Analytics. Se admiten los siguientes tipos de datos: `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String` y `Boolean`. Solo se permite el tipo de datos de esquema `String` en los conjuntos de datos de búsqueda en este momento. |
| [!UICONTROL ID de componente] | Requerido. La [API de Customer Journey Analytics](https://www.adobe.io/cja-apis/docs) utiliza este campo para hacer referencia al componente. Cada componente de una vista de datos debe ser único. Adobe genera automáticamente un ID para cada componente; sin embargo, puede hacer clic en el icono de edición y modificar el ID del componente. Al cambiar este ID de componente, se rompen todos los proyectos existentes de Workspace que contienen este componente. Aunque cada componente necesita un ID único en una sola vista de datos, puede utilizar el mismo ID de componente en otras vistas de datos. Si utiliza el mismo ID de componente en otras vistas de datos, puede hacer que los proyectos del Espacio de trabajo sean compatibles en todas las vistas de datos. <br/>Para los componentes basados en perfiles y búsquedas, el ID del componente tiene un prefijo de ID basado en el ID del conjunto de datos (por ejemplo: `642b28fcc1f0ee1c074265a0.person.name.firstName`). Si desea reutilizar un componente basado en perfiles o búsquedas, como `person.name.firstName`, en el proyecto de Workspace y configure este componente en diferentes vistas de datos, asegúrese de cambiar el nombre del ID del componente de forma exclusiva (por ejemplo: `myUniqueID.person.name.firstName`) en las vistas de datos. |
| [!UICONTROL Ruta] | Requerido. Campo no editable que muestra la ruta de esquema de la que procede el componente. |
| [!UICONTROL Etiquetas de uso de datos] | Cualquier etiqueta de uso de datos asignada a este componente en Adobe Experience Platform. [Más información](/help/data-views/data-governance.md). |
| [!UICONTROL Ocultar componente en creación de informes] | Permite depurar el componente fuera de la vista de datos para los usuarios que no son administradores. Los administradores aún pueden acceder a él haciendo clic en [!UICONTROL Mostrar todos los componentes] en un proyecto de Analysis Workspace. |

{style="table-layout:auto"}



>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuración del tipo de componente](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/data-views/component-type-settings-in-data-views){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


## Etiquetas de contexto

Las etiquetas de contexto son etiquetas definidas por el sistema aplicadas a componentes dentro de una vista de datos. Cuando se aplican etiquetas de contexto a componentes (dimensiones o métricas), se indica a Customer Journey Analytics que utilice automáticamente estos componentes etiquetados como de contexto en determinadas visualizaciones o funciones.

Las etiquetas de contexto permiten proporcionar un contexto semántico a fragmentos individuales de datos.  En general, Customer Journey Analytics no necesita conocer el significado semántico de una dimensión o métrica para realizar su análisis.  Sin embargo, algunas situaciones (plantillas de proyecto y algunas visualizaciones seleccionadas) requieren que Customer Journey Analytics comprenda el significado semántico para realizar algún tipo de análisis. Las etiquetas de contexto se crean para esas situaciones.

Las etiquetas de contexto funcionan en el nivel de componente (dimensión o métrica) y permiten una gran flexibilidad dentro de la vista de datos para el cliente. Por ejemplo, puede asignar una etiqueta de contexto a una dimensión después de aplicar varias transformaciones de posprocesamiento a un campo. O incluso a una dimensión basada en un campo derivado.  Las etiquetas de contexto proporcionan una capa de abstracción sobre los componentes y los campos.

Por motivos de comodidad, las etiquetas de contexto predeterminadas inteligentes se aplican automáticamente a los componentes en función de campos con una ruta XDM específica. Por ejemplo, la etiqueta de contexto **[!UICONTROL Commerce: Product Category]** se aplica automáticamente a una dimensión **[!UICONTROL Category name]** basada en la ruta de esquema `productListItems.productCategories.categoryName`. Sin embargo, puede mover la etiqueta de contexto a un componente diferente sin ningún problema.

Para optimizar las plantillas de proyecto proporcionadas por Adobe, varias integraciones (como Journey Optimizer, Content Analytics y más) configuran vistas de datos en las que los componentes listos para usar se construyen de una manera específica. Y las etiquetas de contexto adecuadas se aplican automáticamente. De nuevo, puede mover cualquiera de esas etiquetas de contexto a otros componentes que se crean en la vista de datos y se utiliza el componente personalizado en su lugar.

Las etiquetas de contexto también son relevantes para la divulgación de las plantillas de proyecto. Las plantillas de proyecto enseguida se dan cuenta de la base de los informes para varios casos de uso creados específicamente. Sin embargo, no todas las plantillas tienen sentido para todas las vistas de datos y no se desea mostrar plantillas no aplicables. Las etiquetas de contexto se utilizan para mostrar plantillas basadas en si las etiquetas de contexto se incluyen en la vista de datos seleccionada.  Simplemente puede agregar más etiquetas de contexto a la vista de datos (componentes), y habrá más plantillas disponibles. O quite etiquetas de contexto para ocultar plantillas específicas.

>[!NOTE]
>
>Puede aplicar más de una etiqueta de contexto a un componente, pero no puede aplicar una etiqueta de contexto a varios componentes dentro de una vista de datos.
>

Las ventajas de las etiquetas de contexto son:

* **Comodidad**: no tiene que volver a seleccionar el mismo componente en cada panel o visualización.
* **Desbloquea la funcionalidad**: algunas visualizaciones (como [Mapa](/help/analysis-workspace/visualizations/map.md)) requieren saber qué componente es la latitud y la longitud. La asignación de etiquetas de contexto revela esa información en la visualización.
* **Coherencia**: todas las personas de su organización que trabajen en uno o más proyectos basados en una vista de datos que utilice etiquetas de contexto obtendrán el mismo comportamiento.
* **Visibilidad de características y plantillas**: Algunas visualizaciones y características solo aparecen cuando se asigna la etiqueta de contexto adecuada. Por ejemplo:

   * Una visualización [Map](/help/analysis-workspace/visualizations/map.md) solo se muestra correctamente cuando Customer Journey Analytics sabe qué componentes representan latitud y longitud.
   * Las [plantillas](/help/analysis-workspace/templates/use-templates.md) específicas solo están visibles cuando se aplican las etiquetas de contexto correctas y los componentes asociados están disponibles.

Las etiquetas de contexto pueden ser necesarias en las siguientes situaciones:

* Para definir un conjunto de componentes, puede usar en informes de experimentación con el [Panel de experimentación](/help/analysis-workspace/c-panels/experimentation.md) en proyectos de Analysis Workspace.

  Para obtener más información, consulte [Integración con Journey Optimizer](/help/integrations/ajo.md#data-view) e [Creación de informes de Target](/help/integrations/at.md) para obtener más información.

* Para definir un conjunto de componentes, puede usar en la visualización [Map](/help/analysis-workspace/visualizations/map.md) en proyectos de Analysis Workspace.

  Para obtener más información, consulte [Agregar etiquetas de contexto en vistas de datos](/help/analysis-workspace/visualizations/map.md#add-context-labels-in-data-views) en [Mapa](/help/analysis-workspace/visualizations/map.md).

  **Nota**: la visualización del mapa se encuentra en la fase de prueba limitada de la versión y es posible que aún no esté disponible en su entorno.

* Para mostrar [plantillas proporcionadas por Adobe](/help/analysis-workspace/templates/use-templates.md). Es posible que algunas plantillas proporcionadas por Adobe no funcionen porque algunos componentes no están en la vista de datos.

  Para cada componente que falta, existe una etiqueta de contexto coincidente disponible en la vista de datos. Debe agregar la etiqueta de contexto coincidente a un componente que ya esté en la vista de datos. O bien, debe agregar un nuevo componente a la vista de datos y agregar la etiqueta de contexto al componente (si no se ha proporcionado ya automáticamente).

  Para obtener más información, consulte [Añadir componentes que faltan a la vista de datos para una plantilla determinada](/help/analysis-workspace/templates/create-templates.md#add-missing-components-to-the-data-view-for-a-given-template) en el artículo [Creación y administración de plantillas](/help/analysis-workspace/templates/create-templates.md).


Están disponibles los siguientes grupos de etiquetas de contexto, cada uno con una lista de etiquetas de contexto específicas.

+++ Campaign

| Nombre | Descripción |
|------|-------------|
| Código de seguimiento | Código de seguimiento. |
| Instancias de código de seguimiento | Seguimiento de instancias de código. |

+++

+++ Comercio

| Nombre | Descripción |
|------|-------------|
| Adiciones al carro de compras | Adiciones al carro de compras |
| Aperturas del carro de compras | Se abre el carro de compras. |
| Eliminaciones del carro de compras | Eliminaciones del carro de compras |
| Vistas del carro de compras | Vistas del carro de compras |
| Cierres de compra | Cierres de compra. |
| Pedidos | Pedidos. |
| Producto | Producto. |
| Categoría del producto | Categoría de producto. |
| Vistas del producto | Vistas del producto. |
| Ingresos | Ingresos. |
| Tienda | Almacenar. |
| Unidades | Unidades. |

+++

+++ Experimentación

| Nombre | Descripción |
|------|-------------|
| Experimento de experimentación | Un experimento es un conjunto de variaciones de una experiencia que se expusieron a los usuarios finales para determinar cuál es mejor mantener de forma perpetua. |
| Variante de experimento | La variante es una de las dos o más alteraciones en la experiencia de un usuario final que se comparan con el fin de identificar la mejor alternativa. |

+++

+++ Medios

| Nombre | Descripción |
|------|-------------|
| ID de contenido | ID de contenido. |
| Tiempo invertido en contenido | Tiempo invertido en contenido. |
| Episodio | Episodio. |
| Tipo de evento | Tipo de evento. |
| Tiempo invertido en contenido | Tiempo invertido en contenido. |
| Temporada | Temporada. |
| Segundos desde la última llamada | Segundos desde la última llamada. |
| Show | Mostrar. |
| Tiempo para el inicio | Hora de inicio. |
| Duración total del búfer | Duración total del búfer. |
| Duración de la pausa | Duración total de la pausa. |
| Duración del vídeo | Duración del vídeo. |
| Nombre del vídeo | Nombre del vídeo. |

+++

+++ Centro de llamadas

| Nombre | Descripción |
|------|-------------|
| Nombre del centro de llamadas | Nombre del centro de llamadas. |
| Costes de llamada | Costes de llamadas. |
| Horas de llamada | Horas de llamadas. |
| Duración de la llamada | Duración de la llamada. |
| Motivo de la llamada | Razón de la llamada. |
| Puntuación de la encuesta de llamadas | Puntuación de encuesta de llamada. |
| Llamadas | Llamadas. |

+++

+++ Demográfico

| Nombre | Descripción |
|------|-------------|
| Género | Género. |

+++

+++ Entorno

| Nombre | Descripción |
|------|-------------|
| Explorador | Explorador. |
| Tipo de explorador | Tipo de explorador. |
| Idioma | Idioma. |
| Sistema operativo | Sistema operativo. |
| Grupo del sistema operativo | Grupo de sistemas operativos. |
| Nombre del sistema operativo | Nombre del sistema operativo. |

+++

+++ General

| Nombre | Descripción |
|------|-------------|
| Nombre de la acción | Nombre de la acción. |
| Acciones | Acciones. |
| Canal de interacción | Canal de interacción. |

+++

+++ Información geográfica

| Nombre | Descripción |
|------|-------------|
| Ciudad geográfica | Ciudad geográfica. |
| País geográfico | País geográfico. |
| DMA geográfico | Geo dma. |
| Región geográfica | Región geográfica. |
| Latitud | Latitud. |
| Longitud | Longitud. |
| Punto de interés | Punto de interés. |
| Estado | Estado. |

+++

+++ Canal de marketing

| Nombre | Descripción |
|------|-------------|
| Canal de primer contacto | Canal de primer contacto. |
| Detalles de canal de primer contacto | Detalles de canal de primer contacto. |
| Canal de último contacto | Canal de último contacto. |
| Detalles de canal de último contacto | Detalles de canal de último contacto. |
| Canal de marketing | Canal de marketing. |

+++

+++ Móvil

| Nombre | Descripción |
|------|-------------|
| ID de aplicación | ID de aplicación. |
| Operador de telefonía móvil | Operador de telefonía móvil. |
| Bloqueos de móvil | Bloqueos de Mobile. |
| Nombre de dispositivo móvil | Nombre del dispositivo móvil. |
| Tipo de dispositivo móvil | Tipo de dispositivo móvil. |
| Nombre de mensaje in-app de móvil | Nombre del mensaje del dispositivo móvil en la aplicación. |
| Instalaciones en móvil | Instalaciones móviles. |
| Lanzamientos en móvil | Lanzamientos móviles. |
| Fabricante de dispositivos móviles | Fabricante del móvil. |
| Cancelaciones de mensajes de móvil | El mensaje móvil se cancela. |
| Clics en mensajes de móvil | Clics en mensajes móviles. |
| Impresiones de mensajes de móvil | Impresiones de mensajes móviles. |
| Adhesión a mensajes push de móvil | Inclusión de mensaje push móvil. |
| Nombre de mensaje push de móvil | Nombre del mensaje push móvil. |
| Actualizaciones en móvil | Actualizaciones móviles. |
| Tiempo empleado por acción temporizada | Tiempo empleado por acción temporizada. |

+++

+++ Buscar

| Nombre | Descripción |
|------|-------------|
| Motor de búsqueda | Motor de búsqueda. |
| Palabra clave del motor de búsqueda | Palabra clave del motor de búsqueda. |
| Motor de búsqueda natural | Motor de búsqueda natural. |
| Palabra clave del motor de búsqueda natural | Palabra clave natural del motor de búsqueda. |
| Motor de búsqueda de pago | Motor de búsqueda de pago. |
| Palabra clave de motor de búsqueda de pago | Palabra clave de pago del motor de búsqueda. |

+++

+++ Encuesta

| Nombre | Descripción |
|------|-------------|
| Encuesta | Encuesta. |
| Respuesta de encuesta | Respuesta de la encuesta. |
| Encuestas completadas | La encuesta finaliza. |
| Pregunta de encuesta | Pregunta de encuesta. |
| Encuestas iniciadas | Se inicia la encuesta. |

+++

+++ Web

| Nombre | Descripción |
|------|-------------|
| Tiempo promedio en la página | Tiempo medio de página. |
| Rechazos | Devoluciones. |
| Página de entrada | Página de entrada. |
| Salir de la página | Página de salida. |
| Página | Página. |
| Vistas de páginas | Vistas de página. |
| Remitente del reenvío | Referente. |
| Tipo de remitente | Tipo de referente. |
| Dominio de referencia | Dominio de referencia. |
| Dominio de referencia original | Dominio de referencia original. |
| Recargas | Recargas. |
| Visitas de página única | Visitas de página única. |
| Secciones del sitio | Secciones del sitio. |

+++

+++ B2B

| Nombre | Descripción |
|------|-------------|
| Nombre de la cuenta | Nombre de la cuenta. |
| Nombre del grupo de compras | Nombre del grupo de compra |
| Nombre de oportunidad | Nombre de oportunidad |

+++

+++ Content Analytics

| Nombre | Descripción |
|------|-------------|
| Resto absoluto de recurso | Recurso Absoluto Izquierdo. |
| Máximo absoluto del recurso | Superior absoluto de recurso. |
| Atributos del recurso | Atributos del recurso. |
| Colores de fondo de recursos | Colores de fondo del recurso. |
| Posiciones de cámara del recurso | Posiciones de cámara de activos. |
| Proximidades de la cámara de recursos | Proximidad de la cámara. |
| Configuración de cámara de recursos | Ajustes de cámara de recursos. |
| Clics en recursos | Clics en recursos. |
| Recurso creado por | Recurso creado por. |
| Fecha de creación del recurso | Fecha de creación del recurso.e |
| Altura de visualización del recurso | Altura de visualización del recurso. |
| Anchura de visualización del recurso | Anchura de visualización de recursos. |
| Colores de primer plano de recursos | Colores de primer plano de recurso. |
| ID de recurso | ID de recurso. |
| Tipos de imagen del recurso | Tipos de imagen de recurso. |
| Última actualización del recurso por | Última actualización del recurso. |
| Fecha de última actualización del recurso | Fecha de última actualización del recurso. |
| Condiciones de iluminación de recursos | Condiciones de alumbrado de los activos. |
| URL de vínculo del recurso | URL de vínculo de recurso. |
| Nombre del recurso | Nombre del recurso. |
| Categorías de personas del recurso | Categorías de personas de recursos. |
| ID de percepción del recurso | Identificador único de recursos que son perceptivamente iguales. |
| Estilos de fotografía del recurso | Estilos de fotografía de recursos. |
| Escenas del recurso | Escenas de recursos. |
| Origen de recursos | Asset Source. |
| Etiquetas del recurso | Etiquetas de recursos. |
| Tipo de recurso | Tipo de recurso. |
| Vistas del recurso | Vistas de recursos. |
| Dispersión de la atención visual del recurso | Propagación de atención visual de recurso. |
| Densidad de contenido visual del recurso | Densidad del contenido visual del recurso. |
| Atributos de la experiencia | Atributos de experiencia. |
| Canal de la experiencia | Canal de experiencia. |
| Clics de la experiencia | Clics en experiencias. |
| Recuento de emojis de la experiencia | Experimente el recuento de emojis. |
| Recuento de hashtags de la experiencia | Recuento de Experience Hashtag. |
| Profundidad porcentual horizontal de la experiencia | Profundidad de porcentaje horizontal de la experiencia. |
| Palabras clave de la experiencia | Palabras clave de experiencia. |
| Emociones de marketing de la experiencia | Experimente las emociones de marketing. |
| Narrativas de la experiencia | Experimente las narrativas. |
| Estrategias de persuasión de la experiencia | Experimente Estrategias De Persuasión. |
| Legibilidad de la experiencia Recuento de palabras por número de frases | Legibilidad de la experiencia Recuento de palabras por número de frases. |
| Puntuación de legibilidad de la experiencia | Puntuación de legibilidad de la experiencia. |
| Recuento de frases de legibilidad de la experiencia | Recuento de oraciones de legibilidad de experiencia. |
| Recuento de palabras de detención de legibilidad de la experiencia | Legibilidad de la experiencia: detener el recuento de palabras. |
| Recuento de citas de texto de legibilidad de la experiencia | Recuento de comillas de texto de legibilidad de experiencia. |
| Recuento de palabras de legibilidad de la experiencia | Legibilidad de la experiencia Recuento de palabras. |
| Fuente de la experiencia | Experimente Source. |
| Tonos de la experiencia | Experimente tonos. |
| Profundidad porcentual vertical de la experiencia | Profundidad de porcentaje vertical de la experiencia. |
| Vistas de la experiencia | Vistas de experiencias. |

+++

+++ Journey Optimizer

| Nombre | Descripción |
|------|-------------|
| Error de acción (AJO) | Recuento de errores generados por acciones de recorrido. |
| Error de ejecución de la acción | Condición de error que impidió que Journey Runtime ejecutase la acción. |
| Etiqueta de acción (AJO) | El nombre para mostrar generado por el cliente del elemento con el que interactuó el usuario final. |
| Salidas alternativas (AJO) | El recuento de salidas que no se produjeron debido a que un perfil alcanzó un nodo final o falló debido a un error. |
| Instalaciones de aplicaciones (AJO) | Número de instalaciones de la aplicación. |
| Lanzamientos de la aplicación (AJO) | Número de veces que se inicia una aplicación móvil. |
| ID de lote (AJO) | GUID creado al invocar cada nueva instancia de lote para un recorrido programado o una acción de campaña. Por ejemplo: Si un Recorrido programado o una acción de campaña se ejecuta a las 8:00 y a las 10:00, habrá dos batchInstanceID diferentes. |
| Marca de tiempo de instancia de lote (AJO) | Marca de tiempo de la instancia de lote. |
| Salidas hacia otro sitio de canales de salida (obsoletas) | Recuento total de mensajes devueltos entre canales salientes. |
| Nombre de acción de la campaña (AJO) | El nombre de la acción de campaña. |
| ID de campaña (AJO) | El ID de la campaña. |
| Nombre de la campaña (AJO) | El nombre de la campaña. |
| ID de versión de la campaña (AJO) | El ID de versión de la campaña. |
| Canal | El canal con el que deben correlacionarse estos datos. |
| Clics (AJO) | Recuento total de clics en todos los canales. |
| Rechazos de la política de consentimiento (AJO) | Recuento de acciones de recorrido que se rechazan debido a una o más políticas de consentimiento. |
| Error de decisión de contenido (AJO) | Mensajes de error generados por los nodos de decisión de contenido del recorrido. |
| Errores de decisión de contenido (AJO) | Recuento de errores generados por los nodos de decisión de contenido del recorrido. |
| Nombre del nodo de decisión de contenido (AJO) | El nombre del nodo de decisión de contenido del recorrido. |
| ID de correlación | ID de correlación. |
| Recuento de ofertas (AJO) | El número de elementos de oferta de la propuesta. |
| Clave de enlace del elemento de decisión | Un identificador compuesto que combina el ID de elemento con el ID de solicitud de Experience Decisioning, lo que permite la persistencia de los datos entre interacciones. |
| Proveedor de decisiones (AJO) | El proveedor al que se le pidió que tomara la decisión. Esta dimensión se utiliza cuando varios servicios pueden tomar decisiones para la misma ubicación o actividad. |
| Proveedor de decisiones (mantenido) (AJO) | El proveedor de decisiones con enlace de persistencia habilitado. |
| ID de directiva de decisión (AJO) | El ID de la política de decisión utilizada a la hora de decidir qué elementos incluir en esta proposición. |
| Métrica Dedup (AJO) | Métrica de desduplicación. |
| Entregado (obsoleto) | Recuento total de mensajes entregados. |
| Visualizaciones (AJO) | Este recuento muestra los mensajes de AJO. Este recuento incluye las aperturas de correo electrónico, las visualizaciones web y las visualizaciones en la aplicación. Las plataformas móviles no informan de las visualizaciones de mensajes SMS y push, por lo que no se contabilizan. |
| Descartado (AJO) | Cuenta cada vez que el SDK de Adobe cierra el mensaje en la aplicación, independientemente de la acción que el usuario final elija para cerrarlo. |
| Id. del ensayo (AJO) | Identificador único del ensayo. |
| Aperturas de correo electrónico realizadas por bots (AJO) | Recuento total de aperturas de correo electrónico realizadas por bots. |
| Aperturas de correos electrónicos (AJO) | Recuento total de aperturas del correo electrónico. |
| Dominio del destinatario del correo electrónico (AJO) | Dominio de la dirección de correo electrónico. |
| Asunto del mensaje de correo electrónico | Asunto del correo electrónico, no personalizado. |
| ID de evento | Un identificador único para el evento de la serie temporal. |
| ID de criterios de salida (AJO) | El ID de los criterios de salida utilizados para determinar si debe salir del recorrido. |
| Nombre de los criterios de salida (AJO) | Nombre de los criterios de salida. |
| ID de experimento (AJO) | El ID del experimento. |
| Nombre del experimento (AJO) | El nombre del experimento. |
| Recuento de ofertas alternativas (AJO) | El número de ofertas de reserva. |
| Error de búsqueda | Condición de error que impidió que Journey Runtime ejecutase la búsqueda. |
| Clics de entrada (AJO) | Recuento total de clics en canales entrantes. |
| Rechazos entrantes (AJO) | Recuento total de rechazos en los canales entrantes. |
| Impresiones entrantes (AJO) | Recuento total de impresiones en los canales entrantes. |
| Envíos entrantes (AJO) | Recuento total de envíos entre canales entrantes. |
| Entrante activado (AJO) | El SDK de Adobe eligió mostrar la propuesta. Otros factores pueden impedir que se muestre realmente. |
| El tiempo de envío está optimizado (AJO) | ¿Está optimizada la ejecución del mensaje SendTimeOptimized? |
| Es un recorrido de prueba | ¿Forma parte el evento de la ejecución de un recorrido de prueba? |
| Es un mensaje de prueba (AJO) | ¿El mensaje se envía como una ejecución de prueba? |
| ID de elemento (mantenido) (AJO) | El ID del elemento con el enlace de persistencia habilitado. |
| ID de elemento (AJO) | El ID del elemento. |
| Nombre del elemento (AJO) | El nombre del elemento. |
| Nombre de elemento (mantenido) (AJO) | El nombre del elemento con enlace de persistencia habilitado. |
| Error de acción de recorrido (AJO) | Mensajes de error generados por acciones del recorrido. |
| Nombre del nodo de acción del recorrido | Nombre del nodo de la acción de recorrido. |
| Entradas del recorrido | Verdadero si el evento de paso era un evento de entrada de un recorrido correspondiente a un perfil. |
| Fin del recorrido (AJO) | El final del recorrido. |
| Nombre del nodo del evento de recorrido | Este valor se establece cada vez que se produce un segmento o un evento externo en un recorrido. |
| Motivo de exclusión del recorrido | Razón de la exclusión de la instancia de recorrido. |
| Nombre de regla de exclusión de recorrido | Nombre de la regla que provocó la denegación de entrada del recorrido. |
| Exclusiones del recorrido (AJO) | Indique si el evento de paso actual ha resultado en un descarte de recorrido para un perfil. Esto suele ocurrir debido a que se aplican reglas de límite o concurrencia, lo que impide una mayor progresión del recorrido. |
| Tipo de salida del recorrido (AJO) | El tipo de salida que se produjo para la instancia de recorrido. |
| Errores del recorrido | Proporciona el estado actual del paso que ha terminado de ejecutarse. |
| ID del recorrido | El ID del recorrido. |
| Nombre del recorrido | El nombre del recorrido. |
| Nombre y versión del recorrido | El nombre y la versión del recorrido. |
| ID de la versión del recorrido | El ID de versión del recorrido. |
| JourneyExits | Verdadero si el paso actual ha llevado a la finalización de una instancia del recorrido. Este es el último paso de un recorrido en el que un perfil determinado se ha ejecutado correctamente. |
| Conversiones de páginas de destino (AJO) | Recuento total de conversiones en la página de destino. |
| ID de la página de destino (AJO) | Identificador único de la página de destino. |
| Fuente de la página de destino (AJO) | La fuente de la página de destino. |
| Vistas de página de destino (AJO) | Recuento total de vistas en la página de destino. |
| Clics en la página de aterrizaje (AJO) | Recuento total de clics en la página de destino. |
| URL del vínculo (AJO) | La URL en la que el usuario hizo clic. |
| Motivo del rechazo del mensaje (AJO) | El motivo del rechazo del mensaje. |
| Motivo del error del mensaje (AJO) | El motivo del error del mensaje. |
| Motivo de exclusión del mensaje (AJO) | Razón de exclusión. |
| Categoría de fallo de mensaje (AJO) | Categoría de error |
| Motivo del fallo del mensaje (AJO) | Razón del error. |
| Tipo de fallo de mensaje (AJO) | Tipo de error. |
| ID del mensaje (AJO) | El ID del mensaje con el que deben correlacionarse estos datos. |
| Idioma del mensaje (AJO) | El idioma del mensaje. |
| Nombre del mensaje (AJO) | Nombre del mensaje. |
| Reintento de mensaje (AJO) | Recuento de reintentos. |
| Estado del mensaje (AJO) | Estado del mensaje (por ejemplo, enviado, devuelto, error, etc.) |
| Tipo de mensaje (AJO) | Si el mensaje es de marketing o transaccional. |
| Estado de comentarios del mensaje (obsoleto) | Estado de los comentarios. |
| Entradas del nodo | Verdadero si el evento de paso era un evento de entrada de un nodo correspondiente a un perfil. |
| ID del nodo | El ID del nodo del recorrido. |
| Nombre del nodo | El nombre del nodo del recorrido. |
| Tipo de nodo | El tipo de nodo del recorrido. |
| Espacio de nombres de identidad de acción de la campaña orquestada (AJO) | El área de nombres de identidad de la acción de campaña orquestada. |
| Nombre de acción de la campaña orquestada (AJO) | Nombre de la acción de la campaña orquestada. |
| ID del nodo de acción de la campaña orquestada (AJO) | El ID de acción de la campaña orquestada. |
| ID de campaña orquestada (AJO) | El ID de la campaña orquestada. |
| Nombre de la campaña orquestada (AJO) | Nombre de la campaña orquestada. |
| ID de versión de la campaña orquestada (AJO) | ID de versión de la campaña orquestada. |
| Clics salientes (AJO) | Recuento total de clics en los canales salientes. |
| Errores salientes (obsoleto) | Recuento total de mensajes con errores en los canales salientes. |
| Exclusiones salientes (obsoleto) | Recuento total de eventos de exclusión en canales salientes. |
| Envíos salientes (obsoleto) | Recuento total de mensajes enviados entre canales salientes. |
| Punto de interés | punto de interés. |
| ID de la propuesta (AJO) | El ID de la propuesta. |
| Acciones personalizadas push (AJO) | Recuento del total de acciones personalizadas en la interacción push. |
| Interacciones push (AJO) | Número de veces que se inicia una aplicación móvil debido a una interacción directa de mensaje push. |
| Plataforma de push (AJO) | Servicio de proveedor push, por ejemplo, APNS o FCM. |
| Título push | Título de mensaje push, no personalizado. |
| ID de estrategia de clasificación (AJO) | El ID de estrategia de clasificación. |
| Nombre de la política de consentimiento rechazado | Nombre de la política de consentimiento rechazada correspondiente. |
| Recuento de reintentos (AJO) | Número de veces que se reintentó un envío de mensaje antes del éxito o el error. |
| Nombre de regla | Nombre de la regla que provocó la denegación de entrada del recorrido. |
| Tipo de selección (AJO) | Es el tipo de selección que se utiliza cuando se deriva un elemento como parte de una decisión. |
| Envíos (obsoleto) | Recuento del total de mensajes enviados a través de todos los canales. |
| Mensaje entrante SMS (AJO) | Respuesta de entrada de SMS como, por ejemplo, detener, iniciar, suscribirse, etc. |
| Mensajes entrantes SMS (AJO) | Respuesta a entrada de SMS, por ejemplo, detener, iniciar, suscribirse, etc. |
| Tipo de mensaje SMS (AJO) | Proveedor de SMS, por ejemplo, inbound, inboundReply o send. |
| Proveedor de SMS (AJO) | El proveedor de SMS, por ejemplo, Sinch o Twilio. |
| Denuncia de spam (AJO) | Recuento total de quejas de spam. |
| Nombre de estrategia (AJO) | Nombre de estrategia. El nombre de la estrategia de la que se derivó el elemento. |
| Nombre de estrategia (mantenido) (AJO) | El nombre de la estrategia con enlace de persistencia habilitado. |
| Adiciones a la lista de suscripción (AJO) | Recuento total de adiciones a una lista de suscripción. |
| ID de la lista de suscripción (AJO) | Identificador único de la lista de suscripción. |
| Eliminaciones de la lista de suscripción (AJO) | Recuento total de eliminaciones de una lista de suscripción. |
| Superficie (AJO) | La superficie de canal en la que apareció el mensaje. |
| Segmentado (obsoleto) | Hace un recuento del número de veces que una propuesta se ha dirigido a una persona. Es el número de veces que se ha considerado una propuesta para mostrarla a una persona. |
| Nombre de regla de segmentación (AJO) | El nombre de la regla de segmentación. |
| Evento de prueba (AJO) | Evento de prueba. |
| Tiempo para el inicio | Hora de inicio. |
| Duración total del búfer | Duración total del búfer. |
| Duración de la pausa | Duración total de la pausa. |
| Tipo de tráfico (AJO) | El tipo de tráfico de clasificación. |
| ID de tratamiento (AJO) | El ID del tratamiento seleccionado para el experimento. |
| Nombre del tratamiento (AJO) | El nombre del tratamiento del experimento. |
| Visitantes únicos del experimento (AJO) | Los visitantes únicos del experimento. |
| Bajas (AJO) | Recuento del total de bajas. |
| Etiqueta de URL (AJO) | Etiqueta descriptiva de la URL |
| ID de URL (AJO) | Identificador único de la URL en la que ha hecho clic el usuario. |

+++
